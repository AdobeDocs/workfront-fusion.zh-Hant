---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 從您的擴充功能呼叫Workfront和Fusion API
description: 從您的擴充功能呼叫Workfront和Fusion API
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 925a8ee910434c474d527c2914897d7c42e4a3d1
workflow-type: tm+mt
source-wordcount: 1083
ht-degree: 0%

---


# 從您的擴充功能呼叫Workfront和Fusion API

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

Fusion內容參考會提供您登入使用者的IMS權杖，因此自然而然的下一步是呼叫Workfront或Fusion API並顯示真實資料。 這是因為CORS。 本文說明如何使用App Builder執行階段動作做為伺服器端Proxy來繞過此限制，並包含範例（事件訂閱儀表板）。

## 為何直接瀏覽器呼叫失敗(CORS)

您的可見UI會在Adobe的CDN (`https://<your-app>.adobeio-static.net`)所提供的`<iframe>`中執行。 當該頁面對&#x200B;**不同**&#x200B;來源上的Workfront或Fusion API執行`fetch(...)`操作時，瀏覽器會強制執行跨來源資源共用(CORS)。 除非API針對您的CDN來源明確傳回`Access-Control-Allow-Origin`，否則瀏覽器會封鎖回應。 這些API不允許列出任意擴充功能來源，因此來自訪客的直接呼叫會失敗。

如需CORS的相關資訊，請參閱[CORS](https://developer.mozilla.org/docs/Web/HTTP/CORS)。

## 在沒有CORS的情況下呼叫您自己的執行階段動作

此問題的修正是呼叫您自己的執行階段動作，而不使用CORS。

App Builder應用程式可包含執行階段動作，這些是在伺服器端Adobe I/O Runtime上執行的小型無伺服器函式。 伺服器對伺服器呼叫不受瀏覽器CORS限制。 而且由於動作屬於應用程式的一部分，訪客可使用相對URL呼叫它，該URL為相同來源，因此不會遭到封鎖。

```
  Guest UI (browser, adobeio-static.net)
     │  fetch('/api/v1/web/<app>/wf-proxy?...')   ← relative = same-origin, no CORS
     ▼
  Your runtime action  (Adobe I/O Runtime, server-side)
     │  fetch('https://fusion.adobe.com/api/v3/...')  ← server-to-server, no CORS
     ▼
  Workfront / Fusion API
```

動作會從訪客接收使用者的IMS權杖並將其轉送至上游，因此仍會代表使用者使用其許可權發出呼叫。

## 步驟1：宣告動作

執行階段動作會在`app.config.yaml`中宣告於擴充功能的`runtimeManifest`之下。 在您的擴充功能旁新增`wf-proxy`動作：

```yaml
extensions:
  fusion/nav-organization/1:
    $include: src/fusion-nav-organization-1/ext.config.yaml
    runtimeManifest:
      packages:
        fusion-uix-guest:                # ← your package name; part of the action URL
          license: Apache-2.0
          actions:
            wf-proxy:
              function: src/fusion-nav-organization-1/actions/wf-proxy/index.js
              web: 'yes'                  # exposes it at /api/v1/web/<package>/wf-proxy
              runtime: nodejs:22
              inputs:
                LOG_LEVEL: debug
              annotations:
                require-adobe-auth: false # see note below
                final: true
```

此動作在下列位置變為可存取：

```
/api/v1/web/<package>/<action>     e.g.  /api/v1/web/fusion-uix-guest/wf-proxy
```

### `require-adobe-auth`： true與false

此註解會控制Adobe的閘道是否在您的動作執行前驗證IMS權杖。

* **`true`：**&#x200B;安全預設值。  閘道會拒絕未驗證的呼叫。 不過，驗證器會嚴格限制所預期的標頭，且可能會拒絕請求或捨棄上游呼叫所需的自訂標頭。 如果發生這種狀況，即使您的權杖有效，也會顯示為`401`。
* **`false`：**&#x200B;略過閘道檢查。 然後您的動作會公開叫用，因此您&#x200B;**必須**&#x200B;自己強制執行授權。 動作中需要`Authorization`持有者，如果遺失則拒絕，然後向上游轉送，由Workfront和Fusion驗證。 結合步驟2中所述的嚴格目標允許清單，這是需要傳遞自訂標題的Proxy的可靠路徑。

>[!TIP]
>
> 請先試用`true`。 如果您看見無法說明的`401`，因為權杖有效且在其他位置運作，請切換至`false` **且**&#x200B;保留動作中的持有者支票與允許清單，這樣安全性仍會強制上游執行。

## 步驟2：為已加入允許清單的Proxy寫入動作

建立`src/fusion-nav-organization-1/actions/wf-proxy/index.js`。 有兩個規則可保持此安全性：上游目標的允許清單（此動作不可作為開放轉送）以及轉送上游的必要持有人權杖。

```js
const fetch = require('node-fetch')
const { Core } = require('@adobe/aio-sdk')
const { errorResponse, getBearerToken, checkMissingRequestInputs } = require('../utils')

// Page-through query params (see "Paginate list results" below).
const pageQuery = (p) => {
  const q = new URLSearchParams()
  if (p.start != null) q.set('start', p.start)
  if (p.limit != null) q.set('limit', p.limit)
  return q
}

// Only these upstreams may be reached. Never build the URL from arbitrary input.
const TARGETS = {
  subscriptions: {
    method: 'GET',
    url: () => 'https://<your-wf-host>/attask/eventsubscription/api/v1/subscriptions',
  },
  hooks: {
    method: 'GET',
    // Fusion hooks are team-scoped: teamId is a REQUIRED query param (see below).
    url: (p) => {
      const q = pageQuery(p)
      if (p.teamId) q.set('teamId', p.teamId)
      return `https://fusion.adobe.com/api/v3/hooks?${q.toString()}`
    },
  },
  scenarios: {
    method: 'GET',
    url: (p) => {
      const q = pageQuery(p)
      if (p.fusionOrgId) q.set('organizationId', p.fusionOrgId)
      return `https://fusion.adobe.com/api/v3/scenarios?${q.toString()}`
    },
  },
}

async function main (params) {
  const logger = Core.Logger('main', { level: params.LOG_LEVEL || 'info' })
  try {
    const missing = checkMissingRequestInputs(params, ['target'], ['Authorization'])
    if (missing) return errorResponse(400, missing, logger)

    const target = TARGETS[params.target]
    if (!target) return errorResponse(400, `unknown target '${params.target}'`, logger)

    const token = getBearerToken(params)              // reads params.__ow_headers.authorization
    const headers = { authorization: `Bearer ${token}`, 'content-type': 'application/json' }
    if (params.orgId) headers['x-gw-ims-org-id'] = params.orgId        // Adobe IMS org id
    if (params.fusionOrgId) headers['x-organization-id'] = params.fusionOrgId  // Fusion tenant id
    if (params.teamId) headers['x-team-id'] = params.teamId            // Fusion team id

    const res = await fetch(target.url(params), { method: target.method, headers })
    const text = await res.text()
    let body
    try { body = JSON.parse(text) } catch (e) { body = text }

    if (!res.ok) {
      return { statusCode: res.status, body: { error: `upstream ${res.status}`, target: params.target, details: body } }
    }
    return { statusCode: 200, body }
  } catch (error) {
    logger.error(error)
    return errorResponse(500, 'server error: ' + error.message, logger)
  }
}

exports.main = main
```

`getBearerToken`、`errorResponse`和`checkMissingRequestInputs`來自產生的`actions/utils.js`，範本將它們支撐在那裡。 `getBearerToken`讀取`params.__ow_headers.authorization`，閘道會將傳入的`Authorization`標頭放在這個位置。

## 步驟3：從訪客呼叫動作

從您的UI中，`fetch`具有相對（相同來源） URL的動作，並以持有者身分傳送IMS權杖。 以查詢引數的形式傳遞上游所需的組織和團隊ID。

```js
const PROXY_URL = "/api/v1/web/fusion-uix-guest/wf-proxy";

async function callProxy(target, token, { imsOrgId, fusionOrgId, teamId, start, limit } = {}) {
  const params = new URLSearchParams({ target });
  if (imsOrgId) params.set("orgId", imsOrgId);          // → x-gw-ims-org-id
  if (fusionOrgId) params.set("fusionOrgId", fusionOrgId); // → x-organization-id
  if (teamId) params.set("teamId", teamId);             // → x-team-id
  if (start != null) params.set("start", start);        // pagination offset
  if (limit != null) params.set("limit", limit);        // pagination page size
  const res = await fetch(`${PROXY_URL}?${params.toString()}`, {
    headers: { authorization: `Bearer ${token}` },
  });
  if (!res.ok) throw new Error(`${target} request failed: ${res.status}`);
  return res.json();
}
```

從內容取得`token`、`imsOrgId`、`fusionOrgId`和`teamId`：

```js
const token       = connection.sharedContext.get("imsToken");
const imsOrgId    = connection.sharedContext.get("imsOrgId");
const fusionOrgId = connection.sharedContext.get("organization")?.id; // Fusion tenant id
const teamId      = connection.sharedContext.get("team")?.id;
```

如需內容的相關資訊，請參閱[Fusion內容參考](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)。

## Fusion v3 API細節

針對`https://fusion.adobe.com/api/v3`的儀表板適用的內容：

| 頁首/引數 | 值 | 附註 |
| ---------------- | ------- | ------- |
| `Authorization` | `Bearer <imsToken>` | 來自內容的使用者IMS權杖。 |
| `x-organization-id` | `organization.id` | Fusion自己的租使用者ID，而不是IMS組織ID。 Fusion會以此來識別租使用者。 |
| `x-team-id` | `team.id` | 當通話屬於團隊範圍時傳送。 |
| `x-gw-ims-org-id` | `imsOrgId` | 閘道的Adobe IMS組織ID。 |

請注意下列警告：

* **`GET /api/v3/hooks`是團隊範圍：** `teamId`是&#x200B;**必要的查詢引數** (`/api/v3/hooks?teamId=...`)。 沒有它，您會得到`400`。 這表示勾點只會針對&#x200B;*作用中團隊回來*；以涵蓋組織、回圈團隊和合併。
* **`GET /api/v3/scenarios`**&#x200B;與`organizationId` (`/api/v3/scenarios?organizationId=...`)搭配使用。

>[!NOTE]
>
> 官方參考為Adobe的[Workfront Fusion API](https://developer.adobe.com/workfront-fusion-apis/)。 標頭/驗證需求因閘道而異。 此表格會反映實際所需的示範專案。 如果呼叫傳回`401`/`400`，請先重新檢查這些標頭。

## 分頁清單結果

Fusion v3清單端點（鉤點、案例）一次傳回一個&#x200B;**頁面**，而不是整個集合。 回應如下所示：

```json
{
  "items": [ /* ...this page of records... */ ],
  "_page": { "start": 0, "limit": 100, "total": 342 }
}
```

記錄在&#x200B;**`items`**&#x200B;之下，分頁中繼資料在&#x200B;**`_page`**&#x200B;之下。 您使用&#x200B;**`start`** （位移）和&#x200B;**`limit`** （頁面大小）查詢引數來頁面。 以上的Proxy會同時傳遞，因此在收集所有內容之前，請以循環方式在訪客中建立頁面：

```js
const PAGE_LIMIT = 100;

async function fetchAllPages(target, token, opts = {}) {
  const all = [];
  let start = 0;
  // Stop when a page returns fewer than PAGE_LIMIT items, or when _page.total is reached.
  for (;;) {
    const res = await callProxy(target, token, { ...opts, start, limit: PAGE_LIMIT });
    const items = res.items ?? [];
    all.push(...items);

    const total = res._page?.total;
    const done = items.length < PAGE_LIMIT || (total != null && all.length >= total);
    if (done) break;
    start += PAGE_LIMIT;
  }
  return all;
}
```

若您想讓分頁離開瀏覽器，請在執行階段動作內執行相同的回圈，並在一個回應中傳回合併的`items`陣列。 無論如何，請勿假設第一頁是整個結果集。 如果團隊擁有多頁鉤點，則團隊會看起來像是缺少情境。

## 安全性檢查清單

* **允許清單上游。** 切勿從原始使用者端輸入建構目標URL。 如步驟2所示，將短的`target`金鑰對應至固定URL。 這可防止您的動作變成開放式轉送。
* **在動作中需要持有人權杖**，並將其向上游轉送。 讓Workfront和Fusion強制執行使用者的許可權。
* **永遠不要記錄權杖。** `imsToken`是認證。 讓`LOG_LEVEL`留意`stringParameters`列印的內容。
* **僅透過HTTPS**&#x200B;轉送到信任的Adobe和Workfront主機。

## 工作範例：事件訂閱儀表板

示範儀表板會聯結三個來源，針對每個Workfront事件訂閱顯示相符的Fusion案例是否狀況良好：

1. `fetchSubscriptions()`個→件訂閱（含已接收/通過的計數器）。
1. 使用中團隊的`fetchHooks(teamId)`個→ Fusion鉤點（以`fetchAllPages`分頁）。
1. 組織的`fetchScenarios(fusionOrgId)`→ Fusion案例（以`fetchAllPages`分頁）。

**join**&#x200B;會連結它們，但值得指出的是：Workfront訂閱和它的Fusion連結指向&#x200B;**不同主機**&#x200B;上的即時狀態，因此它們的URL欄位不是逐位元組相等。 穩定是webhook URL **（最後一個路徑區段）結尾的**&#x200B;權杖。 符合該結尾語彙基元，而非完整URL。 接著，勾點的`scenarioId`會符合情境的`id`：

```
subscription.targetUrl  ──(trailing token)──▶  hook.url
                                                hook.scenarioId  ──▶  scenario.id
```

```js
// Reduce a webhook URL to its trailing token so hosts/bases can differ.
function hookKey(url) {
  if (!url) return "";
  const path = String(url).trim().toLowerCase().split(/[?#]/)[0].replace(/\/+$/, "");
  const i = path.lastIndexOf("/");
  return i >= 0 ? path.slice(i + 1) : path;
}

// Index hooks by token, then look each subscription up by the same token.
const hooksByToken = new Map(hooks.map((h) => [hookKey(pick(h, ["url", "address", "targetUrl"], "")), h]));
const hook = hooksByToken.get(hookKey(pick(sub, ["url", "endpointUrl", "targetUrl", "target.url", "callbackUrl"], "")));
```

狀態衍生自聯結：

* **已中斷**：沒有相符的連結，或連結是`gone`。
* **篩選**：相符，但`passed < received` （事件已送達，但在案例執行前已篩選掉）。
* **狀況良好**：符合併通過。

由於實際的裝載形狀不同，使用者端會防禦性地對應欄位，對每個欄位嘗試數個候選金鑰，因此API的細微差異不會破壞表格：

```js
function pick(obj, keys, fallback) {
  for (const key of keys) {
    const value = key.split(".").reduce((acc, part) => (acc == null ? acc : acc[part]), obj);
    if (value != null) return value;
  }
  return fallback;
}
```

這只是個範例。 相同的Proxy模式適用於您需要的任何Workfront或Fusion API。

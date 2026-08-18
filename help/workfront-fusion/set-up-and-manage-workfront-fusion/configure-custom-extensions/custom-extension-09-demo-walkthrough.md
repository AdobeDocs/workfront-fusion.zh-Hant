---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 自訂擴充功能的示範
description: 自訂擴充功能的示範
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 964
ht-degree: 0%

---


# 在Fusion中建立自訂擴充功能的示範

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

此示範會逐步說明如何建立自訂擴充功能、部署該擴充功能，以及在Fusion中加以執行。

其功能包括:

* 從一般App Builder殼層範本建立Experience Cloud應用程式架構。
* 將應用程式重新鎖定為Fusion擴充功能點。
* 將應用程式部署至中繼工作區。
* 在Fusion中開啟中繼測試，並顯示應用程式執行中。

從範本開始而不是空的`--standalone-app`表示已為您產生SPA啟動程式： `index.js`、`exc-runtime.js`、`App.js` （含路由及`ErrorBoundary`）以及範例`ExtensionRegistration`。 示範中的即時步驟是重新鎖定設定並編輯兩個檔案，這恰恰是實際`fusion-uix-guest`的建置方式。

>[!NOTE]
>
> **時間：**&#x200B;您的工具設定後，即時示範需要約10分鐘的時間。 您必須在&#x200B;**示範之前**&#x200B;執行一次性設定（節點18/20、`aio` CLI、`aio login`）。 如需指示，請參閱[設定UI擴充功能工具和帳戶](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)。


## 開始之前

此作業只需執行一次，且可在示範前於相機外執行。

```sh
node --version          # must be 18 or 20
aio --version           # @adobe/aio-cli installed
aio login               # signs you into your Adobe org
aio console org select  # pick the org you'll demo in (same org as Fusion)
```

示範組織中必須具備兩個條件：

* 已為組織上線`fusion/nav-organization/1`擴充點。 如果未上線，則部署會失敗，並出現錯誤1060。 如需詳細資訊，請參閱[疑難排解自訂擴充功能](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)。
* 自訂擴充功能會在Fusion主機中啟用。 （此功能預設為開啟）。 由於您將展示Stage組建而非發佈的組建，因此您也會在Fusion設定檔中開啟&#x200B;**Stage擴充功能**&#x200B;開關。 （此切換如步驟7所示。） 在您執行之前，Fusion只會顯示已發佈的擴充功能。

## 步驟1：從通用範本產生應用程式

```sh
aio app init my-fusion-extension --template @adobe/generator-app-excshell
cd my-fusion-extension
```

* 選取&#x200B;**出現提示時建立新專案**，並接受建議的名稱。
* `@adobe/generator-app-excshell`是通用的&#x200B;**Experience Cloud Shell** UI擴充功能範本，不是產品專屬的。 它會在`src/dx-excshell-1/`底下建立完整且運作中的SPA。

>[!NOTE]
>
>如果您偏好此功能表，請執行`aio app init my-fusion-extension`，選擇&#x200B;**新增擴充功能或獨立應用程式** > **範本**，然後選取&#x200B;**「適用於Experience Cloud Shell的App Builder UIX擴充功能」**。

您將會取得一組檔案，包括下列專案：

```
my-fusion-extension/
|-- app.config.yaml
|-- src/dx-excshell-1/
    |-- ext.config.yaml
    |-- web-src/src/
        |-- index.js          // SPA bootstrap (exc-app Runtime + React render)
        |-- exc-runtime.js    // Experience Cloud Shell runtime glue
        |-- components/
            |-- App.js                    // Router + ErrorBoundary (generated)
            |-- ExtensionRegistration.js  // sample registration (generated)
```

## 步驟2：新增Fusion來賓程式庫

範本已包含React、React Spectrum和exc-app。 新增與Fusion主機對話的程式庫：

```sh
npm install @adobe/uix-guest
```

## 步驟3：將設定重新鎖定為Fusion

開啟&#x200B;**`app.config.yaml`**&#x200B;並只將&#x200B;**擴充點索引鍵**&#x200B;從Experience Cloud Shell點變更為Fusion點（保留`$include`路徑不變）：

```yaml
extensions:
  fusion/nav-organization/1:                 # was: dx/excshell/1
    $include: src/dx-excshell-1/ext.config.yaml
```

您不需要變更config中的其他任何專案。 資料夾名稱`dx-excshell-1`是內部名稱，不會影響Fusion，因此您可以離開它。 重新命名也代表要更新任何動作路徑。 略過以觀看示範。

>[!NOTE]
>
>如果您正在定位&#x200B;**團隊**&#x200B;區段，請改用`fusion/nav-team/1`。 若要將&#x200B;**同時**&#x200B;個組織和團隊運送到生產環境，請使用&#x200B;**兩個不同的專案**。 每個登入名稱一個擴充點套件組合可避免共用應用程式衝突。

## 步驟4：編輯註冊和Widget檔案

所有路徑都在`src/dx-excshell-1/web-src/src/components/`之下。

### **`ExtensionRegistration.js`**

產生的檔案會註冊Experience Cloud殼層範例。 以Fusion **`dashboard.getWidget`**&#x200B;合約取代其`methods`，讓Fusion知道您的標題和UI所在的位置：

```js
import { Text } from "@adobe/react-spectrum";
import { register } from "@adobe/uix-guest";
import metadata from "../../../../app-metadata.json";
import { extensionId } from "./Constants";

function ExtensionRegistration() {
  const init = async () => {
    await register({
      id: extensionId,
      metadata,
      methods: {
        dashboard: {
          getWidget() {
            return {
              id: extensionId,
              title: "My Fusion tool",          // label on the Fusion nav button
              description: "Hello from App Builder",
              url: "/index.html#/widget",       // route to the visible UI (4b)
              widgetSize: { defaultWidth: 6, defaultHeight: 6 },
              hideWidgetHeader: false,
            };
          },
        },
      },
    });
  };
  init().catch(console.error);

  return <Text>Registering with Fusion...</Text>;
}

export default ExtensionRegistration;
```

如果`Constants.js`不存在於其旁，請建立它：

```js
module.exports = { extensionId: "my-fusion-extension" };
```

### `DashboardWidget.js`

建立此檔案。 它會完成交握並顯示即時Fusion內容：

```js
import { useEffect, useState } from "react";
import { Flex, Heading, Text, View } from "@adobe/react-spectrum";
import { attach } from "@adobe/uix-guest";
import { extensionId } from "./Constants";

const KEYS = ["imsOrgId", "imsUserId", "organization", "team", "user"];

export default function DashboardWidget() {
  const [ctx, setCtx] = useState(null);

  useEffect(() => {
    attach({ id: extensionId })
      .then((guest) => {
        const read = () =>
          KEYS.reduce((acc, k) => ({ ...acc, [k]: guest.sharedContext.get(k) }), {});
        setCtx(read());
        guest.addEventListener("contextchange", () => setCtx(read()));
      })
      .catch((e) => console.error("attach failed", e));
  }, []);

  return (
    <View padding="size-300">
      <Heading level={2}>Hello from App Builder</Heading>
      {!ctx ? (
        <Text>Connecting to Fusion...</Text>
      ) : (
        <Flex direction="column" gap="size-100" marginTop="size-200">
          <Text>User: {ctx.user?.name ?? ctx.imsUserId}</Text>
          <Text>Organization: {ctx.organization?.name} (id {ctx.organization?.id})</Text>
          <Text>Team: {ctx.team?.name ?? "-"}</Text>
        </Flex>
      )}
    </View>
  );
}
```

### `App.js`

產生的路由器已將`index` / `index.html`傳送至`ExtensionRegistration`。 為Widget新增路徑並匯入：

```js
import DashboardWidget from "./DashboardWidget";
// ...inside <Routes>, alongside the existing ExtensionRegistration routes:
<Route exact path="widget" element={<DashboardWidget />} />
```

> 路由路徑(`widget`)必須符合`getWidget().url` (`/index.html#/widget`)中的雜湊。 將產生的`index.js` / `exc-runtime.js`與`App.js`的其餘部分維持原狀，因為這是您希望範本提供的啟動程式。

## 步驟5：建置

```sh
aio app build
```

這會編譯前端並執行產生`app-metadata.json`的中繼資料連結。 請先修正任何錯誤，然後再繼續。

## 步驟6：部署至中繼

```sh
aio console workspace select     # choose Stage
aio app deploy
```

`deploy`在Adobe的CDN上託管您的UI，並在Stage工作區中註冊擴充功能端點，以便Fusion能夠探索到它。 CLI會列印端點URL，例如`https://<project>-stage.adobeio-static.net`。

## 步驟7：開啟中繼測試並在Fusion中顯示擴充功能

1. Experience Cloud上的Open Fusion，已登入您部署至的相同組織。
1. 開啟使用者頭像功能表，然後前往&#x200B;**產品設定** > **Fusion設定檔** > **偏好設定**。
1. 開啟&#x200B;**階段擴充功能**&#x200B;切換器，並確認重新載入。

   Fusion現在會從Stage工作區載入擴充功能，並將其標示為&#x200B;**(Stage)**。
1. 前往左側導覽的&#x200B;**組織**&#x200B;區域。

   您的&#x200B;**「我的Fusion工具（階段）」**&#x200B;按鈕出現。
1. 按一下&#x200B;**「我的Fusion工具（舞台）」**&#x200B;按鈕。
您的UI會載入主面板，並顯示即時使用者、組織和團隊。
1. **在Fusion中切換使用中的組織或團隊**。

   面板更新，示範即時內容(`contextchange`)。

>[!TIP]
>
>如果按鈕未出現，請重新載入一次，因為每個工作階段都會快取探索。 請參閱[疑難排解自訂擴充功能](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)。


## 在示範期間反複執行

進行變更，然後重建並重新部署。  使用者下次開啟擴充功能時，即可看到更新後的擴充功能。

```sh
aio app build && aio app deploy
```

## 示範後進入生產環境

Stage足以示範。 若要在整個組織內發行，請切換至生產工作區、部署並提交核准請求。 必須使用系統管理員角色提交請求。 如需完整程式，請參閱[在生產](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md#release-on-production)上發行。

## 示範談話追蹤（選擇性）

在即時示範期間，您可能會想要提出以下幾點：

* **「我從一般Experience Cloud殼層範本開始。」** 它以整個SPA Shell為基礎，因此我只會重新鎖定擴充功能點，並編輯兩個檔案。
* **&quot;Fusion是主機，我的應用程式是來賓。&quot;** 它們在不同的框架中執行，並討論Adobe的UI擴充性SDK，沒有自訂網路。
* **&quot;註冊與檢視&quot;** 隱藏框架&#x200B;*註冊*&#x200B;我提供的內容(`dashboard.getWidget`)，可見框架&#x200B;*附加*&#x200B;並讀取內容。
* **「中繼測試是每個使用者的切換。」** Fusion預設只會顯示已發佈的擴充功能。 我在Fusion設定檔中翻轉Stage擴充功能，以載入我的Stage組建，無需生產版本。
* **「即時內容」。** 切換組織或團隊會重新傳送內容，而訪客會重新呈現。

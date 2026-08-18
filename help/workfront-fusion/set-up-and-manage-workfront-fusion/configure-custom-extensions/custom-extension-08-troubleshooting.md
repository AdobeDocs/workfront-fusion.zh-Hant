---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 疑難排解自訂擴充功能
description: 疑難排解自訂擴充功能
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
source-wordcount: 1136
ht-degree: 0%

---


# 疑難排解自訂擴充功能

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

本文針對建立自訂擴充功能時最有可能遇到的問題，提供一些解決方案，大致依照開發期間發生問題的順序進行。

## 快速檢查清單

如果某些功能無法運作，請先確認下列事項：

* Node.js的版本為18或20 (`node --version`)。
* 您已登入(`aio login`)且使用正確的組織/專案/工作區(`aio console where`)。
* 擴充點名稱完全相符，包括版本： `fusion/nav-organization/1`。
* `getWidget()`中的`url`符合您應用程式中的路由。
* 您可見的UI呼叫`attach({ id })`。
* 您在Fusion中檢視一組正確的擴充功能：
  * 若要檢視Stage組建，請部署到Stage，並在Fusion設定檔中開啟Stage擴充功能開關（「產品設定> Fusion設定檔>偏好設定」）。
  * 若要檢視已發佈的擴充功能，請部署至生產環境並取得核准。

## 錯誤1060：「擴充功能點不存在」

**完整訊息：** `aio app deploy`期間`CoreConsoleAPISDK ... 1060: Extension point 'fusion/nav-organization/1' does not exist`。

**含義：**&#x200B;您的Adobe組織尚未啟用Fusion擴充點（「已上線」）。 Adobe會在部署時驗證擴充功能點存在於貴組織的目錄中。 **不是**&#x200B;您的程式碼或YAML有問題。

**修正：**&#x200B;要求Fusion團隊加入您IMS組織的擴充點（`fusion/nav-organization/1`和/或`fusion/nav-team/1`）。 當您要求上線時，請包括：

* 您的&#x200B;**IMS組織ID** (`XXXX@AdobeOrg`)，
* 您所需的&#x200B;**延伸點**，
* 您的&#x200B;**Developer Console專案和工作區**&#x200B;名稱。

一旦確認上線，請重新執行`aio app deploy`。


## 「正在等待來自目標iframe的初始訊息」/面板永遠旋轉

**表示：** Fusion已開啟您可見的UI，但未完成交握，因此Fusion逾時。

**常見原因：**

* `attach`只存在於註冊元件中，不在可見的Widget中。
* `getWidget()`中的`url`指向轉譯&#x200B;**註冊**&#x200B;元件（或空白頁面）而不是您的Widget的路由。
* 傳遞至`attach`的`id`與`register`中使用的`id`不同。 它們必須相同，所以兩者都保留在`Constants.js`中。

**修正：**&#x200B;確定您的&#x200B;**可見**&#x200B;元件呼叫`attach({ id })`：

```jsx
useEffect(() => {
  attach({ id: extensionId }).catch(console.error);
}, []);
```

如需詳細資訊，請參閱[建置自訂擴充功能UI](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)。



## 導覽按鈕未出現在Fusion中

如果您的自訂擴充功能的導覽按鈕未出現在Fusion中，請依序檢查下列專案：

1. **您所檢視的擴充功能是否正確組合？** 依預設，Fusion只會顯示已部署到生產環境並核准的已發佈擴充功能。 如果您正在測試Stage組建，請在Fusion設定檔（「產品設定」>「Fusion設定檔」>「偏好設定」）中開啟Stage擴充功能開關，然後重新載入。 階段專案標籤為&#x200B;**（階段）**。
如需詳細資訊，請參閱[發佈您的自訂擴充功能](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)。
1. **是撤銷還是撤銷？** 已撤銷或撤銷的擴充功能在Fusion中停止顯示且沒有錯誤。 如果先前執行的按鈕消失，在尋找程式碼問題之前，請先確認該按鈕在Adobe Exchange中仍為作用中。
1. **是否已部署到正確的工作區？** 部署至您實際載入的工作區，也就是使用中繼測試開關時的中繼工作區。
1. **是否已部署至正確的組織？** 使用您部署至的&#x200B;**相同** IMS組織中的帳戶登入Fusion。
1. **它是否在正確的區段中？** `fusion/nav-organization/1`顯示在&#x200B;**組織**&#x200B;下；`fusion/nav-team/1`顯示在&#x200B;**團隊**&#x200B;下（您必須先選取團隊）。
1. **是否有擴充點名稱拼寫錯誤？** 它必須正確地讀取`app.config.yaml`和資料夾的`ext.config.yaml`包含路徑中的`fusion/nav-organization/1`。


## 按鈕出現，但面板為空白

如果按鈕出現但面板為空白，請檢查下列專案：

* **路由不符：**&#x200B;來自`getWidget()` （例如`/index.html#/my-widget`）的`url`必須符合`App.js`中的`<Route>`。 不相符的專案會載入不含元件的頁面。
* **JavaScript錯誤：**&#x200B;請開啟瀏覽器的開發人員工具(F12) > **主控台**&#x200B;標籤，並尋找來自iframe的錯誤。 修正回報的錯誤並重新部署。
* **標題遺失/重複： `getWidget()`中的** `hideWidgetHeader`控制Fusion是否在您的UI上方顯示標題。 如果您轉譯自己的標頭，請將其設為`true`。

## iframe已封鎖（內容安全性原則/「拒絕框架」）

Fusion只允許在Adobe的App Builder CDN (`*.adobeio-static.net`)上託管的擴充功能，預設為`aio app deploy`放置您的檔案。 如果您將UI託管在其他位置，例如自訂網域，Fusion會拒絕載入它。 透過記錄的App Builder部署，或詢問Fusion團隊您的網域是否可以加入允許清單。

## 內容空白或過時

* **載入後立即清空：**&#x200B;在&#x200B;**`attach`解析後讀取內容**，而不是之前。 在此之前，會顯示「連線……」狀態。
* **當使用者切換組織或團隊時未更新：**&#x200B;訂閱`contextchange`事件並重新讀取處理常式中的金鑰。 如需詳細資訊，請參閱「建立自訂擴充功能UI」一文中的[閱讀內容Fusion共用](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md#read-the-context-fusion-shares)。
* **日期看起來錯誤：**&#x200B;日期欄位會以ISO **字串**&#x200B;送達，而非`Date`物件。 將它們包裝在`new Date(...)`中。 請參閱Fusion內容參考文章中的[日期](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md#dates)。

## 呼叫API失敗並出現CORS錯誤

**症狀：**&#x200B;當您的UI直接呼叫Workfront/Fusion API時，瀏覽器主控台顯示&#x200B;*「沒有&#39;Access-Control-Allow-Origin&#39;標頭」* （或要求遭到封鎖）。

**修正：**&#x200B;請勿從瀏覽器呼叫這些API。 透過您自己的App Builder **執行階段動作** （伺服器端，無CORS）路由呼叫，並讓訪客使用相對的同來源URL呼叫該動作。 如需詳細資訊，請參閱[呼叫Workfront與Fusion API](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)。


## 即使使用有效的權杖，Proxy動作也會傳回401

**含義：**&#x200B;透過`require-adobe-auth: true`，Adobe閘道會在您的動作執行前驗證呼叫，而且可以拒絕呼叫或卸除您的上游需求的自訂標頭，顯示為`401`。

**修正：**&#x200B;在動作&#x200B;**上設定`require-adobe-auth: false`且**&#x200B;自行強制執行授權。 動作中需要`Authorization`持有者、向上游轉送，並保留嚴格的目標允許清單。 請參閱[require-adobe-auth： true與false](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md#require-adobe-auth-true-vs-false)。

## 融合`GET /api/v3/hooks`傳回400

**含義：**&#x200B;掛接端點是&#x200B;**團隊範圍**，因此`teamId`是必要的查詢引數。

**修正：**&#x200B;呼叫`/api/v3/hooks?teamId=<team.id>`。 勾點只會為作用中團隊返回。 若要涵蓋組織，請循環其團隊並合併。 相反地，案例接受`organizationId`。 請參閱[Fusion v3 API細節](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md#fusion-v3-api-specifics)。


## `aio`個錯誤

* **`aio: command not found`：** CLI未安裝或未安裝在您的PATH上。 重新執行`npm install -g @adobe/aio-cli`，然後開啟新的終端機。
* **在全新的節點版本上建置/部署失敗：**&#x200B;使用節點&#x200B;**18或20 LTS**。 非常新的、非LTS發行版本有時會中斷工具鏈。
* **「您不是開發人員」/看不到您的組織：**&#x200B;您的Adobe組織管理員必須授與您此&#x200B;**開發人員**&#x200B;角色和App Builder存取權。 如需詳細資訊，請參閱[設定UI擴充功能工具和帳戶](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)。
* **401 /部署或探索期間的Token無效：**&#x200B;您的工作階段已過期或您正在混合環境。 執行`aio logout`然後`aio login`，確認`aio console where`，並部署至您正在載入的工作區。

## 收集支援資訊

收集這些資訊，以加快診斷速度：

* 您執行的確切命令和&#x200B;**完整**&#x200B;錯誤輸出。
* 您的&#x200B;**IMS組織識別碼**、**專案**&#x200B;和&#x200B;**工作區**。
* 您正在定位的&#x200B;**延伸點**。
* `aio app deploy`是否成功，以及擴充功能是否為&#x200B;**已發佈** （或者，對於Stage測試，Stage擴充功能開關是否開啟）。
* 在Fusion中開啟面板時，瀏覽器&#x200B;**主控台** (F12)發生任何錯誤。

---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 建立UI擴充性的專案
description: 建立UI擴充性的專案
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 1360
ht-degree: 0%

---

# 建立UI擴充性的專案

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

若要建立自訂UI擴充功能，您必須為其建立App Builder專案。

本頁說明如何使用`aio`命令列產生一般App Builder專案。 「一般」表示專案&#x200B;**不**&#x200B;是從產品特定的範本開始。 從一般應用程式開始，可讓專案變得簡單，並可與Workfront Fusion連線。

請務必熟悉下列有關建立專案以搭配Adobe Fusion AI擴充功能的概念和術語。

* **Adobe Developer Console** (<https://developer.adobe.com/console>)是您專案所在的Web儀表板。

* **術語**：

  | 術語 | 其含義 |
  | ------ | --------------- |
  | **組織** | 您公司的Adobe組織。 和您在Fusion中使用的組織相同。 |
  | **專案** | 一個應用程式/擴充功能的容器。 您將為擴充功能建立一個專案。 |
  | **工作區** | 工作階段專案設定的副本。 每個專案都有&#x200B;**生產**&#x200B;工作區，而且您通常也會使用&#x200B;**階段**&#x200B;工作區進行測試。 您可以將工作區想成是「環境」。 |
  | **認證/服務** | 您的應用程式可使用的許可權。 為您建立的預設值足以啟動。 |

* 建立專案的方法有兩種：

  * **自動（建議）：**&#x200B;命令`aio app init`會在產生程式碼時為您建立專案和工作區。 本文會介紹此程式。
  * **手動：**&#x200B;您先在Developer Console中自行建立專案，然後指向`aio`。 我們建議僅在貴組織要求集中建立專案時才進行此作業。

* 決定使用哪個工作區時，請先開發並部署到&#x200B;**階段**。 只有當使用者在其Fusion設定檔中開啟階段測試時（使用者頭像選單>產品設定>Fusion設定檔>偏好設定>階段擴充功能），Fusion才會載入Stage組建；否則，只會顯示已發佈的生產擴充功能。 您也可以使用`aio app run`在本機預覽，稍後再升級至&#x200B;**生產**。

  如需提升至生產環境的詳細資訊，請參閱[發佈您的擴充功能](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)。


## 執行`aio app init`

1. 開啟終端機。
1. 在終端機中，移至您保留專案的資料夾。
1. 執行：

   ```sh
   aio app init my-fusion-extension --standalone-app
   ```

   * `my-fusion-extension`是資料夾/應用程式名稱。 您可以選取此名稱，但請使用小寫字母、連字型大小且不含空格。
   * `--standalone-app`通知CLI建立&#x200B;**純應用程式架構**，而不是要求您挑選產品範本。 這是避免AEM （或任何其他）範本的關鍵。

1. 出現提示時，**選取您的組織** （如果您屬於多個組織）。
1. 出現提示時，請選取&#x200B;**建立新專案**&#x200B;並接受建議的名稱，或選取現有的空白專案。

   命令會自動設定&#x200B;**階段**&#x200B;和&#x200B;**生產**&#x200B;工作區。

   命令也會產生檔案至`my-fusion-extension`資料夾並執行`npm install`。

1. 繼續[確認專案建立](#confirm-project-creation)。

>[!NOTE]
>
> **如果您偏好互動式功能表：**&#x200B;請執行`aio app init my-fusion-extension` > （不含`--standalone-app`）。 當它詢問&#x200B;**「您想要搜尋哪些範本？」** 或顯示範本檢查清單，請勿選取AEM等產品範本。 選擇選項以建立&#x200B;**獨立應用程式** / **「所有延伸點→無」**。

## 檢查專案建立

1. 在終端機中，移至已建立的資料夾：

   ```sh
   cd my-fusion-extension
   ```

   您應該會看到類似以下的結構（省略了一些檔案）：

   ```
   my-fusion-extension/
   |--- app.config.yaml   // main configuration (you will edit this)
   |---  package.json   //dependencies and scripts
   |---  src/    // your source code
   |---  web-src/  or  src/.../web-src/  // front-end files (HTML/JS)
   ```

   您最關心的兩個檔案是：

   * **`app.config.yaml`**：中央組態。 在程式後面的步驟中，您將在此新增`extensions:`區段，以將您的應用程式連線到Fusion擴充點。
   * **`package.json`**：列出您的應用程式所使用的資料庫。 您將在此處新增Adobe UI擴充性來賓程式庫。

1. 繼續[新增必要的資料庫](#add-required-libraries)。

>[!TIP]
>
> 如果您產生的配置在CLI版本之間稍有不同，請不要擔心。 此程式會告訴您確切要建立哪些檔案以及要放進哪些檔案，因此無論起始點為何，您都可以符合預期的結構。

## 新增必要程式庫

您的擴充功能需要兩個程式庫：

* **`@adobe/uix-guest`**：讓您的應用程式與Fusion （主機）交談。
* **`@adobe/react-spectrum`**： Adobe的React UI元件，因此您的畫面會符合Adobe的外觀和風格。 （選填，但建議使用；您可以改用純HTML。）

若要安裝這些程式庫：

1. 在終端機中，執行：

   ```sh
   npm install @adobe/uix-guest @adobe/react-spectrum
   ```

1. （視條件而定）如果您產生的專案尚未包含React，請一併安裝：

   ```sh
   npm install react react-dom react-router-dom
   ```

1. 繼續[確認專案組建](#confirm-the-project-builds)。

## 確認專案建置

在變更任何專案之前，請確定空白的專案已建置

1. 在終端機中，執行：

   ```sh
   aio app build
   ```

   如果順利完成，且沒有錯誤，表示您的工具和專案已正確設定。 您已準備好將專案連線到Fusion。

   >[!TIP]
   >
   > **如果建置失敗，**&#x200B;最常見的原因是不受支援的Node.js版本。 執行`node --version`並確定它是18或20。
   >
   >* 如需有關安裝Node.js的資訊，請參閱[設定工具](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)。
   >* 如需其他可能錯誤的資訊，請參閱[疑難排解](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)。

1. 繼續[設定Fusion](#configure-the-project-for-fusion)的專案。

## 設定專案以進行Fusion

設定自訂擴充功能的下一個步驟是將您的通用專案連線到Workfront Fusion。

您將會：

1. [為您的擴充功能建立資料夾](#create-a-folder-for-your-extension)
1. 告訴App Builder有關Fusion **擴充點** （在`app.config.yaml`中）的資訊。
1. 說明您的擴充功能片段（以`ext.config.yaml`表示）。
1. **註冊**&#x200B;您的Widget，讓Fusion知道其標題和UI所在的位置。

我們全程使用`fusion/nav-organization/1`。 若要改用團隊區段為目標，請將`fusion/nav-team/1`交換到所有位置。 若要同時支援兩者，請為每個重複此模式。

## 為您的擴充功能建立資料夾

1. 建立您的檔案，讓專案看起來像這樣：

   ```
   my-fusion-extension/
   |-- app.config.yaml
   |-- src/
          |-- fusion-nav-organization-1/          // one folder per extension point
             |-- ext.config.yaml
             |-- web-src/
                |-- src/
                   |-- components/
                      |-- App.js
                      |-- ExtensionRegistration.js
                      |-- DashboardWidget.js
                      |-- Constants.js
   ```

   我們建議在延伸點(`fusion-nav-organization-1`)之後命名資料夾。 確切的名稱由您決定，但必須符合您在`app.config.yaml`中參照的名稱。

1. 繼續在`app.config.yaml`](#declare-the-extension-point-in-appconfigyaml)中[宣告擴充點。

## 在`app.config.yaml`中宣告擴充點

1. 開啟`app.config.yaml`並將其內容更新至：

   ```yaml
   extensions:
     fusion/nav-organization/1:
       $include: src/fusion-nav-organization-1/ext.config.yaml
   ```

   以下內容說明如下：

   * `extensions:`：此應用程式實作一或多個擴充點。
   * `fusion/nav-organization/1`：您插入的Fusion插槽。 **名稱必須完全符合**，包括版本`1`。
   * `$include:`：這指向描述此擴充功能內容的第二個設定檔（在下一步中建立）。 將其保留在個別檔案中，可保持`app.config.yaml`整潔狀態，並可讓您稍後新增更多擴充點。

   >[!NOTE]
   >
   >如果您要鎖定這兩個擴充功能，請列出兩者，每個都具有自己的資料夾：
   >
   > ```yaml
   > extensions:
   >     fusion/nav-organization/1:
   >         $include: src/fusion-nav-organization-1/ext.config.yaml
   >     fusion/nav-team/1:
   >         $include: src/fusion-nav-team-1/ext.config.yaml
   > ```

   1. 繼續[在`ext.config.yaml`](#describe-the-extension-in-extconfigyaml)中描述擴充功能

## 在`ext.config.yaml`中描述擴充功能

1. 建立`src/fusion-nav-organization-1/ext.config.yaml`，使用：

   ```yaml
   operations:
      view:
       - type: web
         impl: index.html
   web: web-src
   hooks:
     pre-app-build: node node_modules/@adobe/uix-guest/scripts/generate-metadata.js
      pre-app-run: node node_modules/@adobe/uix-guest/scripts/generate-metadata.js
   ```

   以下內容說明如下：

   * **`operations.view`**：宣告您的擴充功能提供從`index.html`提供的&#x200B;**檢視** （可見UI）。 這就是讓您的擴充功能在熒幕顯示的理由，而不只會在背景執行。
   * **`web: web-src`**：儲存您前端檔案的資料夾。 App Builder會建置這裡底下的所有內容，並在Adobe的內容傳遞網路(CDN)上代管這些內容。
   * **`hooks`**：在建置/執行階段自動執行的小型命令。 `generate-metadata.js`指令碼隨附於`@adobe/uix-guest`，並產生您的註冊代碼所需的`app-metadata.json`檔案（請參閱步驟4）。 您不需要撰寫此指令碼，只需參考它即可。

   >[!NOTE]
   >
   > 如果您也需要伺服器端邏輯，您也可以新增無伺服器`actions` （小型後端函式）。 動作是選用的，並且不需要轉譯UI，因此我們將其排除在外，以保持本指南的重點。 如果您稍後新增這些專案，請在此宣告`actions:`資料夾，並在`app.config.yaml`中宣告`runtimeManifest:`。 新增重複資料夾最常見的原因是呼叫Workfront/Fusion API而不點選瀏覽器CORS。
   > 如需呼叫API的詳細資訊，請參閱[呼叫Workfront與Fusion API](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)。
1. 繼續[設定穩定的擴充功能識別碼](#set-a-stable-extension-id)。

## 設定穩定的擴充功能ID

您的擴充功能需要兩個框架共用的唯一ID。

如需與自訂擴充功能相關的框架資訊，請參閱[包含在UI擴充功能中的框架](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md#frames-included-in-a-ui-extension)。

1. 建立`src/fusion-nav-organization-1/web-src/src/components/Constants.js`：

   ```js
   module.exports = {
     extensionId: 'my-fusion-extension'
   };
   ```

   在您的程式碼參考擴充功能ID的所有位置使用相同的值。
1. 繼續[註冊您的Widget](#register-your-widget)。


## 註冊Widget

「註冊」是隱藏的背景框架告訴Fusion您的擴充功能所提供的內容。 您宣告的`dashboard.getWidget()`方法會傳回Widget的標題及其可見UI的URL。

1. 建立`src/fusion-nav-organization-1/web-src/src/components/ExtensionRegistration.js`。
重要部分為`register(...)`呼叫：

   ```js
   import { register } from "@adobe/uix-guest";
   import metadata from "../../../../app-metadata.json";
   import { extensionId } from "./Constants";
   
   async function init() {
     await register({
       id: extensionId,
       metadata,
       methods: {
         dashboard: {
           getWidget() {
             return {
               id: extensionId,
               title: "My Fusion tool",        // shown on the Fusion nav button
               description: "What this tool does",
               url: "/index.html#/my-widget",  // route to your visible UI
               hideWidgetHeader: false          // false = Fusion shows the title
             };
           }
         }
       }
      });
   }
   
   init().catch(console.error);
   ```

   要點：

   * **`title`**&#x200B;是Fusion放在導覽按鈕上的標籤。 如果`hideWidgetHeader`是`false`，Fusion也會將標題顯示為您UI上方的標題。
   * **`url`**&#x200B;是您&#x200B;*可見* UI在此相同應用程式中的路由。 這是由您的前端路由器（設定於下一頁）處理的雜湊路由(`#/my-widget`)。 它必須解析為轉譯您熒幕的元件。
   * **`metadata`**&#x200B;來自`app-metadata.json`，`generate-metadata`鉤點會在建置時為您建立。 將其匯入，如下所示。
   * `dashboard.getWidget`方法名稱是用來探索您的Widget的協定合約Fusion呼叫。 保留`dashboard`名稱空間和`getWidget`名稱。

擴充功能的後端現已完成。 建置擴充功能UI的下一個步驟。

如需建立UI的說明，請參閱[建立自訂擴充功能UI](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)。

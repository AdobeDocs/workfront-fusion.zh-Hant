---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: UI擴充性概觀
description: Workfront Fusion中的自訂擴充功能
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 925a8ee910434c474d527c2914897d7c42e4a3d1
workflow-type: tm+mt
source-wordcount: 835
ht-degree: 0%

---

# UI擴充性概觀

UI擴充性可讓您將自訂邏輯和UI （使用者介面）匯入Adobe Workfront Fusion。 透過使用Adobe App Builder，您可以修改組織的Workfront Fusion體驗，以更符合組織的需求，同時仍仰賴Fusion的核心功能。

本文概述UI擴充功能，以及您的自訂擴充功能與Workfront Fusion的通訊方式。

## 擴充功能結構

* [主機和來賓](#hosts-and-guests)
* [基礎技術](#the-technology-underneath)

### 主機和來賓

Fusion可以顯示Workfront Fusion團隊未建立的UI。 為確保這些UI變更不會影響Fusion的核心功能，UI會在自己的獨立瀏覽器框架(`<iframe>`)中執行，與Fusion的程式碼完全不同。

* **主機**： *包含*&#x200B;延伸的應用程式。 此處是&#x200B;**Fusion**。 主機會決定可顯示擴充功能的位置以及要與擴充功能共用的資料。
* **來賓**： *您的*&#x200B;延伸模組。 它是小型網頁應用程式，主機會載入到iframe中。

建立UI擴充功能時，您不會修改Fusion。 您可以建置並發佈來賓，Fusion在發佈來賓後即可使用。

### 基礎技術

您的來賓採用兩種Adobe技術：

* **Adobe App Builder**：適用於小型網頁應用程式和無伺服器動作的免費託管與工具平台。 您的擴充功能是App Builder應用程式。 App Builder會提供您一個位置來主控您的UI （在Adobe的`*.adobeio-static.net`內容傳遞網路上）和一個名為`aio`的命令列工具，以建立、建置和發佈它。
* **Adobe UI擴充性SDK (UIX)**：讓主持人和來賓交談的資料庫。 您將會在側邊使用一個封裝`@adobe/uix-guest`。 Fusion在其側面使用相符的`@adobe/uix-host`封裝。

<!--

```
   ┌────────── Browser ─────────────────────────────┐
   │                                                                   │
   │   Fusion (Host)                      Your extension (Guest)       │
   │   ────────────                       ─────────────────────        │
   │   @adobe/uix-host   ◀── messages ──▶  @adobe/uix-guest            │
   │        │                                    │                     │
   │   renders an iframe ───────────────▶  your React/HTML UI          │
   │                                                                   │
   └───────────────────────────────────────────────────────────────────┘

   Your UI files are hosted by Adobe App Builder at
   https://<your-app>.adobeio-static.net
```

-->

## 延伸點

擴充點是主機中允許來賓出現的已命名「位置」。 Fusion會定義其位置，而您可以選取訪客將使用的位置。

擴充點名稱有三個部分： `service/name/version`。

Fusion提供下列擴充點：

| 擴充點 | 您的UI在Fusion中的顯示位置 | 何時使用 |
| --- | --- | ---- |
| `fusion/nav-organization/1` | 在左側導覽的&#x200B;**組織**&#x200B;區段下。 | 您的工具關係到整個組織。 |
| `fusion/nav-team/1` | 在左側導覽的&#x200B;**團隊**&#x200B;區段下（在選取團隊時顯示）。 | 您的工具是關於特定團隊的。 |

* `fusion`是&#x200B;**服務** （產品， Fusion）。
* `nav-organization` / `nav-team`是&#x200B;**名稱** （特定位置）。
* `1`是&#x200B;**版本**。

一個擴充功能可實作一個或兩個擴充點。 大部分的擴充功能都使用一點。

Fusion會根據選取的擴充功能點，將副檔名為的按鈕新增至相符的導覽區段。 按一下該按鈕，會在Fusion的主要內容區域中開啟專用頁面，並在該處載入您的UI。

## UI擴充功能中包含的框架

>[!IMPORTANT]
>
>本節將討論可能導致混淆的UI擴充功能方面。 我們建議您仔細閱讀。

當Fusion載入您的來賓時，您的擴充功能會在&#x200B;**兩個**&#x200B;框架中執行：

1. **註冊框架（隱藏）。** 在背景中先執行。 註冊框架會告訴Fusion您的擴充功能提供哪些功能。 例如，這可能表示它有儀表板Widget，並傳送Widget的標題及其UI的URL。 註冊框架會呼叫`register(...)`來執行此操作。 它不會呈現可見的UI。
1. **UI框架（可見）。** 這是Fusion向使用者顯示的頁面。 它必須透過呼叫`attach(...)`向主機宣告自己。 如果它從未呼叫`attach`，Fusion會等待並且最終因錯誤而逾時。

>[!BEGINSHADEBOX]

此範例顯示使用者按一下擴充功能按鈕時的流程。

1. 已按一下按鈕。
1. Fusion會載入您的REGISTRATION框架（隱藏）。

   ```
   register({ methods: { dashboard: { getWidget() {...} } } })
   ```

   `getWidget()`會傳回您可見使用者介面的URL
1. Fusion會在該URL載入您的UI框架（可見）。

   ```
   attach({ id }) 
   ```

   此為必要專案，否則Fusion逾時
1. Fusion會傳送內容，而您的UI會呈現。

>[!ENDSHADEBOX]

當您建置UI時，兩個框架都會寫入。 重要的是要記住，可見頁面&#x200B;**必須**&#x200B;呼叫`attach`。

如需建立UI的詳細資訊，請參閱[建立自訂擴充功能UI](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)。

## 來自Fusion的內容

附加擴充功能後，Fusion會與您的來賓共用`context`物件。 該檔案內含：

* **使用者**：登入使用者的Fusion設定檔和Adobe IMS使用者ID。
* **組織**：作用中組織的完整Fusion組織記錄和Adobe IMS組織ID。
* **團隊**：作用中的團隊（如果適用）。
* **Adobe IMS存取Token**：如有必要，這將代表使用者呼叫Adobe或Fusion API。

Fusion也會推送更新。 例如，如果使用者在您的UI開啟時切換組織或團隊，Fusion會傳送新內容，以便您的UI可以立即回應。

如需內容欄位的完整清單，請參閱[Fusion內容參考](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)。

## 建立UI擴充功能

若要建立UI擴充功能，請遵循下列步驟：

1. [安裝工具並建立Adobe專案](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)。
1. [產生空白的App Builder專案，將其指向Fusion擴充功能點，並註冊您的Widget](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md)。
1. [建置UI並連線到Fusion](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)。
1. [使用內容Fusion傳送](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)。
1. [發佈，讓Fusion可以找到它](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)。
1. （選用） [呼叫不含CORS之真實資料的Workfront/Fusion API](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)。

若要開始此程式，請移至[設定您的工具和Adobe帳戶](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)。



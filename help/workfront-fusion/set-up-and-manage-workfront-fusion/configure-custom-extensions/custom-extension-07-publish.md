---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 發佈您的自訂擴充功能
description: 發佈您的自訂擴充功能
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: 925a8ee910434c474d527c2914897d7c42e4a3d1
workflow-type: tm+mt
source-wordcount: 1236
ht-degree: 1%

---

# 發佈您的自訂擴充功能

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

您的擴充功能必須在&#x200B;**建置**、**部署**&#x200B;至Adobe且貴組織&#x200B;**核准**&#x200B;後，才能在Fusion中執行。 此頁面上的程式顯示如何發佈您的擴充功能以及如何驗證結果。

此資訊改編自Adobe的官方檔案，並特別適用於Workfront Fusion。 如需一般Adobe資訊，請參閱Adobe檔案中的[UI擴充功能開發流程](https://developer.adobe.com/uix/docs/guides/development-flow/)和[UI擴充功能管理](https://developer.adobe.com/uix/docs/guides/publication/)。

## 工作區

每個App Builder專案都有&#x200B;**階段**&#x200B;和&#x200B;**生產**&#x200B;工作區。 將其視為環境：

* **階段**&#x200B;是用於開發和測試。 您一邊部署於此處，一邊進行反複運算。 不需要核准，且結果只能透過下述中繼測試切換（或本機預覽）看到。
* **生產**&#x200B;即將發行給每個人。 部署至生產環境後，您會提交&#x200B;**核准要求**，且在核准後，該擴充功能即會在Adobe應用程式登入中註冊，並向整個組織顯示。

>[!NOTE]
>
> **角色：**&#x200B;建立和部署需要&#x200B;**開發人員**&#x200B;角色；提交核准要求以發佈需要&#x200B;**系統管理員**角色。
>如需詳細資訊，請參閱：
>
> * [設定UI擴充功能工具和帳戶](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md)
> * 在Adobe檔案中[如何取得存取權](https://developer.adobe.com/uix/docs/guides/get-access/)。

依預設，Fusion只會顯示&#x200B;**已發佈的**&#x200B;擴充功能。 這些是您已部署至&#x200B;**生產**&#x200B;工作區的擴充功能，然後提交以供&#x200B;**核准**。 這是安全的預設值，因此進行中的部署絕不會不小心顯示給整個組織。

對&#x200B;**Stage**&#x200B;工作區的部署未發佈，因此它不會單獨出現在Fusion中。 在發佈擴充功能之前，您有兩種方式可先嘗試擴充功能：

* **使用`aio app run`在本機預覽它** （請參閱Adobe檔案中的[UI擴充功能的本機預覽](https://developer.adobe.com/uix/docs/guides/preview-extension-locally/)）。 不會部署任何專案，只有您能看見。
* 在Fusion設定檔中開啟每位使用者的測試開關，從Fusion **內的Stage**&#x200B;載入它。 本文的[在Fusion](#test-a-stage-build-in-fusion)中測試Stage組建中對此進行了說明。

## 在Fusion中測試階段組建

使用此流程，在發佈Fusion之前檢視其中的Stage部署。

### 步驟1：選取階段工作區

```sh
aio console where                  # shows current org / project / workspace
aio console workspace select       # choose Stage
```

### 步驟2：建置

```sh
aio app build
```

這會編譯您的前端並執行中繼資料連結（產生`app-metadata.json`）。 請先修正所有回報的錯誤，然後再繼續。

### 步驟3：部署

```sh
aio app deploy
```

`deploy`會做兩件事：

* **在Adobe的內容傳遞網路（例如`https://<project>-stage.adobeio-static.net`）上主控您的UI**。 CLI完成時會列印此&#x200B;**延伸端點URL**。 這是URL Fusion載入其iframe中的專案。
* **在Stage工作區中為擴充功能點(`fusion/nav-organization/1`)登入您的擴充功能端點**。

>[!TIP]
>
> **如果部署失敗，並顯示「擴充點&#39;fusion/nav-organization/1&#39;不存在」（錯誤1060）：**您的組織尚未啟用Fusion擴充點。 這是上線步驟，不是程式碼中的錯誤。
>如需詳細資訊，請參閱疑難排解文章中的[擴充點不存在](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md#error-1060-extension-point-does-not-exist)。

### 步驟4：在Fusion設定檔中開啟中繼測試

只有在您選擇加入時，Fusion才會載入階段擴充功能（根據使用者）：

1. 使用您部署至的&#x200B;**相同組織**&#x200B;中的帳戶登入Fusion。
1. 開啟上角的使用者頭像功能表，然後前往&#x200B;**產品設定** > **Fusion設定檔** > **偏好設定**。
1. 開啟&#x200B;**階段擴充功能**&#x200B;開關。

   Fusion會提示您重新載入。
1. 確認重新載入。

重新載入後，Fusion會從Stage工作區載入擴充功能，而非已發佈的集合，並在導覽中標籤每個&#x200B;**(Stage)**，以便您加以區分。

此引數是儲存在瀏覽器中的個人測試設定，不是組織設定。 將其關閉（並重新載入），以返回已發佈的擴充功能。 由於是儲存在本機，因此不會跟著您前往其他瀏覽器或電腦。

### 步驟5：在Fusion中驗證

1. 開啟符合擴充功能的區段：
   * 左側導覽→**組織**&#x200B;區域有`fusion/nav-organization/1`。
   * **團隊**&#x200B;區域→的`fusion/nav-team/1` （請先選取團隊）。

   會出現具有您在`getWidget()`中設定的標題的按鈕，標籤為&#x200B;**（階段）**。
1. 按一下出現的按鈕。

您的UI載入並接收[Fusion內容](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)。

如果按鈕未出現或面板顯示錯誤，請參閱[疑難排解](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)。

## 發佈於生產環境

當您的擴充功能在Stage上運作，且您已準備好供所有使用者使用時：

### 步驟1：切換至生產工作區

```sh
aio console workspace select       # choose Production
```

當CLI提示有關`.env`檔案時，請選取&#x200B;**合併**，以便保留您的環境變數。

### 步驟2：建置並部署至生產環境

```sh
aio app build
aio app deploy
```

### 步驟3：提交核准請求

發佈是從生產工作區&#x200B;**提交的**&#x200B;核准要求：

1. 開啟[Adobe Developer Console](https://developer.adobe.com/console)、選取您的&#x200B;**組織**、開啟您的&#x200B;**專案**，然後切換至&#x200B;**生產**&#x200B;工作區。
1. 提交您的應用程式以進行&#x200B;**核准/發佈** （這需要&#x200B;**系統管理員**&#x200B;角色）。
1. 核准後，您的擴充功能會新增至&#x200B;**Adobe應用程式登入**，並可透過[Adobe Experience Cloud](https://experience.adobe.com) （包括Fusion）供您的組織使用。

如需詳細指示，請參閱Adobe Developer檔案中的[UI擴充功能管理](https://developer.adobe.com/uix/docs/guides/publication/)。

## 狀態和更新

一些行為值得瞭解，因此除了「有些事情不對勁」以外，您還可以區分「仍在處理」：

* **部署到生產環境與可見環境不同。** `aio app deploy`到生產環境上傳您的應用程式，但不會顯示擴充功能。 它只會在核准要求提交並核准後顯示。 如果您已部署到生產環境，但仍在Fusion中看不到它，通常原因是尚未核准它。
* **僅限程式碼的更新不需要新的核准。** 如果您的擴充功能已發佈，而您僅變更其程式碼（UI或執行階段動作），請使用以下專案重新部署至相同的URL：

  ```sh
  aio app deploy --force-deploy
  ```

  使用者下次開啟擴充功能時會取得新版本。 沒有可供安裝的專案。 變更&#x200B;**註冊**&#x200B;本身時（例如新增擴充點或變更`getWidget()`的廣告），您只需要提交新的核准要求。
* **已撤銷或已撤銷的擴充功能會消失。** 如果您撤銷或撤銷了擴充功能，擴充功能就會停止在Fusion中顯示，不會出現錯誤訊息。 如果每個人的先前有效擴充功能消失，請在搜尋程式碼問題之前檢查它是否已撤銷。

## 移除（撤銷）擴充功能

移除已發佈的擴充功能是由&#x200B;**在Adobe Exchange中撤銷**&#x200B;完成的：

1. 登入&#x200B;**Adobe Exchange**。
1. 移至&#x200B;**管理** > **App Builder應用程式**。
1. 選取您要移除之擴充功能旁的&#x200B;**撤銷**，然後確認。

撤銷後，擴充功能會在Extension Manager中顯示&#x200B;*已撤銷*&#x200B;狀態，且不再出現在Fusion中。 若要完全移除該專案，請刪除Developer Console中的專案。 在撤銷專案的擴充功能之前，無法刪除專案。

對於僅中繼測試部署，您可以移除具有以下功能的部署：

```sh
aio app undeploy
```

## 其他資源

Adobe檔案中提供下列資源：

* [UI擴充功能開發流程](https://developer.adobe.com/uix/docs/guides/development-flow/)
* [UI擴充功能管理（發佈/核准/撤銷）](https://developer.adobe.com/uix/docs/guides/publication/)
* [在Developer Console中建立專案](https://developer.adobe.com/uix/docs/guides/creating-project-in-dev-console/)
* [如何取得存取權（角色）](https://developer.adobe.com/uix/docs/guides/get-access/)
* [UI擴充功能的本機預覽](https://developer.adobe.com/uix/docs/guides/preview-extension-locally/)

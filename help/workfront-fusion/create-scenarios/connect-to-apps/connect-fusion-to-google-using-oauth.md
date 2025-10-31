---
title: 使用自訂OAuth使用者端連線Adobe Workfront Fusion至Google Services
description: 您可以使用Adobe Workfront Fusion，透過自訂OAuth使用者端連線至Google服務。 此程式需要現有的Google帳戶。
author: Becky
feature: Workfront Fusion
exl-id: 2f0bc289-4ecf-4a31-9d7b-641bbca6fc95
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 1%

---

# 使用自訂OAuth使用者端連線Adobe Workfront Fusion至Google Services

您可以使用Adobe Workfront Fusion，透過自訂OAuth使用者端連線至Google服務。 此程式需要現有的Google帳戶。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權</td> 
   <td>
   <p>作業型：無Workfront Fusion授權需求</p>
   <p>以聯結器為基礎（舊版）：用於工作自動化和整合的Workfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

您需要現有的Google帳戶才能建立此連線。

## 使用自訂OAuth使用者端連線Fusion至Google服務

若要建立此連線，您必須在Google Cloud平台上建立並設定專案，然後根據該專案在Fusion中設定連線。

>[!NOTE]
>
>此程式的用途為：
>
>* 個人使用（`@gmail.com`和`@googlemail.com`位使用者）
>* 內部使用(偏好使用自訂OAuth使用者端的Google Workspace使用者)

* [在Google Cloud Platform上建立專案](#create-a-project-on-google-cloud-platform)
* [設定OAuth同意設定](#configure-oauth-consent-settings)
* [建立OAuth認證](#create-oauth-credentials)
* [連線至Workfront Fusion中的Google](#connect-to-google-in-workfront-fusion)

### 在Google Cloud Platform上建立專案

若要在Google Cloud Platform上建立專案：

1. 開始在Google Cloud Platform上建立專案。

   如需指示，請參閱Google檔案中的[建立Google Cloud專案](https://developers.google.com/workspace/guides/create-project)。
1. 啟用API時，您必須啟用Google Drive API以及您想使用的所有Google應用程式的API (例如Google Sheets API)。
1. 完成建立專案。
1. 繼續閱讀本文章[設定OAuth同意設定](#configure-oauth-consent-settings)一節。

### 設定OAuth同意設定

1. 開始為專案設定OAuth

   如需指示，請參閱[在Google檔案中設定OAuth同意畫面並選擇範圍](https://developers.google.com/workspace/guides/configure-oauth-consent)。
1. 選取&#x200B;**外部**，然後按一下&#x200B;**建立**。

   >[!NOTE]
   >
   >選取此選項時不會向您收費。 如需詳細資訊，請參閱Google關於驗證需求例外的資訊。

1. 依照以下說明填寫必填欄位：

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>應用程式名稱</p> </td> 
      <td> <p>輸入要求同意的應用程式名稱。</p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>Adobe Workfront Fusion </p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">使用者支援電子郵件</td> 
      <td>輸入電子郵件地址，讓使用者在連線至此應用程式時，針對同意問題聯絡您。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">電子郵件地址</td> 
      <td>輸入一或多個電子郵件地址，Google可將其用於通知您專案的任何變更。</td> 
     </tr> 
    </tbody> 
   </table>

1. 在[授權網域]下，按一下[新增網域] **，然後輸入**。`workfrontfusion.com`
1. 新增下列範圍：

   <table style="table-layout:auto">
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>服務/API</th> 
      <th>必要的範圍</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td> <p>Gmail</p> </td> 
      <td> <p>https://mail.google.com/</p> <p>https://www.googleapis.com/auth/gmail.labels</p> <p>https://www.googleapis.com/auth/gmail.send</p> <p>https://www.googleapis.com/auth/gmail.readonly</p> <p>https://www.googleapis.com/auth/gmail.compose</p> <p>https://www.googleapis.com/auth/gmail.insert</p> <p>https://www.googleapis.com/auth/gmail.modify</p> <p>https://www.googleapis.com/auth/gmail.metadata</p> </td> 
     </tr> 
     <tr> 
      <td> <p>Google Drive</p> </td> 
      <td> <p>https://www.googleapis.com/auth/drive</p> <p>https://www.googleapis.com/auth/drive.readonly</p> </td> 
     </tr> 
    </tbody> 
   </table>

   您可能需要展開清單或前往清單的下一頁檢視所有清單。

1. （選用）將任何測試使用者新增至專案。
1. 檢查您的資訊是否準確，然後按一下&#x200B;**返回儀表板**。

   >[!NOTE]
   >
   >您不需要提交同意畫面和Google驗證申請。

1. 繼續[建立OAuth認證](#create-oauth-credentials)。

### 建立OAuth認證

1. 開始建立OAuth使用者端ID認證。

   如需指示，請參閱Google檔案中的[建立存取認證](https://developers.google.com/workspace/guides/create-credentials)。

   >[!NOTE]
   >
   >如果這不是您啟用的第一個API或服務(Gmail或Google Drive)，您就不需要建立新的認證。

1. 依照以下說明填寫必填欄位：

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">應用程式型別</td> 
      <td> <p> 網頁應用程式</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">姓名</td> 
      <td>Workfront Fusion </td> 
     </tr> 
    </tbody> 
   </table>

1. 在授權的重新導向URI下，輸入下列&#x200B;**一個**：

   * 對於Gmail或Google磁碟機： `https://app.workfrontfusion.com/oauth/cb/google-restricted`

   * 其他Google應用程式： `https://app.workfrontfusion.com/oauth/cb/google`

1. 按一下「**建立**」。

   使用者端ID和使用者端密碼隨即顯示。

1. 將使用者端ID和使用者端密碼複製到安全位置。 您將使用它們在Workfront Fusion中建立連線。
1. 繼續[連線到Workfront Fusion中的Google](#connect-to-google-in-workfront-fusion)。

### 連線至Workfront Fusion中的Google

建立與Google的連線程式會有所不同，端視您是使用Google服務(例如Google Sheets或Google Docs)的模組，或是透過HTTP >建立OAuth2.0請求模組來連線Google。

* [在Google服務中連線至Google](#connect-to-google-in-a-google-service)
* [在HTTP >產生OAuth2.0請求模組中連線至Google](#connect-to-google-in-the-http--make-an-oauth20-request-module)

#### 在Google服務中連線至Google

1. 在Workfront Fusion中，找到您需要建立連線的Google模組。
1. 按一下[建立連線]&#x200B;**&#x200B;**，然後按一下[顯示進階設定]&#x200B;**&#x200B;**。
1. 填寫「連線名稱」、「環境」和「型別」欄位（如適用）。
1. 在個別欄位中輸入您在[建立OAuth認證](#create-oauth-credentials)中擷取的使用者端識別碼和使用者端密碼，然後按一下&#x200B;**繼續**。

1. 使用您的Google帳戶登入。

   **此應用程式未驗證**&#x200B;視窗會顯示。 請注意，視窗標題中提到的「應用程式」是您在上面建立的OAuth使用者端。

1. 按一下&#x200B;**進階**，然後按一下&#x200B;**移至Workfront Fusion （不安全）**&#x200B;以允許使用您的自訂OAuth使用者端進行存取。

1. 按一下&#x200B;**允許**&#x200B;以授予Workfront Fusion許可權。
1. 在出現的視窗中，再按一下&#x200B;**允許**&#x200B;以確認您的選擇。

   會使用自訂OAuth使用者端建立與所需Google服務的連線。

#### 在HTTP >產生OAuth2.0請求模組中連線至Google {#connect-to-google-in-the-http--make-an-oauth20-request-module}

如需在HTTP >產生OAuth2.0要求模組中連線Google的指示，請參閱HTTP >產生OAuth 2.0要求模組[一文中的](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md#instructions-for-creating-a-connection-to-google-in-the-http-make-an-oauth-20-request-module)在HTTP >產生OAuth 2.0要求模組中建立與Google連線的指示。

## 可能的錯誤訊息：[未設定403存取]

如果顯示`403 Access Not Configured`錯誤訊息，您必須在Google Cloud平台中啟用對應的API。 若要啟用API，請依照本文中[在Google Cloud Platform上建立專案](#create-a-project-on-google-cloud-platform)一節中的步驟操作。

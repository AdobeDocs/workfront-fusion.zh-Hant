---
title: 呼叫MS Graph REST API
description: 透過Adobe Workfront Fusion HTTP呼叫MS Graph REST API &>提出OAuth 2.0請求模組
author: Becky
feature: Workfront Fusion
exl-id: f411c807-955d-44fe-98b1-3ebba3fe0861
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 3%

---

# 呼叫MS Graph REST API

許多Microsoft網路服務是透過Microsoft Graph API存取。 您可以使用Microsoft Fusion HTTP >產生OAuth 2.0請求模組，建立與Workfront Graph API的連線。

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

## 在Workfront應用程式註冊入口網站中註冊Microsoft Fusion

若要建立與Microsoft Graph REST API的連線，您必須先註冊Adobe Workfront Fusion。

1. 開始註冊新的應用程式，如Microsoft檔案中的[在Microsoft識別平台](https://docs.microsoft.com/en-us/graph/auth-register-app-v2)註冊應用程式中所述。

   註冊時，Microsoft需要下列資訊：

   <table style="table-layout:auto">
      <tr>
        <td>應用程式名稱</td>
        <td>輸入應用程式的名稱，例如「我的Workfront Fusion應用程式」。</td>
      </tr>
      <tr>
        <td>重新導向 URL</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/oauth2</code></td>
      </tr>
    </table>

1. 完成應用程式註冊後，記下應用程式ID。

   >[!IMPORTANT]
   >
   >您需要應用程式ID才能在Workfront Fusion中設定連線。

1. 產生使用者端密碼。 記下此密碼。

   如需指示，請參閱Microsoft檔案中的[向Microsoft識別平台註冊應用程式](https://docs.microsoft.com/en-us/graph/auth-register-app-v2)。

   >[!IMPORTANT]
   >
   >您需要使用者端密碼才能在Workfront Fusion中設定連線。

1. 設定應用程式的許可權。

   如需尋找和設定這些欄位的詳細資訊，請參閱Microsoft檔案中[在沒有使用者身分的情況下取得存取權](https://docs.microsoft.com/en-us/graph/auth-v2-service)中的「設定Microsoft Graph的許可權」一節。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">您的應用程式需要哪種型別的許可權？</td> 
      <td>選擇「<code>Delegated permissions</code>」。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">選取許可權</td> 
      <td> <p>選取下列許可權：</p> 
       <ul> 
        <li> <p><code>offline_access</code> </p> </li> 
        <li> <p><code>openid</code> </p> </li> 
        <li> <p>您的整合所需的任何其他許可權（範例： <code>User.Read</code>）</p> </li> 
       </ul> <p><b>重要</b>：您需要選取的許可權，才能在Workfront Fusion中設定連線。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 繼續[在Workfront Fusion](#configure-your-ms-graph-api-connection-in-workfront-fusion)中設定MS Graph API連線。

## 在Workfront Fusion中設定MS Graph API連線

依照[在Workfront應用程式註冊入口網站](#register-workfront-fusion-in-the-microsoft-application-registration-portal)中註冊Workfront Fusion中所述，註冊Microsoft Fusion後，您可以在「HTTP >發出Oauth 2.0請求模組」中設定連線。

1. 新增HTTP >為情境產生OAuth 2.0呼叫模組。
1. 按一下連線欄位旁的&#x200B;**新增**。
1. 依照以下方式設定連線欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">連線名稱</td> 
      <td>輸入連線的名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">環境</p> </td> 
      <td>選取您要連線到生產或非生產帳戶。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">類型</p> </td> 
      <td>選取您要連線到服務帳戶還是個人帳戶。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p role="rowheader">流量型別</p> </td> 
      <td>選擇「<code>Authorization Code</code>」。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">授權URI</td> 
      <td>輸入<code>https://login.microsoftonline.com/common/oauth2/v2.0/authorize</code>。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">權杖URI</td> 
      <td>輸入<code>https://login.microsoftonline.com/common/oauth2/v2.0/token</code>。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">範圍</td> 
      <td> <p>如<a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">在Workfront應用程式註冊入口網站中註冊Microsoft Fusion</a>中所述，輸入您在註冊時選取的許可權。</p> <p>針對每個範圍，按一下<b>新增</b>並輸入許可權。</p> <p>範例：<code>offline_access</code>。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">範圍分隔符號</td> 
      <td>選擇「<code>SPACE</code>」。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">用戶端 ID</td> 
      <td>在Microsoft應用程式註冊入口網站<a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">的</a>註冊Workfront Fusion中，輸入步驟2中的應用程式ID。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">用戶端密碼</td> 
      <td>在<a href="#register-workfront-fusion-in-the-microsoft-application-registration-portal" class="MCXref xref">在Workfront應用程式註冊入口網站</a>中註冊Microsoft Fusion中，輸入您在步驟3中產生的使用者端密碼。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">授權引數</td> 
      <td> <p>新增下列Authorize引數。 針對您新增的每個引數，按一下<b>新增專案</b>並輸入下列內容： </p> 
       <ul> 
        <li> <p>索引鍵： <code> response_mode</code>值： <code>query</code></p> </li> 
        <li> <p>索引鍵： <code>prompt </code>值： <code>consent</code></p> </li> 
       </ul> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">存取權杖引數</td> 
      <td>您不需要在此欄位中輸入任何內容。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">重新整理權杖引數</td> 
      <td> 
       <ol> 
        <li value="1"> <p>按一下<b>新增專案</b>。</p> </li> 
        <li value="2"> <p>在<b>索引鍵</b>欄位中，輸入<code>scope</code>。</p> </li> 
        <li value="3"> <p>在<b>值</b>欄位中，輸入您在範圍欄位中輸入的所有範圍，並以空格分隔。</p> <p>範例： <code>offline_access openid User.Read</code></p> </li> 
       </ol> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">自訂標頭</td> 
      <td>您不需要在此欄位中輸入任何內容。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">代號位置</td> 
      <td><code>In the header</code> </td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**繼續**。
1. 在出現的視窗中，按一下&#x200B;**接受**&#x200B;以完成連線並返回模組。

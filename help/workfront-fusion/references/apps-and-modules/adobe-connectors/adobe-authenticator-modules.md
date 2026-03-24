---
title: Adobe Authenticator 模組
description: 透過Adobe Authenticator模組，您可以使用單一連線透過API連線至任何Adobe產品。
author: Becky
feature: Workfront Fusion
exl-id: af4da661-eeee-4033-a2bb-a2196e446a3d
source-git-commit: 42ec34b1931eb9962569906d78c281bbef86a57e
workflow-type: tm+mt
source-wordcount: '1478'
ht-degree: 33%

---

# Adobe Authenticator模組

Adobe Authenticator模組可讓您使用單一連線來連線至任何Adobe API。 這可讓您更輕鬆地連線至尚未具備專用Fusion聯結器的Adobe產品。

與HTTP模組相比，您可在專用應用程式中建立連線。

若要檢視可用的Adobe API清單，請參閱[Adobe API](https://developer.adobe.com/apis)。 您只能使用指派給您的API。

## 存取權要求

+++ 展開以檢視這篇文章中所述功能的存取權要求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront 封裝</td> 
   <td> <p>任何 Adobe Workfront Workflow 封裝及任何 Adobe Workfront Automation and Integration 封裝</p><p>Workfront Ultimate</p><p>Workfront Prime 和 Select 封裝，以及額外購買的 Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront 授權</td> 
   <td> <p>標準</p><p>工作或更高層級</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>連接器型 (舊版)：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

* 您必須擁有您要模組連線的Adobe產品的存取權。
* 您必須擁有Adobe Developer Console的存取權。
* 您在Adobe Developer Console上必須有專案，其中包含您想要模組連線至的API。 您可以：

   * 使用API建立新專案。

     或
   * 將API新增至現有專案。

  如需有關在Adobe Developer Console上建立或新增API至專案的資訊，請參閱Adobe檔案中的[建立專案](https://developer.adobe.com/dep/guides/dev-console/create-project/)。

## Adobe Authenticator API資訊

Adobe Authenticator聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.1.4</td> 
  </tr>
 </tbody> 
 </table>

## 建立連線

Adobe Authenticator連線會連線至Adobe Developer Console上的單一專案。 若要針對多個Adobe API使用相同的連線，請將API新增至相同的專案，並建立與該專案的連線。

您可以建立不同專案的個別連線，但無法使用連線來存取該連線中所指定專案以外的API。

>[!IMPORTANT]
>
>使用Adobe Authenticator聯結器，您可以選擇進行OAuth伺服器對伺服器連線，或選擇服務帳戶(JWT)連線。 Adobe已淘汰JWT憑證，這些憑證將在2025年1月1日之後停止運作。 **因此，強烈建議您建立OAuth連線。**
>
>如需這些連線型別的詳細資訊，請參閱Adobe檔案中的[伺服器對伺服器驗證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/)

若要建立連線：

1. 在任何Adobe Authenticator模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線類型]</td>
        <td>
          <p>選取您要建立OAuth伺服器對伺服器連線，還是要建立服務帳戶(JWT)連線。 我們強烈建議您建立OAuth連線。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的[!DNL Adobe]使用者端識別碼。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的[!DNL Adobe]使用者端密碼。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 範圍]</td>
        <td>如果您已選取OAuth連線，請輸入此連線所需的範圍。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 技術帳戶ID]</td>
        <td>如果您已選取JWT連線，請輸入您的[!DNL Adobe]技術帳戶ID。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 組織ID]</td>
        <td>如果您已選取JWT連線，請輸入您的[!DNL Adobe]組織識別碼。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta範圍]</td>
        <td>如果您已選取JWT連線，請輸入此連線所需的中繼範圍。 </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 私密金鑰]</td>
        <td>
          <p>如果您已選取 JWT 連線，請輸入在 [!DNL Adobe Developer Console] 中建立認證時所產生的私密金鑰。 </p>
          <p>若要擷取您的私密金鑰或憑證：</p>
          <ol>
            <li value="1">
              <p>按一下「<b>[!UICONTROL 擷取]</b>」。</p>
            </li>
            <li value="2">
              <p>選取要擷取的檔案類型。</p>
            </li>
            <li value="3">
              <p>選取包含私密金鑰或憑證的檔案。</p>
            </li>
            <li value="4">
              <p>輸入檔案的密碼。</p>
            </li>
            <li value="5">
              <p>按一下「<b>[!UICONTROL 儲存]</b>」，擷取檔案並返回連線設定。</p>
            </li>
          </ol>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 基底URL]</td>
        <td>您必須新增要此驗證器允許的基本URL。 稍後在情境中使用進行自訂API呼叫模組時，您將新增相對路徑至所選的URL。 在這裡輸入URL，您可以控制進行自訂API呼叫模組可以連線的專案，進而提高安全性。<p>針對您想要新增至驗證器的每個基底URL，按一下<b>新增專案</b>並輸入基底URL。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 驗證 URL]</td>
        <td>請將此專案留空，以使用<code>https://ims-na1.adobelogin.com</code>的標準Adobe IMS驗證URL。 如果您沒有使用Adobe IMS進行驗證，請輸入用於驗證的URL。</td>
      </tr>
    </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

## 模組

* [進行自訂的 API 呼叫](#make-a-custom-api-call)
* [進行自訂API呼叫（舊版）](#make-a-custom-api-call-legacy)
* [進行自訂API呼叫（輪詢）](#make-a-custom-api-call-polling)

### 進行自訂的 API 呼叫

此動作模組可讓您呼叫任何Adobe API。 它支援大型檔案，而非純文字內文。

此單元已在2024年11月14日推出。 任何在此日期前設定的「Adobe Authenticator >進行自訂API呼叫」都不會處理大型檔案，現在視為「進行自訂API呼叫（舊版）」模組。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL 連線]</td>
     <td>如需建立與Adobe Authenticator模組的連線的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref" >建立連線</a>。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 基底URL]</p>
      </td>
      <td>
        <p>輸入您要連線之API點的基底URL。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>輸入相對於基底URL的路徑。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 標頭]</td>
      <td>
        <p>以標準 JSON 物件的形式新增要求標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion 會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 查詢字串]  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 主體型別]</td>
   <td> 選取此API請求的內文型別：
   <ul>
   <li>原始</li>
   <li>application/x-www-form-urlencoded</li>
   <li>多部分/表單資料</li>
   </ul>
      </td>
      </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸出型別]  </td>
      <td>
        <p>選取您要模組輸出的資料型別。 如果您未選取型別，模組會自動選取型別。</p>
      </td>
    </tr>
  </tbody>
</table>

### 進行自訂API呼叫（舊版）

此動作模組可讓您呼叫任何Adobe API。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL 連線]</td>
     <td>如需建立與Adobe Authenticator模組的連線的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref" >建立連線</a>。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 基底URL]</p>
      </td>
      <td>
        <p>輸入您要連線之API點的基底URL。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>輸入相對於基底URL的路徑。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 標頭]</td>
      <td>
        <p>以標準 JSON 物件的形式新增要求標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion 會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 查詢字串]  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 正文]</td>
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

### 進行自訂API呼叫（輪詢）

此模組會進行自訂呼叫，並包含重複執行呼叫的選項，直到符合特定條件或達到定義的限製為止。


<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL 連線]</td>
     <td>如需建立與Adobe Authenticator模組的連線的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref" >建立連線</a>。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 基底URL]</p>
      </td>
      <td>
        <p>輸入您要連線之API點的基底URL。</p>
      </td>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>輸入相對於基底URL的路徑。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 標頭]</td>
      <td>
        <p>以標準 JSON 物件的形式新增要求標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion 會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 查詢字串]  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 主體型別]</td>
   <td> 選取此API請求的內文型別：
   <ul>
   <li>原始</li>
   <li>application/x-www-form-urlencoded</li>
   <li>多部分/表單資料</li>
   </ul>
      </td>
      </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Repeat Until]  </td>
      <td>
        <p>設定條件式篩選器，判斷輪詢何時應停止。 您可以使用點標籤法（例如<code>body.status</code>、<code>body.data.state</code>或<code>headers.status</code>）參考回應資料。 會在每次執行後評估條件，並持續輪詢，直到條件評估為<code>true</code>為止。 支援的運運算元包括： <code>Equal to</code>、<code>Not equal to</code>、<code>Exists</code>、 <code>Does not exist</code></p><p>例如，您可以設定<code>body.status not equal completed</code>以持續輪詢，直到API回應指出程式完成。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 重複延遲]  </td>
      <td>
        <p>輸入或對應執行之間的延遲（以秒為單位）。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 重複限制]  </td>
      <td>
        <p>輸入或對應您希望API呼叫執行的最大次數。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸出型別]  </td>
      <td>
        <p>選取您要模組輸出的資料型別。 如果您未選取型別，模組會自動選取型別。</p>
      </td>
    </tr>
  </tbody>
</table>

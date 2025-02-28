---
title: Adobe Authenticator模組
description: 透過Adobe Authenticator模組，您可以使用單一連線透過API連線至任何Adobe產品。
author: Becky
feature: Workfront Fusion
exl-id: af4da661-eeee-4033-a2bb-a2196e446a3d
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 1%

---

# Adobe Authenticator模組

Adobe Authenticator模組可讓您使用單一連線來連線至任何AdobeAPI。 這可讓您更輕鬆地連線到尚未擁有專用Fusion聯結器的Adobe產品。

與HTTP模組相比，您可在專用應用程式中建立連線。

若要檢視可用的AdobeAPI清單，請參閱[AdobeAPI](https://developer.adobe.com/apis)。 您只能使用指派給您的API。

## 存取需求

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] 封裝</td>
      <td>
        <p>新增：任何</p><p>或</p><p>目前： [!UICONTROL Pro]或更高</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] 授權</td>
      <td>
        <p>新增：標準</p><p>或</p><p>目前： [!UICONTROL Plan]， [!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權</td>
      <td>
   <p>目前的Fusion授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版Fusion授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td>
    </tr>
    <tr>
      <td role="rowheader">產品</td>
      <td>
   <p>新的Workfront計畫：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>目前的Workfront計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td>
    </tr>
  </tbody>
</table>

## 先決條件

* 您必須擁有您希望模組連線的Adobe產品的存取權。
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
   <td role="rowheader">API標籤</td> 
   <td>v1.1.4</td> 
  </tr>
 </tbody> 
 </table>

## 建立連線

Adobe Authenticator連線會連線至Adobe Developer Console上的單一專案。 若要針對多個AdobeAPI使用相同的連線，請將API新增至相同的專案，並建立與該專案的連線。

您可以建立不同專案的個別連線，但無法使用連線來存取該連線中所指定專案以外的API。

>[!IMPORTANT]
>
>使用Adobe Authenticator聯結器，您可以選擇進行OAuth伺服器對伺服器連線，或選擇服務帳戶(JWT)連線。 Adobe已棄用JWT憑證，這些憑證將在2025年1月1日之後停止運作。 **因此，強烈建議您建立OAuth連線。**
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
        <td role="rowheader">[!UICONTROL Connection type]</td>
        <td>
          <p>選取您要建立OAuth伺服器對伺服器連線，還是要建立服務帳戶(JWT)連線。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>輸入您的[!DNL Adobe]使用者端識別碼。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>輸入您的[!DNL Adobe]使用者端密碼。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Scopes]</td>
        <td>如果您已選取OAuth連線，請輸入此連線所需的範圍。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Technical account ID]</td>
        <td>輸入您的[!DNL Adobe]技術帳戶ID。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Organization ID]</td>
        <td>如果您已選取JWT連線，請輸入您的[!DNL Adobe]組織識別碼。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta Scopes]</td>
        <td>如果您已選取JWT連線，請輸入此連線所需的中繼範圍。 </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Private key]</td>
        <td>
          <p>如果您已選取JWT連線，請輸入在[!DNL Adobe Developer Console]中建立認證時產生的私密金鑰。 </p>
          <p>若要擷取您的私密金鑰或憑證：</p>
          <ol>
            <li value="1">
              <p>按一下<b>[!UICONTROL Extract]</b>。</p>
            </li>
            <li value="2">
              <p>選取要解壓縮的檔案型別。</p>
            </li>
            <li value="3">
              <p>選取包含私密金鑰或憑證的檔案。</p>
            </li>
            <li value="4">
              <p>輸入檔案的密碼。</p>
            </li>
            <li value="5">
              <p>按一下<b>[!UICONTROL Save]</b>以擷取檔案並返回連線設定。</p>
            </li>
          </ol>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Base URLs]</td>
        <td>您必須新增要此驗證器允許的基本URL。 稍後在情境中使用進行自訂API呼叫模組時，您將新增相對路徑至所選的URL。 在這裡輸入URL，您可以控制進行自訂API呼叫模組可以連線的專案，進而提高安全性。<p>針對您想要新增至驗證器的每個基底URL，按一下<b>新增專案</b>並輸入基底URL。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Authentication URL]</td>
        <td>請將此專案留空，以使用<code>https://ims-na1.adobelogin.com</code>的標準Adobe IMS驗證URL。 如果您沒有使用Adobe IMS進行驗證，請輸入用於驗證的URL。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>選取您要連線到生產或非生產環境。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>選取您要連線到服務帳戶還是個人帳戶。</td>
      </tr>
    </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以儲存連線並返回模組。

## 模組

* [進行自訂API呼叫](#make-a-custom-api-call)
* [進行自訂API呼叫（舊版）](#make-a-custom-api-call-legacy)

### 進行自訂API呼叫

此動作模組可讓您呼叫任何AdobeAPI。 它支援大型檔案，而非純文字內文。

此單元已在2024年11月14日推出。 任何在此日期前設定的「Adobe Authenticator >進行自訂API呼叫」都不會處理大型檔案，現在視為「進行自訂API呼叫（舊版）」模組。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>如需建立與Adobe Authenticator模組的連線的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref" >建立連線</a>。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
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
        <p>[!UICONTROL Method]</p>
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body Type]</td>
   <td> 選取此API請求的內文型別：
   <ul>
   <li>application/x-www-form-urlencoded</li>
   <li>原始</li>
   <li>多部分/表單資料</li>
   </ul>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL Fields]  </td>
      <td>
        <p>針對您想要新增至APU要求的每個檔案，按一下[新增專案] <b> </b>並輸入檔案的文字（針對原始資料），或輸入索引鍵<code>uploadedFile</code>並對應檔案的資料。</p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

### 進行自訂API呼叫（舊版）

此動作模組可讓您呼叫任何AdobeAPI。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[!UICONTROL Connection]</td>
     <td>如需建立與Adobe Authenticator模組的連線的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref" >建立連線</a>。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Base URL]</p>
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
        <p>[!UICONTROL Method]</p>
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Query String]  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> 
     </div> </p> </td>     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL Limit]  </td>
      <td>
        <p>輸入您希望模組在一個執行週期內傳回的結果數目上限。</p>
      </td>
    </tr>
  </tbody>
</table>

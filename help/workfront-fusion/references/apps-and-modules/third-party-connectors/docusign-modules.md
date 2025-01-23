---
title: docussign模組
description: ' [!DNL Adobe Workfront Fusion DocuSign] 模組可讓您監視和擷取信封狀態、搜尋和擷取信封，或下載和傳送檔案以登入您的 [!DNL DocuSign] 帳戶。'
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: 94a823a6-3c70-42a1-b6cf-298591dbca15
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 0%

---

# docussign模組

[!DNL Adobe Workfront Fusion] [!DNL DocuSign]模組可讓您監視和擷取信封狀態、搜尋和擷取信封，或下載和傳送檔案以登入您的[!DNL DocuSign]帳戶。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
  <td> <p>[!UICONTROL Pro] 或更高</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 先決條件

若要使用[!DNL DocuSign]模組，您必須有[!DNL DocuSign]帳戶。

## DocuSign API資訊

DocuSign聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>1.18.11</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL DocuSign]連線至[!DNL Workfront Fusion] {#connect-docusign-to-workfront-fusion}

若要為您的[!DNL DocuSign]模組建立連線：

1. 當您開始設定第一個[!DNL DocuSign]模組時，請按一下[!UICONTROL Connection]方塊旁的&#x200B;**[!UICONTROL Add]**。
1. 輸入下列內容：

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td>輸入新[!DNL DocuSign]連線的名稱</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Account type]</td> 
      <td>選取您要連線的帳戶是生產帳戶還是示範帳戶。</td> 
     </tr> 
    </tbody> 
   </table>

1. 繼續執行，如[建立與 [!DNL Adobe Workfront Fusion] 的連線 — 基本指示](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md#connect)中所述。

## [!DNL DocuSign]模組及其欄位

當您設定[!DNL DocuSign]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL DocuSign]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)

### 觸發程序

#### [!UICONTROL Watch envelopes]

當信封已傳送、傳遞、簽署、完成或拒絕時，此觸發模組就會啟動案例。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>選取包含要監視之記錄的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p> 選取您要觀看的事件型別。</p> 
    <ul> 
     <li>[!UICONTROL Document completed]</li> 
     <li>[!UICONTROL Document declined]</li> 
     <li>[!UICONTROL Document sent]</li> 
     <li>[!UICONTROL Document signed]</li> 
     <li>[!UICONTROL New document in Inbox]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Output fields]</p> </td> 
   <td> <p>選取您要納入模組輸出的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中處理的最大記錄數量。</td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Download a document]](#download-a-document)
* [[!UICONTROL Read an envelope]](#read-an-envelope)
* [[!UICONTROL Upload a file to an envelope]](#upload-a-file-to-an-envelope)
* [[!UICONTROL Create a new envelope]](#create-a-new-envelope)
* [[!UICONTROL Add Recipient to Envelope]](#add-recipient-to-envelope)
* [[!UICONTROL Add custom field]](#add-custom-field)
* [[!UICONTROL Modify custom field]](#modify-custom-field)
* [[!UICONTROL Send envelope]](#send-envelope)

#### [!UICONTROL Custom API Call]

此動作模組可讓您執行自訂API呼叫。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Account]</td> 
   <td>輸入或對應您要用來存取[!DNL DocuSign] API的帳戶。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>在網頁伺服器上輸入您希望模組與之互動的位址。</p> <p>您可以輸入相對URL，這表示您不必在開頭包含通訊協定（例如<code>http://</code>）。 這會向網頁伺服器提示互動正在伺服器上發生。</p> <p>例如： <code>[!DNL /api/conversations].create</code></p>  </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 這會決定請求的內容型別。</p> <p>例如，<code> {"Content-type":"application/json"}</code></p> <p>注意：如果您收到錯誤且難以判斷其來源，請考慮根據[!DNL Workfront]檔案修改標題。 如果您的自訂API呼叫傳回422 HTTP請求錯誤，請嘗試使用「Content-Type」：「text/plain」標頭。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>輸入或對應在一個執行週期內要處理的結果數目上限。</td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**範例：**&#x200B;清單信封
>
>下列API呼叫會從您[!DNL DocuSign]帳戶中的指定日期傳回信封：
>
>**URL**： `/v2.1/accounts/{accountId}/envelopes/`
>
>**方法**： `GET`
>
>**查詢字串**：
>
>* **索引鍵**： `from_date`
>
>* **值**： `YYYY-MM-DD`
>
>指定要求何時開始檢查帳戶信封的狀態變更。
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/example-docusign-setup-350x770.png)
>
>結果可以在「束>內文>信封」下模組的輸出中找到。
>
>在我們的範例中，傳回6個信封：
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/docusign-example-output-350x677.png)

#### [!UICONTROL Download a document]

此動作模組會下載單一檔案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到[!DNL Workfront Fusion]</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>選取包含您要下載之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 輸入或對應您要下載的信封識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Document ID]</p> </td> 
   <td> <p>輸入或對應您要下載的檔案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Certificate]</td> 
   <td>若要在下載中包含信封簽署憑證，請選取<strong>[!UICONTROL Yes]</strong>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents by User ID]</td> 
   <td>如果要允許收件者依使用者ID擷取檔案，請選取<strong>[!UICONTROL Yes]</strong>。 例如，如果使用者包含在具有不同可見度的兩個不同製程訂單中，則使用此選項會傳回兩個製程的所有檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encrypt]</td> 
   <td>如果您想要將回應中傳回的PDF位元組加密，供您[!DNL DocuSign]帳戶上設定的所有金鑰管理員使用，請選取<strong>[!UICONTROL Yes]</strong>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>選取語言。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Changes]</td> 
   <td>設定為<strong>[!UICONTROL Yes]</strong>時，傳回PDF的任何變更欄位都會以黃色醒目提示，而選用的簽章或縮寫則會以紅色醒目提示。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watermark]</td> 
   <td> <p>選取<strong>[!UICONTROL No]</strong>以從PDF檔案中移除浮水印。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read an envelope]

此動作模組使用信封ID讀取[!DNL DocuSign]中信封的相關資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到[!DNL Workfront Fusion]</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>選取包含您要讀取資訊之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 輸入或對應包含您要讀取資訊之檔案的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>選取您要顯示在模組輸出中的屬性。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file to an envelope]

此模組會將指定的檔案上傳到DocuSign中的現有信封。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到[!DNL Workfront Fusion]</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>選取包含要上傳檔案之信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 輸入或對應您要上傳檔案之信封的識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>從先前的模組中選取來源檔案，或輸入來源檔案的名稱和資料。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a new envelope]

此動作模組會從範本建立新的信封。 它會傳回新信封的ID以及新信封的狀態。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td>

<td> <p>如需有關將DocuSign帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>下的文章。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Account] </td>
   <td> <p>選取包含要上傳檔案之信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template]</td>
   <td> <p> 選取要從中建立新信封的範本。 根據您選取的[!UICONTROL Account]可使用範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [!UICONTROL After creation]
   </td> 
   <td> <p>選取您要將信封儲存為草稿，還是要傳送信封以供簽署。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[!UICONTROL Template recipients]</td>
    <td>選取此信封的收件者</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Recipient to Envelope]

此動作模組將一或多個收件者新增至現有信封。 如果信封已經傳送，則會傳送電子郵件給收件者。 此模組對已完成的信封無效。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將DocuSign帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Account] </td>
   <td> <p>選取包含要新增收件者信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Envelope ID]</td>
    <td>選取或對應您要新增收件者的信封識別碼。</td>
  </tr> 
  <tr data-mc-conditions="">
    <td role="rowheader">[!UICONTROL Recipient type]</td>
   <td> <p> 選取您要新增至信封的收件者型別。</p> 
    <ul> 
     <li> <p>[!UICONTROL Agent]</p> </li> 
     <li> <p>[!UICONTROL Carbon copy]</p> </li> 
     <li> <p>[!UICONTROL Certified delivery]</p> </li> 
     <li> <p>[!UICONTROL In-person signer]</p> </li> 
     <li> <p>[!UICONTROL Intermediary]</p> </li> 
     <li> <p>[!UICONTROL Signer]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Email]</td>
   <td> <p>輸入或對應您要新增至信封的收件者電子郵件地址。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Name]</td>
   <td>輸入或對應您要新增至信封的收件者名稱。</td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Routing order]</td>
   <td> <p>輸入或對應收件者的路由編號。 路由號碼會決定收件者接收及簽署檔案的順序。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Email body]</td>
   <td>輸入或對應傳送給收件者的電子郵件內文（內容）。</td> 
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Email subject]</td>
   <td>輸入或對應傳送給收件者的電子郵件主旨。</td> 
  </tr> 
    <td role="rowheader">[!UICONTROL Private message]</td>
   <td> <li> <p>只有選取的收件者會看到私人訊息及一般訊息。 私人訊息的上限為1000個字元。</p> </li> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Authentication]</td> 
   <td> <p>選取您要用來確認收件者身分的驗證方法。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL None]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL Access code]</strong> </p> <p>輸入或對映存取碼。</p> </li> 
     <li> <p><strong>[!UICONTROL Phone]</strong> </p> <p>輸入或對應電話號碼</p> </li> 
     <li> <p><strong>[!UICONTROL SMS]</strong> </p> <p>輸入或對應電話號碼</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add custom field]

此動作模組新增自訂欄位至檔案

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到[!DNL Workfront Fusion]</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>選取包含您要新增自訂欄位之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 輸入或對應信封的ID，該信封包含您要新增自訂欄位的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>輸入或對應您要新增之新欄位的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>如果您希望新增的欄位是必填欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>如果您希望顯示欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>輸入或對應新增欄位的值（內容）。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Modify custom field]

此動作模組使用欄位名稱修改自訂欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到[!DNL Workfront Fusion]</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>選取包含您要修改自訂欄位之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 輸入或對應包含要修改自訂欄位之檔案的信封識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field ID]</td> 
   <td>輸入或對應您要修改之欄位的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Field name]</td> 
   <td>輸入或對應您要修改的欄位名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Required]</td> 
   <td>如果您希望修改的欄位成為必填欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show field]</td> 
   <td>如果您希望顯示欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value]</td> 
   <td>輸入或對應已修改欄位的值（內容）。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Send envelope]

此動作模組會傳送草稿信封給其收件者。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到[!DNL Workfront Fusion]</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Account] </td> 
   <td> <p>選取包含要傳送給收件者之草稿信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Envelope ID]</td> 
   <td> <p> 輸入或對應您要傳送給收件者的草稿信封的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

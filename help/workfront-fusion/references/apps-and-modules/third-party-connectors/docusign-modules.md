---
title: docussign模組
description: ' [!DNL Adobe Workfront Fusion DocuSign] 模組可讓您監視和擷取信封狀態、搜尋和擷取信封，或下載和傳送檔案以登入您的 [!DNL DocuSign] 帳戶。'
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: 94a823a6-3c70-42a1-b6cf-298591dbca15
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '2244'
ht-degree: 0%

---

# docussign模組

Adobe Workfront Fusion [!DNL DocuSign]模組可讓您監視和擷取信封狀態、搜尋和擷取信封，或下載和傳送檔案以登入您的[!DNL DocuSign]帳戶。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求</p>
   <p>或</p>
   <p>舊版：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增:</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

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

## 將[!DNL DocuSign]連線至Workfront Fusion {#connect-docusign-to-workfront-fusion}

若要為您的[!DNL DocuSign]模組建立連線：

1. 當您開始設定第一個&#x200B;**[!UICONTROL 模組時，請按一下]**&#x200B;連線[!UICONTROL 方塊旁的]新增[!DNL DocuSign]。
1. 輸入下列：

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL連線名稱]</p> </td> 
      <td>輸入新[!DNL DocuSign]連線的名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL環境]</p> </td> 
      <td>選取您是否連線到非生產環境中的生產環境。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL連線名稱]</p> </td> 
      <td>選取您要連線到服務帳戶還是個人帳戶。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL帳戶型別]</td> 
      <td>選取您要連線的帳戶是生產帳戶還是示範帳戶。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**繼續**&#x200B;以儲存連線並返回模組。

## [!DNL DocuSign]模組及其欄位

當您設定[!DNL DocuSign]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL DocuSign]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)

### 觸發程序

#### [!UICONTROL 看信封]

當信封已傳送、傳遞、簽署、完成或拒絕時，此觸發模組就會啟動案例。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將Docusign連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶] </td> 
   <td> <p>選取包含要監視之記錄的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL事件型別]</td> 
   <td> <p> 選取您要觀看的事件型別。</p> 
    <ul> 
     <li>[！UICONTROL檔案已完成]</li> 
     <li>[！UICONTROL檔案已拒絕]</li> 
     <li>[！UICONTROL檔案已傳送]</li> 
     <li>[！UICONTROL檔案已簽署]</li> 
     <li>[！UICONTROL收件匣中的新檔案]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL輸出]</p> </td> 
   <td> <p>選取您要納入模組輸出的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中處理的最大記錄數量。</td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 新增自訂欄位]](#add-a-custom-field)
* [[!UICONTROL 新增收件者到信封]](#add-recipient-to-envelope)
* [[!UICONTROL 建立新信封]](#create-a-new-envelope)
* [[!UICONTROL 自訂API呼叫]](#custom-api-call)
* [[!UICONTROL 下載檔案]](#download-a-document)
* [[!UICONTROL 修改自訂欄位]](#modify-custom-field)
* [[!UICONTROL 讀取信封]](#read-an-envelope)
* [[!UICONTROL 傳送信封]](#send-envelope)
* [[!UICONTROL 將檔案上傳到信封]](#upload-a-file-to-an-envelope)

#### [!UICONTROL 新增自訂欄位]

此動作模組新增自訂欄位至檔案

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到Workfront Fusion</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶] </td> 
   <td> <p>選取包含您要新增自訂欄位之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL信封ID]</td> 
   <td> <p> 輸入或對應信封的ID，該信封包含您要新增自訂欄位的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL欄位名稱]</td> 
   <td>輸入或對應您要新增之新欄位的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL必填]</td> 
   <td>如果您希望新增的欄位是必填欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL顯示欄位]</td> 
   <td>如果您希望顯示欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL值]</td> 
   <td>輸入或對應新增欄位的值（內容）。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 新增收件者到信封]

此動作模組將一或多個收件者新增至現有信封。 如果信封已經傳送，則會傳送電子郵件給收件者。 此模組對已完成的信封無效。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr data-mc-conditions=""> 
    <td>[！UICONTROL Connection] </td>
   <td> <p>如需有關將DocuSign帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[！UICONTROL帳戶] </td>
   <td> <p>選取包含要新增收件者信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
    <td>[！UICONTROL信封ID]</td>
    <td>選取或對應您要新增收件者的信封識別碼。</td>
  </tr> 
  <tr data-mc-conditions="">
    <td role="rowheader">[！UICONTROL收件者型別]</td>
   <td> <p> 選取您要新增至信封的收件者型別。</p> 
    <ul> 
     <li> <p>[！UICONTROL Agent]</p> </li> 
     <li> <p>[！UICONTROL Carbon copy]</p> </li> 
     <li> <p>[！UICONTROL Certified delivery]</p> </li> 
     <li> <p>[！UICONTROL個人簽署者]</p> </li> 
     <li> <p>[！UICONTROL Intermediate]</p> </li> 
     <li> <p>[！UICONTROL簽署者]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td>[！UICONTROL電子郵件]</td>
   <td> <p>輸入或對應您要新增至信封的收件者電子郵件地址。</p> </td> 
  </tr> 
  <tr> 
    <td>[！UICONTROL名稱]</td>
   <td>輸入或對應您要新增至信封的收件者名稱。</td> 
  </tr> 
  <tr>
    <td>[！UICONTROL路由順序]</td>
   <td> <p>輸入或對應收件者的路由編號。 路由號碼會決定收件者接收及簽署檔案的順序。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL電子郵件內文]</td>
   <td>輸入或對應傳送給收件者的電子郵件內文（內容）。</td> 
  </tr> 
  <tr>
    <td role="rowheader">[！UICONTROL電子郵件主旨]</td>
   <td>輸入或對應傳送給收件者的電子郵件主旨。</td> 
  </tr> 
    <td role="rowheader">[！UICONTROL私人訊息]</td>
   <td> 如果您想要傳送私人訊息給收件者，請輸入或對應訊息的文字。 <p>只有選取的收件者會看到私人訊息及一般訊息。 私人訊息的上限為1000個字元。</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Authentication]</td> 
   <td> <p>選取您要用來確認收件者身分的驗證方法。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL無]</strong> </p> </li> 
     <li> <p><strong>[！UICONTROL存取碼]</strong> </p> <p>輸入或對映存取碼。</p> </li> 
     <li> <p><strong>[！UICONTROL電話]</strong> </p> <p>輸入或對應電話號碼。</p> </li> 
     <li> <p><strong>[！UICONTROL簡訊]</strong> </p> <p>輸入或對應電話號碼。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立新信封]

此動作模組會從範本建立新的信封。 它會傳回新信封的ID以及新信封的狀態。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td>

<td> <p>如需有關將DocuSign帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>下的文章。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL帳戶] </td>
   <td> <p>選取包含要上傳檔案之信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[！UICONTROL範本]</td>
   <td> <p> 選取要從中建立新信封的範本。 根據您選取的[！UICONTROL帳戶]可使用範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL建立後]
   </td> 
   <td> <p>選取您要將信封儲存為草稿，還是要傳送信封以供簽署。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader" >[！UICONTROL範本收件者]</td>
    <td>針對您想要新增至此信封的每個收件者，按一下[新增專案] <b>並輸入下列詳細資料：</b>
    <ul>
    <li><b>存取代碼</b><p>輸入或對應收件者用來存取信封的代碼。<p></li>
    <li><b>電子郵件</b><p>輸入或對應收件者的電子郵件地址。<p></li>
    <li><b>姓名</b><p>輸入或對映收件者的名稱。<p></li>
    <li><b>角色名稱</b><p>輸入或對應收件者的角色名稱。<p></li>
    <li><b>製程訂單</b><p>輸入或對應收件者的路由編號。 路由號碼會決定收件者接收及簽署檔案的順序。<p></li>
    </ul>
    </td>
    </tr>
  <tr> 
   <td role="rowheader">
     [！UICONTROL Allow Print and Sign]
   </td> 
   <td> <p>啟用此選項可允許收件者列印檔案並簽署紙張。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL允許重新指派]
   </td> 
   <td> <p>如果您希望收件者能夠將檔案重新指派給其他使用者，請啟用此選項。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL允許收件者遞回]
   </td> 
   <td> <p>啟用此選項以允許收件者遞回。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL授權副本]
   </td> 
   <td> <p>啟用此選項可將此信封中的檔案標示為授權副本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL自動導覽]
   </td> 
   <td> <p>啟用此選項以設定收件者的自動導覽。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL品牌ID]
   </td> 
   <td> <p>輸入或對映品牌的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL標籤已啟用]
   </td> 
   <td> <p>啟用此選項以啟用檔案標示。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL過期已啟用]
   </td> 
   <td> <p>啟用此選項以設定此信封的有效期。 如果啟用此選項，請填寫以下欄位：<ul><li><b>有效期限</b><p>輸入或對應此信封過期的天數。</p></li><li><b>到期警告</b><p>輸入或對應提醒電子郵件傳送給收件者的到期天數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL Body]
   </td> 
   <td> <p>輸入或對應此信封隨附之電子郵件的內文（內容）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">
     [！UICONTROL主旨]
   </td> 
   <td> <p>輸入或對應此信封隨附之電子郵件的主旨。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂API呼叫]

此動作模組可讓您執行自訂API呼叫。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL帳戶]</td> 
   <td>輸入或對應您要用來存取[!DNL DocuSign] API的帳戶。</td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL URL]</td> 
   <td> <p>輸入或對應相對路徑 <code>https://&lt;BASE_URI>/v2/accounts/&lt;ACCOUNT_ID>.</code></p>  </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 這會決定請求的內容型別。</p> <p>例如，<code> {"Content-type":"application/json"}</code></p> <p>注意：如果您收到錯誤且難以判斷其來源，請考慮根據Workfront檔案修改標題。 如果您的自訂API呼叫傳回422 HTTP請求錯誤，請嘗試使用「Content-Type」：「text/plain」標頭。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL限制]</td> 
   <td>輸入或對應在一個執行週期內要處理的結果數目上限。</td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**範例：**&#x200B;清單信封

下列API呼叫會從您[!DNL DocuSign]帳戶中的指定日期傳回信封：

**URL**： `/v2.1/accounts/{accountId}/envelopes/`

**方法**： `GET`

**查詢字串**：

* **索引鍵**： `from_date`

* **值**： `YYYY-MM-DD`

指定要求何時開始檢查帳戶信封的狀態變更。

![範例Docusign設定](/help/workfront-fusion/references/apps-and-modules/assets/example-docusign-setup-350x770.png)

結果可以在「束>內文>信封」下模組的輸出中找到。

在我們的範例中，傳回6個信封：

![範例docusign輸出](/help/workfront-fusion/references/apps-and-modules/assets/docusign-example-output-350x677.png)

>[!ENDSHADEBOX]

#### [!UICONTROL 下載檔案]

此動作模組會下載單一檔案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到Workfront Fusion</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶] </td> 
   <td> <p>選取包含您要下載之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL信封ID]</td> 
   <td> <p> 輸入或對應您要下載的信封識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL檔案ID]</p> </td> 
   <td> <p>輸入或對應您要下載的檔案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL憑證]</td> 
   <td>啟用此選項以在下載中包含信封簽署憑證。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL檔案，依使用者ID]</td> 
   <td>啟用此選項可允許收件者依使用者ID擷取檔案。 例如，如果使用者包含在具有不同可見度的兩個不同製程訂單中，則使用此選項會傳回兩個製程的所有檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Encry]</td> 
   <td>如果您想要為您[!DNL DocuSign]帳戶上設定的所有金鑰管理員加密回應中傳回的PDF位元組，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Language]</td> 
   <td>選取語言。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL顯示變更]</td> 
   <td>啟用此選項以反白傳回PDF的任何變更欄位，並以黃色反白顯示，並以紅色概述可選簽名或縮寫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Watermark]</td> 
   <td> <p>啟用此選項以啟用浮水印功能。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 修改自訂欄位]

此動作模組使用欄位名稱修改自訂欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到Workfront Fusion</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶] </td> 
   <td> <p>選取包含您要修改自訂欄位之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL信封ID]</td> 
   <td> <p> 輸入或對應包含要修改自訂欄位之檔案的信封識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL欄位ID]</td> 
   <td>輸入或對應您要修改之欄位的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL欄位名稱]</td> 
   <td>輸入或對應您要修改的欄位名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL必填]</td> 
   <td>如果您希望修改的欄位成為必填欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL顯示欄位]</td> 
   <td>如果您希望顯示欄位，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL值]</td> 
   <td>輸入或對應已修改欄位的值（內容）。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取信封]

此動作模組使用信封ID讀取[!DNL DocuSign]中信封的相關資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到Workfront Fusion</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶] </td> 
   <td> <p>選取包含您要讀取資訊之檔案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL信封ID]</td> 
   <td> <p> 輸入或對應信封的ID，該信封包含您要從中讀取資訊的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸出]</td> 
   <td>選取您要顯示在模組輸出中的屬性。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 傳送信封]

此動作模組會傳送草稿信封給其收件者。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到Workfront Fusion</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶] </td> 
   <td> <p>選取包含要傳送給收件者之草稿信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL信封ID]</td> 
   <td> <p> 輸入或對應您要傳送給收件者的草稿信封的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 將檔案上傳到信封]

此模組會將指定的檔案上傳到DocuSign中的現有信封。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL DocuSign]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-docusign-to-workfront-fusion" class="MCXref xref">將[!DNL DocuSign]連線到Workfront Fusion</a>。</p> </td>
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶] </td> 
   <td> <p>選取包含要上傳檔案之信封的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL信封ID]</td> 
   <td> <p> 輸入或對應您要上傳檔案之信封的識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source檔案]</td> 
   <td>從先前的模組中選取來源檔案，或輸入來源檔案的名稱和資料。</td> 
  </tr> 
 </tbody> 
</table>

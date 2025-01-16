---
title: AWS S3模組
description: ' [!DNL Adobe Workfront Fusion AWS] S3模組可讓您對S3儲存貯體執行操作。'
author: Becky
feature: Workfront Fusion
exl-id: 6b2d9dd5-0b33-4297-aea0-aba26072b26a
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 0%

---

# AWS S3模組

[!DNL Adobe Workfront Fusion AWS] S3模組可讓您對S3儲存貯體執行作業。

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

若要使用[!UICONTROL AWS S3]模組，您必須有[!DNL Amazon Web Service]帳戶。

## AWS S3 API資訊

AWS S3聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td>https://s3.{{parameters.region}}.amazonaws.com</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.5.21</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL AWS]連線至[!DNL Workfront Fusion] {#connect-aws-to-workfront-fusion}

若要將[!DNL AWS S3]連線至[!DNL Workfront Fusion]，您必須將您的[!DNL AWS]帳戶連線至[!DNL Workfront Fusion]。 若要這麼做，您首先必須在[!DNL AWS] [!UICONTROL IAM]中建立API使用者。

1. 登入您的[!DNL AWS] [!UICONTROL IAM]帳戶。
1. 導覽至&#x200B;**[!UICONTROL Identity and Access Management]** > **[!UICONTROL Access Management]** > **[!UICONTROL Users]**。

1. 按一下&#x200B;**[!UICONTROL Add User]**。
1. 輸入新使用者的名稱，並在[!UICONTROL Access type]區段中選取&#x200B;**[!UICONTROL Programmatic access]**&#x200B;選項。
1. 按一下&#x200B;**[!UICONTROL Attach existing policies directly]**，然後在搜尋列中搜尋&#x200B;**[!UICONTROL AmazonS3FullAccess]**。 出現時按一下它，然後按一下&#x200B;**[!UICONTROL Next]**。

1. 繼續其他對話方塊畫面，然後按一下&#x200B;**[!UICONTROL Create User]**。
1. 複製提供的&#x200B;**[!UICONTROL Access key ID]**&#x200B;和&#x200B;**[!UICONTROL Secret access key]**。

1. 前往[!DNL Workfront Fusion]並開啟[!DNL AWS S3]模組的&#x200B;**[!UICONTROL Create a connection]**&#x200B;對話方塊。
1. 從步驟7到對應的欄位輸入[!UICONTROL Access key ID]和[!UICONTROL Secret access key]，然後按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線。

已建立連線。 您可以繼續設定模組。

## [!DNL AWS S3]模組及其欄位

當您設定[!DNL AWS S3]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL AWS S3]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [搜尋](#searches)

### 動作

* [[!UICONTROL Create Bucket]](#create-bucket)
* [[!UICONTROL Get File]](#get-file)
* [[!UICONTROL Upload File]](#upload-file)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Create Bucket]

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL AWS]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將[!DNL AWS]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入新儲存貯體的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱AWS檔案中<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html">區域端點</a>的討論。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get File]

從貯體下載檔案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL AWS]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將[!DNL AWS]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html">區域端點</a>討論。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>選取要從中下載檔案的貯體。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Path]</p> </td> 
   <td> <p>輸入檔案的路徑。 範例： <code>/photos/2019/February/image023.jpg</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload File]

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL AWS]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將[!DNL AWS]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html">區域端點</a>討論。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Folder] (可選) </p> </td> 
   <td> <p>指定您要上傳檔案的目標資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers] (可選)</p> </td> 
   <td> <p> 插入請求標頭。 在<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/API_PutObject.html">[!DNL AWS S3]檔案中可找到可用的標頭 — [!UICONTROL PUT]物件</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

如需[!DNL Amazon S3] API的詳細討論，請參閱[[!DNL Amazon S3] [!UICONTROL REST] API簡介](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html)。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL AWS]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將[!DNL AWS]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Region] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html">區域端點</a>討論。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>url輸入主機URL。 路徑必須相對於<code> https://s3.&lt;selected-region>.amazonaws.com/</code>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的[!UICONTROL HTTP]要求方法。 如需詳細資訊，請參閱[!DNL Adobe Workfront Fusion]</a>中的<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!UICONTROL HTTP]要求方法。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers]</td> 
   <td> <p>新增請求標頭。 您可以使用以下常見的請求標頭。 如需更多要求標頭，請參閱<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/RESTCommonRequestHeaders.html">[!DNL AWS S3] API檔案</a>。</p> <p>[!DNL Workfront Fusion] 自動新增授權標頭。</p> 
    <table style="table-layout:auto">
     <col> 
     <col> 
     <thead> 
      <tr> 
       <th>頁首名稱</th> 
       <th> <p> 說明</p> </th> 
      </tr> 
     </thead> 
     <tbody> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Length]</p> </td> 
       <td> <p>根據RFC 2616的訊息長度（沒有標頭）。 載入XML的[!UICONTROL PUT]和作業（例如記錄和ACL）需要此標頭。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Type]</p> </td> 
       <td> <p>資源的內容型別（若請求內容位於內文中）。 範例： <code>text/plain</code>。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-MD5]</p> </td> 
       <td> <p>根據RFC 1864，訊息的base64已編碼128位元MD5摘要（沒有標頭）。 此標頭可用作訊息完整性檢查，以確認資料與原來傳送的資料相同。 雖然這是選擇性的，但建議您使用[!UICONTROL Content-MD5]機製作為端對端的完整性檢查。 如需有關[!UICONTROL REST]要求驗證的詳細資訊，請移至<i>[!DNL Amazon] Simple Storage Service Developer Guide</i>中的<a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html?r=1821">[!UICONTROL REST] Authentication</a>。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Date]</p> </td> 
       <td> <p>根據請求者的目前日期和時間。 範例： <code>Wed, 01 Mar 2006 12:00:00 GMT</code>。 當您指定<code>Authorization </code>標頭時，必須指定<code>x-amz-date</code>或<code>Date </code>標頭。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Expect]</p> </td> 
       <td> <p>當您的應用程式使用[!UICONTROL 100-continue]時，它會在收到確認後才傳送要求內文。 如果郵件根據標題遭到拒絕，則不會傳送郵件內文。 此標頭只有在傳送內文時才能使用。</p> <p>有效值： [!UICONTROL 100-continue]</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
       <td> <p>對於路徑樣式要求，值為<code>s3.amazonaws.com</code>。 對於虛擬樣式要求，值為<code>BucketName.s3.amazonaws.com</code>。 如需詳細資訊，請參閱<i>[!DNL Amazon] Simple Storage Service開發人員指南</i>中的<a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html">虛擬託管</a>。</p> <p>HTTP 1.1需要此標頭（大部分的Toolkit會自動新增此標頭）；HTTP/1.0要求則選填。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-content-sha256]</p> </td> 
       <td> <p>使用簽名版本4驗證請求時，此標頭會提供請求承載的雜湊。 以區塊上傳物件時，請將值設為<code>STREAMING-AWS4-HMAC-SHA256-PAYLOAD</code>，表示簽章僅涵蓋標題且沒有裝載。 如需詳細資訊，請參閱授權標頭的<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-streaming.html">簽章計算：傳輸多個區塊中的裝載（區塊上傳） （[!DNL AWS]簽章版本4）</a>。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-date]</p> </td> 
       <td> <p>根據請求者的目前日期和時間。 範例： <code>Wed, 01 Mar 2006 12:00:00 GMT</code>。 當您指定<code>Authorization </code>標頭時，必須指定<code>x-amz-date</code>或<code>Date </code>標頭。 如果您同時指定兩者，則以<code>x-amz-date</code>標頭指定的值優先。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-security-token]</p> </td> 
       <td> <p>此標題可用於下列情況：</p> 
        <ul> 
         <li>提供[!DNL Amazon DevPay]作業的安全性權杖。 每個使用[!DNL Amazon DevPay]的請求都需要兩個<code>x-amz-security-token</code>標頭：一個用於產品權杖，另一個用於使用者權杖。 當[!DNL Amazon S3]收到驗證要求時，會將計算的簽章與提供的簽章做比較。 用來計算簽章的多值標頭格式不正確，可能會導致驗證問題。</li> 
         <li>提供使用臨時安全性憑證時的安全性權杖。 使用您從IAM取得的臨時安全性認證提出請求時，您必須使用此標頭提供安全性權杖。 若要深入瞭解臨時安全性認證，請前往提出要求。</li> 
        </ul> <p>使用[!DNL Amazon DevPay]的請求和使用臨時安全性認證簽署的請求需要此標頭。</p> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p>新增所需的查詢字串，例如引數或表單欄位。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：   <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL List Files]](#list-files)
* [[!UICONTROL List Folders]](#list-folders)

#### [!UICONTROL List Files]

從指定位置傳回檔案清單。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL AWS]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將[!DNL AWS]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html">區域端點</a>討論。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>選取您要搜尋檔案的[!DNL Amazon S3]儲存貯體。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix] (可選)</p> </td> 
   <td> <p> 要在其中查閱檔案的資料夾路徑，例如 <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Folders]

從指定位置傳回資料夾清單。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL AWS]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將[!DNL AWS]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Region] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱AWS檔案中<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html">區域端點</a>的討論。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>選取您要搜尋資料夾的[!DNL Amazon S3]貯體。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Prefix] (可選)</p> </td> 
   <td> <p> 要在其中查閱資料夾的資料夾路徑，例如 <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

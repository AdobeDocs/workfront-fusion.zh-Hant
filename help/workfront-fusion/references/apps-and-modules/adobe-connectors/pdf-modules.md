---
title: Adobe PDF服務
description: Adobe PDF服務
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: e6fbbc20-4315-4668-9e11-af7cfa82ae66
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '3623'
ht-degree: 0%

---

# [!DNL Adobe PDF Services]

透過[!DNL Adobe Workfront Fusion] [!DNL Adobe PDF Services]，您可以從PDF檔案擷取資料，或從您提供的資料產生新的PDF檔案。 此外，您可以將各種檔案型別轉換為PDF，或將PDF轉換為其他檔案型別。 PDF服務也可讓您合併、壓縮或讀取PDF檔案的中繼資料，以及控制檔案的密碼保護。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

如需用於PDF服務的API的相關資訊，請參閱[Adobe檔案產生API](https://www.adobe.io/apis/documentcloud/dcsdk/doc-generation.html)。

## 使用[!DNL Adobe PDF Services]時的安全性考量

[!DNL Adobe PDF Services]可以讀取、轉換或修改您的檔案，但[!DNL Adobe]和[!DNL Workfront Fusion]都無法儲存您的檔案或資料。 這表示：

* 您可以維持對檔案的控制，包括其安全性
* 您不需要有[!UICONTROL Adobe]儲存空間或雲端儲存空間帳戶即可使用PDF服務。

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
   <p>目前：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要建立OAuth伺服器對伺服器連線，您必須在Adobe開發人員控制檯中新增Adobe PDF Services API 。 新增API時，請選取OAuth伺服器對伺服器選項。

如需指示，請參閱Adobe開發人員檔案中的[使用OAuth將API新增至專案](https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/)。

## Adobe PDF服務API資訊

Adobe PDF服務聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td>https://pdf-services-stage.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v2.1.4</td> 
  </tr>
 </tbody> 
 </table>

## 建立與[!DNL Adobe PDF Services]的連線

若要為您的[!DNL Adobe PDF Services]模組建立連線：

1. 在任何[!DNL Adobe PDF Services]模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL Add]**。

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
            <p>選取您要建立伺服器對伺服器連線還是JWT連線。</p>
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
          <td>輸入您的[!DNL Adobe] [!UICONTROL Client ID]。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。<p>如需尋找認證的說明，請參閱Adobe開發人員檔案中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]</td>
          <td>輸入您的[!DNL Adobe] [!UICONTROL Client Secret]。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。<p>如需尋找認證的說明，請參閱Adobe開發人員檔案中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >認證</a>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Technical account ID] （僅限JWT）</td>
          <td>輸入您的[!DNL Adobe] [!UICONTROL Technical account ID]。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。<p>如需尋找認證的說明，請參閱Adobe開發人員檔案中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >認證</a>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Organization ID] （僅限JWT）</td>
          <td>輸入您的[!DNL Adobe] [!UICONTROL Organization ID]。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。<p>如需尋找認證的說明，請參閱Adobe開發人員檔案中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >認證</a>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Meta scopes] （僅限JWT）</td>
          <td>
            輸入連線所需的任何中繼範圍。
          </td>
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
       </tbody>
    </table>
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以儲存連線並返回模組。


## [!DNL Adobe PDF Services]模組及其欄位

當您設定[!DNL PDF Services]時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些以外，其他欄位可能會顯示，端視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL Combine PDF files]](#combine-pdf-files)
* [[!UICONTROL Compress PDF files]](#compress-pdf-files)
* [[!UICONTROL Convert document to PDF file]](#convert-document-to-pdf-file)
* [[!UICONTROL Convert HTML to PDF file]](#convert-html-to-pdf-file)
* [[!UICONTROL Convert image to PDF file]](#convert-image-to-pdf-file)
* [[!UICONTROL Convert PDF to document]](#convert-pdf-to-document)
* [[!UICONTROL Convert PDF to image]](#convert-pdf-to-image)
* [[!UICONTROL Extract Text / Table]](#extract-text--table)
* [[!UICONTROL Generate document]](#generate-document)
* [[!UICONTROL Linearize a PDF file]](#linearize-a-pdf-file)
* [進行自訂API呼叫](#make-a-custom-api-call)
* [[!UICONTROL OCR for PDF file]](#ocr-for-pdf-file)
* [[!UICONTROL Page manipulation]](#page-manipulation)
* [[!UICONTROL PDF accessibility auto-tag]](#pdf-accessibility-auto-tag)
* [[!UICONTROL PDF file properties]](#pdf-file-properties)
* [[!UICONTROL Protect PDF file]](#protect-pdf-file)
* [[!UICONTROL Remove protection of a PDF file]](#remove-protection-of-a-pdf-file)
* [分割PDF檔案](#split-a-pdf-file)

### [!UICONTROL Combine PDF files]

此動作模組會取用多個PDF檔案，並將其合併為單一PDF檔案。 例如，此模組可以在專案完成時，將[!UICONTROL Workfront]專案中的所有檔案合併為單一PDF。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Documents]</td> 
   <td> <p>您可以使用彙總模組來收集檔案，以組合成PDF，或者手動新增檔案。 </p> <p>我們建議使用[!UICONTROL Array Aggregator]模組來彙總先前模組的輸出。 使用彙總器時，您不需要知道要合併的檔案名稱、位置或數目。 因此，使用彙總比手動輸入要合併的檔案要靈活得多，也更具可擴充性。</p> <p>若要搭配彙總器使用[!UICONTROL Combine PDF]檔案模組，您必須在[!UICONTROL Documents]欄位上啟用對應。 </p> <p>在此範例中，[!UICONTROL Read Related Records]模組會識別與專案相關的檔案，而[!UICONTROL Download Documents]模組會下載每個檔案。 所有PDF會彙總到一個陣列中，然後傳遞到[!UICONTROL Combine PDF]檔案模組。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/combine-example-350x104.png" style="width: 350;height: 104;"> </p> <p>您也可以手動輸入檔案。</p> <p>對於要包含在組合PDF中的每個檔案：</p> 
    <ol> 
     <li value="1"> <p>按一下 [!UICONTROL Add a Document]</p> </li> 
     <li value="2"> <p>在[!UICONTROL Source file]欄位中，選取輸出您要包含之檔案的模組，或對應來源檔案的名稱和資料。 </p> </li> 
     <li value="3"> <p>（選擇性）如果您只想包含來源檔案中的特定頁面，針對您要新增的每個頁面範圍，按一下「[!UICONTROL Pages]」欄位中的「<strong>[!UICONTROL Add item]</strong>」，然後輸入要包含的頁面範圍的第一個和最後一個頁面，再按一下「<strong>[!UICONTROL Add]</strong>」。 您可以從單一檔案中包含多個頁面範圍。</p> </li> 
     <li value="4"> <p>按一下<strong>[!UICONTROL Add]</strong>。 </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Compress PDF files]

此動作模組會取用PDF檔案並加以壓縮。 這對於節省頻寬或記憶體非常有用。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是PDF格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Compression level]</td> 
   <td>選取您要使用的壓縮等級。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert document to PDF file]

此工具會將檔案轉換為PDF檔案。 來源檔案必須是下列其中一種檔案格式：

* DOC
* XLS
* PPT
* TXT
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是下列格式之一：</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>XLS</p> </li> 
     <li> <p>PPT</p> </li> 
     <li> <p>TXT</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>選取來原始檔的預設語言。 這可讓模組選取適當的字型（如果來源檔案中未包含的話）。</p> <p>從下列語言中選取：</p> 
    <ul> 
     <li> <p>en-US （預設）：英文（美國）</p> </li> 
     <li> <p>ca-ES：加泰隆尼亞文（西班牙）</p> </li> 
     <li> <p>cs-CZ：捷克文（捷克共和國）</p> </li> 
     <li> <p>da-DK：丹麥文（丹麥）</p> </li> 
     <li> <p>de-DE：德文（德國）</p> </li> 
     <li> <p>en-AE：英文（阿拉伯聯合大公國）</p> </li> 
     <li> <p>en-GB：英文（英國）</p> </li> 
     <li> <p>en-IL：英文（以色列）</p> </li> 
     <li> <p>en-US：英文（美國）</p> </li> 
     <li> <p>es-ES：西班牙文（西班牙）</p> </li> 
     <li> <p>es-MX：西班牙文（墨西哥）</p> </li> 
     <li> <p>eu-ES：巴斯克文（西班牙）</p> </li> 
     <li> <p>fi-FI：芬蘭文（芬蘭）</p> </li> 
     <li> <p>fr-CA：法文（加拿大）</p> </li> 
     <li> <p>fr-FR：法文（法國）</p> </li> 
     <li> <p>fr-MA：法文（摩洛哥）</p> </li> 
     <li> <p>hr-HR：克羅埃西亞文（克羅埃西亞）</p> </li> 
     <li> <p>hu-HU：匈牙利文（匈牙利）</p> </li> 
     <li> <p>it-IT：義大利文（義大利）</p> </li> 
     <li> <p>ja-JP：日文（日本）</p> </li> 
     <li> <p>kr-KR：韓文（南韓）</p> </li> 
     <li> <p>nb-NO：挪威巴克摩（挪威）</p> </li> 
     <li> <p>nl-NL：荷蘭文（荷蘭）</p> </li> 
     <li> <p>pl-PL：波蘭文（波蘭）</p> </li> 
     <li> <p>pt-BR：葡萄牙文（巴西）</p> </li> 
     <li> <p>pt-PT：葡萄牙文（葡萄牙）</p> </li> 
     <li> <p>ro-RO：羅馬尼亞文（羅馬尼亞）</p> </li> 
     <li> <p>ru-RU：俄文（俄羅斯）</p> </li> 
     <li> <p>sk-SK：斯洛伐克文（斯洛伐克）</p> </li> 
     <li> <p>sl-SI：斯洛維尼亞文（斯洛維尼亞）</p> </li> 
     <li> <p>sv-SE：瑞典文（瑞典）</p> </li> 
     <li> <p>tr-TR：土耳其文（土耳其）</p> </li> 
     <li> <p>uk-UA：烏克蘭文（烏克蘭）</p> </li> 
     <li> <p>zh-CN：中文（中國大陸）</p> </li> 
     <li> <p>zh-TW：中文（台灣）</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert HTML to PDF file]

此工具會將HTML檔案轉換為PDF檔案。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>重要： Source檔案必須為HTML或ZIP格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON]</td> 
   <td> <p>如果您的HTML參照JavaScript變數，您可以在此處包含這些變數。 </p> <p>對於每個變數，按一下<strong>[!UICONTROL Add item]</strong>並包含變數的索引鍵和值。</p> <p>注意：   
     <ul> 
      <li> <p>從ZIP檔案建立PDF時，來源附屬資料必須包含指令碼元素，例如： <code> &lt;script src='./json.js' type='text/javascript'&gt;&lt;/script&gt;</code> </p> </li> 
      <li> <p>從URL建立PDF時，此JSON物件的內容會在轉譯頁面之前插入瀏覽器VM。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include header and footer]</td> 
   <td> <p>啟用此選項以建立PDF檔案的頁首和頁尾。</p> 
    <ul> 
     <li> <p>標題包含日期和檔案標題。</p> </li> 
     <li> <p>頁尾包含檔案名稱和頁碼。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page width]</td> 
   <td>輸入紙張的寬度，以英吋為單位。 模組會使用此資訊來格式化所建立PDF檔案中的頁面。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page height]</td> 
   <td>輸入紙張的高度，以英吋為單位。 模組會使用此資訊來格式化所建立PDF檔案中的頁面。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert image to PDF file]

此工具會將影像轉換為PDF檔案。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和影像檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert PDF to document]

此工具會將PDF檔案轉換為檔案。 您可以為輸出檔案選取下列其中一種格式。

* DOC
* DOCX
* PPTX
* XLSX
* RTF

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是PDF格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>選取您要檔案輸出為的格式：</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>DOCX</p> </li> 
     <li> <p>PPTX</p> </li> 
     <li> <p>XLSX</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td> <p>選取來原始檔的預設語言。 這可讓模組選取適當的字型（如果來源檔案中未包含的話）。</p> <p>從下列語言中選取：</p> 
    <ul> 
     <li> <p>en-US （預設）：英文（美國）</p> </li> 
     <li> <p>ca-ES：加泰隆尼亞文（西班牙）</p> </li> 
     <li> <p>cs-CZ：捷克文（捷克共和國）</p> </li> 
     <li> <p>da-DK：丹麥文（丹麥）</p> </li> 
     <li> <p>de-DE：德文（德國）</p> </li> 
     <li> <p>en-AE：英文（阿拉伯聯合大公國）</p> </li> 
     <li> <p>en-GB：英文（英國）</p> </li> 
     <li> <p>en-IL：英文（以色列）</p> </li> 
     <li> <p>en-US：英文（美國）</p> </li> 
     <li> <p>es-ES：西班牙文（西班牙）</p> </li> 
     <li> <p>es-MX：西班牙文（墨西哥）</p> </li> 
     <li> <p>eu-ES：巴斯克文（西班牙）</p> </li> 
     <li> <p>fi-FI：芬蘭文（芬蘭）</p> </li> 
     <li> <p>fr-CA：法文（加拿大）</p> </li> 
     <li> <p>fr-FR：法文（法國）</p> </li> 
     <li> <p>fr-MA：法文（摩洛哥）</p> </li> 
     <li> <p>hr-HR：克羅埃西亞文（克羅埃西亞）</p> </li> 
     <li> <p>hu-HU：匈牙利文（匈牙利）</p> </li> 
     <li> <p>it-IT：義大利文（義大利）</p> </li> 
     <li> <p>ja-JP：日文（日本）</p> </li> 
     <li> <p>kr-KR：韓文（南韓）</p> </li> 
     <li> <p>nb-NO：挪威巴克摩（挪威）</p> </li> 
     <li> <p>nl-NL：荷蘭文（荷蘭）</p> </li> 
     <li> <p>pl-PL：波蘭文（波蘭）</p> </li> 
     <li> <p>pt-BR：葡萄牙文（巴西）</p> </li> 
     <li> <p>pt-PT：葡萄牙文（葡萄牙）</p> </li> 
     <li> <p>ro-RO：羅馬尼亞文（羅馬尼亞）</p> </li> 
     <li> <p>ru-RU：俄文（俄羅斯）</p> </li> 
     <li> <p>sk-SK：斯洛伐克文（斯洛伐克）</p> </li> 
     <li> <p>sl-SI：斯洛維尼亞文（斯洛維尼亞）</p> </li> 
     <li> <p>sv-SE：瑞典文（瑞典）</p> </li> 
     <li> <p>tr-TR：土耳其文（土耳其）</p> </li> 
     <li> <p>uk-UA：烏克蘭文（烏克蘭）</p> </li> 
     <li> <p>zh-CN：中文（中國大陸）</p> </li> 
     <li> <p>zh-TW：中文（台灣）</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert PDF to image]

此工具會將PDF轉換為PNG或JPEG格式的影像，然後輸出為清單或合併為ZIP。

如果輸出為ZIP檔，PDF會轉換為每頁一個影像，而每個影像以頁碼結束。 然後，影像檔案會合併至ZIP檔案中。

例如，一個名為「TestFile」、有8個頁面的檔案會產生8個影像，分別命名為「TestFile_1」和「TestFile_8」。 此模組的輸出是包含8個影像的ZIP檔案。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是PDF格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Files Format]</td> 
   <td> <p>選取您要檔案輸出為的格式：</p> 
    <ul> 
     <li>PNG</li> 
     <li>JPEG</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output type]</td> 
   <td> <p>選取您要將檔案輸出為檔案清單還是ZIP檔案。</td> 
  </tr> 
  <tr> 
 </tbody> 
</table>

### [!UICONTROL Extract Text / Table]

此動作模組可讓您從PDF檔案中擷取資料。 模組會輸出個別的文字元素，例如段落或表格單一儲存格中的文字。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Elements that should be extracted as JSON]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Text]</p> </li> 
     <li> <p>[!UICONTROL Tables]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Extract Bounding boxes?]</td> 
   <td>啟用此選項以擷取有關文字邊界方框的資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include styling information for output?]</td> 
   <td>啟用此選項以將樣式資訊新增到輸出JSON。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Generate document]

[!UICONTROL Generate document]模組是建立包含您選取之資料的PDF的強大方法。 您可以使用[!DNL Microsoft Word]範本或以JSON格式提供資料來格式化它。

如需[!UICONTROL [!DNL Adobe PDF Services] Generate document]功能的詳細資訊，請參閱[!DNL Adobe Document Services]檔案中的[檔案產生概觀](https://www.adobe.io/apis/documentcloud/dcsdk/docs.html)。

* [搭配 [!DNL Microsoft Word] 範本](#use-the-generate-document-module-with-a-microsoft-word-template)使用[!UICONTROL Generate document]模組
* [使用[!UICONTROL Generate document]模組搭配JSON](#use-the-generate-document-module-with-json)

#### 搭配[!DNL Microsoft Word]範本使用[!UICONTROL Generate document]模組


>[!NOTE]
>
>有關Microsoft Word範本的討論，請參閱[Microsoft Word範本模組](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-word-templates-modules.md)。
>
>您不需要使用Microsoft Word範本模組，即可搭配「PDF服務」的「產生檔案」模組使用Microsoft Word範本。


若要搭配[!UICONTROL Microsoft Word]範本使用[!UICONTROL Generate document]模組，您必須先建立範本。 如需指示，請在[!DNL Microsoft Office]檔案中搜尋「建立範本」。

填寫[!UICONTROL Generate document]模組欄位，如下所示：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>此來源檔案是模組用來產生新PDF的[!DNL Microsoft Word]範本。</p> <p>建議您在[!DNL Workfront]中為您在[!DNL Workfront Fusion]中使用的[!DNL Microsoft Word]範本建立專案。 然後您可以使用[!DNL Workfront] &gt; [!UICONTROL Download document]模組，將適當的範本提取到您的情境中。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>選取產生檔案的格式。</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>對於範本中要以文字取代的每個值標籤，請填入下列內容：</p> 
    <ul> 
     <li> <p>[!UICONTROL Key]</p> <p>輸入金鑰。 在範本中，索引鍵是值標籤中顯示的文字。 例如，如果您想要將文字置入值標籤<code>&#123;&#123;name&#125;&#125;</code>中，請在索引鍵欄位中輸入<code>name </code>。</p> </li> 
     <li> <p>值型別</p> <p>選取值欄位中的資料是值、物件或物件陣列。</p> </li> 
     <li> <p>[!UICONTROL Value]</p> <p>輸入或對應您要出現在產生檔案中的文字，以取代值標籤。</p> </li> 
    </ul> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/generate-with-template-350x241.png" style="width: 350;height: 241;"> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 使用[!UICONTROL Generate document]模組搭配JSON

若要搭配JSON使用[!UICONTROL Generate document]模組，請依照下列方式填寫欄位：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source File]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p>選取產生檔案的格式。</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data for merge]</td> 
   <td> <p>若要在此模組中使用JSON，您必須在此欄位上啟用對應。</p> <p>輸入或對應JSON以從中產生檔案。 </p> <p>您可以直接在此欄位中輸入JSON，或從JSON模組對應JSON輸出。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Linearize a PDF file]

此工具會將PDF檔案線性化，以建立網頁最佳化的PDF檔案。 線性PDF檔案可以逐頁檢視，而不需要下載整份檔案。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 進行自訂API呼叫

此動作模組會向PDF服務API傳送自訂HTTP請求。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> 輸入相對路徑或URL。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>針對您想要新增至API呼叫的每個欄位，按一下<b>新增專案</b>，然後輸入欄位的索引鍵和選擇性值。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


### [!UICONTROL OCR for PDF file]

此工具會在檔案上執行光學字元辨識(OCR)並產生PDF。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Language]</td> 
   <td>選取此檔案的語言。<p>如需語言選項，請參閱本文中的<a href="#convert-document-to-pdf-file" class="MCXref xref" >將檔案轉換成PDF檔案</a>。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL OCR type]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL Modified original image] type可確保文字可搜尋且可供選取，但在清除過程中修改原始影像（例如，扭曲影像），然後將不可見的文字圖層置入其上。 此型別會移除不想要的成品，在某些情況下，可能會導致檔案更易讀取。 </p> </li> 
     <li> <p>[!UICONTROL Unchanged original image] 文字也會將可搜尋的文字圖層覆蓋在原始影像上，但在此情況下，原始影像不會變更。 此型別會產生原始影像的最大逼真度。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Page manipulation]

此模組可讓您選擇性地旋轉或刪除PDF檔案中的頁面。 例如，您可以將直向檢視變更為橫向檢視，或從PDF檔案中移除某些頁面。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Action]</td> 
   <td> <p>選取您要對檔案執行的動作。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Delete]</b> </p> <p>選取此選項以從檔案刪除頁面。</p><p>針對您要刪除的每個頁面範圍，按一下<strong>[!UICONTROL Add]</strong>，然後輸入頁面範圍的第一個和最後一個頁面。 </p> <p>注意：   
     <ul> 
      <li> <p>您可以使用負數從檔案結尾往回計數。 檔案的最後一頁為–1，最後一頁的第二頁為–2，依此類推。</p> </li> 
      <li> <p>若要刪除單一頁面，請將相同的頁碼設定為範圍的開始和結束。</p></ul> </li> 
     <li> <p><b>[!UICONTROL Rotate]</b> </p> <p>選取此選項可旋轉頁面，然後輸入想要相對於檔案頁面的起始方向旋轉檔案頁面的角度（以順時針角度為單位）。</p> <p>若要從直向旋轉或橫向旋轉，請將頁面旋轉90度或270度。</p> <p>如果頁面上下顛倒，請將其旋轉180度。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Pages]</td> 
   <td> <p>針對您要刪除的每個頁面範圍，按一下<strong>[!UICONTROL Add]</strong>，然後輸入頁面範圍的第一個和最後一個頁面。 </p> <p>注意：   
     <ul> 
      <li> <p>您可以使用負數從檔案結尾往回計數。 檔案的最後一頁為–1，最後一頁的第二頁為–2，依此類推。</p> </li> 
      <li> <p>若要刪除單一頁面，請將相同的頁碼設定為範圍的開始和結束。</p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中處理的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF accessibility auto-tag]

此動作模組會建立標籤為協助工具使用案例的PDF。 這樣也會建立選用的Microsoft Excel報表，列出問題並提供修正建議。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shift Headings]</td> 
   <td> <p>啟用此選項以移動檔案上的標題。</p> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Generate Report]</td> 
   <td> <p>啟用此選項可產生一份報告，列出PDF中的協助工具問題及其位置，並提供如何修正這些問題的建議。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF file properties]

此工具會擷取有關檔案的基本資訊，例如：

* 頁數
* PDF版本
* 檔案是否已加密
* 檔案是否已線性化
* 檔案是否包含內嵌檔案

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Protect a PDF file]

此工具使用使用者或擁有者密碼保護PDF檔案的安全。 它也會對某些功能設定限制，例如在PDF檔案中列印、編輯和複製。 您可以選取要加密的內容型別和加密演演算法。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是PDF格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password Protection Type]</td> 
   <td> <p>啟用此選項以使用密碼來加密輸入PDF檔案。 如果啟用此選項，則必須指定並輸入下列其中一或兩個的值： </p> 
    <ul> 
     <li> <p>[!UICONTROL User Password]</p> </li> 
     <li> <p>[!UICONTROL Owner Password] </p> </li> 
    </ul> <p>每個密碼的長度最多可達128個字元。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Encryption Algorithm]</td> 
   <td> <p>選取加密演演算法。 </p> 
    <ul> 
     <li> <p>[!UICONTROL AES-128 encryption]</p> <p>密碼僅支援LATIN-I字元。 </p> </li> 
     <li> <p>[!UICONTROL AES-256 encryption]</p> <p>密碼支援Unicode字元集</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content to Encrypt]</td> 
   <td> <p>選取要加密的內容型別。</p> 
    <ul> 
     <li> <p>[!UICONTROL All content]</p> </li> 
     <li> <p>[!UICONTROL All content except metadata]</p> </li> 
     <li> <p>[!UICONTROL Only embedded data] </p> </li> 
    </ul> <p>選取「[!UICONTROL Only embedded data]」會使任何提供的存取許可權變成無效。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Permissions]</td> 
   <td> <p>選取您要包含的任何許可權，以允許列印、編輯或內容複製。</p> <p>只有在[!UICONTROL Password Protection Type]欄位中設定[!UICONTROL Owner Password]時，才會使用許可權設定。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Remove protection of a PDF file]

此工具會從PDF檔案中移除安全性（密碼保護）。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是PDF格式。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password]</td> 
   <td>輸入目前保護檔案的密碼。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Split a PDF file]

此動作模組會將PDF檔案分割成多個較小的檔案。 您可以指定是否依檔案數、每個檔案的頁數或頁面範圍進行分割。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>選取要用於此模組的連線。</p> 如需建立[!DNL Adobe PDF Services]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與[!DNL Adobe PDF Services]</a>的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是PDF格式。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split option]</td> 
   <td>選取您要如何分割檔案。 
   <ul>
   <li><p><b>頁面範圍</b></p><p>針對您想要分割成個別檔案的每個頁面範圍，按一下<b>新增</b>，然後輸入您要開始的頁面和您要結束的頁面。</p></li>
   <li><p><b>頁數</b></p><p>輸入您要納入新檔案中的頁數。</p></li>
   <li><p><b>檔案計數</b></p><p>輸入要分割檔案的平均大小檔案數目。</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>
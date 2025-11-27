---
title: Adobe PDF Services
description: Adobe PDF Services
author: Becky
draft: Probably
feature: Workfront Fusion, Digital Content and Documents
exl-id: e6fbbc20-4315-4668-9e11-af7cfa82ae66
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: ht
source-wordcount: '4151'
ht-degree: 100%

---

# [!DNL Adobe PDF Services]

透過 Adobe Workfront Fusion [!DNL Adobe PDF Services]，您可以從 PDF 檔案擷取資料，或從您提供的資料產生新的 PDF 檔案。此外，您可以將不同的檔案類型轉換成 PDF，或將 PDF 轉換成其他檔案類型。您也可以使用 PDF Services 合併、壓縮或讀取 PDF 檔案的後設資料，以及控制檔案的密碼保護。

關於建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)之下的文章。

關於模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)之下的文章。

如需 PDF Services 使用的 API 相關資訊，請參閱 [Adobe Document Generation API](https://www.adobe.io/apis/documentcloud/dcsdk/doc-generation.html)。

## 使用 [!DNL Adobe PDF Services] 時的安全性考量

[!DNL Adobe PDF Services] 可以讀取、轉換或修改您的檔案，但 [!DNL Adobe] 和 Workfront Fusion 都無法儲存您的檔案或資料。這表示：

* 您保有對檔案的控制權，包括其安全性
* 您不需要擁有 [!UICONTROL Adobe] 儲存空間或雲端儲存空間帳戶，即可使用 PDF Services。

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

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要建立 OAuth 伺服器對伺服器連線，您必須在 Adobe Developers Console 中新增 Adobe PDF Services API。新增 API 時，請選取 OAuth 伺服器對伺服器選項。

如需相關說明，請參閱 Adobe 開發人員文件中的[使用 OAuth 使用者驗證認證將 API 新增至專案](https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication)。

## Adobe PDF Services API 資訊

Adobe PDF Services 連接器使用以下項目：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>https://pdf-services-stage.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v2.1.4</td> 
  </tr>
 </tbody> 
 </table>

## 建立與 [!DNL Adobe PDF Services] 的連線

若要為您的 [!DNL Adobe PDF Services] 模組建立連線：

1. 在任何 [!DNL Adobe PDF Services] 模組中，按一下「連線」方塊旁的「**[!UICONTROL 新增]**」。

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
            <p>選取您要建立伺服器對伺服器連線或是 JWT 連線。</p>
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
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端 ID]。此資訊可在 [!DNL Adobe Developer Console] 的「[!UICONTROL 認證詳細資訊]」區段中找到。<p>如需關於尋找認證的說明，請參閱 Adobe 開發人員文件中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端密碼]。此資訊可在 [!DNL Adobe Developer Console] 的「[!UICONTROL 認證詳細資訊]」區段中找到。<p>如需關於尋找認證的說明，請參閱 Adobe 開發人員文件中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >認證</a>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 技術帳戶 ID] (僅限 JWT)</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 技術帳戶 ID]。此資訊可在 [!DNL Adobe Developer Console] 的「[!UICONTROL 認證詳細資訊]」區段中找到。<p>如需關於尋找認證的說明，請參閱 Adobe 開發人員文件中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >認證</a>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 組織 ID] (僅限 JWT)</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 組織 ID]。此資訊可在 [!DNL Adobe Developer Console] 的「[!UICONTROL 認證詳細資訊]」區段中找到。<p>如需關於尋找認證的說明，請參閱 Adobe 開發人員文件中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth-user-authentication#credentials" class="MCXref xref" >認證</a>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 中繼範圍] (僅限 JWT)</td>
          <td>
            輸入連線所需的任何中繼範圍。
          </td>
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
       </tbody>
    </table>
1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。


## [!DNL Adobe PDF Services] 模組及其欄位

當您設定 [!DNL PDF Services] 時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他欄位。模組中的粗體標題表示為必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL 合併 PDF 檔案]](#combine-pdf-files)
* [[!UICONTROL 壓縮 PDF 檔案]](#compress-pdf-files)
* [[!UICONTROL 將文件轉換成 PDF 檔案]](#convert-document-to-pdf-file)
* [[!UICONTROL 將 HTML 轉換成 PDF 檔案]](#convert-html-to-pdf-file)
* [[!UICONTROL 將影像轉換成 PDF 檔案]](#convert-image-to-pdf-file)
* [[!UICONTROL 將 PDF 轉換成文件]](#convert-pdf-to-document)
* [[!UICONTROL 將 PDF 轉換成影像]](#convert-pdf-to-image)
* [[!UICONTROL 擷取文字/表格]](#extract-text--table)
* [[!UICONTROL 產生文件]](#generate-document)
* [[!UICONTROL 將 PDF 檔案線性化]](#linearize-a-pdf-file)
* [進行自訂的 API 呼叫](#make-a-custom-api-call)
* [[!UICONTROL PDF 檔案的 OCR]](#ocr-for-pdf-file)
* [[!UICONTROL 頁面操作]](#page-manipulation)
* [[!UICONTROL PDF 無障礙自動標記]](#pdf-accessibility-auto-tag)
* [[!UICONTROL PDF 檔案屬性]](#pdf-file-properties)
* [[!UICONTROL 保護 PDF 檔案]](#protect-pdf-file)
* [[!UICONTROL 移除 PDF 檔案的保護]](#remove-protection-of-a-pdf-file)
* [分割 PDF 檔案](#split-a-pdf-file)

### [!UICONTROL 合併 PDF 檔案]

此動作模組會取用多個 PDF 檔案，並將其合併為單一個 PDF 檔案。例如，此模組可在 [!UICONTROL Workfront] 專案完成後，將專案中所有文件合併為單一 PDF。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 文件]</td> 
   <td> <p>您可以使用彙總器模組彙集文件並合併為 PDF，也可以手動新增文件。 </p> <p>我們建議使用 [!UICONTROL 陣列彙總器] 模組，彙總來自先前模組的輸出內容。使用彙總器時，您不需要知道要合併的檔案之名稱、位置或數量。因此，比起手動輸入要合併的文件，使用彙總器是更加靈活且可擴展的方法。</p> <p>若要將[!UICONTROL 合併 PDF] 檔案模組與彙總器搭配使用，您必須啟用[!UICONTROL 文件]欄位的對應功能。 </p> <p>於此範例中，[!UICONTROL 讀取相關記錄]模組會找出與專案相關的文件，而[!UICONTROL 下載文件]模組會下載每個文件。所有 PDF 會彙總成為陣列，此陣列會傳遞至[!UICONTROL 合併 PDF] 檔案模組。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/combine-example-350x104.png" style="width: 350;height: 104;"> </p> <p>您也可以手動輸入文件。</p> <p>針對要納入合併 PDF 中的每個文件進行以下動作：</p> 
    <ol> 
     <li value="1"> <p>按一下「[!UICONTROL 新增文件]」</p> </li> 
     <li value="2"> <p>在「[!UICONTROL 來源檔案]」欄位中，選取會輸出您要包含之文件的模組，或對應來源檔案的名稱和資料。 </p> </li> 
     <li value="3"> <p>(選用) 若您只想包含來源檔案中的某些頁面，對於您要新增的每個頁面範圍，按一下「[!UICONTROL 頁面]」欄位中的「<strong>[!UICONTROL 新增項目]</strong>」，然後輸入要納入的頁面範圍之第一頁和最後一頁，再按一下「<strong>[!UICONTROL 新增]</strong>」。您可以包含單一文件中的多個頁面範圍。</p> </li> 
     <li value="4"> <p>按一下「<strong>[!UICONTROL 新增]</strong>」。 </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 壓縮 PDF 檔案]

此動作模組會取用 PDF 檔案並加以壓縮。這樣做有助於節省頻寬或記憶體。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是 PDF 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 壓縮等級]</td> 
   <td>選取您要使用的壓縮等級。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 將文件轉換成 PDF 檔案]

此工具可將文件轉換成 PDF 檔案。來源檔案必須是下列其中一種文件格式：

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
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是下列其中一種格式：</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>XLS</p> </li> 
     <li> <p>PPT</p> </li> 
     <li> <p>TXT</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 語言]</td> 
   <td> <p>選取來源文件的預設語言。選取語言後，若來源檔案中未包含字型的話，模組可以選取適當的字型。</p> <p>從下列語言中選取：</p> 
    <ul> 
     <li> <p>en-US (預設)：英文 (美國)</p> </li> 
     <li> <p>ca-ES：加泰隆尼亞文 (西班牙)</p> </li> 
     <li> <p>cs-CZ：捷克文 (捷克共和國)</p> </li> 
     <li> <p>da-DK：丹麥文 (丹麥)</p> </li> 
     <li> <p>de-DE：德文 (德國)</p> </li> 
     <li> <p>en-AE：英文 (阿拉伯聯合大公國)</p> </li> 
     <li> <p>en-GB：英文 (英國)</p> </li> 
     <li> <p>en-IL：英文 (以色列)</p> </li> 
     <li> <p>en-US：英文 (美國)</p> </li> 
     <li> <p>es-ES：西班牙文 (西班牙)</p> </li> 
     <li> <p>es-MX：西班牙文 (墨西哥)</p> </li> 
     <li> <p>eu-ES：巴斯克文 (西班牙)</p> </li> 
     <li> <p>fi-FI：芬蘭文 (芬蘭)</p> </li> 
     <li> <p>fr-CA：法文 (加拿大)</p> </li> 
     <li> <p>fr-FR：法文 (法國)</p> </li> 
     <li> <p>fr-MA：法文 (摩洛哥)</p> </li> 
     <li> <p>hr-HR：克羅埃西亞文 (克羅埃西亞)</p> </li> 
     <li> <p>hu-HU：匈牙利文 (匈牙利)</p> </li> 
     <li> <p>it-IT：義大利文 (義大利)</p> </li> 
     <li> <p>ja-JP：日文 (日本)</p> </li> 
     <li> <p>kr-KR：韓文 (南韓)</p> </li> 
     <li> <p>nb-NO：挪威博克莫爾文 (挪威)</p> </li> 
     <li> <p>nl-NL：荷蘭文 (荷蘭)</p> </li> 
     <li> <p>pl-PL：波蘭文 (波蘭)</p> </li> 
     <li> <p>pt-BR：葡萄牙文 (巴西)</p> </li> 
     <li> <p>pt-PT：葡萄牙文 (葡萄牙)</p> </li> 
     <li> <p>ro-RO：羅馬尼亞文 (羅馬尼亞)</p> </li> 
     <li> <p>ru-RU：俄文 (俄羅斯)</p> </li> 
     <li> <p>sk-SK：斯洛伐克文 (斯洛伐克)</p> </li> 
     <li> <p>sl-SI：斯洛維尼亞文 (斯洛維尼亞)</p> </li> 
     <li> <p>sv-SE：瑞典文 (瑞典)</p> </li> 
     <li> <p>tr-TR：土耳其文 (土耳其)</p> </li> 
     <li> <p>uk-UA：烏克蘭文 (烏克蘭)</p> </li> 
     <li> <p>zh-CN：中文 (中國大陸)</p> </li> 
     <li> <p>zh-TW：中文 (台灣)</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 將 HTML 轉換成 PDF 檔案]

此工具可將 HTML 檔案轉換成 PDF 檔案。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>重要：來源檔案必須是 HTML 或 ZIP 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON]</td> 
   <td> <p>若您的 HTML 參照 JavaScript 變數，您可以在這裡納入這些變數。 </p> <p>針對每個變數，按一下「<strong>[!UICONTROL 新增項目]</strong>」並納入變數的索引鍵和值。</p> <p>注意：   
     <ul> 
      <li> <p>使用 ZIP 檔案作為來源建立 PDF 時，來源附屬資料必須包含指令碼元素，例如：<code> &lt;script src='./json.js' type='text/javascript'&gt;&lt;/script&gt;</code> </p> </li> 
      <li> <p>使用 URL 作為來源建立 PDF 時，此 JSON 物件的內容會在頁面轉譯之前注入瀏覽器 VM 中。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 包含頁首和頁尾]</td> 
   <td> <p>啟用此選項以建立 PDF 文件的頁首和頁尾。</p> 
    <ul> 
     <li> <p>頁首包含日期和文件標題。</p> </li> 
     <li> <p>頁尾包含檔案名稱和頁碼。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 頁面寬度]</td> 
   <td>輸入紙張的寬度，以英吋為單位。此模組會使用這項資訊來設定所建立 PDF 檔案的頁面格式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 頁面高度]</td> 
   <td>輸入紙張的高度，以英吋為單位。此模組會使用這項資訊來設定所建立 PDF 檔案的頁面格式。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 將影像轉換成 PDF 檔案]

此工具可將影像轉換成 PDF 檔案。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和影像檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 將 PDF 轉換成文件]

此工具可將 PDF 檔案轉換成文件。您可以選取下列其中一種作為輸出檔案的格式。

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
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是 PDF 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出檔案格式]</td> 
   <td> <p>選取檔案輸出時要使用的格式：</p> 
    <ul> 
     <li> <p>DOC</p> </li> 
     <li> <p>DOCX</p> </li> 
     <li> <p>PPTX</p> </li> 
     <li> <p>XLSX</p> </li> 
     <li> <p>RTF</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 語言]</td> 
   <td> <p>選取來源文件的預設語言。選取語言後，若來源檔案中未包含字型的話，模組可以選取適當的字型。</p> <p>從下列語言中選取：</p> 
    <ul> 
     <li> <p>en-US (預設)：英文 (美國)</p> </li> 
     <li> <p>ca-ES：加泰隆尼亞文 (西班牙)</p> </li> 
     <li> <p>cs-CZ：捷克文 (捷克共和國)</p> </li> 
     <li> <p>da-DK：丹麥文 (丹麥)</p> </li> 
     <li> <p>de-DE：德文 (德國)</p> </li> 
     <li> <p>en-AE：英文 (阿拉伯聯合大公國)</p> </li> 
     <li> <p>en-GB：英文 (英國)</p> </li> 
     <li> <p>en-IL：英文 (以色列)</p> </li> 
     <li> <p>en-US：英文 (美國)</p> </li> 
     <li> <p>es-ES：西班牙文 (西班牙)</p> </li> 
     <li> <p>es-MX：西班牙文 (墨西哥)</p> </li> 
     <li> <p>eu-ES：巴斯克文 (西班牙)</p> </li> 
     <li> <p>fi-FI：芬蘭文 (芬蘭)</p> </li> 
     <li> <p>fr-CA：法文 (加拿大)</p> </li> 
     <li> <p>fr-FR：法文 (法國)</p> </li> 
     <li> <p>fr-MA：法文 (摩洛哥)</p> </li> 
     <li> <p>hr-HR：克羅埃西亞文 (克羅埃西亞)</p> </li> 
     <li> <p>hu-HU：匈牙利文 (匈牙利)</p> </li> 
     <li> <p>it-IT：義大利文 (義大利)</p> </li> 
     <li> <p>ja-JP：日文 (日本)</p> </li> 
     <li> <p>kr-KR：韓文 (南韓)</p> </li> 
     <li> <p>nb-NO：挪威博克莫爾文 (挪威)</p> </li> 
     <li> <p>nl-NL：荷蘭文 (荷蘭)</p> </li> 
     <li> <p>pl-PL：波蘭文 (波蘭)</p> </li> 
     <li> <p>pt-BR：葡萄牙文 (巴西)</p> </li> 
     <li> <p>pt-PT：葡萄牙文 (葡萄牙)</p> </li> 
     <li> <p>ro-RO：羅馬尼亞文 (羅馬尼亞)</p> </li> 
     <li> <p>ru-RU：俄文 (俄羅斯)</p> </li> 
     <li> <p>sk-SK：斯洛伐克文 (斯洛伐克)</p> </li> 
     <li> <p>sl-SI：斯洛維尼亞文 (斯洛維尼亞)</p> </li> 
     <li> <p>sv-SE：瑞典文 (瑞典)</p> </li> 
     <li> <p>tr-TR：土耳其文 (土耳其)</p> </li> 
     <li> <p>uk-UA：烏克蘭文 (烏克蘭)</p> </li> 
     <li> <p>zh-CN：中文 (中國大陸)</p> </li> 
     <li> <p>zh-TW：中文 (台灣)</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 將 PDF 轉換成影像]

此工具可將 PDF 轉換成 PNG 或 JPEG 格式的影像，此影像隨後以清單形式輸出或合併成 ZIP 檔。

若輸出為 ZIP 檔，PDF 會將每頁轉換成一張影像，而每張影像的名稱結尾為頁碼。接著影像檔案會合併成一個 ZIP 檔。

比如，一個共有 8 頁且名為「TestFile」的檔案會產生 8 張影像，分別命名為「TestFile_1」到「TestFile_8」。此模組會輸出含有 8 張影像的 ZIP 檔案。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是 PDF 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出檔案格式]</td> 
   <td> <p>選取檔案輸出時要使用的格式：</p> 
    <ul> 
     <li>PNG</li> 
     <li>JPEG</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出類型]</td> 
   <td> <p>選取要將檔案輸出為檔案清單或是 ZIP 檔案。</td> 
  </tr> 
  <tr> 
 </tbody> 
</table>

### [!UICONTROL 擷取文字/表格]

您可以藉由這個動作模組從 PDF 檔案擷取資料。此模組會輸出個別的文字元素，例如一個段落或表格的單一儲存格中的文字。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 應擷取為 JSON 的元素]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL 文字]</p> </li> 
     <li> <p>[!UICONTROL 表格]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 是否擷取邊界方框？]</td> 
   <td>啟用此選項可擷取關於文字邊界方框的資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 是否包含輸出的樣式資訊？]</td> 
   <td>啟用此選項可將樣式資訊新增至輸出 JSON 中。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 產生文件]

[!UICONTROL 產生文件]模組是建立包含您選取的資料之 PDF 的有效方法。您可以使用 [!DNL Microsoft Word] 範本來設定其格式，或使用 JSON 格式提供資料。

如需關於[!UICONTROL [!DNL Adobe PDF Services]產生文件]功能的詳細資訊，請參閱 [!DNL Adobe Document Services] 文件中的[產生文件概觀](https://www.adobe.io/apis/documentcloud/dcsdk/docs.html)。

* [搭配  [!DNL Microsoft Word]  範本使用[!UICONTROL 產生文件]模組](#use-the-generate-document-module-with-a-microsoft-word-template)
* [搭配 JSON 使用[!UICONTROL 產生文件]模組](#use-the-generate-document-module-with-json)

#### 搭配 [!DNL Microsoft Word] 範本使用[!UICONTROL 產生文件]模組


>[!NOTE]
>
>有關 Microsoft Word 範本的討論，請參閱 [Microsoft Word 範本模組](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-word-templates-modules.md)。
>
>您不需要使用 Microsoft Word 範本模組，也可以搭配 PDF Services 的產生檔案模組使用 Microsoft Word 範本。


若要搭配 [!UICONTROL Microsoft Word] 範本使用[!UICONTROL 產生檔案]模組，您必須先建立範本。如需相關說明，請在 [!DNL Microsoft Office] 文件中搜尋「建立範本」。

依照下列內容填入[!UICONTROL 產生文件]模組欄位：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>此來源檔案是模組用來產生新 PDF 的 [!DNL Microsoft Word] 範本。</p> <p>建議在 Workfront 中為您在 Workfront Fusion 中使用的 [!DNL Microsoft Word] 範本建立一個專案。接著，您可以使用「Workfront &gt; [!UICONTROL 下載文件]」模組，將適當的範本提取至情境中。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出格式]</td> 
   <td> <p>選取所產生文件的格式。</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 用於合併的資料]</td> 
   <td> <p>針對範本中您要以文字取代的每個值標記，請填入下列資訊：</p> 
    <ul> 
     <li> <p>[!UICONTROL 索引鍵]</p> <p>請輸入索引鍵。在範本中，索引鍵為值標記中所顯示的文字。例如，若您想要在值標記 <code>&#123;&#123;name&#125;&#125;</code> 中放入文字，請在索引鍵欄位中輸入 <code>name </code>。</p> </li> 
     <li> <p>值類型</p> <p>對於值欄位中的資料，選取其為值、物件或物件陣列。</p> </li> 
     <li> <p>[!UICONTROL 值]</p> <p>輸入或對應您要在所產生的文件中取代值標記顯示的文字。</p> </li> 
    </ul> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/generate-with-template-350x241.png" style="width: 350;height: 241;"> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 搭配 JSON 使用[!UICONTROL 產生文件]模組

若要搭配 JSON 使用[!UICONTROL 產生文件]模組，請依照下列內容填入欄位：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出格式]</td> 
   <td> <p>選取所產生文件的格式。</p> 
    <ul> 
     <li> <p>PDF</p> </li> 
     <li> <p>DOCX</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 用於合併的資料]</td> 
   <td> <p>若要在此模組中使用 JSON，您必須啟用此欄位的對應功能。</p> <p>輸入或對應要從中產生文件的 JSON。 </p> <p>您可以在此欄位中直接輸入 JSON，或對應來自 JSON 模組的 JSON 輸出。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 將 PDF 檔案線性化]

此工具可將 PDF 文件線性化，以便建立針對網頁最佳化的 PDF 文件。線性化的 PDF 文件可以逐頁檢視，而不需要下載整份文件。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 進行自訂的 API 呼叫

此動作模組把向 PDF Services API 發送自訂 HTTP 要求的動作模組化。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> 輸入相對路徑或 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion 自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td> <p>針對您想要新增至 API 呼叫的每個欄位，按一下「<b>新增項目</b>」，然後輸入欄位的索引鍵和選填的值。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>


### [!UICONTROL PDF 檔案的 OCR]

此工具在檔案上執行光學字元辨識 (OCR) 並產生 PDF。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 語言]</td> 
   <td>選取此文件的語言。<p>關於語言選項的資訊，請參閱這篇文章中的<a href="#convert-document-to-pdf-file" class="MCXref xref" >將文件轉換成 PDF 檔案</a>。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL OCR 類型]</td> 
   <td> 
    <ul> 
     <li> <p>[!UICONTROL 已修改原始影像] 類型可確保文字可搜尋且可供選取，但在執行清理程序期間 (例如，進行去歪斜處理) 會修改原始影像，然後在影像上放置隱形的文字圖層。此類型會移除不想要的成品，並在部分情境下可能製作出更容易閱讀的文件。 </p> </li> 
     <li> <p>[!UICONTROL 未變更原始影像] 類型也會在原始影像上覆蓋可搜尋的文字圖層，但在這個情況下，原始影像維持不變。此類型會維持與原始影像最大的保真度。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 頁面操作]

您可以透過這個模組選擇旋轉或刪除 PDF 文件中的頁面。例如，您可以將縱向檢視變更為橫式檢視，或從 PDF 文件中移除某些頁面。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 動作]</td> 
   <td> <p>選取您要對檔案執行的動作。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL 刪除]</b> </p> <p>選取此選項可刪除文件中的頁面。</p><p>對於您要刪除的每個頁面範圍，按一下「<strong>[!UICONTROL 新增]</strong>」，然後輸入頁面範圍的第一頁和最後一頁。 </p> <p>注意：   
     <ul> 
      <li> <p>您可以使用負數從文件結尾往前計算。文件的最後一頁為 -1，倒數第二頁為 -2，依此類推。</p> </li> 
      <li> <p>若要刪除單一頁面，請將範圍的開始和結尾設定為相同的頁碼。</p></ul> </li> 
     <li> <p><b>[!UICONTROL 旋轉]</b> </p> <p>選取此選項來旋轉頁面，然後按照您要讓文件頁面從起始方向依順時針旋轉的角度，輸入其度數。</p> <p>若要從縱向旋轉為橫式或是反之，請將頁面旋轉 90 度或 270 度。</p> <p>如果頁面上下顛倒，請將其旋轉 180 度。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 頁面]</td> 
   <td> <p>對於您要刪除的每個頁面範圍，按一下「<strong>[!UICONTROL 新增]</strong>」，然後輸入頁面範圍的第一頁和最後一頁。 </p> <p>注意：   
     <ul> 
      <li> <p>您可以使用負數從文件結尾往前計算。文件的最後一頁為 -1，倒數第二頁為 -2，依此類推。</p> </li> 
      <li> <p>若要刪除單一頁面，請將範圍的開始和結尾設定為相同的頁碼。</p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中處理的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF 無障礙自動標記]

此動作模組會建立標記為適用於無障礙使用案例的 PDF，也會建立選用的 Microsoft Excel 報告，其中列出相關問題並提供修正建議。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變換標題]</td> 
   <td> <p>啟用此選項可變換文件上的標題。</p> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 產生報告]</td> 
   <td> <p>啟用此選項可產生報告，其中列出 PDF 中的無障礙相關問題及其位置，並提供修正這些問題的建議。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL PDF 檔案屬性]

此工具可擷取關於文件的基本資訊，例如：

* 頁數
* PDF 版本
* 檔案是否已加密
* 檔案是否線性化
* 檔案是否包含嵌入的檔案

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 保護 PDF 檔案]

此工具可透過使用者或所有者密碼保護 PDF 文件的安全，也可以針對 PDF 文件中某些功能 (例如列印、編輯和複製) 設定限制。由您選取要加密的內容類型及加密演算法。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是 PDF 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 密碼保護類型]</td> 
   <td> <p>啟用此選項可使用密碼來加密輸入的 PDF 文件。若啟用此選項，您必須指定並輸入下列其中一項或兩項的值： </p> 
    <ul> 
     <li> <p>[!UICONTROL 使用者密碼]</p> </li> 
     <li> <p>[!UICONTROL 所有者密碼] </p> </li> 
    </ul> <p>每個密碼的長度最多 128 個字元。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 加密演算法]</td> 
   <td> <p>選取加密演算法。 </p> 
    <ul> 
     <li> <p>[!UICONTROL AES-128 加密]</p> <p>密碼僅支援 LATIN-I 字元。 </p> </li> 
     <li> <p>[!UICONTROL AES-256 加密]</p> <p>密碼支援 Unicode 字元集</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 要加密的內容]</td> 
   <td> <p>選取要加密哪種類型的內容。</p> 
    <ul> 
     <li> <p>[!UICONTROL 所有內容]</p> </li> 
     <li> <p>[!UICONTROL 所有內容但後設資料除外]</p> </li> 
     <li> <p>[!UICONTROL 僅限嵌入的資料] </p> </li> 
    </ul> <p>選取「[!UICONTROL 僅限嵌入的資料]」會讓所提供的任何存取權限失效。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 權限]</td> 
   <td> <p>選取您為了允許列印、編輯或內容複製所要包含的任何權限。</p> <p>唯有當「[!UICONTROL 密碼保護類型]」欄位設定為「[!UICONTROL 所有者密碼]」時，才會使用權限設定。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 移除 PDF 檔案的保護]

此工具可移除 PDF 文件中的安全性 (密碼保護)。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" > 建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是 PDF 格式。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 密碼]</td> 
   <td>輸入目前保護檔案的密碼。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 分割 PDF 檔案]

此動作模組可將 PDF 文件分割成多個小文件。您可以指定依照檔案數量、每個檔案的頁數或者頁面範圍進行分割。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取此模組要使用的連線。</p> 關於建立與 [!DNL Adobe PDF Services] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-pdf-services" class="MCXref xref" >建立與 [!DNL Adobe PDF Services]</a> 的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> <p>來源檔案必須是 PDF 格式。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 分割選項]</td> 
   <td>選取分割檔案的方式。 
   <ul>
   <li><p><b>頁面範圍</b></p><p>對於您要分割成個別文件的每個頁面範圍，按一下「<b>新增</b>」，然後輸入開始的頁面和結束的頁面。</p></li>
   <li><p><b>頁數</b></p><p>輸入您要包含在新文件中的頁面數量。</p></li>
   <li><p><b>檔案數量</b></p><p>輸入您要將文件平均分割為大小相同的檔案之數量。</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>


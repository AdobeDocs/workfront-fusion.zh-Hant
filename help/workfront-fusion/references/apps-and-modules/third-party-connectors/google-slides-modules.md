---
title: Google幻燈片模組
description: Adobe Workfront Fusion Google幻燈片模組可讓您建立、更新、列出及/或刪除簡報，並將影像上傳至Google幻燈片帳戶中的簡報。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 6f5f97b9-b06a-4336-b349-ee9e2606d4bf
source-git-commit: c9c2957aad4c885a622a80b9f25303517db0c506
workflow-type: tm+mt
source-wordcount: '1552'
ht-degree: 0%

---

# [!DNL Google Slides]模組

[!DNL Adobe Workfront Fusion] [!DNL Google Slides]模組可讓您建立、更新、列出和/或刪除簡報，並將影像上傳到您[!DNL Google Slides]帳戶中的簡報。

若要搭配[!DNL Workfront Fusion]使用[!DNL Google Slides]，必須有[!DNL Google]帳戶。 如果您還沒有[!DNL Google]帳戶，您可以在[!DNL Google]帳戶說明頁面建立一個帳戶。

您的[!DNL Google Drive]中還需要[!DNL Google Slides]。

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

若要使用[!DNL Google Slides]模組，您必須有[!DNL Google]帳戶。

## Google投影片API資訊

Google幻燈片聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://slides.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.5.9</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Slides]模組及其欄位

當您設定[!DNL Google Slides]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Slides]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [簡報](#presentation)
* [其他](#other)

### 簡報

* [[!UICONTROL Add/Delete a Slide]](#adddelete-a-slide)
* [[!UICONTROL Create a Presentation From a Template]](#create-a-presentation-from-a-template)
* [[!UICONTROL Get a Page/Thumbnail]](#get-a-pagethumbnail)
* [[!UICONTROL Get a Presentation]](#get-a-presentation)
* [[!UICONTROL List Presentations]](#list-presentations)
* [[!UICONTROL Refresh a Chart]](#refresh-a-chart)
* [[!UICONTROL Upload an Image To a Presentation]](#upload-an-image-to-a-presentation)
* [[!UICONTROL Watch Presentations]](#watch-presentations)

#### [!UICONTROL Add/Delete a Slide]

此動作模組會建立投影片或刪除指定簡報上的現有投影片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the method]</td> 
   <td> <p>選擇您要新增幻燈片或刪除幻燈片。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Enter a Slide ID]</td> 
   <td> <p>如果要刪除幻燈片，請選取是要手動輸入幻燈片ID，還是從清單中選取幻燈片。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Presentation ID]</td> 
   <td> <p>選取簡報或對映您要新增或刪除幻燈片的簡報的簡報ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Slide Object ID]</td> 
   <td> <p>如果您要刪除投影片並選擇手動輸入投影片，請輸入或對映投影片ID。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Predefined layout type]</td> 
   <td> <p> 選取您要新增的幻燈片使用的預先定義幻燈片版面配置。 指定任何其他欄位的值（例如[!UICONTROL Title]）。</p> 
    <ul> 
     <li>[!UICONTROL Blank layout, with no placeholders]</li> 
     <li>[!UICONTROL Layout with a caption at the bottom]</li> 
     <li>[!UICONTROL Layout with a title and subtitle]</li> 
     <li>[!UICONTROL Layout with a title and body]</li> 
     <li>[!UICONTROL Layout with a title and two columns]</li> 
     <li>[!UICONTROL Layout with only a title]</li> 
     <li>[!UICONTROL Layout with a section title]</li> 
     <li>[!UICONTROL Layout with a title and subtitle on one side and description on the other]</li> 
     <li>[!UICONTROL Layout with one title and one body, arranged in a single column]</li> 
     <li>[!UICONTROL Layout with a main point]</li> 
     <li>[!DNL Layout with a big number heading]</li> 
    </ul> <p>如果您選取新增幻燈片，則可使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Content]</td> 
   <td> <p>輸入或對映幻燈片的文字內容。 根據您選取的範本，可使用欄位。</p> <p>如果您選取新增幻燈片，則可使用此欄位。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Presentation From a Template]

此動作模組會複製簡報，並以提供的資料取代所有標籤（如`{{Name}}`、`{{Email}}`）來建立新的簡報。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>輸入新簡報的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy a Presentation]</td> 
   <td> <p> 如果要複製現有的簡報，請選取選項：</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy of Existing Presentation ID]</td> 
   <td> <p> 輸入要複製之現有簡報的路徑或簡報ID。 如果您正在建立簡報[!UICONTROL By Mapping]，就會顯示此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>選取您要列出的簡報所在的[!DNL Google Drive]：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] 共用磁碟機]</li> 
    </ul> <p>如果您正在建立簡報[!UICONTROL By Dropdown]，就會顯示此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> 選取簡報，或輸入或對應您要做為範本之簡報的簡報ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values] </td> 
   <td> <p>新增值：</p> 
    <ul> 
     <li><strong>[!UICONTROL Tag]</strong>：在簡報中輸入您要取代的標籤。 例如， <code>&#123;&#123;Name&#125;&#125;</code></li> 
     <li><strong>[!UICONTROL Replaced Value]</strong>：輸入要取代現有標籤的值。 例如，如果簡報中的字串<code>&#123;&#123;Name&#125;&#125;</code>和取代的值是Sample，則<code>&#123;&#123;Name&#125;&#125;</code>會取代為<code>Sample</code>。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Drive Location]</td> 
   <td> <p>選取您要儲存或新增簡報的[!DNL Google Drive]：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] 共用磁碟機]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New Document's Location]</p> </td> 
   <td> <p>選取您要儲存或新增簡報的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared] </td> 
   <td> <p>選取是否要共用簡報。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sharing with Other's Email Address]</td> 
   <td> <p> 輸入您要共用簡報的電子郵件地址。 如果啟用「共用」選項時未在此欄位中輸入電子郵件，則簡報可與任何人共用。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Page/Thumbnail]

此動作模組取得指定頁面或簡報中頁面縮圖的最新版本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Presentation and Page ID]</td> 
   <td> <p> 選擇是否要手動輸入簡報和頁面ID，或從清單中選取它們。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> 選取您要擷取的簡報ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Page Object ID]</td> 
   <td> <p> 選取您要檢視頁面物件詳細資訊的幻燈片。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show Page Thumbnail]</td> 
   <td> <p> 如果您想要檢視頁面縮圖資訊，請選取核取方塊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Presentation]

此動作模組取得指定簡報的最新版本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>選取您要列出的簡報所在的[!DNL Google Drive]：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] 共用磁碟機]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> 選取您要擷取的簡報。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Presentations]

此模組會擷取指定位置的所有簡報清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive location]</td> 
   <td> <p>選取您要列出的簡報所在的[!DNL Google Drive]：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] 共用磁碟機]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p>選擇您要列出之簡報的資料夾位置。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應您希望模組在一個案例執行週期內傳回的最大簡報數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Refresh a Chart]

此動作模組會重新整理儲存在ID所指定簡報中的圖表資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Presentation ID]</td> 
   <td> <p> 選擇是否要手動輸入簡報ID，或從清單中選取它。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>如果從清單中選取簡報，請選取您要列出之簡報所在的[!DNL Google Drive]：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] 共用磁碟機]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>選取簡報，或輸入或對應包含您要重新整理之圖表的簡報ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Chart Object ID]</td> 
   <td> <p> 如果以手動方式輸入資料，請輸入或對應您要重新整理之圖表的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload an Image To a Presentation]

上傳含有所提供資料的影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>選擇您要如何選取要上傳影像的簡報。</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!DNL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>如果從下拉式清單中選擇，請選取您要新增影像的簡報所在的[!DNL Google Drive]：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] 共用磁碟機]</li> 
    </ul>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p> 選取您要上傳影像的目標簡報的簡報ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select the Method]</td> 
   <td> <p> 選取您要取代影像的方式。</p>
   <ul>
   <li><p><b>取代文字標籤以上傳影像</b></p><p>在[值]欄位中，針對每一個要上傳的影像，按一下[新增專案] <b> </b>，然後輸入影像的標籤和新影像的URL。</p></li>
   <li><p><b>取代影像以上傳影像</b></p><p>在[值]欄位中，針對每一個要上傳的影像，按一下[新增專案] <b> </b>，然後輸入影像的物件ID、取代方法以及新影像的URL。</p></li>
   </ul>
  <p>注意：影像大小必須小於50MB、不能超過2500萬畫素，且必須是PNG、JPEG或GIF格式。</p>   </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Presentations]

此觸發模組會在建立或更新新簡報時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch] </td> 
   <td> <p>選取觀看簡報的選項：</p> 
    <ul> 
     <li> <p>[!UICONTROL Created Date]</p> </li> 
     <li> <p>[!UICONTROL Modified Date]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對映Workfront Fusion在一個案例執行週期內應傳回的最大簡報數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [[!UICONTROL Insert Links in a Presentation]](#insert-links-in-a-presentation)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Insert Links in a Presentation]

此模組可讓簡報中的所有連結可點按，或將連結插入所有相符的輸入文字中。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Presentation]</td> 
   <td> <p>選擇您要如何選取要上傳影像的簡報。</p> 
    <ul> 
     <li>[!UICONTROL By Mapping]</li> 
     <li>[!UICONTROL By Dropdown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a drive]</td> 
   <td> <p>選取您要列出的簡報所在的[!DNL Google Drive]：</p> 
    <ul> 
     <li>[!UICONTROL My Drive]</li> 
     <li>[!UICONTROL Shared With Me]</li> 
     <li>[!UICONTROL [!DNL Google] 共用磁碟機]</li> 
    </ul> <p>如果您正在建立簡報[!UICONTROL By Dropdown]，就會顯示此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Presentation ID]</td> 
   <td> <p>選擇您要列出之簡報的資料夾位置。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select]</td> 
   <td> <p>選取您是否要將簡報中的所有連結設為可點按，或者是否要將連結插入所有相符的輸入文字中。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text Inputs]</td> 
   <td>如果您要插入連結，請針對每個要新增連結的文字專案，按一下<b>新增專案</b>，然後輸入文字及其相關連結。 每次專案出現在簡報中時，它都會自動連結到指定的網站。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

執行任意授權的API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Slides]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>輸入相對於<code>https://developers.google.com/slides/</code>的路徑。 例如，簡報。</p> <p>如需可用端點的清單，請參閱<a href="https://developers.google.com/slides/reference/rest">[!DNL Google Slides] API檔案</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>輸入所需的請求標頭。 您不需要新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> 輸入請求查詢字串。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**範例：**&#x200B;您可以使用API呼叫取得您輸入的簡報ID的簡報詳細資料。 當您在[!DNL Google Slides]中開啟簡報時，可以在URL中找到簡報ID。

![API呼叫範例](/help/workfront-fusion/references/apps-and-modules/assets/api-call-350x13.png)

以下API呼叫會傳回簡報詳細資料：

![簡報詳細資料](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details.png)

在[!UICONTROL Bundle] > [!UICONTROL Body] > [!UICONTROL presentationId]下模組的輸出中找到搜尋的相符專案。

在我們的範例中，已傳回要求的簡報詳細資料：

![簡報詳細資料](/help/workfront-fusion/references/apps-and-modules/assets/presentation-details-2.png)

>[!ENDSHADEBOX]

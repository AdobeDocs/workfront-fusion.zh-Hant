---
title: Google檔案模組
description: Adobe Workfront Fusion [!DNL Google Docs] 模組可讓您監視、建立、編輯和擷取 [!DNL Google Docs] 和 [!DNL Google Docs]  （適用於 [!DNL Google Workspace] 位使用者）中的檔案。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: cd44250d-c2cd-46b2-8773-15b30472a8d8
source-git-commit: 5a95b2c191d4e6d8750dc57a47923f416612b4a9
workflow-type: tm+mt
source-wordcount: '3222'
ht-degree: 0%

---

# [!DNL Google Docs]模組

[!DNL Adobe Workfront Fusion] [!DNL Google Docs]模組可讓您監視、建立、編輯和擷取[!DNL Google Docs]和[!DNL Google Docs] （針對[!DNL Google Workspace]位使用者）中的檔案。

若要搭配[!DNL Adobe Workfront Fusion]使用[!DNL Google Docs]，必須有[!DNL Google]帳戶。 如果您還沒有[!DNL Google]帳戶，您可以在[!DNL Google]帳戶說明頁面建立一個帳戶。

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

若要使用[!DNL Google Docs]模組，您必須擁有Google帳戶。

## Google Docs API資訊

Google Docs聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://docs.googleapis.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.4.13</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Docs]模組及其欄位

當您設定[!DNL Google Docs]模組時，[!UICONTROL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Docs]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 文件

* [[!UICONTROL Watch Documents]](#watch-documents)
* [[!UICONTROL List Documents]](#list-documents)
* [[!UICONTROL Get Content of a Document]](#get-content-of-a-document)
* [[!UICONTROL Create a Document]](#create-a-document)
* [[!UICONTROL Create a Document From a Template]](#create-a-document-from-a-template)
* [[!UICONTROL Insert a Paragraph to a Document]](#insert-a-paragraph-to-a-document)
* [[!UICONTROL Insert an Image to a Document]](#insert-an-image-to-a-document)
* [[!UICONTROL Replace an Image with a New Image]](#replace-an-image-with-a-new-image)
* [[!UICONTROL Replace Text in a Document]](#replace-text-in-a-document)
* [[!UICONTROL Download a Document]](#download-a-document)
* [[!UICONTROL Delete a Document]](#delete-a-document)

#### [!UICONTROL Watch Documents]

在選取的資料夾中建立或修改新檔案時，此觸發模組會傳回檔案詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Documents]</td> 
   <td> <p style="color: #000000;">選取您要觀看已建立的([!UICONTROL By Created Date])或已修改的([!UICONTROL By Modified Date])檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要監視的磁碟機型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取要監視已建立或已修改檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取要監視已建立或已修改檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要觀看的共用磁碟機。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Shared Drive]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>設定Workfront Fusion在一個執行週期中傳回的最大檔案數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Documents]

此動作模組會從選取的資料夾擷取檔案清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要列出檔案的磁碟機型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要列出檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要列出檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取要列出檔案的共用磁碟機。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>設定在一個執行週期內傳回的最大檔案數[!DNL Workfront Fusion]。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Content of a Document]

此動作模組會擷取指定的檔案。

您可能需要擴充許可權。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Get Content of a Document]</td> 
   <td> <p>選取是否要對應檔案的檔案ID，或從下拉式選單中手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取包含您要擷取之檔案的磁碟機型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取包含您要擷取之檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取包含您要擷取之檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取包含您要擷取之檔案的共用磁碟機。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Filter]</p> </td> 
   <td> <p>選取您要在模組輸出中傳回的物件。</p> 
    <ul> 
     <li>[!UICONTROL Image] (預設)</li> 
     <li>[!UICONTROL Drawing]</li> 
     <li>[!UICONTROL Chart]</li> 
    </ul> <p>注意：  <p>若要進一步對應這些物件，請在此模組的輸出中使用[!UICONTROL Inline Objects Array]值（而非[!UICONTROL inlineObjects]）。</p> <p>[!UICONTROL Inline Objects Array]物件會以它們在檔案中的顯示順序排序。 如此一來，任何進一步處理作業都會更輕鬆。</p> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document]

此動作模組可讓您在選取的資料夾中建立新檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入檔案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Content]</td> 
   <td> <p>輸入檔案的內容。 支援HTML。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要建立檔案的磁碟機型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要建立檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要建立檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要建立檔案的共用磁碟機。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Header]</td> 
   <td> <p> 啟用此選項可將頁首插入檔案，然後輸入或對應頁首的文字。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Insert a Footer] </td> 
   <td> <p>啟用此選項可將頁尾插入檔案，然後輸入或對映頁首的文字。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Document From a Template]

此動作模組會建立現有範本檔案的復本，並取代任何標籤。 此模組也允許使用者透過URL將影像更換為新影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Create a Document from a Template]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>選取此選項以對應檔案範本。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br>選取此選項，從下拉式選單中選擇檔案範本。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取範本所在的磁碟機型別。 如果您在上一個欄位中選取[!UICONTROL By Dropdown]，則此選項可供使用。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取範本所在的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取範本所在的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取範本所在的共用磁碟機。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>輸入將輸入的值，而不是新檔案的變數。</p> 
    <ul> 
     <li><strong>[!UICONTROL Tags]</strong> <br>輸入包含在檔案範本中的標籤。 請勿使用<code>&#123;&#123;&#125;&#125;</code>。 範例：使用<code>name</code>而非<code>&#123;&#123;name&#125;&#125;</code>。</li> 
     <li><strong>[!UICONTROL Replaced Value]</strong><br>輸入標籤的值。</li> 
    </ul> <p>例如，來原始檔中的<code> &#123;&#123;name&#125;&#125;</code>變數將顯示為此處的name欄位，可插入值，例如<code>John</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Images Replacement]</p> </td> 
   <td> <p>輸入將取代目前影像的[!UICONTROL Image Object ID]和[!UICONTROL Image URL]連結。</p> <p>注意：您可以使用[!UICONTROL Get a Document]模組來擷取影像ID，其中ID包含在陣列[!UICONTROL Inline Object Array]中。</p> <p>建議您將ALT文字新增至[!DNL Google]檔案中的影像。 </p> <p>若要將ALT文字新增至[!DNL Google Docs]影像：</p> 
    <ol> 
     <li value="1">在影像上按一下右鍵。</li> 
     <li value="2">選取[!UICONTROL ALT text]選項。</li> 
     <li value="3">在[!UICONTROL Title]欄位中輸入[!UICONTROL ALT text]並按一下[!UICONTROL OK]。</li> 
    </ol> <p>將ALT文字加入影像後，ALT文字會顯示在括弧內的欄位名稱中。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Title] </td> 
   <td> <p>輸入新檔案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取範本所在的磁碟機型別。 如果您在上一個欄位中選取[!UICONTROL By Dropdown]，則此選項可供使用。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要建立檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要建立檔案的資料夾。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要建立檔案的共用磁碟機。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert a Paragraph to a Document]

此動作模組會將新段落附加或插入現有檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>選取此選項以對應檔案。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> 選取此選項，從下拉式選單中選擇檔案。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要新增段落的檔案所在位置的磁碟機型別。 如果您在上一個欄位中選取[!UICONTROL By Dropdown]，則此選項可供使用。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要新增段落的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要新增段落的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要新增段落的檔案所在的共用磁碟機，然後選取檔案。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert a Paragraph]</p> </td> 
   <td> <p>選取您要將新文字插入檔案中的方式。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>輸入要插入文字的索引編號。 您可以使用[!UICONTROL Get a Document]模組擷取索引號碼。</p> <p>若要顯示檔案中的所有字元（包括隱藏字元），您可以使用[!UICONTROL Show]附加元件。 您可以在[!UICONTROL Add-ons] &gt; [!UICONTROL Get add-ons]下找到附加元件。 搜尋[!UICONTROL Show]並安裝[!UICONTROL Show]附加元件。</p> </li> 
         <li> <p><strong>[!UICONTROL Inserted text]</strong> </p> <p>輸入要插入檔案的文字。</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>選取您要插入文字內容的頁首與頁尾，並輸入要插入至對應欄位的文字。</p> <p>如果頁首或頁尾已包含文字，則新文字會新增到現有文字之前。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>在檔案內文內容的結尾附加輸入的文字。</p> <p>新段落的樣式將從目前插入索引處的段落複製，包括清單和專案符號。</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>選取您要插入文字內容的頁首與頁尾，並輸入要插入至對應欄位的文字。</p> <p>如果頁首或頁尾已包含文字，則新文字會新增至現有文字之後。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Appended Text]</td> 
   <td>輸入或對應您要附加至檔案的文字</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Insert an Image to a Document]

此動作模組會將URL中的影像插入檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>選取此選項以對應檔案範本。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> 選取此選項，從下拉式選單中選擇檔案。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要新增影像的檔案所在的磁碟機型別。 如果您在上一個欄位中選取[!UICONTROL By Dropdown]，則此選項可供使用。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要新增影像的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要新增影像的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要新增影像的檔案所在的共用磁碟機，然後選取檔案。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Insert an Image]</p> </td> 
   <td> <p>選取您要將新影像插入檔案中的方式。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By specification of location]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL By index]</strong> </p> 
        <ul> 
         <li> <p><strong>[!UICONTROL Index]</strong> </p> <p>輸入要插入影像的索引編號。 您可以使用[!UICONTROL Get a Document]模組擷取[!UICONTROL Index number]。</p> <p>若要顯示檔案中的所有字元（包括隱藏字元），您可以使用[!UICONTROL Show]附加元件。 您可以在[!UICONTROL Add-ons] &gt; [!UICONTROL Get add-ons]下找到附加元件。 搜尋[!UICONTROL Show]並安裝[!UICONTROL Show]附加元件。</p> </li> 
         <li> <p><strong>[!UICONTROL Image URL]</strong> </p> <p>輸入要插入檔案的影像URL。</p> <p>影像大小上限為50 MB。 不得超過2500萬畫素。 僅支援PNG、JPEG或GIF格式。</p> </li> 
        </ul> </li> 
       <li> <p><strong>[!UICONTROL By segment ID]</strong> </p> <p>選取您要插入影像的頁首與頁尾，並將影像URL輸入至對應的欄位。</p> <p>影像大小上限為50 MB。 影像不得超過2500萬畫素。 僅支援PNG、JPEG或GIF格式。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL By appending to the body of the document]</strong> </p> <p>在檔案內文內容的結尾附加特定影像。</p> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL By appending to the end of segment (Header and Footer)]</strong> </p> <p>選取您要插入影像的頁首與頁尾，並輸入要插入至對應欄位的影像URL。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Height Magnitude in Points/Width Magnitude in Points]</p> </td> 
   <td> <p>定義插入影像的大小。 將會保持長寬比。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace an Image with a New Image]

此動作模組會取代現有影像。 將會維持原始影像的外觀比例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>選取此選項以對應檔案範本。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> 選取此選項，從下拉式選單中選擇檔案。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要取代影像之檔案所在的磁碟機型別。 如果您在上一個欄位中選取[!UICONTROL By Dropdown]，則此選項可供使用。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要取代影像的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要取代影像的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要取代影像之檔案所在的共用磁碟機，然後選取檔案。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Image URL]</p> </td> 
   <td> <p>輸入或對映將取代現有影像之新影像的URL。</p> <p>影像會以它們在檔案中的顯示順序列出。 例如，<code>Body: Image No. 1</code>是檔案中的第一個影像。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace Text in a Document]

此動作模組會取代檔案中的文字。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Select a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>選取此選項以對應檔案範本。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> 選取此選項，從下拉式選單中選擇檔案。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要新增文字的檔案所在的磁碟機型別。 如果您在上一個欄位中選取[!UICONTROL By Dropdown]，則此選項可供使用。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要新增文字的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要新增文字的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要新增文字的檔案所在的共用磁碟機，然後選取檔案。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Replace a Text]</p> </td> 
   <td> <p>新增您想要取代的每一個文字。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Old text to be replaced]</strong> </p> <p>輸入要取代的文字。</p> </li> 
     <li> <p><strong>[!UICONTROL New text to be inserted]</strong> </p> <p>輸入新文字。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a Document]

此動作模組會轉換及下載選取的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要下載的檔案所在的磁碟機型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要下載的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要下載的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要下載的檔案所在的共用磁碟機，然後選取檔案。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Type] </p> </td> 
   <td> <p>選取已下載檔案的目標檔案格式。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Document]

此動作模組會刪除檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您要刪除的檔案所在的磁碟機型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您要刪除的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您要刪除的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您要刪除的檔案所在的共用磁碟機，然後選取檔案。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>選取包含您要下載之檔案的磁碟機，然後選取檔案。 如果您已在[!UICONTROL Choose a Drive]欄位中選取[!DNL Google Docs]，則此選項可供使用。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> 選取或對映您要取代一或多個影像的檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Make All Links in a Document Clickable]](#make-all-links-in-a-document-clickable)

#### [!UICONTROL Make an API Call]

此動作模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>輸入相對於<code>https://docs.googleapis.com/</code>的路徑。 範例： <code>/v1/documents/{presentationID}</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 例如，<code>{"Content-type":"application/json"}</code>。 [!DNL Workfront Fusion]為您新增授權標頭。</p> </td> 
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

**範例：**&#x200B;下列API呼叫會擷取Google Docs中指定檔案的詳細資料：

**URL：**

/v1/documents/1ujkf-GDgB0TQSYPrxbCSK4Uso54tHVMqHZEVZZxB6aY

**方法：**

[!UICONTROL GET]

![API呼叫範例](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

在[!UICONTROL Bundle] > [!UICONTROL Body]下的模組輸出中可找到擷取檔案的詳細資料。

![API呼叫輸出](/help/workfront-fusion/references/apps-and-modules/assets/api-output.png)

#### [!UICONTROL Make All Links in a Document Clickable]

此動作模組會尋找檔案中的所有連結，並讓這些連結可供點按。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Make All Links in a Document]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL By Mapping]</strong> <br>選取此選項以對應檔案範本。</li> 
     <li><strong>[!UICONTROL By Dropdown]</strong> <br> 選取此選項，從下拉式選單中選擇檔案。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose a Drive]</td> 
   <td> <p>選取您想讓連結可點選的檔案所在的磁碟機型別。 如果您在上一個欄位中選取[!UICONTROL By Dropdown]，則此選項可供使用。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL My Drive]</strong> </p> <p>選取您想讓連結可點選的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL Shared With Me]</strong> </p> <p>選取您想讓連結可點選的檔案所在的資料夾，然後選取檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL [!DNL Google]共用磁碟機]</strong> （僅適用於[!DNL Google Workspace]位使用者）</p> <p>選取是否要[!UICONTROL Use Domain Admin Access]。 選取[!UICONTROL Yes]會以網域管理員身分發出請求，並且會傳回請求者身為管理員的所有共用磁碟機。</p> <p>選取您想讓連結可點選的檔案所在的共用磁碟機，然後選取檔案。</p> <p>注意：如果您已在此欄位中選取[!DNL Google Docs]選項，而且您不是[!DNL Google Workspace]使用者，則會傳回錯誤<code>[400] Invalid Value</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Shared Drive]</td> 
   <td> <p>選取包含您要更新連結之檔案的磁碟機，然後選取檔案。 如果您已在[!UICONTROL Choose a Drive field]中選取[!DNL Google Docs]，則此選項可供使用。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Document ID]</td> 
   <td> <p> 選取或對應您要更新連結的檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

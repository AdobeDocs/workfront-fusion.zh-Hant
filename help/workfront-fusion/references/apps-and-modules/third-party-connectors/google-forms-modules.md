---
title: Google Forms模組
description: ' [!DNL Adobe Workfront Fusion Google Forms] 模組可讓您監視、選取、新增、更新或刪除Google Forms上的回應。'
author: Becky
feature: Workfront Fusion
exl-id: dc017957-c0f8-4206-916f-21ccda346fb9
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 0%

---

# [!DNL Google Forms]模組

[!DNL Adobe Workfront Fusion] [!DNL Google Forms]模組可讓您監視、選取、新增、更新或刪除您的[!DNL Google Forms]回應。

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

若要使用[!DNL Google Forms]模組，您必須有[!DNL Google]帳戶。

## Google Forms API資訊

Google Forms聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>2.0.10</td> 
  </tr>
 </tbody> 
 </table>

## 從表單建立試算表

若要使用您的表單回應，必須建立回應的試算表。

1. 開啟您的表單。
1. 前往&#x200B;**[!UICONTROL Responses]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL Create Spreadsheet]**&#x200B;圖示![試算表圖示](/help/workfront-fusion/references/apps-and-modules/assets/spreadsheet-icon.png)。

1. 選取您要建立新的試算表或現有的試算表
1. 按一下&#x200B;**[!UICONTROL Create]**。

## [!DNL Google Forms]模組及其欄位

當您設定[!DNL Google Forms]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Forms]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

#### [!UICONTROL Watch Responses]

監視表單以取得新回應。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>選取試算表，其中包含您要監視新回應的表單回應。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> 選取包含表單回應的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Row with headers]</td> 
   <td>指定表格的標頭列。 預設列為<code>A1:Z1</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Value Render Option]</td> 
   <td> <p>指定要在輸出中呈現值的方式。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Formatted value]</strong> </p> <p>系統會根據儲存格的格式，在回覆中計算值並設定格式。 格式設定是以試算表的地區設定為基礎，而非請求使用者的地區設定。 例如，如果<code>A1</code>是<code>1. 23</code>，<code>A2 </code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>$1. 23</code>。</p> </li> 
     <li> <p><strong>[!UICONTROL Unformatted value]</strong> </p> <p>系統會計算值，但不會在回覆中設定格式。 例如，如果<code>A1</code>是<code>1. 23</code>，<code>A2 </code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回數字<code>1. 23</code> 。</p> </li> 
     <li> <p><strong>[!UICONTROL Formula]</strong> </p> <p>不會計算值。 回覆包含公式。 例如，如果<code>A1</code>是<code>1. 23</code>，<code>A2 </code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>=A1</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Date and time render option]</td> 
   <td>選取要在輸出中呈現的日期、時間和持續時間。 如果[!UICONTROL Value Render Option]設定為[!UICONTROL Formatted Value]，則會忽略此欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p> 設定[!DNL Workfront Fusion]在一個週期內處理的最大回應數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL Add a Response]](#add-a-response)
* [[!UICONTROL Update a Response]](#update-a-response)
* [[!UICONTROL Delete a Response]](#delete-a-response)

#### [!UICONTROL Add a Response]

此模組會將新回應附加至表單試算表底部。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>選取包含您要新增回應之工作表的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> 選取包含表單回應的工作表。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>在工作表欄中輸入所需的值。</p> <p>對於正確格式的[!UICONTROL Timestamp]資料行，請使用下列值：</p><pre>formatDate（現在；DD/MM/YYYY HH：mm；UTC）</pre> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> 使用者輸入的值不會剖析並依原樣儲存。 </p> </li> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>這些值會剖析為使用者在UI中輸入。 數字仍為數字，但字串可能會根據透過[!DNL Google Sheets] UI在儲存格中輸入文字時所套用的相同規則，轉換為數字、日期或其他格式。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Insert data option]</td> 
   <td> <p>指定輸入新資料時如何變更現有資料。 </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Overwrite]</strong> </p> <p>新資料會覆寫其寫入區域中的現有資料。 將資料加入工作表結尾會插入新的列或欄，以便寫入資料。</p> </li> 
     <li> <p><strong>[!UICONTROL Insert rows]</strong></p> <p>會為新資料插入列。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Response]

此模組會更新選取的回應。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>選取包含您要更新回應的工作表試算表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> 選取包含表單回應的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Row number]</p> </td> 
   <td> <p>輸入或對應您要更新的資料列編號。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Values]</p> </td> 
   <td> <p>在所需欄中輸入新值。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value input option]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> 使用者輸入的值不會剖析並依原樣儲存。 </p> </li> 
     <li> <p><strong>[!UICONTROL User entered]</strong></p> <p>這些值會剖析為使用者在UI中輸入。 數字仍為數字，但字串可能會根據透過[!DNL Google Sheets] UI在儲存格中輸入文字時所套用的相同規則，轉換為數字、日期或其他格式。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Response]

此模組會刪除選取的回應。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet]</td> 
   <td> <p>選取包含您要刪除回應之工作表的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sheet]</td> 
   <td> <p> 選取包含表單回應的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Row number]</p> </td> 
   <td> <p>輸入或對應您要刪除的列編號。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL Search Responses]](#search-responses)
* [[!UICONTROL Search Responses (Advanced])](#search-responses-advanced)

#### [!UICONTROL Search Responses]

此模組會傳回符合指定條件的回應。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
    <td>連接</td>
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Spreadsheet]</td>
   <td> <p>選取您要搜尋的表單。</p> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Sheet] </td>
   <td> <p>選取包含表單回應的工作表。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Column range]</td>
   <td> <p> 選取您要搜尋的欄範圍。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>定義您要搜尋回應依據的篩選器。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Sort Order] </td>
   <td> <p>選取要以遞增或遞減順序來排序傳回的回應。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
    <td>[!UICONTROL Order By]</td>
   <td> <p> 選取要排序傳回回回回應的資料行。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Value Render Option]</td> 
   <td> <p>指定要在輸出中呈現值的方式。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Formatted value]</strong></p> <p>系統會根據儲存格的格式，在回覆中計算值並設定格式。 格式設定是以試算表的地區設定為基礎，而非請求使用者的地區設定。 例如，如果<code>A1</code>是<code>1. 23</code>，<code>A2 </code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>$1. 23</code>。</p> </li> 
     <li> <p><strong>[!UICONTROL Unformatted value]</strong> </p> <p>系統會計算值，但不會在回覆中設定格式。 例如，如果<code>A1</code>是<code>1. 23</code>，<code>A2 </code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回數字<code>1. 23</code> 。</p> </li> 
     <li> <p><strong>[!UICONTROL Formula]</strong> </p> <p>不會計算值。 回覆包含公式。 例如，如果<code>A1</code>是<code>1. 23</code>，<code>A2 </code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>=A1</code>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr data-mc-conditions="">
    <td>[!UICONTROL Date and time render option]</td>
    <td>選取要在輸出中呈現的日期、時間和持續時間。 如果[!UICONTROL Value Render]選項設定為格式化值，則會忽略此欄位。 </td>
  </tr> 
  <tr>
    <td role="rowheader">[!UICONTROL Maximum number of returned responses]</td>
   <td> <p> 設定[!DNL Workfront Fusion]在一個週期內傳回的回應數上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Responses (Advanced)]

此模組使用[[!DNL Google Charts Query Language]](https://developers.google.com/chart/interactive/docs/querylanguage)執行搜尋。 此模組未傳回列號。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Google]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Spreadsheet]</td>
   <td> <p>選取包含您要搜尋之工作表的試算表。</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Sheet]</td>
   <td> <p> 選取包含表單回應的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>使用<a href="https://developers.google.com/chart/interactive/docs/querylanguage">[!DNL Google Charts Query Language]</a>定義搜尋查詢。</p> <p>範例： <code>select * where C = "John"</code>會擷取C欄為"John"的資料列的所有值。</p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL Maximum number of returned rows]</td>
   <td> <p> 設定[!DNL Workfront Fusion]在一個週期內傳回的回應數上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

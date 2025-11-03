---
title: Google工作表模組
description: 若要搭配Adobe Workfront Fusion使用 [!DNL Google Sheets] ，您需要[!UICONTROL Workfront Fusion Google Sheets]擴充功能（選用，但即時觸發程式必須使用）。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 80965570-2937-4ac8-97c0-54f7a813ec50
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '4046'
ht-degree: 0%

---

# [!DNL Google Sheets]模組

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Google Sheets]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱[建立與Adobe Workfront Fusion的連線 — 基本說明](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權</td> 
   <td>
   <p>作業型：無Workfront Fusion授權需求</p>
   <p>以聯結器為基礎（舊版）：用於工作自動化和整合的Workfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!UICONTROL Google工作表]模組，您必須有[!UICONTROL Google]帳戶。

## Google Sheets API資訊

Google Sheets聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://sheets.googleapis.com/v4</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v4 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v2.5.7</td> 
  </tr>
 </tbody> 
 </table>

## Google工作表模組及其欄位

當您設定[!DNL Google Forms]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Sheets]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 觸發程序

#### [!UICONTROL 觀看列]

從試算表中新新增的列擷取值。

模組只會擷取先前未填入的新列。 觸發器不會處理覆寫的列。

>[!IMPORTANT]
>
>如果工作表包含空白列，則不會處理空白列之後的任何列。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取包含您要觀看之表格的試算表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作表] </td> 
   <td> <p>選取要監視新列的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 表格包含標題]</td> 
   <td> <p> 選取試算表是否包含標題列。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 是]</strong> </p> <p>模組不會將標題列擷取為輸出資料。 </p> <p>輸出中的變數名稱由標題呼叫。</p> </li> 
     <li> <p><strong>[!UICONTROL 號碼]</strong> </p> <p>模組也會擷取第一個表格列</p> <p>輸出中的變數名稱稱為A、B、C、D等等。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 含標題列] </td> 
   <td> <p>輸入頁首列的範圍。 例如 <code>A1:F1</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 第一個表格列]</td> 
   <td> <p>輸入表格第一列的範圍。 例如 <code>A1:F1</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 值演算選項]</p> </td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL 格式值]</p> <p>系統會根據儲存格的格式，在回覆中計算值並設定格式。 格式設定是以試算表的地區設定為基礎，而非請求使用者的地區設定。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"$1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 未格式化的值]</p> <p>系統會計算值，但不會在回覆中設定格式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回數字<code>"1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 公式]</p> <p>不會計算值。 回覆包含公式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"=A1"</code>。</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 日期和時間轉譯選項]</p> </td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL 序號]</p> <p>日期、時間、日期時間和持續時間欄位會以「序號」格式輸出為兩倍，並由Lotus 1-2-3普及。 值的整數部分（小數點左側）計算自1899年12月30日以來的天數。 小數部分（小數點右側）會將時間計為一天中的小數。 例如，1900年1月1日中午是2.5、2，因為是在1899年12月30日之後的2天，而。5，因為中午是半天。 1900年2月1日下午3點會是33.625。這正確將1900年視為閏年。</p> </li><li><p style="font-weight: bold;">[!UICONTROL 格式字串]</p> <p>日期、時間、日期時間和持續時間欄位會以其指定的數字格式（視試算表的地區設定而定）輸出為字串。</p></li><ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>設定Workfront Fusion在一個執行週期內處理的結果數量上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 新增列]](#add-a-row)
* [[!UICONTROL 新增工作表]](#add-a-sheet)
* [[!UICONTROL 清除儲存格]](#clear-a-cell)
* [[!UICONTROL 清除列]](#clear-a-row)
* [[!UICONTROL 建立試算表]](#create-a-spreadsheet)
* [[!UICONTROL 刪除列]](#delete-a-row)
* [[!UICONTROL 刪除工作表]](#delete-a-sheet)
* [[!UICONTROL 取得儲存格]](#get-a-cell)
* [[!UICONTROL 進行API呼叫]](#make-an-api-call)
* [[!UICONTROL 更新儲存格]](#update-a-cell)
* [[!UICONTROL 更新列]](#update-a-row)

#### [!UICONTROL 新增列]

此模組會附加一列至工作表。

當您設定[!DNL Google Sheets]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Sheets]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 模式]</td> 
   <td> <p>選取您要手動選取試算表與工作表，還是透過對應。</p> <p>注意：例如在Workfront Fusion案例中建立新的試算表，而您想要直接在案例中新增資料到新建立的試算表時，手動對應就相當實用。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取要新增列的頁面。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 欄範圍]</td> 
   <td>選取您要使用的欄範圍。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 表格包含標題]</td> 
   <td> <p> 選取試算表是否包含標題列。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 是]</strong> </p> <p>模組不會將標題列擷取為輸出資料。 </p> <p>輸出中的變數名稱由標題呼叫。</p> </li> 
     <li> <p><strong>[!UICONTROL 號碼]</strong> </p> <p>模組也會擷取第一個表格列</p> <p>輸出中的變數名稱稱為A、B、C、D等等。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值] </td> 
   <td> <p>在要新增的資料列中，輸入或對應所需的儲存格。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值輸入選項]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL 使用者已進入]</strong></p> <p>這些值會剖析為使用者在UI中輸入。 數字仍為數字，但字串可能會根據透過[!DNL Google Sheets] UI在儲存格中輸入文字時所套用的相同規則，轉換為數字、日期或其他格式。</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> 使用者輸入的值不會剖析並儲存為輸入值。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 插入資料選項]</td> 
   <td> <p>指定輸入新資料時如何變更現有資料。 </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 插入列]</strong></p> <p>會為新資料插入列。</p> </li> 
     <li> <p><strong>[!UICONTROL 覆寫]</strong> </p> <p>新資料會覆寫其寫入區域中的現有資料。 將資料加入工作表結尾會插入新的列或欄，以便寫入資料。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 新增工作表]

在選取的試算表中建立新工作表。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取您要新增工作表的Google試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 屬性]</td> 
   <td> 
    <ul> 
     <li> <p style="font-weight: bold;">[!UICONTROL 標題]</p> <p>輸入新頁面的名稱。</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL Index]</p> <p>輸入頁面位置。 預設值為0 （將頁面放在第一位）。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清除儲存格]

刪除指定儲存格的值。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取包含您要清除儲存格之工作表的Google試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取您要清除儲存格的頁面。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 儲存格] </td> 
   <td> <p>輸入或對應您要清除的儲存格識別碼。 範例：<code>A5</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清除列]

從指定的列刪除值。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取包含您要清除資料列之工作表的[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p> 選取您要清除其資料的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列號]</td> 
   <td> <p>輸入您要清除資料的資料列編號。 範例：<code> 23</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立試算表]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 標題] </td> 
   <td> <p>輸入新試算表的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Locale]</td> 
   <td> <p>以下列格式之一輸入試算表的地區設定：</p> 
    <ul> 
     <li>ISO 639-1語言代碼，例如 <code>en</code></li> 
     <li>ISO 639-2語言代碼，例如<code>haw</code> （如果沒有639-1代碼）</li> 
     <li>ISO語言代碼和國家/地區代碼的組合，例如 <code>en_US</code></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 重新計算間隔]</td> 
   <td> <p>重新計算易失性函式之前要等待的時間量：</p> <ul><li><p style="font-weight: bold;">[!UICONTROL 變更時]</p> <p>每次變更時，都會更新易失性函式。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 開啟變更且每分鐘]</p> <p>易失性函式會在每一次變更和每分鐘更新一次。</p></li> <li><p style="font-weight: bold;">[!UICONTROL 變更時每小時]</p> <p>揮發性函式會在每次變更時每小時更新。</p></li></ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 時區]</td> 
   <td> <p> 選取試算表的時區。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 數字格式]</td> 
   <td> <p>選取試算表中所有儲存格的預設格式。</p> <p><strong>[!UICONTROL 文字]</strong>：文字格式設定。 範例： <code>1000. 12</code></p> <p><strong>[!UICONTROL Number]</strong>：數字格式。 範例： <code>1,000.12</code></p> <p><strong>[!UICONTROL Percent]</strong>：百分比格式。 範例： <code>10. 12%</code></p> <p><strong>[!UICONTROL 貨幣]</strong>：貨幣格式。 範例： <code>$1,000.12</code></p> <p><strong>[!UICONTROL 日期]</strong>：日期格式。 範例： <code>9/26/2008</code></p> <p><strong>[!UICONTROL 時間]</strong>：時間格式。 範例： <code>3:59:00 PM</code></p> <p><strong>[!UICONTROL 日期時間]</strong>：日期與時間格式。 範例：<code>9/26/08 15:59:00</code> </p> <p><strong>[!UICONTROL Scientific]</strong>：科學數字格式。 範例： <code>1. 01E+03</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>針對您要新增至試算表的每個工作表，按一下<strong>[!UICONTROL 新增專案]</strong>，然後輸入或對應工作表的標題與工作表的索引。 0的索引代表第一個工作表。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除列]

刪除指定的列。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取包含您要刪除列之工作表的Google試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>表 </td> 
   <td> <p>選取您要從中刪除資料列的頁面。</p> </td> 
  </tr> 
  <tr> 
   <td>列號</td> 
   <td> <p>輸入要刪除的列數。 範例： <code>23</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除工作表]

刪除特定工作表。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取您要刪除的頁面。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得儲存格]

從選取的儲存格擷取值。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取包含您要擷取資料之儲存格的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 儲存格] </td> 
   <td> <p>輸入您要擷取資料的儲存格識別碼。 範例： <code>A6</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值演算選項]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL 格式值]</p> <p>系統會根據儲存格的格式，在回覆中計算值並設定格式。 格式設定是以試算表的地區設定為基礎，而非請求使用者的地區設定。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"$1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 未格式化的值]</p> <p>系統會計算值，但不會在回覆中設定格式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回數字<code>"1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 公式]</p> <p>不會計算值。 回覆包含公式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"=A1"</code>。</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!DNL Date and time render option]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!DNL Serial number]</p> <p>日期、時間、日期時間和持續時間欄位會以「序號」格式輸出為兩倍，並由Lotus 1-2-3普及。 值的整數部分（小數點左側）計算自1899年12月30日以來的天數。 小數部分（小數點右側）會將時間計為一天中的小數。 例如，1900年1月1日中午是2.5、2，因為是在1899年12月30日之後的2天，而。5，因為中午是半天。 1900年2月1日下午3點會是33.625。這正確將1900年視為閏年。</p></li><li> <p style="font-weight: bold;">[!DNL Formatted string]</p> <p>日期、時間、日期時間和持續時間欄位會以其指定的數字格式（視試算表的地區設定而定）輸出為字串。</p> </li><ul></td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行API呼叫]

此動作模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Google Sheets帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td>輸入相對於<code>https://sheets.googleapis.com/v4/</code>的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 例如 <code>{"Content-type":"application/json"}</code>。Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p> 以標準JSON物件的形式新增API呼叫的查詢。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：   <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新儲存格]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取要更新儲存格的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 儲存格] </td> 
   <td> <p>輸入要更新的儲存格識別碼。 範例： <code>A5</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值]</td> 
   <td> <p>輸入儲存格的新值。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值輸入選項]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL 使用者已進入]</strong></p> <p>這些值會剖析為使用者在UI中輸入。 數字仍為數字，但字串可能會根據透過[!DNL Google Sheets] UI在儲存格中輸入文字時所套用的相同規則，轉換為數字、日期或其他格式。</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> 使用者輸入的值不會剖析並儲存為輸入值。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新列]

此模組可讓您變更所選列中的儲存格內容。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 模式]</td> 
   <td> <p>選取您要手動選取試算表與工作表，還是透過對應。</p> <p>注意：例如在[!UICONTROL Workfront Fusion]情境中建立新試算表時，而您想要直接在情境中新增資料至新建立的試算表時，手動對應就相當實用。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取要更新資料列的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列號]</td> 
   <td> <p> 輸入您要更新的資料列編號。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 表格包含標題]</td> 
   <td> <p> 選取試算表是否包含標題列。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 是]</strong> </p> <p>模組不會將標題列擷取為輸出資料。 </p> <p>輸出中的變數名稱由標題呼叫。</p> </li> 
     <li> <p><strong>[!UICONTROL 號碼]</strong> </p> <p>模組也會擷取第一個表格列</p> <p>輸出中的變數名稱稱為A、B、C、D等等。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值] </td> 
   <td> <p>輸入值或將值對應至要變更（更新）之列的所需儲存格。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值輸入選項]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL 使用者已進入]</strong></p> <p>這些值會剖析為使用者在UI中輸入。 數字仍為數字，但字串可能會根據透過[!DNL Google Sheets] UI在儲存格中輸入文字時所套用的相同規則，轉換為數字、日期或其他格式。</p> </li> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p> 使用者輸入的值不會剖析並儲存為輸入值。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL 取得範圍值]](#get-range-values)
* [[!UICONTROL 清單工作表]](#list-sheets)
* [[!UICONTROL 搜尋列]](#search-rows)
* [[!UICONTROL 搜尋列（進階）]](#search-rows-advanced)

#### [!UICONTROL 取得範圍值]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取您要取得範圍內容的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 範圍] </td> 
   <td> <p>輸入您要取得的範圍。 範例：<code>A1:D25</code>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 表格包含標題]</td> 
   <td> <p>如果工作表有標題列，請核取此方塊</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 含標題列]</td> 
   <td>輸入表格標題的範圍。 範例<code>A1:F1</code>。 如果讓欄位保持空白，Workfront Fusion會將指定範圍的第一列視為標頭。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值演算選項]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL 格式值]</p> <p>系統會根據儲存格的格式，在回覆中計算值並設定格式。 格式設定是以試算表的地區設定為基礎，而非請求使用者的地區設定。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"$1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 未格式化的值]</p> <p>系統會計算值，但不會在回覆中設定格式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回數字<code>"1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 公式]</p> <p>不會計算值。 回覆包含公式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"=A1"</code>。</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 日期和時間轉譯選項]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL 序號]</p> <p>日期、時間、日期時間和持續時間欄位會以「序號」格式輸出為兩倍，並由Lotus 1-2-3普及。 值的整數部分（小數點左側）計算自1899年12月30日以來的天數。 小數部分（小數點右側）會將時間計為一天中的小數。 例如，1900年1月1日中午是2.5、2，因為是在1899年12月30日之後的2天，而。5，因為中午是半天。 1900年2月1日下午3點會是33.625。這正確將1900年視為閏年。</p> </li><li><p style="font-weight: bold;">[!UICONTROL 格式字串]</p> <p>日期、時間、日期時間和持續時間欄位會以其指定的數字格式（視試算表的地區設定而定）輸出為字串。</p></li><ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清單工作表]

此模組會傳回試算表中所有工作表的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取包含您要列出工作表的[!DNL Google]試算表。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋列]

使用篩選選項來搜尋列。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將Google Sheets帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取[!DNL Google]試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取要搜尋資料列的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 表格包含標題]</td> 
   <td> <p> 選取試算表是否包含標題列。 如果選取[!UICONTROL 是]選項，模組不會擷取標題列做為輸出資料，而輸出中的變數名稱隨後由標題呼叫。 如果選取了[!UICONTROL 否]選項，模組也會擷取第一個表格列，然後輸出中的變數名稱就只稱為A、B、C、D等。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 欄範圍]</td> 
   <td>選取要使用的欄範圍。 範例： <code>A-F</code></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 篩選器]</td> 
   <td> <p>設定您要用來搜尋列的篩選器。</p> <!--<p>For more information about filters, see <a href="/help/workfront-fusion/create-scenarios/add-modules/" class="MCXref xref">Add a filter to a scenario in [!UICONTROL Adobe Workfront Fusion]</a>.</p>--> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 排序順序]</td> 
   <td>選取您要遞增排序還是遞減排序。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Order by]</td> 
   <td>選擇您要作為排序依據的欄。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 值演算選項]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL 格式值]</p> <p>系統會根據儲存格的格式，在回覆中計算值並設定格式。 格式設定是以試算表的地區設定為基礎，而非請求使用者的地區設定。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"$1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 未格式化的值]</p> <p>系統會計算值，但不會在回覆中設定格式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回數字<code>"1.23"</code>。</p></li><li> <p style="font-weight: bold;">[!UICONTROL 公式]</p> <p>不會計算值。 回覆包含公式。 例如，如果<code>A1</code>是<code>1.23</code>，<code>A2</code>是<code>=A1</code>且已格式化為貨幣，則<code>A2</code>會傳回<code>"=A1"</code>。</p> </li><ul></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 日期和時間轉譯選項]</td> 
   <td> <ul><li><p style="font-weight: bold;">[!UICONTROL 序號]</p> <p>日期、時間、日期時間和持續時間欄位會以「序號」格式輸出為兩倍，並由Lotus 1-2-3普及。 值的整數部分（小數點左側）計算自1899年12月30日以來的天數。 小數部分（小數點右側）會將時間計為一天中的小數。 例如，1900年1月1日中午是2.5、2，因為是在1899年12月30日之後的2天，而。5，因為中午是半天。 1900年2月1日下午3點會是33.625。這正確將1900年視為閏年。</p> </li><li><p style="font-weight: bold;">[!UICONTROL 格式字串]</p> <p>日期、時間、日期時間和持續時間欄位會以其指定的數字格式（視試算表的地區設定而定）輸出為字串。</p></li><ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 傳回資料列數目上限]</td> 
   <td>設定Workfront Fusion在一個執行週期內傳回的最大列數。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋列（進階）]

傳回符合指定准則的結果。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Sheets]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Spreadsheet] </td> 
   <td> <p>選取包含您要搜尋之工作表的Google試算表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 工作表] </td> 
   <td> <p>選取包含要搜尋之資料列的工作表。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query]</td> 
   <td> <p>使用[!DNL Google Charts Query Language]。 範例： <code>select * where B = "John"</code></p> <p>如需[!DNL Google Charts Query Language]的詳細資訊，請參閱<a href="https://developers.google.com/chart/interactive/docs/querylanguage">檔案中的</a>查詢語言參考[!DNL Google]。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用量限制

如果發生錯誤`429: RESOURCE_EXHAUSTED`，表示您已超過API速率限制。

[!DNL Google Sheets] API限制每個專案每100秒500個要求，每個使用者每100秒100個要求。 讀取和寫入限制會個別追蹤。 沒有每日使用量限制。

如需詳細資訊，請參閱[developers.google.com/sheets/api/limits](https://developers.google.com/sheets/api/limits)。

## 提示與秘訣

* [從 [!DNL Google] 工作表取得空白儲存格](#get-empty-cells-from-a-google-sheet)
* [在工作表中新增按鈕以執行案例](#add-a-button-in-a-sheet-to-run-a-scenario)

### 從[!DNL Google Sheet]取得空白儲存格

若要取得空白儲存格，您可以使用[!UICONTROL 搜尋列（進階）]模組。 使用此公式來取得空白欄。

```
select * where E is null
```

其中，「E」為欄，而「is null」為條件。 您可以使用Google查詢語言建立更進階的查詢。 如需詳細資訊，請參閱Google檔案中的[Google Query Lang](https://developers.google.com/chart/interactive/docs/querylanguage)。

### 在工作表中新增按鈕以執行案例

1. 在Workfront Fusion中，在情境中插入&#x200B;**[!UICONTROL Webhook]** > **[!UICONTROL 自訂Webhook]**&#x200B;模組並加以設定。 如需指示，請參閱[Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)。

1. 複製webhook的URL。
1. 執行情境。
1. 在Google工作表中，從主功能表列選擇&#x200B;**[!UICONTROL 插入]** > **[!UICONTROL 繪圖]**...。

1. 在[!UICONTROL 繪圖]視窗中，按一下視窗頂端附近的&#x200B;**[!UICONTROL 文字方塊]**&#x200B;圖示![文字方塊](/help/workfront-fusion/references/apps-and-modules/assets/text-box.png)。
1. 設計按鈕並按一下右上角的&#x200B;**[!UICONTROL 儲存並關閉]**&#x200B;按鈕：
1. 此按鈕會放置在您的工作表中。 按一下按鈕右上角的三個垂直點：
1. 選擇&#x200B;**[!UICONTROL 指派指令碼……]。功能表中的**。
1. 輸入指令碼（函式）的名稱，例如`runScenario`，然後按一下&#x200B;**[!UICONTROL 確定]**：
1. 從主功能表列選擇&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL 指令碼編輯器]**。

1. 插入下列程式碼：

   * 函式的名稱必須對應到您在步驟9中指定的名稱。
   * 將URL取代為您在步驟2中複製的webhook URL。

     ```
     function runScenario() {
     UrlFetchApp.fetch("&lt;webhook you copied>");
     }
     ```

1. 按&#x200B;**[!UICONTROL Ctrl+S]**&#x200B;儲存指令碼檔案，輸入專案名稱並按一下&#x200B;**[!UICONTROL 確定]**。

1. 切換回[!DNL Google Sheets]並按一下您的新按鈕。
1. 將所需的授權授與指令碼：
1. 在Workfront Fusion中，確認案例已成功執行。

## 將日期儲存在試算表中

如果您將「日期」值儲存在試算表中沒有任何格式，該值會在試算表中顯示為ISO 8601格式的文字。 但是，使用日期的[!DNL Google Sheets]公式或函式無法理解此文字（範例：公式`=A1+10`）會顯示下列錯誤：

![錯誤](/help/workfront-fusion/references/apps-and-modules/assets/mceclip6-350x87.png)

為協助讓[!DNL Google Sheets]瞭解日期，請使用`formatDate`函式將其格式化。 傳遞給函式做為第二個引數的正確格式，取決於試算表的地區設定。

如需有關這個函式的詳細資訊，請參閱文章日期和時間函式中的[[!UICONTROL formatDate] (date； format； [timezone])](/help/workfront-fusion/references/mapping-panel/functions/date-and-time-functions.md#formatdate-date-format-timezone)。

若要判斷正確的格式：

1. 在Google Sheets中，從主功能表選擇&#x200B;**[!UICONTROL 檔案]** > **[!UICONTROL 試算表]**&#x200B;設定，以驗證和設定地區設定。

1. 在驗證或設定正確的地區設定後，請從主功能表中選擇&#x200B;**[!UICONTROL 格式]** > **[!UICONTROL 數字]**&#x200B;來決定對應的日期和時間格式。 格式會顯示在日期時間功能表專案旁：

1. 若要撰寫應傳遞至[!UICONTROL formatDate()]函式的正確格式，請參閱[Token清單中的日期和時間格式](/help/workfront-fusion/references/mapping-panel/functions/tokens-for-date-and-time-formatting.md)。

>[!BEGINSHADEBOX]

**範例：**

對於`MM/DD/YYYY HH:mm:ss`格式（美國地區設定）：

![地區設定時間公式](/help/workfront-fusion/references/apps-and-modules/assets/locale-time-350x83.png)

>[!ENDSHADEBOX]

## 正在利用[!DNL Google Sheets]功能

若要使用Google Sheets的內建函式，您可以加以利用。 如需詳細資訊，請參閱文章中的[使用 [!DNL Google Sheets] 函式](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md#use-google-sheets-functions)使用函式對應專案。

## 防止[!DNL Google Sheets]將數字變更為日期

如果您用來作為文字的數字字串被解譯為[!DNL Google]工作表中的日期，您可以將數字預先格式化為純文字以防止此情況。 例如，如果您輸入1-2019，打算將它當作文字，Google可能會將其解譯為日期。

1. 在[!DNL Google Sheets]中，反白顯示包含數字的欄或儲存格。
1. 按一下&#x200B;**[!UICONTROL 格式]** > **[!UICONTROL 數字]** > **[!UICONTROL 純文字]**。

Workfront Fusion的另一個因應措施是在數字前輸入撇號(&#39;)，例如，&#39;1-2019或&#39;1/47。 從Workfront Fusion傳送資料後，儲存格中不會顯示單引號。

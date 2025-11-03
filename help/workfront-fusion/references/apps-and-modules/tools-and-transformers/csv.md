---
title: CSV
description: Adobe Workfront Fusion CSV模組可讓您建立CSV檔案，以及從收到的文字值或檔案剖析CSV文字。
author: Becky
feature: Workfront Fusion
exl-id: bc6d5ddc-93c3-437b-8537-5bece1351c1d
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 0%

---

# CSV

Adobe Workfront Fusion [!UICONTROL CSV]模組可讓您建立CSV檔案，並從收到的文字值或檔案剖析CSV文字。

因為這是轉換器，這些模組不需要連線。

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
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

+++



## [!UICONTROL 建立CSV]

[!UICONTROL 建立CSV]彙總器可讓您從收到的文字值建立CSV文字。

如需彙總器的詳細資訊，請參閱[彙總器模組](/help/workfront-fusion/references/modules/aggregator-module.md)。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Source模組]</td>
        <td>選取輸出您要用來建立CSV之欄位的模組。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 彙總欄位]</td>
        <td>從可用欄位清單中選取您要彙總的欄位。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Include headers in the first row]</td>
        <td>選取此選項以在結果中包含標題。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Group by]</td>
        <td>輸入篩選條件以將結果分組。 例如，輸入日期。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 在空白彙總後停止處理]</td>
        <td>選取此選項可在沒有結果時停止情境。</td>
    </tr>
</table>

## [!UICONTROL 建立CSV （進階）]

[!UICONTROL 建立CSV （進階）]彙總器可讓您從收到的文字值建立CSV文字。 它採用一種資料結構，定義所產生CSV檔案中的CSV欄。 定義後，欄會顯示為CSV模組設定中的欄位，並可對應至案例中稍後的模組。

如需彙總器的詳細資訊，請參閱[彙總器模組](/help/workfront-fusion/references/modules/aggregator-module.md)。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source模組]</td> 
        <td>選取輸出您要用來建立CSV之欄位的模組。</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料結構]</td> 
   <td> <p>選取資料結構，以您想要的方式彙總欄位。 定義資料結構後，您可以將專案對應至對應的欄位。</p> <p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">資料結構</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include headers in the first row] </td> 
   <td>選取此選項以在結果中包含標題。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by] </td> 
   <td>輸入篩選條件以將結果分組。 例如，輸入日期。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 在空白彙總後停止處理] </td> 
   <td>選取此選項可在沒有結果時停止情境。 </td> 
  </tr> 
 </tbody> 
</table>


>[!BEGINSHADEBOX]

**範例**：

此範例說明如何將Google連絡人匯出至CSV檔案，其包含名為「全名」和「電子郵件」的兩欄。 來自[!UICONTROL Google連絡人] > [!UICONTROL 從群組]模組取得連絡人的輸出組合具有以下結構。 電子郵件地址儲存在<code>[!UICONTROL 電子郵件[]]中</code> 專案，是一個集合陣列，每個集合包含兩個專案： <code>標籤</code> 和<code>電子郵件</code>.
![正在轉換](/help/workfront-fusion/references/apps-and-modules/assets/transforming-350x546.png)

簡單[!DNL Create CSV]模組提供對應至套件組合最上層專案的核取方塊清單。 如果您嘗試選取<code>全名</code> 和<code>封電子郵件</code> 專案，[!UICONTROL 建立CSV]模組會產生以下輸出，可能不是您想要的：

```
"emails","fullName"
"[object Object]","Shon Winer"
"[object Object]","Lizeth Fulmore"
"[object Object]","Hilario Gullatt"
"[object Object]","Abby Eisenbarth"
```

因為專案<code>全名</code> 屬於簡單型別Text，會如預期匯出。 專案<code>電子郵件</code>屬於複雜型別Array of Collections的匯出為[物件物件]，這是將Collections和Arrays預設轉換為文字的方式。

如需詳細資訊，請參閱[專案資料型別](/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md)。


匯出<code>電子郵件的內容 </code><code>電子郵件[]之第一個集合的專案</code> 陣列取代，您必須使用[!UICONTROL 建立CSV （進階）]模組。 此模組可讓您定義CSV檔案的個別欄，並將專案對應至這些欄，包括巢狀欄。

1. 在情境中插入模組[!UICONTROL 建立CSV （進階）]。
1. 按一下<strong>[!UICONTROL 資料結構]</strong>欄位旁的[!UICONTROL 新增]按鈕，以建立新的資料結構。
1. 輸入資料結構的名稱，然後按一下<strong>[!UICONTROL 新增專案]</strong>以新增個別欄。 若要匯出兩欄：「全名」和「電子郵件」，產生的「資料」結構如下所示：

   ![Google連絡人輸出](/help/workfront-fusion/references/apps-and-modules/assets/google-contacts-350x524.png)

1. 在您定義資料結構後，對應至每個個別欄的欄位會顯示在[!UICONTROL 建立CSV （進階）]模組的組態中，以便您對應專案。 從<code>[!UICONTROL 電子郵件[]]取得第一個專案</code> 陣列並對應其專案<code>電子郵件 </code>至欄位/欄電子郵件：

   ![建立CSV進階模組](/help/workfront-fusion/references/apps-and-modules/assets/create-csv-advanced-350x308.png)

1. 執行情境。 因為專案<code>電子郵件[1]：電子郵件</code> 對應到欄「電子郵件」為簡單型別文字，可正確匯出。

```
"Full Name","Email"
"Shon Winer","Shon@Winer.com"
"Lizeth Fulmore","Lizeth@Fulmore.com"
"Hilario Gullatt","Hilario@Gullatt.com"
"Abby Eisenbarth","Abby@Eisenbarth.com"
```

>[!ENDSHADEBOX]

## [!UICONTROL 剖析CSV]

[!UICONTROL 剖析CSV]轉換器可讓您從收到的文字值或檔案剖析CSV文字。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄數]</td> 
   <td>指定CSV檔案中的欄數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV包含標題]</td> 
   <td> <p>如果CSV文字的第一列包含標題，請選取此選項。</p> <p>注意：模組不會使用這些標頭來標示輸出中的欄。 相反，此欄位可確保輸出資料中不包含標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL delimiterType]</td> 
   <td> <p>選取CSV檔案的分隔符號。 分隔字元是指示個別值或欄位之間界限的文字字元。</p> 
    <ul> 
     <li>[!UICONTROL 逗號]</li> 
     <li>[!UICONTROL 索引標籤]</li> 
     <li> <p>[!UICONTROL 其他]</p> <p>如果您選取[!UICONTROL 其他]，請輸入CSV檔案用來分隔值的分隔字元。 您只能輸入一個字元。<br></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 保留無引號欄位內的引號]</td> 
   <td>啟用此選項以保留引號。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL CSV]</td> 
   <td>輸入或對應您要剖析的CSV檔案。<p>注意： <p>如果您的資料為二進位格式（通常來自檔案），您必須使用'toString()'函式將二進位資料轉換為[!UICONTROL String]：</p><p><img src="/help/workfront-fusion/references/apps-and-modules/assets/parse-csv-350x123.png"></p></p></td> 
  </tr> 
 </tbody> 
</table>

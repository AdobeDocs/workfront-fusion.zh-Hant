---
title: JSON 模組
description: Adobe Workfront Fusion JSON應用程式提供可處理JSON格式資料的模組，讓Adobe Workfront Fusion能夠進一步處理資料內容，或建立新的JSON內容。
author: Becky
feature: Workfront Fusion
exl-id: f8b281c5-bb63-4412-98c5-d82f45f8eafc
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 0%

---

# [!UICONTROL JSON]模組

[!DNL Adobe Workfront Fusion] [!UICONTROL JSON]應用程式提供模組以處理JSON格式的資料，讓[!DNL Adobe Workfront Fusion]可以進一步處理資料內容，或建立新的JSON內容。

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

## 解析JSON時的注意事項

* [資料結構](#data-structure)
* [集合與陣列](#collection-vs-array)

### 資料結構

資料結構說明JSON資料的整理方式，並可讓您將個別JSON專案對應至情境中的其他模組。 如果您未提供資料結構，您可以手動執行模組，而[!DNL Workfront Fusion]將會從提供的JSON建置結構：

1. 將[!UICONTROL Parse JSON]模組新增至情境。
1. 在&#x200B;**[!UICONTROL JSON String]**&#x200B;欄位中，輸入您要建置資料結構的JSON。
1. 尚未將其他模組連線至[!UICONTROL Parse JSON]模組。 由於[!DNL Workfront Fusion]尚不瞭解JSON資料的結構，因此尚無法將[!UICONTROL Parse JSON]模組的資料對應到情境中的其他模組。
1. 手動執行情境。 這可讓[!UICONTROL Parse JSON]模組從您提供的JSON中識別JSON結構。
1. 您現在可以連線下列模組。 剖析JSON模組中的專案現在可用於對應。

如需詳細資訊，請參閱[!UICONTROL Adobe Workfront Fusion]](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md)中的[資料結構。

### 集合與陣列

如果JSON字串欄位包含集合`{ ... }`，則輸出是包含集合專案的單一組合。

>[!BEGINSHADEBOX]

**範例：**

```
{
    "name" : "Peter",

    "ID" : 1>}
```


![JSON集合](/help/workfront-fusion/references/apps-and-modules/assets/json-collection.png)

>[!ENDSHADEBOX]

如果JSON字串欄位包含陣列`[ ... ]`，則輸出是一系列組合。 每個組合都包含陣列的一個元素。

>[!BEGINSHADEBOX]

**範例：**

```
[
  {
    "name" : "Peter",
    "ID" : 1
  },

  {
    "name" : "Mike",
    "ID" : 2
  }
]
```

![JSON陣列](/help/workfront-fusion/references/apps-and-modules/assets/json-array.png)

>[!ENDSHADEBOX]

## [!UICONTROL JSON]模組及其欄位

當您設定[!DNL JSON]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除此之外，可能會顯示其他JSON欄位，實際取決於您應用程式或服務中的存取層級等因素。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [將JSON轉換為XML](#convert-json-to-xml)
* [剖析JSON](#parse-json)
* [建立JSON](#create-json)
* [轉換JSON](#transform-json)

### 彙總

#### [!UICONTROL Aggregate to JSON]

此彙總模組會將先前模組的輸出彙總至JSON。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source module] </td> 
   <td> <p>選取輸出您要彙總至JSON之資料的模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>選取您要用來建立JSON的資料結構。 資料結構會決定此模組中有哪些其他欄位可用。 如需詳細資訊，請參閱本文中的<a href="#data-structure" class="MCXref xref">資料結構</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Indentation]</td> 
   <td> <p> 選取您要使用定位字元、兩個空格或四個空格縮排JSON。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by]</td> 
   <td>定義要將彙總輸出分組依據的運算式。 此運算式可包含一或多個對應專案。 接著，會使用此運算式的值，將彙總資料分隔成群組。 每個群組會輸出一個單獨的組合，內含索引鍵（運算式）和值（彙總文字）。 您可以在後續模組中使用該索引鍵作為篩選條件。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>啟用此選項可在沒有結果時停止情境。</td> 
  </tr> 
 </tbody> 
</table>

### 轉換器

* [將JSON轉換為XML](#convert-json-to-xml)
* [建立JSON](#create-json)
* [剖析JSON](#parse-json)
* [轉換JSON](#transform-json)

#### [!UICONTROL Convert JSON to XML]

此動作模組會將JSON字串轉換為XML。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>輸入或對應您要轉換成XML的JSON。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create JSON]

此動作模組會從資料結構建立JSON。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">資料結構</td> 
   <td> <p>選取您要用來建立JSON的資料結構。 如需詳細資訊，請參閱本文中的<a href="#data-structure" class="MCXref xref">資料結構</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">縮排</td> 
   <td> <p>選取您要用於此JSON的縮排。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Parse JSON]

此動作模組會將JSON字串剖析為資料結構，好讓您存取JSON字串內的資料。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data structure]</td> 
   <td> <p>選取您要用來建立JSON的資料結構。 如需詳細資訊，請參閱本文中的<a href="#data-structure" class="MCXref xref">資料結構</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL JSON string] </td> 
   <td> <p>輸入或對應您要剖析的JSON。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Transform JSON]

此動作模組會將物件轉換為JSON字串。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">縮排</td> 
   <td> <p>選取您要用於此JSON的縮排。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object]</td> 
   <td> <p>輸入或對應您要轉換為JSON的物件。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 將資料記錄轉換為JSON

>[!BEGINSHADEBOX]

**範例：**&#x200B;下列範例說明如何將資料記錄從[!DNL Google Sheets]轉換為JSON格式：

1. 將[!DNL Google Sheets] > [!UICONTROL Select rows]模組放置在情境中，以擷取資料。 設定模組以從[!DNL Google]試算表中擷取列。 將&#x200B;**[!UICONTROL Maximum number of returned rows]**&#x200B;設定為較小的數字，但為了測試目的而設定為大於一個數字（例如，3）。 執行[!DNL Google Sheets]模組，方法是按一下滑鼠右鍵並選擇&#39;&#39;**[!UICONTROL Run this module only]**&#39;&#39;。 驗證模組的輸出。

1. 在[!DNL Google Sheets]模組之後連線[!UICONTROL Array Aggregator]模組。 在模組的設定中，選擇&#x200B;**[!UICONTROL Source node]**&#x200B;欄位中的[!DNL Google Sheets]模組。 讓其他欄位維持目前的狀態。

1. 在[!UICONTROL Array Aggregator]模組之後連線[!UICONTROL JSON] > [!UICONTROL Create JSON]模組。 模組的設定需要說明JSON格式的資料結構。 按一下&#x200B;**[!UICONTROL Add]**&#x200B;以開啟資料結構設定。 建立此資料結構的最簡單方法是，自動從JSON範例產生此資料結構。 按一下「**[!UICONTROL Generator]**」並將您的JSON範例貼到「**[!UICONTROL Sample data]**」欄位：

   **範例：**

   ```
   {
   "books": [
   {
   "id": "ID",
   "title": "Title",
   "author": "Author"
   }
   ]
   }
   ```

1. 按一下&#x200B;**[!UICONTROL Save]**。 資料結構中的[!UICONTROL Specification]欄位現在包含產生的結構。
1. 將您的資料結構名稱變更為更具體的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。 對應至根陣列屬性的欄位會顯示為JSON模組設定中的可對應欄位。

1. 按一下欄位旁的&#x200B;**[!UICONTROL Map]**&#x200B;按鈕，並將陣列彙總器輸出中的`Array[]`專案對應至該欄位。

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以關閉[!UICONTROL JSON]模組的設定。

1. 開啟[!UICONTROL Array Aggregator]模組的設定。 將&#x200B;**[!UICONTROL Target structure]**&#x200B;從[!UICONTROL Custom]變更為與根陣列屬性對應的[!UICONTROL JSON]模組欄位。 將來自[!DNL Google Sheets]模組的專案對應到適當的欄位。

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以關閉[!UICONTROL Array Aggregator]模組的設定。

1. 執行情境。

   [!UICONTROL JSON]模組輸出正確的JSON格式。

1. 開啟[!DNL Google Sheets]模組的設定，並將[!UICONTROL Maximum number of returned rows]數字增加到大於試算表中的列數，以處理所有資料。

>[!ENDSHADEBOX]

## 疑難排解

### 無法對應來自[!UICONTROL Parse JSON]模組的資料

請確定JSON內容已正確對應至[!UICONTROL Parse JSON]模組，而且資料結構已正確定義。 如需詳細資訊，請參閱本文中的[將資料記錄轉換為JSON](#transforming-data-records-to-json)。

### 在JSON中使用條件陳述式時，模組失敗

在JSON中使用條件陳述式（例如`if`）時，請將引號放在條件陳述式之外。

>[!BEGINSHADEBOX]

**範例：**

JSON中的![引號](/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png)

>[!ENDSHADEBOX]

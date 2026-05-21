---
title: JSONata 模組
description: Adobe Workfront Fusion JSONata聯結器提供處理JSON格式資料的模組，讓Adobe Workfront Fusion可以進一步處理資料內容。
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
TQID: https://experienceleague.adobe.com/luvZBccaWY5-8muR71o8C82qVROYJvcuAqt3Ol2LZac
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 28%

---

# [!UICONTROL JSONata]模組

Adobe Workfront Fusion [!UICONTROL JSONata]聯結器可讓您查詢JSON物件。 此模組不需要連線。

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
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++



## JSONata模組及其欄位

### 評估

此動作模組會查詢JSON物件並傳回陣列。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL運算式]</td> 
   <td>輸入您要用來評估JSON物件的運算式。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料] </td> 
   <td> 輸入要評估的JSON物件。  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL字串輸出] </td> 
   <td> 啟用此選項可將輸出轉換為字串。  </td> 
  </tr> 
  </tbody>
  </table>

>[!BEGINSHADEBOX]

**範例**:

目標是從以下JSON物件傳回名稱陣列：

```JSON
{
  "people": [
    { "name": "Alice", "age": 30 },
    { "name": "Bob", "age": 25 },
    { "name": "Charlie", "age": 35 }
  ]
}
```

1. 在運算式欄位中，輸入`people.name`。
1. 在資料欄位中，輸入JSON物件。

模組會傳回從JSON物件中拉取的名稱陣列。

>[!ENDSHADEBOX]



### JSONata MCP

此動作模組會通過分析指定的輸入和輸出結構描述來產生JSONata運算式。 您可以提供結構描述，模型內容通訊協定(MCP)會使用它來產生將輸入轉換為輸出的運算式。




<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>選取您用來連線到要用於此模組的大型語言模型(LLM)的連線。</p> <p>目前僅支援人類API金鑰。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入結構描述]</td> 
   <td> <p>輸入或對應要用於此運算式的輸入結構描述。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸出結構描述]</td> 
   <td> <p>輸入或對應要用於此運算式的輸出結構描述。</p> </td> 
  </tr> 
 </tbody> 
</table>

---
title: JSONata模組
description: Adobe Workfront Fusion JSONata聯結器提供處理JSON格式資料的模組，讓Adobe Workfront Fusion可以進一步處理資料內容。
author: Becky
feature: Workfront Fusion
exl-id: 8c117ecb-3c05-47d4-a629-18dbc546e2a2
source-git-commit: da3bf98f8254228598372fed8c06d6318718721f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# [!UICONTROL JSONata]模組

[!DNL Adobe Workfront Fusion] [!UICONTROL JSONata]聯結器可讓您查詢JSON物件。 此模組不需要連線。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 封裝</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權</td> 
   <td> <p>新增：[！UICONTROL Standard]</p><p>或</p><p>目前： [！UICONTROL Work]或更高版本</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>[！UICONTROL Select]或[！UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>已包含[！UICONTROL Ultimate] [!DNL Workfront]計畫： [!DNL Workfront Fusion]。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

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

**範例**：

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
   <td role="rowheader">[！UICONTROL Connection]</td> 
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

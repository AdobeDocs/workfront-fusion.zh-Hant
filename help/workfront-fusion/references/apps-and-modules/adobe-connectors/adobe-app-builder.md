---
title: Adobe App Builder模組
description: Adobe App Builder聯結器可讓您在情境中使用自訂函式。
author: Becky
feature: Workfront Fusion
source-git-commit: 8250d4fdad8ed7ffe63cd003f6e0cb325cbbfa8d
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 31%

---

# Adobe App Builder模組

您可以在Fusion的「函式」區域中建立自訂函式。 然後，以Adobe App Builder模組的形式，將這些函式新增到您的情境中。

由於自訂函式可透過Adobe App Builder運作，因此您的組織必須擁有Adobe App Builder授權才能使用它們。

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
   <p><ul><li>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li><li>您必須擁有Adobe App Builder授權才能使用自訂函式。</ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## Adobe App Builder模組

目前唯一可用的Adobe App Builder模組是執行動作，可讓您使用先前設定的自訂JavaScript函式。

如需設定自訂函式的指示，請參閱[使用自訂函式對應資料](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md)。

### 執行動作

此模組會執行先前設定的自訂函式。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td>
   <td>選取包含您要執行之自訂函式的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 動作]</td> 
   <td>選取您要執行的自訂函式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 引數] </td> 
   <td>輸入函式引數的值。 可用的引數是根據建立函式時設定的引數。<p>如果引數有預設值，您不會在欄位中看到它，但可以透過在欄位中輸入或對應值來覆寫它。</p></td> 
  </tr> 
   </tbody> 
</table>



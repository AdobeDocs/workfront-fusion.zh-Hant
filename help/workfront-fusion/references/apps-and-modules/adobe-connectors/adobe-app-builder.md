---
title: Adobe App Builder模組
description: Adobe App Builder聯結器可讓您在情境中使用自訂函式。
author: Becky
feature: Workfront Fusion
exl-id: 92661a0c-436b-4fbd-808a-a4fbe3cd2339
source-git-commit: 042f32f35e630ec76a7356fa750f5238f74a6f25
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 23%

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

<!--

### Run a custom code block

This module allows you to run a code block. You configure the code block when you set up the module, and it is run when the module runs during a scenario execution.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>Select the connection that contains the custom function that you want to run. </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Code block]</td> 
   <td>Enter the block of code that you want the module to run.<p>To format the code for easier reading, click the <b>Format code</b> icon.</td> 
  </tr> 
   </tbody> 
</table>

-->

### 從封裝執行自訂函式

此模組會從套件執行函式。

<!--For information on packages, see []().-->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td>
   <td>選取包含您要執行之自訂函式的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 套件]</td> 
   <td>選取包含您要在此案例中執行之函式的套件。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變數] </td> 
   <td>選取您要在該案例中執行的函式。</p></td> 
  </tr> 
   </tbody> 
</table>

### 使用封裝中的變數

此模組會將套件中設定的變數帶入您的情境。

<!--For information on packages, see []().-->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td>
   <td>選取包含您要執行之自訂函式的連線。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 套件]</td> 
   <td>選取包含您要納入情境之變數的套件。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變數] </td> 
   <td>選取您要納入情境的變數。</p></td> 
  </tr> 
   </tbody> 
</table>

### 執行自訂函式或程式碼區塊

此模組可讓您使用儲存在函式區域中之先前設定的自訂JavaScript函式。

如需設定自訂函式的指示，請參閱[使用自訂函式對應資料](/help/workfront-fusion/create-scenarios/map-data/map-using-custom-functions.md)。

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

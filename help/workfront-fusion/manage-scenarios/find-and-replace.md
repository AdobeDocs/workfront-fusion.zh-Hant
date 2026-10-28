---
title: 尋找和取代情境中的變數、來源和連線
description: 使用「尋找和取代」來取代對應的變數、將參照從一個來源模組重新對應到另一個來源模組，或複製與案例中其他模組的連線。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
source-git-commit: 94449f8511d7480f1a4fc0ac6e8db9b067977abd
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 15%
---

# 尋找和取代情境中的變數、來源和連線

>[!NOTE]
>
>此功能僅在新的案例編輯器體驗中可用。 如需詳細資訊，請參閱文章「情境編輯器」中的[新體驗和傳統體驗](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)。

「尋找和取代」可讓您一次對多個模組進行相同的變更。 您可以：

* 在整個案例或一個模組中取代對應變數。
* 將參考從一個來源模組重新對應到另一個來源模組。
* 將連線從相同應用程式複製到一或所有相容的模組。

在進行變更之前，「尋找和取代」會顯示將受影響的模組預覽。

在傳統體驗中，您可以使用DevTool中的「交換變數」、「重新對應來源」和「交換連線」工具來執行這些工作。 如需詳細資訊，請參閱[偵錯案例](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md)。

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 開啟「尋找並取代」

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要變更的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下[控制項]區域中的&#x200B;**尋找及取代**&#x200B;圖示![尋找及取代](assets/find-replace-icon.png)。

   您可能需要按一下「控制項」區域中的三個點圖示，才能檢視「尋找和取代」圖示。

尋找和取代會在畫布右側的面板中開啟。

## 取代變數

使用&#x200B;**變數**&#x200B;索引標籤來取代對應的變數。

1. 開啟[尋找和取代]，然後按一下[變數]。****&#x200B;標籤。
1. 在要尋找的變數欄位中，貼入您要取代的變數。
1. 在取代為欄位中，貼入將取代先前變數的變數。
1. 在「模組」欄位中，選擇將套用變更的模組，或選取&#x200B;**整個案例**&#x200B;將變更套用至案例中所有受影響的模組。
1. 按一下&#x200B;**取代**
1. 檢閱將受影響的模組預覽。 若要移至畫布上的模組，請在預覽中選取其列。
1. 按一下「**套用**」。

## 重新對應來源

使用&#x200B;**Source**&#x200B;標籤來變更其他模組中的對應參照的模組。

1. 開啟「尋找和取代」，然後按一下「**Source**」標籤。
1. 在Source模組欄位中，選取對應目前參照的來源模組。
1. 在Target模組欄位中，選取應改用的模組。
1. 在「模組」欄位中，選擇將套用變更的模組，或選取&#x200B;**整個案例**&#x200B;將變更套用至案例中所有受影響的模組。
1. 按一下&#x200B;**取代**
1. 檢閱將受影響的模組預覽。 若要移至畫布上的模組，請在預覽中選取其列。
1. 按一下「**套用**」。

## 將連線複製到其他模組

使用「**連線**」標籤，在相同應用程式的多個模組中使用相同的連線。

1. 開啟[尋找和取代]，然後按一下[連線]。****&#x200B;索引標籤。
1. 在「連線來源」欄位中，選取目前具有您要用於其他模組之連線的模組。
1. 在「套用至」欄位中，選擇將套用變更的模組，或選擇是否將變更套用至案例中所有相容的模組。
1. 按一下「**套用**」。

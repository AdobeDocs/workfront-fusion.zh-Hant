---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 使用函式在基本情境中更新專案
description: 瞭解如何新增函式以更新Workfront中的工作專案。
author: Becky
feature: Workfront Fusion
exl-id: aa082ac8-48e8-4569-880e-024dd77feaa1
source-git-commit: 88147d0305595e1d0d388f510ed43fc5beaa4b64
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 18%

---

# 使用函式在基本情境中更新專案

更新Workfront工作專案是Workfront Fusion的常見使用案例。 在此範例中，您將使用函式將專案名稱變更為大寫字母。

Fusion包含許多型別的函式，可讓您轉換資料並執行條件式邏輯。 如需使用函式的詳細資訊，請參閱[函式概述](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md)。

此範例修改在[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中建立的案例。

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

## 先決條件

在執行此程式之前，您必須先建立[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中所述的案例。

## 使用函式更新專案

### 將更新記錄模組新增至您的情境

1. 在案例編輯器中開啟案例。
1. 將滑鼠停留在第二個模組右邊的部分圓圈上，然後按一下[新增其他模組] ****。
1. 從應用程式清單中選取Adobe Workfront，然後選擇模組&#x200B;**[!UICONTROL 更新記錄]**。
1. 在ID欄位中，選取「轉換物件模組」下的ID區塊。 這是該模組輸出的專案ID。

   來自轉換物件的![ID](assets/id-convert-object.png)

1. 在「記錄型別」欄位中，選取「專案」，因為要更新的物件是專案。
1. 在「選擇要對應的欄位」區域中，選取「名稱」。

   將會開啟「名稱」欄位。
1. 繼續[對應名稱更新](#map-the-function-for-the-name-update)的函式。

### 對應函式以進行名稱更新

當此案例將請求轉換為專案時，專案名稱與請求相同。 此處的函式會採用該名稱並將其中的所有字母大寫。

1. 按一下&#x200B;**名稱**&#x200B;欄位。

   對應面板隨即開啟。
1. 在對應面板中，按一下&#x200B;**文字和二進位函式**&#x200B;圖示。 ![文字函式圖示](assets/toolbar-icon-text&binary-functions.png)
1. 選取函式&#x200B;**upper**。

   函式會顯示在「名稱」欄位中，包括預期輸入的格式。

   此範例的輸入是專案轉換來源問題的名稱。

1. 將游標移到括弧之間，因為這是輸入要移動的位置。
1. 在對應面板中，按一下&#x200B;**模組輸出**&#x200B;圖示。 ![模組輸出圖示](assets/toolbar-icon-functions-you-map-from-other-modules.png)
1. 選取第一個模組輸出的名稱區塊。

   名稱區塊會顯示在函式中。

   函式![中的](assets/map-name.png)名稱區塊

1. 按一下&#x200B;**確定**&#x200B;以儲存模組設定。

### 測試並啟動

1. 在熒幕左下角按一下&#x200B;**執行一次**&#x200B;以測試情境。
1. 檢查輸出，確保案例如預期般執行。
1. 當您滿意情境如預期般運作時，請按一下畫面左下角的&#x200B;**排程**&#x200B;切換開關至&#x200B;**開啟**。

   這會啟用情境。 作用中情境會根據觸發程式模組中設定的排程執行。
1. 在Workfront Fusion中，按一下左下角附近的&#x200B;**[!UICONTROL 儲存]**，以儲存情境的進度。

   >[!IMPORTANT]
   >
   >隨時儲存並測試情境。 您可能需要在Workfront帳戶中建立新問題才能觸發此情境。

## 資源

* [使用內建函式對應專案](/help//workfront-fusion/create-scenarios/map-data/map-using-functions.md)

---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 將篩選器新增至基本情境
description: 篩選可讓您確保您的案例僅在符合某些條件時進展。
author: Becky
feature: Workfront Fusion
exl-id: 78ab27fe-e2dd-4b52-b986-77b4b7ea3b5e
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 1%

---

# 將篩選器新增至基本情境

篩選可讓您確保您的案例僅在符合某些條件時進展。

在此範例中，您會新增篩選器至情境，以允許只有在請求已提交至特定請求佇列時，才能從請求建立新專案。

此範例修改在[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中建立的案例。

>[!NOTE]
>
>Workfront觸發模組包含篩選器，允許案例只在符合特定條件時啟動。 不過，由於模組間篩選器會用於每個非觸發程式和非Workfront使用案例，因此瞭解如何在模組間使用篩選器非常重要。 此範例針對模組內篩選器可能符合的功能，使用模組間篩選器。

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
   <td> <p>新增：標準</p><p>或</p><p>目前： [!UICONTROL Work]或更高版本</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增:</p> <ul><li>[!UICONTROL Select]或[!UICONTROL Prime] Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li><li>[!UICONTROL Ultimate] Workfront計畫：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

在執行此程式之前，您必須先建立[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中所述的案例。

## 新增篩選器

### 準備新增篩選器

1. 開啟情境。
1. 按一下第一個模組以開啟。
1. 在&#x200B;**輸出**&#x200B;區域中，選取`Project`。
您現在應該已選取`ID`、`Name`和`Project`。
1. 按一下「確定」以儲存模組設定。
1. 開啟Workfront。
1. 在Workfront中，找出代表Fusion案例將使用的請求佇列的專案。

   此專案必須位於為Fusion連線設定的Workfront帳戶中。

1. 在URL中記下專案ID。

   範例： https://\&lt;MyDomain\>.my.workfront.com/project/\&lt;ProjectID\>/tasks

### 新增並設定篩選器

1. 返回案例編輯器中的案例。
1. 按一下第一個模組和第二個模組之間的扳手圖示![扳手圖示](assets/wrench-icon.png)，然後選取&#x200B;**設定篩選器**。
1. 在「標籤」欄位中，輸入此篩選的標籤，例如「篩選請求佇列」。
1. 在&#x200B;**條件**&#x200B;區域中，在頂端欄位中，從第一個模組對應`projectID`。

   ![對應專案識別碼](assets/map-proj-id.png)
1. 將&#x200B;**條件**&#x200B;運運算元保留為Equal to。
1. 在&#x200B;**條件**&#x200B;區域的底部欄位中，貼上您在[準備新增篩選器](#prepare-to-add-the-filter)的專案URL中記下的專案ID。
1. 按一下&#x200B;**確定**&#x200B;以儲存篩選設定。

### 測試並啟動

1. 前往Fusion所連線的Workfront環境，並將問題新增至您在篩選中指定的專案。 將另一個問題新增至其他專案。
1. 按一下案例編輯器左下角的&#x200B;**[!UICONTROL 執行一次]**。
1. 檢查輸出，確保案例如預期般執行。

   這兩個問題都應該出現在第一個模組的輸出中，但只有指定專案中的問題應該顯示為第二個模組的輸入。
1. 當您滿意情境如預期般運作時，請按一下畫面左下角的&#x200B;**排程**&#x200B;切換開關至&#x200B;**開啟**。

   這會啟用情境。
1. 在Workfront Fusion中，按一下左下角附近的&#x200B;**[!UICONTROL 儲存]**，以儲存情境的進度。

   >[!IMPORTANT]
   >
   >隨時儲存並測試情境。

## 資源

* 如需篩選的詳細資訊，請參閱[將篩選新增至情境](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md)。

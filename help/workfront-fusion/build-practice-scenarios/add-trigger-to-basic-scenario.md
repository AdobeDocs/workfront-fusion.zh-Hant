---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 在基本情境中加入觸發程序模組
description: 瞭解如何新增觸發程式模組，以允許案例定期尋找新請求並將它們轉換為專案。
author: Becky
feature: Workfront Fusion
exl-id: cd8ac958-b7a6-4536-89d8-c79a2f8940a6
TQID: https://experienceleague.adobe.com/xepLecibr9U6FpQM0neDy15DbFGF55rR6gVYvo644H4
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
    internal-label: Integrations
source-git-commit: 347280547bea92c0ee498da519495569a3cac661
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 11%
---
# 在基本情境中加入觸發程序模組

觸發模組會放置在情境的開頭。 當指定服務發生變更時，這些模組會開始案例執行。 變更可以是建立新記錄、刪除記錄、更新記錄等。 您可以指定開始案例的變更條件。

輪詢模組會以設定的時間間隔檢查服務，並傳回在該時間間隔內發生變更的相關資訊。 如果沒有變更，則觸發器不會執行情境。

在此範例中，您將新增每15分鐘執行一次的觸發程式模組，並在有任何請求已提交至特定佇列時啟動案例。 然後此情境會將這些請求轉換為專案。

此範例修改在[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中建立的案例。

>[!NOTE]
>
>Workfront Fusion正在將案例編輯器轉換為新體驗。 在此轉換期間，傳統體驗和新體驗皆可使用，而且您可以隨時在它們之間切換。 我們建議您使用新體驗。 如需詳細資訊，請參閱文章「情境編輯器」中的[新體驗和傳統體驗](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)。

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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 先決條件

在執行此程式之前，您必須先建立[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中所述的案例。

## 在新體驗中新增並設定觸發程式模組（建議）

* [新增觸發程式模組](#add-the-trigger-module)
* [排程觸發程式模組](#schedule-the-trigger-module)
* [更新第二個模組](#update-the-second-module)
* [測試並啟動](#test-and-activate)

### 新增觸發程式模組

1. 在案例編輯器中開啟案例。
1. 在第一個（搜尋）模組上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 刪除模組]**。

   模組已刪除，並保留空白預留位置。

1. 按一下空白模組以開啟應用程式和服務清單。

   ![應用程式和服務選擇器](/help/workfront-fusion/build-practice-scenarios/assets/new-connector-picker.png)

1. 選取&#x200B;**Adobe Workfront**。
1. 選取&#x200B;**觀看記錄**。
1. 確認模組使用與案例中其他模組相同的連線。
1. 在[記錄型別]欄位中，選取&#x200B;**問題**。
1. 在篩選欄位中，選取&#x200B;**僅新增記錄**。
1. 在[輸出]方塊中，選取`ID`、`Name`和`Project ID`。
1. 按一下&#x200B;**確定**&#x200B;以儲存模組設定。

   「選擇開始位置」視窗會出現。

1. 從&#x200B;**開始選取**。

### 排程觸發程式模組

1. 按一下「監看紀錄」模組上的時鐘圖示。

   監視記錄模組上的![時鐘圖示](assets/clock-icon-on-watch-record.png)

   「排程」設定視窗會開啟。

1. 在[執行]案例欄位中，選取&#x200B;**定期間隔**。

1. 按一下&#x200B;**「確定」**。

### 更新第二個模組

因為第一個模組已取代，第二個模組必須對應至新的第一個模組。

1. 開啟轉換物件模組。
1. 在「問題ID」欄位中，刪除黑色ID區塊。 區塊為黑色，因為其對應來源模組已無法使用。
1. 在第一個模組（觀看記錄）下方選取ID區塊，將其對應至第二個模組。
1. 按一下&#x200B;**「確定」**。

### 測試並啟動

1. 前往Fusion所連線的Workfront環境並新增問題。
1. 按一下&#x200B;**[!UICONTROL 執行一次]**&#x200B;圖示。

   執行一次，在新體驗中是僅限圖示。 將游標停留在圖示上以檢視&#x200B;**[!UICONTROL 執行一次]**&#x200B;工具提示。

   ![執行案例按鈕](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/run-once-new.png)

1. 檢查輸出，確保案例如預期般執行。
1. 當您滿意情境如預期般運作時，請按一下&#x200B;**排程**&#x200B;切換至&#x200B;**開啟**。

   這會啟用情境。

   ![排程切換](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/scheduling-new.png)

1. 按一下[控制項]區域中的&#x200B;**儲存**&#x200B;圖示![儲存圖示](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/save-icon-new.png)，儲存您的情境進度。

   >[!IMPORTANT]
   >
   >隨時儲存並測試情境。

## 在傳統體驗中新增並設定觸發程式模組

* [新增觸發程式模組(Classic)](#add-the-trigger-module-classic)
* [排程觸發程式模組（傳統）](#schedule-the-trigger-module-classic)
* [更新第二個模組（傳統）](#update-the-second-module-classic)
* [測試並啟動（傳統）](#test-and-activate-classic)

### 新增觸發程式模組(Classic)

1. 在案例編輯器中開啟案例。
1. 在第一個（搜尋）模組上按一下滑鼠右鍵，然後選取&#x200B;**刪除模組**。

   模組已刪除，並保留空白預留位置。

1. 按一下空白模組，然後從應用程式清單中選取&#x200B;**Adobe Workfront**。
1. 選取&#x200B;**觀看記錄**。
1. 確認模組使用與案例中其他模組相同的連線。
1. 在[記錄型別]欄位中，選取&#x200B;**問題**。
1. 在篩選欄位中，選取&#x200B;**僅新增記錄**。
1. 在[輸出]方塊中，選取`ID`、`Name`和`Project ID`。
1. 按一下&#x200B;**確定**&#x200B;以儲存模組設定。

   「選擇開始位置」視窗會出現。

1. 從&#x200B;**開始選取**。

### 排程觸發程式模組（傳統）

1. 按一下Watch Record模組的時鐘。

   「排程」設定視窗會開啟。

1. 在[執行]案例欄位中，選取&#x200B;**定期間隔**。

1. 按一下&#x200B;**「確定」**。

### 更新第二個模組（傳統）

因為第一個模組已取代，第二個模組必須對應至新的第一個模組。

1. 開啟轉換物件模組。
1. 在「問題ID」欄位中，刪除黑色ID區塊。 區塊為黑色，因為其對應來源模組已無法使用。
1. 在第一個模組（觀看記錄）下方選取ID區塊，將其對應至第二個模組。
1. 按一下&#x200B;**「確定」**。

### 測試並啟動（傳統）

1. 前往Fusion所連線的Workfront環境並新增問題。
1. 按一下案例編輯器左下角的&#x200B;**[!UICONTROL 執行一次]**。
1. 檢查輸出，確保案例如預期般執行。
1. 當您滿意情境如預期般運作時，請按一下畫面左下角的&#x200B;**排程**&#x200B;切換開關至&#x200B;**開啟**。

   這會啟用情境。
1. 在Workfront Fusion中，按一下左下角附近的&#x200B;**[!UICONTROL 儲存]**，以儲存情境的進度。

   >[!IMPORTANT]
   >
   >隨時儲存並測試情境。

## 資源

* 如需有關觸發模組的詳細資訊，請參閱文章模組概觀中的[觸發模組](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)。

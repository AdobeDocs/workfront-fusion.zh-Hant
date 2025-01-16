---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 將webhook新增至基本情境
description: Webhook （也稱為即時觸發器）是一種特定的觸發器模組，可以在每次進行變更時啟動案例，而不是按照指定的排程。
author: Becky
feature: Workfront Fusion
exl-id: 28ecca1f-a9c3-4b3d-95f5-73cb9a5dc4b9
source-git-commit: 3ba5d67806e0d495bd4a91589d06cfb9adb25c0c
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 1%

---

# 將webhook新增至基本情境

Webhook （也稱為即時觸發器）是一種特定的觸發器模組，可以在每次進行變更時啟動案例，而不是按照指定的排程。

在此範例中，只要有任何請求已提交至特定請求佇列，您就會新增webhook以啟動案例。 然後此情境會將這些請求轉換為專案。

此範例修改在[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中建立的案例。

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
   <td> <p>新增： [!UICONTROL Standard]</p><p>或</p><p>目前： [!UICONTROL Work]或更高</p> </td> 
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
   <p>新增：</p> <ul><li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

在執行此程式之前，您必須先建立[建立基本案例](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)中所述的案例。

## 新增和設定webhook


### 新增webhook模組

1. 在案例編輯器中開啟案例。
1. 用滑鼠右鍵按一下第一個模組，然後選取&#x200B;**刪除模組**。

   模組已刪除，並保留空白預留位置。

1. 按一下空白模組，然後從應用程式清單中選取&#x200B;**Adobe Workfront**。
1. 選取&#x200B;**觀看活動**。
1. 按一下Webhook欄位旁的&#x200B;**新增**。
1. 在[記錄型別]欄位中，選取&#x200B;**問題**，模組就會觸發問題的變更。
1. 在「狀態」欄位中，選取&#x200B;**新狀態**。 這是用於篩選的必填欄位，此範例未涵蓋此欄位。
1. 在「記錄來源」欄位中，選取&#x200B;**僅新增記錄**。 這可讓情境在新增問題時觸發，而不是在更新或刪除問題時觸發。
1. 按一下[儲存]儲存模組組態。****

## 更新第二個模組

1. 開啟情境。
1. 按一下&#x200B;**轉換物件**&#x200B;模組以開啟。
1. 在「問題ID」欄位中，刪除黑色ID區塊。 區塊為黑色，因為其對應來源模組已無法使用。
1. 在第一個模組（觀看事件）下方選取ID區塊，將其對應至第二個模組。
1. 按一下&#x200B;**確定**。



### 測試並啟動

1. 按一下案例編輯器左下角的&#x200B;**[!UICONTROL Run once]**。

   案例必須執行中，才能監視新請求。
1. 前往Fusion所連線的Workfront環境並新增問題。

   此案例應執行。
1. 檢查輸出，確保案例如預期般執行。
1. 當您滿意情境如預期般運作時，請按一下畫面左下角的&#x200B;**排程**&#x200B;切換開關至&#x200B;**開啟**。

   這會啟用情境。
1. 在[!DNL Workfront Fusion]中，按一下左下角附近的&#x200B;**[!UICONTROL Save]**，以儲存您的情境進度。

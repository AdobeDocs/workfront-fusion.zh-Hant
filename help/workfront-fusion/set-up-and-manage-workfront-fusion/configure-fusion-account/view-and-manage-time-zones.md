---
title: 檢視和管理時區
description: 瞭解如何在Adobe Workfront Fusion中檢視和管理時區設定。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9910d9b4-5a7a-4f4a-9e66-8600d3b6c785
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 39c34b17e766678e187837e07c90b67f365a4f1d
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 17%
---
# 檢視和管理時區

Adobe Workfront Fusion包含組織和使用者層級的時區控制項。

* 組織時區：案例會使用組織時區來決定排程事件的發生時間。

* 使用者時區：使用者時區決定向使用者顯示的時間。

>[!BEGINSHADEBOX]

範例：

組織位於紐約市，組織時間設為UTC-5 （美洲/紐約）。 案例A屬於此組織，並排程在每天上午9:00執行。 此情境會在紐約時區的上午9:00執行。

此組織中的使用者住在洛杉磯，且其使用者時區設定為UTC-8 （美洲/洛杉磯）。 當此使用者檢視案例A的案例執行歷史記錄時，他們會看到案例在早上6:00執行。 即使情境是按照紐約時間執行，使用者仍會看到時間轉換為他們自己的時區。

>[!ENDSHADEBOX]



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
  <tr> 
   <td role="rowheader">存取層級</td> 
   <td> 您必須是組織的擁有者或管理員才能編輯該組織的時區。 </td>
   </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 檢視和管理您的使用者時區

1. 在Fusion中，按一下畫面右上角的Adobe設定檔圖示。
1. 在開啟的功能表中，選取&#x200B;**Fusion設定檔**。
1. 選取&#x200B;**時區選項**標籤。 索引標籤直接位於您的名稱下方。
「時區選項」清單隨即開啟。
1. 在「時區選項」清單的Web區域中，找出您的名稱。

   您目前的使用者時區設定會顯示在您名稱的右側。
1. 若要編輯時區，請按一下時區旁的編輯![編輯時區](assets/edit-timezone-icon.png)。
1. 在「變更詳細資料」視窗的&#x200B;**時區**&#x200B;欄位中，選取您要為自己設定的時區。
1. 按一下「**儲存**」。


## 檢視及管理您組織的時區

>[!NOTE]
>
>您必須是組織的擁有者或管理員才能編輯該組織的時區。

1. 在Fusion中，按一下畫面右上角的Adobe設定檔圖示。
1. 在開啟的功能表中，選取&#x200B;**Fusion設定檔**。
1. 選取&#x200B;**時區選項**標籤。 索引標籤直接位於您的名稱下方。
「時區選項」清單隨即開啟。
1. 在「時區選項」清單的「案例」區域中，找出您要檢視或管理其時區的組織。

   組織的目前時區設定會顯示在組織名稱的右側。
1. 若要編輯時區，請按一下時區旁的編輯![編輯時區](assets/edit-timezone-icon.png)。
1. 在「變更詳細資料」視窗的&#x200B;**時區**&#x200B;欄位中，選取您想要為組織設定的時區。
1. 按一下「**儲存**」。



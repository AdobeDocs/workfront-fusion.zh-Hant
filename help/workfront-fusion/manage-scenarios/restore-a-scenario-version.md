---
title: 檢視和管理案例版本
description: 您可以檢視、還原、重新命名或下載情境舊版的Blueprint。
author: Becky
feature: Workfront Fusion
exl-id: e7fd0351-b840-422c-b861-82ae110c703b
TQID: https://experienceleague.adobe.com/xVihxZH-fwPCIkryQAQEOWgeShtPTMXth4jEl5OLdbo
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: eb4c1ed6991606928beccbb57a8a86182e58a9e7
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 14%

---

# 檢視和管理案例版本

Adobe Workfront Fusion會在每次變更時儲存案例的版本。

您可以檢視、還原、重新命名或下載情境舊版的Blueprint。

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

## 檢視及管理情境的版本記錄

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]** ![案例圖示](assets/scenarios-icon.png)，然後按一下案例以開啟它。
1. 按一下畫面底部的[!UICONTROL 更多]圖示![更多圖示](assets/more-icon.png)，然後按一下&#x200B;**[!UICONTROL 舊版]**。

   先前版本的清單隨即顯示。
1. （選擇性）若要重新命名版本，請按一下該版本行上的[更多]功能表![[更多]功能表](assets/more-icon-vertical.png)，選取&#x200B;**[編輯]**，然後在欄位中輸入名稱。 按一下[儲存]儲存新名稱。**&#x200B;**

   建議您提供名稱，說明針對此版本所做的變更。
1. （選擇性）若要下載舊版的Blueprint，請按一下該版本行上的[更多]功能表![[更多]功能表](assets/more-icon-vertical.png)，然後選取[下載]&#x200B;**&#x200B;**。
1. （選擇性）若要比較兩個版本之間的變更，請按一下該版本的&#x200B;**檢視變更**。

   如需比較版本的詳細資訊與指示，請參閱本文中的[比較案例版本](#compare-scenario-versions)。
1. （選擇性）若要還原版本，請按一下該版本行上的&#x200B;**還原**


   >[!NOTE]
   >
   >情境的還原版本不會自動儲存。 如果要儲存案例的還原版本，您必須手動儲存。



## 比較案例版本

&#x200B;URL
檢視變更功能會並排顯示兩個案例版本之間的差異，讓您在決定還原較舊案例之前可以確切檢視變更內容。

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]** ![案例圖示](assets/scenarios-icon.png)，然後按一下案例以開啟它。
1. 按一下畫面底部的[!UICONTROL 更多]圖示![更多圖示](assets/more-icon.png)，然後按一下&#x200B;**[!UICONTROL 舊版]**。

   先前版本的清單隨即顯示。
&#x200B;URL
1. 按一下您要檢視之情境版本的&#x200B;**檢視變更**。
1. **檢閱變更**&#x200B;檢視會開啟，並將該版本與您目前的案例進行比較。

   「檢閱變更」面板隨即開啟，並排顯示兩個案例版本。

   * 在左側，您會看到目前版本。
   * 在右側，您會看到自己點按的版本。 這是您可以還原的版本。

   若要瞭解變更，請參閱本文中的[檢查變更](#examine-changes)。

1. 若要選取任一端的另一個版本，請按一下面板頂端附近的&#x200B;**比較自**&#x200B;或&#x200B;**比較至**&#x200B;下拉式清單，並選取另一個案例版本。
1. 若要交換側邊，請按一下案例之間的&#x200B;**⇄**&#x200B;按鈕。
1. 若要還原到右側的情境，請按一下&#x200B;**還原到選取的版本**

   還原的版本會儲存為新版本，因此將來可以還原。

   若要還原到目前位於左側的案例，請交換側邊使其位於右側，然後按一下&#x200B;**還原到選取的版本**。


### 檢查變更

&#x200B;URL
每個變更都會顯示在其所屬的一側，並以還原的方式著色
執行：

* 紅色（左側）：此變更不在右側的版本中，若版本還原則會移除。
* 綠色（右）：此變更位於右側，如果版本已還原，則會新增此變更。

如果發生變更，則值會在左側以紅色顯示，在右側以綠色顯示，而不是移除或新增。
&#x200B;URL
變更會分組為多個區段：
&#x200B;URL

* **案例**：名稱、說明和型別。
* **案例設定**：排程與處理選項。
* **模組**：已新增、移除、移動或重新設定模組。
* **流程**：已新增、移除或重新排序區段。
* **路由器路由**：路由及其內容。
* **錯誤處理常式**：錯誤處理分支。
* **孤立群組**：畫布上的模組已中斷連線。
&#x200B;URL
如果兩個版本相同，檢視會顯示訊息/ **找不到差異**。
&#x200B;URL



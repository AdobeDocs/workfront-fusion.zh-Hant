---
title: 將模組移至鏈結
description: 您可以在情境中選取一組模組，然後將它們移至新的鏈結情境，而無需手動重新建立對應或資料結構。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: f1a80f64edc410ae76bfbba1280df7232e2d09c5
workflow-type: tm+mt
source-wordcount: 513
ht-degree: 17%

---

# 將模組移至鏈結

>[!IMPORTANT]
>
>此功能位於Beta中，不建議用於關鍵任務生產工作流程。 由於Beta功能，行為可能會變更，且邊緣案例可能無法完全處理。

您可以在情境中選取一組模組，然後將它們移至新的鏈結情境，而無需手動重新建立對應或資料結構。 這提供了模組化大型情境的簡單方法。

將一組模組移至鏈結時，Workfront Fusion：

* 將選取的模組移至新建立的情境。
* 在單獨的瀏覽器視窗中開啟新情境。
* 以鏈結>呼叫子案例模組取代原始案例中選取的模組。
* 自動建立新子案例所需的輸入和輸出資料結構。
* 保留現有的案例行為，讓案例繼續以移動模組之前的方式執行。
* 自動更新對應：
  * 移至子項案例的模組會透過「鏈結>接收來自父模組輸入的資料」來接收資料。
  * 子情境的輸出會自動顯示回父情境。
  * Blueprint中的現有對應會調整以符合新結構。

如需計畫連結案例的資訊，請參閱[將多個案例連結在一起](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)。

如需設定鏈結模組的說明，請參閱[鏈結模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/chain-modules.md)。

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

您要移至鏈結的模組必須已存在於案例中，而且您必須選取多個模組。

## 限制

在下列情況下，您無法將選取的模組移至鏈中：

* 選取的模組不是單一連續流程的一部分。 例如，您無法同時從兩個不同的未連線路由選取模組。
* 選取範圍包含webhook模組。
* 選取範圍包含另一個鏈結模組。
* 選取範圍包括路由器模組，而您尚未選取該路由器的所有路由。
* 選取的模組具有錯誤處理常式路由，而您尚未選取該路由。

## 將模組移至鏈結中

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取包含您要移動模組的情境。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按住[!UICONTROL Shift]，然後按一下要移動的模組，以選取要移至鏈結的模組。
1. 以滑鼠右鍵按一下其中一個選取的模組。
1. 選取&#x200B;**[!UICONTROL 移至鏈結]**。

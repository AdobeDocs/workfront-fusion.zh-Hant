---
title: 重新觸發特定案例執行
description: 您可以重新觸發特定案例執行，以使用更新的案例藍圖處理資料，或檢視其資料流程。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 5859bbef4f45fd4741d89ba1795df8a67fa5beaa
workflow-type: tm+mt
source-wordcount: 523
ht-degree: 18%

---

# 重新觸發特定案例執行

您可以重新觸發特定案例執行，以使用更新的案例藍圖處理資料，或檢視其資料流程。 當您重新觸發執行時，情境會使用該執行的資料執行。

例如，如果您更新案例以新增動作，例如建立問題，您可以重新觸發更新前發生的執行。 更新的情境將使用原始情境的觸發事件執行，但將包含更新的動作。 在此範例中，情境會在新執行過程中建立問題。

重新觸發適用於具有webhook觸發器的情境以及鏈結情境。

當重新觸發使用webhook的情景時，可以再次使用原始webhook事件，因此您不必重新建立事件來重新觸發情境。

使用鏈結情境時，重新觸發也可以套用至子情境。 子案例可使用從原始執行中的父案例傳送的資料重新觸發，而無需重新觸發父案例。

如需 Webhook 的詳細資訊，請參閱[即時觸發程序 (Webhook)](/help/workfront-fusion/references/modules/webhooks-reference.md)。

如需連結情境的詳細資訊，請參閱[將多個情境連結在一起](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)。

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

## 重新觸發執行

您可以從情境的圖表、情境的歷程記錄區域或特定情境執行的頁面重新觸發情境執行。

### 從案例圖表重新觸發執行

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取執行您要重新觸發的執行的案例。

   情境的圖表隨即開啟。
1. 在頁面右側的執行清單中，找出您要重新觸發的執行。
1. 按一下該案例的&#x200B;**重新觸發程式**。

![從圖表重新觸發程式](assets/retrigger-from-diagram.png)

### 從案例歷史記錄重新觸發執行

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取執行您要重新觸發的執行的案例。

   情境的圖表隨即開啟。

1. 按一下案例名稱正下方的&#x200B;**歷程記錄**&#x200B;標籤。
1. 找到您要重新觸發的執行。 如有必要，您可以使用全文搜尋來尋找它。
1. 按一下該案例的&#x200B;**重新觸發程式**。

![從歷程記錄重新觸發程式](assets/retrigger-from-history.png)

### 從案例執行頁面重新觸發案例

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取執行您要重新觸發的執行的案例。

   情境的圖表隨即開啟。
1. 在頁面右側的執行清單中，找出您要重新觸發的執行。
1. 按一下執行以開啟。
1. 在執行頁面上，按一下&#x200B;**重新觸發程式**。


![從執行重新觸發程式](assets/retrigger-from-execution.png)







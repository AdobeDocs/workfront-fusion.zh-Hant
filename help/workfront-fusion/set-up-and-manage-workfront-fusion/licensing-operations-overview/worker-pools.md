---
title: 工作者集區
description: 工作者集區是專用於一或多個特定組織的Workfront Fusion處理資源數量。 所有Fusion作業和處理都會在組織的已指派工作者集區的內容中進行。
author: Becky
feature: Workfront Fusion
exl-id: 8bf508a8-d1f9-455f-af89-62f688289137
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: b800142d824927e5765eed50a831731e6b5d9925
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 19%
---
# 工作者集區

工作者集區是專用於特定組織的Workfront Fusion處理資源數量。 所有Fusion作業和處理都會在組織的已指派工作者集區的內容中進行。

工作者集區可讓您的情境更有效率地執行，並排除與其他組織競爭Fusion處理容量的機會。

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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 背景工作集區概述

背景工作集區是平行處理案例執行的一種方式。 每個背景工作集區都與下列專案相關聯：

* 背景工作數。
* 執行佇列。

執行案例時，它會傳遞到背景工作集區的執行佇列中。 集區中的工作程式會持續從執行集區提取任務，並同時處理這些任務。

如果執行佇列深度增加，且所有現有背景工作正在使用中，Workfront Fusion會透過新增更多背景工作來自動縮放集區。 此擴充功能是動態且以事件導向，這表示容量會根據即時負載而執行或訂立合約，您或您的組織無需採取任何動作。

Workfront Fusion團隊會持續監控集區的使用率和擴充行為，並可檢閱臨界值或模式，以確保隨著使用率增長而維持一致的效能。

## 重新命名背景工作集區

組織擁有者和管理員可以重新命名指派給其組織的工作者集區。 依預設，每個集區會顯示系統產生的名稱。 您可以為集區指定自訂名稱，例如`Marketing EU`或`High-volume integrations`，並視需要隨時變更。

重新命名集區只會變更其標示方式。 情境、執行和集區容量不受影響。 新名稱會出現在顯示集區的任何位置，例如將案例指派給集區時。

>[!NOTE]
>
>只有當為您的組織指派了多個工作者集區，才會顯示&#x200B;**[!UICONTROL 工作者集區]**&#x200B;標籤。 如果您的組織有單一背景工作集區，或使用共用集區，您不會看到標籤。

若要重新命名工作者集區：

1. 在左側導覽列中，按一下&#x200B;**組織概覽**
1. 按一下靠近頁面頂端的&#x200B;**[!UICONTROL 背景工作集區]**&#x200B;標籤。

   索引標籤會列出每個集區，並顯示指派給它的案例數。

1. 按一下您要重新命名的集區旁的&#x200B;**[!UICONTROL 重新命名]**。
1. 在開啟的面板中輸入新名稱。
1. 按一下「**儲存**」。

---
title: 檢視組織的效能儀表板
description: Fusion administrators can view a dashboard that shows execution metrics for an organization.
author: Becky
feature: Workfront Fusion
exl-id: 8f80f86a-69e5-48a1-9812-87322a4959a6
source-git-commit: 6762806f17a0fc55531b647a84901b8ca572a997
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 7%

---

# 檢視組織的效能儀表板

The Fusion Performance Dashboard allows you to quickly see which scenarios are running the most, where delays are occurring, and how effectively your worker pools are operating. This provides real-time visibility into execution volumes, queue depth, pool utilization, and scenario-level performance.

## 存取權要求

+++ 展開以檢視這篇文章中所述功能的存取權要求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront 封裝</td> 
   <td> <p>Adobe Workfront工作流程Ultimate和Adobe Workfront自動化與整合Ultimate</p><p>Workfront Ultimate</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront 授權</td> 
   <td> <p>標準</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定</td> 
   <td> 
     <p>您必須是組織的Workfront Fusion管理員。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## Performance dashboard components

>[!NOTE]
>
>Metrics are shown by worker pool. To view a different worker pool, click the Pool field near the upper-left corner of the dashboard, then select the pool you want to view metrics for.

<!--

>[!NOTE]
>
>Organizations can request provisioning for one additional worker pool (for a total of 2).

-->

In the Fusion performance dashboard, you can see the following metrics.

* **Executions waiting to be processed**
This chart shows the number of executions waiting to be processed (also known as the execution backlog) at a given point in time.

  A high number of executions waiting to be processed may affect performance in your Fusion instance. You will receive a notification if your execution backlog reaches 5000 executions. We recommend identifying responsible scenarios and modifying or disabling them. If the high execution backlog persists, the Fusion team will protect the performance of your Fusion instance by disabling the responsible scenarios.
* **Pool Utilization**
This chart shows worker pool utilization over time. If this chart routinely shows worker pool utilization, you may want to assign some scenarios to another pool.

  If a pool is nearing 100% utilization, other resources that use the same pool may be delayed or disrupted. If this occurs, we recommend reassigning a high-usage scenario to another worker pool, or modifying existing scenarios to be less resource intensive.
* **Executions per scenario**
This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

  您可以使用此圖表來識別哪些案例可能會導致執行待處理專案或高工作者集區使用率。
* **執行期間**
此圖表顯示每個案例的執行次數。 不同的顏色代表不同的情境。 當您將滑鼠停留在圖表上時，會出現一個視窗，顯示哪個顏色是哪個案例。

  您可以使用此圖表來識別花費較平常更長的情境，包括受連線應用程式或服務問題影響的情境。

## 檢視Fusion效能儀表板

1. 在Fusion中，按一下左側導覽中的&#x200B;**效能**。

   「圖示板」隨即開啟。

1. 若要檢視特定時間點的資料，請將游標暫留在控制面板上，並將游標調整為您要檢視的時間點。

   所有圖形上都會在該時間點上出現一條線條，而每個圖形上都會出現一個顯示該時間資料的視窗。
1. 若要在「每個案例的執行次數」圖表或「執行持續時間」圖表中檢視特定案例的資料，請按一下您要檢視資料之案例的顏色長條。 若要返回顯示所有情境的檢視，請再次按一下圖表。
1. 若要移至「每個案例的執行次數」圖表或「執行持續時間」圖表中顯示的特定案例，請以滑鼠右鍵按一下案例的顏色列，然後選取&#x200B;**在新標籤中開啟案例**。
1. 若要展開圖表，請按一下該圖表右上角的&#x200B;**展開**&#x200B;圖示![展開圖示](assets/expand-icon.png)。
1. 若要變更控制面板的時間範圍，請在控制面板右上角的「時間範圍」欄位中選取新的時間範圍。 可用的最長時段為24小時，最短時段為15分鐘。
1. 若要重新整理圖表，請按一下控制面板右上角附近的重新整理圖示。
1. 若要檢視不同的Worker集區，請按一下控制面板左上角附近的「集區」欄位，然後選取您要檢視的集區。

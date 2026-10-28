---
title: 檢視組織的前瞻分析控制面板
description: Fusion管理員可以檢視顯示組織執行度量的控制面板。
author: Becky
feature: Workfront Fusion
exl-id: 8f80f86a-69e5-48a1-9812-87322a4959a6
TQID: 'https://experienceleague.adobe.com/tBZCbpImQxY42gOE8e04aQwCJC8EKgrDTIAt6Sw1KaU'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 45c755a2f6152b6e230864e4c840d0334705bd22
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 2%
---
# 檢視組織的前瞻分析控制面板

Fusion Insights儀表板可讓您快速檢視哪些案例的執行最頻繁、發生延遲的位置，以及您的背景工作集區的運作效率。 這可提供執行磁碟區、佇列深度、集區使用率和案例層級效能的即時可見度。

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

## 前瞻分析儀表板元件

>[!NOTE]
>
>度量會依工作者集區顯示。 若要檢視不同的Worker集區，請按一下控制面板左上角附近的「集區」欄位，然後選取您要檢視量度的集區。

<!--

>[!NOTE]
>
>Organizations can request provisioning for one additional worker pool (for a total of 2).

-->

在Fusion Insights儀表板中，您可以看到以下量度。

* **失敗的執行記錄檔**
此表格列出整個組織中每個失敗或警告案例的執行情形，因此您可以在不離開控制面板的情況下尋找問題執行並進行疑難排解。
* **組織作業**
此圖表可讓您檢視組織中使用的作業數目。 您可以選取特定的團隊或案例，並檢視過去一週、一個月或年中的作業。
* **依作業排名最前的案例**
此圖表可讓您檢視哪些案例使用最多作業。 您可以選取特定團隊，或檢視過去一天、一週或月的資料。

<!--

* **Executions waiting to be processed**
   This chart shows the number of executions waiting to be processed (also known as the execution backlog) at a given point in time. 

   A high number of executions waiting to be processed may affect performance in your Fusion instance. You will receive a notification if your execution backlog reaches 5000 executions. We recommend identifying responsible scenarios and modifying or disabling them. If the high execution backlog persists, the Fusion team will protect the performance of your Fusion instance by disabling the responsible scenarios.
* **Pool Utilization**
   This chart shows worker pool utilization over time. If this chart routinely shows worker pool utilization, you may want to assign some scenarios to another pool.

   If a pool is nearing 100% utilization, other resources that use the same pool may be delayed or disrupted. If this occurs, we recommend reassigning a high-usage scenario to another worker pool, or modifying existing scenarios to be less resource intensive.
* **Executions per scenario**
   This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

   You can use this chart to identify which scenarios may be causing an execution backlog or high worker pool utilization. 
* **Duration of executions**
   This chart displays executions per scenario. Different colors represent different scenarios. When you hover over the chart, a window appears that shows which color is which scenario.

   You can use this chart to identify scenarios that are taking longer than usual, including those affected by issues with a connected app or service.

-->

## 檢視Fusion Insights控制面板

1. 在Fusion中，按一下左側導覽中的&#x200B;**深入分析**。

   「圖示板」隨即開啟。

1. 若要檢視特定時間點的資料，請將游標暫留在控制面板上，並將游標調整為您要檢視的時間點。

   所有圖形上都會在該時間點上出現一條線條，而每個圖形上都會出現一個顯示該時間資料的視窗。
1. 若要在「每個案例的執行次數」圖表或「執行持續時間」圖表中檢視特定案例的資料，請按一下您要檢視資料之案例的顏色長條。 若要返回顯示所有情境的檢視，請再次按一下圖表。
1. 若要移至「每個案例的執行次數」圖表或「執行持續時間」圖表中顯示的特定案例，請以滑鼠右鍵按一下案例的顏色列，然後選取&#x200B;**在新標籤中開啟案例**。
1. 若要展開圖表，請按一下該圖表右上角的&#x200B;**展開**&#x200B;圖示![展開圖示](assets/expand-icon.png)。
1. 若要變更控制面板的時間範圍，請在控制面板右上角的「時間範圍」欄位中選取新的時間範圍。 可用的最長時段為24小時，最短時段為15分鐘。
1. 若要重新整理圖表，請按一下控制面板右上角附近的重新整理圖示。
1. 若要檢視不同的Worker集區，請按一下控制面板左上角附近的「集區」欄位，然後選取您要檢視的集區。

## 自訂見解儀表板

您可以選擇要讓哪些Widget出現在前瞻分析儀表板上，以及按照什麼順序。

### 新增、移除或重新排序Widget

1. 在左側導覽中，按一下&#x200B;**深入分析** ![深入分析圖示](assets/insights-icon.png)。
1. 按一下前瞻分析標題中的&#x200B;**[!UICONTROL 自訂]**。

   側面板隨即開啟。 它會將每個Widget列為顯示預覽、Widget名稱和說明的資訊卡。

1. 若要顯示或隱藏Widget，請按一下其卡片，或按一下卡片上的&#x200B;**[!UICONTROL 新增Widget]**&#x200B;或&#x200B;**[!UICONTROL 移除Widget]**&#x200B;按鈕。

   顯示的Widget有核取記號。
1. 若要重新排序Widget，請將Widget卡片拖曳至面板中的新位置。

   虛線預留位置與下拉式列顯示卡片將登陸的位置。

您的選擇會依瀏覽器儲存。 在後續發行版本中新增的Widget會自動出現在面板中。

如果移除所有Widget，頁面會顯示「此頁面上沒有Widget」訊息。

## 重新整理見解儀表板

若要重新載入每個介面工具集的資料，請按一下&#x200B;**[!UICONTROL 自訂]**&#x200B;旁的&#x200B;**[!UICONTROL 重新整理]**。

* 每個Widget會保留其篩選器。
* **[!UICONTROL 重新整理]**&#x200B;按鈕會顯示擱置狀態，直到所有Widget完成載入。
* 圖表會將先前的圖表保持在載入進度軸下，而執行記錄會在資料重新載入時，將其表格調暗到進度軸下。
* 如果重新整理失敗，Widget會保留其最後的良好資料。

## 進行見解導覽

第一次開啟「深入分析」儀表板時，歡迎對話方塊可讓您選擇開始導覽或略過導覽。

導覽會以您儲存的順序反白顯示每個Widget，以及標題列中的&#x200B;**[!UICONTROL 自訂]**&#x200B;按鈕和面板、**[!UICONTROL 重新整理]**&#x200B;按鈕和&#x200B;**[!UICONTROL 重播導覽]**&#x200B;按鈕。

若要隨時重新開始導覽，請按一下標題列中的導覽資訊圖示![資訊圖示](assets/insights-tour-information.png)。

當您從情境中的連結開啟前瞻分析儀表板時，導覽不會開始。 如需詳細資訊，請參閱本文中的[從情境](#open-the-insights-dashboard-from-a-scenario)開啟深入分析儀表板。

## 依ID搜尋案例和團隊

在&#x200B;**[!UICONTROL 組織作業]**&#x200B;與&#x200B;**[!UICONTROL 依作業排名最前的案例]** Widget中，**[!UICONTROL 案例]**&#x200B;與&#x200B;**[!UICONTROL 團隊]**&#x200B;欄位在ID與名稱上相符。 每個選項都會在名稱下方顯示其ID，例如「ID 123」。

* 清單會載入前500個案例和前200個團隊。 如果您輸入的ID不在載入清單中，Fusion會在短暫的延遲後自動查詢該ID。
* 如果您清除情境，則自動為該情境填寫的團隊也會被清除。

>[!NOTE]
>
>執行記錄中的案例篩選器在ID上不相符。

## 從情境開啟前瞻分析儀表板

您可以使用篩選至特定案例和團隊的&#x200B;**[!UICONTROL 組織作業]** Widget來開啟「深入分析」儀表板。

若要從案例移至「深入分析」頁面：

1. 開啟案例詳細資訊頁面：

   1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤，然後按一下您想要瞭解詳細資訊的案例。

      或

      如果您正在案例編輯器中處理案例，請按一下視窗左上角附近的向左箭頭![結束編輯箭頭](assets/exit-editing-arrow.png)。
      1. 按一下頁面頂端附近的&#x200B;**報表**&#x200B;索引標籤。

* **[!UICONTROL 組織作業]** Widget會開啟篩選為該案例和團隊的頁面，頁面會捲動至Widget。
* 如果您已從頁面移除介面工具集，則會改為顯示警告訊息，其中包含&#x200B;**[!UICONTROL 新增Widget]**&#x200B;按鈕。

## 使用深色模式

前瞻分析儀表板及其Widget會自動遵循您的深色模式設定。 當您變更設定時，頁面會立即更新，不會重新載入，並維持您目前的狀態。 光源模式不變。

## 效能Widget存取

**[!UICONTROL 效能]** Widget只會顯示給具有下列其中一項許可權的使用者：

* 在作用中組織中編輯組織
* 管理頁面上的組織檢視

其他使用者的Widget會隱藏在頁面和&#x200B;**[!UICONTROL 自訂]**&#x200B;面板中。 如果之後授予使用者存取權，Widget會傳回其儲存位置。 直接開啟深入分析URL不會略過此檢查。

## 在執行記錄中篩選和分類執行

使用執行記錄尋找在您的組織中失敗或傳回警告的案例執行，並重新啟用在重複失敗後自動停用的任何案例。

1. 在執行記錄中，依下列任一專案篩選執行：

   * [!UICONTROL 團隊]
   * [!UICONTROL 情境]
   * [!UICONTROL 執行型別]
   * [!UICONTROL 日期範圍]
   * [!UICONTROL 停用狀態]
   * [!UICONTROL 錯誤訊息]

   對於大多數的篩選器，您可以選擇僅符合您選取的值，或除了這些值之外的所有值。

1. 按一下執行以檢視有關其錯誤的更多詳細資料。
1. 若要重新啟用一或多個在重複失敗後自動停用的案例，請選取執行，然後按一下[啟用]。****

   >[!NOTE]
   >
   >在重新啟用案例之前，請調查失敗的原因，例如過期的憑證或聯結器問題，因此案例不會立即再次失敗。

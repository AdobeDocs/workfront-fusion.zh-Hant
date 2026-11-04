---
title: 說明人工智慧的案例錯誤
description: 當案例執行失敗時，您可以按一下錯誤旁邊的說明，以取得有關哪裡發生錯誤以及如何加以修正的簡短語言說明。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: e2420c8a25fd9e38c4b0300b00560fe1837a5e43
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 15%
---
# 說明人工智慧的案例錯誤

當案例執行失敗時，AI可以為您提供簡短且簡單的語言描述，說明哪裡出了錯誤以及如何修復。 說明會顯示在原始錯誤旁邊，因此您可以同時閱讀兩者。

您可以在Workfront Fusion的下列區域中說明錯誤：

* 案例設計工具中的模組錯誤詳細資料
* 案例執行歷程中的執行詳細資料
* 深入分析頁面上的[!UICONTROL 失敗的執行記錄]表格

>[!NOTE]
>
>**[!UICONTROL Explain]**&#x200B;按鈕僅在新的案例設計工具中可用。 舊版情境設計工具中不提供此功能。

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

## 說明模組輸出詳細資訊中的錯誤

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要說明錯誤的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 以排程方式執行情境，或按一下&#x200B;**執行一次**。
1. 當模組失敗時，請開啟模組的錯誤詳細資料。
1. 按一下&#x200B;**[!UICONTROL 說明]**。

   按鈕在錯誤下方。

   ![模組輸出中的說明錯誤](assets/explain-in-module-output.png)

說明會顯示在錯誤下方。

>[!NOTE]
>
> * 當AI產生說明時，會出現載入狀態。
> * 如果無法產生說明，請按一下&#x200B;**[!UICONTROL 再試一次]**。
> * 如果您的組織達到其AI使用量限制，則會出現使用量限制訊息，而非說明。

## 說明案例執行歷程中的錯誤

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤，然後按一下案例。
1. 按一下情境名稱附近的&#x200B;**[!UICONTROL 歷程記錄]**。
1. 按一下您要檢視的失敗執行。

   執行詳細資訊中的每個錯誤都有&#x200B;**[!UICONTROL Explain]**&#x200B;按鈕。

1. 在您要說明的錯誤下，按一下&#x200B;**[!UICONTROL 說明]**。

   如果多個模組在執行中失敗，您可以自行說明每個錯誤。

   ![在執行歷程記錄中說明](assets/explain-in-execution-details.png)

如需檢視回合的詳細資訊，請參閱[檢視案例的執行歷程記錄](/help/workfront-fusion/manage-scenarios/view-scenario-execution-history.md)和[檢視特定案例執行](/help/workfront-fusion/manage-scenarios/view-a-specific-scenario-execution.md)。

>[!NOTE]
>
> * 當AI產生說明時，會出現載入狀態。
> * 如果無法產生說明，請按一下&#x200B;**[!UICONTROL 再試一次]**。
> * 如果您的組織達到其AI使用量限制，則會出現使用量限制訊息，而非說明。

## 說明前瞻分析頁面上的錯誤

1. 在Fusion中，按一下左側導覽中的&#x200B;**[!UICONTROL 深入分析]**。
1. 在[!UICONTROL 失敗的執行]表格中，暫留在您要檢視的失敗列上。

   出現&#x200B;**[!UICONTROL Explain]**&#x200B;按鈕。

1. 按一下&#x200B;**[!UICONTROL 說明]**。

   ![在深入分析頁面中說明](assets/explain-failed-execution-log.png)

   隨即開啟快顯視窗，顯示錯誤和AI說明。

如需深入分析頁面的詳細資訊，請參閱[檢視組織的深入分析儀表板](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/view-insights-dashboard.md)。

>[!NOTE]
>
> * 當AI產生說明時，會出現載入狀態。
> * 如果無法產生說明，請按一下&#x200B;**[!UICONTROL 再試一次]**。
> * 如果您的組織達到其AI使用量限制，則會出現使用量限制訊息，而非說明。

---
title: k的佇列
description: 許多服務都會提供Webhook，以便在服務發生特定變更時傳送即時通知。 即時觸發器（也稱為Webhook）可以使用這些事件開始案例。 事件在等待處理時進入webhook的佇列，例如當案例已經在執行時。 您可以檢視webhook的佇列。
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
TQID: 'https://experienceleague.adobe.com/FtTjoNtYNM9kuPDMaHa4883m13pLO2MRat5ohnjXuAM'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 1c28e4007e3e9d6503618482002e506f9393ee57
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 16%
---
# 檢視webhook的佇列

許多服務都會提供Webhook，以便在服務發生特定變更時傳送即時通知。 即時觸發器（也稱為Webhook）可以使用這些事件開始案例。 事件在等待處理時進入webhook的佇列，例如當案例已經在執行時。 您可以檢視webhook的佇列。

無論您在案例設定面板中如何設定「資料是機密的」選項，傳入的webhook資料一律會儲存在佇列中。 在情境中處理資料後，資料會從佇列中永久刪除。

如需 Webhook 的詳細資訊，請參閱[即時觸發程序 (Webhook)](/help/workfront-fusion/references/modules/webhooks-reference.md)。

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

## 檢視webhook的佇列

所有來自傳入webhook的訊息都會儲存在webhook的佇列中。

如果情境目前有佇列，則該情境中會顯示橫幅：

![佇列橫幅](assets/queue-banner.png)

webhook的佇列頁面具有與&#x200B;**[!UICONTROL 案例]**&#x200B;和&#x200B;**[!UICONTROL Webhook]**&#x200B;清單相同的配置。

>[!NOTE]
>
>搜尋和排序只適用於目前載入表格中的事件，不適用於整個佇列。 若要包含更多事件，請先載入其他事件。

若要檢視和管理webhook的佇列：

1. 按一下左側功能表中的&#x200B;**[!UICONTROL Webhooks]**。
1. 找到您要檢視其佇列的Webhook。
1. 找出「完整佇列」欄中的事件數。

   ![Webhook佇列](assets/webhook-queue.png)

1. 按一下&#x200B;**作業**&#x200B;按鈕，檢視佇列中事件的詳細資訊。

   webhook的佇列頁面隨即開啟。 此頁面列出資料表中佇列的事件，其資料行如下： **[!UICONTROL ID]**、**[!UICONTROL 建立於]**、**[!UICONTROL 大小]**&#x200B;以及&#x200B;**[!UICONTROL 詳細資料]**。

1. （選擇性）若要篩選表格中的事件，請在表格上方的&#x200B;**[!UICONTROL 搜尋]**&#x200B;欄位中輸入文字。
1. （選擇性）若要排序事件，請按一下&#x200B;**[!UICONTROL ID]**、**[!UICONTROL 建立於]**，或&#x200B;**[!UICONTROL Size]**&#x200B;資料行標頭。
1. （選擇性）若要變更每個頁面上顯示的事件數目，請在頁面底部的&#x200B;**[!UICONTROL 顯示]**&#x200B;下拉式清單中選取一個數字。
1. （選擇性）若要在事件頁面之間移動，請按一下頁面底部的&#x200B;**[!UICONTROL 前]**、**[!UICONTROL 前]**、**[!UICONTROL 後]**&#x200B;或&#x200B;**[!UICONTROL 後]**。

   當佇列只有一頁事件時，這些按鈕無法使用。

1. （選擇性）若要檢視事件的裝載，請按一下事件列中的&#x200B;**[!UICONTROL 詳細資料]**。

   詳細資訊對話方塊會開啟並顯示事件的裝載。

1. （選擇性）若要刪除事件：

   1. 執行下列任一項作業，在Select中刪除您要刪除的事件：

      * Select會勾選您要選取之每個事件旁的核取方塊。
      * Select **[!UICONTROL Select all]**&#x200B;核取方塊以選取整個佇列，而不只是目前載入的事件。 然後，您可以清除要從選取範圍中排除的任何事件的核取方塊。

   1. 在熒幕底部附近的列中，按一下&#x200B;**刪除**。

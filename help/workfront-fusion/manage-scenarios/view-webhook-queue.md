---
title: k的佇列
description: 許多服務都會提供Webhook，以便在服務發生特定變更時傳送即時通知。 即時觸發器（也稱為Webhook）可以使用這些事件開始案例。 事件在等待處理時進入webhook的佇列，例如當案例已經在執行時。 您可以檢視webhook的佇列。
author: Becky
feature: Workfront Fusion
exl-id: 04aed0cb-e837-4c81-8eb1-113075d2ada8
TQID: https://experienceleague.adobe.com/FtTjoNtYNM9kuPDMaHa4883m13pLO2MRat5ohnjXuAM
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 29%

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

若要檢視webhook的佇列：

1. 按一下左側功能表中的&#x200B;**[!UICONTROL Webhooks]**。
1. 找到您要檢視其佇列的Webhook。
1. 在「已接收事件」按鈕中找出事件數。

   ![Webhook佇列](assets/webhook-queue.png)

1. 按一下按鈕，即可檢視佇列中事件的詳細資訊。

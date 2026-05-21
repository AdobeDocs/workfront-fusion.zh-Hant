---
title: 為沒有聯結器的Web服務設定Webhook
description: 如果Web服務目前在Workfront Fusion中沒有專用聯結器，但它支援傳送Webhook，則您可以使用自訂Webhook模組作為立即觸發程式，將服務新增到情境。
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
TQID: https://experienceleague.adobe.com/Ux37ZShkz3kxnJg3Guwqvqt8TISuzV0kAVZ-kKfy0zI
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 27%

---

# 為沒有聯結器的Web服務設定Webhook

如果Web服務目前在Workfront Fusion中沒有專用聯結器，但它支援傳送Webhook，則您可以使用自訂Webhook模組作為立即觸發程式，將服務新增到情境。 此程式稱為接收webhook，並且需要在您連線的應用程式端進行一些設定。

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

## 接收webhook

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要新增webhook的情境。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 新增&#x200B;**Webhook >自訂webhook**&#x200B;模組以開始您的情境。
1. 按一下 Webhook 欄位旁的「**新增**」。
1. 在顯示的方塊中輸入&#x200B;**Webhook名稱**
1. （選用）設定webhook。

   如需指示，請參閱[Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)。

1. 按一下「**儲存**」。

1. 按一下&#x200B;**將地址複製到剪貼簿**，然後按一下&#x200B;**確定**。

1. 登入Web服務並在那裡執行下列動作：

   1. 在Web服務的「設定」區域中，建立webhook。

      特定指示取決於應用程式。 我們建議搜尋應用程式檔案中有關「建立webhook」的內容。
   1. 在步驟3中，將您複製的地址貼到剪貼簿。
   1. 選取將觸發webhook的事件。

1. 執行情境。

   當事件發生時，自訂webhook模組會觸發並且案例會執行。

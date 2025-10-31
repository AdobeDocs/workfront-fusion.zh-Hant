---
title: 為沒有聯結器的Web服務設定Webhook
description: 如果Web服務目前在Workfront Fusion中沒有專用聯結器，但它支援傳送Webhook，則您可以使用自訂Webhook模組作為立即觸發程式，將服務新增到情境。
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---

# 為沒有聯結器的Web服務設定Webhook

如果Web服務目前在Workfront Fusion中沒有專用聯結器，但它支援傳送Webhook，則您可以使用自訂Webhook模組作為立即觸發程式，將服務新增到情境。 此程式稱為接收webhook，並且需要在您連線的應用程式端進行一些設定。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

+++

## 接收webhook

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要新增webhook的情境。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 新增&#x200B;**Webhook >自訂webhook**&#x200B;模組以開始您的情境。
1. 按一下Webhook欄位旁的&#x200B;**新增**。
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

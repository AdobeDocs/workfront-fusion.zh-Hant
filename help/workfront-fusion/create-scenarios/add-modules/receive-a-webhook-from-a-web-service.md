---
title: 為沒有聯結器的Web服務設定Webhook
description: 如果Web服務目前在Workfront Fusion中沒有專用聯結器，但它支援傳送Webhook，則您可以使用自訂Webhook模組作為立即觸發程式，將服務新增到情境。
author: Becky
feature: Workfront Fusion
exl-id: 51ef13fb-2978-4927-8d5f-7d83995f11e0
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---

# 為沒有聯結器的Web服務設定Webhook

如果Web服務目前在Workfront Fusion中沒有專用聯結器，但它支援傳送Webhook，則您可以使用自訂Webhook模組作為立即觸發程式，將服務新增到情境。 此程式稱為接收webhook，並且需要在您連線的應用程式端進行一些設定。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront計畫：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

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

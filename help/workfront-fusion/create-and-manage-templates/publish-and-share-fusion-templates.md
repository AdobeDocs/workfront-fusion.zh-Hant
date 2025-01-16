---
title: Publish和共用範本
description: 建立範本時，您的範本將可供所有專案團隊成員使用。 如果您想要與團隊外部的人員共用範本，必須先發佈。
author: Becky
feature: Workfront Fusion
exl-id: 99a1227d-bff9-479f-b8b9-efcf7cea3708
source-git-commit: 7acc27ab2ce80b964b7f9fbb302816aa75964ab5
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 1%

---

# Publish和共用範本

建立範本時，您的範本將可供所有專案團隊成員使用。 如果您想要與團隊外部的人員共用範本，必須先發佈。

如需建立範本的詳細資訊，請參閱[建立新範本](/help/workfront-fusion/create-and-manage-templates/create-new-fusion-templates.md)。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 封裝</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權</td> 
   <td> <p>新增： [!UICONTROL Standard]</p><p>或</p><p>目前： [!UICONTROL Work]或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

必須先建立範本，然後才能發佈或共用。

## Publish範本

1. 在左側導覽面板中，按一下&#x200B;**[!UICONTROL Templates]**。
1. 按一下「**[!UICONTROL Team templates]**」標籤。
1. 在您要發佈的範本行中按一下&#x200B;**Publish**。

   或


   按一下您要發佈的範本名稱，然後按一下畫面右上角的&#x200B;**[!UICONTROL Publish]**&#x200B;按鈕。

## 共用[!DNL Workfront Fusion]範本

發佈範本後，即可加以共用。

1. 在左側導覽面板中，按一下&#x200B;**[!UICONTROL Templates]**。
1. 按一下「**[!UICONTROL Team templates]**」標籤。
1. 按一下您要共用的範本名稱以開啟範本。
1. 按一下&#x200B;**已發佈**&#x200B;標籤以開啟該版本的範本。
1. （視條件而定）如果您想要分享連結，請按一下&#x200B;**[!UICONTROL Share public link]**。

   >[!NOTE]
   >
   >雖然您可以共用此連結，但範本本身仍停留在[!UICONTROL Team templates]索引標籤中，且不是公開的。

1. （視條件而定）如果您希望範本成為公開範本，請按一下&#x200B;**[!UICONTROL Request Approval]**&#x200B;以傳送給您的管理員進行核准。

   >[!NOTE]
   >
   >* 在核准範本後，它就會變成公開的。 [!UICONTROL Public templates]會顯示在所有[!DNL Workfront Fusion]使用者的[!UICONTROL Public templates]標籤中，無論組織或團隊為何。
   >* 系統不會通知您的管理員收到要透過電子郵件檢閱的範本。 如果核准是緊急的，請直接聯絡管理員。


## 範本狀態

Fusion會將不同的版本（「私人」、「已發佈」和「已核准」）儲存在範本頁面的不同標籤中。

可使用下列狀態：

* **[!UICONTROL Private]**：此範本僅對範本作者及其團隊可見。
* **[!UICONTROL Published]**：此範本僅對範本作者及其團隊可見。 您可以傳送已發佈的範本以供核准，並複製分享連結。
* **[!UICONTROL Approved]**： [!UICONTROL Public templates]索引標籤中的所有Workfront Fusion使用者都可以看見此範本。 您可以按一下畫面右上角的[!UICONTROL Options]，複製分享連結。

<!--You can also check the status from the [!UICONTROL Team templates] tab. If a template is published, it will have an icon to the right of the template name.

* **Eye icon**: The template is published, it is visible only for the team, and the approval request was not sent.
* **Yellow checkmark icon**: The template is published, it is visible only for the team, and the approval request was sent.
* **Green checkmark icon**: The template is published and public. It is visible for any Workfront Fusion user in the [!UICONTROL Public templates] tab. It is also still visible in the [!UICONTROL Team templates] tab, and the template author or their team member can still edit it.

Templates without icons have [!UICONTROL Private] status. They are not published and are visible only to the team.
-->

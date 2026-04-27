---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 透過 Adobe Admin Console 將使用者新增至 Adobe Workfront Fusion
description: You can add a user to the Adobe Admin Console and assign them to Adobe Workfront Fusion, or assign an existing user in the Adobe Admin Console to Workfront Fusion.
author: Becky
feature: Workfront Fusion
exl-id: 7cb1c1a7-3c7a-459a-818f-d9cefcb9988b
source-git-commit: 6762806f17a0fc55531b647a84901b8ca572a997
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 20%

---

# 透過 Adobe Admin Console 將使用者新增至 Adobe Workfront Fusion

You can add a user to the [!DNL Adobe Admin Console] and assign them to Adobe Workfront Fusion, or assign an existing user in the [!DNL Adobe Admin Console] to Workfront Fusion.

For a video describing Workfront Fusion in the [!DNL Adobe Admin Console], including how to add users, see [[!DNL Fusion] on Adobe IMS](https://video.tv.adobe.com/v/3412464/){target=_blank}.

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定</td> 
   <td> 
     <p>您必須是組織的Workfront Fusion管理員。</p>
     <p>您必須是團隊的Workfront Fusion管理員。</p>
   </td> 
  </tr> 
  </tr>
   <tr> 
   <td role="rowheader">存取層級設定</td> 
   <td>You must be a Product Configuration Administrator of Adobe products for your organization.</td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++



## 先決條件

Before using the [!DNL Admin Console] for Workfront, you should receive a receive an email inviting you to the console.

* If you are new to [!DNL Adobe] and you have received an email telling you that you now have administer rights to manage [!DNL Adobe] software and services for your organization, click the button in the email to create an [!DNL Adobe] account and open the [!DNL Admin Console].

  或

  If you already have an Adobe account, go to the [[!DNL Adobe Admin Console] page](https://adminconsole.adobe.com).


## Add a new user to the [!DNL Adobe Admin Console] and Workfront Fusion

1. From the [[!DNL Adobe Admin Console] page](https://adminconsole.adobe.com/), select the **[!UICONTROL Products]** tab in the top navigation bar, and then select the **Workfront Fusion** product tile.

   ![Fusion in Admin Console](assets/fusion-product-admin-console.png)

1. In the list that displays, select the organization where you want to add a user.

   ![Fusion instance in Admin Console](assets/fusion-instances-admin-console.png)

1. In the list that displays, with the **[!UICONTROL Product Profiles]** tab selected, click the name of the Workfront Fusion [!UICONTROL Product Profile] link.

   >[!IMPORTANT]
   >
   > Do not make any changes to the [!UICONTROL Product Profile] itself.

1. With the **[!UICONTROL Users]** tab selected above the list, click **[!UICONTROL Add User]**.

1. In the **[!UICONTROL Add users to this product profile]** box, enter the email address or name of a user you want to add, then select the user in the list that appears.

1. 按一下「**[!UICONTROL 儲存]**」。

   The user is created in Workfront Fusion.

1. (Optional) Continue to [Change a user&#39;s access level in Workfront Fusion](#change-a-users-access-level-in-workfront-fusion).

## Change a user&#39;s access level in Workfront Fusion

* [Change a user&#39;s role to Admin](#change-a-users-role-to-admin)
* [Change a user&#39;s role to Member, Accountant, or App Developer](#change-a-users-role-to-member-accountant-or-app-developer)

### Change a user&#39;s role to Admin

Giving a user an Admin role must be done in the [!DNL Adobe Admin Console].

1. On the Workfront Fusion [!UICONTROL Product Profile] page where you added the user, select the **[!UICONTROL Admins]** tab.

1. 按一下&#x200B;**[!UICONTROL 新增管理員]**。

1. In the **[!UICONTROL Add product profile administrators]** box, enter the email address or name of the user you want to become an admin, then select the user in the list that appears.

1. 按一下「**[!UICONTROL 儲存]**」。

   The user is now an Administrator in Workfront Fusion.

### Change a user&#39;s role to Member, Accountant, or App Developer

Member, Accountant, and App Developer roles are handled inside Workfront Fusion.

For instructions, see [View or edit user roles](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md).

## Assign an existing user in the [!DNL Adobe Admin Console] to Workfront Fusion

You can add an existing user to a team in Fusion. This is handled inside Fusion.

For instructions, see [Add a user to a team](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md).

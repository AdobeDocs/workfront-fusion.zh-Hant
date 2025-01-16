---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: get-started-with-workfront-fusion-2-0
title: 透過Adobe Admin Console將使用者新增到Adobe Workfront Fusion
description: 您可以將使用者新增到Adobe Admin Console並將他們指派到Adobe Workfront Fusion，或將Adobe Admin Console中的現有使用者指派到Workfront Fusion。
author: Becky
feature: Workfront Fusion
exl-id: 7cb1c1a7-3c7a-459a-818f-d9cefcb9988b
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 1%

---

# 透過Adobe Admin Console將使用者新增到Adobe Workfront Fusion

您可以將使用者新增至[!DNL Adobe Admin Console]並將他們指派至[!DNL Adobe Workfront Fusion]，或將[!DNL Adobe Admin Console]中的現有使用者指派至[!DNL Workfront Fusion]。

如需[!DNL Adobe Admin Console]中說明[!DNL Workfront Fusion]的影片，包括如何新增使用者，請參閱Adobe IMS](https://video.tv.adobe.com/v/3412464/){target=_blank}上的[[!DNL Fusion] 。



您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td> 
   <td> <p>[!UICONTROL Pro] 或更高</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td> 
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr>
   <tr> 
   <td role="rowheader">[!DNL Adobe] 管理員許可權</td> 
   <td>您必須是組織[!DNL Adobe]項產品中的[!UICONTROL Product Configuration Administrator]項。</td> 
  </tr>
  </tbody> 
</table>

&#42;若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

&#42;&#42;如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。



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
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定*</td> 
   <td> 
     <p>您必須是組織的[!DNL Workfront Fusion]管理員。</p>
     <p>您必須是團隊的[!DNL Workfront Fusion]管理員。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++


## 先決條件

在針對[!DNL Workfront]使用[!DNL Admin Console]之前，您應該會收到一封邀請您加入主控台的電子郵件。

1. 如果您是[!DNL Adobe]的新手，並且已收到一封電子郵件，告知您現在擁有管理貴組織的[!DNL Adobe]軟體與服務的管理許可權，請按一下電子郵件中的按鈕以建立[!DNL Adobe]帳戶並開啟[!DNL Admin Console]。

   或

   如果您已有Adobe帳戶，請移至[[!DNL Adobe Admin Console] 頁面](https://adminconsole.adobe.com)。


## 新增使用者至[!DNL Adobe Admin Console]和[!DNL Workfront Fusion]

1. 從[[!DNL Adobe Admin Console] 頁面](https://adminconsole.adobe.com/)，選取頂端導覽列中的&#x200B;**[!UICONTROL Products]**&#x200B;索引標籤，然後選取&#x200B;**[!DNL Workfront Fusion]**&#x200B;產品拼貼。

   Admin Console](assets/fusion-product-admin-console.png)中的![Fusion

1. 在顯示的清單中，選取您要新增使用者的組織。

   Admin Console](assets/fusion-instances-admin-console.png)中的![Fusion執行個體

1. 在顯示的清單中，選取&#x200B;**[!UICONTROL Product Profiles]**&#x200B;索引標籤後，按一下[!DNL Workfront Fusion] [!UICONTROL Product Profile]連結的名稱。

   >[!IMPORTANT]
   >
   > 請勿變更[!UICONTROL Product Profile]本身。

1. 在清單上方選取&#x200B;**[!UICONTROL Users]**&#x200B;索引標籤後，按一下&#x200B;**[!UICONTROL Add User]**。

1. 在&#x200B;**[!UICONTROL Add users to this product profile]**&#x200B;方塊中，輸入您要新增的使用者的電子郵件地址或名稱，然後在出現的清單中選取使用者。

1. 按一下&#x200B;**[!UICONTROL Save]**。

   已在[!DNL Workfront Fusion]中建立使用者。

1. （選擇性）繼續在 [!DNL Workfront Fusion]](#change-a-users-access-level-in-workfront-fusion)中[變更使用者的存取層級

## 在Workfront Fusion中變更使用者的存取層級

* [將使用者角色變更為管理員](#change-a-users-role-to-admin)
* [將使用者的角色變更為成員、會計師或應用程式開發人員](#change-a-users-role-to-member-accountant-or-app-developer)

### 將使用者角色變更為管理員

必須在[!DNL Adobe Admin Console]中完成為使用者指定管理員角色。

1. 在您新增使用者的[!DNL Workfront Fusion] [!UICONTROL Product Profile]頁面上，選取「**[!UICONTROL Admins]**」索引標籤。

1. 按一下&#x200B;**[!UICONTROL Add Admin]**。

1. 在&#x200B;**[!UICONTROL Add product profile administrators]**&#x200B;方塊中，輸入您要成為管理員之使用者的電子郵件地址或名稱，然後在出現的清單中選取使用者。

1. 按一下&#x200B;**[!UICONTROL Save]**。

   使用者現在是[!DNL Workfront Fusion]的管理員。

### 將使用者的角色變更為成員、會計師或應用程式開發人員

成員、會計和應用程式開發人員角色在Workfront Fusion中處理。

如需指示，請參閱[檢視或編輯使用者角色](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md)。

## 將[!DNL Adobe Admin Console]中的現有使用者指派給[!DNL Workfront Fusion]

您可以在Fusion中將現有使用者新增到團隊。 這會在Fusion中處理。

如需指示，請參閱[新增使用者至團隊](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md)。

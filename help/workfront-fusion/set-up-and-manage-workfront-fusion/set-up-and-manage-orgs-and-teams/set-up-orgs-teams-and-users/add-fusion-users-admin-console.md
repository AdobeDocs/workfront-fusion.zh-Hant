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
source-git-commit: f7c1d5b1de74cc0c59e3a00938bed14b489500db
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---

# 透過Adobe Admin Console將使用者新增到Adobe Workfront Fusion

您可以將使用者新增到[!DNL Adobe Admin Console]並將他們指派到Adobe Workfront Fusion，或將[!DNL Adobe Admin Console]中的現有使用者指派到Workfront Fusion。

如需在[!DNL Adobe Admin Console]中說明Workfront Fusion的影片，包括如何新增使用者，請參閱Adobe IMS[[!DNL Fusion] 上的](https://video.tv.adobe.com/v/3412464/){target=_blank}。

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
   <td>您必須是貴組織之Adobe產品的產品設定管理員。</td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

+++



## 先決條件

在使用Workfront的[!DNL Admin Console]之前，您應該會收到一封邀請您加入主控台的電子郵件。

1. 如果您是[!DNL Adobe]的新手，並且已收到一封電子郵件，告知您現在擁有管理貴組織的[!DNL Adobe]軟體與服務的管理許可權，請按一下電子郵件中的按鈕以建立[!DNL Adobe]帳戶並開啟[!DNL Admin Console]。

   或

   如果您已有Adobe帳戶，請前往[[!DNL Adobe Admin Console] 頁面](https://adminconsole.adobe.com)。


## 新增使用者至[!DNL Adobe Admin Console]和Workfront Fusion

1. 從[[!DNL Adobe Admin Console] 頁面](https://adminconsole.adobe.com/)，選取頂端導覽列中的&#x200B;**[!UICONTROL Products]**&#x200B;索引標籤，然後選取&#x200B;**Workfront Fusion**&#x200B;產品拼貼。

   Admin Console中的![Fusion](assets/fusion-product-admin-console.png)

1. 在顯示的清單中，選取您要新增使用者的組織。

   Admin Console中的![Fusion執行個體](assets/fusion-instances-admin-console.png)

1. 在顯示的清單中，選取&#x200B;**[!UICONTROL 產品設定檔]**&#x200B;索引標籤後，按一下Workfront Fusion [!UICONTROL 產品設定檔]連結的名稱。

   >[!IMPORTANT]
   >
   > 請勿變更[!UICONTROL 產品設定檔]本身。

1. 在清單上方選取&#x200B;**[!UICONTROL 使用者]**&#x200B;索引標籤後，按一下&#x200B;**[!UICONTROL 新增使用者]**。

1. 在&#x200B;**[!UICONTROL 將使用者新增至此產品設定檔]**&#x200B;方塊中，輸入您要新增使用者的電子郵件地址或名稱，然後在出現的清單中選取使用者。

1. 按一下「**[!UICONTROL 儲存]**」。

   使用者是在Workfront Fusion中建立。

1. （選用）繼續在Workfront Fusion[中](#change-a-users-access-level-in-workfront-fusion)變更使用者的存取層級

## 在Workfront Fusion中變更使用者的存取層級

* [將使用者角色變更為管理員](#change-a-users-role-to-admin)
* [將使用者的角色變更為成員、會計師或應用程式開發人員](#change-a-users-role-to-member-accountant-or-app-developer)

### 將使用者角色變更為管理員

必須在[!DNL Adobe Admin Console]中完成為使用者指定管理員角色。

1. 在您新增使用者的Workfront Fusion [!UICONTROL 產品設定檔]頁面上，選取「**[!UICONTROL 管理員]**」標籤。

1. 按一下&#x200B;**[!UICONTROL 新增管理員]**。

1. 在&#x200B;**[!UICONTROL 新增產品設定檔管理員]**&#x200B;方塊中，輸入您要成為管理員之使用者的電子郵件地址或名稱，然後在顯示的清單中選取使用者。

1. 按一下「**[!UICONTROL 儲存]**」。

   使用者現在是Workfront Fusion的管理員。

### 將使用者的角色變更為成員、會計師或應用程式開發人員

成員、會計和應用程式開發人員角色在Workfront Fusion中處理。

如需指示，請參閱[檢視或編輯使用者角色](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md)。

## 將[!DNL Adobe Admin Console]中的現有使用者指派給Workfront Fusion

您可以在Fusion中將現有使用者新增到團隊。 這會在Fusion中處理。

如需指示，請參閱[新增使用者至團隊](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md)。

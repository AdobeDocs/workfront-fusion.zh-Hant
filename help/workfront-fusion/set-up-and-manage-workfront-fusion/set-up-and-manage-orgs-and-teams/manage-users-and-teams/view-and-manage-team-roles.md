---
title: 檢視及管理專案團隊角色
description: 每個團隊都有一個「角色」標籤，您可以在其中檢視團隊的角色、建立您自己的角色、選擇每個角色包含的許可權，以及更新或刪除角色。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: a3a6922afd713cd002cdf472c7ef62c1855b80d9
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 9%
---
# 檢視及管理專案團隊角色

您可以檢視專案團隊中可用的角色、建立您自己的角色，以及選擇每個角色包含哪些許可權。 您也可以更新和刪除角色。

自訂角色提供下列優點：

* 每個團隊成員只能存取其工作所需的存取權，這降低了關鍵案例意外變更的風險。
* 自訂角色可更符合您組織的運作方式，而不是將您的團隊配合預先定義的角色。
* 您可以自行管理存取權，無需連絡支援人員。

如需組織、專案團隊及預先定義專案團隊角色的概觀，請參閱[組織和專案團隊概觀](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/org-and-team-overview.md)。 有關預先定義角色中包含的許可權，請參閱[組織和團隊角色](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)。

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定</td> 
   <td> 
     <p>您必須在團隊中擁有<b>[!UICONTROL 管理成員]</b>許可權。 在預先定義的角色中，此許可權包含在「專案團隊管理員」和「組織擁有者」角色中。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 誰可以管理專案團隊角色

任何在團隊中擁有&#x200B;**[!UICONTROL 管理成員]**&#x200B;許可權的人都可以建立、更新、刪除使用者並將其指派給該團隊中的角色。

* 組織擁有者可以在所有團隊中建立和管理角色。
* 組織管理員只能管理其所屬團隊中的角色，且具有&#x200B;**[!UICONTROL 管理成員]**&#x200B;許可權的角色。
* 團隊管理員可以管理其團隊中的角色。

## 建立或編輯角色

1. 在Fusion的左側導覽器中，按一下&#x200B;**團隊概觀**。
1. （視條件而定）如果您不在您要檢視角色之團隊的頁面上，請按一下頁面頂端附近的&#x200B;**團隊**&#x200B;下拉式清單，然後選取正確的團隊。
1. 開啟&#x200B;**[!UICONTROL 角色]**&#x200B;標籤。

   標籤會列出專案團隊中可用的角色，包括預先定義的角色。 對於每個角色，清單會顯示角色名稱及其許可權的摘要，例如「無許可權」、「成員」或「自訂· 19許可權」。

1. 若要建立角色，請按一下[建立角色]。**&#x200B;**

   或

   若要編輯角色，請在要編輯的角色列按一下&#x200B;**[!UICONTROL 編輯]**。

   <!-- BECKY CHECK ME: The Edit button is available for the predefined roles as well as custom roles. Confirm the title of the edit page, whether you can rename the predefined roles, and what happens to users who already have the role. -->

1. 在&#x200B;**[!UICONTROL 角色名稱]**&#x200B;欄位中輸入角色名稱。
1. 在&#x200B;**[!UICONTROL 角色範本]**&#x200B;下拉式清單中，選取您要從哪個範本開始。

   範本會設定角色的初始許可權。 預設範本為&#x200B;**[!UICONTROL 檢視器]**。

1. 在&#x200B;**[!UICONTROL 設定範圍的許可權]**&#x200B;區域中，選取您希望角色包含的許可權。

   許可權會依區域分組，例如&#x200B;**[!UICONTROL 自動化]**、**[!UICONTROL 連線]**&#x200B;和&#x200B;**[!UICONTROL 團隊]**。 您可以對每個區域執行下列任一項作業：

   * 若要一次設定某個區域中的所有許可權，請按一下區域名稱旁的&#x200B;**[!UICONTROL 無存取權]**、**[!UICONTROL 僅檢視]**&#x200B;或&#x200B;**[!UICONTROL 完整存取權]**。
   * 若要選擇特定許可權，請選取或清除每個許可權的核取方塊。

   如需許可權清單，請參閱本文章中可包含在角色[&#128279;](#permissions-that-you-can-include-in-a-role)中的許可權。

   <!-- BECKY CHECK ME: Confirm the options in the Role template dropdown and what each one selects. Confirm exactly what No access, View only, and Full access select in each area (in the screenshot, View only selects the view permissions). Confirm whether there is a Description field, and whether there are areas below Team on the page (the screenshots end at Team). -->

1. 按一下「**[!UICONTROL 儲存]**」。 若要關閉頁面而不儲存，請按一下[取消]。**&#x200B;**
1. （選擇性）若要刪除角色，請在&#x200B;**[!UICONTROL 角色]**&#x200B;索引標籤上的角色列中按一下&#x200B;**[!UICONTROL 刪除]**。

   <!-- BECKY CHECK ME: Confirm why the Delete button is unavailable (dimmed) for some roles, such as Team Operator, Team Member, and Team Admin in the screenshot, whether there is a confirmation prompt, and what happens to users who have the role. Update this step and add a note, if needed. -->

您建立的角色可在專案團隊中使用。 您可以將其指派給專案團隊成員。

### 您可以包含在角色中的許可權

<table style="table-layout:auto">
 <col>
 <col>
 <thead>
  <tr>
   <th>區域</th>
   <th>權限</th>
  </tr>
 </thead>
 <tbody>
 <tr>
   <td role="rowheader">[!UICONTROL Automations]</td>
   <td>檢視清單、檢視詳細資訊、檢視執行歷史記錄、管理通知、重設統計資料、執行一次、編輯排程、啟用、停用、建立、編輯、發佈、刪除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL 未完成的執行]</td>
   <td>檢視，管理</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Webhooks]</td>
   <td>檢視、檢視佇列、建立、編輯、管理佇列、變更優先順序、刪除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL Connections]</td>
   <td>檢視、建立、編輯、刪除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL 鍵]</td>
   <td>檢視、建立、編輯、刪除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL 資料存放區]</td>
   <td>檢視清單，瀏覽記錄，建立，編輯，刪除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL 資料結構]</td>
   <td>檢視、建立、編輯、刪除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL 範本]</td>
   <td>檢視清單、檢視詳細資訊、建立、編輯、刪除</td>
  </tr>
 <tr>
   <td role="rowheader">[!UICONTROL 團隊]</td>
   <td>檢視團隊、編輯團隊設定、管理成員、刪除團隊</td>
  </tr>
 </tbody>
</table>

<!-- BECKY CHECK ME: Confirm that this list is complete, and add a description of what each permission allows, if needed. The list is taken from the Create role page, which may have more areas below Team. -->

## 將角色複製至其他團隊

您可以將一個專案團隊中的角色複製到另一個專案團隊，這樣您就不必在每個專案團隊中重新建立相同的角色。

1. 開啟團隊的&#x200B;**[!UICONTROL 角色]**&#x200B;標籤，如本文中[建立或編輯角色](#create-or-edit-a-role)中所述。
1. 按一下「**[!UICONTROL 複製至群組]**」。

   「**[!UICONTROL 複製角色至其他團隊]**」頁面隨即開啟。

1. 在&#x200B;**[!UICONTROL 目標團隊]**&#x200B;下拉式清單中，選取您要複製角色的團隊。

   此時會出現一個列出目前專案團隊中角色的表格。

1. 針對表格中的每個角色，複查並設定下列專案：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Source role]</td> 
      <td> <p>目前團隊中的角色及其許可權摘要。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 動作]</td> 
      <td> <p>如何處理角色。 例如，<b>[!UICONTROL Copy to existing role]</b>會將來源角色的許可權複製到目標團隊中已存在的角色中。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 目標]</td> 
      <td> <p>來源角色複製到的目標團隊中的角色。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 變更]</td> 
      <td> <p>目標角色是否與來源角色不同。 例如，<b>[!UICONTROL 已經在sync]</b>中，表示目標角色已經擁有與來源角色相同的許可權。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 使用者]</td> 
      <td> <p>擁有角色之使用者的相關資訊。 例如，<b>[!UICONTROL 沒有相符的使用者]</b>表示沒有可包含的使用者。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 狀態]</td> 
      <td> <p>複製後角色的結果。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL 複製]**。 若要關閉頁面而不複製，請按一下[取消]。**&#x200B;**

<!-- BECKY CHECK ME: The screenshot shows the Clone roles to another team page after a target team is selected. Confirm the options in the Action dropdown (for example, whether you can create a new role in the target team), the options in the Target dropdown, what the checkbox in the Users column does (for example, whether it also assigns the role to matching users in the target team) and what "matching users" means, what the Changes column shows when the roles differ, and what the Status column shows before and after you clone. -->

<!-- BECKY CHECK ME: Confirm whether the Target team dropdown lists all teams or only the teams that you can manage, and whether the Clone to team button is visible to everyone who can manage roles. -->

## 指派角色給使用者

指派自訂角色的方式與指派預先定義角色的方式相同。 如需指示，請參閱[新增使用者至團隊](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-a-user-to-a-team.md)和[檢視或編輯使用者角色](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-or-edit-user-roles.md#view-or-edit-user-roles-for-a-team)。

<!-- BECKY CHECK ME: Confirm that custom roles appear in the role dropdowns in both of these procedures. -->

## 考量事項

* 組織許可權重疊顯示。 若要授予某人存取權以在所有專案團隊中執行動作，請指派組織角色，而非建立專案團隊角色。 如需詳細資訊，請參閱[組織和團隊角色](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)。
* 您建立的角色屬於一個團隊。

<!-- BECKY CHECK ME: The Slack thread says that defining a role that is available in all teams was out of scope for the initial release. Confirm that a role belongs to a single team, and that you clone it to use it in another team. -->

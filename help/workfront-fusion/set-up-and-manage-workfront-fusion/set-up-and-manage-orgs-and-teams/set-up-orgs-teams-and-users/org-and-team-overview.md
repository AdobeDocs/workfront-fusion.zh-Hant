---
title: Fusion組織和團隊概觀
description: Adobe Workfront Fusion的「組織」和「團隊」功能可讓企業控制Fusion中情境和其他功能的存取權。
author: Becky
feature: Workfront Fusion
exl-id: 44e6de2a-b2d3-410d-abc3-10facd258495
TQID: 'https://experienceleague.adobe.com/rWg9TitUlX092UIFTY1LUZsR7UlmWwE5dItl6wnlBMA'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: f9cdbcf936fc6b022f6513f47b9b377424731419
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%
---
# Adobe Workfront Fusion組織和團隊概觀

Adobe Workfront Fusion的「組織」和「團隊」功能可讓企業控制Fusion中情境和其他功能的存取權。

組織是Adobe Workfront Fusion中最大的實體。 例如，您的Fusion組織可能代表您整個公司的Fusion帳戶。

專案團隊是組織內的小型群組，可共用Fusion資源，例如情境、連線和範本。

如需建立團隊的指示，請參閱[建立團隊](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/create-a-team.md)。

## 組織

Workfront Fusion使用者屬於組織。

必須先將使用者新增至組織，才能將其新增至團隊。

### 組織資源

下列資源會影響整個Fusion組織，因此會在組織層級上擁有與處理：

* **背景工作集區：**：背景工作集區是專用於特定組織的Workfront Fusion處理資源數量。

  如需詳細資訊，請參閱[背景工作集區](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/worker-pools.md)。

* **作業**： Adobe Workfront Fusion中的作業是由模組執行的工作。

  如需詳細資訊，請參閱[作業](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md)。

### 組織角色

使用者在組織中擁有下列其中一種角色：

* **[!UICONTROL 所有者]**：所有者擁有組織中可用的所有許可權。
* **[!UICONTROL 管理員]**：如果組織已啟用Adobe Admin Console Identity Management System (IMS)，管理員可以在Adobe上管理使用者，也可以邀請新使用者加入未使用IMS的組織。 他們也可以核准範本。
* **[!UICONTROL 成員]**：成員可以使用Workfront Fusion，但無法進行組織變更。
* **[!UICONTROL 會計]**：會計可以在組織儀表板上看到授權資訊，但無法執行任何動作。
* **[!UICONTROL 應用程式開發人員]**：此角色的功能目前無法使用，而且將在不久的將來提供。 我們目前不建議將使用者指派給此角色。

如需每個組織角色中使用者可用的特定動作資訊，請參閱[組織和團隊角色](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)。

## 團隊

團隊是共用特定資源存取許可權的使用者群組。 這些資源可能包括：

* 情境
* 連線
* Webhook
* 金鑰
* 資料存放庫
* 資料結構
* 電子郵件通知設定

>[!NOTE]
>
>由於專案團隊會共用資源，因此有時專案團隊僅有一個成員會很有用。 例如，訓練中的使用者可以建立與其個別Workfront帳戶的連線。 任何團隊成員都可以連線至個別Workfront帳戶。 在此情況下，我們建議使用者成為培訓團隊的唯一成員。

組織可以擁有任意所需數量的團隊，使用者可以屬於一個或多個團隊。

使用者可從左側導覽面板的下拉式清單中選取其團隊。 使用者只會看到他們所屬的團隊。 選取團隊將允許使用者存取該團隊的資源。

### 團隊角色

使用者在其每個團隊中具有以下角色之一：

* **[!UICONTROL 團隊管理員]**：管理員可以新增、移除或變更團隊成員的角色。 他們也可以執行其他專案團隊角色可用的任何動作。
* **[!UICONTROL 團隊成員]**：團隊成員角色可讓使用者建立和執行案例。
* **[!UICONTROL 團隊監控]**： [!UICONTROL 監控]角色可讓使用者存取案例的執行資訊，但他們無法設計案例或變更其「作用中」狀態。
* **[!UICONTROL 團隊運運算元]**： [!UICONTROL 運運算元]角色可讓使用者檢視執行資料，並變更案例的「作用中」狀態。
* **[!UICONTROL 團隊受限制成員]**：此角色的功能目前無法使用，而且將在不久的將來提供。 我們目前不建議將使用者指派給此角色。

如需每個專案團隊角色中使用者可用的特定動作資訊，請參閱[組織和專案團隊角色](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)。

### 自訂團隊角色

<!-- BECKY CHECK ME: The source material (the Slack announcement) says flexible permissions are live in QA and for internal customers, with a limited pilot with paid customers next, then general availability. Confirm availability at the 2026-11-12 release before publishing, and whether this section should say that the feature is available only to some organizations. -->

除了預先定義的專案團隊角色之外，每個專案團隊都有&#x200B;**[!UICONTROL 角色]**&#x200B;標籤，您可以在其中建立自己的角色。 您可以建立、更新及刪除角色，並選擇每個角色包含的確切許可權。 您不再受限於固定角色集。

如需指示，請參閱[檢視及管理團隊角色](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/manage-users-and-teams/view-and-manage-team-roles.md)。

使用自訂角色，您可以：

* 僅給予每個人其工作所需的存取權，以降低關鍵案例意外變更的風險。
* 設定存取權以符合您組織的運作方式，而不是將您的團隊配合預先定義的角色。
* 自行管理存取權，無需連絡支援人員。

任何在團隊中擁有&#x200B;**[!UICONTROL 管理成員]**&#x200B;許可權的人都可以建立、更新、刪除使用者並將其指派給該團隊中的角色。 在預先定義的角色中，此許可權包含在「專案團隊管理員」和「組織擁有者」角色中。

* 組織擁有者可以在所有團隊中建立和管理角色。
* 組織管理員只能管理其所屬團隊中的角色，且具有&#x200B;**[!UICONTROL 管理成員]**&#x200B;許可權的角色。
* 團隊管理員可以管理其團隊中的角色。

<!-- BECKY CHECK ME: The source does not describe the steps in the Roles tab, the list of permissions that you can choose from, or whether you can edit or delete the predefined roles. Add the steps and permissions list once confirmed. Also confirm that Team Admins can manage roles (the source says the Manage members permission was previously given to Team Admin and Org Owner roles, and that team and org admins can create roles only in the teams where they are admins). -->

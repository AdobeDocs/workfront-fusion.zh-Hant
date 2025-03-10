---
title: Fusion組織和團隊概觀
description: Adobe Workfront Fusion的「組織」和「團隊」功能可讓企業控制Fusion中情境和其他功能的存取權。
author: Becky
feature: Workfront Fusion
exl-id: 44e6de2a-b2d3-410d-abc3-10facd258495
source-git-commit: d76f199b766d6f18e371f2ce1107a96529afbfd1
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 1%

---

# [!DNL Adobe Workfront Fusion]組織和團隊概觀

[!DNL Adobe Workfront Fusion]的組織與團隊功能可讓企業控制Fusion中案例與其他功能的存取權。

組織是Adobe Workfront Fusion中最大的實體。 例如，您的Fusion組織可能代表您整個公司的Fusion帳戶。

專案團隊是組織內的小型群組，可共用Fusion資源，例如情境、連線和範本。

如需建立團隊的指示，請參閱[建立團隊](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/create-a-team.md)。

## 組織

[!DNL Workfront Fusion]個使用者屬於某個組織。

必須先將使用者新增至組織，才能將其新增至團隊。

### 組織角色

使用者在組織中擁有下列其中一種角色：

* **[!UICONTROL 所有者]**：所有者擁有組織中可用的所有許可權。
* **[!UICONTROL 管理員]**：管理員可以建立和管理組織的團隊和使用者，也可以核准範本。
* **[!UICONTROL 成員]**：成員可以使用[!DNL Workfront Fusion]，但無法進行組織變更。
* **[!UICONTROL 會計]**：會計可以在組織儀表板上看到授權資訊，但無法執行任何動作。
* **[!UICONTROL 應用程式開發人員]**：此角色的功能目前無法使用，而且將在不久的將來提供。 我們目前不建議將使用者指派給此角色。

如需每個組織角色中使用者可用的特定動作資訊，請參閱[組織和團隊角色](/help/workfront-fusion/references/licenses-and-roles/organization-roles.md)。

## 團隊

團隊是共用特定資源存取許可權的使用者群組。 這些資源可能包括：

* 情境
* 連線
* Webhook
* 金鑰
* 資料儲存區
* 資料結構
* 電子郵件通知設定

>[!NOTE]
>
>由於專案團隊會共用資源，因此有時專案團隊僅有一個成員會很有用。 例如，訓練中的使用者可以建立與其個別[!DNL Workfront]帳戶的連線。 任何團隊成員也可以連線至個別[!DNL Workfront]帳戶。 在此情況下，我們建議使用者成為培訓團隊的唯一成員。

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

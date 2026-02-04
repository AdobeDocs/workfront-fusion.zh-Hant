---
title: 導覽 Workfront Fusion
description: 開啟 Fusion 時，您有許多動作選項。這篇文章可協助您了解如何利用那些選項。
author: Becky
feature: Workfront Fusion
exl-id: 427ec131-d68d-4401-b620-998d3d5162da
source-git-commit: 05c75c0e125a4f3f657049d7e57bbc94cc5e4d67
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 100%

---

# 導覽 Adobe Workfront Fusion

您可以使用左側的導覽面板來導覽 Adobe Workfront Fusion 的不同區域。您可以在這裡找到 Fusion 的所有主要區域，並可以快速從一個區域移動到另一個區域。

這篇文章會介紹這些區域，並提供詳細介紹每個區域的連結。

| 區域 | 說明 | 如需詳細資訊，請參閱 |
| --- | --- | --- |
| 組織概觀<br> ![組織圖示](assets/org-icon.png) | 在這裡可以看到關於您的 Fusion 組織的資訊。您可以檢視此組織中由情境執行的作業數量，以及使用中情境的清單。您也可以檢視此組織的團隊、使用者和環境的清單。<br>目前選取的組織會顯示在此圖示上方。 | [組織與團隊](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/org-and-team-overview.md) |
| 團隊概觀<br> ![團隊圖示](assets/team-icon.png) | 在這裡，您可以看到關於 Fusion 團隊的資訊，例如此團隊中由情境執行的作業數量，以及使用中情境的清單。您也可以檢視及管理此團隊的使用者。檢視團隊時，您可以從本頁面頂端的下拉式選單中選取不同的團隊。<br>目前選取的團隊會顯示在此圖示上方。<br>您可能需要先建立團隊，才能看到團隊概觀或這篇文章列出的任何團隊區段。 | [組織與團隊](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/org-and-team-overview.md) |
| 情境<br> ![情境圖示](assets/scenarios-icon.png) | Fusion 中的情境代表自動化的工作流程。例如，一個情境可以監視傳入的 Workfront 請求並將其轉換成專案，而另一個情境可以產生影像、將影像上傳給文件提供者，以及將核准任務新增至 Workfront。您在 Fusion 中的大部分工作是設定和管理各個情境。在「情境」區域中，您可以檢視及組織團隊的情境清單、選取個別情境進行檢視或修改，或者開始建立新情境。 | [情境概觀](/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md) |
| 範本<br> ![範本圖示](assets/templates-icon.png) | 範本是預先建立的情境，而您可以針對自己的使用案例進行設定。在這裡，您可以看到 Workfront Fusion 提供的公開情境，以及您的團隊建立的範本。 | [建立和管理範本：文章索引](/help/workfront-fusion/create-and-manage-templates/create-manage-templates-toc.md) |
| 連線<br> ![連線圖示](assets/connections-icon.png) | 連線包含讓 Fusion 能夠與其他應用程式互動的登入認證和權限。您可以使用特定應用程式的一組特定的認證和權限來建立連線，然後在您的情境中使用該連線。接著，情境可以存取和修改記錄或是擁有那些認證和權限之使用者可用的其他資料。您可以為一個應用程式建立多個連線，並可以在多個情境中使用一個連線。在「連線」區域中，您可以檢視和管理由您的團隊設定的連線清單。 | [連線概觀](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md) |
| Webhook<br> ![Webhook 圖示](assets/webhooks-icon.png) | Webhook 會監視應用程式是否有變更，然後根據該變更啟動一個情境。例如，您可以設定 Webhook 在問題提交至特定 Workfront 專案時啟動一個情境。在 Webhook 區域中，您可以看到由您的團隊設定的 Webhook 清單，及使用這些 Webhook 的情境。 | [即時觸發程序 (Webhook)](/help/workfront-fusion/references/modules/webhooks-reference.md) |
| 金鑰<br> ![金鑰圖示](assets/keys-icon.png) | 我們使用公開和私密金鑰來加密和解密資料。公開金鑰可以分發，任何擁有公開金鑰的人都能加密資料，但只有私密金鑰能夠將資料解密。同樣地，擁有私密金鑰的使用者可以加密資料，而任何擁有公開金鑰者都能將其加密的資料解密。在「金鑰」區域中，您可以檢視和管理您的團隊擁有的金鑰。 | [金鑰](/help/workfront-fusion/references/modules/keys.md) |
| 資料存放庫<br> ![資料存放庫圖示](assets/data-store-icon.png) | 資料存放庫是存在於情境以外的小型資料庫。您可以利用資料存放庫在不同情境之間，或在某個情境的個別執行之間轉移資料。在「資料存放庫」區域中，您可以檢視和管理您團隊擁有的資料存放庫。 | [資料存放庫](/help/workfront-fusion/create-scenarios/map-data/data-stores.md) |
| 資料結構<br> ![資料結構圖示](assets/data-structure-icon.png) | 資料結構說明傳輸至 Fusion 的資料之格式，通常用於序列化或剖析 JSON、XML 和 CSV 等格式。在「資料結構」中，您可以檢視和管理您的團隊擁有的資料結構。 | [資料結構](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md) |

>[!NOTE]
>
>「團隊」標題下的所有區域皆由個別團隊所擁有。若要檢視屬於不同團隊的頁面 (例如不同團隊的「情境」頁面)，請按一下頁面頂端附近的「團隊」下拉式選單，然後選取不同的團隊。


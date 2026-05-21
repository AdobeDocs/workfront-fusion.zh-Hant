---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: connections-annd-webhooks
title: 管理連線
description: 大部分的應用程式都必須建立連線，以便 Adobe Workfront Fusion 能夠透過連線，根據特定情境的設定，與指定的第三方服務進行通訊。
author: Becky
feature: Workfront Fusion
exl-id: 26d7caad-8e12-4f04-ac7c-f71686c90ee6
TQID: https://experienceleague.adobe.com/P-zEd2tJCk9-uzE1xW6COpTCdFJiIq4NwGRLDdpCSVU
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 586
ht-degree: 28%

---

# 管理連線

連線代表 Fusion 用於存取應用程式的授權和權限。 您可以為每個應用程式建立一或多個連線，並可以在多個模組或案例中使用相同的連線。

您可以在「連線」區域中管理這些連線。

如需連線的詳細資訊，請參閱[連線總覽](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md)。

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
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>聯結器型（舊版）：若要連線至Workfront產品系列以外的應用程式，您必須使用Workfront Fusion進行工作自動化和整合 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 檢視和管理連線

您可以從「連線」區域管理所有連線。

>[!NOTE]
>
>連線的擁有者為團隊。 如果您找不到要尋找的連線，請檢查您檢視的群組是否正確。
>
>若要選取新專案團隊，請按一下左側導覽中的專案團隊名稱，然後選取新專案團隊。

1. 若要開啟[連線]區域，請按一下左側導覽中的&#x200B;**連線** ![連線圖示](assets/connections-icon.png)。
1. 找到您要管理的連線，然後在該連線的行中執行以下一個或多個步驟。
1. （選擇性）按一下&#x200B;**環境**&#x200B;和&#x200B;**型別**&#x200B;下拉式清單，並選取選項，以指派環境和連線型別。
1. （選擇性）若要檢視授予Workfront Fusion的連線許可權，請按一下[檢視]圖示![[檢視該連線的連線許可權](assets/view-connection-permissions.png)。
1. （選擇性）若要重新命名連線，請反白連線名稱並輸入新名稱。
1. （選擇性）若要重新授權連線，請核取連線旁的核取方塊，然後按一下畫面底部附近的&#x200B;**重新授權**。
1. （選擇性）若要刪除連線，請核取連線旁的核取方塊，按一下畫面底部附近的&#x200B;**[刪除]**，然後按一下&#x200B;**[確定？**]。
1. （選擇性）若要確認與服務的連線已順利建立，請核取連線旁的核取方塊，然後按一下畫面底部附近的&#x200B;**驗證**。
1. （選擇性）若要檢視使用此連線的使用中案例，請核取連線旁的核取方塊，然後按一下&#x200B;**擷取使用中案例**。 接著，您可以按一下「作用中案例」清單中的案例，移至該案例。

## 更新連線

Workfront Fusion通常會在無限制的時段內取得特定服務的存取權。 某些應用程式需要在一段時間後更新存取許可權。 在這種情況下，Workfront Fusion會在存取權到期前不久，透過電子郵件通知您。

若要更新連線：

1. 若要開啟[連線]區域，請按一下左側導覽中的&#x200B;**連線** ![連線圖示](assets/connections-icon.png)。
1. 找到您要更新的連線。
1. 在該連線的行中，核取連線旁的核取方塊，然後按一下畫面底部附近的&#x200B;**重新授權**。

## 資源

* 如需連線中繼資料的詳細資訊，例如環境和型別，請參閱[連線中繼資料](/help/workfront-fusion/references/connections/connection-metadata.md)。

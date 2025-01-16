---
content-type: reference
title: 核准或不核准範本
description: 本文會說明如何核准或不核准Fusion範本。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: dafecd8b-96e5-46da-9ab6-15f0bc9b52a4
source-git-commit: 23e9f383b25c7b3789c413e557b94418e48a636b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%

---

# 核准或不核准公用索引標籤的範本

Adobe Workfront Fusion範本是預先建立的情境，旨在自動化和簡化各種工作流程。 這些範本可協助使用者快速設定整合和自動化，而不需要從頭開始建立所有內容。

如果您是管理員，則可以在「公用範本」標籤上選擇是否要與整個組織共用特定範本。

使用者可以傳送他們建立以供核准的範本，以便在「公用範本」頁面上共用。<!--do the have to be requested or can an admin just choose to approve?-->

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
  <col>
  <col>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] 計劃</td>
      <td><p>任何</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">[!DNL Adobe Workfront] 授權</td>
      <td><p>新增： [!UICONTROL Standard]</p><p>或</p><p>目前： [!UICONTROL Work]或更高</p></td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td>
      <td>
        <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
        <p>或</p>
        <p>舊版：任何</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">產品</td>
      <td>
        <p>新增：</p>
        <ul>
          <li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li>
          <li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li>
        </ul>
        <p>或</p>
        <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on [!DNL Adobe Workfront Fusion] licenses, see [[!DNL Adobe Workfront Fusion] licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md).-->

+++

## 核准或不核准[!DNL Workfront Fusion]範本

核准範本後，範本便會顯示在[!UICONTROL Public templates]標籤中，且可供所有使用者使用。

不核准範本會將其從[!UICONTROL Public templates]索引標籤中移除，並僅供建立該範本的團隊使用。

1. 按一下左側導覽面板中的&#x200B;**[!UICONTROL Administration]**&#x200B;以開啟[!UICONTROL Administration]區域。
1. 按一下左側導覽面板中的&#x200B;**[!UICONTROL Templates]**。
1. 若要核准範本，請按一下範本右側的&#x200B;**[!UICONTROL Approve]**。
1. 如果您要取消核准範本，請按一下範本右側的&#x200B;**[!UICONTROL Disapprove]**。

>[!NOTE]
>
>如果您核准先前已核准然後編輯的範本，則您的第二次核准將會覆寫原始範本。


## 範本狀態

您可以在範本名稱下方檢查範本頁面上的狀態。

可使用下列狀態：

* **[!UICONTROL Private]**：此範本僅對範本作者及其團隊可見。
* **[!UICONTROL Published]**：此範本僅對範本作者及其團隊可見。 發佈後，您可以視需要傳送範本以供核准。 您也可以複製分享連結。
* **[!UICONTROL Approved]**： [!UICONTROL Public templates]索引標籤中的所有Workfront Fusion使用者都可以看見此範本。 您也可以按一下熒幕右上角的[!UICONTROL Options]，複製分享連結。

您也可以從[!UICONTROL Team templates]索引標籤檢查狀態。 如果範本已發佈，其範本名稱右側會出現圖示。

* **眼睛圖示**：範本已發佈；僅團隊能看見；未傳送核准要求。
* **黃色核取記號圖示**：範本已發佈；它僅對團隊可見；它正在等候核准以新增至公用範本索引標籤。
* **綠色核取記號圖示**：此範本可在「公用範本」標籤中使用，且任何Workfront Fusion使用者都可以看到。 [!UICONTROL Team templates]索引標籤中仍會顯示它。 範本作者或其團隊成員仍可編輯它。

沒有圖示的範本有[!UICONTROL Private]狀態。 它們不會發佈，僅對團隊可見。


<!--

## Questions about how this works

Editing

1. If an admin edits a template, do they have to publish again? ... Do they have to approve again?
1. What does publishing actually do?
1. Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
1. What is the admin approving? Does a user have to submit it for approval? 



What does "Publishing" mean?
What does "Approving" mean?
If an admin edits a template, do they have to publish again? ... Do they have to approve again?
Does a user have to submit for approval to share on the Public tab or can admin go through and approve/reject which ones they want? 
What is the admin approving? Does a user have to submit it for approval?

-->

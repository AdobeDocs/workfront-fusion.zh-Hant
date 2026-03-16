---
title: 管理貴組織中的Adobe Workfront Fusion使用者
description: 管理貴組織中的Adobe Workfront Fusion使用者
author: Becky
feature: Workfront Fusion
exl-id: 32c221fa-856b-4921-9fa6-5e60f2aa08cd
source-git-commit: 3f9390d8947ef2666336c1a4cc6eab8d174849d5
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 18%

---

# 檢視或編輯使用者角色

Adobe Workfront Fusion管理員可以在Workfront Fusion中管理使用者角色。


>[!NOTE]
>
>如果您的組織目前正在移至Adobe Admin Console，您無法在Workfront中管理使用者（新增或刪除使用者）。 完成移轉後，您就可以在Adobe Admin Console中執行這些動作。

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
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 檢視或編輯組織的使用者角色

Adobe Workfront Fusion管理員可以檢視和更新組織的使用者角色。

1. 以Workfront Fusion管理員身分登入時，在左側導覽中選取&#x200B;**[!UICONTROL 所有使用者]**。
1. 在您要檢視的使用者列中，按一下&#x200B;**[!UICONTROL 詳細資料]**。
1. （選擇性）若要更新組織中使用者的角色，請在您要變更使用者角色的組織列中，按一下&#x200B;**[!DNL Role]**&#x200B;欄中的下拉式清單，然後選取新角色。

### 新增或變更組織擁有者時的注意事項

您的組織可以有多個擁有者。

將使用者指派給擁有者角色或從擁有者角色指派使用者時，請考慮下列事項。

* 只有擁有者才能指派擁有者角色，或指派其他角色給目前擁有者。
* 只有管理員可以升級為擁有者。
* 如果只有一個擁有者，則無法變更或移除該擁有者角色。
* 如果只有一個擁有者，則當組織中有其他使用者時，無法刪除該擁有者。
* 當管理員被指派所有者角色時，他們會自動成為組織內所有團隊的管理員。
* 當所有者指派給另一個角色時，該使用者會自動成為所有團隊中的團隊成員。
* 建立新團隊時，所有擁有者都會自動指派為團隊管理員。

## 檢視或編輯團隊的使用者角色

Adobe Workfront Fusion管理員和團隊管理員可以檢視和更新使用者角色。

1. 以Workfront Fusion管理員身分登入時，在左側導覽中選取&#x200B;**[!UICONTROL 所有使用者]**。
1. 在您要檢視的使用者列中，按一下&#x200B;**[!UICONTROL 詳細資料]**。
1. 在包含您要檢視或編輯使用者角色的團隊的組織列中，**[!DNL Role]**&#x200B;欄中的「團隊」圖示按一下。
1. （可選）若要更新團隊中使用者的角色，請在您要變更使用者角色的團隊列，按一下&#x200B;**[!DNL Role]**&#x200B;欄中的下拉式清單，然後選取新角色。

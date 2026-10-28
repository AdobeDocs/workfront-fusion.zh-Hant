---
title: 儲存並重複使用包含程式碼片段的案例區段
description: 程式碼片段是一組您儲存的模組，以便在其他案例中重複使用。 您可以組織、共用、匯入及匯出程式碼片段。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
source-git-commit: 5b049973107f23e46d1aadae8e0d157839e8a7f3
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 15%
---

# 儲存並重複使用包含程式碼片段的案例區段

>[!NOTE]
>
>此功能僅在新的案例編輯器體驗中可用。 如需詳細資訊，請參閱文章「情境編輯器」中的[新體驗和傳統體驗](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)。

程式碼片段是您儲存為單位的模組群組。 您可以將程式碼片段新增至其他情境，如此一來，您就不必多次建立情境的相同區段。

您可以使用「程式碼片段」面板來搜尋、標籤、預覽、釘選及排序程式碼片段；將其拖放到情境中；將其匯入及匯出；並與團隊或組織共用，或將副本傳送給其他使用者。

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
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 建立程式碼片段

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取包含您要儲存之模組的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. Shift +按一下您要納入程式碼片段中的任何模組。
1. 以滑鼠右鍵按一下其中一個選取的模組，然後選取建立代碼片段。
1. 輸入程式碼片段名稱。
1. 按一下&#x200B;**儲存**

## 將程式碼片段新增至案例

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要新增程式碼片段的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下控制項區域中的&#x200B;**程式碼片段**&#x200B;圖示![程式碼片段](assets/snippets-icon.png)。

   您可能需要按一下「控制項」區域中的三點圖示，才能檢視「代碼片段」圖示。

1. （選用）選取要預覽的程式碼片段。
1. 按一下該程式碼片段以將其新增到編輯器中。
1. 將程式碼片段連線至您的案例。
1. 更新程式碼片段中的任何欄位，以搭配已新增該程式碼片段的情境使用。

## 組織代碼片段

在「程式碼片段」面板中，您可以：

* 搜尋程式碼片段。
* 釘選您經常使用的程式碼片段。
* 將程式碼片段匯出為JSON檔案。
* 與其他組織、團隊或使用者共用程式碼片段。
* 在將程式碼片段新增至案例之前先加以預覽。
* 排序代碼片段清單。
  <!--* Add tags to a snippet, and use tags to find it later.-->

## 共用程式碼片段

您可以與團隊或組織共用程式碼片段，或直接將副本傳送給其他使用者。

您可以：

* **與團隊或組織共用**：共用程式碼片段，讓其他成員可以使用。
* **傳送副本給使用者**：傳送副本給一位使用者。 使用者會收到自己的復本。


1. 按一下控制項區域中的&#x200B;**程式碼片段**&#x200B;圖示![程式碼片段](assets/snippets-icon.png)。
1. 將游標暫留在您要共用的程式碼片段上，然後按一下出現時的共用圖示。
1. 選取您是否要與其他組織、團隊或使用者共用程式碼片段。
1. 按一下「**下一步**」。
1. 選取您要共用程式碼片段的組織或團隊，或輸入您要共用程式碼片段之使用者的使用者ID。
1. 按一下&#x200B;**共用**。

與您共用的程式碼片段會顯示在「程式碼片段」面板的「**與我共用**」標籤上。

## 匯入和匯出程式碼片段

您可以將程式碼片段匯出至JSON檔案，並將其匯入其他案例或環境中。

1. 按一下控制項區域中的&#x200B;**程式碼片段**&#x200B;圖示![程式碼片段](assets/snippets-icon.png)。
1. 將游標暫留在您要共用的程式碼片段上，然後按一下出現時的匯出圖示。

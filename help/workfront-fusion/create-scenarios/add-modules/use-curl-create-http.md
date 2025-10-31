---
title: 使用cURL新增HTTP模組
description: 您可以將cURL請求貼入情境中，然後Fusion會建立根據cURL請求設定的HTTP模組。
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
source-git-commit: c83070a7c2d1d048000a4eace4aaede73c7ec49d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# 使用cURL新增HTTP模組

您可以將cURL請求貼入情境中，然後Fusion會建立根據cURL請求設定的HTTP模組。

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
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

+++

## 從cURL請求建立HTTP模組


若要使用cURL建立HTTP模組：

1. 在Fusion外部建立cURL要求的文字，例如在文字編輯器中。
1. 將cURL請求複製到剪貼簿。
1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要建立模組的情境。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 在案例編輯器中的任何空白處按一下滑鼠右鍵，然後選取&#x200B;**貼上**。

   或

   按下Ctrl + V (Windows)或Cmd + V (Mac)。


   HTML模組隨即建立。
1. 拖曳模組以將其連線至您的案例。

## 疑難排解

如果您的cURL未貼上情境中，請檢查瀏覽器設定，以確保已啟用從剪貼簿貼上的功能。

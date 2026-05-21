---
title: 使用 cURL 新增 HTTP 模組
description: 您可以將cURL請求貼入情境中，然後Fusion會建立根據cURL請求設定的HTTP模組。
author: Becky
feature: Workfront Fusion
exl-id: 6d466809-860d-4f72-9044-ebe2df943674
TQID: https://experienceleague.adobe.com/vPAMsVLVV7C3ykPPXgbMgDTosd0M3hYKYVL-OFszXqw
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 269
ht-degree: 39%

---

# 使用 cURL 新增 HTTP 模組

您可以將cURL請求貼入情境中，然後Fusion會建立根據cURL請求設定的HTTP模組。

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
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

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

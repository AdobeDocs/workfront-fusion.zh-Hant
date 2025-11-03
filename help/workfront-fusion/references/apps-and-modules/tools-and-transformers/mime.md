---
title: mime模組
description: 您可以在Adobe Workfront Fusion中使用MIME型別。 多用途網際網路郵件延伸模組(MIME)型別是標籤，可讓軟體識別網際網路上共用的不同資料型別。 Web伺服器和瀏覽器會使用MIME型別來決定應該對檔案執行的操作。 例如，具有MIME型別text/html的檔案在瀏覽器中的處理方式與MIME型別image/jpeg的檔案不同。 MIME型別獨立於作業系統和硬體。
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---

# [!UICONTROL MIME]模組

您可以在Adobe Workfront Fusion中使用MIME型別。 多用途網際網路郵件延伸模組(MIME)型別是標籤，可讓軟體識別網際網路上共用的不同資料型別。 Web伺服器和瀏覽器會使用MIME型別來決定應該對檔案執行的操作。 例如，MIME型別為`text/html`的檔案在瀏覽器中的處理方式與MIME型別為`image/jpeg`的檔案不同。 MIME型別獨立於作業系統和硬體。

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



## [!UICONTROL MIME]模組及其欄位

* [取得副檔名](#get-a-file-extension)
* [取得MIME型別](#get-a-mime-type)

### [!UICONTROL 取得副檔名]

此轉換器模組會傳回指定MIME型別的原始副檔名。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL MIME型別]</td> 
   <td> <p>輸入或對應您要決定副檔名的MIME型別。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 取得MIME型別]

此轉換器模組會傳回與指定檔案名稱、路徑或副檔名相關聯的MIME型別。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案]</td> 
   <td> <p>輸入或對應您要決定其MIME型別的檔案。 </p> <p>您可以使用以下方式輸入檔案：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 檔案路徑]</strong> </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>/file/image.jpeg</p> </li> 
     <li><strong>[!UICONTROL 檔案名稱]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>image.jpeg</p> </li> 
     <li><strong>[!UICONTROL 副檔名]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>jpeg</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

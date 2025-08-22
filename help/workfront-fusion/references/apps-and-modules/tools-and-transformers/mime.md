---
title: mime模組
description: 您可以在Adobe Workfront Fusion中使用MIME型別。 多用途網際網路郵件延伸模組(MIME)型別是標籤，可讓軟體識別網際網路上共用的不同資料型別。 Web伺服器和瀏覽器會使用MIME型別來決定應該對檔案執行的操作。 例如，具有MIME型別text/html的檔案在瀏覽器中的處理方式與MIME型別image/jpeg的檔案不同。 MIME型別獨立於作業系統和硬體。
author: Becky
feature: Workfront Fusion
exl-id: 9259356b-5b42-4b6d-9854-fce9718d14e3
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---

# [!UICONTROL MIME]模組

您可以在Adobe Workfront Fusion中使用MIME型別。 多用途網際網路郵件延伸模組(MIME)型別是標籤，可讓軟體識別網際網路上共用的不同資料型別。 Web伺服器和瀏覽器會使用MIME型別來決定應該對檔案執行的操作。 例如，MIME型別為`text/html`的檔案在瀏覽器中的處理方式與MIME型別為`image/jpeg`的檔案不同。 MIME型別獨立於作業系統和硬體。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>無Workfront Fusion授權需求</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增:</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

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
   <td role="rowheader">[！UICONTROL MIME型別]</td> 
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
   <td role="rowheader">[！UICONTROL檔案]</td> 
   <td> <p>輸入或對應您要決定其MIME型別的檔案。 </p> <p>您可以使用以下方式輸入檔案：</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL檔案路徑]</strong> </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>/file/image.jpeg</p> </li> 
     <li><strong>[！UICONTROL檔案名稱]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>image.jpeg</p> </li> 
     <li><strong>[！UICONTROL副檔名]</strong>  <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>jpeg</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

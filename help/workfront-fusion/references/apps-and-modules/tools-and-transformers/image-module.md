---
title: 影像模組
description: Adobe Workfront Fusion影像模組可讓您取得特定影像的相關資訊（尺寸、型別等）、將影像轉換為其他檔案格式，以及直接變更影像大小。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: a7696c9d-002d-4bb4-ae10-1f69dc5e66fe
source-git-commit: 3834bb9c7f07e0097783c44558fd656d455337b4
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 0%

---

# 影像模組

[!DNL Adobe Workfront Fusion] [!UICONTROL 影像]模組可讓您取得特定影像的相關資訊（尺寸、型別等）、將影像轉換為其他檔案格式，以及直接變更影像大小。

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
   <p>不需要Workfront Fusion授權。</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## [!UICONTROL 影像]模組及其欄位

當您設定此模組時，會顯示下列欄位。 模組中的粗體標題表示必填欄位。

* [[!UICONTROL 轉換格式]](#convert-a-format)
* [[!UICONTROL 擷取中繼資料]](#extract-metadata)
* [[!UICONTROL 調整大小]](#resize)

### [!UICONTROL 轉換格式]

此轉換器模組會變更影像檔案的格式。 此模組與下列格式相容：

* PNG
* JPG
* GIF
* BMP

來源檔案和輸出都必須採用其中一種格式。 例如，[!UICONTROL 影像] >[!UICONTROL 轉換格式]模組可以將PNG檔案轉換為BMP檔案，或將BMP轉換為JPG。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸出格式]</td> 
   <td>選取您希望模組將來源檔案轉換成的格式。 </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 擷取中繼資料]

此轉換器模組會傳回模組的基本資訊。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 調整大小]

此轉換器模組會根據您指定的條件變更影像的高度和寬度。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL我要]</td> 
   <td>選取您要維持高寬比還是將尺寸變更為指定的高度和寬度。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL依據]</td> 
   <td> <p>選取您希望模組如何決定影像的新大小。 如果您在「我想」欄位中選取要維持高寬比例，此欄位就會顯示。 其他欄位會根據此欄位中的選取專案而顯示。</p> 
    <ul> 
     <li> <p>[！UICONTROL最大寬度]</p> <p>將影像縮小至您指定的寬度。 高度會自動計算。</p> </li> 
     <li> <p>[！UICONTROL最大高度]</p> <p>將影像縮小至您指定的高度。 會自動計算寬度。</p> </li> 
     <li> <p>[！UICONTROL最大高度或寬度]</p> <p>以高度和寬度不超過指定值的方式縮小影像。 因為此選項會維持高寬比，所以其中一個尺寸可能小於指定的尺寸。 例如，如果高度和寬度都指定為40,400x300的影像將會減少為40X30。</p> </li> 
     <li> <p>[！UICONTROL最小寬度]</p> <p>將影像放大至您指定的寬度。 高度會自動計算。</p> </li> 
     <li> <p>[！UICONTROL最小高度]</p> <p>將影像放大至您指定的高度。 會自動計算寬度。</p> </li> 
     <li> <p>[！UICONTROL最小高度或寬度]</p> <p>放大影像的方式使其高度和寬度不小於您指定的值。 因為此選項會維持高寬比，所以其中一個尺寸可能會大於指定的尺寸。 例如，如果高度和寬度都指定為300,40x30影像將會放大為400X300。</p> </li> 
     <li> <p>[！UICONTROL百分比]</p> <p>根據您指定的值，以百分比變更影像大小。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL寬度]</td> 
   <td>輸入或對應調整大小影像的所需寬度（畫素）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Height]</td> 
   <td>輸入或對應調整大小影像所需的高度（畫素）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL百分比變更]</td> 
   <td>如果您已選擇以百分比變更影像，請輸入或對應您要以百分比變更影像。</td> 
  </tr> 
 </tbody> 
</table>

## 疑難排解

### 動作因錯誤而終止

由於下列其中一個原因，動作可能會因錯誤而終止：

* 收到的資料不是JPG/GIF/PNG/BMP格式
* 變更影像尺寸時，已超過最大寬度/高度限制。 影像大小不得超過3840畫素寬度和2160畫素高度
* 變更影像的尺寸或格式時，已超過影像的最大允許大小。

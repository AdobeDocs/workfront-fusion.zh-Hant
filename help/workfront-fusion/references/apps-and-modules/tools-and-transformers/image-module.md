---
title: 影像模組
description: Adobe Workfront Fusion影像模組可讓您取得特定影像的相關資訊（尺寸、型別等）、將影像轉換為其他檔案格式，以及直接變更影像大小。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: a7696c9d-002d-4bb4-ae10-1f69dc5e66fe
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 0%

---

# 影像模組

[!DNL Adobe Workfront Fusion] [!UICONTROL Image]模組可讓您取得特定影像的相關資訊（尺寸、型別等）、將影像轉換為其他檔案格式，以及直接變更影像大小。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
  <td> <p>[!UICONTROL Pro] 或更高</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]用於Work Automation and Integration]，[!UICONTROL [!DNL Workfront Fusion]用於Work Automation]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## [!UICONTROL Image]模組及其欄位

當您設定此模組時，會顯示下列欄位。 模組中的粗體標題表示必填欄位。

* [[!UICONTROL Resize]](#resize)
* [[!UICONTROL Convert a format]](#convert-a-format)
* [[!UICONTROL Extract metadata]](#extract-metadata)

### [!UICONTROL Resize]

此轉換器模組會根據您指定的條件變更影像的高度和寬度。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>選取您要轉換的影像來源。 您可以從先前的模組中選取輸出，或對應資料檔案和檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data]</td> 
   <td>對應您要轉換的檔案。 如果您在[!UICONTROL Source file]欄位中選取[!UICONTROL Map]，則可使用此欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>輸入轉換檔案的名稱。 如果您在[!UICONTROL Source file]欄位中選取[!UICONTROL Map]，則可使用此欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL I want to]</td> 
   <td>選取您要維持高寬比還是將尺寸變更為指定的高度和寬度。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL According to]</td> 
   <td> <p>選取您希望模組如何決定影像的新大小。 如果您在「我想」欄位中選取要維持高寬比例，此欄位就會顯示。 其他欄位會根據此欄位中的選取專案而顯示。</p> 
    <ul> 
     <li> <p>[!UICONTROL Maximum width]</p> <p>將影像縮小至您指定的寬度。 高度會自動計算。</p> </li> 
     <li> <p>[!UICONTROL Maximum height]</p> <p>將影像縮小至您指定的高度。 會自動計算寬度。</p> </li> 
     <li> <p>[!UICONTROL Maximum height or width]</p> <p>以高度和寬度不超過指定值的方式縮小影像。 因為此選項會維持高寬比，所以其中一個尺寸可能小於指定的尺寸。 例如，如果高度和寬度都指定為40,400x300的影像將會減少為40X30。</p> </li> 
     <li> <p>[!UICONTROL Minimum width]</p> <p>將影像放大至您指定的寬度。 高度會自動計算。</p> </li> 
     <li> <p>[!UICONTROL Minimum height]</p> <p>將影像放大至您指定的高度。 會自動計算寬度。</p> </li> 
     <li> <p>[!UICONTROL Minimum height or width]</p> <p>放大影像的方式使其高度和寬度不小於您指定的值。 因為此選項會維持高寬比，所以其中一個尺寸可能會大於指定的尺寸。 例如，如果高度和寬度都指定為300,40x30影像將會放大為400X300。</p> </li> 
     <li> <p>[!UICONTROL Percent]</p> <p>根據您指定的值，以百分比變更影像大小。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Width]</td> 
   <td>輸入或對應調整大小影像的所需寬度（畫素）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Height]</td> 
   <td>輸入或對應調整大小影像所需的高度（畫素）。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Convert a format]

此轉換器模組會變更影像檔案的格式。 此模組與下列格式相容：

* PNG
* JPG
* GIF
* BMP

來源檔案和輸出都必須採用其中一種格式。 例如，[!UICONTROL Image] >[!UICONTROL Convert a format]模組可以將PNG檔案轉換為BMP檔案，或將BMP轉換為JPG。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>選取您要轉換的影像來源。 您可以從先前的模組中選取輸出，或對應資料檔案和檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data]</td> 
   <td>對應您要轉換的檔案。 如果您在[!UICONTROL Source file]欄位中選取[!UICONTROL Map]，則可使用此欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>輸入轉換檔案的名稱。 如果您在[!UICONTROL Source file]欄位中選取[!UICONTROL Map]，則可使用此欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output format]</td> 
   <td>選取您希望模組將來源檔案轉換成的格式。 </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Extract metadata]

此轉換器模組會傳回模組的基本資訊。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>選取您要轉換的影像來源。 您可以從先前的模組中選取輸出，或對應資料檔案和檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data]</td> 
   <td>對應您要轉換的檔案。 如果您在[!UICONTROL Source file]欄位中選取對應，則可使用此欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>輸入轉換檔案的名稱。 如果您在[!UICONTROL Source file]欄位中選取對應，則可使用此欄位。</td> 
  </tr> 
 </tbody> 
</table>

## 可能的問題

### 動作因錯誤而終止

在三種情況下，動作可能會因錯誤而終止：

* 收到的資料不是JPG/GIF/PNG/BMP格式
* 變更影像尺寸時，已超過最大寬度/高度限制。 影像大小不得超過3840畫素寬度和2160畫素高度
* 變更影像的尺寸或格式時，已超過影像的最大允許大小。

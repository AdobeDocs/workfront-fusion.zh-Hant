---
title: 在模組之間對應檔案
description: 有些模組有能力處理檔案。 這些模組可以傳回要傳送以供進一步處理的輸出檔案，或要求將檔案傳遞給它們以供處理。 這些模組必須彼此對應，才能共同處理檔案。
author: Becky
feature: Workfront Fusion
exl-id: 25c632f4-169e-4d3c-989a-f57b398bd3f0
source-git-commit: b2ca63ca5af26ee79758798118817b55113b3bd0
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# 在模組之間對應檔案

有些模組可以處理檔案。 這些模組可以傳回要傳送以供進一步處理的輸出檔案，或要求將檔案傳遞給它們以供處理。 檔案可以對映，以便一個模組的檔案輸出可以由另一個模組處理。

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

## 將檔案從來源模組對應至目標模組

處理檔案的模組需要兩項資訊：

* 檔案名稱
* 檔案內容（資料）

如果之前有任何模組輸出檔案，您可以選取來源模組，而該模組輸出的檔案名稱和資料會對應至目標模組。

您也可以手動輸入此名稱與資料，或從先前的模組進行對應。 例如，在重新命名檔案時，這可能很方便。

>[!NOTE]
>
>如果您需要處理來自URL的檔案，我們建議使用`HTTP > Get a File`模組從URL下載檔案，然後將檔案從`HTTP > Get a File`模組對應到您案例中所需模組的欄位。
>
>![對應檔案](assets/map-source-file.png)

若要對應檔案：

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要對應檔案的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 在目標模組（您對應到的目標）中，找出&#x200B;**Source檔案**&#x200B;區域。
1. 若要對應上一個模組的檔案輸出，請選取輸出檔案的模組。

   ![Workfront下載檔案](assets/wf-download-document.png)

1. 若要手動對應名稱和資料，請選取「對應」，然後輸入或對應檔案的名稱和資料。

   ![使用地圖選項](assets/use-the-map-option.png)

1. 繼續設定模組，或按一下[確定]。**&#x200B;**

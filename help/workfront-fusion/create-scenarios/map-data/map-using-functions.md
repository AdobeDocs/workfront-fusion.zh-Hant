---
title: 使用函式對應專案
description: 對映專案時，您可以使用函式來建立簡單或複雜的公式。
author: Becky
feature: Workfront Fusion
exl-id: b9d7643e-febf-42e2-9ddc-8ec8eba98e7a
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 0%

---

# 使用函式對應專案

對映專案時，您可以使用函式來建立簡單或複雜的公式。 可用的函式類似於Excel和某些程式語言中的函式：

* 它們會評估一般邏輯、數學、文字、日期和陣列。
* 它們可讓您執行專案值的條件邏輯和轉換，例如將文字轉換為大寫、裁剪文字、將日期轉換為不同格式等等。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 封裝</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權</td> 
   <td> <p>新增： [!UICONTROL Standard]</p><p>或</p><p>目前： [!UICONTROL Work]或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定*</td> 
   <td> 
     <p>您必須是組織的[!DNL Workfront Fusion]管理員。</p>
     <p>您必須是團隊的[!DNL Workfront Fusion]管理員。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 將函式插入欄位

若要將函式插入欄位：

1. 按一下左側面板中的&#x200B;**[!UICONTROL Scenarios]**&#x200B;索引標籤。
1. 選取您要對應資料的情境。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下您要插入函式的欄位。
1. 在包含要插入的函式的對映面板中選取索引標籤。

   如需對應面板標籤的相關資訊，請參閱[函式概述](/help/workfront-fusion/get-started-with-fusion/understand-fusion/function-overview.md)
   1. 按一下函式名稱。

      或

      將函式拖曳至欄位。
1. 設定函式引數。

   如需函式引數的說明，請將游標停留在對應面板中的函式上。

   如需函式及其引數的詳細資訊，請參閱[函式參考下的文章：文章索引](/help/workfront-fusion/references/mapping-panel/functions/functions-toc.md)。

1. 繼續設定模組，或按一下[確定]。**&#x200B;**

>[!TIP]
>
>當您建立要在其他欄位中重複使用的複雜公式時，可以按一下包含組合的欄位，使用Cmd-A或Ctrl-A來選取它，然後將其複製並貼到其他欄位中。


>[!BEGINSHADEBOX]

**範例：**&#x200B;有些資料型別會防止使用者輸入超過特定數目的字元。 您可以使用子字串函式將值限製為特定字元數。

在此範例中，子字串函式將專案名稱限製為50個字元。

![會議長度限制範例](assets/example-meet-length-restriction-350x184.png)

>[!ENDSHADEBOX]

## 巢狀函式

您可以巢狀內嵌函式。

>[!BEGINSHADEBOX]

**範例：**

在此範例中，子字串函式將修剪的專案名稱限製為50個字元。

![已修剪名稱](assets/trimmed-name-under-50.png)

>[!ENDSHADEBOX]

若要巢狀內嵌函式：

1. 按一下您要建立公式的欄位。

   這會開啟對應面板。

1. 按一下您要新增的第一個函式。 這是外部的函式。 如果下列範例，則為`substring`函式。
1. 在該函式中，按一下要巢狀函式移至何處。 在此範例中，巢狀函式會取代第一個引數。
1. 在對映面板中，按一下巢狀函式。 在此範例中，這是`trim`函式。
1. 繼續視需要設定函式。
1. 繼續設定模組，或按一下[確定]。**&#x200B;**

## 使用[!DNL Google Sheets]函式

如果[!DNL Workfront Fusion]沒有您要使用的功能，但它由[!DNL Google Sheets]所提供，您可以依照下列步驟來使用：

1. 在[!DNL Google Sheets]中建立新的空白試算表。
1. 在[!DNL Workfront Fusion]中，開啟您的情境。
1. 將&#x200B;**[!DNL Google Sheets]** >**[!UICONTROL Update a cell]**&#x200B;模組新增至情境。

1. 設定模組：

   1. 在&#x200B;**[!UICONTROL Spreadsheet]**&#x200B;欄位中選擇新建立的試算表。
   1. 將包含[!DNL Google Sheets]函式的公式插入&#x200B;**[!UICONTROL Value]**&#x200B;欄位。

      您可以照常使用先前模組的輸出。

      ![使用Google工作表功能](assets/exploit-google-sheet-functions-350x218.png)

1. 插入&#x200B;**[!UICONTROL Google Sheets]>[!UICONTROL Get a cell]**&#x200B;模組以取得計算結果。
1. 使用您在步驟4中使用的相同儲存格ID來設定模組。

   ![使用Google工作表功能](assets/exploit-google-sheet-functions-2-350x187.png)

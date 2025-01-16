---
title: MariaDB模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動化使用 [!DNL MariaDB]的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 41179cfe-c0f9-4d18-ab7e-374670ac688b
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---

# [!DNL MariaDB]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL MariaDB]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

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
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
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

## 先決條件

若要使用[!DNL MariaDB]模組，您必須有[!DNL MariaDB]帳戶。

## 將[!DNL MariaDB]連線至[!DNL Workfront Fusion]

您可以直接從[!DNL MariaDB]模組內建立與您的[!DNL MariaDB]帳戶的連線。

1. 在任何[!DNL MariaDB]模組中，按一下[!UICONTROL Connection]欄位旁的&#x200B;**[!UICONTROL Add]**。
1. 設定下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Connection name]</p> </td> 
      <td> <p>輸入新連線的名稱。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Host]</td> 
      <td> <p>輸入資料庫執行處理的IP位址或主機名稱。 此主機必須可從您的網路外部存取。</p> <p>範例： <code>[!DNL mariadb.hwoh2j5h.us-east-1.rds.amazon.com]</code></p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Port]</td> 
      <td>預設連線埠為3306。 如果您使用非標準連線埠，請將此號碼設定為您的連線埠。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Database Name]</td> 
      <td>輸入您要與其互動的資料庫名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Username]</td> 
      <td>輸入您的使用者名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Password]</td> 
      <td>輸入您的密碼。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線，並返回模組。

## [!DNL MariaDB]模組及其欄位

當您設定[!DNL MariaDB]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL MariaDB]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 執行查詢（進階）

此動作模組會根據您提供的查詢，從資料庫擷取資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL MariaDB]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">將[!DNL MariaDB]連線到[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>輸入您希望模組用來擷取資料的SQL查詢。</p> <p>重要：查詢中使用的變數不會經過淨化。 請務必正確清理變數，以防止SQL插入。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Select rows from a table (advanced)]

此模組會從您的資料庫讀取記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL MariaDB]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">將[!DNL MariaDB]連線到[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Table]</td> 
   <td> <p>選取包含要讀取之記錄的表格。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>設定您要用來選取列的篩選器</p> 
    <ul> 
     <li> <p>選取您要搜尋的欄位</p> </li> 
     <li> <p>選取您要用於搜尋的運運算元</p> </li> 
     <li> <p>輸入或對應您要搜尋的值。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort] </td> 
   <td> <p>針對您想要排序結果的每個層級，按一下<strong>[!UICONTROL Add item]</strong>，然後選取您想要排序結果的欄位，以及您想要以升序或降序排序</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

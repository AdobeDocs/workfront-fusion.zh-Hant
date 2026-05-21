---
title: MariaDB 模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL MariaDB] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 41179cfe-c0f9-4d18-ab7e-374670ac688b
TQID: https://experienceleague.adobe.com/Dq7tbOvvEndH-6k3yX8AvH29kZxp748JeT1HW-zcDDQ
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 657
ht-degree: 60%

---

# [!DNL MariaDB] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL MariaDB] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

關於建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)之下的文章。

關於模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)之下的文章。

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
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>連接器型 (舊版)：Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用 [!DNL MariaDB] 模組，您必須擁有 [!DNL MariaDB] 帳戶。

## 將 [!DNL MariaDB] 連接至 Workfront Fusion

您可以直接從[!DNL MariaDB]模組內建立與您的[!DNL MariaDB]帳戶的連線。

1. 在任何[!DNL MariaDB]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 設定下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線名稱]</p> </td> 
      <td> <p>輸入新連線的名稱。</p> </td> 
     </tr> 
        <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>選取此連線是用於生產或非生產環境。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 類型]</td>
        <td>選取要連接至服務帳戶或者個人帳戶。</td>
        </tr>
     <tr> 
      <td role="rowheader">[！UICONTROL主機]</td> 
      <td> <p>輸入資料庫執行處理的IP位址或主機名稱。 此主機必須可從您的網路外部存取。</p> <p>範例： <code>[!DNL mariadb.hwoh2j5h.us-east-1.rds.amazon.com]</code></p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL連線埠]</td> 
      <td>預設連線埠為3306。 如果您使用非標準連線埠，請將此號碼設定為您的連線埠。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL資料庫]</td> 
      <td>輸入您要與其互動的資料庫名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL使用者]</td> 
      <td>輸入您的使用者名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 密碼]</td> 
      <td>輸入您的密碼。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

## [!DNL MariaDB] 模組及其欄位

當您設定 [!DNL MariaDB] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL MariaDB] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 執行查詢（進階）

此動作模組會根據您提供的查詢，從資料庫擷取資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於將您的 [!DNL MariaDB] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">將 [!DNL MariaDB] 連接至 Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Query]</td> 
   <td> <p>輸入您希望模組用來擷取資料的SQL查詢。</p> <p>重要：查詢中使用的變數不會經過淨化。 請務必正確清理變數，以防止SQL插入。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 從資料表選取資料列（進階）]

此模組會從您的資料庫讀取記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於將您的 [!DNL MariaDB] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-mariadb-to-workfront-fusion" class="MCXref xref">將 [!DNL MariaDB] 連接至 Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL表格]</td> 
   <td> <p>選取包含要讀取之記錄的表格。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td> <p>設定您要用來選取列的篩選器</p> 
    <ul> 
     <li> <p>選取您要搜尋的欄位</p> </li> 
     <li> <p>選取您要用於搜尋的運運算元</p> </li> 
     <li> <p>輸入或對應您要搜尋的值。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL排序] </td> 
   <td> <p>針對您想要排序結果的每個層級，按一下<strong>[！UICONTROL新增專案]</strong>，然後選取您想要排序結果的欄位，以及您想要以升序或降序排序</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

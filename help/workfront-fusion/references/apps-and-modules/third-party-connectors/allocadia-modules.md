---
title: 配置模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Allocadia的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 9a6fccd6-6eee-42dc-a678-c1f34280d139
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 0%

---

# [!DNL Allocadia]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Allocadia]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!DNL Allocadia]模組，您必須有[!DNL Allocadia]帳戶。

## [!DNL Allocadia] API資訊

Allocadia聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.7.6</td> 
  </tr>
 </tbody> 
</table>

## 將[!DNL Allocadia]連線至[!DNL Workfront Fusion]

您可以直接從[!DNL Allocadia]模組內建立與您的[!DNL Allocadia]帳戶的連線。

1. 在任何[!DNL Allocadia]模組中，按一下[!UICONTROL Connection]欄位旁的&#x200B;**[!UICONTROL Add]**。
1. 選取您要使用北美或歐洲伺服器。
1. 輸入您的使用者名稱和密碼。
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線，並返回模組。

## [!DNL Allocadia]模組及其欄位

當您設定[!DNL Allocadia]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Allocadia]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發器](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發器

#### [!UICONTROL Watch Record]

此觸發模組會在新增、更新特定型別的物件或兩者同時進行時，執行案例。 模組會傳回與一個或多個記錄相關聯的所有標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> <table style="table-layout:auto"> <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將Allocadia帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect Allocadia]到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">篩選器</td> 
   <td> <p>選取您希望情境只觀看「新記錄」、[!UICONTROL Updated Records Only]或「新記錄和更新的記錄」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">實體型別</td> 
   <td>選取您希望模組觀看的Allocadia記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出</td> 
   <td> <p>選取您要納入模組輸出的欄位。 可用欄位取決於您選取的實體型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">限制</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中監視的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [自訂API呼叫](#custom-api-call)
* [讀取記錄](#read-record)
* [建立記錄](#create-record)
* [刪除記錄](#delete-record)
* [更新記錄](#update-record)

#### [!UICONTROL Custom API Call]

此動作模組可讓您對[!DNL Allocadia] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Allocadia]模組無法完成的資料流程自動化。

動作以您指定的圖元型別（Allocadia物件型別）為基礎。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Allocadia]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將[!DNL Allocadia]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>https://api-na.allocadia.com/{version}</code>或<code>https://api-eu.allocadia.com/{version}</code>的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱[!DNL Adobe Workfront Fusion]</a>中的<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read Record]

此動作模組從[!DNL Allocadia]中的單一記錄讀取資料。

您指定記錄的ID。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Allocadia]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將[!DNL Allocadia]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您希望模組讀取的[!DNL Allocadia]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>選取您要納入模組輸出的欄位。 可用欄位取決於您選取的[!UICONTROL Entity Type]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>輸入或對應您要模組讀取之記錄的唯一[!DNL Allocadia]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Record]

此動作模組會建立記錄。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Allocadia]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將[!DNL Allocadia]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您要建立以線上專案或欄選擇為基礎的新記錄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Budgets]</td> 
   <td> <p>選取您要建立記錄的預算。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Column choices]</td> 
   <td>選取要用來建立新記錄的欄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Label]</td> 
   <td>輸入或對應新記錄的標籤</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Record]

此動作模組會刪除特定記錄。

您指定記錄的ID。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Allocadia]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將[!DNL Allocadia]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>選取要刪除的實體型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Line item]</strong> </p> <p>輸入明細專案識別碼</p> </li> 
     <li> <p><strong>[!UICONTROL Column Choice]</strong> </p> <p>選取您要刪除記錄的預算，然後輸入「欄位識別碼」與「選擇識別碼」。</p> </li> 
     <li> <p><strong>[!UICONTROL Forecast Tags]</strong> </p> <p>選取您要刪除記錄的預算，然後輸入盤點單識別碼。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update Record]

此動作模組會更新記錄，例如行專案、使用者或欄選擇。

您指定記錄的ID。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!UICONTROL Allocadia]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將[!DNL Allocadia]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您希望模組更新的[!DNL Allocadia]記錄型別。 其他欄位會根據您選取的實體型別而顯示。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Budgets]</td> 
   <td> <p>選取您要更新記錄的預算。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL Search Record]

此搜尋模組會在[!DNL Allocadia]中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境中的後續模組中對應此資訊。

您可以指定所要的記錄型別。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Allocadia]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將[!DNL Allocadia]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您要模組搜尋的[!DNL Allocadia]記錄型別。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Budgets]</td> 
   <td> <p>選取您要搜尋的預算。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Result set]</td> 
   <td>選取您希望模組傳回「所有比對記錄」，還是隻傳回「第一個比對記錄」。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximal count of records]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search criteria]</td> 
   <td>選取您要搜尋的欄位、選取作業，然後輸入或對應您要搜尋的值。 您可以新增[!DNL AND]或[!DNL OR]規則以進一步篩選您的搜尋。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>選取您要納入模組輸出的欄位。 可用欄位取決於您選取的實體型別。</p> </td> 
  </tr> 
 </tbody> 
</table>

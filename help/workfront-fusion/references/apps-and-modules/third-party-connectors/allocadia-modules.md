---
title: Allocadia 模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Allocadia的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 9a6fccd6-6eee-42dc-a678-c1f34280d139
TQID: https://experienceleague.adobe.com/bCfkq5fzw21hmZWLrWztL27g2RAlBbyk9vPEQ-v6bBU
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1467
ht-degree: 56%

---

# [!DNL Allocadia] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Allocadia] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

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

若要使用[!DNL Allocadia]模組，您必須有[!DNL Allocadia]帳戶。

## [!DNL Allocadia] API資訊

Allocadia聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API 版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.7.6</td> 
  </tr>
 </tbody> 
</table>

## 將 [!DNL Allocadia] 連接至 Workfront Fusion

您可以直接從[!DNL Allocadia]模組內建立與您的[!DNL Allocadia]帳戶的連線。

1. 在任何[!DNL Allocadia]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 選取您要使用北美或歐洲伺服器。
1. 輸入您的使用者名稱和密碼。
1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

## [!DNL Allocadia] 模組及其欄位

當您設定 [!DNL Allocadia] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Allocadia] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

#### [!UICONTROL 監視記錄]

此觸發程序模組會在新增、更新或是同時新增和更新特定類型的物件時執行情境。 模組會傳回與記錄相關聯的所有標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> <table style="table-layout:auto"> <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將Allocadia帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">[！UICONTROL Connect Allocadia]到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">篩選器</td> 
   <td> <p>選取您希望情境只觀看「新記錄」、「[！UICONTROL僅更新記錄」，還是「新記錄和更新記錄」。</p> </td> 
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

#### [!UICONTROL 自訂 API 呼叫]

您可以利用此動作模組，對 [!DNL Allocadia] API 進行已驗證的自訂呼叫。 如此一來，您就可以建立其他 [!DNL Allocadia] 模組無法完成的資料流程自動化。

動作以您指定的圖元型別（Allocadia物件型別）為基礎。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Allocadia] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將 [!DNL Allocadia] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>https://api-na.allocadia.com/{version}</code>或<code>https://api-eu.allocadia.com/{version}</code>的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組從[!DNL Allocadia]中的單一記錄讀取資料。

您指定記錄的 ID。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Allocadia] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將 [!DNL Allocadia] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您希望模組讀取的[!DNL Allocadia]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取您要納入模組輸出的欄位。 可用欄位取決於您選取的[！UICONTROL實體型別]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>輸入或對應您要模組讀取之記錄的唯一[!DNL Allocadia]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立記錄]

此動作模組會建立記錄。

模組會傳回記錄的 ID 和任何相關欄位，以及連線存取的任何自訂欄位和值。 您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Allocadia] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將 [!DNL Allocadia] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您要建立以線上專案或欄選擇為基礎的新記錄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL預算]</td> 
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

#### [!UICONTROL 刪除記錄]

此動作模組會刪除特定記錄。

您指定記錄的 ID。

模組會傳回記錄的 ID 和任何相關欄位，以及連線存取的任何自訂欄位和值。 您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Allocadia] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將 [!DNL Allocadia] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td> <p>選取要刪除的實體型別。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL條列專案]</strong> </p> <p>輸入明細專案識別碼</p> </li> 
     <li> <p><strong>[！UICONTROL資料行選擇]</strong> </p> <p>選取您要刪除記錄的預算，然後輸入「欄位識別碼」與「選擇識別碼」。</p> </li> 
     <li> <p><strong>[！UICONTROL預測標籤]</strong> </p> <p>選取您要刪除記錄的預算，然後輸入盤點單識別碼。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組會更新記錄，例如行專案、使用者或欄選擇。

您指定記錄的 ID。

模組會傳回記錄的 ID 和任何相關欄位，以及連線存取的任何自訂欄位和值。 您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[！UICONTROL Allocadia]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將[!DNL Allocadia]連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您希望模組更新的[!DNL Allocadia]記錄型別。 其他欄位會根據您選取的實體型別而顯示。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL預算]</td> 
   <td> <p>選取您要更新記錄的預算。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL 搜尋記錄]

此搜尋模組會在[!DNL Allocadia]中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境內之後的模組中對應此資訊。

您可以指定所要的記錄型別。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   td role="rowheader"&gt; <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Allocadia] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-allocadia-to-workfront-fusion" class="MCXref xref">將 [!DNL Allocadia] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您要模組搜尋的[!DNL Allocadia]記錄型別。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL預算]</td> 
   <td> <p>選取您要搜尋的預算。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL結果集]</td> 
   <td>選取您希望模組傳回「所有比對記錄」，還是隻傳回「第一個比對記錄」。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL最大記錄數]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋條件]</td> 
   <td>選取您要搜尋的欄位、選取作業，然後輸入或對應您要搜尋的值。 您可以新增[!DNL AND]或[!DNL OR]規則以進一步篩選您的搜尋。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取您要納入模組輸出的欄位。 可用欄位取決於您選取的實體型別。</p> </td> 
  </tr> 
 </tbody> 
</table>

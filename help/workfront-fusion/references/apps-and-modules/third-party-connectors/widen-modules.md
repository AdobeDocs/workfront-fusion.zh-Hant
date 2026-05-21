---
title: Widen 模組
description: 在Adobe Workfront Fusion案例中，您可以自動使用[!UICONTROL Widen]的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 11376e58-a44b-4766-85dc-e2421b0112de
TQID: https://experienceleague.adobe.com/joW38nxn0gj6qr1bd1RMS2RT2xOd2KgUsA-M8l57-ys
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1673
ht-degree: 30%

---

# [!DNL Widen] 模組

在Adobe Workfront Fusion案例中，您可以自動使用[!UICONTROL Widen]的工作流程，並將其連線到多個協力廠商應用程式和服務。

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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!UICONTROL Widen]模組，您必須有[!UICONTROL Widen]帳戶。

## 擴充API資訊

「加寬」聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API 版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.10.11</td> 
  </tr>
 </tbody> 
 </table>

## 將 [!DNL Widen] 連接至 Workfront Fusion  {#connect-widen-to-workfront-fusion}

您可以直接從[!DNL Widen]模組內建立與您的[!DNL Widen]帳戶的連線。

1. 在任何[!DNL Widen]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 選取您要連線的環境和帳戶型別。 這僅供參考，並顯示在Fusion的「連線」區域中。
1. 選取您要連線的[!DNL Widen]網域。
1. 輸入您[!DNL Widen]帳戶的權杖。 如需尋找此Token的說明，請參閱[[!DNL Widen] API常見問題集](https://community.widen.com/collective/s/article/API-FAQs)。
1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

## [!DNL Widen] 模組及其欄位

當您設定 [!DNL Widen] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Widen] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序模組](#trigger-modules)
* [動作模組](#action-modules)
* [搜尋模組](#search-modules)

### 觸發程序模組

#### [!UICONTROL 觀看資產]

建立或更新資產時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 事件型別]</td> 
   <td> <p>選取您要觀看新資產或更新資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 展開]</td> 
   <td> <p>選取除了資產欄位之外，您還要納入模組輸出的屬性。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作模組

* [[!UICONTROL 新增資產至集合]](#add-assets-to-collections)
* [[!UICONTROL 自訂 API 呼叫]](#custom-api-call)
* [[!UICONTROL 下載檔案]](#download-file)
* [[!UICONTROL 讀取資產資訊]](#read-asset-info)
* [[!UICONTROL 從集合]移除資產](#remove-assets-from-collection)
* [[!UICONTROL 更新資產中繼資料]](#update-asset-metadata)
* [[!UICONTROL 上傳檔案]](#upload-a-file)

#### [!UICONTROL 新增資產至集合]

此動作模組會將一個或多個資產新增至收藏集。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 集合ID]</td> 
   <td>針對您想要新增資產的每個集合，按一下<strong>[集合ID]</strong>，然後輸入或對應[!UICONTROL 集合ID]。</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> 針對您想要新增至集合的每個資產，按一下<strong>[!UICONTROL Assets ID]</strong>，然後輸入或對應資產ID。</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂 API 呼叫]

您可以利用此動作模組，對 [!DNL Widen] API 進行已驗證的自訂呼叫。 如此一來，您就可以建立其他 [!DNL Widen] 模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API版本]</td> 
   <td>選取您要使用最新版的[!DNL Widen] API，還是1.0版</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入或對應您API呼叫的URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] 會為您新增授權標頭。</p> </td> 
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

#### [!UICONTROL 下載檔案]

此動作模組會從您的[!DNL Widen]帳戶下載資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID]</td> 
   <td> <p>輸入或對應您要下載的資產識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取資產資訊]

此動作模組會透過其唯一ID擷取個別資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID]</td> 
   <td> <p>輸入或對應您要讀取資訊之資產的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 展開]</td> 
   <td> <p>選取除了資產欄位之外，您還要納入模組輸出的屬性。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 從集合]移除資產

此動作模組會從集合中移除一或多個資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 集合ID]</td> 
   <td>針對您要移除資產的每個集合，按一下<strong>[集合ID]</strong>，然後輸入或對應[!UICONTROL 集合ID]。</li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> 針對您要從集合中移除的每個資產，按一下<strong>[!UICONTROL Assets ID]</strong>，然後輸入或對應資產ID。</p> </li> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新資產中繼資料]

此動作模組會更新資產的中繼資料欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID]</td> 
   <td> <p>輸入或對應您要更新中繼資料的資產ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 中繼資料型別]</td> 
   <td> <p>選取您要更新之中繼資料的中繼資料型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 中繼資料]</td> 
   <td>選取您要更新的中繼資料欄位。 針對每個欄位，輸入欄位的新值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳檔案]

此動作模組會將檔案上傳到您的[!DNL Widen]帳戶。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 上傳設定檔]</td> 
   <td> <p>選取您要模組使用的上傳設定檔。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 上傳方法]</td> 
   <td> <p>選取您要如何上傳檔案。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL From File]</strong> </p> <p>從上一個模組選取或對應來源檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL （依URL）]</strong> </p> <p>輸入或對應您要上傳之檔案的URL。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案名稱]</td> 
   <td>輸入或對應所上傳檔案的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 中繼資料型別]</td> 
   <td>選取您要上傳之檔案的中繼資料型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 中繼資料]</td> 
   <td>選取要包含在檔案上載中的中繼資料欄位。 對於每個欄位，輸入該欄位的[!UICONTROL 值]。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋模組

* [[!UICONTROL 讀取集合資產]](#read-collection-assets)
* [[!UICONTROL 搜尋資產]](#search-assets)

#### [!UICONTROL 讀取集合資產]

此動作模組會擷取集合中的資產清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 集合ID]</td> 
   <td> <p>輸入或對應包含您要讀取之資產的集合ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 開始]</td> 
   <td>輸入或對映您要列出的第一個專案編號。 這是分頁記錄的方式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 排序依據]</td> 
   <td> <p>選取您要用來排序資產的屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 順序]</td> 
   <td>選取您要以遞增或遞減方式排序資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋資產]

此搜尋模組會擷取符合特定搜尋條件的資產清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋查詢]</td> 
   <td> <p>輸入您要搜尋資產的條件。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 排序依據]</td> 
   <td> <p>選取您要如何排序資產。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 順序]</td> 
   <td>選取您要以遞增或遞減方式排序資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 包含已刪除]</td> 
   <td>啟用此選項以在搜尋中包含已刪除的資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 包含已封存的]</p> </td> 
   <td> <p>啟用此選項以在搜尋中包含已封存的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋檔案文字]</td> 
   <td>啟用此選項以在搜尋中包含檔案文字，或設為false以僅包含標題符合搜尋條件的資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 位移]</td> 
   <td>輸入或對應您要擷取其詳細資訊的第一個專案編號。 這是分頁記錄的方式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scroll]</td> 
   <td>啟用此選項以允許捲動。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 展開]</td> 
   <td> <p>選取除了資產欄位之外，您還要納入模組輸出的屬性。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

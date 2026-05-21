---
title: Bynder 模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL Bynder] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 0a45f8a7-12cc-41cc-9135-92f4779afac0
TQID: https://experienceleague.adobe.com/2NCbEM8bb0s7m30uCFTWK-wYdhCYKEZC-W01Zr21mRw
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1863
ht-degree: 31%

---

# [!DNL Bynder] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Bynder] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

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

若要使用 [!DNL Bynder] 模組，您必須擁有 [!DNL Bynder] 帳戶。

## Bynder API資訊

Bynder聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API 版本</td> 
   <td> v4 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.25.21</td> 
  </tr>
 </tbody> 
 </table>

## 將 [!DNL Bynder] 連接至 Workfront Fusion  {#connect-bynder-to-workfront-fusion}

>[!NOTE]
>
>Bynder使用授權代碼/重新整理權杖授予型別。 這是Fusion Bynder聯結器使用的唯一授予型別。

* [從Workfront Fusion建立與 [!DNL Bynder] 的連線](#create-a-connection-to-bynder-from-workfront-fusion)
* [在 [!DNL Bynder] 中產生[!UICONTROL 使用者端識別碼]和[!UICONTROL 使用者端密碼] （選擇性）](#generate-a-client-id-and-client-secret-in-bynder-optional)

### 從Workfront Fusion建立與[!DNL Bynder]的連線

您可以從[!DNL Bynder]模組內，直接從Workfront Fusion建立與[!DNL Bynder]帳戶的連線。

1. 在任何[!DNL Bynder]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 選取您要連線的[!DNL Bynder]網域。
1. （選擇性）按一下&#x200B;**[!UICONTROL 進階設定]**，然後輸入您的[!UICONTROL 使用者端識別碼]和[!UICONTROL 使用者端密碼]。

   如需有關產生使用者端ID和使用者端密碼的指示，請參閱本文中的[在 [!DNL Bynder] （選擇性）](#generate-a-client-id-and-client-secret-in-bynder-optional)中產生使用者端ID和使用者端密碼。

1. 在[!UICONTROL 登入]視窗中輸入您的使用者名稱（電子郵件地址）和密碼。
1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

### 在[!DNL Bynder]中產生[!UICONTROL 使用者端識別碼]和[!UICONTROL 使用者端密碼] （選擇性）

如果您要使用使用者端ID和使用者端密碼建立連線，可以從您的[!DNL Bynder]帳戶產生連線。 當您在[!DNL Bynder]中建立應用程式時，會產生使用者端識別碼和使用者端密碼。

如需在[!DNL Bynder]中建立應用程式的指示，請參閱[!DNL Bynder]檔案中的[Oauth 2.0應用程式](https://developer-docs.bynder.com/api/authentication-oauth2-oauth-apps/)。

>[!NOTE]
>
>* 在[!DNL Bynder]中建立應用程式時，請輸入下列專案作為`redirect uri`：
>
>   * US叢集： `https://app.workfrontfusion.com/oauth/cb/workfront-bynder`
>   * 歐盟叢集： `https://app-eu.workfrontfusion.com/oauth/cb/workfront-bynder`
>   * Azure叢集： `https://app-az.workfrontfusion.com/oauth/cb/workfront-bynder`
>* Bynder使用授權代碼/重新整理權杖授予型別。 這是Fusion Bynder聯結器使用的唯一授予型別。

## [!DNL Bynder] 模組及其欄位

當您設定 [!DNL Bynder] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Bynder] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [搜尋](#searches)
* [觸發程序](#triggers)

### 動作

* [[!UICONTROL 新增標籤至資產]](#add-a-tag-to-assets)
* [[!UICONTROL 將資產新增至集合]](#add-assets-to-a-collection)
* [[!UICONTROL 自訂 API 呼叫]](#custom-api-call)
* [[!UICONTROL 下載資產]](#download-asset)
* [[!UICONTROL 讀取資產中繼資料]](#read-asset-metadata)
* [[!UICONTROL 從資產移除標籤]](#remove-a-tag-from-assets)
* [[!UICONTROL 從集合]移除資產](#remove-assets-from-collection)
* [[!UICONTROL 更新資產中繼資料]](#update-asset-metadata)
* [[!UICONTROL 上傳資產]](#upload-asset)

#### [!UICONTROL 新增標籤至資產]

此動作模組會將標籤新增至一或多個資產

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤ID]</td> 
   <td> <p>輸入或對應您要新增至資產的標籤ID。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產ID]</td> 
   <td> <p>針對您要標籤的每個資產，按一下<strong>[!UICONTROL 新增專案]</strong>，然後輸入或對應資產ID。</p> </td> 
  </tr> 
 </tbody> 
 </table>

#### [!UICONTROL 將資產新增至集合]

此動作模組新增一或多個資產至收藏集。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 集合ID]</td> 
   <td> <p>輸入或對應您要新增資產的集合ID。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產ID]</td> 
   <td> <p>針對您想要新增至集合的每個資產，按一下<strong>[!UICONTROL 新增專案]</strong>，然後輸入或對應資產ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂 API 呼叫]

您可以利用此動作模組，對 [!DNL Bynder] API 進行已驗證的自訂呼叫。 如此一來，您就可以建立其他 [!DNL Bynder] 模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

模組會傳回狀態代碼，以及API呼叫的標題和正文。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>輸入相對於 <code>https://{your-bynder-domain}/api/{api-version}/</code> 的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
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

#### [!UICONTROL 下載資產]

此動作模組會下載單一資產。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID]</td> 
   <td>輸入或對應您要下載的資產識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產版本]</td> 
   <td> <p>輸入或對映您要下載的資產版本。 若要下載最新版本的資產，請將此欄位留空。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取資產中繼資料]

此動作模組會讀取資產的中繼資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID]</td> 
   <td>輸入或對應您要擷取中繼資料的資產ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取要包含在此模組的輸出組合包中的資訊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 從資產移除標籤]

此動作模組會從一個或多個資產中移除標籤

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤ID]</td> 
   <td> <p>輸入或對應您要從資產移除之標籤的ID。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產ID]</td> 
   <td> <p>針對您要移除標籤的每個資產，按一下<strong>[!UICONTROL 新增專案]</strong>，然後輸入或對應資產ID。</p> </td> 
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
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 集合ID]</td> 
   <td> <p>輸入或對映您要移除資產之集合的ID。</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產ID]</td> 
   <td> <p>針對您要從集合中移除的每個資產，按一下<strong>[!UICONTROL 新增專案]</strong>，然後輸入或對應資產ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新資產中繼資料]

此動作模組會更新現有資產的中繼資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID]</td> 
   <td>輸入或對應您要更新中繼資料的資產ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td> <p>選取您要輸入資訊的欄位，然後輸入或對應您要使用更新中繼資料的資訊，到這些欄位中。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Metaproperties]</p> </td> 
   <td>選取您要更新的選項，然後輸入資訊或將資訊對應至這些屬性。 中繼屬性是不代表資產中特定欄位的資產相關資訊。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳資產]

此動作模組會上傳單一資產。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 另存新檔]</td> 
   <td> <p>選取要如何儲存上傳的檔案。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 新資產]</strong> </p> <p>選取您要輸入資訊的欄位和中繼屬性，然後在這些欄位中輸入資訊。</p> <p>輸入或對應您要用於上傳資產的品牌ID。</p> </li> 
     <li> <p><strong>[!UICONTROL 新資產版本]</strong> </p> <p>輸入您要上傳新版本之資產的識別碼。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 非同步檔案上傳]</td> 
   <td>上傳大型檔案時啟用此選項。 這可防止大型檔案封鎖案例執行。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL 清單記錄]](#list-record)
* [[!UICONTROL 搜尋Assets]](#search-assets)

#### [!UICONTROL 清單記錄]

此搜尋模組會擷取特定型別的所有專案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要列出的記錄型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 讀取所有集合]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL 讀取所有標籤的相關資訊]</strong> </p> </li> 
     <li> <p><strong>[!UICONTROL 讀取集合的所有資產]</strong> </p> <p>輸入或對應您要列出其資產的集合ID。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取您要納入模組輸出的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋Assets]

此搜尋模組會根據您提供的條件來搜尋資產。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋條件]</td> 
   <td> <p>輸入搜尋條件。 </p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 欄位]</strong> </p> <p>選取您要在搜尋中使用的欄位</p> </li> 
     <li> <p><strong>[!UICONTROL 邏輯運運算元]</strong> </p> <p>選取要在搜尋中使用的運運算元。</p> </li> 
     <li> <p><strong>[!UICONTROL 值]</strong> </p> <p>在選取的欄位中輸入或對應要尋找的值。 值型別應與所選欄位的資料型別相同。 </p> <p>如需資料型別的詳細資訊，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">專案資料型別</a>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結果集]</td> 
   <td>選取您要傳回第一個相符的資產，還是所有相符的資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 排序依據]</td> 
   <td> <p>選取您要排序的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 排序方向]</td> 
   <td> <p>選取您要遞增排序還是遞減排序。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取您要納入模組輸出的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 觸發程序

#### [!UICONTROL 觀看資產]

建立或更新資產時，此觸發模組就會啟動案例。

<table style="table-layout:auto">
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">事件型別</td>
    <td>選取您是否要在建立新資產或更新現有資產時啟動案例。</td>
  </tr> 
  <tr>
     <td role="rowheader">[!UICONTROL 集合]</td>
   <td> <p>選取您要觀看新資產的集合。 若要觀看所有集合，請將此欄位留空。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">輸出</td>
    <td>選取要包含在輸出中的欄位。</td>
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 限制]</td>

<td> <p>輸入您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

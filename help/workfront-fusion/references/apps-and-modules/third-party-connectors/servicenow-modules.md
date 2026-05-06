---
title: ServiceNow 模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL ServiceNow] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 7b236869-bd83-4db5-a363-d6570f6e4aff
source-git-commit: 3e39d284014c76a1cc300a075e61c25964c49995
workflow-type: tm+mt
source-wordcount: '1643'
ht-degree: 43%

---

# [!DNL ServiceNow] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL ServiceNow] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

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

若要使用 [!DNL ServiceNow] 模組，您必須擁有 [!DNL ServiceNow] 帳戶。

## ServiceNow API資訊

ServiceNow聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td><pre><code>https://&#123;&#123;connection.instance&#125;&#125;/api</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.5.13</td> 
  </tr>
 </tbody> 
 </table>

## 將 [!DNL ServiceNow] 連接至 Workfront Fusion

若要為您的 [!DNL ServiceNow] 模組建立連線：

1. 當您開始設定第一個[!DNL ServiceNow]模組時，請按一下[!UICONTROL 連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。
1. 輸入下列：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線名稱]</p> </td> 
      <td>輸入新[!DNL ServiceNow]連線的名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 環境]</p> </td> 
      <td>選取您要連線到生產或非生產環境。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 密碼]</p> </td> 
      <td>選取要連接至服務帳戶或者個人帳戶。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 使用者名稱]</p> </td> 
      <td>輸入您的[!DNL ServiceNow]使用者名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 密碼]</p> </td> 
      <td>輸入您的ServiceNow密碼。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 執行個體]</p> </td> 
      <td> <p>輸入沒有<code>https://</code>的[!DNL ServiceNow]帳戶位址（通常是<code>&lt;company>.service-now.com</code>）。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**繼續**」，儲存連線並返回模組。

   <!--Markdown placeholder-->

## [!UICONTROL ServiceNow]模組及其欄位

當您設定 [!DNL ServiceNow] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL ServiceNow] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* 如果在&quot;[!UICONTROL 記錄型別]&quot;欄位中選取自訂記錄，則載入自訂欄位可能需要一些時間。
>
>* 如果沒有自訂記錄，「記錄型別」欄位下拉式清單將為空白。

### 觸發程序

#### [!UICONTROL 監視記錄]

建立或更新記錄時，此觸發模組會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要觀察的表格是自訂表格還是標準表格。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td>選取您要觀看的記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示]</td> 
   <td>選取您要顯示的值型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要模組輸出的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td>選取您要監視新記錄或更新的記錄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 建立記錄]](#create-a-record)
* [[!UICONTROL 自訂 API 呼叫]](#custom-api-call)
* [[!UICONTROL 停用使用者]](#deactivate-a-user)
* [[!UICONTROL 刪除記錄]](#delete-a-record)
* [[!UICONTROL 下載附件]](#download-an-attachment)
* [[!UICONTROL 讀取記錄]](#read-a-record)
* [[!UICONTROL 上傳附件]](#upload-an-attachment)
* [[!UICONTROL 更新記錄]](#update-a-record)

#### [!UICONTROL 建立記錄]

此動作模組會建立新的[!DNL ServiceNow]記錄。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要在自訂表格或標準表格中建立記錄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td>選取您要模組建立的[!DNL ServiceNow]記錄型別。 然後，您可以填寫此記錄型別的可用欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂 API 呼叫]

您可以利用此動作模組，對 [!DNL ServiceNow] API 進行已驗證的自訂呼叫。 如此一來，您就可以建立其他 [!DNL ServiceNow] 模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 相對URL]</td> 
   <td> 輸入相對於 <code>https://&ltinstance_url&gt/api/</code> 的路徑。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> </td> 
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

#### [!UICONTROL 停用使用者]

此動作模組使用系統ID在[!DNL ServiceNow]中停用使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 使用者系統識別碼]</td> 
   <td> 輸入或對應您要停用模組之使用者的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除事件或使用者。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td>選取您要刪除事件或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 系統ID]</td> 
   <td>輸入或對應您要模組刪除之記錄的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 下載附件]

此動作模組會下載[!DNL ServiceNow]記錄中的附件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 附件系統ID]</td> 
   <td> 輸入或對應您要模組下載之附件的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組使用系統ID讀取[!DNL ServiceNow]記錄。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄系統ID]</td> 
   <td>輸入或對應您要模組讀取之記錄的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要讀取的記錄是在自訂表格中還是在標準表格中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td>選取您希望模組讀取的[!DNL ServiceNow]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示]</td> 
   <td>選取您要顯示的值型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組會建立新的[!DNL ServiceNow]記錄。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄系統ID]</td> 
   <td>輸入或對應您要模組更新的記錄的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取要更新的記錄是在自訂表格中還是在標準表格中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td>選取您希望模組更新的[!DNL ServiceNow]記錄型別。 然後，您可以填寫此記錄型別的可用欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳附件]

此動作模組會將附件上傳至[!DNL ServiceNow]記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表名稱]</td> 
   <td>輸入或對應您要上傳附件的表格名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 系統ID]</td> 
   <td>輸入或對應您要上傳附件之專案的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL 搜尋記錄]

此模組會使用您選取的條件來搜尋記錄。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境內之後的模組中對應此資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要搜尋的表格是自訂表格還是標準表格。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td>選取您要搜尋的記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結果集]</td> 
   <td>選取您希望模組傳回符合條件的所有記錄，還是隻傳回符合條件的第一筆記錄。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 最大記錄數]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋型別]</td> 
   <td> <p>選取您希望模組執行的搜尋型別</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 進階查詢]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL 搜尋查詢]</p> <p>輸入自訂搜尋查詢。 如需[!DNL ServiceNow]自訂搜尋查詢的相關資訊，請參閱<a href="https://docs.servicenow.com/bundle/orlando-platform-user-interface/page/use/common-ui-elements/reference/r_OpAvailableFiltersQueries.html">ServiceNow查詢檔案</a>。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Simple]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL 搜尋條件]</p> <p>輸入您希望模組搜尋的條件。 </li> 
       <li> <p>[!UICONTROL 排序依據]</p> <p>指出您希望模組排序結果的欄位，以及應依遞增或遞減排序。</p> </li> 
      </ul> </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示]</td> 
   <td>選取您要顯示的值型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

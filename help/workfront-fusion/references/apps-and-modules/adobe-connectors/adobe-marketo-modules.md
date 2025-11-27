---
title: Marketo 模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL Marketo] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: da417ac7-e532-45f7-86d9-3643b5f9f203
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: ht
source-wordcount: '2237'
ht-degree: 100%

---

# [!DNL Marketo] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Marketo] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

如需關於 Marketo 連接器的簡介影片，請參閱：

* [Marketo](https://video.tv.adobe.com/v/3427026/){target=_blank}

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

若要使用 [!DNL Marketo] 模組，您必須擁有 [!DNL Marketo] 帳戶。

## Marketo API 資訊

Marketo 連接器會使用以下內容：

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
   <td>v1.14.19</td> 
  </tr>
 </tbody> 
 </table>

## 將 [!DNL Marketo] 連接至 Workfront Fusion {#connect-marketo-to-workfront-fusion}

您可以從任何 [!DNL Marketo] 模組內直接建立與您 [!DNL Marketo] 帳戶的連線。

1. 在任何 Marketo 模組中，按一下「連線」欄位旁的「**新增**」。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>
          <p>選取要連接至生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 類型]</td>
        <td>
          <p>選取要連接至服務帳戶或者個人帳戶。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 帳戶/Munchkin ID]</td>
        <td>
          <p>輸入您的 [!DNL Marketo] 帳戶或者 [!DNL Marketo] [!UICONTROL Munchkin] ID。這是指派至您帳戶的基礎 URL 或端點的獨特部分，而您可以透過 [!DNL Marketo] 的 [!UICONTROL REST] API 進行存取。如需尋找這個帳戶或 Munchkin ID 的說明，請參閱 [!DNL Marketo] 文件中的 [基礎 URL](https://developers.marketo.com/rest-api/base-url/)。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的 Marketo 用戶端 ID。如需找到這個用戶端 ID 的說明，請參閱 [!DNL Marketo] 文件中的 [驗證](https://developers.marketo.com/rest-api/authentication/)。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的 Marketo 用戶端密碼。如需尋找這些密碼的說明，請參閱 [!DNL Marketo] 文件中的 [驗證](https://developers.marketo.com/rest-api/authentication/)。</td>
      </tr>
     </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

## [!DNL Marketo] 模組及其欄位

當您設定 [!DNL Marketo] 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Marketo] 欄位。在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

* [[!UICONTROL 監視事件 (即時)]](#watch-events-instant)
* [[!UICONTROL 監視記錄]](#watch-records)

#### [!UICONTROL 監視事件 (即時)]

建立或更新記錄時，此觸發程序模組便會啟動一個情境。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>輸入您要模組使用的 Webhook。</p> <p>如需關於 Webhook 的詳細資訊，請參閱 <a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webhook</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 監視記錄]

建立或更新記錄時，此觸發程序模組便會啟動一個情境。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要建立的記錄類型。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 活動]</strong> </p> <p>選取您要監視的活動類型。 </p> <p>此模組只會監視新活動。<br></p> </li> 
     <li> <p><strong>[!UICONTROL 商機]</strong> </p> <p>在「<b>事件類型</b>」欄位中，選取您要監視新記錄、更新的記錄、新記錄以及更新的記錄，或是特定的欄位更新。若您選取監視特定欄位更新，請選取您要模組監視的欄位。</p> </li> 
     <li> <p><strong>[!UICONTROL 方案]</strong> </p> <p>在「<b>事件類型</b>」欄位中，選取您要監視新記錄、更新的記錄，或新記錄以及更新的記錄。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取要包含在此模組的輸出組合包中的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 將商機新增至清單]](#add-leads-to-a-list)
* [[!UICONTROL 原地複製一個方案]](#clone-a-program)
* [[!UICONTROL 建立記錄]](#create-a-record)
* [[!UICONTROL 自訂 API 呼叫]](#custom-api-call)
* [[!UICONTROL 下載檔案]](#download-a-file)
* [[!UICONTROL 讀取記錄]](#read-a-record)
* [[!UICONTROL 從清單中移除商機]](#remove-leads-from-a-list)
* [[!UICONTROL 安排行銷活動的時間]](#schedule-a-campaign)
* [[!UICONTROL 更新記錄]](#update-a-record)
* [[!UICONTROL 上傳檔案]](#upload-a-file)

#### [!UICONTROL 將商機新增至清單]

此動作模組使用商機 ID 將一個或多個商機新增至清單。一次最多可以新增 300 個商機。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 清單 ID]</td> 
   <td>輸入或對應您要新增商機的清單之 ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 商機 ID]</td> 
   <td> <p>對於您要新增至清單的每個商機，按一下「<b>[!UICONTROL 新增]</b>」，然後輸入或對應您要新增商機的 ID。您可以為模組新增最多 300 個商機以便加入清單中。</p> <p>按一下「對應切換」，對應您想要新增至清單中的現有商機集合。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 原地複製一個方案]

此動作模組使用現有的方案 ID 製作方案的副本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 現有的方案 ID]</td> 
   <td>輸入或對應您要複製的方案之 ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 新方案名稱]</p> </td> 
   <td> <p>輸入或對應新方案的名稱</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾 ID]</td> 
   <td>輸入或對應您要放置新方案的資料夾之 ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立記錄]

此動作模組在 [!DNL Marketo] 中建立新記錄

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要建立的記錄類型。</p> 
    <ul> 
     <li> <p>[!UICONTROL 公司]</p> </li> 
     <li> <p>[!UICONTROL 資料夾]</p> </li> 
     <li> <p>[!UICONTROL 商機]</p> </li> 
     <li> <p>[!UICONTROL 方案]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 選取要對應的欄位]</td> 
   <td>如果您要建立公司或商機，請選取在建立新記錄時要設定值的欄位，然後輸入這些欄位的值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方案類型]</td> 
   <td>如果您要建立方案，請選取您要建立的方案類型。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方案管道] </td> 
   <td>如果您要建立方案，請選取您要建立方案的方案管道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾]/[!UICONTROL 方案名稱]</td> 
   <td>如果您要建立資料夾或方案，請輸入或對應新記錄的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 說明]</td> 
   <td> <p>如果您要建立資料夾或方案，請輸入或對應新記錄的說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 上層資料夾 ID]</td> 
   <td>如果您要建立資料夾或方案，請輸入或對應您要建立新記錄之上層資料夾的 ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 成本]</td> 
   <td>如果您要建立方案，請新增任何成本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標記]</td> 
   <td>如果您要建立方案，請新增任何標記。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂 API 呼叫]

您可以利用此動作模組，對 [!DNL Marketo] API 進行已驗證的自訂呼叫。如此一來，您就可以建立其他 [!DNL Marketo] 模組無法完成的資料流程自動化。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於 <code>https://{your-base-url}.mktorest.com/</code> 的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
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
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td> <p>對於您要新增至 API 呼叫的每個欄位，按一下「<b>新增項目</b>」，然後輸入欄位的索引鍵和值。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 下載檔案]

此動作模組使用檔案 ID 下載檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案 ID]</td> 
   <td>輸入或對應您要下載的檔案之 ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組使用記錄的 ID 讀取其相關資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要建立的記錄類型。</p> 
    <ul> 
     <li> <p>[!UICONTROL 行銷活動]</p> </li> 
     <li> <p>[!UICONTROL 公司]</p> </li> 
     <li> <p>[!UICONTROL 商機]</p> </li> 
     <li> <p>[!UICONTROL 清單]</p> </li> 
     <li> <p>[!UICONTROL 方案]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取要包含在此模組的輸出組合包中的資訊。可用欄位根據您選取的[!UICONTROL 記錄類型]而定。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL &lt;物件&gt; ID]</td> 
   <td>輸入或對應您要檢索相關資訊之物件的 ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 從清單中移除商機]

此動作模組使用商機 ID 從清單中移除一個或多個商機。一次最多可以移除 300 個商機。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 清單 ID]</td> 
   <td>輸入或對應您要移除商機的清單之 ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 商機 ID]</td> 
   <td> <p>對於您要從清單移除的每個商機，按一下「<b>[!UICONTROL 新增項目]</b>」，然後輸入或對應您要移除之商機的 ID。您可以為模組新增最多 300 個商機，以便從清單中移除。 </p> <p>按一下「對應切換」，對應您要從清單中移除的現有商機集合。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 安排行銷活動的時間]

此動作模組安排現有的行銷活動在特定日期進行。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行銷活動 ID]</td> 
   <td>輸入或對應您要安排時間之行銷活動的 ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 安排日期]</p> </td> 
   <td>選取您要執行該行銷活動的日期。若此欄位留空，則行銷活動會在情境開始後 5 分鐘執行。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組使用現有記錄的 ID 來更新該記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要建立的記錄類型。</p> 
    <ul> 
     <li> <p>[!UICONTROL 公司]</p> </li> 
     <li> <p>[!UICONTROL 商機]</p> </li> 
     <li> <p>[!UICONTROL 方案]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 公司]/[!UICONTROL 商機]/[!UICONTROL 方案 ID]</td> 
   <td>輸入或對應您要更新之記錄的 ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 選取要對應的欄位]</td> 
   <td>如果您要更新公司或商機，請選取要更新值的欄位，然後輸入這些欄位的值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方案名稱]</td> 
   <td>如果您要更新方案，請輸入或對應方案的新名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 說明]</td> 
   <td> <p>如果您要更新方案，請輸入或對應方案的新說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 開始日期]</td> 
   <td>如果您要更新方案，請輸入或對應方案的新開始日期。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結束日期]</td> 
   <td>如果您要更新方案，請輸入或對應方案的新結束日期。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 成本]</td> 
   <td>如果您要更新方案，請新增任何成本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標記]</td> 
   <td>如果您要更新方案，請新增任何標記。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳檔案]

此動作模組上傳新檔案至 [!UICONTROL Marketo]。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾 ID]</td> 
   <td>輸入或對應您要放置新檔案之資料夾的 ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 說明]</td> 
   <td>輸入已上傳檔案的說明。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL 清單記錄]](#list-records)
* [[!UICONTROL 搜尋記錄]](#update-a-record)

#### [!UICONTROL 清單記錄]

此動作模組檢索特定類型的所有記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要列出清單的記錄類型。</p> 
    <ul> 
     <li> <p>[!UICONTROL 讀取所有行銷活動]</p> </li> 
     <li> <p>[!UICONTROL 讀取所有方案]</p> </li> 
     <li> <p>[!UICONTROL 讀取所有商機] </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td>若您已選取要檢索商機，請選取要從清單或是方案檢索商機。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取要包含在此模組的輸出組合包中的資訊。可用欄位根據您選取的[!UICONTROL 記錄類型]而定。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋記錄]

此搜尋模組檢索符合特定搜尋條件的記錄清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>關於將您的 [!DNL Marketo] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將 [!DNL Marketo] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要搜尋的記錄類型。</p> 
    <ul> 
     <li> <p>[!UICONTROL 行銷活動]</p> </li> 
     <li> <p>[!UICONTROL 商機]</p> </li> 
     <li> <p>[!UICONTROL 方案]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 欄位]</p> </td> 
   <td> <p>選取您要搜尋的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 值]</td> 
   <td>輸入您要搜尋的欄位的值。若欄位可以搜尋多個值，對於您要搜尋的每個值，按一下「<b>[!UICONTROL 新增項目]</b>」並輸入值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取要包含在此模組的輸出組合包中的資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

---
title: Adobe Workfront 模組
description: 您可以使用 Adobe Workfront Fusion Adobe Workfront 連接器，在 Workfront 內部將流程自動化。若您具備 Workfront Fusion for Work Automation and Integration 授權，也可以使用此授權連接至第三方應用程式和服務。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 93c27cf6-38b0-466c-87bb-926c4817eae7
source-git-commit: ab12dbf0dbad25a8300eb1201fa3e0fde9148acc
workflow-type: tm+mt
source-wordcount: '7366'
ht-degree: 99%

---

# Adobe Workfront 模組

>[!IMPORTANT]
>
>這篇文章包含 2025 年 10 月 22 日發行的新版本 Workfront 連接器的說明。此新連接器會反映對 Workfront API 所做的變更。
>
>新的連接器會標示為「Workfront」，而先前可用的連接器會標示為「Workfront (舊版)」。
>
>我們建議您：
>
>* 在建立或更新情境時使用新連接器。
>* 將現有模組升級為使用新連接器。
>
>舊版 Workfront 連接器使用 Workfront API 版本 20，此版本預計在 28.4 版本發行時 (2028 年 4 月) 棄用。舊版連接器中的模組將持續運作，直到上述時間為止。
>
>關於升級現有模組的說明，請參閱「將模組升級為新版本」文章中的[將 Workfront 模組升級為新版本](/help/workfront-fusion/manage-scenarios/update-module-to-new-version.md)。
>
>關於為什麼有時會需要新連接器的資訊，請參閱 [Fusion 中的 API 概觀](/help/workfront-fusion/get-started-with-fusion/understand-fusion/api-overview.md)。

您可以使用 Adobe Workfront Fusion Adobe Workfront 連接器，在 Workfront 內部將流程自動化。您也可以將 Workfront 連接至其他應用程式和服務。

關於建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)之下的文章。關於模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)之下的文章。

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
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 將Workfront連線至Workfront Fusion

Workfront 連接器使用 OAuth 2.0 連接至 Workfront。

您可以直接從 Workfront Fusion 模組內部建立與 Workfront 帳戶的連線。

* [使用用戶端 ID 和用戶端密碼連接至 Workfront](#connect-to-workfront-using-client-id-and-client-secret)
* [使用伺服器對伺服器連線連接 Workfront](#connect-to-workfront-using-a-server-to-server-connection)

### 使用用戶端 ID 和用戶端密碼連接至 Workfront

1. 在任何 Adobe Workfront 模組中，按一下「連線」欄位旁的「**新增**」。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線類型]</td>
        <td>
          <p>選取「<b>Adobe Workfront 驗證連線</b>」。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的 Workfront 用戶端 ID。您可在 Workfront「設定」區域的「OAuth2 應用程式」區域內找到此項資訊。開啟您要連接的特定應用程式以便查看用戶端 ID。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的 Workfront 用戶端密碼。您可在 Workfront「設定」區域的「OAuth2 應用程式」區域內找到此項資訊。如果您在 Workfront 的 OAuth2 應用程式沒有用戶端密碼，您可以產生另一個密碼。相關說明請參閱 Workfront 文件。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 驗證 URL]</td>
        <td>此欄位可維持預設值，或者您可以輸入 Workfront 實例的 URL 且後面接著 <code>/integrations/oauth2</code>。 <p>範例： <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 主機前置詞]</td>
        <td>在大多數情況下，此值應為 <code>origin</code>。
      </tr>
    </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

   若您未登入 Workfront，系統會將您導向至登入畫面。登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API 的 OAuth 2.0 連線不再依賴 API 金鑰。
>* 若要建立與 Workfront 沙箱環境的連線，您必須在該環境中建立 OAuth2 應用程式，然後在您的連線中使用該應用程式產生的用戶端 ID 和用戶端密碼。

### 使用伺服器對伺服器連線連接 Workfront

1. 在任何 Adobe Workfront 模組中，按一下「連線」欄位旁的「**新增**」。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線類型]</td>
        <td>
          <p>選取「<b>Adobe Workfront 伺服器對伺服器連線</b>」。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 執行個體名稱]</td>
        <td>
          <p>輸入執行個體的名稱，也是您的網域。</p><p>範例：若您的 URL 為 <code>https://example.my.workfront.com</code>，請輸入 <code>example</code>。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 執行個體路徑]</td>
        <td>
          <p>輸入此連線將連接的環境類型。</p><p>範例：若您的 URL 為 <code>https://example.my.workfront.com</code>，請輸入 <code>my</code>。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的 Workfront 用戶端 ID。您可在 Workfront「設定」區域的「OAuth2 應用程式」區域內找到此項資訊。開啟您要連接的特定應用程式以便查看用戶端 ID。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的 Workfront 用戶端密碼。您可在 Workfront「設定」區域的「OAuth2 應用程式」區域內找到此項資訊。如果您在 Workfront 的 OAuth2 應用程式沒有用戶端密碼，您可以產生另一個密碼。相關說明請參閱 Workfront 文件。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 範圍]</td>
        <td>輸入此連線的適用範圍。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 主機前置詞]</td>
        <td>在大多數情況下，此值應為 <code>origin</code>。
      </tr>
    </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

   若您未登入 Workfront，系統會將您導向至登入畫面。登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API 的 OAuth 2.0 連線不再依賴 API 金鑰。
>* 若要建立與 Workfront 沙箱環境的連線，您必須在該環境中建立 OAuth2 應用程式，然後在您的連線中使用該應用程式產生的用戶端 ID 和用戶端密碼。

## Workfront 模組及其欄位

當您設定 Workfront 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 Workfront 欄位。在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。


![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* 若您在 Workfront 模組中未看到最新的欄位，可能是因為快取問題。請等待一小時，然後再試一次。
>* Adobe Workfront 發出的 HTTP 429 狀態代碼不應導致停用，而是在情境中觸發短暫的執行暫停。

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

<!--
* [Watch Events](#watch-events) 
* [Watch Record](#watch-record) 
* [Watch Field](#watch-field)
-->

+++ **[!UICONTROL 監視事件]**

在Workfront中新增、更新或刪除特定型別的物件時，此觸發模組會即時執行案例。

模組會顯示與webhook相關的所有事件訂閱。 這包括透過Fusion建立的事件訂閱，以及直接透過API建立的事件訂閱。 舊版Watch Events模組不提供此事件訂閱檢視。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。您可以在情境內之後的模組中對應此資訊。

1. 按一下「**Webhook**」方框右側的「**[!UICONTROL 新增]**」。

1. 在所顯示的「**[!UICONTROL 新增鉤子]**」方框中設定 Webhook。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Webhook 名稱]</td> 
      <td>輸入 Webhook 的名稱</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL 連線]</td> 
      <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL 記錄類型]</td> 
      <td>選取您要模組監視的 Workfront 記錄類型。</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL 狀態]</td> 
      <td>選取您要監視舊狀態或新狀態。<ul><li><p><b>[!UICONTROL 新狀態]</b></p><p>當記錄變更<b>為</b>特定值時觸發一個情境。</p><p>例如，若狀態設定為「[!UICONTROL 新狀態]」而篩選器設定為「[!UICONTROL 狀態] [!UICONTROL 等於] [!UICONTROL 進行中]」，則當「[!UICONTROL 狀態]」變更為「[!UICONTROL 進行中]」時，無論先前的狀態為何，Webhook 會觸發一個情境。 </p></li><li><p><b>[!UICONTROL 舊狀態]</b></p><p>當記錄<b>從</b>特定值變更為其他時會觸發一個情境。</p><p>例如，若狀態設定為「[!UICONTROL 舊狀態]」而篩選器設定為「[!UICONTROL 狀態] [!UICONTROL 等於] [!UICONTROL 進行中]」，則當目前為「[!UICONTROL 進行中]」的「[!UICONTROL 狀態]」變更為其他狀態時，Webhook 會觸發一個情境。 </p></li></ul></td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL 事件篩選器]</p> </td> 
      <td> <p>您可以設定篩選器為僅監視符合所選取條件的記錄。</p> <p>對於每個篩選器，輸入您要篩選器評估的欄位、運算子，以及要讓篩選器允許的值。您可以新增 AND 規則，以便使用一個以上的篩選器。</p> <p><b>注意</b>：您無法編輯現有 Workfront Webhook 中的篩選器。若要為 Workfront 事件訂閱設定不同的篩選器，請移除目前的 Webhook 並建立新的。</p> <p>關於事件篩選器的詳細資訊，請參閱這篇文章中的 <a href="#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">Workfront 中的事件訂閱篩選器 &gt; [!UICONTROL 監視事件]模組</a>。</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td>排除此連線所造成的事件</td> 
      <td>啟用此選項，以便排除使用與此觸發程序模組相同的連接器所建立或更新的事件。這樣可以避免情境可能觸發自身，導致其在無限迴圈中重複的情況。<p><b>注意</b>：指派記錄類型不包含此選項。</p></td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL 記錄來源]</td> 
      <td>
       <p>選擇您想要情境監視「[!UICONTROL 僅限新記錄]」、「[!UICONTROL 僅限更新的記錄]」、「[!UICONTROL 新記錄以及更新的記錄]」或者「[!DNL Deleted Records Only]。」</p>
       <p><b>注意</b>：若選擇「[!UICONTROL 新記錄以及更新的記錄]」，建立 Webhook 時會建立 2 個事件訂閱 (但使用相同的 Webhook 位址)。</p>
       </td> 
     </tr> 
    </tbody> 
   </table>



   <!--Markdown 0032 placeholder-->

建立 Webhook 後，您可以檢視事件傳送目標端點的位址。

如需詳細資訊，請參閱 Workfront 文件中「事件訂閱 API」文章中的[事件承載範例](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-api#examples-of-event-payloads)區段。

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

+++

+++ **[!UICONTROL 監視欄位]**

當您指定的欄位更新時，此觸發程序模組會執行一個情境。模組會同時傳回指定欄位舊的值和新的值。您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要模組監視的 Workfront 記錄類型。</p> <p>例如，若您要在每次任務中的記錄欄位更新時開始執行情境，請選取「[!UICONTROL 任務]」。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 欄位]</td> 
   <td>選取您要模組監視其更新的欄位。這些欄位反映 Workfront 管理員為了追蹤而設定的欄位。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 輸出]</td> 
   <td>選取要包含在此模組的輸出組合包中的物件欄位。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

+++

+++ **[!UICONTROL 監視記錄]**

此觸發程序模組會在新增、更新或是同時新增和更新特定類型的物件時執行情境。模組會傳回與記錄相關聯的所有標準欄位，以及連線存取的任何自訂欄位和值。您可以在情境內之後的模組中對應此資訊。

在輸出中，模組會指出每個記錄是新記錄或是更新的記錄。

自上次執行情境後新增和更新的記錄會傳回為新記錄。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td> <p>選擇情境要監視「[!UICONTROL 僅限新記錄]」、「[!UICONTROL 僅限更新的記錄]」或者「[!UICONTROL 新記錄以及更新的記錄]」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要模組監視的 Workfront 記錄類型。</p> <p>例如，若您要在每次建立新專案時啟動情境，請選取「[!UICONTROL 專案]」</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取要包含在此模組的輸出組合包中的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 參考資料]</td> 
   <td> <p>選取要包含在此模組的輸出組合包中的參考資料欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取要包含在此模組的輸出組合包中的集合欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 選用篩選器]</td> 
   <td> <p>(進階) 輸入 API 程式碼字串，定義用於縮小條件範圍的任何其他參數或程式碼。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

+++


### 動作

<!--
* [Convert object](#convert-object) 
* [Create a record (attaching custom forms)](#create-a-record-attaching-custom-forms) 
* [Create a record](#create-a-record) 
* [Custom API Call](#custom-api-call) 
* [Delete Record](#delete-record) 
* [Download Document](#download-document) 
* [Misc Action](#misc-action) 
* [Read a Record](#read-a-record) 
* [Update Record](#update-record) 
* [Upload Document](#upload-document)
-->

+++ **[!UICONTROL 轉換物件]**

此動作模組會進行下列其中一種轉換：

* 將問題轉換成專案
* 將問題轉換成任務
* 將任務轉換成專案

>[!NOTE]
>
>自 2024 年 7 月起，轉換物件時可包含自訂表單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 物件類型]</td> 
   <td> <p>選取您要轉換的物件類型。這是物件在轉換之前的類型。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 轉換成]</td> 
   <td>選取您要轉換成哪一種物件。這是物件在轉換之後的類型。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL &lt;物件&gt; ID]</td> 
   <td> <p>輸入物件的 ID。 </p> <p>注意：輸入物件的 ID 時，您可以開始輸入物件的名稱，然後從清單中選取。然後模組會在欄位中輸入適當的 ID。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 範本 ID]</td> 
   <td> <p>若要轉換成專案，請選取您要用於專案的範本 ID。</p> <p>注意：輸入物件的 ID 時，您可以開始輸入物件的名稱，然後從清單中選取。然後模組會在欄位中輸入適當的 ID。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 自訂表單]</td> 
   <td>選取您要新增至新轉換物件的任何自訂表單，然後在自訂表單的欄位中輸入值。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 選項]</td> 
   <td> <p>啟用轉換物件時所需的任何選項。可用選項取決於您要轉換成哪種物件或是從哪種物件進行轉換。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 複製原生欄位]</td> 
   <td> <p>啟用此選項，可將原始物件中的任何原生欄位複製到新物件。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 複製自訂表單]</td> 
   <td> <p>啟用此選項，可將原始物件中的任何原生欄位複製到新物件。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 建立記錄]** 

此動作模組會建立物件，例如 Workfront 中的專案、任務或問題，並讓您在新物件中新增自訂表單。您可以透過模組選取在模組中可以使用物件的哪些欄位。

您指定記錄的 ID。

模組會傳回記錄的 ID 和任何相關欄位，以及連線存取的任何自訂欄位和值。您可以在情境內之後的模組中對應此資訊。

請務必提供最少數量的輸入欄位。例如，若您要建立問題，則需要在「專案 ID」欄位中提供有效的上層專案 ID，以便指出問題在 Workfront 中應存放在哪裡。您可以使用對應面板來對應來自情境中另一個模組的這些資訊，或是輸入名稱然後從清單中選取，以手動方式輸入資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要模組建立的 Workfront 記錄類型。</p> <p>例如，若您要建立專案，請從下拉式清單中選取「[!UICONTROL 專案]」。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 選取要對應的欄位]</td> 
   <td> <p>選取可供輸入資料的欄位。這樣一來，您可以使用這些欄位，但是不需要捲動瀏覽不需要的欄位。接著，您可以在這些欄位中輸入或對應資料。</p> <p>對於自訂表單中的欄位，請使用「<b>[!UICONTROL 附加自訂表單]</b>」欄位。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 附加自訂表單]</td> 
   <td>選取您要新增至新物件的任何自訂表單，接著選取要輸入值的欄位，然後輸入或對應這些欄位的值。</td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

>[!NOTE]
>
>* 輸入物件的 ID 時，您可以開始輸入物件的名稱，然後從清單中選取。然後模組會在欄位中輸入適當的 ID。
>* 輸入自訂欄位或[!UICONTROL 備註]物件 (註解或回覆) 的文字時，您可以在「[!UICONTROL 備註文字]」欄位中使用 HTML 標記來建立 RTF 文字，例如粗體或斜體文字。
>



>[!NOTE]
>
>所建立的使用者皆是「已停用」和「待核准」的狀態。如果您的組織已移轉至 Adobe Admin Console，但在幾分鐘內「待核准」徽章並未移除，您可以核准使用者。
>
>* **解析個別使用者**
>
>      您可以解析使用者清單中的個別使用者。
>
>      1. 在使用者清單中選取一個或多個使用者。
>      1. 按一下清單標頭中的三點選單。
>      1. 選取「**核准**」。
>      1. 幾分鐘後，重新整理頁面。
>
>* **解析大批新增的使用者**
>
>   若要解析大批新增的使用者，您可以直接將該批次的使用者新增至 Adobe Admin Console。
>
>   相關說明請參閱 Adobe 文件中的[管理多個使用者 | 上傳大量 CSV](https://helpx.adobe.com/tw/enterprise/using/bulk-upload-users.html)。

+++

<!--

+++ **[!UICONTROL Create Record (Legacy)]**

>[!IMPORTANT]
>
>This module has been replaced with the Create a record module. We recommend using that module in new scenarios.
>Existing scenarios that use this module will continue to function as expected. This module will be removed from the module selector in May 2025.

This action module creates an object, such as a project, task, or issue in Workfront. The module allows you to select which of the object's fields are available in the module.

You specify the ID of the record.

The module returns the ID of the  record and any associated fields, along with any custom fields and values that the connection accesses. You can map this information in subsequent modules in the scenario.

Make sure you provide the minimum number of input fields. For example, if you want to create an issue, you need to provide a valid parent project ID in the Project ID field to indicate where the issue should live in Workfront. You can use the mapping panel to map this information from another module in your scenario, or you can enter it manually by typing in the name and then selecting it from the list.

This module does not attach custom forms when creating the object. To attach custom forms while creating an object, use the [!UICONTROL Create a record (attaching custom forms)] module.

When you are configuring this module, the following fields display.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to create.</p> <p>For example, if you want to create a Project, select [!UICONTROL Project] from the dropdown list.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Select fields to map]</td> 
   <td>Select the fields that you want available for data input. This allows you to use these fields without having to scroll through the ones you don't need.</td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* When entering the ID of an object, you can begin typing the name of the object, then select it from the list. The module then enters the appropriate ID into the field.
>* When entering the text for a custom field or a [!UICONTROL Note] object (Comment or reply), you can use HTML tags in the [!UICONTROL Note Text] field to create rich text, such as bold or italic text.

+++

-->

+++ **[!UICONTROL 自訂 API 呼叫]**

您可以利用此動作模組，對 Workfront API 進行已驗證的自訂呼叫。如此一來，您就可以建立其他 Workfront 模組無法完成的資料流程自動化。

模組會傳回以下資訊：

* **[!UICONTROL 狀態代碼]** (數字)：此代碼表示您的 HTTP 要求是成功或失敗。您可以在網際網路上查閱這些標準代碼。
* **[!UICONTROL 標頭]** (物件)：與輸出正文無關之回應/狀態代碼的更詳細內容。並非顯示在回應標頭中的所有標頭都是回應標頭，因此有一部分對您而言可能並無用處。

  回應標頭取決於您在設定模組時所選擇的 HTTP 要求。

* **[!UICONTROL 正文]** (物件)：根據您在設定模組時所選擇的 HTTP 要求，您可能會收到一些傳回的資料。該資料 (例如來自 GET 請求的資料) 會包含在此物件中。

您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>輸入相對於 <code> https://&lt;WORKFRONT_DOMAIN&gt;/attask/api/&lt;API_VERSION&gt;/</code> 的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API 版本]</td> 
   <td>選取您要模組使用的 Workfront API 版本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion 中的 HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。此資訊會決定請求的內容類型。</p> <p>例如，<code> {"Content-type":"application/json"}</code></p> <p>注意：如果您收到錯誤訊息而且無法判斷其來源，請考慮根據 Workfront 文件修改標頭。如果您的自訂 API 呼叫傳回 422 HTTP 要求錯誤，請嘗試使用 <code>"Content-Type":"text/plain"</code> 標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> <p>提示：建議您透過 JSON 正文而非查詢參數傳送資訊。</p> </td> 
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

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

+++

+++ **[!UICONTROL 刪除記錄]**

此動作模組會刪除物件，例如 Workfront 中的專案、任務或問題。

您指定記錄的 ID。

模組會傳回記錄的 ID 和任何相關欄位，以及連線存取的任何自訂欄位和值。您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 強制刪除]</td> 
   <td>啟用此選項確保刪除記錄，即使 Workfront 使用者介面會請求確認刪除。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 非同步刪除]</td> 
   <td>啟用此選項，允許模組採非同步方式刪除。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>ID</td> 
   <td> <p>輸入您要模組刪除之記錄的唯一 Workfront ID。</p> <p>若要取得 ID，請在瀏覽器中開啟 Workfront 物件，並複製 URL 結尾在「ID=」之後的文字。例如：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄類型]</td> 
   <td>選取您要模組刪除的 Workfront 記錄類型。</td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

>[!NOTE]
>
>我們建議使用下列情境設定，以避免可能因為非同步作業而無法刪除記錄。
>
>1. 同步刪除記錄。
>1. 將錯誤處理新增至刪除記錄模組，以便忽略因為 40 秒逾時造成的錯誤。


+++

+++ **[!UICONTROL 下載文件]**

此動作模組會從 Workfront 下載文件。

您指定記錄的 ID。

模組會傳回文件的內容、檔案名稱、副檔名和檔案大小。您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 文件 ID]</td> 
   <td> <p>對應或手動輸入您要模組下載的檔案之唯一 Workfront ID。</p> <p>若要取得 ID，請在瀏覽器中開啟 Workfront 物件，並複製 URL 結尾在「ID=」之後的文字。例如：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

+++

### **取得預先簽署的檔案 URL**

此動作模組會取得預先簽署的檔案 URL，稍後可供其他 API 使用。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 文件 ID]</td> 
   <td> <p>對應或手動輸入您要取得預先簽署 URL 之檔案的唯一 Workfront ID。</p> <p>若要取得 ID，請在瀏覽器中開啟 Workfront 物件，並複製 URL 結尾在「ID=」之後的文字。例如：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL 過期時間]</td> 
   <td> <p>輸入或對應此 URL 在過期前存在的分鐘數。預設值為 1 分鐘。</p><p>若要變更此值，您必須讓 Workfront Fusion 團隊啟用此參數。若未啟用，則無論您輸入什麼數字，此值都將維持 1 分鐘。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++ **[!UICONTROL 其他動作]**

此動作模組讓您對 API 執行動作。

>[!NOTE]
>
>自 2024 年 7 月起，`convertToProject` 動作包含欄位 `copyCategories`。設定為 `TRUE` 時，所有自訂表單都將包含在由問題轉換而成的專案中。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 記錄類型]</td> 
   <td> <p>選取模組要與之互動的 Workfront 記錄類型。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 動作]</td> 
   <td> <p>選取您要模組執行的動作。</p> <p>視您選擇的「[!UICONTROL 記錄類型]」和「[!UICONTROL 動作]」而定，可能需要填寫其他欄位。這兩項設定的部分組合可能只需要記錄 ID，而其他設定 (例如「<strong>[!UICONTROL 記錄類型]</strong>」為專案以及「<strong>[!UICONTROL 動作]」</strong>為「[!UICONTROL 附加範本]」) 則需要其他資訊 (例如物件 ID 和範本 ID)。</p><p>關於部分動作可用的選項，請參閱這篇文章中的<a href="#misc-action-options" class="MCXref xref">其他動作選項</a>。</p> <p>關於個別欄位的詳細資訊，請參閱 <a href="http://developer.workfront.com/">Workfront 開發人員文件</a>。 <p><strong>注意</strong>：開發人員文件網站僅包含至 API 版本 14 為止的資訊，但仍包含 API 呼叫的重要資訊。 </p> 
    <ol> 
     <li value="1"> <p>在 Workfront 開發人員文件頁面的左側導覽區中選取記錄類型。下列類型有其專屬頁面：</p> 
      <ul> 
       <li> <p>[!UICONTROL 專案]</p> </li> 
       <li> <p>[!UICONTROL 任務]</p> </li> 
       <li> <p>[!UICONTROL 問題]</p> </li> 
       <li> <p>[!UICONTROL 使用者]</p> </li> 
       <li> <p>[!UICONTROL 文件]</p> </li> 
      </ul> <p>針對所有其他記錄類型，請選取「<b>[!UICONTROL 其他物件和端點]</b>」，然後在依字母順序排序的頁面上尋找記錄類型。</p> </li> 
     <li value="2"> <p>在適當記錄類型的頁面上搜尋 (Ctrl-F 或 Cmd-F) 該動作。</p> </li> 
     <li value="3"> <p>檢視所選動作之下可用欄位的說明。</p> </li> 
    </ol> <p>注意：  <p>透過 Workfront [!UICONTROL 其他動作]模組建立校訂時，最佳做法是建立不含任何進階選項的校訂，然後使用 [!DNL Workfront Proof] SOAP API 更新校訂。</p><p>關於使用 Workfront API (此模組所使用) 建立校訂的詳細資訊，請參閱<a href="https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/tips-troubleshooting-apis/api-create-proof-options-json" class="MCXref xref">透過 Adobe Workfront API 建立校訂時新增進階校訂選項</a></p> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td>輸入或對應模組要與其互動之記錄的不重複 Workfront ID。<p>若要取得 ID，請在瀏覽器中開啟 Workfront 物件，並複製 URL 結尾在「ID=」之後的文字。例如：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p></td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

#### 其他動作選項

##### 任務

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>動作</th> 
   <th>選項</th> 
  </tr> 
  <tr> 
   <td>複製</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearConstraints</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>清除提醒通知</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>移動</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearDocuments</li>
   <li>clearConstraints</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>清除提醒通知</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

##### 問題

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>動作</th> 
   <th>選項</th> 
  </tr> 
  <tr> 
   <td>複製</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearPermissions</li>
   <li>clearProgress</li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>轉換成任務</td> 
   <td>
   <ul>
   <li>preserveIssue<p>保留原始問題並將其解決方案連結至此任務</p></li>
   <li>preservePrimaryContact<p>允許問題的主要聯絡人存取此任務</p></li>
   <li>preserveCompletionDate<p>維持問題的規劃完成日期</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>轉換成專案</td> 
   <td>
   <ul>
   <li>preserveIssue<p>保留原始問題並將其解決方案連結至此任務</p></li>
   <li>preservePrimaryContact<p>允許問題的主要聯絡人存取此任務</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



##### 專案

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <th>動作</th> 
   <th>選項</th> 
  </tr> 
  <tr> 
   <td>複製</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearPermissions</li>
   <li>clearPredecessors</li>
   <li>clearProgress</li>
   <li>clearTimedNotifications<p>清除提醒通知</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>附加範本/另存為範本</td> 
   <td>
   <ul>
   <li>clearApprovers</li>
   <li>clearAssignments</li>
   <li>clearBillingRates</li>
   <li>clearConstraints</li>
   <li>clearDeliverables<p>清除目標</p></li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearHourTypes</li>
   <li>clearIssueSetup<p>清除佇列屬性和問題設定</p></li>
   <li>clearPredecessors</li>
   <li>clearRisks</li>
   <li>clearSharingOptions</li>
   <li>clearTimedNotifications<p>清除提醒通知</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



+++

+++ **[!UICONTROL 讀取記錄]**

此動作模組會從單一記錄檢索資料。

您指定記錄的 ID。您也可以指定您要模組讀取的相關記錄。

例如，若模組正在讀取的記錄為專案，您可以指定要讀取專案的任務。

模組會傳回取自您指定的輸出欄位的資料陣列。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL 連線]</td>
    <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 記錄類型]</td>

<td>選擇您要模組讀取的 Workfront 物件類型。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 輸出]</td>

<td> <p>選取要包含在此模組的輸出組合包中的資訊。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 輸出自訂表單]</td>
     <td> <p>選取要包含在此模組的輸出組合包中的自訂表單，然後從要包含在輸出中的自訂表單選取特定欄位。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 參考資料]</td>
   <td>選取您要包含在輸出中的任何參考資料欄位。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 集合]</td>
   <td>選取您要包含在輸出中的任何參考資料欄位。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>輸入您要模組讀取之記錄的唯一 Workfront ID。</p> <p>若要取得 ID，請在瀏覽器中開啟 Workfront 物件，並複製 URL 結尾在「ID=」之後的文字。例如：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

+++

<!--

+++ **[!UICONTROL Read a Record (Legacy)]**

>[!IMPORTANT]
>
>This module has been replaced with the Read a record module. We recommend using that module in new scenarios.
>Existing scenarios that use this module will continue to function as expected. This module will be removed from the module selector in May 2025.

This action module retrieves data from a single record.

You specify the ID of the record. You can also specify which related records you want the module to read.

For example, if the record that the module is reading is a project, you can specify that you want the project's tasks read.

The module returns an array of data from the output fields you specified.

When you are configuring this module, the following fields display.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>
  
   <td>Choose the Workfront object type that you want the module to read.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>
  
   <td> <p>Select the information you want included in the output bundle for this module.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL References]</td>
   <td>Select any reference fields that you want to include in the output.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Collections]</td>
   <td>Select any reference fields that you want to include in the output.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>Enter the unique Workfront ID of the record that you want the module to read.</p> <p>To get the ID, open the Workfront object in your browser and copy the text at the end of the URL after "ID=." For example: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).

+++

-->

+++ **更新事件承載版本**

Workfront 最近發行新版本的事件訂閱服務。新版本並非對 Workfront API 有所變更，而是變更事件訂閱功能。此動作模組會更新此情境所使用的事件承載版本。

關於事件訂閱新版本的詳細資訊，請參閱 Workfront 文件中的[事件訂閱版本設定](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning)

關於在事件訂閱升級期間保留 Workfront Fusion 情境的資源，包括網路研討會錄影，請參閱[在事件訂閱 V2 升級期間保留 Fusion 情境](https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182)。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 版本]</td> 
   <td> 選取您要用於此承載的事件訂閱版本。 </td> 
  </tr> 
 </tbody> 
</table>


+++

+++ **更新記錄**


此動作模組會更新物件，例如專案、任務或問題。您可以透過模組選取在模組中可以使用物件的哪些欄位。

您指定記錄的 ID。

模組會傳回物件的 ID 和任何相關欄位，以及連線存取的任何自訂欄位和值。您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>輸入您要模組更新之記錄的唯一 Workfront ID。</p> <p>若要取得 ID，請在瀏覽器中開啟 Workfront 物件，並複製 URL 結尾在「ID=」之後的文字。例如：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>選取您要模組更新的 Workfront 記錄類型。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>選取可供輸入資料的欄位。這樣一來，您可以使用這些欄位，但是不需要捲動瀏覽不需要的欄位。接著，您可以在這些欄位中輸入或對應資料。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Attach Custom Form]</td> 
   <td>選取您要在新記錄上提供欄位值的自訂表單。選取表單後，在表單上的欄位中輸入資料。<p> 若要對您附加在此模組的表單提供欄位值，需包含欄位中的自訂表單 ID 才能對應區段。</td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

>[!NOTE]
>
> 輸入自訂欄位或[!UICONTROL 備註]物件 (註解或回覆) 的文字時，您可以在「[!UICONTROL 備註文字]」欄位中使用 HTML 標記來建立 RTF 文字，例如粗體或斜體文字。


+++

<!--

+++ **[!UICONTROL Update Record (Legacy)]**

>[!IMPORTANT]
>
>This module has been replaced with the Update a record module. We recommend using that module in new scenarios.
>Existing scenarios that use this module will continue to function as expected. This module will be removed from the module selector in May 2025.

This action module updates an object, such as a project, task, or issue. The module allows you to select which of the object's fields are available in the module.

You specify the ID of the record.

The module returns the ID of the  object and any associated fields, along with any custom fields and values that the connection accesses. You can map this information in subsequent modules in the scenario.

When you are configuring this module, the following fields display.

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>Enter the unique Workfront ID of the record that you want the module to update.</p> <p>To get the ID, open the Workfront object in your browser and copy the text at the end of the URL after "ID=." For example: https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to update.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>Select the fields that you want available for data input. This allows you to use these fields without having to scroll through the ones you don't need. You can then enter or map data into these fields.</td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).

>[!NOTE]
>
>* When entering the ID of an object, you can begin typing the name of the object, then select it from the list. The module then enters the appropriate ID into the field.
>* When entering the text for a custom field or a [!UICONTROL Note] object (Comment or reply), you can use HTML tags in the [!UICONTROL Note Text] field to create rich text, such as bold or italic text.

+++

-->

+++ **[!UICONTROL 上傳文件]**

此動作模組會將文件上傳至 Workfront 物件，例如專案、任務或問題。此模組會以區塊形式上傳文件，讓 Workfront 的上傳流程更為順暢。

此模組能夠處理比舊版模組更大的檔案，而且是採分階段方式向擁有 Ultimate Workfront 封裝的組織推出實施。

您可以指定文件的位置、要上傳的檔案，以及可供檔案選用的新名稱。

模組會傳回文件的 ID 和任何相關欄位，以及連線存取的任何自訂欄位和值。您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 關聯的記錄 ID]</td> 
   <td>輸入您要上傳文件的那個記錄的不重複 Workfront ID。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 關聯的記錄類型]</td> 
   <td>選取模組要上傳文件的目標位置之 Workfront 記錄類型。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾 ID]</td> 
   <td>視關聯記錄的類型而定，您可能需要輸入或對應資料夾 ID。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

在[各 Workfront 模組可用的 Workfront 物件類型](#workfront-object-types-available-for-each-workfront-module)中查看可使用此模組的 Workfront 物件類型清單。

+++

<!--

+++ **[!UICONTROL Upload Document (Legacy)]**

This action module uploads a document to a Workfront object, such as a project, task, or issue. It uploads the entire document at once. 

You specify the location for the document, the file you want to upload, and an optional new name for the file.

The module returns the ID of the document and any associated fields, along with any custom fields and values that the connection accesses. You can map this information in subsequent modules in the scenario.

When you are configuring this module, the following fields display.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Related Record ID]</td> 
   <td>Enter the unique Workfront ID of the record to which you want to upload the document.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Related Record Type]</td> 
   <td>Select the type of Workfront record where you want the module to upload the document.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder ID]</td> 
   <td>Depending on the type of related record, you may need to enter or map a folder ID.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).


+++
-->

### 搜尋

<!--
* [Read Related Records](#read-related-records) 
* [Search](#search)
-->

+++ **[!UICONTROL 讀取關聯的記錄]**

此搜尋模組會讀取在特定上層物件中，符合您指定之搜尋查詢的記錄。

您指定在輸出中要包含哪些欄位。您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要讀取其關聯記錄的上層記錄 (Workfront 物件) 類型。</p> <p>在這篇文章的<a href="#object-types-available-for-each-workfront-search-module" class="MCXref xref">各 Workfront 模組可用的 Workfront 物件類型</a>中查看可使用此模組的 Workfront 物件類型清單。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 上層記錄 ID]</td> 
   <td> <p>輸入或對應您要讀取其關聯記錄的上層記錄的 ID。</p> <p>若要取得 ID，請在瀏覽器中開啟 Workfront 物件，並複製 URL 結尾在「ID=」之後的文字。例如：https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 集合]</td> 
   <td>選取或對應您要模組讀取的下層記錄類型。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 輸出]</td> 
   <td> <p>選取要包含在此模組的輸出組合包中的資訊。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 搜尋]**

此搜尋模組會在 Workfront 中尋找物件中符合您指定之搜尋查詢的記錄。

您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要模組搜尋的 Workfront 記錄類型。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 自訂表單清單]</td> 
   <td> <p>選取至少一個自訂表單。這些自訂表單中的欄位將可用於搜尋查詢。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 結果集]</td> 
   <td>選取一個選項，指定模組要取得符合搜尋條件的第一個結果，或是取得符合該條件的所有結果。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 最大值]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件欄位]</td> 
   <td> <p>選取您要用於搜尋條件的欄位。隨後在搜尋條件下拉式選單中可使用這些欄位。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件]</td> 
   <td> <p>輸入您要搜尋的欄位、要在查詢中使用的運算子，以及要在欄位中搜尋的值。</p> <p>注意：請勿在您的搜尋條件中使用 <code>username </code>。若在對 Workfront 進行的 API 查詢中加入 <code>username </code>，使用者便會登入 Workfront，而搜尋不會成功。</p> <p>注意：<code>In</code> 和 <code>NotIn</code> 可搭配陣列使用。輸入應使用陣列的格式。</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 輸出]</td> 
   <td> <p>選取您要包含在此模組的輸出中的欄位。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 參考資料]</td> 
   <td>選取您要包含在搜尋中的任何參考資料欄位。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 集合]</td> 
   <td>選取您要新增至搜尋的任何集合。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 搜尋 (舊版)]**

>[!IMPORTANT]
>
>搜尋記錄模組已經取代這個模組。我們建議在新情境中使用該模組。
>使用這個模組的現有情境將繼續如常運作。這個模組將在 2025 年 5 月從模組選擇器中移除。

此搜尋模組會在 Workfront 中尋找物件中符合您指定之搜尋查詢的記錄。

您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄類型]</td> 
   <td> <p>選取您要模組搜尋的 Workfront 記錄類型。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 結果集]</td> 
   <td>選取一個選項，指定模組要取得符合搜尋條件的第一個結果，或是取得符合該條件的所有結果。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 最大值]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件欄位]</td> 
   <td> <p>選取您要用於搜尋條件的欄位。隨後在搜尋條件下拉式選單中可使用這些欄位。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件]</td> 
   <td> <p>輸入您要搜尋的欄位、要在查詢中使用的運算子，以及要在欄位中搜尋的值。</p> <p>注意：請勿在您的搜尋條件中使用 <code>username </code>。若在對 Workfront 進行的 API 查詢中加入 <code>username </code>，使用者便會登入 Workfront，而搜尋不會成功。</p> <p>注意：<code>In</code> 和 <code>NotIn</code> 可搭配陣列使用。輸入應使用陣列的格式。</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 輸出]</td> 
   <td> <p>選取您要包含在此模組的輸出中的欄位。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 參考資料]</td> 
   <td>選取您要包含在搜尋中的任何參考資料欄位。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 集合]</td> 
   <td>選取您要新增至搜尋的任何集合。</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--not visible Jan 6, 2025

+++ **[!UICONTROL Search (Legacy)]**

This search module looks for records in an object in Workfront that match the search query you specify.

You can map this information in subsequent modules in the scenario.

When you are configuring this module, the following fields display.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Workfront app to Workfront Fusion, see <a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">Connect Workfront to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to search for.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Result Set]</td> 
   <td>Select an option to specify whether you want the module to get the first result that matches your search criteria or all the results that match it.</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search criteria]</td> 
   <td> <p>Enter the field that you want to search by, the operator you want to use in your query, and the value that you are searching for in the field.</p> <p>Note: Do not use <code>username </code>in your search criteria. Including <code>username </code>in an API query to Workfront logs the user into Workfront, and the search will not be successful.</p> <p>Note: <code>In</code> and <code>NotIn</code>work with arrays. The inputs should be in array format.</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Outputs]</td> 
   <td> <p>Select the fields that you want to include in the output for this module.</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL References]</td> 
   <td>Select any reference fields that you want to include in the search.</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Collections]</td> 
   <td>Select any collections that you want to add to the search.</td> 
  </tr> 
 </tbody> 
</table>

See a list of the Workfront object types for which you can use this module in [Workfront object types available for each Workfront module](#workfront-object-types-available-for-each-workfront-module).

+++-->

## 各 Workfront 模組可用的 Workfront 物件類型

<!-- [Object types available for each Workfront trigger module](#object-types-available-for-each-workfront-trigger-module) 
* [Object types available for each Workfront action module](#object-types-available-for-each-workfront-action-module) 
* [Object types available for each Workfront search module](#object-types-available-for-each-workfront-search-module)-->

+++**各 Workfront 觸發程序模組可用的物件類型**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col>         
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL 監視記錄]</th> 
   <th>[!UICONTROL 監視欄位]</th> 
   <th>[!UICONTROL 監視事件]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>核准流程</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>指派</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>基準線</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 計費記錄 </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>計費費率</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>公司</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>儀表板</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件資料夾</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>文件請求</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>文件版本</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>費用類型</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>群組</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時數</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>時數類型</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>問題</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>疊代</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>職務角色</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>日誌項目</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>里程碑</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>里程碑路徑</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>備註</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>備註標記</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>專案組合</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>方案</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>專案</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>專案使用者</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>校訂核准</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>已保留時間* </td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>報告</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>風險</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>風險類型</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>步驟核准者</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>任務</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>團隊</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>範本</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>範本任務</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時程表</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>使用者</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>更新</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**各 Workfront 動作模組可用的物件類型**

>[!NOTE]
>
>[!UICONTROL 下載文件]模組未包含在此表格中，因為 Workfront 物件類型不屬於其設定的一部分。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL 建立記錄]</th> 
   <th>[!UICONTROL 更新記錄]</th> 
   <th>[!UICONTROL 刪除記錄]</th> 
   <th>[!UICONTROL 上傳文件]</th> 
   <th>[!UICONTROL 讀取記錄]</th> 
   <th>[!UICONTROL 自訂 API 呼叫]</th> 
   <th>[!UICONTROL 其他動作]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>核准流程</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>指派</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>基準線</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
   <tr> 
   <td>計費記錄</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>計費費率</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>公司</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件資料夾</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件版本</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>匯率</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>費用類型</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>外部文件</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>群組</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>時數</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時數類型</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>問題</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>疊代</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>職務角色</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>日誌項目</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>里程碑</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>里程碑路徑</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>備註</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>備註標記</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>專案組合</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>方案</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>專案</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>專案使用者</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>已保留時間* </td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>風險</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>風險類型</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>步驟核准者</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>任務</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>團隊</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>範本</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>範本任務</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>時程表</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>使用者</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>更新</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**各 Workfront 搜尋模組可用的物件類型**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL 搜尋]</th> 
   <th>[!UICONTROL 讀取關聯的記錄]</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>核准流程</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>指派</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>計費記錄</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>計費費率</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>公司</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件資料夾</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>文件版本</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>費用類型</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>群組</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>時數</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時數類型</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>問題</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>疊代</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>職務角色</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>日誌項目</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>里程碑</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>里程碑路徑</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>備註</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>備註標記</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>專案組合</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>方案</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>專案</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>專案使用者</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>已保留時間* </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>風險</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>風險類型</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>步驟核准者</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>任務</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>團隊</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>範本</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>範本任務</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>時程表</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>使用者</td> 
   <td>✓</td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>使用者委派</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

我們建議您再次檢查，以確保其運作方式符合預期。

+++

## Workfront > [!UICONTROL 監視事件]模組中的事件訂閱篩選器

>[!NOTE]
>
>* 我們強烈建議您在[!UICONTROL 監視事件]模組中使用事件訂閱篩選器。
>
>* Workfront 最近發行新版本的事件訂閱服務。新版本並非對 Workfront API 有所變更，而是變更事件訂閱功能。此動作模組會更新此情境所使用的事件承載版本。
>
>   關於事件訂閱新版本的詳細資訊，請參閱 Workfront 文件中的[事件訂閱版本設定](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning)
>
>   關於在事件訂閱升級期間保留 Workfront Fusion 情境的資源，包括網路研討會錄影，請參閱[在事件訂閱 V2 升級期間保留 Fusion 情境 (https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182)]。

Workfront [!UICONTROL 監視事件]模組會根據在 Workfront API 中建立事件訂閱的 Webhook 觸發情境。事件訂閱是一個資料集，用於決定哪些事件要傳送至 Webhook。例如，若您設定監視問題的[!UICONTROL 監視事件]模組，則事件訂閱只會傳送與問題相關的事件。

藉由使用事件訂閱篩選器，Fusion 使用者可以根據其使用案例建立更加合適的事件訂閱。例如，您可以在 Workfront API 中設定事件訂閱，僅將特定專案中的問題傳送至 Webhook，確保[!UICONTROL 監視事件]模組僅會因為該專案中的問題而觸發。由於能夠建立範圍較小的觸發程序，因此可以減少不相關的觸發程序的數量，進而改善情境設計。

這與在 Workfront Fusion 情境中設定篩選器不同。若沒有事件訂閱篩選器，您的 Webhook 會接收與所選物件類型相關的所有事件。這些事件大多與情境無關，必須先篩選掉，情境才能繼續。

Workfront > 監視事件篩選器中提供下列運算子：

* 等於
* 不等於
* 大於
* 小於
* 大於或等於
* 小於或等於
* 包含
* 存在
   * 此運算子不需要值，且值欄位不存在。
* 不存在
   * 此運算子不需要值，且值欄位不存在。
* 已變更
   * 此運算子不需要值，且值欄位不存在。
   * 此運算子會忽略狀態欄位。
   * 使用 `Changed` 時，請在「**記錄來源**」欄位中選取「**僅更新事件**」。

>[!IMPORTANT]
>
>您無法編輯現有 Workfront Webhook 中的篩選器。若要為 Workfront 事件訂閱設定不同的篩選器，請移除目前的 Webhook 並建立新的。

>[!INFO]
>
>**範例：**&#x200B;考慮一個會處理指派至特定使用者 Ana 之新問題的情境。
>
>### 使用事件訂閱篩選器來篩選事件 (建議使用)
>
>透過事件篩選器，您可以設定 Webhook 在問題建立時若將問題指派至 Ana，則觸發情境。Ana 的使用者 ID 是 b378489d8f7cd3cee0539260720a84b7。
>
>![事件篩選器](/help/workfront-fusion/references/apps-and-modules/assets/event-filter-watch-events-350x277.png)
>
>如果一天內建立了 100 個問題，但只有兩個問題指派至 Ana，則情境會執行兩次。
>
>### 在情境內篩選事件 (不建議使用)
>
>若要篩選事件，以便僅處理指派至 Ana 的問題，您可以在[!UICONTROL 監視事件]模組之後建立篩選器。
>
>![沒有事件篩選器](/help/workfront-fusion/references/apps-and-modules/assets/watch-events-non-event-filter-350x206.png)
>
>如果一天內建立了 100 個問題，但只有兩個問題指派至 Ana，情境會執行 100 次。其中 98 次執行會在遇到篩選器時便停止，但觸發程序模組仍在所有執行中使用資料及執行作業。

關於 Workfront 事件訂閱的詳細資訊，請參閱[常見問題集 - 事件訂閱](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-faq)。

關於 Webhook 的詳細資訊，請參閱 [Adobe Workfront Fusion 中的即時觸發程序 (Webhook)](/help/workfront-fusion/references/modules/webhooks-reference.md)

如需關於情境中篩選器的詳細資訊，請參閱[在情境中加入篩選器](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md)。

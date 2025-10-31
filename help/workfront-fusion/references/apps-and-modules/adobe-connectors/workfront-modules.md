---
title: Adobe Workfront模組
description: 您可以使用Adobe Workfront Fusion Adobe Workfront聯結器在Workfront中自動化您的流程。 如果您有Workfront Fusion for Work Automation and Integration授權，也可以用它來連線至協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 93c27cf6-38b0-466c-87bb-926c4817eae7
source-git-commit: 6e2593c0f171bae278e86fed53492b8f64ae3d7e
workflow-type: tm+mt
source-wordcount: '7323'
ht-degree: 2%

---

# Adobe Workfront模組

>[!IMPORTANT]
>
>本文包含2025年10月22日發行之新版Workfront聯結器的指示。 此新聯結器反映對Workfront API所做的變更。
>
>新的聯結器會標示為「Workfront」，而先前可用的聯結器會標示為「Workfront （舊版）」。
>
>我們建議：
>
>* 在建立或更新案例時使用新聯結器。
>* 將現有模組升級至新聯結器。
>
>舊版Workfront聯結器使用Workfront API版本20，此版本預計在28.4版本（2028年4月）中淘汰。 舊版聯結器中的模組將持續運作，直到該時間為止。
>
>如需有關升級現有模組的說明，請參閱將模組升級為新版本一文中的[將Workfront模組升級為新版本](/help/workfront-fusion/manage-scenarios/update-module-to-new-version.md)。
>
>如需為什麼有時需要新聯結器的詳細資訊，請參閱[Fusion中的API概觀](/help/workfront-fusion/get-started-with-fusion/understand-fusion/api-overview.md)。

您可以使用Adobe Workfront Fusion Adobe Workfront聯結器在Workfront中自動化您的流程。 您也可以將Workfront連線至其他應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。 如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

+++##將Workfront連線至Workfront Fusion 

Workfront聯結器使用OAuth 2.0連線至Workfront。

您可以直接從Workfront Fusion模組內建立與Workfront帳戶的連線。

* [使用使用者端ID和使用者端密碼連線至Workfront](#connect-to-workfront-using-client-id-and-client-secret)
* [使用伺服器對伺服器連線來連線Workfront](#connect-to-workfront-using-a-server-to-server-connection)

### 使用使用者端ID和使用者端密碼連線至Workfront

1. 在任何Adobe Workfront模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線型別]</td>
        <td>
          <p>選取<b>Adobe Workfront驗證連線</b>。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的Workfront使用者端ID。 您可在Workfront中「設定」區域的「OAuth2應用程式」區域中找到此專案。 開啟您要連線的特定應用程式以檢視使用者端ID。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的Workfront使用者端密碼。 您可在Workfront中「設定」區域的「OAuth2應用程式」區域中找到此專案。 如果您的Workfront中的OAuth2應用程式沒有使用者端密碼，您可以產生另一個密碼。 如需指示，請參閱Workfront檔案。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 驗證URL]</td>
        <td>這可以維持預設值，或者您可以輸入Workfront執行個體的URL，然後輸入<code>/integrations/oauth2</code>。 <p>範例： <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 主機前置詞]</td>
        <td>在大多數情況下，此值應該是<code>origin</code>。
      </tr>
    </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

   如果您未登入Workfront，系統會將您導向至登入畫面。 登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API的OAuth 2.0連線不再依賴API金鑰。
>* 若要建立與Workfront沙箱環境的連線，您必須在該環境中建立OAuth2應用程式，然後在您的連線中使用該應用程式產生的使用者端ID和使用者端密碼。

### 使用伺服器對伺服器連線來連線Workfront

1. 在任何Adobe Workfront模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線型別]</td>
        <td>
          <p>選取<b>Adobe Workfront伺服器對伺服器連線</b>。</p>
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
          <p>輸入執行個體的名稱，也稱為您的網域。</p><p>範例：若您的URL為<code>https://example.my.workfront.com</code>，請輸入<code>example</code>。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Instance Lane]</td>
        <td>
          <p>輸入此連線將連線的環境型別。</p><p>範例：若您的URL為<code>https://example.my.workfront.com</code>，請輸入<code>my</code>。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的Workfront使用者端ID。 您可在Workfront中「設定」區域的「OAuth2應用程式」區域中找到此專案。 開啟您要連線的特定應用程式以檢視使用者端ID。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的Workfront使用者端密碼。 您可在Workfront中「設定」區域的「OAuth2應用程式」區域中找到此專案。 如果您的Workfront中的OAuth2應用程式沒有使用者端密碼，您可以產生另一個密碼。 如需指示，請參閱Workfront檔案。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 範圍]</td>
        <td>輸入此連線的適用範圍。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 主機前置詞]</td>
        <td>在大多數情況下，此值應該是<code>origin</code>。
      </tr>
    </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

   如果您未登入Workfront，系統會將您導向至登入畫面。 登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API的OAuth 2.0連線不再依賴API金鑰。
>* 若要建立與Workfront沙箱環境的連線，您必須在該環境中建立OAuth2應用程式，然後在您的連線中使用該應用程式產生的使用者端ID和使用者端密碼。

## Workfront模組及其欄位

設定Workfront模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Workfront欄位，視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。


![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* 如果您在Workfront模組中未看到最新欄位，可能是因為快取問題。 請等待一小時，然後再試一次。
>* 來自Adobe Workfront的HTTP 429狀態程式碼不應導致停用，而會在案例中觸發短暫的執行暫停。

* [觸發器](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

<!--
* [Watch Events](#watch-events) 
* [Watch Record](#watch-record) 
* [Watch Field](#watch-field)
-->

+++ **[!UICONTROL 觀看活動]**

在Workfront中新增、更新或刪除特定型別的物件時，此觸發模組會即時執行案例

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

1. 按一下&#x200B;**[!UICONTROL Webhook]**&#x200B;方塊右側的&#x200B;**[新增**]。

1. 在顯示的&#x200B;**[!UICONTROL 新增連結]**&#x200B;方塊中設定webhook。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Webhook名稱]</td> 
      <td>輸入webhook的名稱</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Connection]</td> 
      <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL 記錄型別]</td> 
      <td>選取您要模組觀看的Workfront記錄型別。</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL 狀態]</td> 
      <td>選取您要觀看舊狀態還是新狀態。<ul><li><p><b>[!UICONTROL 新狀態]</b></p><p>當記錄將指定值<b>變更為</b>時觸發案例。</p><p>例如，如果狀態設為[!UICONTROL New State]，而篩選條件設為[!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress]，則webhook會在[!UICONTROL Status]變更為[!UICONTROL In Progress]時觸發案例，無論狀態之前為何。 </p></li><li><p><b>[!UICONTROL 舊狀態]</b></p><p>當記錄從<b>變更指定值時，觸發案例</b>。</p><p>例如，如果狀態設為[!UICONTROL Old State]，而篩選條件設為[!UICONTROL Status] [!UICONTROL Equals] [!UICONTROL In Progress]，則當[!UICONTROL Status]目前為[!UICONTROL In Progress]的狀態變更為其他狀態時，webhook會觸發一個情境。 </p></li></ul></td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL 事件篩選器]</p> </td> 
      <td> <p>您可以設定篩選器，只監視符合您選取條件的記錄。</p> <p>針對每個篩選器，輸入您希望篩選器評估的欄位、運運算元，以及您希望篩選器允許的值。 您可以新增AND規則來使用一個以上的篩選器。</p> <p><b>注意</b>：您無法編輯現有Workfront Webhook中的篩選器。 若要為Workfront活動訂閱設定不同的篩選器，請移除目前的webhook並建立新的篩選器。</p> <p>如需事件篩選的詳細資訊，請參閱本文中的Workfront &gt; [!UICONTROL 觀看活動]模組<a href="#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">中的</a>事件訂閱篩選。</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td>排除此連線造成的事件</td> 
      <td>啟用此選項可排除使用此觸發模組使用的相同聯結器建立或更新的事件。 這可防止案例可能觸發自身的情況，導致其在無限回圈中重複。<p><b>注意</b>： Assignment記錄型別不包含此選項。</p></td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL 記錄來源]</td> 
      <td>
       <p>選擇您希望案例僅觀看[!UICONTROL 新記錄]、僅觀看[!UICONTROL 更新記錄]、[!UICONTROL 新記錄和更新記錄]或[!DNL Deleted Records Only]。</p>
       <p><b>注意</b>：如果您選擇[!UICONTROL 新增和更新的記錄]，webhook建立將建立2個事件訂閱（針對相同的webhook位址）。</p>
       </td> 
     </tr> 
    </tbody> 
   </table>



   <!--Markdown 0032 placeholder-->

建立webhook後，您可以檢視事件傳送到的端點位址。

如需詳細資訊，請參閱Workfront檔案中事件訂閱API一文中的[事件裝載範例](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-api#examples-of-event-payloads)小節。

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

+++

+++ **[!UICONTROL 觀看欄位]**

當您指定的欄位更新時，此觸發模組會執行情境。 模組會傳回指定欄位的舊值和新值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組觀看的Workfront記錄型別。</p> <p>例如，如果您要在每次更新任務中的記錄欄位時開始執行案例，請選取[!UICONTROL 任務]。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 欄位]</td> 
   <td>選取您希望模組監視更新的欄位。 這些欄位反映Workfront管理員針對追蹤而設定的欄位。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 輸出]</td> 
   <td>選取您要包含在此模組輸出組合中的物件欄位。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

+++

+++ **[!UICONTROL 觀看記錄]**

此觸發模組會在新增、更新特定型別的物件或兩者同時進行時，執行案例。 模組會傳回與一個或多個記錄相關聯的所有標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

在輸出中，模組會指出每個記錄是新的還是更新的。

自上次執行案例後新增和更新的記錄會傳回為新記錄。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td> <p>選擇您希望情境只觀看[!UICONTROL 新記錄]、只觀看[!UICONTROL 更新記錄]還是[!UICONTROL 新記錄和更新記錄]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組觀看的Workfront記錄型別。</p> <p>例如，如果您要在每次建立新專案時啟動情境，請選取[!UICONTROL 專案]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取您要包含在此模組之輸出組合中的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 參考]</td> 
   <td> <p>選取您要包含在此模組輸出組合中的參考欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取您要包含在此模組輸出組合中的集合欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 選用篩選器]</td> 
   <td> <p>（進階）輸入API程式碼字串，以定義將縮小條件範圍的任何其他引數或程式碼。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

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

此動作模組會進行下列其中一個轉換：

* 將問題轉換為專案
* 將問題轉換為任務
* 將任務轉換為專案

>[!NOTE]
>
>自2024年7月起，轉換物件時可包含自訂表單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 物件型別]</td> 
   <td> <p>選取您要轉換的物件型別。 這是轉換前物件的型別。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 轉換為]</td> 
   <td>選取您想要將它轉換成的物件。 這是物件在轉換後的型別。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL &lt;物件&gt; ID]</td> 
   <td> <p>輸入物件的ID。 </p> <p>附註：輸入物件識別碼時，您可以開始輸入物件的名稱，然後從清單中選取它。 模組接著在欄位中輸入適當的ID。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 範本ID]</td> 
   <td> <p>如果要轉換為專案，請選取要用於專案的範本ID。</p> <p>附註：輸入物件識別碼時，您可以開始輸入物件的名稱，然後從清單中選取它。 模組接著在欄位中輸入適當的ID。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 自訂表單]</td> 
   <td>選取您要新增至新轉換物件的任何自訂表單，然後輸入自訂表單欄位的值。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL Options]</td> 
   <td> <p>啟用轉換物件時所需的任何選項。 選項是否可用取決於您轉換至哪個物件或轉換自哪個物件。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 複製原生欄位]</td> 
   <td> <p>啟用此選項可將任何原生欄位從原始物件複製到新物件。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 複製自訂表單]</td> 
   <td> <p>啟用此選項可將任何原生欄位從原始物件複製到新物件。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 建立記錄]** 

此動作模組會建立物件，例如Workfront中的專案、任務或問題，並允許您新增自訂表單至新物件。 模組可讓您選取可在模組中取得哪些物件欄位。

您指定記錄的ID。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

請務必提供最小輸入欄位數。 例如，如果您想建立問題，則需要在「專案ID」欄位中提供有效的父專案ID，以指出問題應存在於Workfront中的何處。 您可以使用對應面板從情境中的另一個模組對應此資訊，或是輸入名稱，然後從清單中選取它，以手動方式輸入資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組建立的Workfront記錄型別。</p> <p>例如，如果您想要建立專案，請從下拉式清單中選取[!UICONTROL 專案]。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 選擇要對應的欄位]</td> 
   <td> <p>選取您想用於資料輸入的欄位。 這可讓您使用這些欄位，而無需捲動瀏覽您不需要的欄位。 您接著可以在這些欄位中輸入或對應資料。</p> <p>對於自訂表單中的欄位，請使用<b>[!UICONTROL 附加自訂表單]</b>欄位。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 附加自訂表單]</td> 
   <td>選取您要新增至新物件的任何自訂表單，選取要輸入值的欄位，然後輸入或對應這些欄位的值。</td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

>[!NOTE]
>
>* 輸入物件的ID時，您可以開始輸入物件的名稱，然後從清單中選取它。 模組接著在欄位中輸入適當的ID。
>* 輸入自訂欄位或[!UICONTROL Note]物件（註解或回覆）的文字時，您可以使用[!UICONTROL 註解文字]欄位中的HTML標籤來建立RTF文字，例如粗體或斜體文字。
>



>[!NOTE]
>
>系統會建立處於停用中和未決核准狀態的使用者。 如果您的組織已移轉至Adobe Admin Console，但未在幾分鐘內移除未決核准徽章，您可以核准使用者。
>
>* **解析個別使用者**
>
>      您可以解析「使用者」清單中的個別使用者。
>
>      1. 在使用者清單中選取一個或多個使用者。
>      1. 按一下清單標題中的三點選單。
>      1. 選取&#x200B;**核准**。
>      1. 幾分鐘後，重新整理頁面。
>
>* **解析新增至大型批次的使用者**
>
>   若要解析大量新增的使用者，您可以直接將批次使用者新增到Adobe Admin Console。
>
>   如需指示，請參閱[管理多個使用者 | 在Adobe檔案中大量上傳CSV](https://helpx.adobe.com/tw/enterprise/using/bulk-upload-users.html)。

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

+++ **[!UICONTROL 自訂API呼叫]**

此動作模組可讓您對Workfront API發出自訂的已驗證呼叫。 如此一來，您便可建立其他Workfront模組無法完成的資料流程自動化。

模組會傳回下列資訊：

* **[!UICONTROL 狀態碼]** （數字）：這表示您的HTTP要求成功或失敗。 這些是您可在網際網路上查閱的標準程式碼。
* **[!UICONTROL Headers]** （物件）：與輸出本文無關之回應/狀態代碼的更詳細內容。 並非顯示在回應標題中的所有標題都是回應標題，因此某些標題可能對您並不實用。

  回應標題取決於您在設定模組時選擇的HTTP請求。

* **[!UICONTROL 內文]** （物件）：根據您在設定模組時所選擇的HTTP要求，您可能會收到一些傳回的資料。 該資料(例如來自GET請求的資料)包含在此物件中。

您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>輸入相對於<code> https://&lt;WORKFRONT_DOMAIN&gt;/attask/api/&lt;API_VERSION&gt;/</code>的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API版本]</td> 
   <td>選取您希望模組使用的Workfront API版本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱Adobe Workfront Fusion<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">中的</a>HTTP要求方法。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 這會決定請求的內容型別。</p> <p>例如，<code> {"Content-type":"application/json"}</code></p> <p>注意：如果您收到錯誤且難以判斷其來源，請考慮根據Workfront檔案修改標題。 如果您的自訂API呼叫傳回422 HTTP請求錯誤，請嘗試使用<code>"Content-Type":"text/plain"</code>標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> <p>提示：建議您透過JSON內文傳送資訊，而非查詢引數。</p> </td> 
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

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

+++

+++ **[!UICONTROL 刪除記錄]**

此動作模組會刪除物件，例如Workfront中的專案、任務或問題。

您指定記錄的ID。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 強制刪除]</td> 
   <td>啟用此選項以確保刪除記錄，即使Workfront UI會請求確認刪除。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 非同步刪除]</td> 
   <td>啟用此選項可允許模組非同步刪除。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>ID</td> 
   <td> <p>輸入您要模組刪除之記錄的唯一Workfront ID。</p> <p>若要取得ID，請在瀏覽器中開啟Workfront物件，並在「ID=」後複製URL結尾的文字。 例如： https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄型別]</td> 
   <td>選取您要模組刪除的Workfront記錄型別。</td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

>[!NOTE]
>
>我們建議使用下列案例設定，以避免因非同步操作而無法刪除記錄的可能性。
>
>1. 同步刪除記錄。
>1. 新增錯誤處理至刪除記錄模組，以忽略40秒逾時造成的錯誤。


+++

+++ **[!UICONTROL 下載檔案]**

此動作模組會從Workfront下載檔案。

您指定記錄的ID。

模組會傳回檔案的內容、檔案名稱、副檔名和檔案大小。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td> <p>對應或手動輸入您要模組下載之檔案的唯一Workfront ID。</p> <p>若要取得ID，請在瀏覽器中開啟Workfront物件，並在「ID=」後複製URL結尾的文字。 例如： https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

+++

### **取得預先簽署的檔案URL**

此動作模組會取得預先簽署的檔案URL，以便稍後供其他API使用。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td> <p>對應或手動輸入您要取得預先簽署URL之檔案的唯一Workfront ID。</p> <p>若要取得ID，請在瀏覽器中開啟Workfront物件，並在「ID=」後複製URL結尾的文字。 例如： https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL到期時間]</td> 
   <td> <p>輸入或對應此URL在過期之前存在的分鐘數。 預設值為1分鐘。</p><p>若要變更此值，您必須讓Workfront Fusion團隊啟用此引數。 如果未啟用，則無論您輸入多少數字，此值都將保持1分鐘。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++ **[!UICONTROL 其他動作]**

此動作模組可讓您對API執行動作。

>[!NOTE]
>
>截至2024年7月，`convertToProject`動作包含欄位`copyCategories`。 設定為`TRUE`時，所有自訂表單都將包含在問題轉換為的專案中。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您希望模組與之互動的Workfront記錄型別。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 動作]</td> 
   <td> <p>選取您希望模組執行的動作。</p> <p>視您選擇的[!UICONTROL 記錄型別]和[!UICONTROL 動作]而定，您可能需要填寫其他欄位。 這兩個設定的某些組合可能只需要記錄ID，而其他設定（例如<strong>[!UICONTROL 記錄型別]</strong>的Project和<strong>[!UICONTROL 動作]</strong>的[!UICONTROL 附加範本]）則需要其他資訊（例如物件ID和範本ID）。</p><p>如需某些動作可用的選項，請參閱本文中的<a href="#misc-action-options" class="MCXref xref">其他動作選項</a>。</p> <p>如需個別欄位的詳細資訊，請參閱<a href="http://developer.workfront.com/">Workfront開發人員檔案</a>。 <p><strong>注意</strong>：開發人員檔案網站僅包含透過API版本14的資訊，但仍包含API呼叫的重要資訊。 </p> 
    <ol> 
     <li value="1"> <p>在Workfront開發人員檔案頁面的左側導覽區中選取記錄型別。 下列型別有自己的頁面：</p> 
      <ul> 
       <li> <p>[!UICONTROL 專案]</p> </li> 
       <li> <p>[!UICONTROL 工作]</p> </li> 
       <li> <p>[!UICONTROL 問題]</p> </li> 
       <li> <p>[!UICONTROL 使用者]</p> </li> 
       <li> <p>[!UICONTROL 檔案]</p> </li> 
      </ul> <p>針對所有其他記錄型別，選取<b>[!UICONTROL Other objects and endpoints]</b>，然後在依字母順序排序的頁面上尋找記錄型別。</p> </li> 
     <li value="2"> <p>在適當記錄型別的頁面上，搜尋動作（Ctrl-F或Cmd-F）。</p> </li> 
     <li value="3"> <p>檢視所選動作下可用欄位的說明。</p> </li> 
    </ol> <p>注意：  <p>透過Workfront [!UICONTROL 雜湊動作]模組建立校訂時，最佳實務是建立不含任何進階選項的校訂，然後使用[!DNL Workfront Proof] SOAP API更新校訂。</p><p>如需使用Workfront API （此模組使用）建立校訂的詳細資訊，請參閱<a href="https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/tips-troubleshooting-apis/api-create-proof-options-json" class="MCXref xref">透過Adobe Workfront API建立校訂時新增進階校訂選項</a></p> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td>輸入或對應您希望模組與之互動之記錄的唯一Workfront ID。<p>若要取得ID，請在瀏覽器中開啟Workfront物件，並在「ID=」後複製URL結尾的文字。 例如： https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p></td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

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
   <li>clearAssigments</li>
   <li>clearConstraints</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearpermissions</li>
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
   <li>clearAssigments</li>
   <li>clearDocuments</li>
   <li>clearConstraints</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearpermissions</li>
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
   <li>clearAssigments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearpermissions</li>
   <li>clearProgress</li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>轉換為任務</td> 
   <td>
   <ul>
   <li>preserveIssue<p>保持初始問題並將其解決方案連結至此任務</p></li>
   <li>preservePrimaryContact<p>允許問題的主要連絡人存取此任務</p></li>
   <li>preserveCompletionDate<p>保持問題的計畫完成日期</p></li>
   </ul>
   </td> 
  </tr> 
  <tr> 
   <td>轉換為專案</td> 
   <td>
   <ul>
   <li>preserveIssue<p>保持初始問題並將其解決方案連結至此任務</p></li>
   <li>preservePrimaryContact<p>允許問題的主要連絡人存取此任務</p></li>
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
   <li>clearAssigments</li>
   <li>clearCustomData</li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearpermissions</li>
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
   <li>clearAssigments</li>
   <li>clearBillingRates</li>
   <li>clearConstraints</li>
   <li>clearDeliverables<p>清除目標</p></li>
   <li>clearDocuments</li>
   <li>clearExpenses</li>
   <li>clearFinancials<p>清除財務資料</p></li>
   <li>clearHourTypes</li>
   <li>Clearisssetup<p>清除佇列屬性和問題設定</p></li>
   <li>clearPredecessors</li>
   <li>clearrisks</li>
   <li>clearSharingOptions</li>
   <li>clearTimedNotifications<p>清除提醒通知</p></li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>



+++

+++ **[!UICONTROL 讀取記錄]**

此動作模組會從單一記錄擷取資料。

您指定記錄的ID。 您也可以指定要讓模組讀取哪些相關記錄。

例如，如果模組正在讀取的記錄是專案，您可以指定您要讀取專案任務。

模組會從您指定的輸出欄位傳回資料陣列。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 記錄型別]</td>

<td>選擇您希望模組讀取的Workfront物件型別。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 輸出]</td>

<td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 輸出自訂表單]</td>
     <td> <p>選取要納入此模組輸出組合的自訂表單，然後從要納入輸出的自訂表單中選取特定欄位。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 參考]</td>
   <td>選取您要納入輸出的任何參考欄位。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 集合]</td>
   <td>選取您要納入輸出的任何參考欄位。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL ID]</td>
   <td> <p>輸入您希望模組讀取之記錄的唯一Workfront ID。</p> <p>若要取得ID，請在瀏覽器中開啟Workfront物件，並在「ID=」後複製URL結尾的文字。 例如： https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

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

+++ **更新事件裝載版本**

Workfront最近發佈了其事件訂閱服務的新版本。 新版本並非變更Workfront API，而是變更事件訂閱功能。 此動作模組會更新用於此情境的事件裝載版本。

如需新事件訂閱版本的詳細資訊，請參閱Workfront檔案中的[事件訂閱版本設定](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning)

如需在事件訂閱升級期間保留Workfront Fusion案例的資源，包括網路研討會影片，請參閱[在事件訂閱V2升級期間保留Fusion案例](https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182)。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 版本]</td> 
   <td> 選取您要用於此裝載的事件訂閱版本。 </td> 
  </tr> 
 </tbody> 
</table>


+++

+++ **更新記錄**


此動作模組會更新物件，例如專案、任務或問題。 模組可讓您選取可在模組中取得哪些物件欄位。

您指定記錄的ID。

模組會傳回物件ID及任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL ID]</td> 
   <td> <p>輸入您希望模組更新的記錄的唯一Workfront ID。</p> <p>若要取得ID，請在瀏覽器中開啟Workfront物件，並在「ID=」後複製URL結尾的文字。 例如： https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Record Type]</td> 
   <td> <p>選取您要模組更新的Workfront記錄型別。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Select fields to map]</td> 
   <td>選取您想用於資料輸入的欄位。 這可讓您使用這些欄位，而無需捲動瀏覽您不需要的欄位。 您接著可以在這些欄位中輸入或對應資料。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!DNL Attach Custom Form]</td> 
   <td>選取您要在新記錄上提供欄位值的自訂表單。 選取表單後，輸入表單上欄位的資料。<p> 若要為您要附加在此模組中的表單提供欄位值，請在要對應的欄位區段中加入自訂表單ID。</td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

>[!NOTE]
>
> 輸入自訂欄位或[!UICONTROL Note]物件（註解或回覆）的文字時，您可以使用[!UICONTROL 註解文字]欄位中的HTML標籤來建立RTF文字，例如粗體或斜體文字。


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

+++ **[!UICONTROL 上傳檔案]**

此動作模組會將檔案上傳到Workfront物件，例如專案、任務或問題。 此模組會以區塊上傳檔案，讓Workfront的上傳程式更順暢。

此模組可處理比舊版模組更大的檔案，屬於分階段推出至使用Ultimate Workfront套件的組織的一部分。

您可以指定檔案的位置、要上傳的檔案，以及檔案的可選新名稱。

模組會傳回檔案ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 相關記錄ID]</td> 
   <td>輸入您要上傳檔案之記錄的唯一Workfront ID。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 相關記錄型別]</td> 
   <td>選取您希望模組上傳檔案的Workfront記錄型別。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾ID]</td> 
   <td>視相關記錄的型別而定，您可能需要輸入或對映資料夾ID。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

檢視您可以在每個Workfront模組[可用的](#workfront-object-types-available-for-each-workfront-module)Workfront物件型別中使用此模組的Workfront物件型別清單。

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

+++ **[!UICONTROL 讀取相關記錄]**

此搜尋模組會讀取符合您指定之搜尋查詢的記錄（在特定父物件中）。

您可以指定要包含在輸出中的欄位。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要讀取其關聯記錄的父記錄型別(Workfront物件)。</p> <p>請參閱本文中每個Workfront模組<a href="#object-types-available-for-each-workfront-search-module" class="MCXref xref">可用的</a>Workfront物件型別中，可使用此模組的Workfront物件型別清單。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 父記錄ID]</td> 
   <td> <p>輸入或對應您要讀取其關聯記錄的父記錄識別碼。</p> <p>若要取得ID，請在瀏覽器中開啟Workfront物件，並在「ID=」後複製URL結尾的文字。 例如： https://my.workfront.com/project/view?ID=<i>5e43010c03286a2a555e1d0a75d6a86e</i></p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 集合]</td> 
   <td>選取或對應您希望模組讀取的子記錄型別。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 輸出]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 搜尋]**

此搜尋模組會在Workfront中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組搜尋的Workfront記錄型別。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 自訂表單清單]</td> 
   <td> <p>請至少選取一個自訂表格。 這些自訂表單中的欄位將可用於搜尋查詢。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 結果集]</td> 
   <td>選取選項以指定您希望模組取得符合搜尋條件的第一個結果，還是所有符合該條件的結果。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件欄位]</td> 
   <td> <p>選取您要用於搜尋條件的欄位。 這些欄位隨後將顯示在搜尋條件下拉式清單中。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件]</td> 
   <td> <p>輸入您要搜尋的欄位、要在查詢中使用的運運算元，以及要在欄位中搜尋的值。</p> <p>注意：請勿在您的搜尋條件中使用<code>username </code>。 若在Workfront的API查詢中加入<code>username </code>，使用者就會登入Workfront，搜尋將不會成功。</p> <p>注意： <code>In</code>和<code>NotIn</code>可搭配陣列使用。 輸入的格式應為陣列。</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 輸出]</td> 
   <td> <p>選取您要包含在此模組輸出中的欄位。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 參考]</td> 
   <td>選取您要納入搜尋的任何參考欄位。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 集合]</td> 
   <td>選取您要新增至搜尋的任何集合。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 搜尋（舊版）]**

>[!IMPORTANT]
>
>此模組已由搜尋記錄模組取代。 我們建議在新案例中使用該模組。
>&#x200B;>使用此模組的現有情境將繼續如預期運作。 此模組將於2025年5月從模組選擇器中移除。

此搜尋模組會在Workfront中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將Workfront連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組搜尋的Workfront記錄型別。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 結果集]</td> 
   <td>選取選項以指定您希望模組取得符合搜尋條件的第一個結果，還是所有符合該條件的結果。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximal]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件欄位]</td> 
   <td> <p>選取您要用於搜尋條件的欄位。 這些欄位隨後將顯示在搜尋條件下拉式清單中。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件]</td> 
   <td> <p>輸入您要搜尋的欄位、要在查詢中使用的運運算元，以及要在欄位中搜尋的值。</p> <p>注意：請勿在您的搜尋條件中使用<code>username </code>。 若在Workfront的API查詢中加入<code>username </code>，使用者就會登入Workfront，搜尋將不會成功。</p> <p>注意： <code>In</code>和<code>NotIn</code>可搭配陣列使用。 輸入的格式應為陣列。</p></td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 輸出]</td> 
   <td> <p>選取您要包含在此模組輸出中的欄位。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 參考]</td> 
   <td>選取您要納入搜尋的任何參考欄位。</td> 
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

## 適用於每個Workfront模組的Workfront物件型別

<!-- [Object types available for each Workfront trigger module](#object-types-available-for-each-workfront-trigger-module) 
* [Object types available for each Workfront action module](#object-types-available-for-each-workfront-action-module) 
* [Object types available for each Workfront search module](#object-types-available-for-each-workfront-search-module)-->

+++**每個Workfront觸發程式模組可用的物件型別**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col>         
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL 監看紀錄]</th> 
   <th>[!UICONTROL 監視欄位]</th> 
   <th>[!UICONTROL 觀看活動]</th> 
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
   <td>控制面板</td> 
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
   <td>文件要求</td> 
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
   <td>Hour</td> 
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
   <td>日誌輸入項目</td> 
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
   <td>附註標籤</td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>產品組合</td> 
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
   <td>校樣核准</td> 
   <td> </td> 
   <td> </td> 
   <td>✓</td> 
  </tr> 
  <tr> 
   <td>保留時間* </td> 
   <td> </td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>報表</td> 
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

+++**每個Workfront動作模組可用的物件型別**

>[!NOTE]
>
>[!UICONTROL 下載檔案]模組未包含在此資料表中，因為Workfront物件型別不是其設定的一部分。

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
   <th>[!UICONTROL 上傳檔案]</th> 
   <th>[!UICONTROL 讀取記錄]</th> 
   <th>[!UICONTROL 自訂API呼叫]</th> 
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
   <td>外部檔案</td> 
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
   <td>Hour</td> 
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
   <td>日誌輸入項目</td> 
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
   <td>附註標籤</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td>✓</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>產品組合</td> 
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
   <td>保留時間* </td> 
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

+++**每個Workfront搜尋模組可用的物件型別**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> </th> 
   <th>[!UICONTROL 搜尋]</th> 
   <th>[!UICONTROL 讀取相關記錄]</th> 
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
   <td>Hour</td> 
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
   <td>日誌輸入項目</td> 
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
   <td>附註標籤</td> 
   <td>✓</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>產品組合</td> 
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
   <td>保留時間* </td> 
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

建議您仔細檢查，確保此功能的運作方式與預期的一樣。

+++

## Workfront > [!UICONTROL 觀看活動]模組中的活動訂閱篩選器

>[!NOTE]
>
>* 我們強烈建議您在您的[!UICONTROL 觀看活動]模組中使用事件訂閱篩選器。
>
>* Workfront最近發佈了其事件訂閱服務的新版本。 新版本並非變更Workfront API，而是變更事件訂閱功能。 此動作模組會更新用於此情境的事件裝載版本。
>
>   如需新事件訂閱版本的詳細資訊，請參閱Workfront檔案中的[事件訂閱版本設定](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-versioning)
>
>   如需在事件訂閱升級期間保留Workfront Fusion案例的資源（包括網路研討會影片），請參閱[在事件訂閱V2升級期間保留Fusion案例(https://experienceleaguecommunities.adobe.com/t5/workfront-discussions/event-follow-up-preserving-your-fusion-scenarios-during-the/td-p/754182)]。

Workfront [!UICONTROL 觀看活動]模組會根據在Workfront API中建立活動訂閱的webhook觸發案例。 事件訂閱是一組資料，可決定要將哪些事件傳送到webhook。 例如，如果您設定監視問題的[!UICONTROL 監視事件]模組，則事件訂閱只會傳送與問題相關的事件。

透過使用事件訂閱篩選器，Fusion使用者可建立更適合其使用案例的事件訂閱。 例如，您可以在Workfront API中設定事件訂閱，以僅將特定專案中的問題傳送至webhook，確保[!UICONTROL 觀看事件]模組僅會觸發該專案中的問題。 建立較窄觸發器的功能可減少不相關觸發器的數量，進而改善情境設計。

這與在Workfront Fusion情境中設定篩選器不同。 如果沒有事件訂閱篩選器，您的webhook會接收與您選取的物件型別相關的所有事件。 這些事件大多與情境無關，必須先篩選掉，情境才能繼續。

「Workfront >關注事件」篩選器中提供下列運運算元：

* 等於
* 不等於
* 大於
* 小於
* 大於或等於
* 小於或等於
* 包含
* 存在
   * 此運運算元不需要值，而且值欄位不存在。
* 不存在
   * 此運運算元不需要值，而且值欄位不存在。
* 已變更
   * 此運運算元不需要值，而且值欄位不存在。
   * 此運運算元會忽略狀態列位。
   * 使用`Changed`時，請在&#x200B;**記錄來源**&#x200B;欄位中選取&#x200B;**僅更新事件**。

>[!IMPORTANT]
>
>您無法在現有的Workfront Webhook中編輯篩選器。 若要為Workfront活動訂閱設定不同的篩選器，請移除目前的webhook並建立新的篩選器。

>[!INFO]
>
>**範例：**&#x200B;考慮處理指派給特定使用者Ana之新問題的案例。
>
>### 使用事件訂閱篩選器來篩選事件（建議使用）
>
>使用事件篩選器，您可以設定webhook以在建立問題時將問題指派給Ana時觸發情境。 Ana具有userID b378489d8f7cd3cee0539260720a84b7。
>
>![事件篩選器](/help/workfront-fusion/references/apps-and-modules/assets/event-filter-watch-events-350x277.png)
>
>如果一天內建立100個問題，但只有兩個問題指派給Ana，則案例會執行兩次。
>
>### 篩選案例中的事件（不建議）
>
>若要篩選事件，以便只處理指派給Ana的問題，您可以在[!UICONTROL 觀看事件]模組之後建立篩選器。
>
>![沒有事件篩選器](/help/workfront-fusion/references/apps-and-modules/assets/watch-events-non-event-filter-350x206.png)
>
>如果一天內建立100個問題，但只有兩個問題指派給Ana，則案例將執行100次。 98個執行會在篩選後停止，但觸發模組仍在所有執行中使用資料並執行操作。

如需Workfront活動訂閱的詳細資訊，請參閱[常見問題集 — 活動訂閱](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/adobe-workfront-api/event-subscriptions/event-subs-faq)。

如需Webhook的詳細資訊，請參閱Adobe Workfront Fusion中的[即時觸發器(Webhook)](/help/workfront-fusion/references/modules/webhooks-reference.md)

如需情境中篩選器的詳細資訊，請參閱[將篩選器新增至情境](/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md)。

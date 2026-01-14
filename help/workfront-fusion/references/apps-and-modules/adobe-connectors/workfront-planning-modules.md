---
title: Adobe Workfront 規劃模組
description: 透過 [!DNL Adobe Workfront Planning] 模組，您可以根據 [!DNL Adobe] Adobe Workfront Planning帳戶中的事件來啟動Workfront Fusion案例、建立、讀取或更新合約與其他記錄、使用您設定的條件搜尋記錄，以及上傳檔案。
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
source-git-commit: 86747ffc38fddde91352558277d40572d13ba2b0
workflow-type: tm+mt
source-wordcount: '1993'
ht-degree: 52%

---

# [!DNL Adobe Workfront Planning] 模組

透過[!DNL Adobe Workfront Planning]模組，您可以在Workfront Planning中發生事件時觸發案例。 您也可以建立、讀取、更新及刪除記錄，或執行自訂API呼叫至您的[!DNL Adobe Workfront Planning]帳戶。

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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

s##必要條件

您必須具備下列專案才能存取Workfront Planning：

* 新的Workfront套件和授權。 Workfront計畫不適用於舊版Workfront套件或授權。
* Workfront計畫套件。
* 貴組織的Workfront執行個體必須上線至Adobe統一體驗。

## Adobe Workfront規劃API資訊

Adobe Workfront Planning聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>https://{{connection.host}}/maestro/api/{{common.maestroApiVersion}}/</td> 
  </tr>
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## 將Workfront Planning連線至Workfront Fusion

Workfront Planning聯結器使用OAuth 2.0連線至Workfront Planning。

您可以直接從Workfront Planning Fusion模組內建立與Workfront Planning帳戶的連線。

* [使用使用者端ID和使用者端密碼連線至Workfront Planning](#connect-to-workfront-planning-using-client-id-and-client-secret)
* [使用伺服器對伺服器連線來連線至Workfront Planning](#connect-to-workfront--planning-using-a-server-to-server-connection)

### 使用使用者端ID和使用者端密碼連線至Workfront Planning

1. 在任何Adobe Workfront Planning模組中，按一下「連線」欄位旁的&#x200B;**新增**。
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

   如果您未登入Workfront Planning，系統會將您導向至登入畫面。 登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API 的 OAuth 2.0 連線不再依賴 API 金鑰。
>* 若要建立與 Workfront 沙箱環境的連線，您必須在該環境中建立 OAuth2 應用程式，然後在您的連線中使用該應用程式產生的用戶端 ID 和用戶端密碼。

### 使用伺服器對伺服器連線來連線至Workfront Planning

1. 在任何Adobe Workfront Planning模組中，按一下「連線」欄位旁的&#x200B;**新增**。
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

   如果您未登入Workfront Planning，系統會將您導向至登入畫面。 登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API 的 OAuth 2.0 連線不再依賴 API 金鑰。
>* 若要建立與 Workfront 沙箱環境的連線，您必須在該環境中建立 OAuth2 應用程式，然後在您的連線中使用該應用程式產生的用戶端 ID 和用戶端密碼。


## [!DNL Adobe Workfront Planning] 模組及其欄位

當您設定 Workfront 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 Workfront 欄位。在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。


![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)
* [未分類](#uncategorized)

### 觸發程序

#### 觀看活動

在Workfront Planning中建立、更新或刪除記錄、記錄型別或工作區時，此觸發模組會啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>選取您要使用的webhook，或按一下「新增」以建立新的webhook。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 物件類型]</td>
      <td>選取您要監視記錄、記錄型別或工作區。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 狀態]</td>
      <td>選取您要監視舊狀態或新狀態。<ul><li><p><b>[!UICONTROL 新狀態]</b></p><p>當記錄變更<b>為</b>特定值時觸發一個情境。</p></li><li><p><b>[!UICONTROL 舊狀態]</b></p><p>當記錄<b>從</b>特定值變更為其他時會觸發一個情境。</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>如果觀看記錄，請選取您要觀看記錄的Workspace 。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄類型]</td>
      <td>如果觀看記錄，請選取您要觀看的記錄型別。</td>
    </tr>
    </tr>
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL 事件篩選器]</p> </td> 
      <td> <p>您可以設定篩選器為僅監視符合所選取條件的記錄。</p> <p>對於每個篩選器，輸入您要篩選器評估的欄位、運算子，以及要讓篩選器允許的值。您可以新增 AND 規則，以便使用一個以上的篩選器。</p> <p>注意：您無法編輯現有Workfront Webhook中的篩選器。 若要為 Workfront 事件訂閱設定不同的篩選器，請移除目前的 Webhook 並建立新的。</p> <p>如需事件篩選的詳細資訊，請參閱Workfront模組文章中的Workfront &gt; [!UICONTROL 觀看活動]模組中的<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">事件訂閱篩選</a>。</p> </td> 
     </tr> 
    <tr>
      <td role="rowheader">要觀看的[!UICONTROL 物件]</td>
      <td>選取是否要監視新專案。 更新、新增和更新或刪除的記錄。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 排除此連線所做的更新]</p>
      </td>
      <td>啟用此選項可防止此模組使用的連線進行變更時觸發此案例。 如此可防止在此案例執行觸發動作時觸發另一個案例例項。</td> 
      </tr>
  </tbody>
</table>

### 動作

* [刪除記錄型別](#delete-a-record-type)
* [進行自訂AI呼叫](#make-a-custom-api-call)

#### 刪除記錄型別

此動作模組會依據其ID刪除Workfront Planning中的單一記錄型別。

>[!WARNING]
>
>刪除Workfront Planning中的記錄型別也會刪除記錄型別表格中的所有記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄型別的ID。</td> 
      </tr>
  </tbody>
</table>

#### 進行自訂的 API 呼叫

此模組會對[!DNL Adobe Workfront Planning] API發出自訂API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
      </td>
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 標頭]</td>
      <td>
        <p>以標準 JSON 物件的形式新增要求標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion 會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 查詢字串]  </td>
      <td>
        <p>針對您想要新增至查詢字串的每個索引鍵/值組，按一下<b>新增專案</b>並輸入索引鍵和值。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 正文]</td>
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>


### 搜尋

#### 搜尋記錄

此動作模組會根據您指定的條件擷取記錄清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>輸入或對應包含您要搜尋之記錄的Workspace。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要搜尋的記錄型別。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄欄位]</p>
      </td>
      <td>針對搜尋中要使用的每個欄位，找到該欄位，選取運運算元，然後輸入或對應您要搜尋的值。 根據所選的記錄型別，可使用欄位。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 篩選條件]</p>
      </td>
      <td>選取篩選條件：<ul><li><b>且</b><p>模組傳回符合您選取之欄位值的<b>所有</b>的記錄。</p></li><li><b>或</b><p>模組傳回符合您選取之欄位值的<b>任一</b>的記錄。</p></li></ul></td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 限制]</p>
      </td>
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
      </tr>
  </tbody>
</table>


### 未分類


#### 建立記錄

這個動作會在Workfront Planning中建立單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要建立的記錄型別。 可用的記錄型別取決於您的Workfront Planning帳戶。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>輸入您希望新記錄具有的值。 這些欄位是根據您選取的記錄型別。</td> 
      </tr>
     <tr>
  </tbody>
</table>

### 刪除記錄

此動作模組會刪除Workfront Planning中的指定記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄的ID。</td> 
      </tr>
  </tbody>
</table>

### 取得記錄

此動作模組會從其ID所指定的[!DNL Adobe Workfront Planning]擷取單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄ID]</td>
      <td>輸入或對應您要擷取之記錄的ID。</td>
    </tr>
  </tbody>
</table>

### 依記錄型別取得記錄

此動作模組會擷取指定型別的所有記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>選取或對映包含您要擷取之記錄的工作區。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄類型]</td>
      <td>選取您要擷取的記錄型別。</td>
    </tr>
     <!--<tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> -->
  </tbody>
</table>

### 取得記錄型別

此動作模組會擷取[!DNL Adobe Workfront Planning]帳戶中的記錄型別清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>選取或對應包含您要擷取之記錄型別的工作區。</td>
    </tr>
  </tbody>
</table>

### 更新記錄

此動作會更新Workfront Planning中的單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要更新的記錄型別。 可用的記錄型別取決於您的Workfront Planning帳戶。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>輸入您要記錄的新值。 這些欄位是根據您選取的記錄型別。</td> 
      </tr>
     <tr>
  </tbody>
</table>


## 使用JSONata進行可讀取的`record-types`劃分

下列JSONata運算式會建立可讀取的Planning查詢輸出，提供您記錄型別劃分。 這使記錄型別名稱、欄位名稱和欄位選項名稱（如果適用）可由名稱讀取，並保持結構的其餘部分不變。

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

如需有關使用JSONata模組的資訊，請參閱[JSONata模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md)。


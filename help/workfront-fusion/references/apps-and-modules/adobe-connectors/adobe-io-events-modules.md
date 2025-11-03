---
title: Adobe I/O Events模組
description: 透過Adobe I/O Events模組，您可以根據Adobe應用程式中的事件啟動Adobe Workfront Fusion案例。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: b2229f3e-a2a7-4b07-8ead-a37d193c2ec7
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 2%

---

# Adobe I/O Events模組

透過Adobe I/O Events模組，您可以根據沒有專用Adobe Workfront Fusion聯結器的Adobe帳戶和服務中的事件來啟動Workfront Fusion案例。

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
   <td role="rowheader">Adobe Workfront Fusion授權</td> 
   <td>
   <p>作業型：無Workfront Fusion授權需求</p>
   <p>以聯結器為基礎（舊版）：用於工作自動化和整合的Workfront Fusion </p>
   </td> 
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

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

使用Adobe I/O Events聯結器之前，您必須確保符合下列先決條件：

* 您必須擁有作用中的Adobe帳戶。

## Adobe I/O Events API資訊

Adobe I/O Events聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>https://api.adobe.io/events</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.6.7</td> 
  </tr>
 </tbody> 
 </table>

## 建立與Adobe I/O Events的連線

若要建立Adobe I/O Events模組的連線：

1. 按一下「連線」方塊旁的「新增」。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">連線名稱</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">環境</td>
        <td>
          <p>選取您要連線到生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">類型</td>
        <td>
          <p>選取您要連線到服務帳戶或個人帳戶。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">其他範圍</td>
        <td>若要新增任何其他範圍，請按一下[新增專案] <b> </b>並輸入範圍。</td>
      </tr>
      <tr>
        <td role="rowheader">用戶端 ID</td>
        <td>輸入您的Adobe使用者端ID。 您可在Adobe Developer Console的「認證詳細資料」區段中找到</td>
      </tr>
      <tr>
        <td role="rowheader">用戶端密碼</td>
        <td>輸入您的Adobe使用者端密碼。 您可在Adobe Developer Console的「認證詳細資料」區段中找到</td>
      </tr>
      </tr>
        <tr>
        <td role="rowheader">消費者組織ID</td>
        <td>輸入您的消費者組織ID。 您可以在專案的認證URL中找到此專案： <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">認證ID</td>
        <td>輸入您的認證識別碼。 您可以在專案的認證URL中找到此專案： <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">IMS組織ID</td>
        <td>輸入您的Adobe組織ID。 您可在Adobe Developer Console的「認證詳細資料」區段中找到</td>
      </tr>
        <tr>
        <td role="rowheader">專案 ID</td>
        <td>輸入您的專案ID。 您可以在專案的認證URL中找到此專案： <code>https://developer.adobe.com/console/projects/{consumer org ID}/ {project ID}/credentials/{credential ID}/details</code></td>
      </tr>
      <tr>
        <td role="rowheader">WORKSPACE ID</td>
        <td>若要檢視專案的Workspace ID，請從Adobe Developer Console的專案概觀頁面下載專案詳細資訊。 </td>
      </tr>
    </tbody>
    </table>

1. 按一下&#x200B;**繼續**&#x200B;以儲存連線並返回模組。

## Adobe I/O Events模組及其欄位

當您設定[!DNL Adobe I/O Events]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe I/O Events]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

<!--Becky start here-->

#### 建立事件註冊

此動作模組使用webhook建立事件說明。 您可以在這裡設定webhook。 如果您使用現有的webhook，則此模組中的欄位為唯讀。

若要建立webhook：

1. 按一下Webhook欄位旁的&#x200B;**新增**。
1. 填寫下列欄位：

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[！UICONTROL Webhook名稱]</td>
        <td>輸入此webhook的名稱。</td>
       </tr>
       <tr>
         <td role="rowheader">[！UICONTROL Connection]</td>
        <td>如需建立[!DNL Adobe I/O Events]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >建立與[!DNL Adobe I/O Events]</a>的連線。</td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL Webhook說明]
         </td>
         <td>
           輸入此webhook的說明。
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL事件提供者]
         </td>
         <td>
           選取您要建立事件的來源產品或帳戶。
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL事件型別]
         </td>
         <td>
           選取您希望webhook觀看的活動。 這些事件發生時會觸發此情境。
         </td>
       </tr>
     </tbody>
   </table>

1. 按一下儲存，儲存webhook並返回模組。

### 動作

* [取得提供者和事件ID](#get-provider-and-event-ids)
* [進行自訂API呼叫](#make-a-custom-api-call)

#### 取得提供者和事件ID

此搜尋模組會取得指定之提供者和事件的Adobe I/O Events ID。

<table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[！UICONTROL Connection]</td>
        <td>如需建立[!DNL Adobe I/O Events]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >建立與[!DNL Adobe I/O Events]</a>的連線。</td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL事件提供者]
         </td>
         <td>
           選取您要擷取ID的提供者。
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL事件型別]
         </td>
         <td>
              選取您要提供ID的事件。 根據事件提供者，可使用事件。 
         </td>
       </tr>
     </tbody>
   </table>


#### 進行自訂API呼叫

此動作模組會對[!DNL Adobe I/O Events] API發出自訂API呼叫

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
     <td role="rowheader">[！UICONTROL Connection]</td>
        <td>如需建立[!DNL Adobe I/O Events]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >建立與[!DNL Adobe I/O Events]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[！UICONTROL路徑]</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://api.adobe.io/events</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[！UICONTROL方法]</p>
      </td>
      <td>
  <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p>  
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會自動新增授權標題和x-api-key標題。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL查詢字串]  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL Body]</td>
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

### 搜尋

#### 從日誌取得所有事件

此搜尋模組會從日誌中擷取註冊的所有事件。

<table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">[！UICONTROL Connection]</td>
        <td>如需建立[!DNL Adobe I/O Events]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-io-events" class="MCXref xref" >建立與[!DNL Adobe I/O Events]</a>的連線。</td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL註冊ID]
         </td>
         <td>
           選取您要擷取事件的註冊。
        </td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL傳回事件數上限]
         </td>
         <td>
              輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。 
         </td>
       </tr>
       <tr>
         <td role="rowheader">
           [！UICONTROL傳回發生於]之後的事件
         </td>
         <td>輸入或對映日期。 模組會傳回此日期之後發生的事件。
         </td>
       </tr>
<!--       <tr>
         <td role="rowheader">
           [!UICONTROL Seek]
         </td>
         <td>
         </td>
       </tr>-->
       <tr>
         <td role="rowheader">
           [！UICONTROL Latest]
         </td>
         <td>
         啟用此選項以傳回最新事件。
         </td>
       </tr>
     </tbody>
   </table>
&lt;！—

觀看活動

此觸發模組會在所選Adobe產品或服務中發生事件時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">Webhook</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下webhook欄位旁的<b>新增</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您要觀看之事件的來源</li></ul></li><li>按一下<b>儲存</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

-->

---
filename: adobe-indesign-modules
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe InDesign模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Adobe InDesign的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
source-git-commit: 30ddefa8519e6f2052308482137d0fa018676902
workflow-type: tm+mt
source-wordcount: '1693'
ht-degree: 20%

---


# Adobe InDesign模組

在Adobe Workfront Fusion案例中，您可以自動化使用Adobe InDesign的工作流程，並將其連結至多個協力廠商應用程式和服務。

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

您必須先擁有作用中的Adobe InDesign帳戶，才能使用Adobe InDesign聯結器。

## 建立與Adobe InDesign的連線

若要建立Adobe InDesign模組的連線：

1. 在任何Adobe InDesign模組中，按一下[連線]方塊旁的&#x200B;**新增**。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col>
      </col>
      <col>
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
          <p>選取要連接至生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">類型</td>
        <td>
          <p>選取要連接至服務帳戶或者個人帳戶。</p>
        </td>
      </tr>
        <tr>
          <td role="rowheader">用戶端 ID</td>
          <td>輸入您的Adobe使用者端ID。 您可在Adobe Developer Console的「認證詳細資料」區段中找到</td>
        </tr>
        <tr>
          <td role="rowheader">用戶端密碼</td>
          <td>輸入您的Adobe使用者端密碼。 您可在Adobe Developer Console的「認證詳細資料」區段中找到</td>
        </tr>
        <tr>
          <td role="rowheader">IMS 組織 ID</td>
          <td>輸入您的Adobe組織ID。 您可在Adobe Developer Console的「認證詳細資料」區段中找到</td>
        </tr>
      </tbody>
    </table>
1. 按一下「**繼續**」，儲存連線並返回模組。

## InDesign模組及其欄位

設定Adobe InDesign模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Adobe InDesign欄位，視您應用程式或服務中的存取層級等因素而定。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 動作

* [建立轉譯](#create-rendition)
* [刪除自訂指令碼](#delete-a-custom-script)
* [合併資料](#merge-data)
* [重新對應連結](#remap-links)
* [提交自訂指令碼執行請求](#submit-a-custom-script-execution-request)

#### 建立轉譯

此動作模組會建立並傳回特定InDesign檔案的JPEG、PNG或PDF轉譯。 如需`StatusCompletedRespons/output/data`的結構，請參閱`RenditionOutputData`。 如需`FailedEvent`中可能的錯誤碼清單，請參閱`RenditionFailedData`。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>類型</p>
      </td>
      <td>選取您要建立的轉譯檔案型別。 
      <ul><li>JPEG</li><li>PNG</li><li>PDF</li></ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>資產</p>
      </td>
      <td>針對您想要新增至轉譯的每個資產：<ol><li>按一下<b>新增專案</b>。</li><li>選取或對應資產的來源。</li><li>輸入目的地。 目的地是相對於下載資源的暫存基底目錄（工作目錄）的路徑。 這可在引數中識別資產。 無法使用'..'上傳 或'/'。 應該要有有效的檔案名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">目標檔案</td>
      <td>輸入或對映將處理和轉譯的檔案。 目前一次僅支援一個檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">其他欄位</td>
   <td>如需其他欄位，請參閱模組包含的資訊。</td>     </tr>
  </tbody>
</table>

#### 刪除自訂指令碼

此動作模組會刪除單一已註冊的自訂指令碼。 將永久移除指令碼的所有版本。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>指令碼名稱</p>
      </td>
      <td>輸入或對應您要刪除的指令碼名稱。</td>
    </tr>
  </tbody>
</table>

#### 合併資料

此模組會將CSV資料與InDesign範本合併，以建立InDesign檔案或PDF。 輸出格式包括JPEG、PNG、PDF和InDesign檔案。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>資產</p>
      </td>
      <td>針對您要新增至資料合併的每個資產：<ol><li>按一下<b>新增專案</b>。</li><li>選取或對應資產的來源。</li><li>輸入目的地。 目的地是相對於下載資源的暫存基底目錄（工作目錄）的路徑。 這可在引數中識別資產。 無法使用'..'上傳 或'/'。 應該要有有效的檔案名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">目標檔案</td>
      <td>輸入或對應要用來作為合併範本的檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">資料來源</td>
      <td>輸入或對應要使用的來源檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">其他欄位</td>
   <td>如需其他欄位，請參閱模組包含的資訊。</td>     </tr>
  </tbody>
</table>

#### 重新對應連結

此模組以Adobe Experience Manager (AEM) URL取代InDesign檔案中的檔案型連結。 這對使用Adobe Asset Link的Adobe Experience Manager來說很有用。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
      </tr>
    <tr>
      <td role="rowheader">AEM Token</td>
      <td>輸入或對應為AEM技術帳戶產生的持有人權杖，不含持有人權杖。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>資產</p>
      </td>
      <td>針對您想要新增至模組的每個資產：<ol><li>按一下<b>新增專案</b>。</li><li>選取或對應資產的來源。</li><li>輸入目的地。 目的地是相對於下載資源的暫存基底目錄（工作目錄）的路徑。 這可在引數中識別資產。 無法使用'..'上傳 或'/'。 應該要有有效的檔案名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">目標檔案</td>
      <td>輸入或對映您要在其中重新對映連結的檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">資料來源</td>
      <td>輸入或對應要用於擷取及比對標籤的來源檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">其他欄位</td>
   <td>如需其他欄位，請參閱模組包含的資訊。</td>     </tr>
  </tbody>
</table>

#### 提交自訂指令碼執行請求

此動作模組會提交自訂指令碼的執行請求。 您可以定義自訂指令碼在執行期間使用的輸入資產和引數。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>指令碼ID</p>
      </td>
      <td>輸入或對映自訂指令碼的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>資產</p>
      </td>
      <td>針對您要提交執行者請求的每個資產， <ol><li>按一下<b>新增專案</b>。</li><li>選取或對應資產的來源。</li><li>輸入目的地。 目的地是相對於下載資源的暫存基底目錄（工作目錄）的路徑。 這可在引數中識別資產。 無法使用'..'上傳 或'/'。 應該要有有效的檔案名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">其他欄位</td>
   <td>如需其他欄位，請參閱模組包含的資訊。</td>     </tr>
  </tbody>
</table>

### 搜尋

* [取得自訂指令碼詳細資料](#get-custom-script-details)
* [取得資料合併標籤](#get-data-merge-tags)
* [取得檔案資訊](#get-document-information)
* [列出自訂指令碼](#list-custom-scripts)

#### 取得自訂指令碼詳細資料

此搜尋模組會擷取單一已註冊自訂指令碼的詳細資料，包括版本、下載連結、註冊日期和指令碼名稱。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>指令碼名稱</p>
      </td>
      <td>輸入或對應您要擷取其詳細資訊的指令碼名稱。</td>
    </tr>
  </tbody>
</table>

#### 取得資料合併標籤

此模組會從檔案中擷取資料合併標籤。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>資產</p>
      </td>
      <td>針對您想要新增至模組的每個資產：<ol><li>按一下<b>新增專案</b>。</li><li>選取或對應資產的來源。</li><li>輸入目的地。 目的地是相對於下載資源的暫存基底目錄（工作目錄）的路徑。 這可在引數中識別資產。 無法使用'..'上傳 或'/'。 應該要有有效的檔案名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">目標檔案</td>
      <td>輸入或對應您要從中擷取標籤的檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">資料來源</td>
      <td>輸入或對應要用於擷取及比對標籤的來源檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">其他欄位</td>
   <td>如需其他欄位，請參閱模組包含的資訊。</td>     </tr>
  </tbody>
</table>

#### 取得檔案資訊

此模組會擷取有關INDD/IDML檔案的完整資訊，並根據請求中指定的啟用資訊型別傳回資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
      </tr>
    <tr>
      <td role="rowheader">
        <p>資產</p>
      </td>
      <td>針對您想要新增至模組的每個資產：<ol><li>按一下<b>新增專案</b>。</li><li>選取或對應資產的來源。</li><li>輸入目的地。 目的地是相對於下載資源的暫存基底目錄（工作目錄）的路徑。 這可在引數中識別資產。 無法使用'..'上傳 或'/'。 應該要有有效的檔案名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">目標檔案</td>
      <td>輸入或對應您要從中擷取資訊的檔案。</td>
    </tr>
     <tr>
      <td role="rowheader">其他欄位</td>
   <td>如需其他欄位，請參閱模組包含的資訊。</td>     </tr>
  </tbody>
</table>

#### 列出自訂指令碼

此模組會擷取所有已註冊自訂指令碼最新版本的詳細資料，包括版本、下載連結、註冊日期和指令碼名稱。 結果會根據清單長度分頁。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
      </tr>
    <tr>
      <td role="rowheader">頁碼</td>
      <td>輸入或對映您要開始的頁碼。</td>
    </tr>
  <tr> 
   <td>傳回結果的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期中傳回的團隊或群組數量上限。</td> 
  </tr> 
  </tbody>
</table>


### 其他

#### 進行自訂的 API 呼叫

此模組會對Adobe InDesign API發出自訂API呼叫

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需建立與Adobe InDesign的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-indesign" class="MCXref_0">建立與Adobe InDesign的連線</a>。</td>
    </tr>
       <tr>
      <td role="rowheader">
        <p>路徑</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://indesign.adobe.io/v3</code> 的路徑。</p><p> 範例： <code>/create-rendition</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>方法</p>
      </td>
      <td>
        <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱[HTTP要求方法](/help/workfront-fusion/references/modules/http-request-methods.md)。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">標頭</td>
      <td>
        <p>以標準 JSON 物件的形式新增要求標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion 會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">查詢字串  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
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

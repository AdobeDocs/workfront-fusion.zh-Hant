---
title: Veeva儲存庫模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Veeva Vault的工作流程，並將其連線到多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
source-git-commit: 37cb18a2e13a494c4174514539c0c7e43cdee011
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 3%

---

# Veeva儲存庫模組

在Adobe Workfront Fusion案例中，您可以自動化使用Veeva Vault的工作流程，並將其連線到多個第三方應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

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

若要使用Veeva Vault模組，您必須擁有Veeva Vault帳戶。

## 將Veeva Vault連線至Workfront Fusion

您可以直接從Veeva Vault模組內建立與Veeva Vault帳戶的連線。

1. 在任何Veeva儲存庫模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 填寫下列欄位。

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">連線名稱</td> 
       <td> <p>輸入連線的名稱。</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">環境</td>
        <td>
          <p>選取要連線到生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">類型</td>
        <td>
          <p>選取您要連線到服務帳戶還是個人帳戶。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">使用者名稱</td>
        <td>
          <p>輸入Veeva Vault帳戶的使用者名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">密碼</td>
        <td>
          <p>輸入Veeva Vault帳戶的密碼。</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">儲存庫DNS</td> 
       <td>輸入您的Veeva Vault DNS （網域名稱）。</p><p>若要找到Veeva Vault DNS，請檢查您用來存取Veeva Vault的URL。</p>例如，在URL <code>https://my-dns.veevavault.com</code>中，DNS是<code>my-dns</code>。 您不需要輸入整個URL。</td> 
      </tr> 
     </tbody> 
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。



## Veeva Vault模組及其欄位

設定Veeva Vault模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Veeva Vault欄位，視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 文件

* [建立單一檔案](#create-a-single-document)
* [建立多個檔案](#create-multiple-documents)
* [刪除單一檔案](#delete-a-single-document)
* [匯出檔案](#export-documents)
* [取得單一檔案](#get-a-single-document)
* [啟動使用者動作](#initiate-user-action)
* [列出檔案](#list-documents)
* [擷取檔案匯出結果](#retrieve-document-export-results)
* [更新多份檔案](#update-multiple-documents)
* [更新單一檔案](#update-a-single-document)

#### 建立單一檔案

此模組會建立單一檔案、資料夾或範本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要建立檔案、繫結器或範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>選取欄位</p> </td> 
   <td> <p>選取您要輸入資料的欄位，然後在那些欄位中輸入資料。</td> 
  </tr> 
 </tbody> 
</table>

#### 建立多個檔案

此模組會使用CSV檔案建立多個檔案或範本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要建立範本或檔案</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>檔案資料</p> </td> 
   <td> <p>對應將用於建立檔案的CSV檔案。</td> 
  </tr> 
 </tbody> 
</table>

#### 刪除單一檔案

此模組會刪除單一檔案、資料夾或範本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要刪除檔案、繫結器或範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>檔案ID/繫結器ID/範本名稱</p> </td> 
   <td> <p>選取您要刪除的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### 匯出檔案

此模組會匯出您指定的檔案，包括來源、轉譯和文字。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要刪除檔案、繫結器或範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>來源</p> </td> 
   <td> <p>啟用此選項以在匯出中包含來源檔案。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>轉譯</p> </td> 
   <td> <p>啟用此選項以在匯出中包含轉譯檔案。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>所有版本</p> </td> 
   <td> <p>啟用此選項以在匯出中包含檔案檔案的所有版本。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>文字</p> </td> 
   <td> <p>啟用此選項以在匯出中包含來原始檔文字。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 取得單一檔案

此模組會擷取單一檔案、資料夾或範本的中繼資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取是否要擷取檔案、繫結器或範本的資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>檔案ID/繫結器ID/範本名稱</p> </td> 
   <td> <p>選取您要擷取資料的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### 啟動使用者動作

此模組會對檔案和資料夾啟動動作，例如傳送檔案以供稽核或變更其狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要在檔案或繫結器上執行動作。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>檔案/資料夾</p> </td> 
   <td> <p>選取您要對其執行動作的檔案或資料夾。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>檔案版本/繫結器版本</p> </td> 
   <td> <p>選取您要對其執行動作的檔案或資料夾。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>動作</p> </td> 
   <td> <p>選取要在檔案或繫結器上執行的動作。</td> 
  </tr> 
 </tbody> 
</table>

#### 列出檔案

此模組會列出所選型別的所有檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要列出檔案、資料夾或範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>

#### 擷取檔案匯出結果

此模組會傳回先前請求的檔案匯出結果。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>工作ID</p> </td> 
   <td> <p>輸入或對應您要傳回結果的作業ID。 </p> </td> 
  </tr> 
  </tbody> 
</table>

#### 更新多份檔案

此模組會使用CSV檔案更新多個檔案或範本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要建立範本或檔案</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>檔案資料</p> </td> 
   <td> <p>對應將用於建立檔案的CSV檔案。</td> 
  </tr> 
 </tbody> 
</table>

#### 更新單一檔案

此模組會更新單一檔案、資料夾或範本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要建立檔案、檔案版本、繫結器或範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID/名稱</p> </td> 
   <td> <p>如果您要更新範本，請輸入範本的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>新範本名稱</p> </td> 
   <td> <p>輸入或對應您要更新的物件ID或名稱。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">  <p>選取欄位</p> </td> 
   <td> <p>選取您要輸入資料的欄位，然後在那些欄位中輸入資料。</td> 
  </tr> 
 </tbody> 
</table>

### 物件



#### 列出物件

此模組會擷取已驗證儲存庫中的所有儲存庫物件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>擷取當地語系化標籤</p> </td> 
   <td> <p>選取「是」以擷取label和label_plural物件欄位的本地化（轉譯）字串。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [進行自訂API呼叫](#make-a-custom-api-call)
* [進行VQL查詢](#make-a-vql-query)
* [讀取記錄](#read-logs)

#### 進行自訂API呼叫

此動作模組會對Veeva Vault API進行自訂呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>輸入相對於<code>baseurl/api/v</code>的路徑。  例如： <code>/objects/documents</code>。 不要包含<code>baseurl/api/v/</code>，因為它已包含。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方法</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">標頭</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">查詢字串</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">內文</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 進行VQL查詢

此模組會使用Vault Query Language (VQL)進行查詢。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要建立範本或檔案</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">  <p>檔案資料</p> </td> 
   <td> <p>對應將用於建立檔案的CSV檔案。</td> 
  </tr> 
 </tbody> 
</table>

#### 讀取記錄

此模組會從稽核軌跡傳回資料

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>稽核型別</p> </td> 
   <td> <p>選取您要擷取資料的稽核型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>開始日期</p> </td> 
   <td> <p>輸入或對應您要擷取之稽核的開始日期。</p><p>如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>結束日期</p> </td> 
   <td> <p>輸入或對應您要擷取之稽核的結束日期。</p><p>如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>結果URL </p> </td> 
   <td> <p>如果您想要取得URL以下載結果的CSV，請選取CSV。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>



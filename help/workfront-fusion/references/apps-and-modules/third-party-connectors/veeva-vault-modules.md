---
title: Veeva Vault 模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Veeva Vault的工作流程，並將其連線到多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
source-git-commit: 881e5ba39d1730b641085cf0d02137d18e443135
workflow-type: tm+mt
source-wordcount: '2485'
ht-degree: 19%

---

# Veeva Vault 模組

在Adobe Workfront Fusion案例中，您可以自動化使用Veeva Vault的工作流程，並將其連線到多個第三方應用程式和服務。

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

若要使用Veeva Vault模組，您必須擁有Veeva Vault帳戶。

## 將Veeva Vault連線至Workfront Fusion

您可以直接從Veeva Vault模組內建立與Veeva Vault帳戶的連線。

建立連線時，您可以選取是否使用密碼，或是否使用OAuth2驗證。

### 使用使用者名稱和密碼連線至Veeva Vault

1. 在任何Veeva儲存庫模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 在&#x200B;**連線型別**&#x200B;欄位中，選取`Veeva Username Password`。
1. 填寫下列欄位。

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">連線名稱</td> 
       <td> <p>輸入此連線的名稱。</p> </td> 
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

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

### 使用OAuth2驗證連線至Veeva Vault

1. 在任何Veeva儲存庫模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 在&#x200B;**連線型別**&#x200B;欄位中，選取`Veeva Oauth 2`。
1. 填寫下列欄位。

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">連線名稱</td> 
       <td> <p>輸入此連線的名稱。</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">用戶端 ID</td>
        <td>
          <p>輸入此連線將使用的Veeva Vault應用程式的使用者端ID。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">用戶端密碼</td>
        <td>
          <p>輸入此連線將使用的Veeva Vault應用程式的使用者端密碼。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">範圍</td>
        <td>
          <p>輸入此連線的範圍。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">租使用者ID</td>
        <td>
          <p>輸入此連線的租使用者ID。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">設定檔ID</td>
        <td>
          <p>輸入您OAuth2 / Copen ID Connect設定檔的ID。</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">儲存庫DNS</td> 
       <td>輸入您的Veeva Vault DNS （網域名稱）。</p><p>若要找到Veeva Vault DNS，請檢查您用來存取Veeva Vault的URL。</p>例如，在URL <code>https://my-dns.veevavault.com</code>中，DNS是<code>my-dns</code>。 您不需要輸入整個URL。</td> 
      </tr> 
     </tbody> 
    </table>

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。


## Veeva Vault模組及其欄位

設定Veeva Vault模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Veeva Vault欄位，視您應用程式或服務中的存取層級等因素而定。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [文件](#document)
* [物件](#object)
* [其他](#other)

### 文件

* [建立單一檔案](#create-a-single-document)
* [建立多個檔案](#create-multiple-documents)
* [刪除單一檔案](#delete-a-single-document)
* [下載檔案](#download-file)
* [匯出檔案](#export-documents)
* [取得單一檔案](#get-a-single-document)
* [啟動使用者動作](#initiate-user-action)
* [列出檔案](#list-documents)
* [擷取檔案匯出結果](#retrieve-document-export-results)
* [更新單一檔案](#update-a-single-document)
* [更新多份檔案](#update-multiple-documents)

#### 建立單一檔案

此模組會建立單一檔案、資料夾或範本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線 </td> 
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
   <td role="rowheader">連線 </td> 
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
   <td role="rowheader">連線 </td> 
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

#### 下載檔案

此模組會從Veeva Vault下載檔案、檔案版本或範本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要下載檔案或範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>下載型別</p> </td> 
   <td> <p>選取您要下載檔案或檔案版本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>檔案ID/範本名稱</p> </td> 
   <td> <p>輸入或對應檔案的ID或您要下載的範本名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>簽出檔案</p> </td> 
   <td> <p>如果您正在下載檔案，請啟用此選項以在下載檔案之前先出庫檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"><p>版本</p> </td> 
   <td> <p>如果您正在下載檔案版本，請選取要下載的版本。</td> 
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
   <td role="rowheader">連線 </td> 
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
   <td role="rowheader">連線 </td> 
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
   <td role="rowheader">連線 </td> 
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
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取您要列出檔案、資料夾或範本。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</td> 
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
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>工作 ID</p> </td> 
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
   <td role="rowheader">連線 </td> 
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
   <td role="rowheader">連線 </td> 
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

* [建立單一物件記錄](#create-a-single-object-record)
* [刪除單一物件記錄](#delete-a-single-object-record)
* [取得單一物件](#get-a-single-object)
* [列出物件記錄](#list-objects-records)
* [更新單一物件記錄](#update-a-single-object-record)

#### 建立單一物件記錄

此模組會建立、複製或深層複製單一物件記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取是否要建立或複製記錄，或是否要深層複製記錄。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">移轉模式</td> 
   <td>如果建立或複製記錄，請啟用此選項以建立或更新非初始狀態的物件記錄，並以最小的驗證方式，建立非使用中記錄，以及設定標準和系統管理的欄位，例如<code>createdby_v</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">無觸發程式</td> 
   <td>如果設為true且已啟用移轉模式，則模組會略過所有系統、標準、自訂SDK觸發程式和動作觸發程式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">物件名稱</td> 
   <td>輸入或對應物件名稱__v欄位值，例如<code>product__v</code>、<code>country__v</code>或<code>custom_object__c</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄ID</td> 
   <td>如果您要深度複製記錄，請選取要複製的記錄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄欄位</td> 
   <td>如果您深度複製記錄，請選取要提供值的欄位，然後提供這些值。</td> 
  </tr> 
 </tbody> 
</table>

#### 刪除單一物件記錄

此模組會刪除或重疊刪除單一物件記錄。 重疊刪除記錄會刪除記錄及其所有子物件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取要刪除記錄，還是重疊刪除記錄。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">物件名稱</td> 
   <td>選取您要刪除的物件。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄ID</td> 
   <td>選取您要刪除的記錄ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">外部 ID</td> 
   <td>您可以使用這個使用者定義檔案外部ID，而不使用記錄ID。</td> 
  </tr> 
 </tbody> 
</table>

#### 取得單一物件

此模組會擷取在儲存庫中特定物件記錄上設定的中繼資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">物件名稱</td> 
   <td>選取您要擷取中繼資料的物件。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄ID</td> 
   <td>選取您要擷取中繼資料的記錄ID。</td> 
  </tr> 
 </tbody> 
</table>

#### 列出物件記錄

此模組會擷取已驗證儲存庫中的所有儲存庫物件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>擷取當地語系化標籤</p> </td> 
   <td> <p>選取「是」以擷取label和label_plural物件欄位的本地化（轉譯）字串。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</td> 
  </tr> 
 </tbody> 
</table>

<!--#### Update a single object record-->

此模組會更新現有物件記錄中的欄位。

此模組會建立、複製或深層複製單一物件記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>類型</p> </td> 
   <td> <p>選取是否要建立或複製記錄，或是否要深層複製記錄。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">移轉模式</td> 
   <td>啟用此選項以建立或更新非初始狀態且驗證最少的物件記錄、建立非使用中記錄，以及設定標準和由系統管理的欄位，例如<code>createdby_v</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">無觸發程式</td> 
   <td>如果已啟用移轉模式，您可以啟用此選項以略過所有系統、標準、自訂SDK觸發程式和動作觸發程式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">物件名稱</td> 
   <td>輸入或對應物件名稱__v欄位值，例如<code>product__v</code>、<code>country__v</code>或<code>custom_object__c</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄ID</td> 
   <td>選取要更新的記錄識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">狀態</td> 
   <td>指定當<code>X-VaultAPI-MigrationMode</code>設為true時記錄的生命週期狀態。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">狀態標籤</td> 
   <td>當<code>X-VaultAPI-MigrationMode</code>設為true時，指定記錄的生命週期狀態型別。 使用格式<code>base:object_lifecycle:</code>，後接物件狀態型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄欄位</td> 
   <td>如果您深度複製記錄，請選取要提供值的欄位，然後提供這些值。</td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [進行自訂的 API 呼叫](#make-a-custom-api-call)
* [進行VQL查詢](#make-a-vql-query)
* [讀取記錄](#read-logs)

#### 進行自訂的 API 呼叫

此動作模組會對Veeva Vault API進行自訂呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>輸入相對於<code>baseurl/api/v</code>的路徑。  例如： <code>/objects/documents</code>。 不要包含<code>baseurl/api/v/</code>，因為它已包含。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方法</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">標頭</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">查詢字串</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">正文</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
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
   <td role="rowheader">連線 </td> 
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
   <td role="rowheader">連線 </td> 
   <td> <p>如需有關將Veeva Vault帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>稽核型別</p> </td> 
   <td> <p>選取您要擷取資料的稽核型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>開始日期</p> </td> 
   <td> <p>輸入或對應您要擷取之稽核的開始日期。</p><p>如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">類型強制轉換</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>結束日期</p> </td> 
   <td> <p>輸入或對應您要擷取之稽核的結束日期。</p><p>如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">類型強制轉換</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>結果URL </p> </td> 
   <td> <p>如果您想要取得URL以下載結果的CSV，請選取CSV。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</td> 
  </tr> 
 </tbody> 
</table>



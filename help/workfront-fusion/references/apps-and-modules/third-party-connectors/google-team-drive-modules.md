---
title: Google團隊磁碟機模組
description: ' [!DNL Adobe Workfront Fusion Google Team Drive] 模組可讓您監視、上傳、更新、複製、刪除或擷取檔案，以及在 [!DNL Google Shared] 磁碟機中建立資料夾。'
author: Becky
feature: Workfront Fusion
exl-id: 95dd9d23-1df9-40da-8fd0-646cc697bfc8
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1370'
ht-degree: 0%

---

# [!DNL Google Team Drive]模組

Adobe Workfront Fusion [!DNL Google Team Drive]模組可讓您監視、上傳、更新、複製、刪除或擷取檔案，以及在您的[!DNL Google Shared Drive]中建立資料夾。

若要搭配Adobe Workfront Fusion使用[!DNL Google Team Drive]，您必須有[!DNL Google Workspace]帳戶。 如果您沒有帳戶，可以在[!DNL Google Workspace]註冊網站[[!DNL Google Workspace] 建立](https://workspace.google.com/business/signup/welcome)帳戶。

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Google Team Drive]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!DNL Google Team Drive]模組，您必須有[!DNL Google Team Drive]。

## [!DNL Google Team Drive]模組及其欄位

當您設定[!DNL Google Team Drive]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Team Drive]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

以&#x200B;**bold**&#x200B;顯示的模組對話方塊欄位(在Workfront Fusion案例中，此檔案文章中為&#x200B;**not**)是必要的。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 觸發程序

#### [!UICONTROL 觀看檔案]

在指定的資料夾中新增和/或修改新檔案時，傳回檔案詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> 選取您要觀看的共用磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾] </td> 
   <td> <p>選取共用磁碟機中的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 要觀看的檔案]</td> 
   <td> <p> 選取您要觀看的檔案型別。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Documents]個檔案轉換為格式] </td> 
   <td> <p>選取您要將watched [!DNL Google Documents]檔案轉換為的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Sheets]個檔案轉換為格式] </td> 
   <td> <p>選取您要將watched [!DNL Google Sheets]檔案轉換為的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Slides]個檔案轉換為格式] </td> 
   <td> <p>選取您要將watched [!DNL Google Slides]檔案轉換為的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Drawings]個檔案轉換為格式] </td> 
   <td> <p>選取您要將watched [!DNL Google Drawings]檔案轉換為的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 手錶]</td> 
   <td> <p> 選取您要監視資料夾中是否有新的和修改的檔案，或只監視新檔案。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 下載檔案數上限]</td> 
   <td> <p> 設定Workfront Fusion在一個執行週期內傳回的最大檔案數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 上傳檔案]](#upload-a-file)
* [[!UICONTROL 更新檔案]](#update-a-file)
* [[!UICONTROL 複製檔案]](#copy-a-file)
* [[!UICONTROL 刪除檔案]](#delete-a-file)
* [[!UICONTROL 將檔案移至垃圾桶]](#move-a-file-to-trash)
* [[!UICONTROL 取得檔案]](#get-a-file)
* [[!UICONTROL 取得檔案清單]](#get-a-file-list)
* [[!UICONTROL 建立資料夾]](#create-a-folder)

#### [!UICONTROL 上傳檔案]

將檔案上傳至指定的共用磁碟機。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive] </td> 
   <td> <p>選取您要上傳檔案的共用磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾] </td> 
   <td> <p>選取共用磁碟機中的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source檔案]</p> </td> 
   <td> <p>指定您要上傳至共用磁碟機的檔案。</p> <p>對應您要從上一個模組上傳的檔案(例如[!UICONTROL HTTP] &gt; [!UICONTROL 取得檔案]或[!UICONTROL Dropbox] &gt;[!UICONTROL 取得檔案)]，或手動輸入檔案名稱和檔案資料。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 標題]</td> 
   <td> <p> 輸入將在共用資料夾中顯示的檔案標題。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 轉換檔案]</td> 
   <td> <p> 啟用此選項可將檔案轉換為共用資料夾中對應的Google格式。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新檔案]

可讓您變更檔案名稱和/或檔案內容。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> 選取包含要更新檔案的共用磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾] </td> 
   <td> <p>選取共用磁碟機中的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td> <p> 輸入（對應）您要更新的檔案ID。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source檔案]</p> </td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 標題] </td> 
   <td> <p>輸入更新檔案的新標題。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 轉換檔案]</td> 
   <td> <p> 啟用此選項可將檔案轉換為共用資料夾中對應的[!DNL Google]格式。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 複製檔案]

將指定的檔案複製到選取的資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> 選取包含您要複製之檔案的共用磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾] </td> 
   <td> <p>選取您要複製檔案的目標資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td> <p> 輸入（對應）您要複製的檔案ID。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL 複製檔案的名稱]</p> </td> 
   <td> <p>如果您想要在目標位置變更新檔案名稱，請輸入新檔案名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除檔案]

刪除指定的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td> <p> 輸入或對應您要刪除之檔案的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 將檔案移至垃圾桶]

將指定的檔案移至垃圾桶。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td> <p> 輸入或對應您要移至垃圾桶之檔案的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得檔案]

擷取有關指定檔案的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Documents]個檔案轉換為格式] </td> 
   <td> <p>選取您要將[!DNL Google Documents]個檔案轉換成的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Sheets]個檔案轉換為格式] </td> 
   <td> <p>選取您要將[!DNL Google Sheets]個檔案轉換成的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Slides]個檔案轉換為格式] </td> 
   <td> <p>選取您要將[!DNL Google Slides]個檔案轉換成的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Drawings]個檔案轉換為格式] </td> 
   <td> <p>選取您要將[!DNL Google Drawings]個檔案轉換成的格式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td> <p> 輸入或對應您要擷取的檔案ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得檔案清單]

根據搜尋字詞擷取檔案和/或資料夾詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> 選取要列出檔案的共用磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾] </td> 
   <td> <p>選取您要列出檔案的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋] </td> 
   <td> <p>選取您要執行的搜尋型別 — 請參閱下文。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Query]</p> </td> 
   <td> 
    <ul> 
     <li style="font-weight: bold;"> <p>[!UICONTROL 在檔案名稱中搜尋]</p> <p style="font-weight: normal;">選取[!UICONTROL 搜尋確切的字詞搜尋]選項時，輸入檔案名稱（包括副檔名），或選取[!UICONTROL 搜尋包含搜尋字詞的名稱]選項時，輸入名稱的一部分。</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL 全文檢索搜尋]</p> <p>輸入搜尋字詞，以搜尋檔案名稱、說明和內容。</p> </li> 
     <li> <p style="font-weight: bold;">[!UICONTROL 自訂搜尋查詢]</p> <p>輸入[!DNL Google]搜尋查詢詞。 如需更多詳細資料，請參閱[!DNL Google]的<a href="https://developers.google.com/drive/api/v2/ref-search-terms">搜尋查詢檔案</a>。 範例： <code>fullText contains '"Hello world"'</code></p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Retrieve]</td> 
   <td>選取您要擷取檔案、資料夾或兩者。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 傳回結果的最大數目]</td> 
   <td> <p> 設定Workfront Fusion在一個執行週期中傳回的檔案或資料夾數量上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立資料夾]

建立新資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Team Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Team Drive]</td> 
   <td> <p> 選取您要建立資料夾的共用磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾] </td> 
   <td> <p>選取您要建立資料夾的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 新資料夾的名稱]</td> 
   <td> <p> 輸入新資料夾的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

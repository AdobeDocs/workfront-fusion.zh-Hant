---
title: 方塊模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Box的工作流程，並將其連結到多個協力廠商應用程式和服務。 監視指定的資料夾以檢查檔案變更、修改和刪除現有檔案，或將新檔案上傳到資料夾。
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 1%

---

# 方塊模組

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Box]的工作流程，並將其連線至多個協力廠商應用程式和服務。 監視指定的資料夾以檢查檔案變更、修改和刪除現有檔案，或將新檔案上傳到資料夾。

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

若要使用[!DNL Box]模組，您必須有[!DNL Box]帳戶。

## Box API資訊

Box聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://api.box.com/2.0
    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v3.0.3</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Box]模組及其欄位

當您設定[!DNL Box]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Box]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

* [[!UICONTROL 新檔案事件]](#new-file-event)
* [新增資料夾事件](#new-folder-event)
* [[!UICONTROL 觀看檔案]](#watch-files)

#### [!UICONTROL 新檔案事件]

此即時觸發模組會在檔案上發生選取的動作時啟動案例。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>選取您要用來觀看外寄訊息的webhook，或新增webhook。 </p><p>若要新增webhook，請按一下<strong>[!UICONTROL 新增]</strong>，然後輸入webhook的名稱和連線、您要觀看的檔案以及要觀看的觸發程式。</p> <p> 如需有關將您的[!UICONTROL Box]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">連線到服務 — 基本指示</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 新增資料夾事件

此即時觸發模組會在選取動作發生在資料夾中時啟動案例。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>選取您要用來觀看外寄訊息的webhook，或新增webhook。 </p><p>若要新增webhook，請按一下<strong>[!UICONTROL 新增]</strong>，然後輸入webhook的名稱和連線、您要監視的資料夾以及要監視的觸發器。</p> <p> 如需有關將您的[!UICONTROL Box]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">連線到服務 — 基本指示</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看檔案]

此觸發模組會在新增新檔案或更新正在觀看的資料夾中的現有檔案時啟動案例。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  <tr> 
   <td role="rowheader">在資料夾中監視</td> 
   <td> <p>選取要監視的資料夾。 一個案例可以觀看單一資料夾。</p> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">觀看</td> 
   <td> <p>選取您要觀看的檔案型別。</p> 
    <ul> 
     <li> <p><strong>僅新檔案</strong> </p> <p>在新增檔案時，此案例就會開始。</p> </li> 
     <li> <p><strong>新檔案與所有變更</strong> </p> <p>新增檔案、修改檔案內容或檔案屬性（例如其名稱）時，就會開始此案例。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>已下載檔案的最大數量</p> </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大檔案數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

<!--* [[!UICONTROL Delete a file]](#delete-a-file)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Update a file]](#update-a-file)
* [[!UICONTROL Upload] a file](#upload-a-file)-->
* [建立資料夾](#create-a-folder)
* [取得資料夾](#get-a-folder)
* [取得資料夾中繼資料](#get-folder-metadata)
* [進行API呼叫](#make-an-api-call)
* [更新資料夾中繼資料](#update-folder-metadata)

<!--#### [!UICONTROL Delete a file] 

This action module deletes a file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to delete.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

This action module downloads a file.

You specify the ID of the file.

>[!NOTE]
>
>This module is useful for providing files to subsequent modules.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to retrieve.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a file] 

This action module updates a file.

You specify the ID of the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL File ID]</td> 
   <td>Enter or map the unique ID of the file that you want the module to update.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file] 

This action module uploads a file.

You specify the file. You can also provide a new filename for the file.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your [!DNL Box] account to Workfront Fusion, see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to Adobe Workfront Fusion - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td> <p>Select the folder where you want to upload the file.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>Select a source file from a previous module, or map the source file's name and data.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>If this module is not successful, consider the following:
>
>* The size of the file might exceed the maximum file size limit for your [!DNL Box] plan, or you may have used all of your [!DNL Box] account's storage quota. To get more storage space, delete existing files from [!DNL Box] or upgrade your [!DNL Box] account.
>* [!DNL Box] does not upload more than one files with the same name to a single folder. If the destination folder contains a file with the same name as the file being uploaded, the scenario run terminates with an error. To avoid this, rename the file. If you want to update the file, use the **[!UICONTROL Update a file]** module.-->

#### 建立資料夾

此動作模組會在指定的父資料夾內建立新的空白資料夾。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 名稱]</td> 
   <td> <p>輸入或對應新資料夾的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 父資料夾]</td> 
   <td> <p>選取您要建立新資料夾的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾上傳電子郵件存取權]</td> 
   <td> <p>設定此引數後，使用者可以用電子郵件將檔案傳送到已為此資料夾自動建立的電子郵件地址。 共同作業人員選項只允許共同作業人員使用註冊的電子郵件。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Synchronization State]</td> 
   <td> <p>指定資料夾是否應該同步至使用者的裝置。 Box Sync （已停用）會使用此功能，Box Drive則不會使用此功能。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得資料夾

此動作模組會擷取資料夾的詳細資料，包括資料夾中的前100個專案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾]</td> 
   <td> <p>選取您要擷取其詳細資料的資料夾。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得資料夾中繼資料

此動作模組會依資料夾ID擷取資料夾中繼資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 範圍]</td> 
   <td> <p>選取您要用於此中繼資料擷取的範圍。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾]</td> 
   <td> <p>選取您要擷取中繼資料的資料夾。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 進行API呼叫

此動作模組會對Box API進行自訂呼叫。



<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Bynder]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-bynder-to-workfront-fusion" class="MCXref xref">將[!DNL Bynder]連線到Workfront Fusion </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>輸入相對於<code>https://api.box.com</code>的路徑。 <p>範例： <code>/2.0/users/me</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
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

#### 更新資料夾中繼資料

此動作模組會建立或更新資料夾的中繼資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 範圍]</td> 
   <td> <p>選取您要用於此中繼資料更新的範圍。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾]</td> 
   <td> <p>選取您要更新中繼資料的資料夾。</p> </td> 
  </tr> 
 </tbody> 
</table>


### 搜尋

#### 搜尋內容

此搜尋模組會搜尋可供使用者或整個企業使用的專案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td> <p>輸入或對應要搜尋的字串。 此查詢會比對專案名稱、說明、檔案的文字內容以及不同專案型別的各種其他欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 範圍]</td> 
   <td> <p>選取您是要搜尋與使用者相關聯的內容（該使用者的認證用於此模組中所使用的連線），還是要搜尋與整個企業相關聯的內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 型別]</td> 
   <td> <p>選取您要搜尋的檔案、資料夾或網頁連結。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 排序]</td> 
   <td> <p>選取您要依關聯性或修改日期排序。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 垃圾桶內容]</td> 
   <td> <p>選取您要搜尋已清除的內容或尚未清除的內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 父資料夾ID]</td> 
   <td> <p>若要在特定資料夾中搜尋，針對您要搜尋的每個資料夾，按一下[新增專案] <b> </b>並輸入資料夾的識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 建立自]</td> 
   <td> <p>若要搜尋在特定日期範圍內建立的資產，請輸入範圍中最早的日期。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 建立至]</td> 
   <td> <p>若要搜尋在特定日期範圍內建立的資產，請在範圍中輸入最新日期。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 更新自]</td> 
   <td> <p>若要搜尋在特定日期範圍內更新的資產，請輸入範圍中最早的日期。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 已更新至]</td> 
   <td> <p>若要搜尋在特定日期範圍內更新的資產，請在範圍中輸入最新日期。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td> <p>針對您要在模組回應中傳回的每個屬性，按一下<b>新增專案</b>並輸入欄位。</p><p>這可用來要求一般不會以標準回應傳回的欄位。 請注意，指定此引數會造成回應中不會傳回任何標準欄位，除非明確指定。 </p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 副檔名]</td> 
   <td> <p>若要將搜尋限制在特定副檔名，請輸入以逗號分隔的副檔名清單。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小自]</td> 
   <td> <p>若要搜尋特定大小範圍內的資產，請輸入該範圍的小端（以位元組為單位）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小至]</td> 
   <td> <p>若要搜尋特定大小範圍內的資產，請輸入範圍的大結尾（位元組）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 擁有者使用者ID]</td> 
   <td> <p>若要搜尋特定使用者擁有的資產，請輸入擁有者ID的逗號分隔清單。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個執行週期中傳回的最大結果數量。</p> </td> 
  </tr> 
 </tbody> 
</table>



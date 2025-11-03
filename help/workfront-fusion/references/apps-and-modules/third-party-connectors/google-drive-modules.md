---
title: Google磁碟機模組
description: ' [!DNL Adobe Workfront Fusion Google Drive] 模組可讓您監視、搜尋、建立、更新、刪除及管理 [!DNL Google Drive]中的檔案、資料夾或共用磁碟機。'
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 788f4e1b-d774-45ad-a8be-b16922c1d5dc
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2102'
ht-degree: 0%

---

# [!DNL Google Drive]模組

Adobe Workfront Fusion [!DNL Google Drive]模組可讓您監視、搜尋、建立、更新、刪除及管理[!DNL Google Drive]中的檔案、資料夾或共用磁碟機。

在Adobe Workfront Fusion案例中，您可以將[!DNL Google Drive]帳戶連線至多個協力廠商應用程式和服務。

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

## Google Drive API資訊

Google磁碟機聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://www.googleapis.com/drive/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v4.1.22</td> 
  </tr>
 </tbody> 
 </table>



## 正在將[!DNL Google Drive]連線到Workfront Fusion

如果您使用[!DNL @gmail.com]或[!DNL @googlemail.com]使用者，您必須在[!DNL Google Cloud Platform]上建立OAuth使用者端以取得您的[!UICONTROL 使用者端識別碼]和[!UICONTROL 使用者端密碼]。

如需如何建立OAuth使用者端（以及取得[!UICONTROL 使用者端識別碼]和[!UICONTROL 使用者端密碼]）的逐步指示，請參閱[使用自訂OAuth使用者端將Adobe Workfront Fusion連線至 [!DNL Google Services] &#x200B;](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)。

如需有關將您的[!DNL Google Drive]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) — 基本指示

## [!DNL Google Drive]模組及其欄位

當您設定[!DNL Google Drive]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Drive]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)



* [觸發程序](#triggers)
* [動作](#actions)

### 觸發程序

* [[!UICONTROL 觀看所有檔案]](#watch-all-files)
* [[!UICONTROL 觀看註解]](#watch-comments)
* [[!UICONTROL 監視資料夾中的檔案]](#watch-files-in-folder)
* [[!UICONTROL 觀看共用檔案]](#watch-shared-files)

#### [!UICONTROL 觀看所有檔案]

新增或修改您[!DNL Google Drive]中的檔案時，此觸發模組會啟動情境。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 要觀看的檔案]</td> 
   <td> <p>選取您要觀看的檔案型別。</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL 將[!DNL Google Documents]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Documents]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Spreadsheets]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Spreadsheets]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Slides]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Slides]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Drawings]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Drawings]轉換成的檔案格式。</td>
  </tr>  
  <tr> 
   <td>[!UICONTROL 手錶]</td> 
   <td>選取您要監視新檔案與所有變更，還是隻監視新檔案。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 下載檔案數上限]</td> 
   <td>設定Workfront Fusion在一個週期內下載的結果數量上限（每個案例執行的重複次數）。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看註解]

在選取的檔案上新增或修改註解時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案]</td> 
   <td>選取您要觀看註解的檔案。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 手錶]</td> 
   <td>選取您是要監視所有變更，還是隻監視新註解</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 傳回評論的最大數量]</td> 
   <td>設定Workfront Fusion在一個週期內傳回的最大評論數量（每個案例執行的重複數量）。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 監視資料夾中的檔案]

在指定的資料夾中新增或修改檔案時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr>
    <td>[!UICONTROL 選取要監看的資料夾]</td>
    <td >選取您要在磁碟機上觀看檔案的資料夾。</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL 要觀看的檔案]</td>
   <td> <p>選取您要觀看的檔案型別。</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL 將[!DNL Google Documents]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Documents]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Spreadsheets]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Spreadsheets]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Slides]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Slides]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Drawings]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Drawings]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 手錶]</td>
    <td>選取您要監視新檔案與所有變更，還是隻監視新檔案。</td>
  </tr> 
  <tr> 
    <td>[!UICONTROL 下載檔案數上限]</td>
    <td>設定Workfront Fusion在一個週期內下載的結果數量上限（每個案例執行的重複次數）。</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看共用檔案]

在您共用新檔案或更新現有共用檔案時觸發。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 選取要監看的資料夾]</td> 
   <td>選取您想要監看檔案的共用資料夾。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 要觀看的檔案]</td> 
   <td> <p>選取您要觀看的檔案型別。</p> 
    <ul> 
     <li>[!UICONTROL All]</li> 
     <li>[!DNL Google Documents]</li> 
     <li>[!DNL Google Spreadsheets]</li> 
     <li>[!DNL Google Slides]</li> 
     <li>[!DNL Google Drawings]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
    <td >[!UICONTROL 將[!DNL Google Documents]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Documents]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Spreadsheets]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Spreadsheets]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Slides]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Slides]轉換成的檔案格式。</td>
  </tr> 
  <tr>
    <td>[!UICONTROL 將[!DNL Google Drawings]個檔案轉換為格式]</td>
    <td>選取您要將[!DNL Google Drawings]轉換成的檔案格式。</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL 手錶]</td> 
   <td>選取您要監視新檔案與所有變更，還是隻監視新檔案。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 下載檔案數上限]</td> 
   <td>設定Workfront Fusion在一個週期內下載的結果數量上限（每個案例執行的重複次數）。</td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 複製檔案]](#copy-a-file)
* [[!UICONTROL 建立fFolder]](#create-a-folder)
* [[!UICONTROL 刪除檔案]](#delete-a-file)
* [[!UICONTROL 取得檔案]](#get-a-file)
* [[!UICONTROL 取得共用連結]](#get-a-share-link)
* [[!UICONTROL 將檔案移至垃圾桶]](#move-a-filefolder-to-trash)
* [[!UICONTROL 搜尋檔案/資料夾]](#search-for-filesfolders)
* [[!UICONTROL 更新檔案]](#update-a-file)
* [[!UICONTROL 上傳檔案]](#upload-a-file)

#### [!UICONTROL 複製檔案]

此動作模組會將檔案複製到新位置。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 目的地]</td> 
   <td> <p>選取您要複製檔案的目的地。</p> 
    <ul> 
     <li>[!UICONTROL 我的磁碟機]</li> 
     <li>[!UICONTROL 與我共用]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 目標資料夾]</td> 
   <td>選取包含要複製之檔案的資料夾。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td>對應您要複製的檔案ID。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 副本的名稱]</td> 
   <td>輸入新檔案的標題。 如果您不想變更原始檔案名稱，請將此欄位保留空白。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立資料夾]

此動作模組會在指定位置建立資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 目的地]</td> 
   <td> <p>選取您要建立資料夾的目的地。</p> 
    <ul> 
     <li>[!UICONTROL 我的磁碟機]</li> 
     <li>[!UICONTROL 與我共用]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 新資料夾位置]</td> 
   <td>導覽至您要建立新資料夾的位置。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 新資料夾的名稱]</td> 
   <td>輸入您正在建立的資料夾名稱。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 共用資料夾]</td> 
   <td>如果您想要與任何具有[!UICONTROL 共用]連結的人共用資料夾，請選取此選項。 否則，共用連結僅供擁有者使用。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除檔案]

此動作模組會永久刪除檔案或資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td>對應您要刪除的檔案ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得檔案]

此動作模組會擷取具有指定ID的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Documents]個檔案轉換為格式]</td> 
   <td>選取您要將[!DNL Google Documents]轉換成的檔案格式。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Spreadsheets]個檔案轉換為格式]</td> 
   <td>選取您要將[!DNL Google Spreadsheets]轉換成的檔案格式。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Slides]個檔案轉換為格式]</td> 
   <td>選取您要將[!DNL Google Slides]轉換成的檔案格式。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 將[!DNL Google Drawings]個檔案轉換為格式]</td> 
   <td>選取您要將[!DNL Google Drawings]轉換成的檔案格式。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td>對應您要擷取的檔案ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得共用連結]

此動作模組會擷取Google Drive中檔案的共用連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td>對應您要取得共用連結的檔案ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 將檔案移至垃圾桶]

此動作模組會將檔案或資料夾移至垃圾桶。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td>對應您要移至垃圾桶的檔案ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋檔案/資料夾]

此搜尋模組會根據搜尋條件搜尋檔案或資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 目的地]</td> 
   <td> <p>選取您要搜尋的目的地磁碟機。</p> 
    <ul> 
     <li>[!UICONTROL 我的磁碟機]</li> 
     <li>[!UICONTROL 與我共用]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 列出資料夾]</td> 
   <td>瀏覽至您要搜尋檔案或資料夾的資料夾。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Retrieve]</td> 
   <td> <p> 選取您要搜尋檔案、資料夾或兩者。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL 搜尋]</p> </td> 
   <td> <p>選取您要執行的搜尋型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 在檔案/資料夾名稱內搜尋]</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL 查詢]</strong> </p> <p>輸入要搜尋的部分檔案名稱或完整檔案名稱（包括尾碼）。</p> </li> 
       <li> <p><strong>[!UICONTROL 搜尋選項]</strong> </p> <p>選取您要搜尋完全相同的字詞，或是要搜尋包含搜尋字詞的名稱。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Fulltext]搜尋</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL 查詢]</strong> </p> <p>在[!DNL Google Drive]中輸入您要搜尋的任何搜尋字詞。</p> </li> 
      </ul> </li> 
     <li> <p><strong>輸入自訂搜尋查詢</strong> </p> 
      <ul> 
       <li> <p><strong>[!UICONTROL 查詢]</strong> </p> <p>輸入自訂搜尋查詢。 如需更多詳細資料，請參閱本文的[!UICONTROL 搜尋檔案]一節。</p> </li> 
       <li> <p><strong>將上面選取的資料夾新增到查詢</strong> </p> <p>搜尋父項集合中的資料夾。 這會尋找直接位於上方所選資料夾中的所有檔案和資料夾。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 傳回結果的最大數目]</td> 
   <td>設定Workfront Fusion在一個執行週期中傳回的檔案或資料夾數量上限。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 即使模組未傳回任何結果，仍繼續執行路由]</td> 
   <td>啟用此選項可確保在模組未傳回任何結果時不會停止此案例。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新檔案]

此動作模組會更新檔案的中繼資料或內容。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 目的地]</td> 
   <td> <p>選取包含您要更新檔案的目的地。</p> 
    <ul> 
     <li>[!UICONTROL 我的磁碟機]</li> 
     <li>[!UICONTROL 與我共用]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 移至資料夾]</td> 
   <td>如果要將檔案移動到特定資料夾，請選取要將檔案移動到其中的資料夾。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案ID]</td> 
   <td>對應您要更新的檔案ID。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 標題]</td> 
   <td>輸入更新檔案的標題。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 變更檔案內容]</td> 
   <td>選取是否要取代檔案的內容。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source檔案]</td> 
   <td>如果您要取代內容，請從先前的模組中選取來源檔案，或對映來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 轉換檔案]</td> 
   <td>啟用此選項以將檔案轉換為對應的Google檔案格式。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳檔案]

上傳檔案至您的[!DNL Google Drive]。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Drive]帳戶連線到Workfront Fusion的說明，請參閱<a href="#connecting-google-drive-to-workfront-fusion" class="MCXref xref">將[!DNL Google Drive]連線到[!UICONTROL Workfront Fusion]</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Destination]</td> 
   <td> <p>選取您要上傳檔案的目的地。</p> 
    <ul> 
     <li>[!DNL My Drive]</li> 
     <li>[!DNL Shared with Me]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 目標資料夾]</td> 
   <td>選取您要上傳檔案的資料夾。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source檔案]</td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 標題]</td> 
   <td>輸入新檔案的標題。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 轉換檔案]</td> 
   <td>啟用此選項可讓模組將檔案轉換為對應的[!DNL Google]格式。</td> 
  </tr> 
 </tbody> 
</table>

## 疑難排解

### 無法上傳或更新檔案

上傳或更新檔案失敗有幾個原因：

* 上傳的檔案太大，超過您的[!DNL Google Drive]計畫允許的最大檔案大小限制，或者您已超過[!DNL Google Drive]儲存空間限制。 您可以升級儲存空間方案，或從[!DNL Google Drive]服務中刪除現有檔案。
* 要上傳檔案到的所選資料夾已不存在。 在此情況下，案例會停止，您必須在模組中選取不同的目標資料夾。

<!-- Not present February 2025

## Search for files

In the module List files in a folder you can use your own query which consists of these parts:

* **[!UICONTROL Field]** - Attribute of the file that is being searched, for example, the attribute `name` of the file.

* **[!UICONTROL Operator]** - Test that is performed on the data to provide a match, for example, `contains`.

* **[!UICONTROL Value]** - The content of the attribute that is tested, for example, the name of the file `My cool document`.

Combine clauses with the conjunctions `and` or `or`, and negate the query with `not`.

* [Fields](#fields)
* [Value types](#value-types)
* [Operators](#operators)
* [Examples](#examples)

### Fields 

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Field </th> 
   <th>Value Type </th> 
   <th>Operators</th> 
   <th> <p> Description</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>[!UICONTROL title]</code></td> 
   <td>string</td> 
   <td><code>contains</code><sup>1</sup>, <code>=</code>, <code>!=</code></td> 
   <td> <p> Name of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL fullText]</code> </td> 
   <td>string </td> 
   <td><code>contains</code><sup>2, 3</sup> </td> 
   <td> <p> Full text of the file including name, description, content, and indexable text.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL mimeType]</code> </td> 
   <td> string</td> 
   <td><code>contains</code>, <code>=</code>, <code>!=</code></td> 
   <td> <p> MIME type of the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL modifiedDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code> &lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date of the last modification to the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL lastViewedByMeDate]</code> </td> 
   <td> date<sup>4</sup></td> 
   <td><code>&lt;=</code>, <code>&lt;</code>, <code>=</code>, <code>!=</code>, <code>></code>, <code>>=</code></td> 
   <td> <p> Date that the user last viewed a file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL trashed]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Whether the file is in the trash or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL starred]</code></td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p>Whether the file is starred or not.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL parents]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Whether the [!UICONTROL parents] collection contains the specified ID.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL owners]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who own the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL writers]</code></td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to modify the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL readers] </code> </td> 
   <td>collection </td> 
   <td><code>in </code> </td> 
   <td> <p>Users who have permission to read the file.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL sharedWithMe]</code> </td> 
   <td>boolean </td> 
   <td><code>=</code>, <code>!=</code></td> 
   <td> <p> Files that are in the user's "Shared with me" collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>[!UICONTROL properties] </code> </td> 
   <td>collection</td> 
   <td><code>has </code> </td> 
   <td> <p> Public custom file properties.</p> </td> 
  </tr> 
 </tbody> 
</table>

Consider the following about operators in these fields:

* The `contains` operator only performs prefix matching for a `title`.

   For example, the title "HelloWorld" matches for `title contains 'Hello'` but not for `title contains 'World'`.

* The `contains` operator only performs matching on entire string tokens for `fullText`.

   For example, if the full text of a doc contains the string "HelloWorld" only the query `fullText contains 'HelloWorld'` returns a result. Queries such as `fullText contains 'Hello'` would not return results in this scenario.

* The `contains` operator matches on an exact alphanumeric phrase if it is surrounded by double quotes.

   For example, if the `fullText` of a doc contains the string "Hello there world", then the query `fullText contains '"Hello there"'` returns a result, but the query `fullText contains '"Hello world"'` does not.

   Furthermore, because the search is alphanumeric, if the `fullText` of a doc contains the string "Hello_world", then the query `fullText contains '"Hello world"'` returns a result.

* Fields of `type` date are currently not comparable to each other, only to constant dates.

### Value types

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Value Type</th> 
   <th> <p> Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>String </td> 
   <td> <p>Surround with single quotes '. Escape single quotes in queries with <code>\'</code>, e.g.,<code> 'Valentine\'s Day'</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Boolean </td> 
   <td> <p><code>true </code>or <code>false</code>.</p> </td> 
  </tr> 
  <tr> 
   <td>Date </td> 
   <td> <p>RFC 3339 format, default timezone is UTC, e.g., <code>2012-06-04T12:00:00-08:00</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Operators

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>Operator </th> 
   <th> <p>Notes</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>contains</code></td> 
   <td> <p>The content of one string is present in the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>=</code> </td> 
   <td> <p> The content of a string or boolean is equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>!=</code> </td> 
   <td> <p> The content of a string or boolean is not equal to the other.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;</code> </td> 
   <td> <p> A date is earlier than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>&lt;=</code> </td> 
   <td> <p> A date is earlier than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>></code> </td> 
   <td> <p> A date is later than another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>>=</code> </td> 
   <td> <p> A date is later than or equal to another.</p> </td> 
  </tr> 
  <tr> 
   <td><code>in </code> </td> 
   <td> <p>An element is contained within a collection.</p> </td> 
  </tr> 
  <tr> 
   <td><code>and </code> </td> 
   <td> <p>Return files that match both clauses.</p> </td> 
  </tr> 
  <tr> 
   <td><code>or </code> </td> 
   <td> <p>Return files that match either clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>not </code> </td> 
   <td> <p>Negates a search clause.</p> </td> 
  </tr> 
  <tr> 
   <td><code>has </code> </td> 
   <td> <p>A collection contains an element matching the parameters.</p> </td> 
  </tr> 
 </tbody> 
</table>

For compound clauses, you can use parentheses to group clauses together. For example:
`modifiedDate > '2012-06-04T12:00:00' and (mimeType contains 'image/' or mimeType contains 'video/')` This search returns all files with an image or video MIME type that their last modification was after June 4, 2012. Because `and` and `or` operators are evaluated from left to right, without parentheses, the above example would return only images modified after June 4, 2012, but would return all videos, even those before June 4, 2012.

### Examples 

All examples on this page show the unencoded `<q>q</q>` parameter, where `title = 'hello'` is encoded as `title+%3d+%27hello%27`. Client libraries handle this encoding automatically.

* Search for files with the name "hello"
   <pre>title = 'hello'</pre>
* Search for folders using the folder-specific MIME type
   <pre>mimeType = 'application/vnd.google-apps.folder'</pre>
* Search for files that are not folders
   <pre>mimeType != 'application/vnd.google-apps.folder'</pre>
* Search for files with a name containing the words "hello" and "goodbye"
   <pre>title contains 'hello' and [!UICONTROL name] contains 'goodbye'</pre>
* Search for files with a name that does not contain the word "hello"
   <pre>not title contains 'hello'</pre>
* Search for files containing the word "hello" in the content
   <pre>fullText contains 'hello'</pre>
* Search for files not containing the word "hello" in the content
   <pre>not fullText contains 'hello'</pre>
* Search for files containing the exact phrase "hello world" in the content
   <pre>fullText contains '"hello world"'fullText contains '"hello_world"'</pre>
* Search for files with a query containing the "\" character (e.g., "\authors")
   <pre>fullText contains '\\authors'</pre>
* Search for files writeable by the user `test@example.org`
   <pre>'test@example.org' in [!DNL writers]</pre>
* Search for the ID `1234567` in the `parents` collection. This finds all files and folders located directly in the folder whose ID is `1234567`.
   <pre>'1234567' in [!UICONTROL parents]</pre>
* Search for the alias ID `appDataFolder` in the `parents` collection. This finds all files and folders located directly under the [Application Data folder](https://developers.google.com/drive/api/v2/appdata).
   <pre>'appDataFolder' in parents</pre>
* Search for files writeable by the users `test@example.org` and `test2@example.org`
   <pre>'test@example.org' in writers and 'test2@example.org' in writers</pre>
* Search for files containing the text "important" which are in the trash
   <pre>fullText contains 'important' and trashed = true</pre>
* Search for files modified after June 4th 2012
   <pre>modifiedDate > '2012-06-04T12:00:00' // default time zone is UTC</pre><pre>modifiedDate > '2012-06-04T12:00:00-08:00'</pre>
* Search for files shared with the authorized user with "hello" in the name
   <pre>sharedWithMe and title contains 'hello'</pre>
* Search for files with a [custom file property](https://developers.google.com/drive/api/v2/properties) named `additionalID` with the value `8e8aceg2af2ge72e78`.
   <pre>properties has { key='additionalID' and value='8e8aceg2af2ge72e78' and visibility='PRIVATE' }</pre>

Source of this guide is [[!DNL Google Drive] documentation](https://developers.google.com/drive/api/v2/search-shareddrives).

-->

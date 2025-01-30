---
title: Dropbox模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Dropbox的工作流程，以及將其連線至多個協力廠商應用程式和服務。這可讓您自動執行Dropbox中的監控、搜尋、擷取、列出、建立及編輯檔案與資料夾等活動。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 29ce5940-4d71-4719-ab5e-f03c44b28c8c
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '2876'
ht-degree: 0%

---

# [!DNL Dropbox]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!UICONTROL Dropbox]或[!DNL Dropbox Business]的工作流程，以及將其連線至多個協力廠商應用程式和服務。這可讓您自動化活動，例如監視、搜尋、擷取、列出、建立及編輯[!UICONTROL Dropbox]中的檔案和資料夾。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
  <td> <p>[!UICONTROL Pro] 或更高</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 先決條件

* 若要使用[!DNL Dropbox]模組，您必須有[!DNL Dropbox]帳戶。

>[!IMPORTANT]
>
>Dropbox必須核准使用者超過50人的應用程式。
>
>如需詳細資訊，請在Dropbox開發人員指南中搜尋「生產核准」。

## DropboxAPI資訊

Dropbox聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://api.dropboxapi.com/2    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> 2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td><ul><li><p>Dropbox</p><p>v5.3.9</p></li><li><p>Dropbox企業</p><p>v1.0.12</p></li></ul></td> 
  </tr>
 </tbody> 
 </table>


## 建立與[!DNL Dropbox]的連線

若要為您的[!DNL Dropbox]模組建立連線：

1. 按一下[連線]方塊旁的&#x200B;**[!UICONTROL Add]**。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL Connection name]</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
        <tr>
        <td role="rowheader">[!UICONTROL Environment]</td>
        <td>選取此連線是用於生產或非生產環境。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Type]</td>
        <td>選取您要連線到服務帳戶還是個人帳戶。</td>
        </tr>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client ID]</td>
        <td>輸入您的[!UICONTROL Dropbox] [!UICONTROL Client ID]。 </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Client Secret]</td>
        <td>輸入您的[!DNL Dropbox] [!UICONTROL Client Secret]。 </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL Account Type]</td>
        <td>選取您要連線至個人Dropbox帳戶或企業(Dropbox企業)帳戶。</td>
        </tr>
      </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以儲存連線並返回模組。## [!DNL Dropbox]模組及其欄位

## [!DNL Dropbox]模組及其欄位

當您設定[!DNL Dropbox]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Dropbox]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發模組](#trigger-modules)
* [取得 [!DNL Dropbox] 檔案與資料夾的模組](#modules-for-getting-dropbox-files-and-folders)
* [建立和編輯 [!DNL Dropbox] 檔案與資料夾的模組](#modules-for-creating-and-editing-dropbox-files-and-folders)
* [其他模組](#other-modules)

### 觸發模組

#### [!UICONTROL Watch Files]

修改指定資料夾中的檔案時，此觸發型別模組會傳回檔案詳細資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>選取您要監視變更的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Watch also subfolders]</td> 
   <td> <p> 啟用此選項也可監視所選資料夾中用於修改檔案的子資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 取得[!DNL Dropbox]檔案與資料夾的模組

* [[!UICONTROL Search Files/Folders]](#search-filesfolders)
* [[!UICONTROL Download a File]](#download-a-file)
* [[!UICONTROL Get a Folder Metadata]](#get-a-folder-metadata)
* [[!UICONTROL List All Files/Subfolders in a Folder]](#list-all-filessubfolders-in-a-folder)
* [[!UICONTROL List File Revisions]](#list-file-revisions)

#### [!UICONTROL Search Files/Folders]

此搜尋模組會在[!DNL Dropbox]中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境中的後續模組中對應此資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>輸入搜尋字詞。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>選取您要搜尋的資料夾。 如果您未選取資料夾，此模組會搜尋整個[!DNL Dropbox]。</p> </td> 
  </tr> 
  <tr> 
   <td>檔案狀態</td> 
   <td> <p> 選取檔案狀態，將搜尋限制在選取的檔案狀態。</p> </td> 
  </tr> 
  <tr> 
   <td>檔案類別</td> 
   <td> <p> 選取檔案類別，將搜尋限制在選取的類別。</p> </td> 
  </tr> 
  <tr> 
   <td>副檔名</td> 
   <td> <p> 選擇您要搜尋的副檔名。</p> </td> 
  </tr> 
  <tr> 
   <td>限制 </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a File]

此動作模組會從資料夾下載檔案。

您可以指定檔案及其位置。

模組會傳回檔案ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

>[!NOTE]
>
>此模組對於提供檔案給後續模組相當實用。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>選取檔案的方式</td> 
   <td> <p> 選取您要對應檔案路徑還是手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>檔案路徑/檔案</p> </td> 
   <td> <p style="font-weight: bold;">檔案路徑</p> <p>輸入或對應目標路徑至檔案。</p> <p style="font-weight: bold;">檔案</p> <p>從選單中選取檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Folder Metadata]

此動作模組會擷取共用資料夾詳細資料。

您可以指定資料夾的ID。

模組會傳回資料夾的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>共用資料夾識別碼</td> 
   <td> <p> 輸入或對應您要擷取其詳細資訊的資料夾ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List All Files/Subfolders in a Folder]

此動作模組會列出特定資料夾中的檔案或資料夾。

您可以指定資料夾的ID。

模組會傳回檔案或資料夾的ID及任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>清單 </td> 
   <td> <p>選取您要擷取檔案或資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>僅顯示可下載的檔案</td> 
   <td> <p> 啟用此選項以僅傳回可下載的檔案。 部分型別的檔案(例如Google Docs)無法下載。</p> </td> 
  </tr> 
  <tr> 
   <td>資料夾 </td> 
   <td> <p>輸入或對應您要從中擷取檔案或資料夾的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>限制 </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中列出的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List File Revisions]

此動作模組會擷取特定檔案的所有檔案修訂版本（版本記錄）。\
您指定檔案的ID。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>選取檔案的方式</td> 
   <td> <p> 選取您要對應檔案路徑還是手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>檔案路徑/檔案</p> </td> 
   <td> <p style="font-weight: bold;">檔案路徑</p> <p>輸入或對應目標路徑至檔案。</p> <p style="font-weight: bold;">檔案</p> <p>從選單中選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>限制</p> </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中列出的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 建立和編輯[!DNL Dropbox]檔案與資料夾的模組

* [[!UICONTROL Upload]檔案](#upload-a-file)
* [[!UICONTROL Create a Folder]](#create-a-folder)
* [[!UICONTROL Create/Overwrite a Text File]](#createoverwrite-a-text-file)
* [[!UICONTROL Create/Update a Share Link]](#createupdate-a-share-link)
* [[!UICONTROL Restore a File]](#restore-a-file)
* [[!UICONTROL Move a File/Folder]](#move-a-filefolder)
* [[!UICONTROL Rename a File/Folder]](#rename-a-filefolder)
* [[!UICONTROL Delete a File/Folder]](#delete-a-filefolder)

#### [!UICONTROL Upload a File]

此動作模組會將檔案上傳至資料夾。

您可以指定資訊，例如檔案的位置、要上傳的檔案，以及檔案的可選新名稱。

模組會傳回檔案ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder]</td> 
   <td> <p> 選取您要上傳檔案的[!DNL Dropbox]資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>輸入或對應您要新增至上方所選[!DNL Dropbox]資料夾的檔案。</p> <p style="font-weight: bold;">[!UICONTROL File name]</p> <p>輸入或對應檔案名稱，包括副檔名。</p> <p style="font-weight: bold;">[!UICONTROL File data]</p> <p>輸入或對應檔案資料（來自先前模組，例如[!UICONTROL Google Drive] &gt;[!UICONTROL Get a File)]）。</p> <p>注意：上傳檔案的大小上限為150 MB。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Overwrite an existing file]</td> 
   <td> <p> 啟用此選項以新檔案取代現有檔案。 如果此選項保持停用，則會重新命名上傳的檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Folder]

此動作模組會建立新資料夾。

您可以指定資料夾的路徑和名稱。

模組會傳回資料夾的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name] </td> 
   <td> <p>輸入新資料夾的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>輸入或對應您要建立新資料夾的路徑。</p> <p>注意：   <p>如果您使用[!DNL Dropbox Business]帳戶（含團隊空間），您必須移除斜線<code>/</code>，或不要按一下<strong>[!UICONTROL Click here]選擇資料夾</strong>以在根目錄中建立團隊資料夾。</p> <p>如果未移除斜線，則會傳回錯誤<code>[409] path/malformed_path/..</code>。</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Auto rename]</td> 
   <td> <p> 啟用此選項可重新命名新資料夾（如果目標位置中已存在相同名稱的資料夾）。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Overwrite a Text File]

此動作模組會建立DOC檔案或覆寫現有檔案的內容。

您可以指定來源檔案和資料夾。

模組會傳回資料夾的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Select to]</td> 
   <td> <p> 選取您要建立或覆寫DOC檔案。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>選取您要建立檔案的目標位置。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Source File]</p> </td> 
   <td> <p>輸入或對應您要新增至[!DNL Dropbox]資料夾的檔案。</p> <p style="font-weight: bold;">檔案名稱</p> <p>輸入新DOC檔案的檔案名稱（沒有副檔名）。</p> <p style="font-weight: bold;">檔案內容</p> <p>輸入DOC檔案的文字內容。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create/Update a Share Link]

此動作模組會建立檔案的公開連結。

您可以指定檔案和連結的相關資訊。

模組會傳回連結的ID及任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> 選取您要對映或輸入檔案路徑，或手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path / File]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File Path]</p> <p>輸入或對應目標路徑至檔案。</p> <p style="font-weight: bold;">[!UICONTROL File]</p> <p>從選單中選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Requested Visibility]</p> </td> 
   <td> <p>選取連結是公用連結、專案團隊連結或密碼限制連結。</p> <p>注意： [!UICONTROL Team only]和[!UICONTROL Access with password]選項僅適用於具有[!DNL Dropbox Pro]或更新版本的使用者。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Link's Expiration Date]</td> 
   <td> <p> 輸入連結到期且無法再存取的日期和時間。 如果此欄位留空，連結將不會過期。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</p> <p>注意： [!UICONTROL Team only]和[!UICONTROL Access with password]選項僅供具有[!UICONTROL Dropbox Pro]或更新版本的使用者使用。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Link's Access Level]</p> </td> 
   <td> <p>設定連結收件者的許可權。</p> <p><strong>[!UICONTROL Viewer]</strong> 使用連結的使用者可以檢視內容並加上註解。</p> <p><strong>[!UICONTROL Editor]</strong> 使用連結的使用者可以編輯、檢視和評論內容。</p> <p><strong>[!UICONTROL Max]</strong> 使用連結的使用者會收到您可以為其設定連結的最大存取層級。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Restore a File]

此動作模組會還原檔案的先前版本。

您可以指定檔案和您想要的修訂版本編號。

模組會傳回版本ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> 選取您要對映或輸入檔案路徑，或手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path] / [!UICONTROL File]</p> </td> 
   <td> <p><strong>[!UICONTROL File Path]</strong> </p> <p>輸入或對應目標路徑至檔案。</p> <p><strong>[!UICONTROL File]</strong> </p> <p>從選單中選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Revision]</p> </td> 
   <td> <p>輸入或對應您要還原之修訂版本的修訂版本編號。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File/Folder]

此動作模組會將檔案或資料夾移至其他位置。

您可以指定檔案或資料夾，以及移動的方式和位置。

模組會傳回檔案或資料夾的ID以及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files] </td> 
   <td> <p>選取您要對映或輸入檔案路徑，或手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File/Folder Path] / [!UICONTROL File/Folder]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File/Folder Path]</p> <p>輸入或對應目標路徑至檔案或資料夾。</p> <p style="font-weight: bold;">[!UICONTROL File/Folder]</p> <p>從選單中選取檔案或資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL To Folder]</p> </td> 
   <td> <p>輸入或對應檔案或資料夾的目標位置。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL New Name]</p> </td> 
   <td> <p>在新位置輸入檔案或資料夾的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Auto Rename]</p> </td> 
   <td> <p>啟用此選項以確保如果存在相同名稱的檔案或資料夾，模組會重新命名新檔案或資料夾，方法是在檔案或資料夾名稱后面新增([!UICONTROL NUMBER])。 否則，會覆寫目標位置中的檔案或資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Allow ownership transfer]</p> </td> 
   <td> <p>啟用此選項可允許所有者移動，即使這將導致所移動內容的所有權轉移。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Rename a File/Folder]

此動作模組會重新命名檔案或資料夾。

您可以指定檔案或資料夾以及新名稱。

模組會傳回檔案或資料夾的ID以及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>選取檔案的方式</td> 
   <td> <p> 選取您要對映或輸入檔案路徑，或手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>檔案/資料夾路徑/檔案/資料夾</p> </td> 
   <td> <p style="font-weight: bold;">檔案/資料夾路徑</p> <p>輸入或對應目標路徑至檔案或資料夾。</p> <p style="font-weight: bold;">檔案/資料夾</p> <p>從選單中選取檔案或資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>重新命名 </td> 
   <td> <p>輸入檔案的[!UICONTROL target name]，包括副檔名。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File/Folder]

此動作模組會刪除檔案或資料夾。

您指定檔案或資料夾。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Way of selecting files]</td> 
   <td> <p> 選取您要對映或輸入檔案路徑，或手動選取檔案。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL File Path] / [!UICONTROL File]</p> </td> 
   <td> <p style="font-weight: bold;">[!UICONTROL File Path]</p> <p>輸入或對應目標路徑至檔案。</p> <p style="font-weight: bold;">[!UICONTROL File]</p> <p>從選單中選取檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他模組

#### [!UICONTROL Make an API Call]

此動作模組可讓您對[!DNL Dropbox] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Dropbox]模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Dropbox]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-dropbox" class="MCXref xref">建立與[!DNL Dropbox]</a>的連線。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對路徑。輸入相對於<code>https://api.dropboxapi.com</code>的路徑。 例如， <code>/2/files/list_folder</code></p> <p>注意：如需可用端點的清單，請參閱<a href="https://www.dropbox.com/developers/documentation/http/documentation">DropboxAPI v2檔案</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Headers] </td> 
   <td> <p>輸入所需的請求標頭。 [!DNL Workfront Fusion]會自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query String]</td> 
   <td> <p> 輸入請求查詢字串。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Body] </td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：   <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**範例：**&#x200B;下列API呼叫傳回您[!DNL Dropbox]帳戶中[!DNL /Text files]資料夾的前10個檔案：
>
>URL： `/2/files/list_folder`
>
>內文：
> 
>`{`
>
>`"path": "/Text files",`
>
>`"limit": 10,`
>
>`"recursive": false,`
>
>`"include_deleted": false`
>
>`}`
>
>在[!UICONTROL Bundle] > [!UICONTROL Body] >專案下的模組輸出中可找到搜尋的相符專案。
>
>在我們的範例中，傳回10張票證：

## 常見問題

* [無法上傳或更新檔案](#unable-to-upload-or-update-a-file)
* [透過共用連結參照的影像無法呈現](#image-referenced-via-a-shared-link-does-not-render)

### 無法上傳或更新檔案

上傳或更新檔案失敗時有幾種情況：

* 上傳的檔案太大，超過您的[!DNL Dropbox]計畫允許的最大檔案大小，或者您已使用所有[!DNL Dropbox]帳戶的儲存配額。 您必須從您的[!DNL Dropbox]帳戶刪除現有檔案，或升級您的計畫。
* 先前選取的資料夾（檔案將上傳至該資料夾）已不存在。 此情境將停止，您必須再次選取目標資料夾。

### 透過共用連結參照的影像無法呈現

[!UICONTROL Dropbox] >[!UICONTROL Create a shared link]傳回的URL未直接連結至影像，而是連結至[!DNL Dropbox]頁面。 若要強制下載影像，請將結尾的`?dl=0`取代為`?dl=1`。 若要強制轉譯影像(例如在網頁瀏覽器或Facebook Messenger中)，請將`&raw=1`附加至URL。

如果您需要取得您網站或其他[!DNL Workfront Fusion]模組的直接或原始影像連結，您必須以下列方式修改初始的共用URL：

原始URL：

`https://www.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png?dl=0`

1. 以`dl`取代`www`。
1. 移除`?dl=0`。

最終URL：

`https://dl.dropbox.com/s/ia8qtvs20f3a5ux/Screen%20Shot%202018-10-15%20at%204.21.11%20PM.png`

若要自動修改URL，您可以使用`replace()`函式兩次：

* 以dl取代www

  ![以dl](/help/workfront-fusion/references/apps-and-modules/assets/www-to-dl-350x32.png)取代www

* 若要移除？dl=0

  ![移除DL](/help/workfront-fusion/references/apps-and-modules/assets/remove-dl0-350x33.png)

若要在一個步驟中執行操作，請組合下列函式：

![取代兩者](/help/workfront-fusion/references/apps-and-modules/assets/replace-both-350x47.png)

您也可以複製並貼到欄位中。 以URL取代`1.url`。

```
{{replace(replace(1.url; "?dl=0"; ""); "www"; "dl")}}
```

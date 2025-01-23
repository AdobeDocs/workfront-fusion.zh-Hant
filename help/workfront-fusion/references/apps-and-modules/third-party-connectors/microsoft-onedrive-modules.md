---
title: Microsoft Onedrive模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用OneDrive的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: d21eafad-9c67-4f42-b718-0aa4223846e6
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '3285'
ht-degree: 0%

---

# [!DNL Microsoft OneDrive]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL OneDrive]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!DNL OneDrive]模組，您必須有[!DNL Microsoft OneDrive]帳戶。



## OneDrive API資訊

OneDrive聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://graph.microsoft.com/v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v2.0.10</td> 
  </tr>
 </tbody> 
 </table>


## 正在將[!DNL OneDrive]服務連線到[!DNL Workfront Fusion]

如需有關將您的[!DNL OneDrive]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線 — 基本指示](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## [!DNL Microsoft OneDrive]模組及其欄位

當您設定[!DNL OneDrive]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL OneDrive]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [檔案/資料夾](#filefolder)
* [其他](#other)

### 檔案/資料夾

* [[!UICONTROL Watch Files/Folders]](#watch-filesfolders)
* [[!UICONTROL Search Files/Folders]](#search-filesfolders)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL Download a file]](#download-a-file)
* [[!UICONTROL Upload a file]](#upload-a-file)
* [[!UICONTROL Create a Folder]](#create-a-folder)
* [[!UICONTROL Get a Share Link]](#get-a-share-link)
* [[!UICONTROL Move a File/Folder]](#move-a-filefolder)
* [[!UICONTROL Copy a File]](#copy-a-file)
* [[!UICONTROL Delete a File/Folder]](#delete-a-filefolder)

#### [!UICONTROL Watch Files/Folders]

此觸發模組會在檔案或資料夾建立或更新時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch Files/Folders]</td> 
   <td> <p>選取您要如何監視檔案或資料夾：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL By Created Time]</b> </p> <p>留意新檔案或資料夾。</p> </li> 
     <li> <p><b>[!UICONTROL By Updated Time]</b> </p> <p>留意已更新的現有檔案或資料夾。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要觀看的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入您要模組觀看的磁碟機ID。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> <p>導覽至您要模組觀看的資料夾。 您也可以輸入查詢來篩選傳回的結果。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Shared With Me]</b> </p> <p>模組會監視已和磁碟機擁有者共用的檔案。</p> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取您要模組觀看的SharePoint網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取您要模組監視其磁碟機的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose an Item Type]</td> 
   <td> <p>選取您要監視檔案、資料夾或兩者。</p> <p>注意：您無法監視[!UICONTROL Shared With Me]磁碟機中的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>



#### [!UICONTROL Search Files/Folders]

此搜尋模組會根據您設定的條件傳回檔案和資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要搜尋的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入您希望模組搜尋的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> <p>導覽至您要模組搜尋的資料夾。 您也可以輸入查詢來篩選傳回的結果。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Shared With Me]</b> </p> <p>模組會搜尋與磁碟機擁有者共用的檔案。</p> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取您要模組搜尋的[!DNL SharePoint]網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取您要模組搜尋其磁碟機的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose an Item Type]</td> 
   <td> <p>選取您要搜尋檔案、資料夾或兩者。</p> <p>注意：您無法搜尋[!UICONTROL Shared With Me]磁碟機中的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a file]

此動作模組取得指定檔案的中繼資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>選取您要依「檔案ID」或「檔案路徑」來識別檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>選取您要如何輸入「檔案ID」或「檔案路徑」：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您要從可用檔案或路徑清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要搜尋的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入包含您要取得之檔案的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取包含您要取得之檔案的SharePoint網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取其磁碟機包含您要取得之檔案的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要取得之檔案的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td> 
   <td> <p>如果您已選取[!UICONTROL Enter Manually]，請輸入或對應您要取得之檔案的檔案ID或路徑。</p> <p>如果您已選取[!UICONTROL Select from the list]，請選取您要取得的檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a file]

此動作模組會下載指定的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>選取您要依「檔案ID」或「檔案路徑」來識別檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸入檔案ID /檔案路徑</td> 
   <td> <p>選取您要如何輸入「檔案ID」或「檔案路徑」：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您要從可用檔案或路徑清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要包含要下載之檔案的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入包含您要下載之檔案的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取包含您要下載之檔案的SharePoint網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取磁碟機包含要下載之檔案的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要下載之檔案的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td>
   <td> <p>如果您已選取[!UICONTROL Enter Manually]，請輸入或對應您要下載的檔案識別碼或路徑。</p> <p>如果您已選取[!UICONTROL Select from the list]，請選取您要下載的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Convert to PDF]</td> 
   <td> <p>啟用此選項可將檔案轉換成PDF檔案。 您可以從下列檔案型別轉換：</p> 
    <table style="table-layout:auto"> 
     <col> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td> 
        <ul> 
         <li> <p> <p>CSV</p> </p> </li> 
         <li> <p> <p>DOC</p> </p> </li> 
         <li> <p> <p>DOCX</p> </p> </li> 
         <li> <p> <p>ODP</p> </p> </li> 
         <li> <p> <p>ODS</p> </p> </li> 
         <li> <p> <p>ODT</p> </p> </li> 
        </ul> </td> 
       <td> 
        <ul> 
         <li> <p> <p>POT</p> </p> </li> 
         <li> <p> <p>POTM</p> </p> </li> 
         <li> <p> <p>POTX</p> </p> </li> 
         <li> <p> <p>PPS</p> </p> </li> 
         <li> <p> <p>PPSX</p> </p> </li> 
         <li> <p> <p>PPSXM</p> </p> </li> 
        </ul> </td> 
       <td> 
        <ul> 
         <li> <p>PPT</p> </li> 
         <li> <p>PPTM</p> </li> 
         <li> <p>PPTX</p> </li> 
         <li> <p>RTF</p> </li> 
         <li> <p>XLS</p> </li> 
         <li> <p>XLSX</p> </li> 
        </ul> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

此動作模組會將檔案上傳至指定的資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸入（資料夾位置ID與路徑）</td> 
   <td>選取您要依ID或路徑識別目標資料夾。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要上傳檔案的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>選取包含您要取得之檔案的磁碟機。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取包含您要上傳檔案之資料夾的[!DNL SharePoint]網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取其磁碟機包含要上傳檔案之資料夾的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取包含您要上傳檔案之資料夾的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL If the File with the Same Name Exists]</td> 
   <td>選取當同名檔案已存在時如何繼續。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td>新增說明至上傳的檔案。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Folder]

這個動作模組會在指定的磁碟機中建立新資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要建立資料夾的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>選取您要建立資料夾的磁碟機。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取您要建立資料夾的[!DNL SharePoint]網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取擁有您要建立資料夾之驅動程式的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取您要建立資料夾的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>如果您希望新資料夾是子資料夾，請瀏覽至您希望它成為子資料夾的資料夾。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Folder Name]</td> 
   <td> <p>輸入或對應新資料夾的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL If the Folder with the Same Name Exists]</td> 
   <td>選取當同名檔案已存在時如何繼續。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Share Link]

此動作模組會傳回指定檔案的共用連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>選取您要依「檔案ID」或「檔案路徑」來識別檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>選取您要如何輸入「檔案ID」或「檔案路徑」：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您要從可用檔案或路徑清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要擷取共用連結的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入包含您要擷取共用連結之檔案的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取包含您要擷取共用連結之檔案的SharePoint網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取其磁碟機包含您要擷取共用連結之檔案的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要擷取共用連結之檔案的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td> 
   <td> <p>如果您選取[!UICONTROL Enter Manually]，請輸入或對應您要擷取共用連結之檔案的檔案ID或路徑。</p> <p>如果您從清單中選取[!UICONTROL Select]，請選取您要擷取共用連結的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Permission Type]</td> 
   <td> <p>選取您希望擁有連結的人員能夠讀取和寫入檔案，還是唯讀。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td>選取您希望檔案可供擁有該連結的任何人使用，還是僅供擁有該連結的組織成員使用。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File/Folder]

此動作模組會將檔案或資料夾移至新的資料夾位置

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>選取您要依「檔案ID」或「檔案路徑」來識別檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID / File Path]</td> 
   <td> <p>選取您要如何輸入「檔案ID」或「檔案路徑」：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您要從可用檔案或路徑清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取包含您要移動之檔案或資料夾的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入包含您要移動之檔案或資料夾的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取包含您要移動之檔案或資料夾的[!DNL SharePoint]網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取其磁碟機包含您要移動之檔案或資料夾的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要移動之檔案或資料夾的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">選取 [!UICONTROL File/Folder]</td> 
   <td>選取您要移動檔案還是資料夾。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</p> <p role="rowheader">[!UICONTROL Folder] / [!UICONTROL Folder ID] / [!UICONTROL Folder Path]</p> </td> 
   <td> <p>如果您已選取[!UICONTROL Enter Manually]，請輸入或對應您要移動之檔案或資料夾的ID或路徑。</p> <p>如果您從清單中選取[!UICONTROL Select]，請選取您要移動的檔案或資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a New Folder Location]</td> 
   <td> <p>選取要如何輸入您要移動檔案或資料夾的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您要從可用檔案或路徑清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要移動檔案或資料夾的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入您要移動檔案或資料夾的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取您要移動檔案或資料夾的[!DNL SharePoint]網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取您要移動檔案或資料夾之磁碟機的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要移動檔案或資料夾之資料夾的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> <p>如果您將此保留為空白，則檔案或資料夾只能在同一[!DNL OneDrive]中移動。</p> <p>您可以將檔案和資料夾從[!UICONTROL My Drive]移至[!UICONTROL Site's Drive]或[!UICONTROL Group's Drive]。 </p> <p>您只能將檔案從[!UICONTROL Site's Drive]移到相同網站中的相同磁碟機。</p> <p>您只能將檔案從[!UICONTROL Group's Drive]移到相同群組中的相同磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>輸入或對應您要移動檔案或資料夾的資料夾。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Copy a File]

此動作模組會將檔案複製到新的資料夾位置

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File ID & File Path)]</td> 
   <td>選取您要依「檔案ID」或「檔案路徑」來識別檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File ID] / [!UICONTROL File Path]</td> 
   <td> <p>選取您要如何輸入「檔案ID」或「檔案路徑」：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您要從可用檔案或路徑清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取包含您要複製之檔案的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入包含您要複製之檔案或資料夾的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取包含您要移動之檔案的SharePoint網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取其磁碟機包含您要複製之檔案的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要複製之檔案的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</p> </td> 
   <td> <p>如果您已選取[!UICONTROL Enter Manually]，請輸入或對應您要複製的檔案識別碼或路徑。</p> <p>如果您從清單中選取[!UICONTROL Select]，請選取您要複製的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a New Folder Location]</td> 
   <td> <p>選取要如何輸入您要複製檔案的位置，或：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您想要從可用資料夾清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New OneDrive location]</td> 
   <td> <p>選取您要複製檔案管理員的位置。 如果您選擇從清單中選取新資料夾位置，則此選項可供使用。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入您要複製檔案之磁碟機的識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取您要複製檔案的[!DNL SharePoint]網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取您要複製檔案的磁碟機所在的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要複製檔案之資料夾的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> <p>如果您將此保留為空白，則檔案或資料夾只能複製於相同的[!UICONTROL OneDrive]內。</p> <p>您可以將檔案和資料夾從[!UICONTROL My Drive]複製到[!UICONTROL Site's Drive]或[!UICONTROL Group's Drive]。 </p> <p>您只能將檔案從[!UICONTROL Site's Drive]複製到相同網站中的相同磁碟機。</p> <p>您只能將檔案從[!UICONTROL Group's Drive]複製到相同群組中的相同磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder]</td> 
   <td>輸入或對應您要移動復本或資料夾的資料夾。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Copied File Name]</td> 
   <td> <p>輸入或對應檔案新復本的名稱。 如果您不想變更原始檔案名稱，可以保留空白。</p> <p>名稱必須包含副檔名。 範例：<code> file.txt</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File/Folder]

此動作模組會刪除選取的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter (File/Folder ID & Path)]</td> 
   <td>選取您要依「檔案ID」或「檔案路徑」來識別檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a File/Folder ID /Enter a File/Folder Path]</td> 
   <td> <p>選取您要如何輸入「檔案ID」或「檔案路徑」：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL Enter Manually]</b> </p> <p>如果您想要直接輸入ID或路徑，或是從先前的模組進行對應，請選取此選項。</p> </li> 
     <li> <p><b>[!UICONTROL Select from a list]</b> </p> <p>如果您要從可用檔案或路徑清單中選取，請選取此選項。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Choose your [!DNL OneDrive] 位置]</td> 
   <td> <p>選取您要搜尋的位置：</p> 
    <ul> 
     <li> <p><b>[!UICONTROL My Drive]</b> </p> <p>選取是否啟用模組以輸入磁碟機ID。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Yes]</b> </p> <p>輸入包含您要刪除之檔案或資料夾的磁碟機識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL No]</b> </p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Site's Drive]</b> </p> <p>選取包含您要刪除之檔案或資料夾的[!DNL SharePoint]網站。 可用的網站是後面跟著登入使用者的網站。</p> </li> 
     <li> <p><b>[!UICONTROL Group's Drive]</b> </p> <p>選取其磁碟機包含您要刪除之檔案或資料夾的群組。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Drive ID]</td> 
   <td> <p>選取或對應包含您要刪除之檔案或資料夾的磁碟機。 如果您在[!UICONTROL Enable to Enter a Drive ID]欄位中選取[!UICONTROL No]，則無法使用此欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">選取 [!UICONTROL File/Folder]</td> 
   <td>選取您要刪除檔案還是資料夾。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File] / [!UICONTROL File ID] / [!UICONTROL File Path]</td>
   <td> <p>如果您已選取[!UICONTROL Enter Manually]，請輸入或對應您要刪除之檔案的檔案ID或路徑。</p> <p>如果您從清單中選取[!UICONTROL Select]，請選取您要刪除的檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### [!UICONTROL Make an API Call]

此模組會執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL OneDrive]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>https://graph.microsoft.com</code>的路徑。 範例：<code> /v1.0/me/drive/root/children</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
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



## 如果您無法上傳或更新檔案

上傳或更新檔案失敗時，可能會出現幾個問題：

* 上傳的檔案太大，超過您[!DNL OneDrive]計畫的檔案大小上限，或者您已使用所有[!DNL OneDrive]帳戶的儲存配額。 若要取得更多儲存空間，請從[!DNL OneDrive]刪除現有檔案，或升級您的[!DNL OneDrive]帳戶。
* OneDrive不允許將兩個同名檔案上傳至單一資料夾。 如果目標資料夾包含與正在上傳的檔案同名的檔案，則案例執行會以錯誤終止。 解決方法就是重新命名要上傳的檔案。 如果您的目的是更新檔案，請使用[!UICONTROL Update a file]動作。
* 先前選取的資料夾（檔案將上傳至該資料夾）已不存在。 此情境將停止，您將需要再次選取目標資料夾。

---
title: CloudConvert模組
description: CloudConvert模組
author: Becky
feature: Workfront Fusion
exl-id: 52c4d18a-8bee-44d6-9a2c-cc9e157e1dde
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '2486'
ht-degree: 0%

---

# [!DNL CloudConvert]模組

在Adobe Workfront Fusion案例中，您可以自動化使用CloudConvert的工作流程，並將其連結至多個協力廠商應用程式和服務。 [!DNL CloudConvert]模組可讓您監視和管理[!DNL CloudConvert]帳戶中的工作、工作，以及匯入和匯出檔案。

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

## CloudConvert API資訊

CloudConvert聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://api.cloudconvert.com/v2/</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v2.14.22</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL CloudConvert]連線至[!DNL Workfront Fusion] {#connect-cloudconvert-to-workfront-fusion}

若要將您的[!DNL CloudConvert]帳戶連線至[!DNL Workfront Fusion]，您必須從您的[!DNL CloudConvert]帳戶取得API金鑰。

1. 登入您的[!DNL CloudConvert]帳戶並開啟您的[!UICONTROL Dashboard]。
1. 開啟&#x200B;**[!UICONTROL Authorization]>[!UICONTROL API Keys]**&#x200B;區段。
1. 按一下&#x200B;**[!UICONTROL Create New API key]**。
1. 輸入API金鑰的名稱，啟用您要使用的範圍，然後按一下&#x200B;**[!UICONTROL Create]**。
1. 複製提供的Token並將其儲存在安全的地方。
1. 在[!DNL Workfront Fusion]中，開始建立情境並開啟[!DNL CloudConvert]模組的&#x200B;**[!UICONTROL Create a connection]**&#x200B;對話方塊。

   如需指示，請參閱[在 [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)中建立情境。

1. 輸入您在步驟5中儲存的Token，然後按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線。

## [!DNL CloudConvert]模組及其欄位 {#cloudconvert-modules-and-their-fields}

當您設定[!DNL CloudConvert]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL CloudConvert]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [常見工作](#common-tasks)
* [個工作](#jobs)
* [任務](#tasks)
* [其他](#other)

### 常見任務

* [擷取網站](#capture-a-website)
* [[!UICONTROL Convert a file]](#convert-a-file)
* [建立封存](#create-an-archive)
* [合併檔案](#merge-files)
* [最佳化檔案](#optimize-a-file)

#### [!UICONTROL Capture a Website]

此動作模組會擷取指定的網站，並以PDF、JPG或PNG格式儲存。

您可以指定網站的URL和其他資訊，例如要儲存資訊的位置。

模組會傳回檔案ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入您要擷取的網站URL。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format] </td> 
   <td>選取您要以PNG、JPG或PDF格式儲存擷取的網站。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td>輸入目標輸出檔案的檔案名稱（包括副檔名）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers] </td> 
   <td> <p>（選用）定義請求標頭。 </p> <p>這在指定的URL需要授權時很有用。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Conversion and engine specific options] </p> </td> 
   <td>指定轉換和引擎特定選項。 若要檢視可用的選項，請參閱<code>input_format</code>和<code>output_format</code>的<a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API</a>檔案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a file] </td> 
   <td> <p>如果您也想在模組的輸出中包含檔案資料，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Convert a file]

將檔案轉換為選取的輸出格式。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input file]</td> 
   <td>選取您要使用[!DNL Workfront Fusion]上傳檔案，或提供要從中上傳檔案的URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a file]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Import a File from URL]</td> 
   <td> 
    <ul> 
     <li> <p><strong>[!UICONTROL URL]</strong> </p> <p>輸入要轉換的檔案URL。</p> </li> 
     <li> <p><strong>[!UICONTROL Headers]</strong></p> <p>定義請求標頭（選用）。 這在指定的URL需要授權時很有用。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Format]</td> 
   <td>選取是否要指定要轉換之檔案的輸入格式。 如果未指定，則會使用輸入檔案的副檔名作為輸入格式。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Input Format]</td> 
   <td>選取檔案的目前格式。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td>選取您要轉換檔案的目標檔案格式。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL File Name]</td> 
   <td>選擇目標輸出檔案的檔案名稱（包括副檔名）。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader"> <p>[!UICONTROL Conversion and engine specific options] </p> </td> 
   <td>指定轉換和引擎特定選項。 若要檢視可用的選項，請參閱<code>input_format</code>和<code>output_format</code>的<a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API</a>檔案。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Download a file] </td> 
   <td> <p>如果您也想在模組的輸出中包含檔案資料，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an Archive]

可讓您新增一或多個檔案至ZIP、RAR、7Z、TAR、TAR.GZ或TAR.BZ2封存檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Input Files]</p> </td> 
   <td> <p>指定您要新增至封存的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a File]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Import a file from URL]</p> </td> 
   <td> <p><strong>[!UICONTROL URL]</strong> </p> <p>輸入要封存的檔案URL。</p> <p><strong>[!UICONTROL Headers]</strong> </p> <p>定義請求標頭（選用）。 這在指定的URL需要授權時很有用。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p> 選取已封存檔案的目標格式。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td> <p> 輸入目標輸出檔案的檔案名稱（包括副檔名）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Conversion and engine specific options] </td> 
   <td> <p>指定轉換和引擎特定選項。 若要檢視可用的選項，請參閱<code>input_format</code>和<code>output_format</code>的<a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API</a>檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a File]</td> 
   <td> <p>如果您也想在模組的輸出中包含檔案資料，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Merge Files]

至少將兩個檔案合併到一個PDF中。 如果輸入檔案不是PDF，則會自動轉換成PDF。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Input Files]</p> </td> 
   <td> <p>指定您要合併的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a File]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Import a file from URL]</p> </td> 
   <td> <p><strong>[!UICONTROL URL]</strong> </p> <p>輸入要封存的檔案URL。</p> <p><strong>[!UICONTROL Headers]</strong> </p> <p>定義請求標頭（選用）。 這在指定的URL需要授權時很有用。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format]</td> 
   <td> <p> 選取合併檔案的目標格式。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td> <p> 輸入目標輸出檔案的檔案名稱（包括副檔名）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Conversion and engine specific options] </td> 
   <td> <p>指定轉換和引擎特定選項。 若要檢視可用的選項，請參閱<code>input_format</code>和<code>output_format</code>的<a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API</a>檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a File]</td> 
   <td> <p>如果您也想在模組的輸出中包含檔案資料，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Optimize a File]

此動作模組會最佳化並壓縮PDF、PNG或JPG格式的檔案。

您可以指定檔案以及最佳化及儲存檔案的引數。

模組會傳回檔案ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input File]</td> 
   <td>選取您要使用Workfront Fusion上傳檔案，或提供要從中上傳檔案的URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Upload a File]</p> </td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Import a file from URL] </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL URL]</strong>：輸入要轉換的檔案URL。</li> 
     <li><strong>[!UICONTROL Headers]</strong>：（選用）定義請求標頭。 這在指定的URL需要授權時很有用。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Optimization for] </td> 
   <td> <p>針對特定目標需求選取最佳化設定檔。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Web]</strong>：網頁的最佳化（預設）</p> 
      <ul> 
       <li>移除Web多餘和不必要的資料</li> 
       <li>縮減取樣、剪下並聰明地壓縮影像</li> 
       <li>合併字型和子集字型</li> 
       <li>將色彩轉換為RGB</li> 
      </ul> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL Print]</strong>：最佳化列印</p> 
      <ul> 
       <li> <p>移除列印時多餘和不必要的資料</p> </li> 
       <li> <p>縮減取樣、剪下並聰明地壓縮影像</p> </li> 
       <li> <p>合併字型和子集字型</p> </li> 
       <li> <p>將顏色轉換為CMYK</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Archive]</strong>：針對封存用途最佳化</p> 
      <ul> 
       <li> <p>移除多餘和不必要的資料以進行封存</p> </li> 
       <li> <p>智慧型壓縮影像</p> </li> 
       <li> <p>合併字型和子集字型</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Scanned images]</strong>：掃描影像的最佳化</p> 
      <ul> 
       <li> <p>主要包含點陣化影像的PDF最佳化的設定檔</p> </li> 
       <li> <p>壓縮影像，而不大幅降低視覺品質</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL maximal size reduction]</strong>：最佳化以最大程度地減少大小</p> 
      <ul> 
       <li> <p>使用最大可能的壓縮</p> </li> 
       <li> <p>可能會降低視覺品質</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input format] </td> 
   <td>選取要最佳化的輸入檔案格式。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td> <p>輸入目標輸出檔案的檔案名稱（包括副檔名）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Conversion and engine specific options]</td> 
   <td> <p>指定轉換和引擎特定選項。 若要檢視可用的選項，請參閱<code>input_format</code>和<code>output_format</code>的<a href="https://cloudconvert.com/api/v2/convert#convert-tasks">[!DNL CloudConvert] API</a>檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Download a file]</td> 
   <td> <p>如果您也想在模組的輸出中包含檔案資料，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 工作

* [[!UICONTROL Create a Job (advanced)]](#create-a-job-advanced)
* [[!UICONTROL New Job Event]](#new-job-event)
* [[!UICONTROL List Jobs]](#list-jobs)
* [[!UICONTROL Get a Job]](#get-a-job)
* [[!UICONTROL Delete a Job]](#delete-a-job)

#### [!UICONTROL Create a Job (advanced)]

此模組會建立工作。 一個工作可以是一個或多個在[!UICONTROL Name]欄位中識別並使用[!UICONTROL Input]欄位相互連結的任務。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Input Files]</td> 
   <td> <p>選取您要使用[!DNL Workfront Fusion]上傳檔案，或提供要從中上傳檔案的URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload a File]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Import a File from URL]</p> </td> 
   <td> 
    <ul> 
     <li><strong>[!UICONTROL URL]</strong>：輸入您要處理之檔案的URL。</li> 
     <li><strong>[!UICONTROL Headers]</strong>：（選用）定義請求標頭。 這在指定的URL需要授權時很有用。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Tasks]</p> </td> 
   <td> <p>新增將在工作內執行的任務。</p> <p>請在對應區段中尋找作業欄位的說明。</p> 
    <ul> 
     <li><a href="#convert-a-file" class="MCXref xref">[!UICONTROL Convert a file]</a> </li> 
     <li><a href="#capture-a-website" class="MCXref xref">[!UICONTROL Capture a Websit]e</a> </li> 
     <li><a href="#optimize-a-file" class="MCXref xref">[!UICONTROL Optimize a File]</a> </li> 
     <li><a href="#create-an-archive" class="MCXref xref">[!UICONTROL Create an Archive]</a> </li> 
     <li><a href="#merge-files" class="MCXref xref">[!UICONTROL Merge Files]</a> </li> 
    </ul> 
    <ul> 
     <li> <p><strong>[!UICONTROL Execute a Command]</strong> </p> <p>如需有關執行命令的詳細資訊，請參閱<a href="https://cloudconvert.com/api/v2/command#command-tasks">[!DNL CloudConvert] API檔案</a>。</p> </li> 
     <li> <p><strong>[!UICONTROL Export a File to Temporary URL]</strong> </p> <p> 指定工作名稱和輸入工作名稱（例如轉換）。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tag] </td> 
   <td> <p>輸入標籤。 標籤是用來識別工作的任意字串。 註解沒有任何效果，可用來將工作與ID建立關聯。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Job]

此模組會刪除工作，包括所有任務和資料。

>[!NOTE]
>
>工作會在結束24小時後自動刪除。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID]</td> 
   <td> <p>輸入或對應您要刪除之工作的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Job]

此模組會擷取工作詳細資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之作業的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Jobs]

此模組會擷取已在您帳戶中執行的所有工作。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status] </td> 
   <td> <p>選取工作狀態，以篩選傳回的工作。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>設定Workfront Fusion 2.0在一個執行週期中傳回的工作數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL New Job Event]

在您的帳戶或任務中建立、完成或失敗時觸發。

>[!NOTE]
>
>* 由[!UICONTROL Create a Job (advanced)]模組建立的工作包含&#x200B;*多個*&#x200B;工作。
>* 建立、完成或失敗的&#x200B;*個別*&#x200B;任務時，也會觸發[!UICONTROL New Job Event]觸發器。
>

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhhook name]</td> 
   <td>輸入webhook名稱。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output Format] </td> 
   <td>選取您要以PNG、JPG或PDF格式儲存擷取的網站。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event]</td> 
   <td>選取在建立、完成或失敗工作或任務時是否觸發模組。</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* 如果使用陣列彙總（例如，您有許多不同格式的檔案要轉換），請使用[!UICONTROL Add a task]對話方塊中的&#x200B;**[!UICONTROL I don't know the input format]**&#x200B;選項。 否則會傳回錯誤。
>* 連結工作內的工作（名稱>輸入、名稱>輸入……）：
>
>  ![](/help/workfront-fusion/references/apps-and-modules/assets/linking-name-across-jobs-350x808.png)>

### 任務

* [[!UICONTROL Get a Task]](#get-a-task)
* [[!UICONTROL Download a File]](#download-a-file)
* [[!UICONTROL List Tasks]](#list-tasks)
* [[!UICONTROL Retry a Task]](#retry-a-task)
* [[!UICONTROL Cancel a Task]](#cancel-a-task)
* [[!UICONTROL Delete a Task]](#delete-a-task)

#### [!UICONTROL Cancel a Task]

此模組會取消處於等待或處理狀態的任務。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> 輸入或對應您要取消之工作的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Task]

刪除任務，包括所有資料。

>[!NOTE]
>
>任務結束後24小時會自動刪除。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> 輸入（對應）您要刪除之任務的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download a File]

此模組會從指定的工作擷取檔案名稱和檔案資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> 輸入或對應您要從其中下載檔案的工作的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Task]

此模組會擷取任務詳細資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之任務的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Tasks]

此模組會根據篩選設定擷取您帳戶中的所有工作。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Status] </td> 
   <td> <p>選取任務狀態，以篩選傳回的任務。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Job ID] </td> 
   <td> <p>輸入或對應工作ID以僅傳回指定工作內的工作。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Operation] </td> 
   <td> <p>輸入作業型別，以僅傳回具有指定作業的任務。 </p> <p>注意：使用[!UICONTROL List Possible Operations]模組來擷取作業。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Retry a Task]

此模組會根據其他任務的設定（裝載）建立新任務。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Task ID]</td> 
   <td> <p> 輸入或對應您要建立新任務的任務ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [[!UICONTROL Get My Info]](#get-my-info)
* [[!UICONTROL Make an API Call]](#make-an-api-call)

#### [!UICONTROL Get My Info]

擷取有關目前使用者的已驗證帳戶詳細資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL CloudConvert]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cloudconvert-to-workfront-fusion" class="MCXref xref">將[!DNL CloudConvert]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Make an API Call]

可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將[Fusion App]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>輸入相對於<code>https://api.cloudconvert.com/</code>的路徑。 例如： <code>/v2/tasks</code></p> <p>如需可用端點的清單，請參閱<a href="https://cloudconvert.com/api/v2">[!DNL CloudConvert] API v2檔案</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion 2.0會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。<img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"></p> </td> 
  </tr> 
 </tbody> 
</table>

**範例：**&#x200B;清單任務

以下API呼叫傳回您CloudFront帳戶中的所有任務：

URL： `/v2/tasks`

方法： `GET`

![](/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-api-example-input.png)

在[!UICONTROL Bundle] > [!UICONTROL Body] > [!UICONTROL data]下模組的輸出中找到搜尋的相符專案。

在我們的範例中，傳回6項工作：

![](/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-api-example-output.png)

## 疑難排解 {#troubleshooting}

請參閱下表以瞭解可能的錯誤及其解決方案：

<table style="table-layout:auto">
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th> <p>錯誤</p> </th> 
   <th>後續步驟</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p><span style="font-weight: normal;">[!UICONTROL The output file size exceeds the limit allowed for your scenario.]</span> </p> </td> 
   <td> <p>請參閱檔案大小限制。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p><span style="font-weight: normal;">[!UICONTROL You have exceeded the maximum conversion time.]</span> </p> </td> 
   <td> <p>免費的[!DNL CloudConvert]計畫每天提供25分鐘的轉換時間。 如果您的使用量超過免費方案的限制，則可切換為（預付）套件或訂閱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p><span style="font-weight: normal;">[!UICONTROL Failed to read frame size: Could not seek to 1508. �/output/JLIADSA00137P0.mp3: Invalid argument.]</span> </p> </td> 
   <td> <p>例如，將檔案從MP3轉換為WAV時會擲回此錯誤。 請確定您選取了正確的區域，因為它會找到檔案的參照，而不只是正確的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL RuntimeError:] </p> <p><span style="font-weight: normal;">[!UICONTROL Maximum number of repeats exceeded.]</span> </p> </td> 
   <td> <p>在您的[!DNL CloudConvert]儀表板工作清單中找到對應的[!DNL CloudConvert]工作，並檢查工作的持續時間：</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-duration-350x177.png" style="width: 350;height: 177;"> </p> <p>[!DNL CloudConvert] &gt; [!UICONTROL Convert a File]模組的逾時設為3分鐘。 如果工作的持續時間超過3分鐘（可能是因為[!DNL CloudConvert]服務暫時超載），模組會擲回上述錯誤。</p> <p>在此案例中，請考量下列其中一個選項：</p> 
    <ul> 
     <li>啟用案例設定中的<strong>[!UICONTROL Allow storing of Incomplete Executions]</strong>選項，以儲存未完成的執行，以供稍後手動解析。 您可以選擇使用[!UICONTROL Break]指示詞將錯誤處理路由附加至[!DNL CloudConvert]模組，以自動解決未完成的執行。</li> 
     <li>停用[!DNL CloudConvert] &gt; [!UICONTROL Convert a file]模組中的<strong>[!UICONTROL Download a file]選項</strong>。 在此情況下，模組不會等待轉換結果。 若要取得轉換結果，請建立新案例並使用[!DNL CloudConvert] &gt; [!UICONTROL New Job Event]觸發器。</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## [!DNL CloudConvert]聯結器的範例工作流程

>[!INFO]
>
>**範例：**&#x200B;將視訊從MOV轉換為MP4格式
>
>1. 造訪[https://cloudconvert.com/video-converter](https://>cloudconvert.com/video-converter)
>1. 按一下&#x200B;**[!UICONTROL Select File]**&#x200B;並選擇您的範例MOV檔案。
>1. 按一下&#x200B;**[!UICONTROL Convert to]**&#x200B;旁的下拉式清單，然後選擇&#x200B;**[!UICONTROL MP4]**。
>
>1. 按一下&#x200B;**[!UICONTROL wrench]**&#x200B;圖示。
>1. 視需要設定MP4壓縮設定。
>1. 按一下&#x200B;**[!UICONTROL Convert]**。
>1. 轉換完成後，請按一下&#x200B;**[!UICONTROL Download]**。
>1. 檢閱轉換後的視訊。
>1. 重複步驟1至8，直到找到步驟5的最佳轉換設定為止。
>1. 造訪[https://cloudconvert.com/api/v2/convert#convert-tasks](https://cloudconvert.com/api/v2/convert#convert-tasks)
>1. 為&#x200B;**[!UICONTROL input_format]**&#x200B;欄位選擇&#x200B;**[!UICONTROL mov]**。
>
>1. 為&#x200B;**[!UICONTROL output_format]**&#x200B;欄位選擇&#x200B;**[!UICONTROL mp4]**。
>
>1. 所有可能的引數清單，例如video_codec、crf等。 將會出現。
>1. 在Workfront Fusion 2.0中，在您的情境中插入&#x200B;**[!UICONTROL CloudConvert]** > **[!UICONTROL Convert a File]**&#x200B;模組。
>
>1. 開啟模組的設定。
>1. 設定模組，如下所示：
>
>   ![](/help/workfront-fusion/references/apps-and-modules/assets/cloudconvert-mp4-example.png)
>
>1. 確定在「轉換及引擎特定選項」欄位中包含所有設定：針對步驟5中的每個設定，找出步驟13中的對應引數及其對應值。

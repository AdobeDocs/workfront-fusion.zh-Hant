---
title: Microsoft OneDrive for Business 模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL Microsoft OneDrive for Business] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 657bea46-064e-4333-8e86-81678bb1c3bd
TQID: https://experienceleague.adobe.com/bFoOLIFIX2ml2K2I2FVSJuNCPwlhfm6sa1RXaVzUoO0
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1154
ht-degree: 29%

---

# [!DNL Microsoft OneDrive for Business] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Microsoft OneDrive for Business] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

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

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要搭配Adobe Workfront Fusion使用[!DNL Microsoft OneDrive for Business]，您需要[!DNL Microsoft]帳戶。

## 正在將[!DNL Microsoft OneDrive for Business]服務連線到Workfront Fusion

如需有關將您的[!DNL Microsoft OneDrive for Business]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) — 基本指示

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## [!DNL Microsoft OneDrive for Business] 模組及其欄位

當您設定 [!DNL Microsoft OneDrive for Business] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Microsoft OneDrive for Business] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)

### 觸發程序

* [[!UICONTROL 觀看檔案]](#watch-files)
* [[!UICONTROL 監視資料夾]](#watch-folders)

#### [!UICONTROL 觀看檔案]

在被監視的資料夾中新增或更新新檔案時，此觸發模組會啟動。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL磁碟機ID]</p> </td> 
   <td> <p>選取您要觀看的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾]</td> 
   <td> <p> 選取要監視的資料夾。 在案例中，您只能監視一個資料夾。</p> <p>提示：若要監視多個資料夾，請為每個資料夾建立獨立的情境。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL我要觀看]</p> </td> 
   <td> <p>選取您是要監視新檔案與所有變更，還是隻監視新檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回資料列數目上限]</td> 
   <td> <p> 設定在一個週期內要模組傳回的結果數目上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 監視資料夾]

將新資料夾新增到要監看的資料夾時，此觸發模組會啟動。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 連線]</p> </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL磁碟機ID]</p> </td> 
   <td> <p>選取您要觀看的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾]</td> 
   <td> <p> 選取要監視的資料夾。 在案例中，您只能監視一個資料夾。</p> <p>提示：若要追蹤多個資料夾，請為每個資料夾建立獨立案例。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL我要觀看]</p> </td> 
   <td> <p>選取您要監視新資料夾和所有變更，還是隻監視新資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回資料列數目上限]</td> 
   <td> <p> 設定在一個週期內要模組傳回的結果數目上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 建立資料夾]](#create-a-folder)
* [[!UICONTROL 刪除檔案]](#delete-a-file)
* [[!UICONTROL 刪除資料夾]](#delete-a-folder)
* [[!UICONTROL 取得檔案]](#get-a-file)
* [[!UICONTROL 取得共用連結]](#get-a-sharing-link)
* [[!UICONTROL 上傳檔案]](#upload-a-file)

#### [!UICONTROL 建立資料夾]

在指定的父資料夾內建立資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td><strong>[！UICONTROL連線]</strong> </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td><strong>[！UICONTROL磁碟機識別碼]</strong> </td> 
   <td> <p>選取您要建立新資料夾的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td><strong>[！UICONTROL資料夾]</strong> </td> 
   <td> <p>選取您要建立新資料夾的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td><strong>[！UICONTROL資料夾名稱]</strong> </td> 
   <td>輸入或對應新資料夾的名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除檔案]

此動作模組會將指定的檔案移至資源回收筒。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL磁碟機ID]</td> 
   <td> <p>選取您要刪除檔案的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案 ID]</td> 
   <td> <p>輸入您要刪除之檔案的ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除資料夾]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL磁碟機ID]</td> 
   <td> <p>選取您要刪除檔案的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾 ID]</td> 
   <td> <p>輸入或對應您要刪除的資料夾識別碼。 </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得檔案]

此動作模組會擷取具有特定ID的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL磁碟機ID]</td> 
   <td> <p>選取您要擷取檔案的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 檔案 ID]</td> 
   <td> <p>輸入您要擷取的檔案ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得共用連結]

此模組會擷取您可共用的連結，以授予指定檔案的存取權。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL磁碟機ID]</td> 
   <td> <p>選取您要上傳檔案的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Enter]</td> 
   <td> <p>選取您要使用「檔案ID」或「檔案」路徑來選擇檔案。 在出現的欄位中輸入檔案ID或路徑。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[！UICONTROL許可權型別]</p> </td> 
   <td> <p>選取您希望收到連結的人員具有讀取/寫入許可權還是唯讀。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL範圍]</td> 
   <td> <p> 選取您是否希望檔案僅供擁有連結的任何人存取或僅供組織成員存取。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳檔案]

此動作模組會將二進位檔或文字檔上傳至指定的資料夾

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL磁碟機ID]</td> 
   <td> <p>選取您要上傳檔案的磁碟機。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 資料夾] </td> 
   <td> <p>選取磁碟機中的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL 來源檔案]</p> </td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL如果存在相同名稱的檔案]</td> 
   <td> <p> 選取當您嘗試上傳的檔案已存在時，您要執行的動作。</p> 
    <ul> 
     <li>[！UICONTROL取代現有的檔案]</li> 
     <li>[！UICONTROL重新命名新檔案]</li> 
     <li>[！UICONTROL結尾有錯誤]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

---
title: Azure DevOps模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動化使用 [!DNL Azure DevOps]的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: c0919a9a-ce99-485c-9627-45353741f6d8
source-git-commit: 58bda8289db60ce915613337880297e5c8ec7097
workflow-type: tm+mt
source-wordcount: '1821'
ht-degree: 0%

---

# [!DNL Azure DevOps]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Azure DevOps]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求</p>
   <p>或</p>
   <p>舊版：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL Azure DevOps]模組，您必須有[!DNL Azure] DevOps帳戶。

## [!DNL Azure DevOps] API資訊

Azure DevOps聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v5.1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.29.33</td> 
  </tr>
 </tbody> 
</table>

## 將[!DNL Azure DevOps]連線至[!DNL Workfront Fusion] {#connect-azure-devops-to-workfront-fusion}

1. 將[!DNL Azure DevOps]模組新增至您的情境。
1. 按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 在[!UICONTROL 連線型別]欄位中，選取您要使用的連線型別。

   >[!NOTE]
   >
   >[!UICONTROL [!DNL Azure DevOps] (EntraApp)]可讓您要求連線的所有領域。

1. 填寫下列欄位：

   <table style="table-layout:auto">
      <tr>
            <td>[!UICONTROL 連線名稱]</td>
            <td>輸入您正在建立的連線名稱。</td>
      </tr>
      <tr>
            <td>[!UICONTROL 組織]</td>
            <td>輸入您建立[!DNL Azure DevOps]應用程式的組織名稱。</td>
      </tr>
      <tr>
            <td>[!UICONTROL 應用程式ID]</td>
            <td>輸入您要連線的DevOps應用程式ID。</td>
      </tr>
      <tr>
            <td>[!UICONTROL 使用者端密碼]</td>
            <td>輸入您要連線之DevOps應用程式的使用者端密碼。</td>
      </tr>
      <tr>
            <td>[!UICONTROL 要求所有範圍]</td>
            <td>如果您使用[!DNL Azure DevOps] (EntraApp)連線型別，請啟用此選項以要求連線的所有範圍。</td>
      </tr>
   </table>

1. 若要輸入Azure DevOps應用程式ID或使用者端密碼，請按一下<b>顯示進階設定</b>，然後在開啟的欄位中輸入這些設定。
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;完成連線的設定並繼續建立您的情境。

## [!UICONTROL Azure DevOps]模組及其欄位

當您設定[!DNL Azure DevOps]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Azure DevOps]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

#### [!UICONTROL 觀看工作專案]

此立即觸發模組會在[!UICONTROL Azure DevOps]中新增、更新或刪除記錄時執行案例。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>選取或新增模組的webhook。</p> <p>如需有關觸發程式模組中webhook的詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/webhooks-reference.md" class="MCXref xref">即時觸發程式(webhook)</a>。</p> <p>如需如何建立Webhook的詳細資訊，請參閱<a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webhook</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [建立記錄](#create-a-record)
* [自訂API呼叫](#custom-api-call)
* [下載附件](#download-an-attachment)
* [連結工作專案](#link-work-items)
* [讀取記錄](#read-record)
* [更新工作專案](#update-a-work-item)
* [[!UICONTROL 上傳附件]](#upload-an-attachment)

#### [!UICONTROL 建立記錄]

此動作模組會建立新專案或工作專案。

模組會輸出新建立工作專案的物件ID，或新建立專案的URL和狀態代碼。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要建立工作專案或專案。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 專案]</strong> </p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL 名稱]</strong>：輸入或對應新專案的名稱。</p> </li> 
       <li> <p><strong>[!UICONTROL 描述]</strong>：輸入或對應新專案的描述。 </p> </li> 
       <li> <p><strong>[!UICONTROL 可見性]</strong>：選取您要將專案設為公開或私人。 使用者必須登入您的組織，且必須已被授予專案的存取權，才能與私人專案互動。 未登入您組織的使用者可看見公用專案。</p> </li> 
       <li> <p><strong>[!UICONTROL 版本控制]</strong>：選取您要專案使用[!DNL Git]或[!UICONTROL Team Foundation版本控制(TFCV)]進行版本控制。</p> </li> 
       <li> <p><strong>[!UICONTROL 工作專案程式]</strong>：選取您要用於專案的工作程式。 選項為[!UICONTROL Basic]、[!UICONTROL Scrum]、[!UICONTROL Capability Maturity Model Integration (CMMI)]及[!UICONTROL Agile]。</p> <p>如需[!DNL Azure DevOps]流程的詳細資訊，請參閱[!DNL Azure DevOps]檔案中的<a href="https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/choose-process?view=azure-devops&amp;tabs=basic-process">預設流程與流程範本</a>。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL 工作專案]</strong> </p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL 專案]</strong>：選取您要建立工作專案的專案。</p> </li> 
       <li> <p><strong>[!UICONTROL 工作專案型別]</strong>：選取您要建立的工作專案型別。</p> </li> 
       <li> <p><strong>[!UICONTROL 其他欄位]</strong>：在這些欄位中，輸入您想要工作專案對於指定屬性具有的值。 可用欄位取決於工作專案型別。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂API呼叫]

此動作模組可讓您對[!DNL Azure DevOps] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Azure DevOps]模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 基底URL]</td> 
   <td> <p>選取或對應您用來連線至[!DNL Azure DevOps]帳戶的基本URL</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 相對URL]</td> 
   <td> <p>輸入此API呼叫要連線的相對URL。</p> <p><b>範例： </b><code>{organization}/_apis[/{area}]/{resource}</code> </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL API版本]</td> 
   <td>選取或對應您要連線至此API呼叫的[!DNL Azure DevOps] API版本。 如果未選取版本，[!DNL Workfront Fusion]會連線至[!DNL Azure DevOps] API 5.1版。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> </td> 
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

#### [!UICONTROL 下載附件]

此動作模組會下載附件。

模組會傳回附件的檔案內容。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 附件URL]</td> 
   <td> <p>輸入或對應您要下載之附件的URL。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 連結工作專案]

此動作模組連結兩個工作專案並定義它們之間的關係。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作專案ID]</td> 
   <td>輸入或對應您要連結其他工作專案的主要工作專案專案ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連結的工作專案ID]</td> 
   <td>輸入或對應您要連結至主要工作專案的工作專案ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連結型別]</td> 
   <td> <p>定義您要連結之工作專案之間的關係。</p> <p>如需詳細資訊，請參閱[!UICONTROL Azure DevOps]檔案中的<a href="https://docs.microsoft.com/en-us/azure/devops/boards/queries/link-type-reference?view=azure-devops">連結型別</a>參考指南。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解]</td> 
   <td>輸入或對應註解的文字。 這對於說明連結的推理或意圖很有用。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組從[!DNL Azure DevOps]中的單一記錄讀取資料。

您指定記錄的ID。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要讀取專案或工作專案</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 專案]</strong>：選取您要讀取的專案。</p> </li> 
     <li> <p><strong>[!UICONTROL 工作專案]</strong>：選取包含您要讀取之工作專案的專案，然後選取工作專案型別。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取要包含在此模組輸出組合中的資訊。 可用欄位取決於工作專案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>輸入或對應您要讀取之記錄的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新工作專案]

此動作模組使用其ID更新現有工作專案。

模組會傳回已更新工作專案的識別碼。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案]</td> 
   <td>選取包含您要更新之工作專案的專案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作專案型別]</td> 
   <td> <p>選取您要更新的工作專案型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 其他欄位]</td> 
   <td>在每個欄位中，輸入您想要工作專案對於指定屬性具有的值。 可用欄位取決於工作專案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作專案ID]</td> 
   <td>輸入或對應您要更新的工作專案ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳附件]

此動作模組會上傳檔案並將其附加至工作專案。

模組會傳回附件的附件ID和下載URL。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案] </td> 
   <td> <p>選取您要上傳附件的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作專案ID]</td> 
   <td> <p>輸入或對應您要上傳附件之工作專案的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解]</td> 
   <td>輸入要新增至已上傳附件的註解文字。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source檔案] </td> 
   <td>從先前的模組中選取來源檔案，或輸入或對應來源檔案的名稱和內容。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL 列出工作專案]

此動作模組會擷取[!DNL Azure DevOps]專案中所有特定型別的工作專案。

模組會傳回主要工作專案的ID及任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Azure DevOps]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-azure-devops-to-workfront-fusion" class="MCXref xref">將[!DNL Azure DevOps]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案]</td> 
   <td>選取您要從中擷取工作專案的專案。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作專案型別]</td> 
   <td> <p>選取您要擷取的工作專案型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要顯示在模組輸出中的屬性。 可用欄位取決於您要擷取的工作專案型別。 您必須至少選取一個屬性。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對映[!DNL Workfront Fusion]在一個執行週期內傳回的最大工作專案數。</td> 
  </tr> 
 </tbody> 
</table>

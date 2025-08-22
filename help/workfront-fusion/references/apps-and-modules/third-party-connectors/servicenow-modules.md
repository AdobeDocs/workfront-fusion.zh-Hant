---
title: ServiceNow模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用 [!DNL ServiceNow]的工作流程，並將其連線至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 7b236869-bd83-4db5-a363-d6570f6e4aff
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 1%

---

# [!DNL ServiceNow]模組

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL ServiceNow]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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
   <p>新增:</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL ServiceNow]模組，您必須有[!DNL ServiceNow]帳戶。

## ServiceNow API資訊

ServiceNow聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>https://{{connection.instance}}/api</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.5.13</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL ServiceNow]連線至Workfront Fusion

若要為您的[!DNL ServiceNow]模組建立連線：

1. 當您開始設定第一個&#x200B;**[!UICONTROL 模組時，請按一下]**&#x200B;連線[!UICONTROL 方塊旁的]新增[!DNL ServiceNow]。
1. 輸入下列：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線名稱]</p> </td> 
      <td>輸入新[!DNL ServiceNow]連線的名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 環境]</p> </td> 
      <td>選取您要連線到生產或非生產環境。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 密碼]</p> </td> 
      <td>選取您要連線到服務帳戶還是個人帳戶。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 使用者名稱]</p> </td> 
      <td>輸入您的[!DNL ServiceNow]使用者名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 密碼]</p> </td> 
      <td>輸入您的ServiceNow密碼。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 執行個體]</p> </td> 
      <td> <p>輸入沒有[!DNL ServiceNow]的<code>https://</code>帳戶位址（通常是<code>&lt;company>.service-now.com</code>）。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**繼續**&#x200B;以儲存連線並返回模組。

   <!--Markdown placeholder-->

## [!UICONTROL ServiceNow]模組及其欄位

當您設定[!DNL ServiceNow]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL ServiceNow]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

>[!NOTE]
>
>* 如果在&quot;[!UICONTROL 記錄型別]&quot;欄位中選取自訂記錄，則載入自訂欄位可能需要一些時間。
>
>* 如果沒有自訂記錄，「記錄型別」欄位下拉式清單將為空白。

### 觸發程序

#### [!UICONTROL 觀看記錄]

建立或更新記錄時，此觸發模組會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要觀察的表格是自訂表格還是標準表格。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td>選取您要觀看的記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示]</td> 
   <td>選取您要顯示的值型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要模組輸出的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td>選取您要監視新記錄或更新的記錄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 建立記錄]](#create-a-record)
* [[!UICONTROL 自訂API呼叫]](#custom-api-call)
* [[!UICONTROL 停用使用者]](#deactivate-a-user)
* [[!UICONTROL 刪除記錄]](#delete-a-record)
* [[!UICONTROL 下載附件]](#download-an-attachment)
* [[!UICONTROL 讀取記錄]](#read-a-record)
* [[!UICONTROL 上傳附件]](#upload-an-attachment)
* [[!UICONTROL 更新記錄]](#update-a-record)

#### [!UICONTROL 建立記錄]

此動作模組會建立新的[!DNL ServiceNow]記錄。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要在自訂表格或標準表格中建立記錄。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td>選取您要模組建立的[!DNL ServiceNow]記錄型別。 然後，您可以填寫此記錄型別的可用欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂API呼叫]

此動作模組可讓您對[!DNL ServiceNow] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL ServiceNow]模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 相對URL]</td> 
   <td> 輸入相對於<code>https://&ltinstance_url&gt/api/</code>的路徑。 </td> 
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

#### [!UICONTROL 停用使用者]

此動作模組使用系統ID在[!DNL ServiceNow]中停用使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 使用者系統識別碼]</td> 
   <td> 輸入或對應您要停用模組之使用者的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除事件或使用者。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td>選取您要刪除事件或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 系統ID]</td> 
   <td>輸入或對應您要模組刪除之記錄的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 下載附件]

此動作模組會下載[!DNL ServiceNow]記錄中的附件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 附件系統ID]</td> 
   <td> 輸入或對應您要模組下載之附件的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組使用系統ID讀取[!DNL ServiceNow]記錄。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄系統ID]</td> 
   <td>輸入或對應您要模組讀取之記錄的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要讀取的記錄是在自訂表格中還是在標準表格中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td>選取您希望模組讀取的[!DNL ServiceNow]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示]</td> 
   <td>選取您要顯示的值型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組會建立新的[!DNL ServiceNow]記錄。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄系統ID]</td> 
   <td>輸入或對應您要模組更新的記錄的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取要更新的記錄是在自訂表格中還是在標準表格中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td>選取您希望模組更新的[!DNL ServiceNow]記錄型別。 然後，您可以填寫此記錄型別的可用欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳附件]

此動作模組會將附件上傳至[!DNL ServiceNow]記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表名稱]</td> 
   <td>輸入或對應您要上傳附件的表格名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 系統ID]</td> 
   <td>輸入或對應您要上傳附件之專案的唯一[!DNL ServiceNow]識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL 搜尋記錄]

此模組會使用您選取的條件來搜尋記錄。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將ServiceNow帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-servicenow-to-workfront-fusion" class="MCXref xref">將[!DNL ServiceNow]連線到[!UICONTROL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料表型別]</td> 
   <td>選取您要搜尋的表格是自訂表格還是標準表格。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td>選取您要搜尋的記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結果集]</td> 
   <td>選取您希望模組傳回符合條件的所有記錄，還是隻傳回符合條件的第一筆記錄。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 最大記錄數]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋型別]</td> 
   <td> <p>選取您希望模組執行的搜尋型別</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 進階查詢]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL 搜尋查詢]</p> <p>輸入自訂搜尋查詢。 如需[!DNL ServiceNow]自訂搜尋查詢的相關資訊，請參閱<a href="https://docs.servicenow.com/bundle/orlando-platform-user-interface/page/use/common-ui-elements/reference/r_OpAvailableFiltersQueries.html">ServiceNow查詢檔案</a>。</p> </li> 
      </ul> </li> 
     <li> <p><strong>[!UICONTROL Simple]</strong> </p> 
      <ul> 
       <li> <p>[!UICONTROL 搜尋條件]</p> <p>輸入您希望模組搜尋的條件。 </li> 
       <li> <p>[!UICONTROL 排序依據]</p> <p>指出您希望模組排序結果的欄位，以及應依遞增或遞減排序。</p> </li> 
      </ul> </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示]</td> 
   <td>選取您要顯示的值型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

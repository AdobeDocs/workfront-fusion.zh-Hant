---
title: Microsoft Dynamics 365模組
description: 在Adobe Workfront Fusion情境中，您可以自動化使用Microsoft Dynamics 365的工作流程，並將其連線到多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 16ae173b-10ce-481d-8f6c-1df0e65f7c0e
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1866'
ht-degree: 1%

---

# [!DNL Microsoft Dynamics 365 modules]

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Microsoft Dynamics 365]的工作流程，並將其連線至多個協力廠商應用程式和服務。

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365]聯結器不支援[!DNL Dynamics Finance and Operations]。
>
>有關[!DNL Microsoft Dynamics 365 Finance and Operations]聯結器的資訊，請參閱[[!DNL Microsoft Dynamics 365 Finance and Operations] 模組](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/dynamics-finance-operations-modules.md)。

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

若要使用[!DNL Microsoft Dynamics] 365，您必須有[!DNL Microsoft Dynamics 365]帳戶。

## 將Microsoft Dynamics 365連線至Workfront Fusion

您可以直接從[!DNL Microsoft Dynamics 365]模組內建立與您的[!DNL Microsoft Dynamics 365]帳戶的連線。

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

1. 在任何[!DNL Microsoft Dynamics 365]模組中，按一下&#x200B;**[!UICONTROL 連線]**&#x200B;欄位旁的[!UICONTROL 新增]。


1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[！UICONTROL連線名稱]</td>
          <td>
            <p>輸入此連線的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL環境]</td>
          <td>選取您要連線到生產或非生產環境。</td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL型別]</td>
          <td>選取您是要連線到服務帳戶還是個人帳戶。</td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL使用者端ID]<p>(選填)</p></td>
          <td>輸入您的[!DNL Microsoft Dynamics] [！UICONTROL使用者端識別碼]。</td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL使用者端密碼]<p>(選填)</p></td>
          <td>輸入您的[!DNL Microsoft Dynamics] [！UICONTROL使用者端密碼]。
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL驗證URL]</td>
          <td>輸入您的Workfront執行個體將用來驗證此連線的URL。 <p>預設值為 <code>https://oauth.my.workfront.com/integrations/oauth2</code>。</p>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL資源]</td>
          <td>輸入您[!DNL Dynamics 365]帳戶的地址，不含<code>>https://</code>。</p>
        </tr>
      </tbody>
    </table>
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

>[!NOTE]
>
>在您的[!DNL Microsoft Azure]入口網站中註冊Workfront Fusion時，請使用下列重新導向URI：
>
>* `https://app.workfrontfusion.com/oauth/cb/workfront-microsoft-dynamics2`


## [!DNL Microsoft Dynamics 365]模組及其欄位

當您設定[!DNL Microsoft Dynamics 365]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Microsoft Dynamics 365]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

* [[!UICONTROL 觀看記錄（即時）]](#watch-records-real-time)
* [[!UICONTROL 觀看記錄（已排程）]](#watch-records-scheduled)

#### [!UICONTROL 觀看記錄（即時）]

這個立即觸發模組會在[!DNL Dynamics 365]中建立或更新您指定的記錄（物件）時執行案例。

此模組需要webhook。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook]</td> 
   <td> <p>選取您要用於此模組的webhook。 </p> <p>若要新增webhook：</p> 
    <ol> 
     <li value="1"> <p>按一下Webhook欄位右側的<strong>[！UICONTROL Add]</strong></p> </li> 
     <li value="2"> <p>在<strong>[！UICONTROL Webhook]</strong>名稱欄位中，輸入webhook的描述性名稱。</p> </li> 
     <li value="3"> <p>在<strong>[！UICONTROL Connection]</strong>欄位中，選取您要使用的連線</p> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </li> 
     <li value="4"> <p>按一下<strong>[！UICONTROL儲存]</strong>以儲存您的webhook並返回模組。</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看記錄（已排程）]

當您指定的物件中的記錄是在此案例的上次排定執行後建立或更新時，此排定的觸發模組會執行案例。

模組輸出會指出找到的記錄是新的還是更新的。 如果記錄是在時段中新增和更新的，則會傳回為新記錄。

這會以您指定的定期排程間隔發生。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> "
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Include]</td> 
   <td>選取您希望模組僅觀看<strong>[！UICONTROL新記錄]</strong>、<strong>[！UICONTROL僅更新記錄]</strong>或<strong>[！UICONTROL新記錄和更新記錄]</strong>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選擇要讓情境觀看的[！UICONTROL Microsoft Dynamics 365]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸出]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。 根據所選的實體型別，可使用欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL最大記錄數]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 建立記錄]](#create-record)
* [[!UICONTROL 進行API呼叫]](#make-an-api-call)
* [[!UICONTROL 刪除記錄]](#delete-record)
* [[!UICONTROL 讀取記錄]](#read-records)
* [[!UICONTROL 更新記錄]](#update-record)


#### [!UICONTROL 建立記錄]

此動作模組會建立實體，例如約會或任務。

您可以指定要建立的圖元相關資訊。

模組會傳回新實體的ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您要模組建立的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL選擇要對應的欄位]</td> 
   <td>選取建立記錄時您想要包含值的欄位。 可用欄位取決於實體型別。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[！UICONTROL屬性欄位]</td> 
   <td> 這些是您選取的欄位。 輸入您要讓記錄擁有指定屬性的值。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除實體。

您可以指定實體的ID。

模組會傳回實體ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td> <p>選取您要讓模組刪除的實體型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL ID]</td> 
   <td> <p>輸入或對應您要模組刪除之記錄的唯一[!DNL Microsoft Dynamics 365]識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行API呼叫]

此動作模組可讓您對[!DNL Microsoft Dynamics 365] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Microsoft Dynamics 365]模組無法完成的資料流程自動化。

模組會傳回狀態代碼、標題和本文的相關資訊。 您可以在情境中的後續模組中對應此資訊。

若要深入瞭解，請參閱有關使用[!DNL Microsoft]的[!DNL Dynamics 365 Customer Engagement Web API]檔案。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL URL]</td> 
   <td> <p>輸入相對於<code>&lt;Instance URL>/api/data/v9.1/</code>的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> <p>有關詳細資訊</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組從[!DNL Microsoft Dynamics 365]中的單一實體讀取資料。

您可以指定實體的ID。

模組會傳回實體ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您希望模組讀取的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸出]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL ID]</td> 
   <td>輸入或對應您要模組讀取之記錄的唯一[!DNL Microsoft Dynamics 365]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組會更新實體。

您可以指定實體的ID。

模組會傳回更新記錄的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您希望模組更新的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL選擇要對應的欄位]</td> 
   <td>選取建立記錄時您想要包含值的欄位。 可用欄位取決於實體型別。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[！UICONTROL屬性欄位]</td> 
   <td>這些是您選取的欄位。 輸入您要讓記錄擁有指定屬性的值。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[！UICONTROL ID]</td> 
   <td>輸入或對應您要模組更新的記錄的唯一[!DNL Microsoft Dynamics] 365 ID。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL 搜尋記錄]

此搜尋模組會在[!DNL Microsoft Dynamics 365]中尋找符合您指定之搜尋查詢的物件記錄。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到Workfront Fusion</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL實體型別]</td> 
   <td>選取您希望模組更新的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL篩選器]</td> 
   <td> <p>選取要用於此搜尋的篩選器。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL標準篩選器]</strong> </p> <p>選取欄位和運運算元，然後輸入或對應您要搜尋的值，以設定篩選。 您可以使用AND或OR規則來篩選篩選器。</p> </li> 
     <li> <p><strong>[！UICONTROL查詢函式]</strong> </p> <p>輸入您要用來搜尋的[!DNL Dynamics 365]網頁API查詢函式。 </p> <p>如需查詢函式的詳細資訊，請參閱<a href="https://docs.microsoft.com/en-us/dynamics365/customer-engagement/web-api/queryfunctions?view=dynamics-ce-odata-9">檔案中的</a>Web API查詢函式參考[!DNL Microsoft]。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL排序]</td> 
   <td> <p>指定專案傳回的順序。 您可以新增多個排序。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL欄位]</strong> </p> <p>指定您要排序結果的欄位。</p> </li> 
     <li> <p><strong>[！UICONTROL方向]</strong> </p> <p>指定排序方向（升序或降序）。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL最大記錄數]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸出]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
 </tbody> 
</table>

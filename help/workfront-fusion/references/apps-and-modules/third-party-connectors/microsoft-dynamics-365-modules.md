---
title: Microsoft Dynamics 365模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Microsoft Dynamics 365的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 16ae173b-10ce-481d-8f6c-1df0e65f7c0e
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics 365 modules]

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Microsoft Dynamics 365]的工作流程，並將其連線至多個協力廠商應用程式和服務。

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365]聯結器不支援[!DNL Dynamics Finance and Operations]。

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

若要使用[!DNL Microsoft Dynamics] 365，您必須有[!DNL Microsoft Dynamics 365]帳戶。

## 將Microsoft Dynamics 365連線至Workfront Fusion

您可以直接從[!DNL Microsoft Dynamics 365]模組內建立與您的[!DNL Microsoft Dynamics 365]帳戶的連線。

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

1. 在任何[!DNL Microsoft Dynamics 365]模組中，按一下[!UICONTROL Connection]欄位旁的&#x200B;**[!UICONTROL Add]**。
1. 輸入連線的名稱。
1. 在&#x200B;**[!UICONTROL Resource]**&#x200B;欄位中，輸入您的[!DNL Dynamics 365]帳戶位址（不含`https://`）。
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線，並返回模組。

>[!NOTE]
>
>在您的[!DNL Microsoft Azure]入口網站中註冊[!DNL Workfront Fusion]時，請使用下列重新導向URI：
>
>* `https://app.workfrontfusion.com/oauth/cb/workfront-microsoft-dynamics2`


## [!DNL Microsoft Dynamics 365]模組及其欄位

當您設定[!DNL Microsoft Dynamics 365]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Microsoft Dynamics 365]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [[!UICONTROL Watch Records (Scheduled)]](#watch-records-scheduled)
* [[!UICONTROL Watch Records (Real Time)]](#watch-records-real-time)
* [[!UICONTROL Create Record]](#create-record)
* [[!UICONTROL Make an API Call]](#make-an-api-call)
* [[!UICONTROL Delete Record]](#delete-record)
* [[!UICONTROL Read Records]](#read-records)
* [[!UICONTROL Update Record]](#update-record)
* [[!UICONTROL Search Records]](#search-records)

### [!UICONTROL Watch Records (Scheduled)]

當您指定的物件中的記錄是在[!DNL Dynamics 365]中上次排定的執行之後建立或更新時，此排定的觸發模組會執行一個案例。

模組的輸出指出它找到的記錄是新的還是更新的（如果它在時段中同時新增和更新，則標籤為新）。 您可以在情境中的後續模組中對應此資訊。

這會以您指定的定期排程間隔發生。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include]</td> 
   <td>選取您要讓模組觀看<strong>[!UICONTROL Only new records]</strong>、<strong>[!UICONTROL Updated records only]</strong>或<strong>[!UICONTROL New records and all changes]</strong>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選擇您希望案例觀看的[!UICONTROL Microsoft Dynamics 365]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Watch Records (Real Time)]

這個立即觸發模組會在[!DNL Dynamics 365]中建立或更新您指定的記錄（物件）時執行案例。

此模組需要webhook。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>選取您要用於此模組的webhook。 </p> <p>若要新增webhook：</p> 
    <ol> 
     <li value="1"> <p>按一下Webhook欄位右側的<strong>[!UICONTROL Add]</strong></p> </li> 
     <li value="2"> <p>在<strong>[!UICONTROL Webhook]</strong>名稱欄位中，輸入webhook的描述性名稱。</p> </li> 
     <li value="3"> <p>在<strong>[!UICONTROL Connection]</strong>欄位中，選取您要使用的連線</p> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </li> 
     <li value="4"> <p>按一下<strong>[!UICONTROL Save]</strong>以儲存您的webhook並返回模組。</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Create Record]

此動作模組會建立實體，例如約會或任務。

您可以指定要建立的圖元相關資訊。

模組會傳回新實體的ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您要模組建立的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>選取建立記錄時您想要包含值的欄位。 可用欄位取決於實體型別。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td> 這些是您選取的欄位。 輸入您要讓記錄擁有指定屬性的值。 </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Make an API Call]

此動作模組可讓您對[!DNL Microsoft Dynamics 365] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Microsoft Dynamics 365]模組無法完成的資料流程自動化。

模組會傳回狀態代碼、標題和本文的相關資訊。 您可以在情境中的後續模組中對應此資訊。

若要深入瞭解，請參閱有關使用[!DNL Dynamics 365 Customer Engagement Web API]的[!DNL Microsoft]檔案。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td> <p>輸入相對於<code>&lt;Instance URL>/api/data/v9.1/</code>的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> <p>有關詳細資訊</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 為您新增授權標頭。</p> </td> 
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

### [!UICONTROL Delete Record]

此動作模組會刪除實體。

您可以指定實體的ID。

模組會傳回實體ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td> <p>選取您要讓模組刪除的實體型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>輸入或對應您要模組刪除之記錄的唯一[!DNL Microsoft Dynamics 365]識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Read Records]

此動作模組從[!DNL Microsoft Dynamics 365]中的單一實體讀取資料。

您可以指定實體的ID。

模組會傳回實體ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您希望模組讀取的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>輸入或對應您要模組讀取之記錄的唯一[!DNL Microsoft Dynamics 365]識別碼。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Update Record]

此動作模組會更新實體。

您可以指定實體的ID。

模組會傳回更新記錄的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您希望模組更新的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Select Fields to Map]</td> 
   <td>選取建立記錄時您想要包含值的欄位。 可用欄位取決於實體型別。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL Property fields]</td> 
   <td>這些是您選取的欄位。 輸入您要讓記錄擁有指定屬性的值。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>輸入或對應您要模組更新的記錄的唯一[!DNL Microsoft Dynamics] 365 ID。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Search Records]

此搜尋模組會在[!DNL Microsoft Dynamics 365]中尋找符合您指定之搜尋查詢的物件記錄。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Microsoft Dynamics 365]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-dynamics-365-to-workfront-fusion" class="MCXref xref">將[!DNL Microsoft Dynamics 365]連線到[!DNL Workfront Fusion]</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Entity Type]</td> 
   <td>選取您希望模組更新的實體型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filters]</td> 
   <td> <p>選取要用於此搜尋的篩選器。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Standard Filters]</strong> </p> <p>選取欄位和運運算元，然後輸入或對應您要搜尋的值，以設定篩選。 您可以使用AND或OR規則來篩選篩選器。</p> </li> 
     <li> <p><strong>[!UICONTROL Query Functions]</strong> </p> <p>輸入您要用來搜尋的[!DNL Dynamics 365]網頁API查詢函式。 </p> <p>如需查詢函式的詳細資訊，請參閱[!DNL Microsoft]檔案中的<a href="https://docs.microsoft.com/en-us/dynamics365/customer-engagement/web-api/queryfunctions?view=dynamics-ce-odata-9">Web API查詢函式參考</a>。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort]</td> 
   <td> <p>指定專案傳回的順序。 您可以新增多個排序。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Field]</strong> </p> <p>指定您要排序結果的欄位。</p> </li> 
     <li> <p><strong>[!UICONTROL Direction]</strong> </p> <p>指定排序方向（升序或降序）。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max Records]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
 </tbody> 
</table>

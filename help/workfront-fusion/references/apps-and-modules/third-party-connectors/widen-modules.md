---
title: 加寬模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動處理使用[!UICONTROL Widen]的工作流程，以及將其連線到多個協力廠商應用程式和服務。
author: Becky
draft: Probably
feature: Workfront Fusion
exl-id: 11376e58-a44b-4766-85dc-e2421b0112de
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 1%

---

# [!DNL Widen]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!UICONTROL Widen]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!UICONTROL Widen]模組，您必須有[!UICONTROL Widen]帳戶。

## 擴充API資訊

「加寬」聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.10.11</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Widen]連線至[!DNL Workfront Fusion] {#connect-widen-to-workfront-fusion}

您可以直接從[!DNL Widen]模組內建立與您的[!DNL Widen]帳戶的連線。

1. 在任何[!DNL Widen]模組中，按一下[!UICONTROL Connection]欄位旁的&#x200B;**[!UICONTROL Add]**。
1. 選取您要連線的[!DNL Widen]網域。
1. 輸入您[!DNL Widen]帳戶的權杖。 如需尋找此Token的說明，請參閱[[!DNL Widen] API常見問題集](https://community.widen.com/collective/s/article/API-FAQs)。
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線，並返回模組。

## [!DNL Widen]模組及其欄位

當您設定[!DNL Widen]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Widen]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發模組](#trigger-modules)
* [動作模組](#action-modules)
* [搜尋模組](#search-modules)

### 觸發模組

#### [!UICONTROL Watch assets]

建立或更新資產時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event type]</td> 
   <td> <p>選取您要觀看新資產或更新資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>選取除了資產欄位之外，您還要納入模組輸出的屬性。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作模組

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Read asset info]](#read-asset-info)
* [[!UICONTROL Add assets to collections]](#add-assets-to-collections)
* [[!UICONTROL Remove assets from collection]](#remove-assets-from-collection)
* [[!UICONTROL Update asset metadata]](#update-asset-metadata)
* [[!UICONTROL Download File]](#download-file)
* [[!UICONTROL Upload]檔案](#upload-a-file)

#### [!UICONTROL Custom API Call]

此動作模組可讓您對[!DNL Widen] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Widen]模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API Version]</td> 
   <td>選取您要使用最新版的[!DNL Widen] API，還是1.0版</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入或對應您API呼叫的URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] 為您新增授權標頭。</p> </td> 
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

#### [!UICONTROL Read asset info]

此動作模組會透過其唯一ID擷取個別資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>輸入或對應您要讀取資訊之資產的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>選取除了資產欄位之外，您還要納入模組輸出的屬性。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add assets to collections]

此動作模組會將一個或多個資產新增至收藏集。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td> <p>針對您想要新增資產的每個集合：</p> 
    <ol> 
     <li value="1"> <p> 按一下<strong>[!UICONTROL Add]</strong>。</p> </li> 
     <li value="2"> <p>輸入或對應[!UICONTROL Collection ID]。</p> </li> 
     <li value="3"> <p>按一下<strong>[!UICONTROL Add item]</strong>。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Assets ID]</td> 
   <td> <p>針對您想要新增至集合的每個資產：</p> 
    <ol> 
     <li value="1"> <p> 按一下<strong>[!UICONTROL Add]</strong>。</p> </li> 
     <li value="2"> <p>輸入或對映資產ID。</p> </li> 
     <li value="3"> <p>按一下<strong>[!UICONTROL Add item]</strong>。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove assets from collection]

此動作模組會從集合中移除一或多個資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collections ID]</td> 
   <td> <p>針對您想要從中移除資產的每個集合：</p> 
    <ol> 
     <li value="1"> <p> 按一下<strong>[!UICONTROL Add]</strong>。</p> </li> 
     <li value="2"> <p>輸入或對應「集合ID」。</p> </li> 
     <li value="3"> <p>按一下<strong>[!UICONTROL Add item]</strong>。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ASSETS ID</td> 
   <td> <p>針對您要從集合中移除的每個資產：</p> 
    <ol> 
     <li value="1"> <p> 按一下<strong>[!UICONTROL Add]</strong>。</p> </li> 
     <li value="2"> <p>輸入或對映資產ID。</p> </li> 
     <li value="3"> <p>按一下<strong>[!UICONTROL Add item]</strong>。</p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update asset metadata]

此動作模組會更新資產的中繼資料欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>輸入或對應您要更新中繼資料的資產ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata type]</td> 
   <td> <p>選取您要更新之中繼資料的中繼資料型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>選取您要更新的中繼資料欄位。 針對每個欄位，輸入欄位的新值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應每個案例執行週期中您希望模組使用的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Download File]

此動作模組會從您的[!DNL Widen]帳戶下載資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID]</td> 
   <td> <p>輸入或對應您要下載的資產識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

此動作模組會將檔案上傳到您的[!DNL Widen]帳戶。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Profile]</td> 
   <td> <p>選取您要模組使用的上傳設定檔。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Upload Method]</td> 
   <td> <p>選取您要如何上傳檔案。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL From File]</strong> </p> <p>從上一個模組選取或對應來源檔案。</p> </li> 
     <li> <p><strong>[!UICONTROL By URL]</strong> </p> <p>輸入或對應您要上傳之檔案的URL。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File name]</td> 
   <td>輸入或對應已上傳檔案的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata Type]</td> 
   <td>選取您要上傳之檔案的中繼資料型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Metadata]</td> 
   <td>選取要包含在檔案上載中的中繼資料欄位。 對於每個欄位，輸入欄位的[!UICONTROL value]。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋模組

* [[!UICONTROL Read collection assets]](#read-collection-assets)
* [[!UICONTROL Search assets]](#search-assets)

#### [!UICONTROL Read collection assets]

此動作模組會擷取集合中的資產清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Collection ID]</td> 
   <td> <p>輸入或對應包含您要讀取之資產的集合ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start]</td> 
   <td>輸入或對映您要列出的第一個專案編號。 這是分頁記錄的方式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Max]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>選取您要用來排序資產的屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>選取您要以遞增或遞減方式排序資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search assets]

此搜尋模組會擷取符合特定搜尋條件的資產清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
  <td> <p>如需有關將您的[!DNL Widen]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-widen-to-workfront-fusion" class="MCXref xref">將[!DNL Widen]連線到[!DNL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search query]</td> 
   <td> <p>輸入您要搜尋資產的條件。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sort By]</td> 
   <td> <p>選取您要如何排序資產。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order]</td> 
   <td>選取您要以遞增或遞減方式排序資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Include deleted]</td> 
   <td>啟用此選項以在搜尋中包含已刪除的資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Include archived]</p> </td> 
   <td> <p>啟用此選項以在搜尋中包含已封存的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Search document text]</td> 
   <td>啟用此選項可在搜尋中包含檔案文字，或啟用為假以僅包含標題符合搜尋條件的資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Offset]</td> 
   <td>輸入或對應您要擷取其詳細資訊的第一個專案編號。 這是分頁記錄的方式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scroll]</td> 
   <td>啟用此選項以允許捲動。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Expand]</td> 
   <td> <p>選取除了資產欄位之外，您還要納入模組輸出的屬性。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
 </tbody> 
</table>

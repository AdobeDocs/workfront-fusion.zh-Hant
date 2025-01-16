---
title: Split.io模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動化使用 [!DNL Split.io]的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 7d738a96-5424-4c30-831f-82e1d4c6f9d2
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 0%

---

# [!DNL Split.io]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Split.io]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!DNL Split.io]模組，您必須有[!DNL Split.io]帳戶。

## Split.io API資訊

Split.io聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://api.split.io/internal/api</td>
   </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.34.1</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Split.io]連線至[!DNL Workfront Fusion] {#connect-split-io-to-workfront-fusion}

您可以直接從[!DNL Split.io]模組內建立與您的[!DNL Split.io]帳戶的連線。

1. 在任何[!DNL Split.io]模組中，按一下[!UICONTROL Connection]欄位旁的&#x200B;**[!UICONTROL Add]**。
1. 輸入連線的名稱。
1. 輸入您的[!DNL Split.io] API金鑰。

   如需[!DNL Split.io] API金鑰的詳細資訊，請參閱[!DNL Split.io]檔案中的[API金鑰](https://help.split.io/hc/en-us/articles/360019916211-API-keys)。

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線，並返回模組。

## [!DNL Split.io]模組及其欄位

當您設定[!DNL split.io]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL split.io]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [搜尋](#searches)

### 動作

* [[!UICONTROL Custom API Call]](#custom-api-call)
* [[!UICONTROL Get Split]](#get-split)
* [[!UICONTROL Get Split Definition in Environment]](#get-split-definition-in-environment)
* [[!UICONTROL Create Split]](#create-split)
* [[!UICONTROL Delete Split]](#delete-split)
* [[!UICONTROL Create Split Definition in Environment]](#create-split-definition-in-environment)
* [[!UICONTROL Remove Split Definition from Environment]](#remove-split-definition-from-environment)
* [[!UICONTROL Partial Update Split Definition in Environment]](#partial-update-split-definition-in-environment)
* [[!UICONTROL Associate Tags]](#associate-tags)

#### [!UICONTROL Custom API Call]

此動作模組可讓您對[!DNL split.io] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL split.io]模組無法完成的資料流程自動化。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>https://api.split.io/internal/api/v2/</code>的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱[!DNL Adobe Workfront Fusion]</a>中的<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法。</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中處理的最大記錄數量。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split]

此動作模組會擷取拆分。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要擷取之分割的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>輸入或對映您要擷取的分割名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Split Definition in Environment]

此動作模組會從指定的環境中擷取特定的分割定義。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要擷取之分割定義的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>選取或對應包含您要擷取之分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>輸入或對應您要擷取分割定義的分割名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split]

在指定流量型別時，此動作模組會在您的組織中建立新的分割。

>[!NOTE]
>
>API不會在任何環境中設定分割。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應您要建立分割的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Traffic Type ID or Name]</td> 
   <td>選取或對應您要用來建立分割的流量型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>輸入或對應您要建立的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Description]</td> 
   <td>輸入或對應您要建立的分割的[!UICONTROL split]描述。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Split]

此動作模組會從您的組織刪除分割。 這會從所有環境中自動取消設定分割定義。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應您要刪除分割的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>輸入或對映您要刪除的分割名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Split Definition in Environment]

此動作模組會為特定環境設定分割定義。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應您要建立分割定義的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>選取或對應您要建立分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>輸入或對應您要建立定義的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>輸入或對應您要新增至分割定義的任何註解。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Rules]</td> 
   <td> <p>針對您想要新增至定義的每個目標規則，按一下<b>[!UICONTROL Add item]</b>，然後輸入或對應規則。</p> <p>如需鎖定目標規則的詳細資訊，請參閱[!DNL Split.io]檔案中的<a href="https://docs.split.io/reference#create-split-definition-in-environment">在環境中建立分割定義</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default rule]</td> 
   <td> <p>輸入或對映您要分割用於不符合其他規則規格的流量的規則。</p> <p>如需鎖定目標規則的詳細資訊，請參閱[!DNL Split.io]檔案中的<a href="https://docs.split.io/reference#create-split-definition-in-environment">在環境中建立分割定義</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Default treatment]</td> 
   <td> <p>輸入或對應分割要使用的處理方式（如果分割已終止或客戶未包含在流量分配中）。</p> <p>如需處理的詳細資訊，請參閱[!DNL Split.io]檔案中的<a href="https://docs.split.io/reference#create-split-definition-in-environment">在環境中建立分割定義</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Treatments]</td> 
   <td> <p>針對您想要新增至定義的每個處理，按一下<b>[!UICONTROL Add item]</b>，然後輸入或對應處理。</p> <p>如需處理的詳細資訊，請參閱[!DNL Split.io]檔案中的<a href="https://docs.split.io/reference#create-split-definition-in-environment">在環境中建立分割定義</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Remove Split Definition from Environment]

此動作模組會取消設定特定環境的分割定義。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應您要移除分割定義的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>選取或對應您要移除分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>輸入或對應您要移除其定義的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>輸入或對應您要新增至分割定義的任何註解。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Partial Update Split Definition in Environment]

此動作模組會更新特定環境的分割定義。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應您要更新分割定義的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>選取或對應您要更新分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Split Name]</td> 
   <td> <p>輸入或對應您要更新其定義的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Update content]</td> 
   <td> <p>針對您要更新的每個分割屬性，按一下<b>[!UICONTROL Add item]</b>並輸入或對應所需的變更。</p> <p>如需詳細資訊，請參閱[!DNL Split.io]檔案中的<a href="https://docs.split.io/reference#partial-update-split-definition-in-environment">環境</a>中的部分更新分割定義。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comments]</td> 
   <td>輸入或對應您要新增至分割定義的任何註解。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Associate Tags]

此動作模組會將標籤新增至指定的物件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應您要新增標籤的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Name]</td> 
   <td>輸入或對應您要新增標籤的物件名稱，</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Object Type]</td> 
   <td> <p>輸入或對應您要新增標籤的物件型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Tags]</td> 
   <td> <p>針對您要新增的每個標籤，按一下<b>[!UICONTROL Add item]</b>並輸入或對應標籤。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL Get Workspaces]](#get-workspaces)
* [[!UICONTROL Get Environments]](#get-environments)
* [[!UICONTROL Get Splits]](#get-splits)
* [[!UICONTROL List Split Definitions in an Environment]](#list-split-definitions-in-an-environment)
* [[!UICONTROL Get Traffic Types]](#get-traffic-types)

#### [!UICONTROL Get Workspaces]

此搜尋模組會擷取組織的工作區。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中擷取的最大工作區數量。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Environments]

此搜尋模組會擷取環境清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要列出之環境的工作區。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Splits]

此搜尋模組會擷取分割清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對映包含您要列出之分割的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中擷取的最大分割數。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Split Definitions in an Environment]

此搜尋模組會擷取指定環境中分割定義的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要列出之分割定義的工作區。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Environment Name or ID]</td> 
   <td>選取或對應包含您要列出之分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中擷取的最大分割定義數目。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Traffic Types]

此搜尋模組會擷取流量型別清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Split.io]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-split-io-to-workfront-fusion" class="MCXref xref">將[!DNL Split.io]連線到[!UICONTROL Workfront Fusion] </a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要列出之流量型別的工作區。</td> 
  </tr> 
 </tbody> 
</table>

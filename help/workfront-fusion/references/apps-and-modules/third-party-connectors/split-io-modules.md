---
title: Split.io模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動化使用 [!DNL Split.io]的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 7d738a96-5424-4c30-831f-82e1d4c6f9d2
source-git-commit: 25d98999eb99e8d842333a1c87b4b0600447b2f5
workflow-type: tm+mt
source-wordcount: '1873'
ht-degree: 0%

---

# [!DNL Split.io]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Split.io]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

1. 在任何[!DNL Split.io]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 填寫下列欄位。

   <table style="table-layout:auto"> 
     <col> 
     <col> 
     <tbody> 
      <tr> 
       <td role="rowheader">[!UICONTROL 連線名稱]</td> 
       <td> <p>輸入連線的名稱。</p> </td> 
      </tr> 
      <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>
          <p>選取要連線到生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 型別]</td>
        <td>
          <p>選取您要連線到服務帳戶還是個人帳戶。</p>
        </td>
      </tr>
      <tr> 
       <td role="rowheader">[!UICONTROL API金鑰]</td> 
       <td>輸入您的[!DNL Split.io] API金鑰。<p>如需[!DNL Split.io] API金鑰的詳細資訊，請參閱[!DNL Split.io]檔案中的<a href="https://help.split.io/hc/en-us/articles/360019916211-API-keys">API金鑰</a>。</p></td> 
      </tr> 
     </tbody> 
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

## [!DNL Split.io]模組及其欄位

當您設定[!DNL split.io]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL split.io]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [搜尋](#searches)

### 動作

* [[!UICONTROL 關聯標籤]](#associate-tags)
* [[!UICONTROL 建立分割]](#create-split)
* [[!UICONTROL 在環境中建立分割定義]](#create-split-definition-in-environment)
* [[!UICONTROL 自訂API呼叫]](#custom-api-call)
* [[!UICONTROL 刪除分割]](#delete-split)
* [[!UICONTROL 取得分割]](#get-split)
* [[!UICONTROL 在環境中取得分割定義]](#get-split-definition-in-environment)
* [[!UICONTROL 在環境中部分更新分割定義]](#partial-update-split-definition-in-environment)
* [[!UICONTROL 從環境中移除分割定義]](#remove-split-definition-from-environment)

#### [!UICONTROL 關聯標籤]

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
   <td role="rowheader">[!UICONTROL 物件名稱]</td> 
   <td>輸入或對應您要新增標籤的物件名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 物件型別]</td> 
   <td> <p>輸入或對應您要新增標籤的物件型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td> <p>針對您要新增的每個標籤，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應標籤。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立分割]

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
   <td role="rowheader">[!UICONTROL 流量型別ID或名稱]</td> 
   <td>選取或對應您要用來建立分割的流量型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 分割名稱]</td> 
   <td> <p>輸入或對應您要建立的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 分割說明]</td> 
   <td>為您要建立的分割輸入或對映[!UICONTROL split]說明。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 在環境中建立分割定義]

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
   <td role="rowheader">[!UICONTROL 環境名稱或ID]</td> 
   <td>選取或對應您要建立分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 分割名稱]</td> 
   <td> <p>輸入或對應您要建立定義的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解]</td> 
   <td>輸入或對應您要新增至分割定義的任何註解。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 規則]</td> 
   <td> <p>針對您想要新增至定義的每個目標規則，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應規則。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 預設規則]</td> 
   <td> <p>輸入或對映您要分割用於不符合其他規則規格的流量的規則。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 預設處理]</td> 
   <td> <p>輸入或對應分割要使用的處理方式（如果分割已終止或客戶未包含在流量分配中）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Threads]</td> 
   <td> <p>針對您想要新增至定義的每個處理，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應處理和大小。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂API呼叫]

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
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
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
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中處理的最大記錄數量。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除分割]

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
   <td role="rowheader">[!UICONTROL 分割名稱]</td> 
   <td> <p>輸入或對映您要刪除的分割名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得分割]

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
   <td role="rowheader">[!UICONTROL 分割名稱]</td> 
   <td> <p>輸入或對映您要擷取的分割名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 在環境中取得分割定義]

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
   <td role="rowheader">[!UICONTROL 環境名稱或ID]</td> 
   <td>選取或對應包含您要擷取之分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 分割名稱]</td> 
   <td> <p>輸入或對應您要擷取分割定義的分割名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 在環境中部分更新分割定義]

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
   <td role="rowheader">[!UICONTROL 環境名稱或ID]</td> 
   <td>選取或對應您要更新分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 分割名稱]</td> 
   <td> <p>輸入或對應您要更新其定義的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 更新內容]</td> 
   <td> <p>針對您要更新的分割的每個屬性，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應所需的變更。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解]</td> 
   <td>輸入或對應您要新增至分割定義的任何註解。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 從環境中移除分割定義]

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
   <td role="rowheader">[!UICONTROL 環境名稱或ID]</td> 
   <td>選取或對應您要移除分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 分割名稱]</td> 
   <td> <p>輸入或對應您要移除其定義的分割名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解]</td> 
   <td>輸入或對應您要新增至分割定義的任何註解。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 關聯標籤]

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
   <td role="rowheader">[!UICONTROL 物件名稱]</td> 
   <td>輸入或對應您要新增標籤的物件名稱，</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 物件型別]</td> 
   <td> <p>輸入或對應您要新增標籤的物件型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td> <p>針對您要新增的每個標籤，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應標籤。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL 取得環境]](#get-environments)
* [[!UICONTROL 取得流量型別]](#get-traffic-types)
* [[!UICONTROL 取得工作區]](#get-workspaces)
* [[!UICONTROL 列出環境中的分割定義]](#list-split-definitions-in-an-environment)
* [[!UICONTROL 清單分割]](#list-splits)

#### [!UICONTROL 取得環境]

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

#### [!UICONTROL 取得流量型別]

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

#### [!UICONTROL 取得工作區]

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
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中擷取的最大工作區數量。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出環境中的分割定義]

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
   <td role="rowheader">[!UICONTROL 環境名稱或ID]</td> 
   <td>選取或對應包含您要列出之分割定義的環境。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中擷取的最大分割定義數目。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清單分割]

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
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中擷取的最大分割數。</td> 
  </tr> 
 </tbody> 
</table>

---
title: Microsoft Dynamics 365財務與營運模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Microsoft Dynamics 365 Finance and Operations的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 96f8d4f1-f97b-4da8-8d82-83cccb54ec68
TQID: https://experienceleague.adobe.com/MSvJMXg8hyI8piqHpn1OnEPEoCcP1Tn-za1veFtHeIo
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1147
ht-degree: 39%

---

# [!DNL Microsoft Dynamics 365 Finance and Operations modules]

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Microsoft Dynamics 365] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

>[!NOTE]
>
>[!DNL Microsoft Dynamics 365 Finance and Operations]聯結器不支援[!DNL Dynamics 365]。
>
>若為Microsoft Dynamics 365模組，請參閱[[!DNL Microsoft Dynamics 365 modules]](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md)。



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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++



## 建立連線

若要建立Microsoft Dynamics 365 Finance and Operations模組的連線：

1. 在任何Microsoft Dynamics 365 Finance and Operations模組中，按一下[連線]方塊旁的[新增]。**&#x200B;**

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL 連線類型]</td>
        <td>
          <p>選取您要建立標準的Dynamics Finance and Operations連線，或使用授權碼建立連線。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的Dynamics Finance and Operations [!UICONTROL 使用者端ID]。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的Dynamics Finance and Operations [!UICONTROL 使用者端密碼]。 </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 租使用者ID]</td>
        <td>輸入您的Dynamics Finance and Operations租使用者ID。</td>
        </tr>
        <tr>
        <td role="rowheader">資源</td>
        <td>輸入Dynamics Finance and Operations帳戶的URL （不含https://）</td>
        </tr>
      </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。



## Microsoft Dynamics 365 Finance and Operations模組及其欄位

>[!IMPORTANT]
>
>透過Dynamics 365 F&amp;O API提供的資料實體可能會因執行個體而異。 如果您不確定哪些實體可透過API使用，則使用「data」端點來檢視例項中的實體會很有用。 Dynamics 365 Finance and Operations中的「資料」端點是用於存取OData服務的根URL。 此端點可讓您使用標準OData通訊協定，與系統公開的各種資料實體互動。
>
>您可以使用自訂API呼叫模組擷取這些實體。
>
><!--For more information -->



### 建立實體專案

此動作模組會在Microsoft Dynamics 365 Finance and Operations中建立新的實體專案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL 連線]</td>
    <td> <p>如需有關將Microsoft Dynamics 365 Finance and Operations連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref">建立連線</a>。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 實體]</td>
     <td>輸入或對應您要建立的Dynamics Finance and Operations實體型別。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 正文]</td>
     <td> <p>輸入或對應包含您要納入新實體專案之資料的JSON內文。</p> </td> 
  </tr> 
 </tbody> 
</table>



### 刪除實體專案

此動作模組會從Dynamics Finance and Operations刪除實體專案。 專案由其主索引鍵欄位識別。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL 連線]</td>
    <td> <p>如需有關將Microsoft Dynamics 365 Finance and Operations連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref">建立連線</a>。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 實體]</td>
     <td>輸入或對應您要刪除的Dynamics Finance and Operations實體型別。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 主鍵欄位]</td>
     <td> 主索引鍵欄位可識別專案。 針對您想要提供的每個主索引鍵欄位，按一下<b>新增專案</b>，然後輸入或對應識別該專案的唯一索引鍵和值。 </td> 
  </tr> 
 </tbody> 
</table>

### 進行自訂的 API 呼叫

此動作模組會對Dynamics Finance and Operations API進行自訂呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
    <td> <p>如需有關將Microsoft Dynamics 365 Finance and Operations連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref">建立連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>輸入相對於Dynamics Finance and Operations URL的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。 此資訊會決定請求的內容類型。</p> <p>例如，<code> {"Content-type":"application/json"}</code></p> <p>注意：如果您收到錯誤訊息而且無法判斷其來源，請考慮根據 Workfront 文件修改標頭。 如果您的自訂 API 呼叫傳回 422 HTTP 要求錯誤，請嘗試使用 <code>"Content-Type":"text/plain"</code> 標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> <p>提示：建議您透過 JSON 正文而非查詢參數傳送資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>



### 讀取實體專案

此動作模組會從實體專案傳回資料。 專案由其主索引鍵欄位識別。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL 連線]</td>
    <td> <p>如需有關將Microsoft Dynamics 365 Finance and Operations連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref">建立連線</a>。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 實體]</td>
     <td>輸入或對應您要讀取的Dynamics Finance and Operations實體型別。</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 主鍵欄位]</td>
     <td> 主索引鍵欄位可識別專案。 針對您想要提供的每個主索引鍵欄位，按一下<b>新增專案</b>，然後輸入或對應識別該專案的唯一索引鍵和值。 </td> 
  </tr> 
 </tbody> 
</table>

### 更新實體專案

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL 連線]</td>
    <td> <p>如需有關將Microsoft Dynamics 365 Finance and Operations連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection" class="MCXref xref">建立連線</a>。</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 實體]</td>
     <td>輸入或對應您要更新的Dynamics Finance and Operations實體型別。</td> 
  </tr>  
  <tr> 
    <td>[!UICONTROL 主鍵欄位]</td>
     <td> 主索引鍵欄位可識別專案。 針對您想要提供的每個主索引鍵欄位，按一下<b>新增專案</b>，然後輸入或對應識別該專案的唯一索引鍵和值。 </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL 正文]</td>
     <td> <p>輸入或對應包含您要納入新實體專案之資料的JSON內文。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

此搜尋模組會根據您指定的條件傳回結果。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 實體]</td> 
   <td>輸入或對應您要搜尋的Dynamics Finance and Operations實體型別。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 搜尋條件]</td> 
   <td> <p>輸入您要搜尋的欄位、要在查詢中使用的運算子，以及要在欄位中搜尋的值。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[!UICONTROL 排序依據]</td> 
   <td> <p>輸入或對應您要排序結果的欄位。</p> </td> 
  </tr> 
 </tbody> 
</table>


<!--

### List All

This module lists all records for a given entity.  The item is identified by its Primary key fields.

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td>[!UICONTROL Connection]</td>
    <td> <p>For instructions about connecting Microsoft Dynamics 365 Finance and Operations to Workfront Fusion, see <a href="#create-a-connection" class="MCXref xref">Create a connection</a> in this article.</p> </td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Record Type]</td>
     <td>Choose the Dynamics Finance and Operations entity type that you want the module to list.</td> 
  </tr> 
  <tr> 
    <td>[!UICONTROL Outputs]</td>
     <td> <p>Select the information you want included in the output bundle for this module.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Watch Record

This trigger module starts a scenario when a record of the given type is created or updated.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
    <td> <p>For instructions about connecting Microsoft Dynamics 365 Finance and Operations to Workfront Fusion, see <a href="#create-a-connection" class="MCXref xref">Create a connection</a> in this article.</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Record Type]</td> 
   <td> <p>Select the type of Workfront record that you want the module to watch.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>Enter the field that you want to search by, the operator you want to use in your query, and the value that you are searching for in the field.</p> <p>Note: Do not use <code>username </code>in your search criteria. Including <code>username </code>in an API query to Workfront logs the user into Workfront, and the search will not be successful.</p> <p>Note: <code>In</code> and <code>NotIn</code>work with arrays. The inputs should be in array format.</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>Select the information you want included in the output bundle for this module.</p> </td> 
  </tr> 
 </tbody> 
</table>

-->

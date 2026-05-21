---
filename: workday-modules
title: Workday 模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL Workday] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 77237a1b-2acd-4350-9cc0-ec43b8b08137
TQID: https://experienceleague.adobe.com/b-RlvqOsRRrFZMh8JrPFAS2pigkQP-6ugZ5kZl8AdZ8
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 1063
ht-degree: 52%

---

# [!DNL Workday] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Workday] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

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

## 先決條件

若要使用[!DNL Workday]模組，您必須：

* 擁有[!DNL Workday]帳戶。

* 在[!DNL Workday]中建立OAuth應用程式。 如需指示，請參閱[!DNL Workday]檔案。

## Workday API資訊

Workday聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td><pre><code>https://&#123;&#123;connection.servicesUrl&#125;&#125;/api</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.6.4</td> 
  </tr>
 </tbody> 
 </table>

## 將 [!DNL Workday] 連接至 Workfront Fusion

1. 在任何Workfront Fusion模組中，按一下[!UICONTROL 連線]欄位旁的[!UICONTROL 新增]

2. 填寫下列欄位：

   <table style="table-layout:auto"> 
        <col/>
        <col/>
        <tbody>
            <tr>
                <td role="rowheader">
                    <p role="rowheader">[!UICONTROL 連線名稱]</p>
                </td>
                <td>輸入此連線的名稱。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Workday主機]</td>
                <td>輸入不含<code>https://</code>的[!DNL Workday]主機位址。 例如: <code>mycompany.workday.com</code>。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 服務URL]</td>
                <td>輸入您的[!DNL Workday]網路服務位址（不含<code>https://</code>）。 例如: <code>mycompany-services.workday.com</code>。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL 租使用者名稱稱]</td>
                <td>輸入此[!DNL Workday]帳戶的租使用者。 您的租使用者是您組織的識別碼，可在您用來登入Workday的URL中看見。 範例：在地址<code>https://www.myworkday.com/mycompany</code>中，租使用者是<code>mycompany</code>。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
                <td>輸入此連線使用的[!DNL Workday]應用程式的使用者端識別碼。 當您在[!DNL Workday]中建立應用程式時，就會取得此資訊。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL 用戶端密碼]</td>
                <td>輸入此連線使用的[!DNL Workday]應用程式的使用者端密碼。 當您在[!DNL Workday]中建立應用程式時，就會取得此資訊。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 工作階段逾時（分鐘）]</td>
                <td >輸入您的授權Token過期的分鐘數。</td>
            </tr>
        </tbody>
    </table>


3. 按一下[!UICONTROL 繼續]以儲存連線並返回模組

## [!DNL Workday] 模組及其欄位

當您設定 [!DNL Workday] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Workday] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#action)

* [搜尋](#search)


### 動作

* [[!UICONTROL 建立記錄]](#create-a-record)

* [[!UICONTROL 刪除記錄]](#delete-a-record)

* [[!UICONTROL 進行自訂的 API 呼叫]](#make-a-custom-api-call)

* [[!UICONTROL 更新記錄]](#update-a-record)


#### [!UICONTROL 建立記錄]

此動作模組會在[!DNL Workday]中建立單一記錄。

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL 連線]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到Workfront Fusion</a>。</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄類型]</td>
            <td>選取您要建立的記錄類型。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>輸入或對應您要建立的記錄ID。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 子資源ID]</td>
            <td >輸入或對應您要建立之子資源的ID。</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除[!DNL Workday]中的單一記錄。

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL 連線]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到Workfront Fusion</a>。</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄類型]</td>
            <td>選取您要刪除的記錄型別。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 特定記錄型別]</td>
            <td>選取您要刪除的特定記錄型別。 這些是以您選擇的記錄型別為基礎。</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 子資源ID]</td>
            <td>輸入或對應您要刪除之子資源的ID。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >輸入或對應您要刪除之記錄的ID。</td>
        </tr>
    </tbody>
</table>


### [!UICONTROL 進行自訂的 API 呼叫]

您可以利用此動作模組，對 [!DNL Workday] API 進行已驗證的自訂呼叫。 如此一來，您就可以建立其他 [!DNL Workday] 模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

模組會傳回a狀態代碼，以及API呼叫的標題和正文。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Connection]</p> </td> 
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到Workfront Fusion</a>。</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於 <code style="color: #ff1493;">https://&lt;tenantHostname>/api/&lt;serviceName>/&lt;version>/&lt;tenant></code> 的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] 會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
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

#### [!UICONTROL 更新記錄]

此動作模組更新[!DNL Workday]中的單一記錄。

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL 連線]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >[!UICONTROL 連線[!DNL Workday]到Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄類型]</td>
            <td>選取您要更新的記錄型別。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>輸入或對應您要更新之記錄的 ID。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 子資源ID]</td>
            <td >輸入或對應您要更新的子資源ID。</td>
        </tr>
    </tbody>
</table>

### 搜尋

* [[!UICONTROL 讀取記錄]](#read-a-record)

* [[!UICONTROL 清單記錄]](#list-records)


#### [!UICONTROL 讀取記錄]

此動作模組會讀取單一記錄。

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL 連線]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >[!UICONTROL 連線[!DNL Workday]到Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄類型]</td>
            <td>選取您要刪除的記錄型別。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 特定記錄型別]</td>
            <td>選取您要讀取的特定記錄型別。 這些是以您選擇的記錄型別為基礎。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >輸入或對應您要刪除之記錄的ID。</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL 清單記錄]

此搜尋模組會擷取指定型別的記錄清單。

<table style="table-layout:auto"> 
      <col/>
      <col/>
      <tbody>
          <tr>
              <td role="rowheader">[!UICONTROL 連線]</td>
              <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到Workfront Fusion</a></td>
          </tr>
          <tr>
              <td  role="rowheader">[!UICONTROL 記錄類型]</td>
              <td>選取您要擷取的記錄型別。</td>
          </tr>
          <tr>
              <td role="rowheader">[!UICONTROL 限制]</td>
              <td >
                  <p>輸入或對應您希望模組在每個案例執行週期中擷取的記錄數上限。</p>
              </td>
          </tr>
      </tbody>
  </table>

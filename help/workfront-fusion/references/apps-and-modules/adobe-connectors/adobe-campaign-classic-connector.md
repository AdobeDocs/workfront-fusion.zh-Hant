---
title: Adobe Campaign v7/v8模組
description: 透過 [!DNL Adobe Campaign] 模組，您可以根據 [!DNL Adobe Campaign] 帳戶中的事件來啟動Adobe Workfront Fusion案例、建立、讀取或更新合約及其他記錄、使用您設定的條件搜尋記錄，以及上傳檔案。
author: Becky
feature: Workfront Fusion
exl-id: 9fdff26c-c7c0-4eb8-a36f-4aeaf432b333
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 1%

---

# [!DNL Adobe Campaign]模組

透過[!DNL Adobe Campaign]模組，您可以根據[!DNL Adobe Campaign v7/v8]帳戶中的事件啟動Adobe Workfront Fusion案例、建立、讀取或更新記錄、使用您設定的條件搜尋記錄，以及執行自訂API呼叫。

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

您必須將Fusion IP位址新增到[!DNL Adobe Campaign]。

* 如需將IP位址新增至您的Campaign允許清單的指示，請參閱Adobe Campaign檔案中的[將IP位址新增至允許清單](https://experienceleague.adobe.com/en/docs/control-panel/using/sftp-management/ip-range-allow-listing#adding-ip-addresses-allow-list)。
* 如需新增至允許清單的IP位址清單，請參閱貴組織的允許清單[中的](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)設定Fusion的IP位址。

## Adobe Campaign API資訊

Adobe Campaign聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.7.22</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Adobe Campaign]連線至Adobe Workfront Fusion

>[!IMPORTANT]
>
>我們強烈建議您建立伺服器對伺服器連線。 Adobe Campaign已更新其API，僅接受伺服器對伺服器連線。 如果您要連線至Campaign 8或更新版本，則&#x200B;**必須**&#x200B;建立伺服器對伺服器連線。
>
>如需有關Campaign新連線需求的詳細資訊，請參閱Campaign檔案中的[將Campaign技術運運算元移轉至Adobe Developer Console](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/ims-migration.html)。

1. 在任何[!DNL Adobe Campaign]模組中，按一下&#x200B;**[!UICONTROL 連線]**&#x200B;欄位旁的[!UICONTROL 新增]。
1. 填寫下列欄位：
   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL 連線型別]</td>
          <td>
            <p>選擇您要建立基本連線還是伺服器對伺服器連線。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 連線名稱]</td>
          <td>
            <p>輸入此連線的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 基底URL]</td>
          <td>輸入您用來連線至[!DNL Adobe Campaign]執行個體的基底URL。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 使用者名稱]</td>
          <td>如果您要建立基本連線，請輸入您的Adobe Campaign使用者名稱。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 密碼]</td>
          <td>如果您要建立基本連線，請輸入您的Adobe Campaign密碼。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 使用者端ID]</td>
          <td>如果您正在建立伺服器對伺服器連線，請輸入您的[!DNL Adobe] [!UICONTROL 使用者端ID]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
          <td>如果您正在建立伺服器對伺服器連線，請輸入您的[!DNL Adobe] [!UICONTROL 使用者端密碼]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。
        </tr>
     </tbody>
    </table>
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

## [!DNL Adobe Campaign]模組及其欄位

當您設定[!DNL Adobe Campaign]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe Campaign]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

<!--* [Triggers](#triggers)-->
* [動作](#actions)
* [搜尋](#searches)

<!--### Triggers

#### [!UICONTROL Watch records]

This scheduled trigger module starts a scenario when a record changes.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Adobe Campaign], see <a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >Create a connection to [!DNL Adobe Campaign]</a> in this article.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>Select whether you want to watch for new records, updated records, or both.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Resource]</td> 
   <td>Select the resource that you want to watch for.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields to include in output]</td> 
   <td>Select the fields that you want to include in the module's output.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields to include in output]</td> 
   <td>For each custom field that you want to include in output, click <b>[!UICONTROL Add]</b> and enter the name of the custom field.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned results]</td> 
   <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> 
  </tr> 
 </tbody> 
</table>-->


### 動作

* [[!UICONTROL 建立記錄]](#create-a-record)
* [[!UICONTROL 刪除記錄]](#delete-record)
* [[!UICONTROL 進行自訂API呼叫]](#make-a-custom-api-call)
* [[!UICONTROL 執行動作]](#perform-an-action)
* [[!UICONTROL 讀取記錄]](#read-a-record)
* [[!UICONTROL 訂閱或取消訂閱]](#subscribe-or-unsubscribe)
* [[!UICONTROL 更新記錄]](#update-record)

#### [!UICONTROL 建立記錄]

此動作模組會在[!DNL Adobe Campaign]中建立新記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資源]</td> 
   <td>選取您要建立的[!DNL Adobe Campaign]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位] </td> 
   <td>選取建立記錄時您想要設定值的欄位，然後填寫這些欄位的值。 欄位會依您選取的記錄型別而有所不同。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 自訂欄位]</td> 
   <td> 針對您想要新增至新記錄的每個自訂欄位，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應欄位的名稱和值。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會從[!DNL Adobe Campaign]刪除單一記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資源]</td> 
   <td>選取您要刪除的資源型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>輸入或對應您要刪除之資源的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行自訂API呼叫]

此模組會對[!DNL Adobe Campaign] API發出自訂API呼叫

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 動作]</td>
      <td><p>選取您希望API呼叫執行的動作。</p>
      <p>[!UICONTROL 執行查詢]</p>
      <p>[!UICONTROL 寫入]</p>
      <p>[!UICONTROL Get entity if more recent]</p>
      <p>[!UICONTROL 全選]</p>
      <p>[!UICONTROL 推送事件]</p>
    </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會自動新增[!UICONTROL x-security]權杖標題。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL XML Body]</td>
   <td> <p>以XML新增API呼叫的內文內容，而不使用工作階段元素。 </td>     </tr>
  </tbody>
</table>


#### [!UICONTROL 執行動作]

此動作模組會對[!DNL Adobe Campaign] API中的物件執行選取的動作。

如需特定動作和欄位的詳細資訊，請參閱[[!DNL Adobe Campaign] - API檔案](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html)。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 動作]</td> 
   <td><p>選取要在物件上執行的動作。</p>
   <ul>
   <li><p><b>[!DNL List]</b></p><p> 如需可用欄位，請參閱本文中的<a href="#search" class="MCXref xref" >[!UICONTROL 搜尋]</a>。 </p></li>
     <li><p><b>[!UICONTROL Get]</b></p><p> 如需可用欄位，請參閱本文中的<a href="#search" class="MCXref xref" >[!UICONTROL 搜尋]</a>。 </p></li> 
   <li><p><b>[!UICONTROL 建立]</b></p><p> 如需可用欄位，請參閱本文中的<a href="#create-a-record" class="MCXref xref" >[!UICONTROL 建立記錄]</a>。 </p></li>
   <li><p><b>[!UICONTROL 更新]</b></p><p> 如需可用欄位，請參閱本文中的<a href="#update-record" class="MCXref xref" >[!UICONTROL 更新記錄]</a>。 </p></li>
   <li><p><b>[!UICONTROL Delete]</b></p><p> 如需可用欄位，請參閱本文中的<a href="#delete-record" class="MCXref xref" >[!UICONTROL 刪除記錄]</a>。 </p></li>
   </ul>
   </td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組從[!DNL Adobe Campaign]讀取記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資源]</td> 
   <td>選取您要讀取的[!DNL Adobe Campaign]記錄型別。</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>輸入對應您要讀取之記錄的ID。</td> 
  </tr> 
 <tr> 
   <td role="rowheader">要包含在輸出中的[!UICONTROL 欄位] </td> 
   <td>選取您要納入模組輸出的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 要包含在輸出中的自訂欄位]</td> 
   <td>對於要包含在輸出中的每個自訂欄位，按一下<b>[!UICONTROL 新增]</b>並輸入自訂欄位的名稱。</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL 訂閱或取消訂閱]

此動作模組會訂閱資訊服務的使用者或取消訂閱資訊服務的使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 訂閱或取消訂閱]</td> 
   <td>選取您要訂閱或取消訂閱資訊服務。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 服務名稱]</td> 
   <td>選取您要訂閱或取消訂閱的服務。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 收件者電子郵件地址] </td> 
   <td>輸入或對應您要訂閱或取消訂閱資訊服務之使用者的電子郵件地址。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組更新[!DNL Adobe Campaign]中的單一記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資源]</td> 
   <td>選取您要建立的[!DNL Adobe Campaign]記錄型別。</td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL ID] </td> 
   <td>輸入對應您要更新之記錄的ID。</td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL 欄位] </td> 
   <td>選取您要更新值的欄位，然後填寫這些欄位的值。 欄位會依您選取的記錄型別而有所不同。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 自訂欄位]</td> 
   <td> 針對您要更新的每個自訂欄位，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應欄位的名稱和值。 </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL 搜尋]

此搜尋模組會根據指定的條件傳回記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td>
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#connect-adobe-campaign-to-adobe-workfront-fusion" class="MCXref xref" >建立與[!DNL Adobe Campaign]</a>的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資源]</td> 
   <td>選取您要建立的[!DNL Adobe Campaign]記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋條件]</td> 
   <td>輸入您希望搜尋使用的欄位和值。 欄位視選取的資源而定。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>

---
title: Marketo模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動化使用 [!DNL Marketo]的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: da417ac7-e532-45f7-86d9-3643b5f9f203
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2165'
ht-degree: 0%

---

# [!DNL Marketo]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Marketo]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需Marketo聯結器的簡介影片，請參閱：

* [Marketo](https://video.tv.adobe.com/v/3427026/){target=_blank}

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

若要使用[!DNL Marketo]模組，您必須有[!DNL Marketo]帳戶。

## Marketo API資訊

Marketo聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.14.19</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Marketo]連線至Workfront Fusion {#connect-marketo-to-workfront-fusion}

您可以從任何[!DNL Marketo]模組內直接建立與您的[!DNL Marketo]帳戶的連線。

1. 在任何Marketo模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
        </td>
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
        <td role="rowheader">[!UICONTROL 帳戶/ Munchkin ID]</td>
        <td>
          <p>輸入您的[!DNL Marketo]帳戶或[!DNL Marketo] [!UICONTROL Munchkin] ID。 這是指派給您帳戶的基本URL或端點的唯一部分，您用來透過其[!UICONTROL REST] API存取[!DNL Marketo]。 如需尋找此位置的指示，請參閱[!DNL Marketo]檔案中的[基底URL](https://developers.marketo.com/rest-api/base-url/)。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的Marketo使用者端ID。 如需尋找此位置的指示，請參閱[!DNL Marketo]檔案中的[Authentication](https://developers.marketo.com/rest-api/authentication/)。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的Marketo使用者端密碼。 如需尋找這些專案的說明，請參閱[!DNL Marketo]檔案中的[驗證](https://developers.marketo.com/rest-api/authentication/)。</td>
      </tr>
     </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

## [!DNL Marketo]模組及其欄位

當您設定[!DNL Marketo]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Marketo]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

* [[!UICONTROL 觀看活動（即時）]](#watch-events-instant)
* [[!UICONTROL 觀看記錄]](#watch-records)

#### [!UICONTROL 觀看活動（即時）]

建立或更新記錄時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>輸入您希望模組使用的webhook。</p> <p>如需Webhooks的詳細資訊，請參閱<a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md" class="MCXref xref">Webhooks</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看記錄]

建立或更新記錄時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要建立的記錄型別。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 活動]</strong> </p> <p>選取您要觀看的活動型別。 </p> <p>模組只會監視新活動。<br></p> </li> 
     <li> <p><strong>[!UICONTROL 銷售機會]</strong> </p> <p>在<b>事件型別</b>欄位中，選取是否要監視新記錄、更新記錄、新記錄和更新記錄，或特定欄位更新。 如果您選取觀看特定欄位更新，請選取您希望模組觀看的欄位。</p> </li> 
     <li> <p><strong>[!UICONTROL 程式]</strong> </p> <p>在<b>事件型別</b>欄位中，選取您要監視新記錄、更新的記錄，或同時監視新記錄和更新的記錄。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td> <p>選取您要包含在此模組之輸出組合中的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 新增銷售機會至清單]](#add-leads-to-a-list)
* [[!UICONTROL 復製程式]](#clone-a-program)
* [[!UICONTROL 建立記錄]](#create-a-record)
* [[!UICONTROL 自訂API呼叫]](#custom-api-call)
* [[!UICONTROL 下載檔案]](#download-a-file)
* [[!UICONTROL 讀取記錄]](#read-a-record)
* [[!UICONTROL 從清單中移除銷售機會]](#remove-leads-from-a-list)
* [[!UICONTROL 排程行銷活動]](#schedule-a-campaign)
* [[!UICONTROL 更新記錄]](#update-a-record)
* [[!UICONTROL 上傳檔案]](#upload-a-file)

#### [!UICONTROL 新增銷售機會至清單]

此動作模組會使用銷售機會ID將一或多個銷售機會新增至清單。 您一次最多可以新增300個銷售機會。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 清單ID]</td> 
   <td>輸入或對應您要新增潛在客戶之清單的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 銷售機會ID]</td> 
   <td> <p>針對您要新增至清單的每個銷售機會，按一下<b>[!UICONTROL 新增]</b>，然後輸入或對應您要新增的銷售機會ID。 您可以新增最多300個銷售機會，以供模組新增至清單。</p> <p>按一下地圖切換來對應您想要新增到清單中的現有銷售機會集合。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 復製程式]

此動作模組會使用現有程式ID製作程式的副本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 現有計畫ID]</td> 
   <td>輸入或對應您要複製的程式ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 新計畫名稱]</p> </td> 
   <td> <p>輸入或對應新方案的名稱</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾ID]</td> 
   <td>輸入或對應您要將新程式放置到的資料夾的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立記錄]

此動作模組會在[!DNL Marketo]中建立新記錄

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要建立的記錄型別。</p> 
    <ul> 
     <li> <p>[!UICONTROL 公司]</p> </li> 
     <li> <p>[!UICONTROL 資料夾]</p> </li> 
     <li> <p>[!UICONTROL 銷售機會]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 選擇要對應的欄位]</td> 
   <td>如果您要建立「公司」或「銷售機會」，請在建立新記錄時選取要設定值的欄位，然後輸入這些欄位的值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 程式型別]</td> 
   <td>如果您正在建立方案，請選取您要建立的方案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 計畫頻道] </td> 
   <td>如果您正在建立方案，請選取您要建立方案的方案頻道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾] / [!UICONTROL 程式名稱]</td> 
   <td>如果您正在建立資料夾或程式，請輸入或對應新記錄的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 說明]</td> 
   <td> <p>如果您要建立資料夾或程式，請輸入或對應新記錄的描述。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 父資料夾ID]</td> 
   <td>如果您正在建立資料夾或程式，請輸入或對應您要建立新記錄的父資料夾的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 成本]</td> 
   <td>如果您正在建立方案，請新增任何成本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td>如果您正在建立方案，請新增任何標籤</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂API呼叫]

此動作模組可讓您對[!DNL Marketo] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Marketo]模組無法完成的資料流程自動化。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>https://{your-base-url}.mktorest.com/</code>的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion]會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td> <p>針對您想要新增至API呼叫的每個欄位，按一下<b>新增專案</b>並輸入欄位的索引鍵和值。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 下載檔案]

此動作模組會使用檔案ID下載檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案ID]</td> 
   <td>輸入或對應您要下載的檔案ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組使用記錄的ID來讀取記錄的相關資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要建立的記錄型別。</p> 
    <ul> 
     <li> <p>[!UICONTROL 行銷活動]</p> </li> 
     <li> <p>[!UICONTROL 公司]</p> </li> 
     <li> <p>[!UICONTROL 銷售機會]</p> </li> 
     <li> <p>[!UICONTROL 清單]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取要包含在此模組輸出組合中的資訊。 根據您選取的[!UICONTROL 記錄型別]，可以使用欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL &lt;物件&gt; ID]</td> 
   <td>輸入或對應您要擷取相關資訊之物件的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 從清單中移除銷售機會]

此動作模組會使用銷售機會ID從清單中移除一或多個銷售機會。 您一次最多可以移除300個銷售機會。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 清單ID]</td> 
   <td>輸入或對映您要移除潛在客戶的清單ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 銷售機會ID]</td> 
   <td> <p>針對您要從清單中移除的每個銷售機會，按一下<b>[!UICONTROL 新增專案]</b>，然後輸入或對應您要移除的銷售機會ID。 您最多可以新增300個銷售機會，以便模組從清單中移除。 </p> <p>按一下地圖切換來對應您要從清單中移除的現有銷售機會集合。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 排程行銷活動]

此動作模組會為特定日期排程現有行銷活動。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 促銷活動ID]</td> 
   <td>輸入或對應您要排程之行銷活動的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 日期排程]</p> </td> 
   <td>選取您要執行行銷活動的日期。 如果此欄位留空，則行銷活動會在情境開始後5分鐘執行。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組使用其ID更新現有記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要建立的記錄型別。</p> 
    <ul> 
     <li> <p>[!UICONTROL 公司]</p> </li> 
     <li> <p>[!UICONTROL 銷售機會]</p> </li> 
     <li> <p>[!UICONTROL Program]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Company] / [!UICONTROL Lead] / [!UICONTROL 計畫ID]</td> 
   <td>輸入或對應您要更新的記錄ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 選擇要對應的欄位]</td> 
   <td>如果您要更新「公司」或「銷售機會」，請選取要更新值的欄位，然後輸入這些欄位的值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 程式名稱]</td> 
   <td>如果您正在更新方案，請輸入或對應方案的新名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 說明]</td> 
   <td> <p>如果您要更新程式，請輸入或對應程式的新描述。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 開始日期]</td> 
   <td>如果您要更新程式，請輸入或對應程式的新開始日期。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結束日期]</td> 
   <td>如果您要更新方案，請輸入或對應方案的新結束日期。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 成本]</td> 
   <td>如果您要更新程式，請新增任何成本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td>如果您要更新程式，請新增任何標籤</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳檔案]

此動作模組會將新檔案上傳至[!UICONTROL Marketo]。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source檔案]</td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾ID]</td> 
   <td>輸入或對應您要放置新檔案的資料夾識別碼。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 說明]</td> 
   <td>輸入已上傳檔案的說明。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL 清單記錄]](#list-records)
* [[!UICONTROL 搜尋記錄]](#update-a-record)

#### [!UICONTROL 清單記錄]

此動作模組會擷取特定型別的所有記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要列出的記錄型別。</p> 
    <ul> 
     <li> <p>[!UICONTROL 讀取所有行銷活動]</p> </li> 
     <li> <p>[!UICONTROL 讀取所有程式]</p> </li> 
     <li> <p>[!UICONTROL 讀取所有潛在客戶] </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td>如果您已選取擷取銷售機會，請選取您要從清單還是從方案中擷取銷售機會。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取要包含在此模組輸出組合中的資訊。 根據您選取的[!UICONTROL 記錄型別]，可以使用欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋記錄]

此搜尋模組會擷取符合特定搜尋條件的記錄清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Marketo]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-marketo-to-workfront-fusion" class="MCXref xref">將[!DNL Marketo]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要搜尋的記錄型別。</p> 
    <ul> 
     <li> <p>[!UICONTROL 行銷活動]</p> </li> 
     <li> <p>[!UICONTROL 銷售機會]</p> </li> 
     <li> <p>[!UICONTROL 程式]</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 欄位]</p> </td> 
   <td> <p>選取您要搜尋的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 值/值]</td> 
   <td>輸入您要搜尋之欄位的值。 如果欄位可讓您搜尋多個值，請針對您要搜尋的每個值，按一下<b>[!UICONTROL 新增專案]</b>並輸入值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Output]</td> 
   <td> <p>選取要包含在此模組輸出組合中的資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

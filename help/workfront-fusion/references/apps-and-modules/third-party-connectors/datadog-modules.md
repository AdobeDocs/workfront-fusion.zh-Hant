---
title: Datadog模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Datadog的工作流程，並將其連結到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: c8c5f2e3-5af1-4957-bb6f-6c19c35102c5
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 1%

---

# [!DNL Datadog]模組

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Datadog]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!DNL Datadog]模組，您必須有[!DNL Datadog]帳戶。

## Datadog API資訊

Datadog聯結器會使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>1.0.11</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Datadog]連線至Workfront Fusion {#connect-datadog-to-workfront-fusion}

### 擷取您的API金鑰和應用程式金鑰 {#retrieve-your-api-key-and-application-key}

若要將您的[!DNL Datadog]帳戶連線至Workfront Fusion，您必須從您的[!DNL Datadog]帳戶擷取API金鑰和應用程式金鑰。

1. 登入您的[!DNL Datadog]帳戶。
1. 在左側導覽面板中，按一下&#x200B;**[!UICONTROL 整合]**，然後按一下&#x200B;**[!UICONTROL API]**。
1. 在主畫面上，按一下&#x200B;**[!UICONTROL API金鑰]**。
1. 將滑鼠停留在紫色列上以顯示API金鑰。
1. 將API金鑰複製到安全位置。
1. 在主畫面上，按一下&#x200B;**[!UICONTROL 應用程式鍵]**。
1. 將滑鼠指標暫留在紫色列上，即可顯示應用程式索引鍵。
1. 將應用程式金鑰複製到安全位置。

### 在Workfront Fusion中建立與[!DNL Datadog]的連線

您可以直接從[!DNL Datadog]Datadog[!UICONTROL 模組內建立與您的]帳戶的連線。

1. 在任何[!UICONTROL Datadog]模組中，按一下&#x200B;**[!UICONTROL 連線]**&#x200B;欄位旁的[!UICONTROL 新增]。
1. 依照以下方式填寫模組的欄位：

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL 連線名稱]</td> 
      <td> <p> 輸入連線的名稱。</p> </td> 
     </tr> 
        <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>選取此連線是用於生產或非生產環境。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 型別]</td>
        <td>選取您要連線到服務帳戶還是個人帳戶。</td>
        </tr>
     <tr> 
      <td role="rowheader">[!UICONTROL 網域] </td> 
      <td> <p>選取您要連線的網域（美國或歐盟）。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API金鑰位置] </td> 
      <td> <p>選取在標頭或查詢字串中包含API金鑰。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td> <p> 輸入您的[!DNL Datadog] API金鑰。 </p> <p>如需擷取API金鑰的指示，請參閱本文中的<a href="#retrieve-your-api-key-and-application-key" class="MCXref xref">擷取您的API金鑰和應用程式金鑰</a>。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

## [!DNL Datadog]模組及其欄位

當您設定[!DNL Datadog]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Datadog]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 動作

* [[!UICONTROL 進行API呼叫]](#make-an-api-call)
* [[!UICONTROL 張貼時間序列點]](#post-timeseries-points)

#### [!UICONTROL 進行API呼叫]

此動作模組可讓您執行自訂API呼叫。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Datadog]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">將[!DNL Datadog]連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 使用專用網域]</td> 
   <td>有些Datadog API端點預期會有大量傳入流量，但在其專用網域中執行。 核取此方塊以使用您API呼叫的專用網域。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>https://api.datadoghq.com/api/</code>的路徑。 範例： <code> /v1/org</code>。</td> 
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
 </tbody> 
</table>

**範例：**&#x200B;下列API呼叫傳回您[!DNL Datadog]帳戶中的所有儀表板：

URL： `/v1/dashboard`

方法： `GET`

![Datadog API呼叫範例](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-example.png)

結果可在模組的輸出中找到，位於「套件>內文>控制面板」下。

在我們的範例中，傳回3個控制面板：

![Datadog API回應](/help/workfront-fusion/references/apps-and-modules/assets/datadog-api-response-example.png)

#### [!UICONTROL 張貼時間序列點]

此模組可讓您張貼可以在[!DNL Datadog]的儀表板上繪製的時間序列資料。

壓縮有效負載的限製為3.2 MB (3200000)，而解壓縮有效負載的限製為62 MB (62914560)。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Datadog]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-datadog-to-workfront-fusion" class="MCXref xref">將[!DNL Datadog]連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 型別]</td> 
   <td> 選取您要使用的量度型別。 
   <ul>
   <li>量測計</li>
   <li>費率</li>
   <li>計數</li>
   </ul>
   </td> 
  <tr> 
   <td role="rowheader">[!UICONTROL 間隔]</td> 
   <td> 如果度量的型別是「比率」或「計數」，請定義對應的間隔。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 點]</td> 
   <td><p>新增與量度相關的點。</p> <p>這是JSON點陣列。 每個點的格式如下： <code>[[POSIX_timestamp, numeric_value], ...] </code></p> <p>注意：  <p>時間戳記必須以秒為單位。</p> <p>時間戳記必須是最新的。 「目前」的定義是未來不超過10分鐘，或過去不超過1小時。</p> <p> 數值格式應為浮點數值。</p> </p> <p>此欄位必須至少包含1個專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 主機]</td> 
   <td>輸入產生測量結果的主機名稱。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td> 針對您想要新增至量度的每個標籤，按一下<b>新增專案</b>並輸入標籤的值。</td> 
  </tr> 
 </tbody> 
</table>

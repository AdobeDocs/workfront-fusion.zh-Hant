---
title: Adobe Firefly 模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL Adobe Firefly] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
TQID: https://experienceleague.adobe.com/1hI4NuUl2eEAgWyXRKLHQ3-6MM9-2tFyujGbRfHSBmU
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 3886
ht-degree: 15%

---

# [!DNL Adobe Firefly] 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Adobe Firefly] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

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

使用[!DNL Adobe Firefly]聯結器之前，您必須確定符合下列先決條件：

* 您必須擁有使用中的[!DNL Adobe Firefly]帳戶。

## Adobe Firefly API資訊

Adobe Firefly聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.4.24</td> 
  </tr>
 </tbody> 
 </table>

## 建立與 [!DNL Adobe Firefly] 的連線

若要為您的 [!DNL Adobe Firefly] 模組建立連線：

1. 在任何模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

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
          <p>輸入此連線的名稱。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>選取您要連線到生產或非生產環境。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 類型]</td>
        <td>選取要連接至服務帳戶或者個人帳戶。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的[!UICONTROL Adobe] [!UICONTROL 使用者端ID]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials]詳細資訊區段中找到。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端密碼]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials]詳細資訊區段中找到。</td>
        </tr>
      </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

## [!DNL Adobe Firefly] 模組及其欄位

當您設定 [!DNL Adobe Firefly] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Adobe Firefly] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 展開影像

此動作模組會展開影像，選擇性地從您提供的提示中展開內容。

此模組適用於Firefly API V3 Async。 此模組的先前版本已淘汰，將於近期移除。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提示]</td> 
   <td>針對您要展開影像的內容輸入或對應提示。 如果未提供提示，影像將會展開並包含符合原始影像的內容。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變化數]</td> 
   <td>輸入介於1-4之間的數字。 模組會產生此數量的展開影像變數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source]</td> 
   <td>選取您提供來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 展開影像格式]</td> 
   <td>選取將儲存展開影像的檔案格式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 展開依據]</td> 
   <td>  <p>選取您要使用影像位置或使用遮色片來展開影像。</p> 
   <ul>
   <li><b>產品建議放置環境</b><p>輸入水平和垂直對齊方式，以及置入影像的邊緣內縮。</p></li>
   <li><b>遮色片</b><p>選取遮罩的來源檔案，以及遮罩是否應反轉。</p></li>
   </ul>
</td> 
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小]</td> 
   <td>選取您想要展開影像的高度和寬度。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 種子]</td> 
   <td>針對模組將產生的每個影像，按一下<b>新增專案</b>並輸入或對應整數。 您可以在其他展開影像模組中使用相同的種子，以產生具有不同樣式的類似影像。 您新增的種子數必須等於「變化數」欄位。</td> 
  </tr> 
 </tbody> 
</table>

### 展開影像（已棄用）

此模組已淘汰，將於不久將來移除。 請改用展開影像模組。

### 填滿影像

此動作模組會填滿影像的遮色區域，選擇性地使用您提供的提示內容。

此模組適用於Firefly API V3 Async。 此模組的先前版本已淘汰，將於近期移除。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 影像&gt; Source]</td> 
   <td>選取您提供影像來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 遮色片&gt; Source]</td> 
   <td>選取您提供遮罩來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提示]</td> 
   <td>針對您要填滿影像的內容，輸入或對應提示。 如果未提供提示，則會以符合原始影像的內容來填滿影像。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變化數]</td> 
   <td>輸入介於1-4之間的數字。 模組會產生此數量的填入影像變數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 填色影像格式]</td> 
   <td>選取將儲存填色影像的檔案格式。</td> 
  </tr> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 種子]</td> 
   <td>針對模組將產生的每個影像，按一下<b>新增專案</b>並輸入或對應整數。 您可以在其他展開影像模組中使用相同的種子，以產生具有不同樣式的類似影像。 您新增的種子數必須等於「變化數」欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小]</td> 
   <td>選取您想要填色影像的大小。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>如果提供了地區設定，模組會產生與指定地區設定更相關的內容。 <p>地區必須以ISO 639-1語言代碼和ISO 3166-1區域提供。</p><p> 範例： <code>en-US</code></p></td> 
  </tr> 
 </tbody> 
</table>

### 填滿影像（已棄用）

此模組已淘汰，將於不久將來移除。 請改用「填滿影像」模組。

### 產生自適應複合

此動作模組會將主題影像完美地合成至遮色位置的背景影像。 您可以控制陰影套用的強烈程度、物件的光源和顏色與背景的協調方式，以及原始背景細節是否保留在遮色區域內。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 背景&gt;影像&gt; Source]</td> 
   <td>選取您提供背景影像的方式。 背景影像是合成物件的目的地場景。<ul><li><p><b>上傳影像</b></p><p>上傳背景影像，或對映上一個模組的影像檔案。</p></li><li><p><b>影像URL</b></p><p>輸入或對映背景影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 背景&gt;填色區域遮色片&gt; Source]</td> 
   <td>選取如何提供填色區域遮色片。 填色區域遮色片會指出將放置物件的背景區域。<ul><li><p><b>上傳影像</b></p><p>上傳填色區域遮色片影像，或對映上一個模組的影像檔案。</p></li><li><p><b>影像URL</b></p><p>輸入或對映填色區域遮色片影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 物件&gt;影像&gt; Source]</td> 
   <td>選取您提供物件影像的方式。 物件影像是物件的來源影像，可合成到背景中。<ul><li><p><b>上傳影像</b></p><p>上傳物件影像，或對映上一個模組的影像檔案。</p></li><li><p><b>影像URL</b></p><p>輸入或對應物件影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 物件&gt;遮色片&gt; Source]</td> 
   <td>選取提供物件遮色片的方式。 物件遮色片是物件的分段遮色片。<ul><li><p><b>上傳影像</b></p><p>上傳物件遮色片影像，或對映上一個模組的影像檔案。</p></li><li><p><b>影像URL</b></p><p>輸入或對應物件遮色片影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變化數]</td> 
   <td>輸入介於1和3之間的數字。 模組會產生此數量的複合變數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 種子]*</td> 
   <td>按一下<b>新增專案</b>以新增種子值，然後輸入或對應整數。 每個變數使用一個種子。 如果同時提供這兩個值，則種子值的計數必須與[!UICONTROL Number of Variations]值相符。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 協調]*</td> 
   <td>輸入介於0和1之間的數字，以控制物件的顏色和光源調整成符合背景的程度。 <code>0.0</code>套用最小協調，<code>1.0</code>套用最大協調。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 陰影強度]*</td> 
   <td>輸入介於0和1之間的數字，以控制合成結果中的陰影強度。 較低的值會減少陰影。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 保留背景]*</td> 
   <td>選取在合成期間是否保留遮色區域的原始背景細節。 <ul><li><b>是</b><p>在合成期間，遮色區域內的原始背景細節會保留。</p></li><li><b>無</b><p>在合成期間，遮色區域內的原始背景細節不會保留。</p></li><li><b>未定義</b><p>使用此選項的預設行為。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出&gt;媒體型別]*</td> 
   <td>選取產生的複合將儲存為的檔案格式。</td> 
  </tr> 
 </tbody> 
</table>

* 這些欄位是進階欄位，除非您選取&#x200B;**[!UICONTROL 顯示進階設定]**，否則不會顯示。

### 產生影像

此動作模組會根據您提供的提示產生和影像。 您也可以提供選用的參考影像，產生的影像將與參考影像的樣式相符。

此模組適用於Firefly API V3 Async。 此模組的先前版本已淘汰，將於近期移除。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提示]</td> 
   <td>輸入或對應您要產生之影像的提示。 提示中更詳細的內容可讓您更能控制影像中顯示的內容。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 模型版本]</td> 
   <td>選取您要用來產生影像的Firefly模型版本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變化數]</td> 
   <td>輸入介於1-4之間的數字。 模組會產生此數量的影像變數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 產生的影像格式]</td> 
   <td>選取將儲存展開影像的檔案格式。 如果您選取「預設」，則若未提供參考影像，檔案格式將為JPEG。 如果提供參考影像，則產生影像的檔案格式將與參考影像相同。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結構&gt;影像參考]</td> 
    <td>選取您為新影像結構提供來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結構&gt;強度]</td> 
    <td>輸入介於0和100之間的數字，以控制Firefly遵循來源影像結構的嚴格程度。 數字愈高，表示Firefly愈嚴格地遵循影像。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 樣式&gt;影像參考]</td> 
    <td>選取您為新影像的樣式提供來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結構&gt;強度]</td> 
    <td>輸入介於0和100之間的數字，以控制Firefly遵循來源影像樣式的嚴格程度。 數字愈高，表示Firefly愈嚴格地遵循影像。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 樣式&gt;預設集]</td> 
   <td>如果要使用預設樣式，請按一下「新增專案」，然後輸入或對應您要使用的樣式。<p>如需預設樣式清單，請參閱Adobe開發人員檔案中的<a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >影像模型樣式</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 負面提示]</td> 
   <td>在產生的內容中輸入或對應您要避免的文字。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內容類別]</td> 
   <td>選取您希望產生的影像更像是像片，還是更像是建立的圖案。 <ul><li><b>相片</b><p>輸入「光圈」、「快門速度」（以秒為單位）和「視野」（以毫米為單位）的值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 種子]</td> 
   <td>針對模組將產生的每個影像，按一下<b>新增專案</b>並輸入或對應整數。 您可以在其他展開影像模組中使用相同的種子，以產生具有不同樣式的類似影像。 您新增的種子數必須等於「變化數」欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小]</td> 
   <td>選取您希望產生的影像的大小。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 視覺強度]</td> 
   <td>輸入或對應整數，代表像片現有視覺特性的整體強度。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]</td> 
   <td>如果提供了地區設定，模組會產生與指定地區設定更相關的內容。 <p>地區必須以ISO 639-1語言代碼和ISO 3166-1區域提供。</p><p> 範例： <code>en-US</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 可分頁]</td> 
   <td>啟用此選項可產生可在每個方向無限重複的影像。</td> 
  </tr> 
 </tbody> 
</table>

### 產生影像（已棄用）

此模組已淘汰，將於不久將來移除。 請改用產生影像模組。

### 產生物件複合

此動作模組會合併Firefly產生的影像，以建立影像組合。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提示]</td> 
   <td>輸入或對應您要產生之影像的提示。 提示中更詳細的內容可讓您更能控制影像中顯示的內容。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變化數]</td> 
   <td>輸入介於1-4之間的數字。 模組會產生此數量的影像變數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內容類別]</td> 
   <td>選取您希望產生的影像更像是像片還是圖稿。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 影像&gt; Source]</td> 
    <td>選取您為新影像結構提供來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 產生的影像格式]</td> 
   <td>選取將儲存展開影像的檔案格式。 如果您選取「預設」，則若未提供參考影像，檔案格式將為JPEG。 如果提供參考影像，則產生影像的檔案格式將與參考影像相同。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 樣式&gt;影像參考]</td> 
    <td>選取您為新影像的樣式提供來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結構&gt;強度]</td> 
    <td>輸入介於0和100之間的數字，以控制Firefly遵循來源影像樣式的嚴格程度。 數字愈高，表示Firefly愈嚴格地遵循影像。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 樣式&gt;預設集]</td> 
   <td>如果要使用預設樣式，請按一下「新增專案」，然後輸入或對應您要使用的樣式。<p>如需預設樣式清單，請參閱Adobe開發人員檔案中的<a href="https://developer.adobe.com/firefly-services/docs/firefly-api/guides/concepts/style-presets//" >影像模型樣式</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小]</td> 
   <td>選取您希望產生的複合的大小。 </td> 
  </tr> 
 </tbody> 
</table>

### 使用Image5產生影像

此動作模組使用[!DNL Adobe Firefly] Image5模型產生影像。 您可以提供文字提示，也可選擇提供參考影像來指導產生作業。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提示]</td> 
   <td>輸入或對應您要產生的影像描述。 提示必須介於1到1500個字元之間。 提示中的詳細資訊可讓您更深入控制影像中顯示的內容。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 外觀比例]</td> 
   <td>選取產生影像的形狀。 如果提供參考影像，請選取<b>自動</b>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 解析度]</td> 
   <td>選取產生影像的解析度。 產生更高的解析度需要更長的時間。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 參考影像]</td> 
   <td>可選擇提供一個參考影像來指導產生流程。 按一下<b>新增專案</b>並提供影像。 使用參考影像時，請將[!UICONTROL 外觀比例]設定為<b>自動</b>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 種子]*</td> 
   <td>按一下<b>新增專案</b>，然後輸入或對應整數來重新產生特定的產生結果。 留空將產生隨機結果。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提示推理]*</td> 
   <td>選取產生期間使用的提示推理策略。<ul><li><p><b>品質 — 產生影像說明</b></p><p>在模組的輸出中產生影像說明。</p></li><li><p><b>速度 — 產生速度更快，不提供說明</b></p><p>產生影像的速度更快，但影像說明維持空白。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Locale]*</td> 
   <td>輸入或對應語言與地區代碼，將產生的內容量身訂做特定的國家/地區和語言。 <p>地區必須以ISO 639-1語言代碼和ISO 3166-1區域提供。</p><p>範例： <code>en-US</code></p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變數數目]*</td> 
   <td>輸入每個請求要產生的影像數量。 目前僅支援1個。 若要產生多個影像，請傳送個別請求。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 模型]*</td> 
   <td>選取您要用來產生影像的[!DNL Firefly]模型。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在一個執行週期內使用的最大結果數量。</td> 
  </tr> 
 </tbody> 
</table>

*這些欄位為進階欄位，除非您選取[顯示進階設定]&#x200B;**&#x200B;**，否則不會顯示。

### 產生精確複合

此動作模組會將主旨置於背景影像的遮色區域中，並套用產生式協調，使主旨與背景自然融合。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 背景&gt;影像&gt; Source]</td> 
   <td>選取您提供背景影像的方式。 背景影像是合成物件的目的地場景。<ul><li><p><b>上傳影像</b></p><p>上傳背景影像，或對映上一個模組的影像檔案。</p></li><li><p><b>影像URL</b></p><p>輸入或對映背景影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 背景&gt;填色區域遮色片&gt; Source]</td> 
   <td>選取如何提供填色區域遮色片。 填色區域遮色片會指出將放置物件的背景區域。<ul><li><p><b>上傳影像</b></p><p>上傳填色區域遮色片影像，或對映上一個模組的影像檔案。</p></li><li><p><b>影像URL</b></p><p>輸入或對映填色區域遮色片影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 物件&gt;影像&gt; Source]</td> 
   <td>選取您提供物件影像的方式。 物件影像是物件的來源影像，可合成到背景中。<ul><li><p><b>上傳影像</b></p><p>上傳物件影像，或對映上一個模組的影像檔案。</p></li><li><p><b>影像URL</b></p><p>輸入或對應物件影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變化數]</td> 
   <td>輸入介於1和3之間的數字。 模組會產生此數量的複合變數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 種子]*</td> 
   <td>按一下<b>新增專案</b>以新增種子值，然後輸入或對應整數。 每個變數使用一個種子。 如果同時提供這兩個值，則種子值的計數必須與[!UICONTROL Number of Variations]值相符。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Blend]*</td> 
   <td>輸入介於0和1之間的數字，以控制物件的協調外觀和原始外觀之間的混合。 <code>0.0</code>套用完全協調，且<code>1.0</code>保留原始物件的外觀。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出&gt;媒體型別]*</td> 
   <td>選取產生的複合將儲存為的檔案格式。</td> 
  </tr> 
 </tbody> 
</table>

* 這些欄位是進階欄位，除非您選取&#x200B;**[!UICONTROL 顯示進階設定]**，否則不會顯示。

### 產生類似影像

此動作模組會產生與您指定的來源影像類似的影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 變化數]</td> 
   <td>輸入介於1-4之間的數字。 模組會產生此數量的影像變數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 模型版本]</td> 
   <td>選取您要用來產生影像的Firefly模型版本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 產生的影像格式]</td> 
   <td>選取將儲存展開影像的檔案格式。 如果您選取「預設」，則若未提供參考影像，檔案格式將為JPEG。 如果提供參考影像，則產生影像的檔案格式將與參考影像相同。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 影像&gt; Source]</td> 
    <td>選取您為新影像結構提供來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 樣式&gt;影像參考]</td> 
    <td>選取您為新影像的樣式提供來源檔案的方式：<ul><li><p><b>檔案</b></p><p>從先前的模組中選取來源檔案，或對應來源檔案的「參照」影像檔案名稱和參照影像檔案。</p></li><li><p><b>預先簽署的URL</b></p><p>輸入或對應來源影像的URL。</p></li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小]</td> 
   <td>選取您希望產生的複合的大小。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 種子]</td> 
   <td>針對模組將產生的每個影像，按一下<b>新增專案</b>並輸入或對應整數。 您可以在其他展開影像模組中使用相同的種子，以產生具有不同樣式的類似影像。 您新增的種子數必須等於「變化數」欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 可分頁]</td> 
   <td>啟用此選項可產生可在每個方向無限重複的影像。</td> 
  </tr> 
 </tbody> 
</table>


### 產生視訊

此動作模組會從文字提示產生視訊。 您也可以提供一個或多個參考影像來指導視訊的產生。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提示]</td> 
   <td>輸入或對應您要產生之視訊的說明。 提示中的詳細資訊可讓您更深入控制視訊中顯示的內容。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 影像&gt;條件]</td> 
   <td>可選擇提供一或多個參考影像來指導視訊的產生。 按一下每個參考影像的<b>新增專案</b>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大小]</td> 
   <td>按一下<b>新增專案</b>，然後輸入或對應所產生視訊的尺寸。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 位元速率係數]*</td> 
   <td>輸入0到63之間的數字，指定產生視訊的位元速率係數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 視訊設定&gt;相機動作]*</td> 
   <td>選取您要在產生的視訊中使用的相機動作。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 視訊設定&gt;提示樣式]*</td> 
   <td>選取您要用於產生視訊的提示樣式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 視訊設定&gt;拍攝角度]*</td> 
   <td>選取您要在產生的視訊中使用的拍攝角度。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 視訊設定&gt;拍攝大小]*</td> 
   <td>選取您要在產生的視訊中使用的拍攝大小。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在一個執行週期內使用的最大結果數量。</td> 
  </tr> 
 </tbody> 
</table>

* 這些欄位是進階欄位，除非您選取&#x200B;**[!UICONTROL 顯示進階設定]**，否則不會顯示。

### 進行自訂的 API 呼叫

此動作模組會對Firefly API進行自訂呼叫。

如需特定可用的API，請參閱Adobe Developer檔案中的[Adobe Firefly API](https://developer.adobe.com/firefly-services/docs/firefly-api/)。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Firefly] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與 [!DNL Adobe Firefly]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>輸入相對於 <code>https://firefly-api.adobe.io/</code> 的路徑。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
      </td>
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 標頭]</td>
      <td>
        <p>以標準 JSON 物件的形式新增要求標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion 會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 正文]</td>
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>


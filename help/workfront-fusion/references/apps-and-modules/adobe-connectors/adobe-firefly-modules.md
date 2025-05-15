---
title: Adobe Firefly模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動化使用 [!DNL Adobe Firefly]的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: 6219cd4406c2ccf22b1e94e5d264722e640fe3e4
workflow-type: tm+mt
source-wordcount: '2466'
ht-degree: 0%

---

# [!DNL Adobe Firefly]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Adobe Firefly]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

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

使用[!DNL Adobe Firefly]聯結器之前，您必須確定符合下列先決條件：

* 您必須擁有使用中的[!DNL Adobe Firefly]帳戶。

## Adobe Firefly API資訊

Adobe Firefly聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.4.24</td> 
  </tr>
 </tbody> 
 </table>

## 建立與[!DNL Adobe Firefly]的連線

若要為您的[!DNL Adobe Firefly]模組建立連線：

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
        <td role="rowheader">[!UICONTROL 型別]</td>
        <td>選取您要連線到服務帳戶還是個人帳戶。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的[!UICONTROL Adobe] [!UICONTROL 使用者端ID]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials]詳細資訊區段中找到。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的[!DNL Adobe] [!UICONTROL 使用者端密碼]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials]詳細資訊區段中找到。</td>
        </tr>
      </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

## [!DNL Adobe Firefly]模組及其欄位

當您設定[!DNL Adobe Firefly]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe Firefly]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 展開影像

此動作模組會展開影像，選擇性地從您提供的提示中展開內容。

此模組適用於Firefly API V3 Async。 此模組的先前版本已淘汰，將於近期移除。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與[!DNL Adobe Firefly]</a>的連線。</td> 
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
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與[!DNL Adobe Firefly]</a>的連線。</td> 
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

### 產生影像

此動作模組會根據您提供的提示產生和影像。 您也可以提供選用的參考影像，產生的影像將與參考影像的樣式相符。

此模組適用於Firefly API V3 Async。 此模組的先前版本已淘汰，將於近期移除。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與[!DNL Adobe Firefly]</a>的連線。</td> 
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
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與[!DNL Adobe Firefly]</a>的連線。</td> 
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

### 產生類似影像

此動作模組會產生與您指定的來源影像類似的影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Adobe Campaign]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與[!DNL Adobe Firefly]</a>的連線。</td> 
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


### 進行自訂API呼叫

此動作模組會對Firefly API進行自訂呼叫。

如需特定可用的API，請參閱Adobe Developer檔案中的[Adobe Firefly API](https://developer.adobe.com/firefly-services/docs/firefly-api/)。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Firefly]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與[!DNL Adobe Firefly]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>輸入相對於<code>https://firefly-api.adobe.io/</code>的路徑。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
      </td>
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] 自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>


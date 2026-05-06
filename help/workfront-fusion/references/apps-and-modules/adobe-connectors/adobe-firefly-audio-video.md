---
title: Adobe Firefly音訊與視訊模組
description: 在Adobe Workfront Fusion情境中，您可以自動化使用Adobe Firefly音訊和視訊的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: f54338aa35b8453ac991c9e16974f2b61fd30168
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 14%

---

# Adobe Firefly音訊與視訊模組

在Adobe Workfront Fusion情境中，您可以自動化使用Adobe Firefly音訊和視訊的工作流程，並將其連線到多個協力廠商應用程式和服務。

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

使用Adobe Firefly Audio and Video聯結器前，您必須確定符合下列先決條件：

* 您必須擁有使用中的Adobe Firefly音訊與視訊帳戶。

## 建立與Adobe Firefly音訊和視訊的連線

若要建立Adobe Firefly音訊與視訊模組的連線：

1. 在任何模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">連線名稱</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">環境</td>
        <td>選取您要連線到生產或非生產環境。</td>
        </tr>
        <tr>
        <td role="rowheader">類型</td>
        <td>選取要連接至服務帳戶或者個人帳戶。</td>
        </tr>
        <tr>
        <td role="rowheader">用戶端 ID</td>
        <td>輸入您的Adobe使用者端ID。 您可在Adobe Developer Console的「認證詳細資料」區段中找到。</td>
        </tr>
        <tr>
        <td role="rowheader">用戶端密碼</td>
        <td>輸入您的Adobe使用者端密碼。 您可在Adobe Developer Console的「認證詳細資料」區段中找到。</td>
        </tr>
      </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。


## Adobe Firefly音訊與視訊模組及其欄位

當您設定Adobe Firefly音訊與視訊模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Adobe Firefly音訊和視訊欄位，視您在應用程式或服務中的存取層級等因素而定。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 動作

* [描述範本](#describe-template)
* [音訊或視訊配音](#dub-audio-or-video)
* [從文字或音訊產生顯示圖片視訊](#generate-avatar-video-from-text-or-audio)
* [從文字產生語音](#generate-speech-from-text)
* [重新設定視訊框架](#reframe-video)
* [演算範本](#render-template)
* [轉錄媒體](#transcribe-media)

#### 描述範本

此動作模組會分析MOGRT （視訊範本）檔案，並傳回可編輯控制項、字型、影像、音訊、視訊和其他支援值的資訊清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與Adobe Firefly的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>輸入或對應指向輸入範本檔案的預簽署URL。</td> 
  </tr>
 </tbody> 
</table>

#### 音訊或視訊配音

此動作模組會產生配音音訊或視訊。 它亦可在產生的視訊中包含唇同步。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與Adobe Firefly的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Dub型別</td> 
   <td>選取您要產生音訊或視訊dub。</td> 
  </tr>
  <tr> 
   <td role="rowheader">預先簽署的URL</td> 
   <td>輸入或對應模組將用來輸入的預先簽署URL。<p>Firefly Audio and Video接受下列媒體儲存網域</p>
   <ul>
   <li>adobe.io</li>
   <li>frame.io</li>
   <li>amazonaws.com</li>
   <li>windows.net</li>
   <li>dropboxusercontent.com</li>
   <li>drive.google.com</li>
   <li>cloudfront.net</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">媒體型別</td> 
   <td>選取輸入檔案的媒體型別</td> 
  </tr>
  <tr> 
   <td role="rowheader">唇同步</td> 
   <td>選取是否要為視訊輸出產生高品質的合成唇同步。</td> 
  </tr>
  <tr> 
   <td role="rowheader">目標地區設定代碼</td> 
   <td>針對您要新增的每個地區設定代碼，按一下<b>新增專案</b>並選取地區設定代碼。</td> 
  </tr>
  <tr> 
   <td role="rowheader">成績單</td> 
   <td>針對您想要新增的每個筆錄，按一下<b>新增專案</b>，然後輸入或對應該筆錄的預先簽署URL。</td> 
  </tr>
 </tbody> 
</table>

#### 從文字或音訊產生顯示圖片視訊

此動作模組會從您提供的文字記錄或音訊檔案中產生顯示圖片視訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與Adobe Firefly的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>輸入或對應模組將用來輸入的預先簽署URL。   </td> 
  </tr>
  <tr> 
  <tr> 
   <td role="rowheader">地區代碼</td> 
   <td>選取代表您要在結果中使用的語言的區域設定代碼。</td> 
  </tr>
   <td role="rowheader">媒體型別(Source)</td> 
   <td>選取輸入檔案的媒體型別</td> 
  </tr>
  <tr> 
   <td role="rowheader">頭像</td> 
   <td>選取您要用於產生視訊的頭像。</td> 
  </tr>
  <tr> 
   <td role="rowheader">媒體型別</td> 
   <td>為產生的視訊選取輸出媒體型別。</td> 
  </tr>
  <tr> 
   <td role="rowheader">寬度</td> 
   <td>輸入或對應產生視訊的寬度。</td> 
  </tr>
  <tr> 
   <td role="rowheader">高度</td> 
   <td>輸入或對映所產生視訊的高度。</td> 
  </tr>
  <tr> 
   <td role="rowheader">背景</td> 
   <td>選取您要用於產生視訊的背景型別：
   <ul>
   <li><b>影片</b>：輸入或對應背景影片的URL。</li> 
   <li><b>影像</b>：輸入或對應背景影像的URL。</li>
   <li><b>色彩</b>：輸入或對應您要用於視訊背景的色彩十六進位值。</li> 
   </ul>
   </td>
  </tr>
 </tbody> 
</table>

#### 從文字產生語音

此動作模組會從成績單產生語音。 您可以提供純文字記錄或預先簽署的URL。 回應包含作業ID和用於追蹤作業的狀態URL。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與Adobe Firefly的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">指令碼</td> 
   <td>選取您要提供的指令碼型別。
   <ul>
   <li><b>文字</b>：輸入或對應來源文字至[文字]欄位。</li>
   <li><b>文字檔</b>：在URL欄位中輸入或對應文字檔的URL。</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">地區代碼</td> 
   <td>選取代表您要在結果中使用的語言的區域設定代碼。</td> 
  </tr>
  <tr> 
   <td role="rowheader">媒體型別</td> 
   <td>這應該是<code>text/plain</code>。</td> 
  </tr>
  <tr> 
   <td role="rowheader">語音</td> 
   <td>選取您要使用的聲音。 可用的聲音來自聲音的Adobe Firefly目錄。</td> 
  </tr>
  <tr> 
   <td role="rowheader">輸出</td> 
   <td>這應該是<code>audio/wav</code>。</td> 
  </tr>
 </tbody> 
</table>

#### 重新設定視訊框架

此模組會重新格式化您提供的媒體。 媒體是透過預先簽署的URL提供。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與Adobe Firefly的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">預先簽署的URL</td> 
   <td>輸入或對應模組將用來輸入的預先簽署URL。<p>Firefly Audio and Video接受下列媒體儲存網域</p>
   <ul>
   <li>adobe.io</li>
   <li>frame.io</li>
   <li>amazonaws.com</li>
   <li>windows.net</li>
   <li>dropboxusercontent.com</li>
   <li>drive.google.com</li>
   <li>cloudfront.net</li>
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">場景編輯偵測</td> 
   <td>選取是否要在重新定格前套用場景編輯偵測。 </td> 
  </tr>
  <tr> 
   <td role="rowheader">焦點</td> 
   <td>針對您想要新增的每個焦點，按一下[新增專案] <b> </b>，然後輸入或焦點的關鍵字識別碼。</td> 
  </tr>
  <tr> 
   <td role="rowheader">覆蓋</td> 
   <td>針對您想要新增的每個覆蓋，按一下<b>新增專案</b>並輸入覆蓋資訊。
   <ul>
   <li><b>Source</b>：輸入或對應指向來源媒體的URL。</li> 
   <li><b>開始時間</b>：輸入或對應開始時間。</li>
   <li><b>持續時間</b>：輸入或對映覆蓋的持續時間。</li> 
   <li><b>寬度</b>：輸入或對應縮放覆蓋的寬度。</li> 
   <li><b>高度</b>：輸入或對應縮放覆蓋的高度。</li> 
   <li><b>錨點</b>：選取覆蓋圖的錨點。</li> 
   <li><b>位移X</b>：輸入或對映覆蓋圖的水平位移。</li> 
   <li><b>位移Y</b>：輸入或對映覆蓋圖的垂直位移。</li> 
   <li><b>重複</b>：輸入<code>loop</code>以導致GIF重複播放。</li> 
   </ul>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">媒體格式</td> 
   <td>選取重新設定影格的視訊格式。</td> 
  </tr>
  <tr> 
   <td role="rowheader">側邊欄格式</td> 
   <td>選取其他中繼資料的格式。</td> 
  </tr>
  <tr> 
   <td role="rowheader">轉譯</td> 
   <td>若要新增其他轉譯，請按一下[新增專案] <b>並輸入轉譯資訊。</b><!--add additional info--></td> 
  </tr>
 </tbody> 
</table>

#### 演算範本

此模組會套用覆寫和匯出預設集，以轉譯一或多個視訊變化。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與Adobe Firefly的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸入範本檔案URL</td> 
   <td>輸入或對應代表您要轉譯之範本的預簽署URL。</td> 
  </tr>
  <tr> 
   <td role="rowheader">字型</td> 
   <td>針對您想要新增的每個字型，按一下[新增專案] <b> </b>，然後輸入字型的Postscript名稱和字型檔案URL。</td> 
  </tr>
  <tr> 
   <td role="rowheader">當缺少字型時</td> 
   <td>選取是否要讓轉譯失敗，或是在缺少字型時使用預設字型。</td> 
  </tr>
  <tr> 
   <td role="rowheader">媒體資產</td> 
   <td>針對您要新增的每個媒體資產，按一下[新增專案] <b> </b>，然後輸入或對應代表資產的預先簽署URL。</td> 
  </tr>
  <tr> 
   <td role="rowheader">匯出預設集</td> 
   <td>針對您想要新增的每個匯出預設集，按一下「新增專案」<b>並選取視訊預設集，然後輸入或對應代表預設集的預先簽署URL。</b></td> 
  </tr>
  <tr> 
   <td role="rowheader">變數</td> 
   <td>針對您想要新增的每個變數，按一下<b>新增專案</b>並輸入變數的詳細資料。 您必須輸入至少一個變數的詳細資訊。<!--add data here--></td> 
  </tr>
  <tr> 
   <td role="rowheader">輸出定義</td> 
   <td>按一下<b>新增專案</b>並選取您要使用哪些新增的變數和預設集，然後新增檔案名稱，以定義輸出。 變異和預設集會編制索引為0 （變異清單中的第一個專案是0，下一個專案是1，以此類推）。</td> 
  </tr>
 </tbody> 
</table>

#### 轉錄媒體

此模組會轉譯音訊或視訊。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly" class="MCXref xref" >建立與Adobe Firefly的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">轉錄型別</td> 
   <td>選取您要轉譯音訊或視訊。   </td> 
  </tr>
  <tr> 
   <td role="rowheader">預先簽署的URL</td> 
   <td>輸入或對應模組將用來輸入的預先簽署URL。   </td> 
  </tr>
  <tr> 
  </tr>
   <td role="rowheader">媒體型別 </td> 
   <td>選取輸入檔案的媒體型別</td> 
  </tr>
  <tr> 
   <td role="rowheader">目標地區設定代碼</td> 
   <td>針對您要新增的每個地區設定代碼，按一下<b>新增專案</b>，然後選取代表您要在結果中使用的語言的地區設定代碼。</td> 
  <tr> 
   <td role="rowheader">註解格式</td> 
   <td>輸入<code>SRT</code>以包含字幕，或若您不要字幕，則保留空白。</td> 
  </tr>
 </tbody> 
</table>




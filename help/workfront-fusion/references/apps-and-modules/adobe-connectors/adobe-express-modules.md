---
title: Adobe Express模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Adobe Express的工作流程。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: eab04db9a38020ed973f98d7f8f290ccd183251c
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 17%

---

# Adobe Express模組

在Adobe Workfront Fusion案例中，您可以自動化使用Adobe Express的工作流程，並將其連結至多個協力廠商應用程式和服務。

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

使用Adobe Express聯結器之前，您必須確保符合下列先決條件：

* 您必須擁有作用中的Adobe Express帳戶。

## 建立與Adobe Express的連線

若要建立Adobe Express模組的連線：

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


## Adobe Express模組及其欄位

設定Adobe Express模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Adobe Express欄位，視您應用程式或服務中的存取層級等因素而定。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 動作

#### 匯出轉譯

此模組會將檔案匯出為JPG或PNG格式。 它可以提供預先簽署的頁面轉譯URL，有效期為四小時。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Express的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >建立與Adobe Express的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">文件</td> 
   <td>選取您要匯出轉譯的檔案。</td> 
  </tr>
  <tr> 
   <td role="rowheader">頁碼</td> 
   <td>輸入或對應您要納入轉譯的頁碼。 轉譯請求所針對之頁碼的逗號分隔字串。 例如，「1,2，3」。 您也可以指定頁面範圍。 例如，「1-3」包括頁面1、2和3。 另一個範例為「1,3-5」，包括第1、3、4和5頁。 「1 — 」可用來指定所有頁面，而「5 — 」表示頁面5到最後一頁。 若未提供，預設會考量第一頁。 頁碼從1開始。</td> 
  </tr>
  <tr> 
   <td role="rowheader">轉譯型別</td> 
   <td>選取您要匯出的轉譯型別：影像、視訊或PDF</td> 
  </tr>
  <tr> 
   <td role="rowheader">格式</td> 
   <td>選取轉譯的檔案格式。</td> 
  </tr>
  <tr> 
   <td role="rowheader">PDF型別</td> 
   <td>如果您要匯出PDF，請選取要匯出標準版還是列印PDF。</td> 
  </tr>
  <tr> 
   <td role="rowheader">大小</td> 
   <td>如果您要匯出影像或視訊，請輸入或對應最長邊的大小（以畫素為單位）。 外觀比例會維持不變。 影像的最小支援大小為1px，最大支援大小為8192px。 若未提供，則會考量頁面的預設大小。</td> 
  </tr>
  <tr> 
   <td role="rowheader">下載個別PDF檔案</td> 
   <td>如果您要匯出PDF，請選取是否要將頁面下載為個別的PDF檔案。 為true時，每個頁面都會下載為自己的PDF檔案。 為false時，所有頁面都會合併至單一PDF檔案中。</td> 
  </tr>
  <tr> 
   <td role="rowheader">設定</td> 
   <td>如果您要匯出PDF，請選取您想要以標準或列印設定來使用PDF。</td> 
  </tr>
  <tr> 
   <td role="rowheader">協助工具標籤</td> 
   <td>如果您要匯出標準PDF，請選取是否在PDF中包含協助工具標籤。</td> 
  </tr>
  <tr> 
   <td role="rowheader">出血</td> 
   <td>如果您要匯出列印PDF，請選取是否要在匯出中包含出血設定</td> 
  </tr>
  <tr> 
   <td role="rowheader">出血設定&gt;數量</td> 
   <td>輸入出血利潤的金額。</td> 
  </tr>
  <tr> 
   <td role="rowheader">出血設定&gt;單位</td> 
   <td>選取量是參照英吋還是公厘。</td> 
  </tr>
  <tr> 
   <td role="rowheader">裁切</td> 
   <td>如果您要匯出列印PDF，請選取是否要在匯出中包含裁切設定</td> 
  </tr>
  <tr> 
   <td role="rowheader">裁切設定&gt;數量</td> 
   <td>輸入裁切邊界的大小。</td> 
  </tr>
  <tr> 
   <td role="rowheader">裁切設定&gt;單位</td> 
   <td>選取量是參照英吋還是公厘。</td> 
  </tr>
 </tbody> 
</table>

#### 產生變數

此模組會根據提供的輸入引數建立檔案變體。 處理之後，它會暫時儲存產生的檔案，並讓使用者在指定的資料夾中可以使用它。 檔案會保留30天的存取時間，之後系統會自動移除檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Express的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >建立與Adobe Express的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">文件</td> 
   <td>選取您要為其產生變體的檔案。</td> 
  </tr>
  <tr> 
   <td role="rowheader">頁碼</td> 
   <td>輸入或對應您要納入轉譯的頁碼。 提出變化要求的頁碼字串（以逗號分隔）。 例如，「1,2，3」。 您也可以指定頁面範圍。 例如，「1-3」包括頁面1、2和3。 另一個範例為「1,3-5」，包括第1、3、4和5頁。 「1 — 」可用來指定所有頁面，而「5 — 」表示頁面5到最後一頁。 若未提供，預設會考量第一頁。 頁碼從1開始。</td> 
  </tr>
  <tr> 
   <td role="rowheader">偏好的檔名稱。</td> 
   <td>輸入或對應新檔案的名稱。 如果您未提供名稱或名稱已在使用中，系統將產生唯一名稱。</td> 
  </tr>
  <tr> 
   <td role="rowheader">專案 ID</td> 
   <td>輸入將儲存變數的專案ID。</td> 
  </tr>
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td>輸入其他欄位的值。 可用欄位取決於所選檔案。</td> 
  </tr>
 </tbody> 
</table>


### 搜尋

#### 擷取標籤檔案

此模組會擷取標籤檔案的清單以及相關中繼資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Express的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >建立與Adobe Express的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">開始索引</td> 
   <td>輸入或對映分頁開始索引。 當您擷取到另一個結果清單，並且要繼續該清單時，請使用此選項。 預設索引為0。</td> 
  </tr>
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個執行週期傳回的最大結果數量。</td> 
  </tr>
  <tr> 
   <td role="rowheader">排序依據</td> 
   <td>選取您要用來排序結果的屬性。</td> 
  </tr>
  <tr> 
   <td role="rowheader">方向</td> 
   <td>選取您要以遞增或遞減方式排序結果。</td> 
  </tr>
 </tbody> 
</table>

#### 擷取檔案詳細資訊

此模組會擷取指定檔案中頁面和標籤元素的詳細資料。 它會傳回檔案頁面的分頁清單以及有關每個頁面的中繼資料。 如果檔案有標籤元素，則API會包含其各自的詳細資料，例如大小和位置。 如果檔案沒有已標籤的元素，則會傳回空白陣列。 回應包括分頁資訊，以協助使用者導覽檔案的頁面。 一個週期最多可傳回10頁。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Express的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >建立與Adobe Express的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">文件</td> 
   <td>選取您要傳回頁面和詳細資訊的檔案。</td> 
  </tr>
  <tr> 
   <td role="rowheader">起始頁面</td> 
   <td>輸入或對應要擷取詳細資料之第一頁的頁碼。</td>

#### 擷取工作狀態

此模組會依作業ID來擷取作業的狀態。 根據工作型別，回應可能包含工作特定的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Express的連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-express" class="MCXref xref" >建立與Adobe Express的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作 ID</td> 
   <td>輸入或對應您要擷取其詳細資訊之作業的ID。</td> 
  </tr>


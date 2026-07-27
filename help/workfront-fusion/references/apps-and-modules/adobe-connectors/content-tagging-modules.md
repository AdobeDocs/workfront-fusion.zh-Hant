---
title: Adobe內容標籤模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Adobe內容標籤的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
source-git-commit: 737e9b07237960d5833cd21e110ef573ddd0a72c
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 20%

---

# Adobe內容標籤模組

在Adobe Workfront Fusion案例中，您可以自動化使用Adobe內容標籤的工作流程，並將其連結至多個協力廠商應用程式和服務。

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

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 建立與Adobe Content Tagger的連線

若要建立Adobe內容標籤模組的連線：

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


## Adobe內容標籤模組及其欄位

當您設定Adobe內容標籤模組時，Workfront Fusion會顯示下列欄位。 除此之外，也會根據您應用程式或服務中的存取層級等因素，顯示其他Adobe內容標籤欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 動作

* [標籤顏色](#tag-colors)
* [標籤關鍵字](#tag-keywords)
* [標籤影像中的文字](#tag-text-in-an-image)

#### 標籤顏色

此模組會傳回不同畫素顏色所涵蓋影像的百分比，並歸類為40種顏色類別。


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Content Tagger的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >建立與Adobe Content Tagger的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像檔案名稱</td> 
   <td>輸入或對應您要標籤顏色的影像檔案名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像資料</td> 
   <td>輸入或對應您要標籤顏色之影像的檔案資料。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">影像格式</td> 
    <td>選取您要標籤顏色的影像型別。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">色彩數目</td> 
    <td>輸入或對應要傳回的顏色數目。 若要傳回所有結果，請輸入0。</p></td> 
  </tr> 
 <tr> 
   <td role="rowheader">最小涵蓋範圍</td> 
   <td>輸入或對應您要標籤顏色的最小涵蓋範圍。 系統只會傳回至少涵蓋此影像量的色彩。 值1是影像的100%，值。5代表影像的50%。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">在擷取前調整影像大小。</td> 
   <td>選取「是」將影像大小調整為320x320，然後再擷取顏色。 選取「否」從完整大小的影像中擷取顏色。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">啟用前景/背景遮色片</td> 
   <td>如果您要分別報告整體影像、前景和背景的顏色，請選取「是」。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">擷取色調</td> 
   <td>如果您要擷取暖色、中性色和冷色調，以及顏色，請選取「是」。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回顏色的最大數量</td> 
   <td>輸入或對應模組在執行一個週期內傳回的最大色彩數量。</td> 
  </tr> 
 </tbody> 
</table>



#### 標籤關鍵字

此模組會擷取最能描述檔案主旨的關鍵字或關鍵片語。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Content Tagger的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >建立與Adobe Content Tagger的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案檔案名稱</td> 
   <td>輸入或對應您要從中擷取關鍵字之檔案的檔案名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像資料</td> 
   <td>輸入或對應您要從中擷取關鍵字之檔案的檔案資料。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">影像格式</td> 
    <td>選取要從中擷取關鍵字的檔案格式。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">應用程式ID</td> 
   <td>輸入或對應檔案的應用程式ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">關鍵片語數量</td> 
   <td>輸入或對應您希望模組傳回的關鍵片語數目。 若要傳回所有結果，請輸入0。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">最低關聯性</td> 
   <td>輸入或對應不會傳回結果的評分臨界值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">關鍵片語長度下限（單字）</td> 
   <td>輸入或對應關鍵短語中所需的最少字數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">關鍵片語長度上限（單字）</td> 
   <td>輸入或對應關鍵短語中所需的最大字數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">語意單位深度</td> 
   <td>選取您要階層式回應移動的深度。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">實體型別</td> 
   <td>針對您想要限制其索引鍵片段的每個實體型別，按一下<b>新增專案</b>並輸入實體型別的資訊。</td> 
  </tr> 
 </tbody> 
</table>

#### 標籤影像中的文字

此模組會指出影像中是否有文字，若有，則會傳回文字。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Content Tagger的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-content-tagger" class="MCXref xref" >建立與Adobe Content Tagger的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像檔案名稱</td> 
   <td>輸入或對應您要從中擷取文字之檔案的檔案名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像資料</td> 
   <td>輸入或對應您要從中擷取文字之檔案的檔案資料。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">影像格式</td> 
    <td>選取要從中擷取文字的檔案格式。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用字典篩選</td> 
   <td>選取是否只傳回英文字典中的單字。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">最小機率</td> 
   <td>輸入或對應最小機率，模組將只傳回至少具有此機率識別的單字。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">關聯性下限</td> 
   <td>輸入傳回文字應涵蓋之影像的最小百分比。 相關性的計算方式為擷取文字的邊界方塊區域與完整影像相較之下的比例。 0.01會翻譯成至少佔影像1%的文字。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應模組將傳回一個執行週期的最大結果數量。</td> 
  </tr> 
 </tbody> 
</table>

---
title: Adobe Firefly 模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Adobe Firefly Lightroom的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3b29ba3d-a769-4e97-b2c2-0b4eeed5b029
source-git-commit: 965cb643039be36eb3608cd801439a6a055974e4
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 16%

---

# Adobe Firefly Lightroom模組

<!--add to tocs-->

在Adobe Workfront Fusion案例中，您可以自動化使用Adobe Firefly Lightroom的工作流程，並將其連結至多個協力廠商應用程式和服務。

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

使用Adobe Firefly Lightroom聯結器之前，您必須確保符合下列先決條件：

* 您必須擁有作用中的Adobe Firefly Lightroom帳戶。

## 建立與Adobe Firefly Lightroom的連線

若要建立Adobe Firefly Lightroom模組的連線：

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


## Adobe Firefly Lightroom模組及其欄位

當您設定Adobe Firefly Lightroom模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Adobe Firefly Lightroom欄位，視您應用程式或服務中的存取層級等因素而定。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [將XMP新增至影像](#add-xmp-to-image)
* [套用Lightroom編輯](#apply-lightroom-edits)
* [套用Lightroom預設集](#apply-lightroom-presets)
* [自動拉直](#auto-straighten)
* [自動色調](#auto-tone)


### 將XMP新增至影像

此模組會將以XMP為基礎的Lightroom預設集套用至影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly Lightroom的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >建立與Adobe Firefly Lightroom的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像URL</td> 
   <td>輸入或對映代表您要套用XMP之影像的預設URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">儲存型別</td> 
   <td>選取影像儲存所在的儲存型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">XMP內容</td> 
   <td>輸入或對應您要新增至影像的XMP內容文字。 這應該是XML字串。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">方向</td> 
    <td>輸入或對應EXIF方向以套用至影像。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出儲存空間</td> 
    <td>選取要儲存輸出檔案的位置。 <p>Fusion內部儲存不會將影像儲存在情境之外，但允許情境中的其他模組存取影像。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出型別</td> 
   <td>選取輸出檔案的檔案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>如果您要允許模組覆寫已經存在的輸出，請選取「是」。 這僅適用於Adobe雲端儲存空間。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">質量</td> 
   <td>輸入或對映輸出影像的品質。 1代表最低品質，12代表最高品質。 這僅適用於JPEG檔案。</td> 
  </tr> 
 </tbody> 
</table>

### 套用Lightroom編輯

此模組會將一或多個Lightroom編輯套用至影像。 編輯包括曝光、對比、銳利度和飽和度。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly Lightroom的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >建立與Adobe Firefly Lightroom的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像URL</td> 
   <td>輸入或對映代表您要套用XMP之影像的預設URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">儲存型別</td> 
   <td>選取影像儲存所在的儲存型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">編輯選項</td> 
   <td>設定您要套用至影像的任何編輯選項。<p>如需選項的詳細資訊，請參閱Adobe Firefly Lightroom API檔案中的<a href="https://developer.adobe.com/firefly-services/docs/lightroom/api/#operation/applyEdits">套用Lightroom編輯</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出儲存空間</td> 
    <td>選取要儲存輸出檔案的位置。 <p>Fusion內部儲存不會將影像儲存在情境之外，但允許情境中的其他模組存取影像。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出型別</td> 
   <td>選取輸出檔案的檔案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>如果您要允許模組覆寫已經存在的輸出，請選取「是」。 這僅適用於Adobe雲端儲存空間。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">質量</td> 
   <td>輸入或對映輸出影像的品質。 1代表最低品質，12代表最高品質。 這僅適用於JPEG檔案。</td> 
  </tr> 
 </tbody> 
</table>

### 套用Lightroom預設集

此模組會使用指定的預設集XMP Lightroom檔案，將一個或多個XMP預設集套用至指定的影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly Lightroom的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >建立與Adobe Firefly Lightroom的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像URL</td> 
   <td>輸入或對映代表您要套用XMP之影像的預設URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">儲存型別</td> 
   <td>選取影像儲存所在的儲存型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">預設集</td> 
   <td>針對您要套用的每個預設集，按一下<b>新增專案</b>，輸入預設集的預先簽署URL，然後選取其儲存型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出儲存空間</td> 
    <td>選取要儲存輸出檔案的位置。 <p>Fusion內部儲存不會將影像儲存在情境之外，但允許情境中的其他模組存取影像。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出型別</td> 
   <td>選取輸出檔案的檔案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>如果您要允許模組覆寫已經存在的輸出，請選取「是」。 這僅適用於Adobe雲端儲存空間。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">質量</td> 
   <td>輸入或對映輸出影像的品質。 1代表最低品質，12代表最高品質。 這僅適用於JPEG檔案。</td> 
  </tr> 
 </tbody> 
</table>

### 自動拉直

此模組會套用自動直立變形來自動拉直影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly Lightroom的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >建立與Adobe Firefly Lightroom的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像URL</td> 
   <td>輸入或對映代表您要套用XMP之影像的預設URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">儲存型別</td> 
   <td>選取影像儲存所在的儲存型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">直立模式</td> 
   <td>選取您要使用的直立模式型別。 如果您未設定值，則會自動提供適當的模式。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">限制裁切</td> 
   <td>選取是否應裁切已拉直的影像，以移除所有空白邊緣。</td> 
  </tr> 
 <tr> 
   <td role="rowheader">輸出儲存</td> 
    <td>選取要儲存輸出檔案的位置。 <p>Fusion內部儲存不會將影像儲存在情境之外，但允許情境中的其他模組存取影像。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出型別</td> 
   <td>選取輸出檔案的檔案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>如果您要允許模組覆寫已經存在的輸出，請選取「是」。 這僅適用於Adobe雲端儲存空間。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">質量</td> 
   <td>輸入或對映輸出影像的品質。 1代表最低品質，12代表最高品質。 這僅適用於JPEG檔案。</td> 
  </tr> 
 </tbody> 
</table>


### 自動色調

此模組會自動校正影像的曝光、對比、銳利度和飽和度。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td>如需建立與Adobe Firefly Lightroom的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-firefly-lightroom" class="MCXref xref" >建立與Adobe Firefly Lightroom的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">影像URL</td> 
   <td>輸入或對映代表您要套用XMP之影像的預設URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">儲存型別</td> 
   <td>選取影像儲存所在的儲存型別。</td> 
  </tr> 
  </tr> 
 <tr> 
   <td role="rowheader">輸出儲存空間</td> 
    <td>選取要儲存輸出檔案的位置。 <p>Fusion內部儲存不會將影像儲存在情境之外，但允許情境中的其他模組存取影像。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出型別</td> 
   <td>選取輸出檔案的檔案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>如果您要允許模組覆寫已經存在的輸出，請選取「是」。 這僅適用於Adobe雲端儲存空間。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">質量</td> 
   <td>輸入或對映輸出影像的品質。 1代表最低品質，12代表最高品質。 這僅適用於JPEG檔案。</td> 
  </tr> 
 </tbody> 
</table>



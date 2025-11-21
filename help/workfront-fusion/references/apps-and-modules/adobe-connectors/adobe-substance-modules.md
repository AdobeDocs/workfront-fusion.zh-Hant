---
title: Adobe Substance模組
description: 在 Adobe Workfront Fusion 情境中，您可以將使用  [!DNL Adobe Substance] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
source-git-commit: 2e44c89d487100b3245b40f6927185a0ff12ef2f
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 32%

---

# [!DNL Adobe Substance]模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Adobe Substance] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

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

使用[!DNL Adobe Substance]聯結器之前，您必須確定符合下列先決條件：

* 您必須擁有使用中的[!DNL Adobe Substance]帳戶。



## [!DNL Adobe Substance] 模組及其欄位

當您設定 [!DNL Adobe Substance] 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Adobe Substance] 欄位。模組中欄位名稱旁的星號表示必填欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [複合](#composites)
* [場景](#scenes)
* [空間](#spaces)

### 複合

#### 產生3D物件複合

此動作模組會為3D複合產生內容，其中包含選取的主圖資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需將您的[!DNL Adobe Substance]帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td>視需要設定其他欄位。 如需欄位的詳細資訊，請參閱<a href="https://s3d.adobe.io/docs#/operations/v1/composites/compose">Adobe Substance API檔案</a>。</td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">Camera name</td> 
   <td>Enter or map the name of an existing camera that has been previously defined in the source 3D file.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Content class</td> 
   <td>Select whether you want the composite to have the style of art or of a photo.</td> 
  </tr> 
  <tr> 
   <td role="rowheader">Enable ground plane</td> 
   <td>Enable this to enable the auto-generated ground plane under the hero asset. This is useful if the 3D scene contains only a hero asset, without additional elements.</td> 
  </tr> -->
 </tbody> 
</table>

### 場景

* [轉換三維檔案](#convert-3d-files)
* [建立3D場景](#create-3d-scene)
* [描述3D場景](#describe-3d-scene)
* [呈現3D物件](#render-3d-object)
* [呈現3D物件（基本版本）](#render-3d-object-basic-version)

#### 轉換三維檔案

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需將您的[!DNL Adobe Substance]帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">格式</td> 
   <td>選取您要轉換檔案的格式。</td> 
  </tr> 
<tr> 
   <td role="rowheader">模型進入點</td> 
   <td>轉換通常需要第一個被視為有效3D模型的檔案。 定義此進入點，以便在有多個選項時消除混淆。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">來源</td> 
   <td>針對您要轉換的每個檔案，按一下<b>新增專案</b>並輸入檔案資訊。</td> 
  </tr> 
 </tbody> 
</table>

#### 建立3D場景

此動作模組會使用您指定的資產建立場景。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需將您的[!DNL Adobe Substance]帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
  </tr> 
   <td role="rowheader">編碼</td> 
   <td>選取場景的檔案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案基底名稱</td> 
   <td>輸入或對應輸出檔案的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td>視需要設定其他欄位。 如需欄位的詳細資訊，請參閱<a href="https://s3d.adobe.io/docs#/operations/v1/scenes/assemble">Adobe Substance API檔案</a>。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">來源</td> 
   <td>針對您想要使用的每個檔案，按一下<b>新增專案</b>並輸入檔案資訊。</td> 
  </tr> 
 </tbody> 
</table>

#### 描述3D場景

此動作模組會擷取3D場景內容的相關資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需將您的[!DNL Adobe Substance]帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
  </tr> 
   <td role="rowheader">場景檔案</td> 
   <td>輸入或對應路徑至您要說明的場景檔案。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">來源</td> 
   <td>針對您想要說明的每個檔案，按一下<b>新增專案</b>並輸入檔案資訊。</td> 
  </tr> 
 </tbody> 
</table>

#### 呈現3D物件

此動作模組會呈現場景的影像。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需將您的[!DNL Adobe Substance]帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
   <td role="rowheader">其他欄位</td> 
   <td>視需要設定其他欄位。 如需欄位的詳細資訊，請參閱<a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render">Adobe Substance API檔案</a>。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">來源</td> 
   <td>針對您想要使用的每個檔案，按一下<b>新增專案</b>並輸入檔案資訊。</td> 
  </tr> 
 </tbody> 
</table>

#### 呈現3D物件（基本版本）

此動作模組會轉譯場景的影像，但選項少於「轉譯3D物件」模組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需將您的[!DNL Adobe Substance]帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
   <td role="rowheader">其他欄位</td> 
   <td>視需要設定其他欄位。 如需欄位的詳細資訊，請參閱<a href="https://s3d.adobe.io/docs#/operations/v1/scenes/render-basic">Adobe Substance API檔案</a>。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">來源</td> 
   <td>針對您想要使用的每個檔案，按一下<b>新增專案</b>並輸入檔案資訊。</td> 
  </tr> 
 </tbody> 
</table>

### 空間

#### 建立空間

此動作模組可讓您上傳及暫時儲存檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需將您的[!DNL Adobe Substance]帳戶連線到Workfront Fusion的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立與Adobe Workfront Fusion的連線 — 基本指示</a>。</p> </td> 
  </tr> 
   <td role="rowheader">檔案名稱</td> 
   <td>輸入或對應正在上傳的檔案名稱。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">檔案資料</td> 
   <td>輸入或對應檔案的二進位資料。</td> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱</td> 
   <td>輸入或對映多部分表單值的名稱。</td> 
  </tr> 
 </tbody> 
</table>

---
title: 圖形模組
description: 使用Adobe Workfront Fusion Figma模組，您可以擷取註解、檔案、檔案版本或專案的清單。 您也可以張貼註解或呼叫Figma API。
author: Becky
feature: Workfront Fusion
exl-id: 1220460b-1957-4dfc-b7c1-4c97b36ea061
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2600'
ht-degree: 0%

---

# [!DNL Figma]模組

使用Adobe Workfront Fusion [!DNL Figma]模組，您可以擷取註解、檔案、檔案版本或專案的清單。 您也可以張貼註解或呼叫[!DNL Figma] API。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

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

若要使用[!DNL Figma]模組，您必須有[!DNL Figma]帳戶。

## 圖表API資訊

Figma聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://api.figma.com/v1</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.8.25</td> 
  </tr>
 </tbody> 
 </table>

## 建立與Figma的連線

若要建立Figma模組的連線：

1. 在任何Figma模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

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
          <p> 若為新連線，請選取不含舊版標籤的<code>Figma</code>。 </p><p>Figma已於2025年1月變更其驗證要求。 <code>Figma</code>連線型別符合新需求。 <code>Figma (Legacy)</code>連線型別將在未來移除。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的[!UICONTROL 組圖] [!UICONTROL 使用者端ID]。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的Figma [!UICONTROL 使用者端密碼]。</td>
        </tr>
        <tr>
        <td role="rowheader">自訂範圍</td>
        <td>輸入此連線所需的任何自訂範圍。</td>
        </tr>
        <tr>
        <td role="rowheader">自訂連線驗證URL</td>
        <td>驗證連線是否成功建立的預設端點為： <code>https://api.figma.com/v1/me</code>如果自訂範圍不支援此URL，請提供自訂驗證URL。</td>
        </tr>
      </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。



## [!DNL Figma]模組及其欄位

當您設定[!DNL Figma]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Figma]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [註解](#comments)

* [專案和檔案](#projects-and-files)

* [元件和樣式](#components-and-styles)

* [其他](#other)


### 註解

* [刪除評論](#delete-a-comment)

* [列出註解](#list-comments)

* [發表評論](#post-a-comment)


#### [!UICONTROL 刪除註解]

此動作模組會從檔案中刪除單一註解。

<table style="table-layout:auto"> 
  <col/>
  <col />
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案ID]</td>
      <td>輸入或對應您要新增或刪除註解的檔案的檔案ID。 </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 註解ID]</td>
      <td>輸入要刪除的註解文字。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出註解]

此搜尋模組列出附加至[!DNL Figma]中單一檔案的所有註解。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案ID]</td>
      <td>
        <p>輸入或對應您要擷取註解的檔案的檔案ID。 </p>
        <ul>
          <li>
            <p>如果您不知道識別碼，請按一下<b>[!UICONTROL 尋找檔案]</b>，然後輸入或對應檔案關聯之專案的識別碼，然後選取檔案。</p>
          </li>
          <li>
            <p>如果您不知道專案的ID，請按一下<b>[!UICONTROL 尋找專案]</b>，然後輸入或對應擁有檔案相關聯專案之團隊的ID，然後選取專案，再選取檔案。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 傳回評論的最大數量]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大註解數。</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL 張貼註解]

此動作模組會將註解張貼至Figma檔案。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    </tr>
    <tr>
      <td  role="rowheader">[!UICONTROL 檔案ID]</td>
      <td>
        <p>輸入或對應您要張貼註解的檔案的檔案ID。 </p>
        <ul>
          <li>
            <p>如果您不知道檔案的識別碼，請按一下<b>[!UICONTROL 尋找檔案]</b>，然後輸入或對應與檔案關聯的專案識別碼，然後選取檔案。</p>
          </li>
          <li>
            <p>如果您嘗試尋找檔案的ID但不知道專案的ID，請按一下<b>[!UICONTROL 尋找專案]</b>，然後輸入或對應擁有檔案相關專案之團隊的ID。 選取專案，然後選取檔案。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 註解]</td>
      <td>輸入註解的文字。</td>
    </tr>
  </tbody>
</table>


### 專案和檔案

* [取得檔案或影像](#get-a-file-or-image)

* [列出檔案版本記錄](#list-file-version-history)

* [列出專案檔案](#list-project-files)

* [列出專案](#list-projects)


#### [!UICONTROL 取得檔案或影像]

此動作模組會從Figma程式庫中擷取單一檔案或影像

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 物件型別]</td>
      <td>
        <p>選取您要擷取的物件型別。</p>
        <ul>
          <li>
            <p><b>[!UICONTROL 檔案]</b>
            </p>
            <p>模組會傳回[!UICONTROL Key]參考的檔案作為JSON物件。 您可以從任何Figma檔案URL剖析檔案金鑰。</p>
            <p>如需欄位，請參閱<a href="#get-a-file-or-image-file" class="MCXref xref" >[!UICONTROL 取得檔案或影像：檔案]</a>。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 檔案節點]</b>
            </p>
            <p>傳回ID參照的節點作為JSON物件。 節點是從[!UICONTROL Key]參考的[!DNL Figma]檔案擷取。</p>
            <p>如需欄位，請參閱<a href="#get-a-file-or-image-file-nodes" class="MCXref xref" >[!UICONTROL 取得檔案或影像：檔案節點]</a>。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 影像]</b>
            </p>
            <p>模組會從檔案轉譯影像。</p>
            <p>如需欄位，請參閱<a href="#get-a-file-or-image-image" class="MCXref xref" >[!UICONTROL 取得檔案或影像： Image]</a>。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 影像填滿]</b>
            </p>
            <p>模組會傳回檔案中影像填色中所有影像的下載連結。 影像填色是[!DNL Figma]表示任何使用者提供的影像的方式。 當您將影像拖曳至[!DNL Figma]中時，[!DNL Figma]會建立具有單一填色的矩形（代表影像），使用者可以轉換矩形（和填色上的屬性）。</p>
            <p>如需欄位，請參閱<a href="#get-a-file-or-image-image-fills" class="MCXref xref" >[!UICONTROL 取得檔案或影像：影像填滿]</a>。</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>


##### 取得檔案或影像：檔案

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案索引鍵]</td>
      <td>選取您要傳回JSON的來源檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 版本ID]</td>
      <td>輸入或對應您希望模組傳回的檔案版本。 對於目前的模組，請將此欄位留空。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 節點ID]</td>
      <td>
        <p>若只要傳回檔案的子集，請輸入您希望模組傳回的節點。 模組會傳回列出的節點、其子系，以及根節點與列出的節點之間的任何專案。</p>
        <p>針對您要傳回的每個節點，按一下<b>[!UICONTROL 新增]</b>並輸入節點的文字。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 深度]</td>
      <td>
        <p>輸入或對應整數，該整數代表要傳回結果的檔案樹狀結構深度。 </p>
        <div class="example"><span class="autonumber"><span><b>範例： </b></span></span>
          <ul>
            <li>
              <p>若要僅傳回頁面，請輸入<code>1</code>。</p>
            </li>
            <li>
              <p>若要傳回頁面和最上層物件，請輸入<code>2</code>。</p>
            </li>
          </ul>
        </div>
        <p>若要傳回所有節點，請將此欄位留空。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Geometry]</td>
      <td>若要傳回向量資料，請輸入<code>paths</code>。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 外掛程式資料]</td>
      <td>外掛程式ID和/或字串「[!UICONTROL shared]」的逗號分隔清單。 這些外掛程式所撰寫的檔案中的任何資料都會包含在<code>pluginData</code>和<code>sharedPluginData</code>屬性的結果中。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 分支資料]</td>
      <td>啟用此選項可傳回請求檔案的分支中繼資料。 如果檔案是分支，則主要檔案的金鑰會包含在傳回的回應中。 如果檔案有分支，則其中繼資料會包含在傳回的回應中。 預設值： <code>false</code>。</td>
    </tr>
  </tbody>
</table>

##### 取得檔案或影像：檔案節點

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案索引鍵]</td>
      <td>選取您要傳回JSON的來源檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 節點ID]</td>
      <td>
        <p>輸入您希望模組傳回並轉換的節點</p>
        <p>針對您要傳回的每個節點，按一下<b>[!UICONTROL 新增]</b>並輸入節點的文字。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 版本ID]</td>
      <td>輸入或對應您希望模組傳回的檔案版本。 對於目前的模組，請將此欄位留空。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 深度]</td>
      <td>
        <p>輸入或對應整數，該整數代表要傳回結果的檔案樹狀結構深度。 </p>
        <div class="example"><span class="autonumber"><span><b>範例： </b></span></span>
          <ul>
            <li>
              <p>若要僅傳回頁面，請輸入<code>1</code>。</p>
            </li>
            <li>
              <p>若要傳回頁面和最上層物件，請輸入<code>2</code>。</p>
            </li>
          </ul>
        </div>
        <p>若要傳回所有節點，請將此欄位留空。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Geometry]</td>
      <td>若要傳回向量資料，請輸入<code>paths</code>。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 外掛程式資料]</td>
      <td>外掛程式ID和/或「共用」字串的逗號分隔清單。 這些外掛程式所撰寫的檔案中的任何資料都會包含在pluginData和sharedPluginData屬性的結果中。</td>
    </tr>
  </tbody>
</table>


##### 取得檔案或影像：影像

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案索引鍵]</td>
      <td>選取您要傳回JSON的來源檔案。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 節點ID]</td>
      <td>
        <p>輸入您希望模組呈現的節點。</p>
        <p>針對您要呈現的每個節點，按一下<b>[!UICONTROL 新增]</b>並輸入節點的文字。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 縮放]</td>
      <td>若要縮放影像，請輸入或對應縮放係數。 此數字必須介於0.01到4之間。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 格式]</td>
      <td>
        <p>選取影像輸出的格式。</p>
        <ul>
          <li>
            <p>JPG</p>
          </li>
          <li>
            <p>PNG</p>
          </li>
          <li>
            <p>SVG</p>
          </li>
          <li>
            <p>PDF</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SVG — 包含ID]</td>
      <td>啟用此選項即可包含所有SVG元素的ID屬性。 預設值： [!UICONTROL false]。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SVG — 簡化筆畫]</td>
      <td>啟用此選項可簡化內/外筆畫，並儘可能使用筆畫屬性而非&lt;mask&gt;。 預設值： [!UICONTROL true]。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 使用絕對界限]</td>
      <td>啟用此選項可使用節點的完整尺寸，無論節點是否裁切或周圍空間是空的。 使用此項可匯出文位元組點而不進行裁切。 預設值： [!UICONTROL false]。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 版本]</td>
      <td>輸入或對應您希望模組傳回的檔案版本。 對於目前的模組，請將此欄位留空。</td>
    </tr>
  </tbody>
</table>

##### 取得檔案或影像：影像填色

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案索引鍵]</td>
      <td>選取您要傳回JSON的來源檔案。</td>
    </tr>
  </tbody>
</table>

### [!UICONTROL 列出檔案版本記錄]

此搜尋模組傳回[!UICONTROL Figma]中單一檔案的版本記錄。
<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案ID]</td>
      <td>
        <p>輸入或對應您要擷取版本記錄的檔案的檔案ID。 </p>
        <ul>
          <li>
            <p>如果您不知道檔案的識別碼，請按一下<b>[!UICONTROL 尋找檔案]</b>，然後輸入或對應與檔案關聯的專案識別碼，然後選取檔案。</p>
          </li>
          <li>
            <p>如果您嘗試尋找檔案的ID但不知道專案的ID，請按一下<b>[!UICONTROL 尋找專案]</b>，然後輸入或對應擁有檔案相關專案之團隊的ID。 選取專案，然後選取檔案。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 傳回檔案的最大數量]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出專案檔]

此搜尋模組會傳回指定專案中所有檔案的清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案ID]</td>
      <td>
        <p>輸入或對映您要擷取檔案的專案之專案ID。 </p>
        <ul>
          <li>
            <p>如果您不知道專案的ID，請按一下<b>[!UICONTROL 尋找專案]</b>，然後輸入或對應專案相關團隊的ID，然後選取專案。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 傳回檔案的最大數量]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出專案]

此搜尋模組會傳回指定團隊中所有專案的清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 團隊ID]</td>
      <td>輸入或對應您要擷取檔案之專案的專案ID。 團隊ID可在菲格瑪團隊頁面的URL中找到</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 傳回專案的最大數量]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>


### 元件和樣式

#### [!UICONTROL 取得樣式或元件]

此動作模組會擷取單一樣式或元件，或一組樣式或元件。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    </tr>
    <tr>
      <td role="rowheader">Object&gt;型別</td>
      <td>選取您要擷取的物件型別。</td>
    </tr>
    <tr>
      <td role="rowheader">&lt;[!UICONTROL Object&gt;鍵]</td>
      <td>輸入您要擷取之物件的金鑰（唯一識別碼）。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 團隊ID]</td>
      <td>如果擷取專案團隊元件或專案團隊元件集，請輸入或對應與記錄關聯的專案團隊ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 頁面大小]</td>
      <td>如果擷取群組元件或群組元件集，請輸入或對應每頁要傳回的數目或結果。 預設值： 30。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL After]</td>
      <td>
        <p>如果擷取群組元件或群組元件集，請輸入或對映結果數目，之後將開始擷取結果。 這可以與[!UICONTROL 頁面大小]欄位結合以分頁結果。</p>
        <p>此值未對應至物件ID。</p>
        <p>此欄位不能與[!UICONTROL Before]欄位結合使用。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Before]</td>
      <td>
        <p>如果擷取群組元件或群組元件集，請輸入或對應要開始擷取結果之前的結果數目。 這可以與[!UICONTROL 頁面大小]欄位結合以分頁結果。</p>
        <p>此值未對應至物件ID。</p>
        <p>此欄位不能與[!UICONTROL After]欄位結合使用。</p>
      </td>
    </tr>
  </tbody>
</table>


### 其他

* [進行API呼叫](#make-an-api-call)

* [觀看活動](#watch-events)


#### [!UICONTROL 進行API呼叫]

此動作模組可讓您對Figma API發出自訂的已驗證呼叫，而不需思考驗證問題。 如此一來，您就可以建立其他Figma模組無法完成的資料流程自動化。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將您的[!DNL Figma]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#create-a-connection-to-figma" class="MCXref xref" data-mc-variable-override="">建立與Figma的連線</a>。</p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>輸入相對於<code>https://api.figma.com/v1/</code>的路徑。</p>
        <p>例如： <code>[!DNL files/7179110/comments]</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 方法]</td>
      <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會為您新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 查詢字串]</td>
      <td>
        <p>以標準JSON物件的形式新增API呼叫的查詢。</p>
        <p>例如： <code>{"name":"something-urgent"}</code></p>
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

#### [!UICONTROL 觀看活動]

當您的[!DNL Figma]團隊空間中的特定團隊發生下列其中一項事件時，此觸發模組就會啟動案例：

* 檔案更新

* 檔案版本更新

* 檔案刪除

* 程式庫發佈

* 檔案註解

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>
        <p>選取模組要監視的webhook。</p>
        <p>若要新增webhook：</p>
        <ol>
          <li>
            <p>按一下[!UICONTROL Webhook]欄位旁的<b>[!UICONTROL Add]</b>。</p>
          </li>
          <li>
            <p>輸入webhook的名稱。</p>
          </li>
          <li>
            <p>選取您要用於此webhook的連線。 如需有關將[!DNL Figma]帳戶連線至[!UICONTROL Workfront Fusion]的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!UICONTROL Adobe Workfront Fusion]的連線 — 基本說明。</a></p>
          </li>
          <li>
            <p>選取您要模組觀看的事件型別。</p>
          </li>
          <li>
            <p>輸入您希望webhook觀看其事件的團隊識別碼。</p>
          </li>
          <li>
            <p>選取您想要啟動或暫停webhook。</p>
          </li>
          <li>
            <p>輸入webhook的說明。</p>
          </li>
          <li>
            <p>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。</p>
          </li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>

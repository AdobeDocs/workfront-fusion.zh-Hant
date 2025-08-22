---
title: Adobe Creative Cloud程式庫模組
description: 使用 [!DNL Adobe Workfront Fusion Adobe Creative Cloud] 程式庫模組，您可以在建立或更新元素或程式庫時啟動案例。 您也可以上傳、擷取、封存或列出元素，或呼叫 [!DNL Adobe Creative Cloud Libraries] API。
author: Becky
feature: Workfront Fusion
exl-id: 85607e4e-538a-427f-8a99-a0ab65a75ac2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1404'
ht-degree: 1%

---

# Adobe Creative Cloud程式庫模組

使用Adobe Workfront Fusion [!DNL Adobe Creative Cloud Libraries]模組，您可以在建立或更新元素或程式庫時啟動案例。 您也可以上傳、擷取、封存或列出元素，或呼叫[!DNL Adobe Creative Cloud Libraries] API。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

>[!IMPORTANT]
>
>Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。

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
   <p>新增:</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL Adobe Creative Cloud Libraries]模組，您必須有[!UICONTROL Adobe Creative Cloud]帳戶。

## Adobe Creative Cloud Libraries API資訊

Adobe Creative Cloud Libraries聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>https://cc-libraries.adobe.io/api/v1</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.1.7</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL Adobe Creative Cloud Libraries]模組及其欄位

當您設定[!UICONTROL Adobe Creative Cloud Libraries]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe Creative Cloud Libraries]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [元素](#elements)

* [程式庫](#libraries)

* [其他](#other)


### 元素

* [[!UICONTROL 封存元素]](#archive-an-element)

* [[!UICONTROL 取得專案]](#get-an-element)

* [[!UICONTROL 列出專案]](#list-elements)

* [[!UICONTROL 上傳元素]](#upload-an-element)

* [！UICONTROL [在程式庫中監視新元素]](#watch-new-element-in-library)

* [[!UICONTROL 觀看更新的元素]](#watch-updated-elements)


#### [!UICONTROL 封存元素]

此動作模組會從程式庫中封存元素。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL資料庫ID]</td>
      <td >選取或對應包含您要封存之元素的程式庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL元素ID]</td>
      <td>選取或對應您要封存的元素。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 取得專案]

此動作模組會從程式庫中傳回單一元素。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL資料庫ID]</td>
      <td>選取或對應包含您要擷取之元素的程式庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL元素ID]</td>
      <td>輸入或對應您要擷取之元素的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL選擇器]</td>
      <td>
        <p>選取模組傳回的資訊型別。 </p>
        <ul>
          <li>
            <p><b>[！UICONTROL預設值]</b>
            </p>
            <p>基礎資料</p>
          </li>
          <li>
            <p><b>[！UICONTROL詳細資料]</b>
            </p>
            <p>所有可用資料</p>
          </li>
          <li>
            <p><b>[！UICONTROL代表]</b>
            </p>
            <p>與資料庫元素相關聯的平面化資產清單</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出專案]

此動作模組會擷取程式庫中元素的清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL資料庫ID]</td>
      <td >選取或對應您要列出其元素的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL Order by]</td>
      <td>選取您要依名稱排序結果，還是要依上次修改元素的日期排序。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL型別]</td>
      <td >輸入或對應MIME型別，將結果限製為使用指定MIME型別識別的元素。 範例：<code>string</code>。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL選擇器]</td>
      <td>
        <p>選取模組傳回的資訊型別。 </p>
        <ul>
          <li>
            <p><b>[！UICONTROL預設值]</b>
            </p>
            <p>基礎資料</p>
          </li>
          <li>
            <p><b>[！UICONTROL詳細資料]</b>
            </p>
            <p>所有可用資料</p>
          </li>
          <li>
            <p><b>[！UICONTROL代表]</b>
            </p>
            <p>與資料庫元素相關聯的平面化資產清單</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL限制]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 觀看資料庫中的新元素]

此觸發模組會在元素新增至程式庫時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL資料庫ID]</td>
      <td >選取您要監視更新元素的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL限制]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL 觀看更新的元素]

此觸發模組會在程式庫中的元素更新時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL資料庫ID]</td>
      <td >選取您要監視新元素的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL限制]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

### 程式庫

* [[!UICONTROL 觀看新資料庫]](#watch-new-libraries)

* [[!UICONTROL 觀看更新的資料庫]](#watch-updated-libraries)


#### [!UICONTROL 觀看新資料庫]

此觸發模組會在建立新程式庫時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL限制]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 觀看更新的資料庫]

此觸發模組會在現有程式庫更新時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL限制]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

### 其他

* [進行API呼叫](#make-an-api-call)
* [上傳資產](#upload-an-asset)

#### [!UICONTROL 進行API呼叫]

此模組會對[!DNL Adobe Creative Cloud Libraries] API發出自訂API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td> <p>如需有關將Adobe Creative Cloud帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明。</a></p>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL URL]</td>
      <td>
        <p>輸入相對於<code>https://cc-libraries.adobe.io/api</code>的路徑。</p>
    <p>例如 <code>/v1/libraries</code>.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL API版本]</td>
      <td>
        <p>選取您要連線的[!DNL Adobe Analytics] API版本。</p>
      </td>
    </tr>    <tr>
      <td role="rowheader">[！UICONTROL方法]</td>
      <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會為您新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL查詢字串]</td>
      <td>
        <p>以標準JSON物件的形式新增API呼叫的查詢。</p>
        <p>例如： <code>{"name":"something-urgent"}</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL Body]</td>
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
       <tr>
      <td role="rowheader">[！UICONTROL上傳暫時性檔案]</td>
      <td>
      <p>如果要上傳暫時性檔案，請輸入要上傳檔案的來源檔案。</p>
      <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p>
    </td>
    </tr>
</tbody>
</table>


#### [!UICONTROL 上傳資產]

此動作模組會將小型檔案資產上傳至現有程式庫。 檔案大小上限為1 GB。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[！UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL資料庫ID]</td>
      <td >選取您要上傳資產的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL呼叫模式]</td>
      <td>
        <p>選取要用來叫用此要求程式的處理模式。</p>
        <ul>
          <li>
            <p><b>[！UICONTROL同步]</b>
            </p>
            <p>API呼叫會同步處理。 處理完成時會傳送回應（除非呼叫逾時）。</p>
          </li>
          <li>
            <p><b>[！UICONTROL async]</b>
            </p>
            <p>系統會立即傳回非同步監視器回應，且非同步處理請求。 呼叫負責輪詢端點，直到完成。</p>
          </li>
          <li>
            <p><b>[！UICONTROL sync，async]</b> （預設）</p>
            <p>已嘗試同步處理請求。 當處理過程延長超過5000毫秒時，將傳回非同步監視器回應。 應輪詢監視URL，直到請求完成。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL元素型別]</td>
      <td >選取您要上傳的元素型別</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL檔案型別]</td>
      <td >輸入或對應已上傳檔案的MIME型別。</td>
    </tr>
    <tr>
      <td role="rowheader">[！UICONTROL Source檔案]</td>
      <td>
        <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p>
      </td>
    </tr>
  </tbody>
</table>






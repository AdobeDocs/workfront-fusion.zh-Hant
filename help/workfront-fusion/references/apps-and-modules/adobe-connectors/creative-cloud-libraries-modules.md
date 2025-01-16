---
title: Adobe Creative Cloud程式庫模組
description: 使用 [!DNL Adobe Workfront Fusion Adobe Creative Cloud] 程式庫模組，您可以在建立或更新元素或程式庫時啟動案例。 您也可以上傳、擷取、封存或列出元素，或呼叫 [!DNL Adobe Creative Cloud Libraries] API。
author: Becky
feature: Workfront Fusion
exl-id: 85607e4e-538a-427f-8a99-a0ab65a75ac2
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 0%

---

# Adobe Creative Cloud程式庫模組

使用[!DNL Adobe Workfront Fusion] [!DNL Adobe Creative Cloud Libraries]模組，您可以在建立或更新元素或程式庫時啟動案例。 您也可以上傳、擷取、封存或列出元素，或呼叫[!DNL Adobe Creative Cloud Libraries] API。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

>[!IMPORTANT]
>
>Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
      <td>
        <p>[!UICONTROL Pro] 或更高</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
      <td>
        <p>[!UICONTROL Plan]， [!UICONTROL Work]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td>
      <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td>
    </tr>
    <tr>
      <td role="rowheader">產品</td>
      <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td>
    </tr>
  </tbody>
</table>


若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 先決條件

若要使用[!DNL Adobe Creative Cloud Libraries]模組，您必須有[!UICONTROL Adobe Creative Cloud]帳戶。

## Adobe Creative Cloud Libraries API資訊

Adobe Creative Cloud Libraries聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td>https://cc-libraries.adobe.io/api/v1</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.1.7</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL Adobe Creative Cloud Libraries]模組及其欄位

當您設定[!UICONTROL Adobe Creative Cloud Libraries]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe Creative Cloud Libraries]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [元素](#elements)

* [資料庫](#libraries)

* [其他](#other)


### 元素

* [[!UICONTROL Archive an Element]](#archive-an-element)

* [[!UICONTROL Get an Element]](#get-an-element)

* [[!UICONTROL List Elements]](#list-elements)

* [[!UICONTROL Upload an Element]](#upload-an-element)

* [！UICONTROL [在程式庫中監視新元素]](#watch-new-element-in-library)

* [[!UICONTROL Watch Updated Elements]](#watch-updated-elements)


#### [!UICONTROL Archive an Element]

此動作模組會從程式庫中封存元素。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >選取包含您要封存之元素的程式庫。</td>
    </tr>
    <tr>
      <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-LightGray" role="rowheader">[!UICONTROL Element ID]</td>
      <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-LightGray">選取您要封存的元素。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Get an Element]

此動作模組會從程式庫中傳回單一元素。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >選取包含您要擷取之元素的程式庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Element ID]</td>
      <td>輸入或對應您要擷取之元素的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>選取模組傳回的資訊型別。 </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>基礎資料</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>所有可用資料</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>與資料庫元素相關聯的平面化資產清單</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL List Elements]

此動作模組會擷取程式庫中元素的清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >選取您要列出其元素的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Order by]</td>
      <td>選取您要依名稱或上次修改元素的日期來排序結果。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Type]</td>
      <td >輸入MIME型別，將結果限製為使用指定MIME型別識別的元素。 範例： <code>string</code>。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selector]</td>
      <td>
        <p>選取模組傳回的資訊型別。 </p>
        <ul>
          <li>
            <p><b>[!UICONTROL Default]</b>
            </p>
            <p>基礎資料</p>
          </li>
          <li>
            <p><b>[!UICONTROL Details]</b>
            </p>
            <p>所有可用資料</p>
          </li>
          <li>
            <p><b>[!UICONTROL Representations]</b>
            </p>
            <p>與資料庫元素相關聯的平面化資產清單</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Upload an Element]

此動作模組會將小型檔案資產上傳至現有程式庫。 檔案大小上限為1 GB。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >選取您要列出其元素的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Invocation Mode]</td>
      <td>
        <p>選取要用來叫用此要求程式的處理模式。</p>
        <ul>
          <li>
            <p><b>[!UICONTROL sync]</b>
            </p>
            <p>API呼叫會同步處理。 處理完成時會傳送回應（除非呼叫逾時）。</p>
          </li>
          <li>
            <p><b>[!UICONTROL async]</b>
            </p>
            <p>系統會立即傳回非同步監視器回應，且非同步處理請求。 呼叫負責輪詢端點，直到完成。</p>
          </li>
          <li>
            <p><b>[!UICONTROL sync,async]</b> （預設）</p>
            <p>已嘗試同步處理請求。 當處理過程延長超過5000毫秒時，將傳回非同步監視器回應。 應輪詢監視URL，直到請求完成。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Type File]</td>
      <td >輸入或對應已上傳檔案的MIME型別。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Source File]</td>
      <td>
        <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Watch New Element in Library]

此觸發模組會在元素新增至程式庫時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >選取您要監視更新元素的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>


#### [!UICONTROL Watch Updated Elements]

此觸發模組會在程式庫中的元素更新時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Library ID]</td>
      <td >選取您要監視新元素的資料庫。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

### 資料庫

* [[!UICONTROL Watch New Libraries]](#watch-new-libraries)

* [[!UICONTROL Watch Updated Libraries]](#watch-updated-libraries)


#### [!UICONTROL Watch New Libraries]

此觸發模組會在建立新程式庫時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL Watch Updated Libraries]

此觸發模組會在現有程式庫更新時啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>選取現有的Creative Cloud Libraries連線。 Creative Cloud Libraries聯結器目前無法建立連線。 現有連線如預期般運作。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Limit]</td>
      <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td>
    </tr>
  </tbody>
</table>

### 其他

#### [!UICONTROL Make an API Call]

此模組會對[!DNL Adobe Creative Cloud Libraries] API發出自訂API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td> <p>如需有關將Adobe Creative Cloud帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明。</a></p>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]</td>
      <td>
        <p>輸入相對於<code>https://cc-libraries.adobe.io/api</code>的路徑。</p>
    <p>例如<code>/v1/libraries</code>。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL API version]</td>
      <td>
        <p>選取您要連線的[!DNL Adobe Analytics] API版本。</p>
      </td>
    </tr>    <tr>
      <td role="rowheader">[!UICONTROL Method]</td>
      <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱[!DNL Adobe Workfront Fusion]</a>中的<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法。</p> </td> 
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
      <td role="rowheader">[!UICONTROL Query String]</td>
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
       <tr>
      <td role="rowheader">[!UICONTROL Upload a transient document]</td>
      <td>
      <p>如果要上傳暫時性檔案，請輸入要上傳檔案的來源檔案。</p>
      <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p>
    </td>
    </tr>

</tbody>
</table>

---
title: Adobe Workfront規劃模組
description: 透過 [!DNL Adobe Workfront Planning] 模組，您可以根據您 [!DNL Adobe] Workfront Planning帳戶中的事件來啟動 [!DNL Adobe Workfront Fusion] 案例、建立、讀取或更新協定及其他記錄、使用您設定的條件搜尋記錄以及上傳檔案。
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
source-git-commit: 51bb87572f16f6194f6c37bbe52ea7f27050c303
workflow-type: tm+mt
source-wordcount: '1591'
ht-degree: 0%

---

# [!DNL Adobe Workfront Planning]模組

透過[!DNL Adobe Workfront Planning]模組，您可以在Workfront Planning中發生事件時觸發案例。 您也可以建立、讀取、更新及刪除記錄，或執行自訂API呼叫至您的[!DNL Adobe Workfront Planning]帳戶。

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

您必須具備下列專案才能存取Workfront Planning：

* 新的Workfront套件和授權。 Workfront計畫不適用於舊版Workfront套件或授權。
* Workfront計畫套件。
* 貴組織的Workfront執行個體必須上線至Adobe統一體驗。

## Adobe Workfront規劃API資訊

Adobe Workfront Planning聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td>https://{{connection.host}}/maestro/api/{{common.maestroApiVersion}}/</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## 建立與[!DNL Adobe Workfront Planning]的連線 {#create-a-connection-to-adobe-workfront-planning}

您可以直接從[!DNL Workfront Fusion]模組內建立與您的[!DNL Workfront Planning]帳戶的連線。

1. 在任何[!DNL Adobe Workfront Planning]模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

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
          <td>選取您是要連線到服務帳戶還是個人帳戶。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 使用者端ID]<p>（可選）</p></td>
          <td>輸入您的[!DNL Adobe] [!UICONTROL 使用者端識別碼]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 使用者端密碼]<p>（可選）</p></td>
          <td>輸入您的[!DNL Adobe] [!UICONTROL 使用者端密碼]。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 驗證URL]</td>
          <td>輸入您的Workfront執行個體將用來驗證此連線的URL。 <p>預設值為<code>https://oauth.my.workfront.com/integrations/oauth2</code>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 主機前置詞]</td>
          <td>輸入您的主機前置詞。<p>預設值為<code>origin-</code>。</p>
        </tr>
      </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

## [!DNL Adobe Workfront Planning]模組及其欄位

設定Workfront模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Workfront欄位，視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。


![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)
* [未分類](#uncategorized)

### 觸發程序

#### 觀看活動

在Workfront Planning中建立、更新或刪除記錄、記錄型別或工作區時，此觸發模組會啟動案例。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>選取您要使用的webhook，或按一下「新增」以建立新的webhook。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 物件型別]</td>
      <td>選取您要監視記錄、記錄型別或工作區。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 狀態]</td>
      <td>選取您要觀看舊狀態還是新狀態。<ul><li><p><b>[!UICONTROL 新狀態]</b></p><p>當記錄將指定值<b>變更為</b>時觸發案例。</p></li><li><p><b>[!UICONTROL 舊狀態]</b></p><p>當記錄從</b>變更指定值時，觸發案例<b>。</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>如果觀看記錄，請選取您要觀看記錄的Workspace 。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄型別]</td>
      <td>如果觀看記錄，請選取您要觀看的記錄型別。</td>
    </tr>
    </tr>
     <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL 事件篩選器]</p> </td> 
      <td> <p>您可以設定篩選器，只監視符合您選取條件的記錄。</p> <p>針對每個篩選器，輸入您希望篩選器評估的欄位、運運算元，以及您希望篩選器允許的值。 您可以新增AND規則來使用一個以上的篩選器。</p> <p>注意：您無法編輯現有[!DNL Workfront] Webhook中的篩選器。 若要為[!DNL Workfront]個事件訂閱設定不同的篩選器，請移除目前的webhook並建立新的篩選器。</p> <p>如需事件篩選的詳細資訊，請參閱Workfront模組文章中的[!DNL Workfront] &gt; [!UICONTROL 觀看事件]模組</a>中的<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">事件訂閱篩選。</p> </td> 
     </tr> 
    <tr>
      <td role="rowheader">要觀看的[!UICONTROL 物件]</td>
      <td>選取是否要監視新專案。 更新、新增和更新或刪除的記錄。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 排除此連線所做的更新]</p>
      </td>
      <td>啟用此選項可防止此模組使用的連線進行變更時觸發此案例。 如此可防止在此案例執行觸發動作時觸發另一個案例例項。</td> 
      </tr>
  </tbody>
</table>

### 動作

* [刪除記錄型別](#delete-a-record-type)
* [進行自訂AI呼叫](#make-a-custom-api-call)

#### 刪除記錄型別

此動作模組會依據其ID刪除Workfront Planning中的單一記錄型別。

>[!WARNING]
>
>刪除Workfront Planning中的記錄型別也會刪除記錄型別表格中的所有記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄型別的ID。</td> 
      </tr>
  </tbody>
</table>

#### 進行自訂API呼叫

此模組會對[!DNL Adobe Workfront Planning] API發出自訂API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
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
      <td role="rowheader">[!UICONTROL 查詢字串]  </td>
      <td>
        <p>針對您想要新增至查詢字串的每個索引鍵/值組，按一下<b>新增專案</b>並輸入索引鍵和值。</p>
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


### 搜尋

#### 搜尋記錄

此動作模組會根據您指定的條件擷取記錄清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>輸入或對應包含您要搜尋之記錄的Workspace。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別]</p>
      </td>
      <td>選取您要搜尋的記錄型別。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄欄位]</p>
      </td>
      <td>針對搜尋中要使用的每個欄位，找到該欄位，選取運運算元，然後輸入或對應您要搜尋的值。 根據所選的記錄型別，可使用欄位。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 篩選條件]</p>
      </td>
      <td>選取篩選條件：<ul><li><b>且</b><p>模組傳回符合您選取之欄位值的<b>所有</b>的記錄。</p></li><li><b>或</b><p>模組傳回符合您選取之欄位值的<b>任一</b>的記錄。</p></li></ul></td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 限制]</p>
      </td>
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
      </tr>
  </tbody>
</table>


### 未分類


#### 建立記錄

這個動作會在Workfront Planning中建立單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要建立的記錄型別。 可用的記錄型別取決於您的Workfront Planning帳戶。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>輸入您希望新記錄具有的值。 這些欄位是根據您選取的記錄型別。</td> 
      </tr>
     <tr>
  </tbody>
</table>

### 刪除記錄

此動作模組會刪除Workfront Planning中的指定記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄的ID。</td> 
      </tr>
  </tbody>
</table>

### 取得記錄

此動作模組會從其ID所指定的[!DNL Adobe Workfront Planning]擷取單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄ID]</td>
      <td>輸入或對應您要擷取之記錄的ID。</td>
    </tr>
  </tbody>
</table>

### 依記錄型別取得記錄

此動作模組會擷取指定型別的所有記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>選取或對映包含您要擷取之記錄的工作區。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄型別]</td>
      <td>選取您要擷取的記錄型別。</td>
    </tr>
     <!--<tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td> -->
  </tbody>
</table>

### 取得記錄型別

此動作模組會擷取[!DNL Adobe Workfront Planning]帳戶中的記錄型別清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>選取或對應包含您要擷取之記錄型別的工作區。</td>
    </tr>
  </tbody>
</table>

### 更新記錄

此動作會更新Workfront Planning中的單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Workfront Planning]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與[!DNL Adobe Workfront Planning]</a>的連線。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要更新的記錄型別。 可用的記錄型別取決於您的Workfront Planning帳戶。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>輸入您要記錄的新值。 這些欄位是根據您選取的記錄型別。</td> 
      </tr>
     <tr>
  </tbody>
</table>


## 使用JSONata進行可讀取的`record-types`劃分

下列JSONata運算式會建立可讀取的Planning查詢輸出，提供您記錄型別劃分。 這使記錄型別名稱、欄位名稱和欄位選項名稱（如果適用）可由名稱讀取，並保持結構的其餘部分不變。

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

如需有關使用JSONata模組的資訊，請參閱[JSONata模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md)。


---
filename: workday-modules
title: Workday模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用 [!DNL Workday]的工作流程，並將其連線至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 77237a1b-2acd-4350-9cc0-ec43b8b08137
source-git-commit: 40470e5d2183f690ad65f5e1170f78c37dee8603
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 1%

---

# [!DNL Workday]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Workday]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

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

若要使用[!DNL Workday]模組，您必須：

* 擁有[!DNL Workday]帳戶。

* 在[!DNL Workday]中建立OAuth應用程式。 如需指示，請參閱[!DNL Workday]檔案。

## Workday API資訊

Workday聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td>https://{{connection.servicesUrl}}/api</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.6.4</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Workday]連線至[!DNL Workfront Fusion]

1. 在任何[!DNL Workfront Fusion]模組中，按一下[!UICONTROL 連線]欄位旁的[!UICONTROL 新增]

2. 填寫下列欄位：

   <table style="table-layout:auto"> 
        <col/>
        <col/>
        <tbody>
            <tr>
                <td role="rowheader">
                    <p role="rowheader">[!UICONTROL 連線名稱]</p>
                </td>
                <td>輸入連線的名稱。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL Workday主機]</td>
                <td>輸入不含<code>https://</code>的[!DNL Workday]主機位址。 例如： <code>mycompany.workday.com</code>。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 服務URL]</td>
                <td>輸入您的[!DNL Workday]網路服務位址（不含<code>https://</code>）。 例如： <code>mycompany-services.workday.com</code>。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL 租使用者名稱稱]</td>
                <td>輸入此[!DNL Workday]帳戶的租使用者。 您的租使用者是您組織的識別碼，可在您用來登入Workday的URL中看見。 範例：在地址<code>https://www.myworkday.com/mycompany</code>中，租使用者是<code>mycompany</code>。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 使用者端ID]</td>
                <td>輸入此連線使用的[!DNL Workday]應用程式的使用者端識別碼。 當您在[!DNL Workday]中建立應用程式時，就會取得此資訊。</td>
            </tr>
            <tr>
                <td  role="rowheader">[!UICONTROL 使用者端密碼]</td>
                <td>輸入此連線使用的[!DNL Workday]應用程式的使用者端密碼。 當您在[!DNL Workday]中建立應用程式時，就會取得此資訊。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 工作階段逾時（分鐘）]</td>
                <td >輸入您的授權Token過期的分鐘數。</td>
            </tr>
        </tbody>
    </table>


3. 按一下[!UICONTROL 繼續]以儲存連線並返回模組

## [!DNL Workday]模組及其欄位

當您設定[!DNL Workday]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Workday]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#action)

* [搜尋](#search)


### 動作

* [[!UICONTROL 建立記錄]](#create-a-record)

* [[!UICONTROL 刪除記錄]](#delete-a-record)

* [[!UICONTROL 進行自訂API呼叫]](#make-a-custom-api-call)

* [[!UICONTROL 更新記錄]](#update-a-record)


#### [!UICONTROL 建立記錄]

此動作模組會在[!DNL Workday]中建立單一記錄。

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到[!DNL Workfront Fusion]</a>。</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄型別]</td>
            <td>選取您要建立的記錄型別。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>輸入或對應您要建立的記錄ID。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 子資源ID]</td>
            <td >輸入或對應您要建立之子資源的ID。</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除[!DNL Workday]中的單一記錄。

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到[!DNL Workfront Fusion]</a>。</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄型別]</td>
            <td>選取您要刪除的記錄型別。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 特定記錄型別]</td>
            <td>選取您要刪除的特定記錄型別。 這些是以您選擇的記錄型別為基礎。</td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 子資源ID]</td>
            <td>輸入或對應您要刪除之子資源的ID。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >輸入或對應您要刪除之記錄的ID。</td>
        </tr>
    </tbody>
</table>


### [!UICONTROL 進行自訂API呼叫]

此動作模組可讓您對[!DNL Workday] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Workday]模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

模組會傳回a狀態代碼，以及API呼叫的標題和正文。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Connection]</p> </td> 
            <td>如需有關將您的[!DNL Workday]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到[!DNL Workfront Fusion]</a>。</td>
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code style="color: #ff1493;">https://&lt;tenantHostname>/api/&lt;serviceName>/&lt;version>/&lt;tenant></code>的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion]會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組更新[!DNL Workday]中的單一記錄。

<table style="table-layout:auto"> 
    <col/>
    <col/>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >[!UICONTROL 連線[!DNL Workday]到Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄型別]</td>
            <td>選取您要更新的記錄型別。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td>輸入或對應您要更新的記錄ID。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 子資源ID]</td>
            <td >輸入或對應您要更新的子資源ID。</td>
        </tr>
    </tbody>
</table>

### 搜尋

* [[!UICONTROL 讀取記錄]](#read-a-record)

* [[!UICONTROL 清單記錄]](#list-records)


#### [!UICONTROL 讀取記錄]

此動作模組會讀取單一記錄。

<table style="table-layout:auto"> 
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
        <tr>
            <td role="rowheader">[!UICONTROL Connection]</td>
            <td>如需有關將您的[!DNL Workday]帳戶連線到Workfront Fusion的說明，請參閱<a href="#Connect" class="MCXref xref" >[!UICONTROL 連線[!DNL Workday]到Workfront Fusion]</a></td>
        </tr>
        <tr>
            <td  role="rowheader">[!UICONTROL 記錄型別]</td>
            <td>選取您要刪除的記錄型別。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL 特定記錄型別]</td>
            <td>選取您要讀取的特定記錄型別。 這些是以您選擇的記錄型別為基礎。</td>
        </tr>
        <tr>
            <td role="rowheader">[!UICONTROL ID] </td>
            <td >輸入或對應您要刪除之記錄的ID。</td>
        </tr>
    </tbody>
</table>

#### [!UICONTROL 清單記錄]

此搜尋模組會擷取指定型別的記錄清單。

<table style="table-layout:auto"> 
      <col/>
      <col/>
      <tbody>
          <tr>
              <td role="rowheader">[!UICONTROL Connection]</td>
              <td>如需有關將您的[!DNL Workday]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱<a href="#Connect" class="MCXref xref" >將[!DNL Workday]連線到[!DNL Workfront Fusion]</a></td>
          </tr>
          <tr>
              <td  role="rowheader">[!UICONTROL 記錄型別]</td>
              <td>選取您要擷取的記錄型別。</td>
          </tr>
          <tr>
              <td role="rowheader">[!UICONTROL 限制]</td>
              <td >
                  <p>輸入或對應您希望模組在每個案例執行週期中擷取的記錄數上限。</p>
              </td>
          </tr>
      </tbody>
  </table>

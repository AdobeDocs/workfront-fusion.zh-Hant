---
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Anaplan的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 81c9b141-4e40-430f-99f1-c44b7a833bcd
source-git-commit: 99f2e558db3d2b126adf748d7e013a4a39735bcd
workflow-type: tm+mt
source-wordcount: '1617'
ht-degree: 0%

---

# [!DNL Anaplan]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Anaplan]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
  <td> <p>[!UICONTROL Pro] 或更高</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
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

使用[!DNL Anaplan]聯結器之前，您必須確定符合下列先決條件：

* 您必須擁有使用中的[!UICONTROL Anaplan]帳戶。
* 您必須先在[!UICONTROL Anaplan]帳戶中設定工作區、模型和其他[!DNL Anaplan]物件，然後[!DNL Workfront Fusion]才能與它們互動。

## Anaplan API資訊

Anaplan聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td>https://api.anaplan.com/2/0/
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.11.5/td&gt; 
 </tbody> 
</table>

## 將[!DNL Anaplan]連線至[!DNL Workfront Fusion] {#connect-anaplan-to-workfront-fusion}

若要為您的[!DNL Anaplan]模組建立連線：

1. 按一下[!UICONTROL Connection]方塊旁的&#x200B;**[!UICONTROL Add]**。
1. 選取連線型別。

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL Basic]</td> 
      <td> <p>[!DNL Anaplan] [!UICONTROL Basic]連線只需要電子郵件地址和密碼即可建立連線。 </p> <p>輸入連線的名稱，然後輸入您的電子郵件地址和[!DNL Anaplan]帳戶的密碼。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL CA Certificate]</td> 
      <td> <p>[!DNL Anaplan] [!UICONTROL CA Certificate]連線需要[!UICONTROL Certificate Key]、[!UICONTROL Encoded Data]和[!UICONTROL Encoded Signed Data]。 您可以在您的[!DNL Anaplan]帳戶中產生這些專案。 如需指示，請參閱[!DNL Anaplan]檔案。</p> <p>輸入連線的名稱，然後輸入您在[!DNL Anaplan]帳戶中產生的[!UICONTROL Certificate Key]、[!UICONTROL Encoded Data]和[!UICONTROL Encoded Signed Data]。</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以儲存連線並返回模組。

## [!DNL Anaplan]模組及其欄位

當您設定[!DNL Anaplan]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Anaplan]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發器](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發器

#### [!DNL Watch records]

建立或更新所選型別的記錄時，此觸發模組就會啟動案例。

>[!NOTE]
>
>此模組會傳回新記錄的資料。 它不會傳回已修改現有記錄的資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">要觀看的物件型別</td> 
   <td>選取您要觀看的專案型別。 建立或更新此型別的記錄時，此案例即會開始。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">&lt;Object&gt; ID</td> 
   <td>在Anaplan中輸入與您要觀看之物件關聯的物件ID，例如「模型」或「模組」</td> 
  </tr> 
  <tr> 
   <td role="rowheader">限制</td> 
   <td> <p>在每個案例執行週期中，輸入或對應您要模組至[action]的最大記錄數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL Create a list item]](#create-a-list-item)
* [[!UICONTROL Make a custom API Call]](#make-a-custom-api-call)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Run an action]](#run-an-action)
* [[!UICONTROL Update a record]](#update-a-record)
* [[!UICONTROL Upload a file]](#upload-a-file)

#### [!UICONTROL Create a list item]

此動作模組會將新專案新增至Anaplan中的清單。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Connection]</td>
        <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Workspace ID]</td>
        <td>選取或對應Anaplan Workspace的ID，此ID包含您要新增專案的清單。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Model ID]</td>
        <td>選取或對應包含您要新增專案之清單的模型ID。</td>
    </tr>
    <tr>
        <td>[!UICONTROL List ID]</td>
        <td>選取或對應您要建立專案之清單的ID。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Name]</td>
        <td>輸入新專案的名稱。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Code]</td>
        <td>輸入新料號的代碼。 代碼是使用者產生的代碼，可讓您區分具有相同名稱的條列專案。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Parent]</td>
        <td>輸入要在其下建立新專案的父專案名稱。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Properties]</td>
        <td>如果要新增專案的清單具有自訂屬性，請選取要為其新增值的屬性，然後新增值。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Subsets]</td>
        <td>如果要新增專案的清單具有自訂子集，請選取要新增專案的子集，然後選取「<b>[!UICONTROL Yes]</b>」以將新專案新增到該子集。</td>
    </tr>
</table>

#### [!UICONTROL Make a custom API Call]

此模組可讓您對[!DNL Anaplan] API執行自訂API呼叫。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於 <code>https://api.anaplan.com/2/0/</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱[!DNL Adobe Workfront Fusion]</a>中的<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>輸入請求查詢字串。</p> </td> 
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

#### [!UICONTROL Delete a record]

此動作模組會刪除現有記錄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要刪除之物件的Anaplan Workspace的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Model ID]</td> 
   <td>輸入或對應包含要刪除物件的模型ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">刪除</td> 
   <td> <p>選取要刪除的物件型別。</p> 
    <ul> 
     <li> <p><b>動作</b> </p> <p>選取或對應要刪除的動作。</p> </li> 
     <li> <p><b>清單專案</b> </p> <p>選取您要刪除專案的清單，然後輸入或對應您要刪除的專案識別碼或代碼</p>  </li> 
     <li> <p><b>[!UICONTROL File]</b> </p> <p>選取或對應要刪除的檔案。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

此動作模組會讀取單一記錄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>選取要讀取的記錄型別。</p> 
    <ul> 
     <li> <p><b>模型</b> </p> <p>選取或對應您要讀取的模型ID</p> </li> 
     <li> <p><b>模型清單</b> </p> <p>選取或對應包含您要讀取之清單的Workspace和模型的ID，然後選取「清單」。 在[!UICONTROL Data type]欄位中，選取您要讀取資料或中繼資料。</p> </li> 
     <li> <p><b>模型版本</b> </p> <p>選取或對應您要讀取的模型ID。</p> </li> 
     <li> <p><b>使用者</b> </p> <p>選取您是否要傳回正在使用的帳戶擁有者或其他使用者的相關資料。 如果您選取其他使用者，請選取該使用者的名稱。</p> </li> 
     <li> <p><b>Workspace</b> </p> <p>選取或對應您要讀取之Workspace的ID。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Run an action]

此動作模組會匯入、匯出、刪除或處理動作。

<table style="table-layout:auto"> 
     <col/>
     <col/>
     <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection]</td>
        <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#Connect" class="MCXref xref" >[!UICONTROL Connect Anaplan to Workfront Fusion]</a>。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Workspace ID]</td>
        <td>選取或對應您要執行動作之[!DNL Anaplan] Workspace的ID</td>
      </tr>
      <tr >
        <td role="rowheader">[!UICONTROL Model ID]</td>
        <td>選取或對應您要執行動作之模型的ID。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Action type]</td>
        <td>
          <p>選取您要執行的動作</p>
            <ul>
              <li>
                <p><b>[!UICONTROL Delete]</b>
                </p>
                <p>輸入或對應您要刪除之動作的ID。</p>
              </li>
              <li>
                <p><b>[!UICONTROL Export]</b>
                </p>
                <p>輸入或對應您要使用之匯出定義的ID。 您可以匯出為下列檔案格式：</p>
                  <ul>
                    <li>
                      <p>XLS</p>
                    </li>
                    <li>
                      <p>XLSX</p>
                    </li>
                    <li>
                      <p>CSV</p>
                    </li>
                  </ul>
                </li>
                <li>
                  <p><b>[!UICONTROL Import] </b>
                  </p>
                  <p style="font-weight: normal;">輸入或對應您要使用之匯入定義的ID。</p>
                </li>
                <li>
                 <p><b>[!UICONTROL Process]</b>
                 </p>
                  <p>輸入或對應您要使用的程式ID。 </p>
                </li>
              </ul>
            </td>
          </tr>
        </tbody>
      </table>


#### [!UICONTROL Update a record]

此動作模組更新[!UICONTROL Anaplan]中的單一記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record type]</td> 
   <td> <p>選取您要更新的記錄型別。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL List item]</b> </p> <p>如需欄位，請參閱本文中的<a href="#create-a-list-item" class="MCXref xref">建立清單專案</a>。</p> </li> 
     <li> <p><b>[!UICONTROL Module cell data]</b> </p> <p>當您更新儲存格資料時，也會更新使用該資料的所有下游計算。</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Model ID]</b> </p> <p>選取或對應包含要更新之儲存格的模型。</p> </li> 
       <li> <p><b>[!UICONTROL Module ID]</b> </p> <p>選取或對應包含要更新之儲存格的模組</p> </li> 
       <li> <p><b>[!UICONTROL Line item name]</b> </p> <p>選取或對應您要更新之儲存格的行專案</p> </li> 
       <li> <p style="font-weight: bold;">[!UICONTROL Dimension ID]</p> <p>選取或對應行專案上的維度。</p> 
       <p><b>附註： </b> 
       <ul>
       <li> Dimension金鑰（值）必須是<code>dimensionName</code> （下一個）或<code>dimensionId</code> （識別碼）。</li>
       <li>專案索引鍵（值）必須是<code>itemName</code> （文字）、<code>itemCode</code> （文字）或<code>itemId</code> （識別碼）。</li>
       <li>Dimension和專案索引鍵必須是相同的型別（文字或ID）。
       </ul>
        </p> 
        <p>如需維度的相關資訊，請在[!DNL Anaplan Anapedia]中搜尋Dimension。</p> </li> 
       <li> <p><b>[!UICONTROL Value]</b> </p> <p>輸入或對應儲存格的新值。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL Model current fiscal year]</b> </p> <p>輸入您要更新其會計年度之模型的Workspace ID與模型ID，然後輸入或對映模型的新年度。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a file]

此動作模組會將檔案上傳至Anaplan。 檔案必須已上傳至Anaplan。 您可以使用此模組將其上傳至Anaplan中的其他位置。
<table style="table-layout:auto">
<col>
<col>
<tbody>
<tr>
<td role="rowheader">[!UICONTROL Connection]</td>
<td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Workspace ID]</td>
<td>選取或對應您要上傳檔案的[!DNL Anaplan] Workspace識別碼。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Model ID]</td>
<td>選取或對應您要上傳檔案之模型的ID。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL File ID]</td>
<td>選取或對應您要上傳之檔案的ID。</td>
</tr>
</tbody>
</table>
</div>

### 搜尋

#### [!UICONTROL Get record]

此搜尋模組會傳回所選型別的所有可存取記錄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的說明，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至[!DNL Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Record types]</td> 
   <td> <p>選取您要擷取的記錄型別。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Workspaces]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Models]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Line items]</b> </p> <p>選取或對應包含您要擷取[!DNL line]個專案的模型識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL Model lists]</b> </p> <p>選取或對應包含您要擷取之模型清單的Workspace ID和模型ID。</p> </li> 
       <li> <p><b>[!UICONTROL Model calendar]</b> </p> <p>選取或對應包含您要擷取之模型行事曆的Workspace ID。</p> </li> 
       <li> <p><b>[!UICONTROL Model versions]</b> </p> </li> 
       <li> <p>選取或對應包含要擷取之模型版本的模型ID。</p> </li> 
       <li> <p><b>[!UICONTROL Users]</b> </p> </li> 
       <li> <p><b>[!UICONTROL Views]</b> </p> <p>選取您要選擇「依模組」或「依模型」檢視，然後選取或對應包含您要擷取之檢視的「模組」或「模型」的ID。</p> </li> 
      </ul> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Return workspace size]</td> 
   <td>啟用此選項可傳回工作區目前大小的預估值。 此估計是根據工作區中包含的所有模組大小而定。</td> 
  </tr> 
 </tbody> 
</table>

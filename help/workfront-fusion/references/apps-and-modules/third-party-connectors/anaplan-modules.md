---
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Anaplan的工作流程，並將其連線到多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: 81c9b141-4e40-430f-99f1-c44b7a833bcd
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '2023'
ht-degree: 1%

---

# [!DNL Anaplan]模組

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Anaplan]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

使用[!DNL Anaplan]聯結器之前，您必須確定符合下列先決條件：

* 您必須擁有使用中的[!UICONTROL Anaplan]帳戶。
* 您必須先在[!DNL Anaplan]Anaplan[!UICONTROL 帳戶中設定工作區、模型和其他]物件，Workfront Fusion才能與這些物件互動。

## Anaplan API資訊

Anaplan聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>https://api.anaplan.com/2/0/
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.11.5</td> 
 </tbody> 
</table>

## 將[!DNL Anaplan]連線至Workfront Fusion {#connect-anaplan-to-workfront-fusion}

若要為您的[!DNL Anaplan]模組建立連線：

1. 按一下&#x200B;**[!UICONTROL 連線]**&#x200B;方塊旁的[!UICONTROL 新增]。
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
          <p>輸入新連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>
          <p>選取要連線到生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 型別]</td>
        <td>
          <p>選取您要連線到服務帳戶還是個人帳戶。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 電子郵件]</td>
        <td>
          <p>輸入此Anaplan帳戶的電子郵件地址</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 密碼]</td>
        <td>輸入此Anaplan帳戶的密碼。</td>
      </tr>
     </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

<!--1. Click **[!UICONTROL Add]** next to the [!UICONTROL Connection] box.
1. Select the connection type.

   <table style="table-layout:auto">
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL Basic]</td> 
      <td> <p>An [!DNL Anaplan] [!UICONTROL Basic] connection requires only an email address and password to create the connection. </p> <p>Enter a name for the connection, then enter your email address and the password of your [!DNL Anaplan] account.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Anaplan] [!UICONTROL CA Certificate]</td> 
      <td> <p>An [!DNL Anaplan] [!UICONTROL CA Certificate] connection requires a [!UICONTROL Certificate Key], [!UICONTROL Encoded Data], and [!UICONTROL Encoded Signed Data]. You can generate these in your [!DNL Anaplan] account. For instructions, see the [!DNL Anaplan] documentation.</p> <p>Enter a name for the connection, then enter the [!UICONTROL Certificate Key], [!UICONTROL Encoded Data], and [!UICONTROL Encoded Signed Data] that you generated in your [!DNL Anaplan] account.</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. Click **[!UICONTROL Continue]** to save the connection and return to the module.-->

## [!DNL Anaplan]模組及其欄位

當您設定[!DNL Anaplan]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Anaplan]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

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
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
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
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 建立清單專案]](#create-a-list-item)
* [刪除記錄](#delete-a-record)
* [匯出資料](#export-data)
* [匯入資料](#import-data)
* [[!UICONTROL 進行自訂API呼叫]](#make-a-custom-api-call)
* [[!UICONTROL 讀取記錄]](#read-a-record)
* [[!UICONTROL 執行動作]](#run-an-action)
* [[!UICONTROL 更新記錄]](#update-a-record)
* [[!UICONTROL 上傳檔案]](#upload-a-file)

#### [!UICONTROL 建立清單專案]

此動作模組會將新專案新增至Anaplan中的清單。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Connection]</td>
        <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Workspace ID]</td>
        <td>選取或對應Anaplan Workspace的ID，此ID包含您要新增專案的清單。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 模型ID]</td>
        <td>選取或對應包含您要新增專案之清單的模型ID。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 清單ID]</td>
        <td>選取或對應您要建立專案之清單的ID。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 名稱]</td>
        <td>輸入新專案的名稱。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 程式碼]</td>
        <td>輸入新料號的代碼。 代碼是使用者產生的代碼，可讓您區分具有相同名稱的條列專案。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Parent]</td>
        <td>輸入要在其下建立新專案的父專案名稱。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 屬性]</td>
        <td>如果要新增專案的清單具有自訂屬性，請選取要為其新增值的屬性，然後新增值。</td>
    </tr>
    <tr>
        <td>[!UICONTROL 子集]</td>
        <td>如果要新增專案的清單具有自訂子集，請選取要新增專案的子集。</td>
    </tr>
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除現有記錄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要刪除之物件的Anaplan Workspace的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 模型ID]</td> 
   <td>輸入或對應包含要刪除物件的模型ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取要刪除的物件型別。</p> 
    <ul> 
     <li> <p><b>動作</b> </p> <p>選取或對應要刪除的動作。</p> </li> 
     <li> <p><b>清單專案</b> </p> <p>選取您要刪除專案的清單，然後輸入或對應您要刪除的專案識別碼或代碼</p>  </li> 
     <li> <p><b>[!UICONTROL 檔案]</b> </p> <p>選取或對應要刪除的檔案。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>



#### [!UICONTROL 匯出資料]

此動作模組使用匯出定義從Anaplan擷取資料。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應包含您要匯出之資料的Anaplan Workspace的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 模型ID]</td> 
   <td>輸入或對應包含您要匯出之資料的模型ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">匯出定義ID</td> 
   <td> <p>輸入或對應您要使用的「Anaplan匯出」定義的ID。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

#### 匯入資料

此動作模組會將資料匯入Anaplan。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID]</td> 
   <td>選取或對應您要匯入資料之Anaplan Workspace的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 模型ID]</td> 
   <td>輸入或對應您要匯入資料之模型的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">匯出定義ID</td> 
   <td> <p>輸入或對應您要使用的「Anaplan匯入」定義的ID。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行自訂API呼叫]

此模組可讓您對[!DNL Anaplan] API執行自訂API呼叫。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於 <code>https://api.anaplan.com/2/0/</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串] </td> 
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

#### [!UICONTROL 讀取記錄]

此動作模組會讀取單一記錄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取要讀取的記錄型別。</p> 
    <ul> 
     <li> <p><b>模型</b> </p> <p>選取或對應您要讀取的模型ID</p> </li> 
     <li> <p><b>模型清單</b> </p> <p>選取或對應包含您要讀取之清單的Workspace和模型的ID，然後選取「清單」。 在[!UICONTROL 資料型別]欄位中，選取您要讀取資料還是中繼資料。</p> </li> 
     <li> <p><b>模型版本</b> </p> <p>選取或對應您要讀取的模型ID。</p> </li> 
     <li> <p><b>使用者</b> </p> <p>選取您是否要傳回正在使用的帳戶擁有者或其他使用者的相關資料。 如果您選取其他使用者，請選取該使用者的名稱。</p> </li> 
     <li> <p><b>Workspace</b> </p> <p>選取或對應您要讀取之Workspace的ID。</p> </li> 
     <li> <p><b>檢視</b> </p> <p>選取或對應包含您要讀取之檢視的模型ID。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 執行動作]

此動作模組會匯入、匯出、刪除或處理動作。

<table style="table-layout:auto"> 
     <col/>
     <col/>
     <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL Connection]</td>
        <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#Connect" class="MCXref xref" >[!UICONTROL Connect Anaplan to Workfront Fusion]</a>。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Workspace ID]</td>
        <td>選取或對應您要執行動作之[!DNL Anaplan] Workspace的ID</td>
      </tr>
      <tr >
        <td role="rowheader">[!UICONTROL 模型ID]</td>
        <td>選取或對應您要執行動作之模型的ID。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 動作型別]</td>
        <td>
          <p>選取您要執行的動作</p>
            <ul>
              <li>
                <p><b>[!UICONTROL 刪除]</b>
                </p>
                <p>輸入或對應您要刪除之動作的ID。</p>
              </li>
              <li>
                <p><b>[!UICONTROL 匯出]</b>
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
                  <p><b>[!UICONTROL 匯入] </b>
                  </p>
                  <p style="font-weight: normal;">輸入或對應您要使用之匯入定義的ID。</p>
                </li>
                <li>
                 <p><b>[!UICONTROL 處理序]</b>
                 </p>
                  <p>輸入或對應您要使用的程式ID。 </p>
                </li>
              </ul>
            </td>
          </tr>
        </tbody>
      </table>


#### [!UICONTROL 更新記錄]

此動作模組更新[!UICONTROL Anaplan]中的單一記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要更新的記錄型別。</p> 
    <ul> 
     <li> <p><b>[!UICONTROL 清單專案]</b> </p> <p>如需欄位，請參閱本文中的<a href="#create-a-list-item" class="MCXref xref">建立清單專案</a>。</p> </li> 
     <li> <p><b>[!UICONTROL 模組儲存格資料]</b> </p> <p>當您更新儲存格資料時，也會更新使用該資料的所有下游計算。</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p><b>[!UICONTROL 模型識別碼]</b> </p> <p>選取或對應包含要更新之儲存格的模型。</p> </li> 
       <li> <p><b>[!UICONTROL 模組識別碼]</b> </p> <p>選取或對應包含要更新之儲存格的模組</p> </li> 
       <li> <p><b>[!UICONTROL 行專案名稱]</b> </p> <p>選取或對應您要更新之儲存格的行專案</p> </li> 
       <li> <p style="font-weight: bold;">[!UICONTROL Dimension ID]</p> <p>選取或對應行專案上的維度。</p> 
       <p><b>附註： </b> 
       <ul>
       <li> Dimension金鑰（值）必須是<code>dimensionName</code> （下一個）或<code>dimensionId</code> （識別碼）。</li>
       <li>專案索引鍵（值）必須是<code>itemName</code> （文字）、<code>itemCode</code> （文字）或<code>itemId</code> （識別碼）。</li>
       <li>Dimension和專案索引鍵必須是相同的型別（文字或ID）。
       </ul>
        </p> 
        <p>如需維度的相關資訊，請在[!DNL Anaplan Anapedia]中搜尋維度。</p> </li> 
       <li> <p><b>[!UICONTROL 值]</b> </p> <p>輸入或對應儲存格的新值。</p> </li> 
      </ul> </li> 
     <li> <p><b>[!UICONTROL 模型目前會計年度]</b> </p> <p>輸入您要更新其會計年度之模型的Workspace ID與模型ID，然後輸入或對映模型的新年度。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳動作檔案]

此動作模組會將Anaplan中的現有檔案上傳到Anaplan內的其他位置。
<table style="table-layout:auto">
<col>
<col>
<tbody>
<tr>
<td role="rowheader">[!UICONTROL Connection]</td>
<td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL Workspace ID]</td>
<td>選取或對應您要上傳檔案的[!DNL Anaplan] Workspace識別碼。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL 模型ID]</td>
<td>選取或對應您要上傳檔案之模型的ID。</td>
</tr>
<tr>
<td role="rowheader">[!UICONTROL 檔案ID]</td>
<td>選取或對應您要上傳之檔案的ID。</td>
</tr>
</tbody>
</table>
</div>

### 搜尋

#### [!UICONTROL 取得記錄]

此搜尋模組會傳回所選型別的所有可存取記錄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需建立[!DNL Anaplan]連線的指示，請參閱本文中的<a href="#connect-anaplan-to-workfront-fusion" class="MCXref xref">連線[!DNL Anaplan]至Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要擷取的記錄型別。</p> 
      <ul> 
       <li> <p><b>[!UICONTROL Workspaces]</b> </p> </li> 
       <li> <p><b>[!UICONTROL 模型]</b> </p> </li> 
       <li> <p><b>[!UICONTROL 行專案]</b> </p> <p>選取或對應包含您要擷取[!DNL line]個專案的模型識別碼。</p> </li> 
       <li> <p><b>[!UICONTROL 模型清單]</b> </p> <p>選取或對應包含您要擷取之模型清單的Workspace ID和模型ID。</p> </li> 
       <li> <p><b>[!UICONTROL 模型行事曆]</b> </p> <p>選取或對應包含您要擷取之模型行事曆的Workspace ID。</p> </li> 
       <li> <p><b>[!UICONTROL 模型版本]</b> </p> </li> 
       <li> <p>選取或對應包含要擷取之模型版本的模型ID。</p> </li> 
       <li> <p><b>[!UICONTROL 使用者]</b> </p> </li> 
       <li> <p><b>[!UICONTROL 檢視]</b> </p> <p>選取您要選擇「依模組」或「依模型」檢視，然後選取或對應包含您要擷取之檢視的「模組」或「模型」的ID。</p> </li> 
      </ul> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回工作區大小]</td> 
   <td>啟用此選項可傳回工作區目前大小的預估值。 此估計是根據工作區中包含的所有模組大小而定。</td> 
  </tr> 
 </tbody> 
</table>

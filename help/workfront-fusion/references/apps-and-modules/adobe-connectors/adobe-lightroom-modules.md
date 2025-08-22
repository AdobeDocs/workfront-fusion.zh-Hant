---
title: Adobe Lightroom模組
description: 透過Adobe Lightroom模組，您可以根據Adobe Lightroom帳戶中的事件啟動Adobe Workfront Fusion案例。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '3200'
ht-degree: 0%

---

# [!DNL Adobe Lightroom]模組

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Adobe Lightroom]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

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

使用[!DNL Adobe Lightroom]聯結器之前，您必須確定符合下列先決條件：

* 您必須擁有使用中的[!DNL Adobe Lightroom]帳戶。
* 您必須在Adobe Admin Console中設定OAuth網頁應用程式。 如需詳細資訊，請參閱本文中的[在Adobe Admin Console中設定OAuth應用程式](#configure-an-oauth-application-in-the-adobe-admin-console)。

## Adobe Lightroom API資訊

Adobe Lightroom聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>https://lr.adobe.io</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.17.128</td> 
  </tr>
 </tbody> 
 </table>



## 建立與Adobe Lightroom的連線

若要連線至Adobe Lightroom，您必須先在Adobe Admin Console中設定OAuth應用程式。 設定此應用程式後，您可以從Workfront Fusion建立連線。

### 在Adobe Admin Console中設定Oauth應用程式

1. 開始在Adobe Admin Console中設定OAuth網頁應用程式。

   如需相關說明，請參閱Adobe開發人員檔案中的[使用者驗證實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/UserAuthentication/implementation)。
1. 設定OAuth網頁應用程式時，請輸入下列值：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL 範圍]</td>
        <td>
          <ul>
            <li>AdobeID</li>
            <li>lr_partner_rendition_api</li>
            <li>openid</li>
            <li>offline_access</li>
            <li>lr_partner_apis</li>
          </ul>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 重新導向URI]</td>
        <td><code>https://app.workfrontfusion.com/oauth/cb/adobe-lightroom5</code></td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 重新導向URI模式]</td>
        <td><code>https://app\.workfrontfusion\.com/oauth/cb/adobe-lightroom5</code></td>
        </tr>
      </tbody>
    </table>

### 從Workfront Fusion建立與Adobe Lightroom的連線

若要為您的[!DNL Adobe Lightroom]模組建立連線：

1. 在任何Adobe Lightroom模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

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
        <td>選取您要連線到服務帳戶還是個人帳戶。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的[!UICONTROL Adobe] [!UICONTROL 使用者端ID]。 您可在的[!UICONTROL Credentials]詳細資訊區段中找到 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的[!DNL Adobe] [!UICONTROL 使用者端密碼]。 您可在的[!UICONTROL Credentials]詳細資訊區段中找到 [!DNL Adobe Developer Console]</td>
        </tr>
      </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。


## Adobe Lightroom模組及其欄位

當您設定[!DNL Adobe Lightroom]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe Lightroom]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [其他](#other)
* [資產](#assets)
* [相簿](#albums)

### 其他

* [健康情況檢查](#health-check)
* [擷取使用者目錄中繼資料](#retrieve-user-catalog-metadata)

#### 健康情況檢查

此動作模組會擷取Lightroom伺服器版本ID，以證明Lightroom服務目前是否執行。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 認證]</td>
      <td>
        <p>如果您要提供特定認證，以確保特定伺服器正在執行，請按一下[新增專案] <b> </b>，然後輸入認證。</p><p>授權標頭會自動新增。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 擷取使用者目錄中繼資料

此動作模組會從Adobe Lightroom中的目錄擷取中繼資料。 目錄包含資產、專輯或其他資源。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 認證]</td>
      <td>
        <p>如果您想提供特定認證，以確保可以存取正確的使用者帳戶，請按一下[新增專案]並輸入認證。</p><p>授權標頭會自動新增。</p>
      </td>
    </tr>
  </tbody>
</table>

### 資產

* [建立資產原始檔案](#create-an-asset-original-file)
* [建立資產](#create-an-asset)
* [建立資產外部XMP開發設定檔案](#create-an-asset-external-xmp-develop-setting-file)
* [產生原始檔案的轉譯](#generate-renditions-for-an-original-file)
* [取得目錄資產](#get-a-catalog-asset)
* [取得最新的資產外部XMP開發設定](#get-the-latest-asset-external-xmp-develop-setting-file)
* [取得最新的資產轉譯](#get-the-latest-asset-rendition)
* [擷取資產](#retrieve-assets)

#### 建立資產原始檔案

此動作模組會為資產建立和上傳原始檔案。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含資產的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應您要建立及上傳檔案的資產ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 內容長度（位元組）]</td>
      <td>
        <p>輸入或對應內容的長度（位元組）。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 位元組範圍]</td>
      <td>
        <p>輸入或對應要求的位元組範圍，包括第一個和最後一個位元組，以及如RFC 2616所定義的實體長度。 只有在資料太大而無法透過單一呼叫上傳時，才應包含此資訊。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 內容型別]</td>
      <td>
        <p>選取新檔案的內容型別。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 建立資產

此動作模組會使用初始中繼資料和匯入資訊建立新資產。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對映將建立資產的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對映新資產的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產型別]</td>
      <td>
        <p>選取資產為影像或影片。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 日期時間使用者已建立]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00</code>的日期。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 日期時間使用者已更新]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00</code>的日期。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 擷取日期]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00</code>之資產的擷取日期。 如果擷取的日期設為<code>0000-00-00T00:00:00</code>，則伺服器會設定此專案。 </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 檔案名稱]</td>
      <td>
        <p>輸入或對應您要匯入Lightroom之資產的檔案名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 匯入的裝置名稱]</td>
      <td>
        <p>輸入或對映匯入資產的裝置名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 匯入使用者帳戶ID]</td>
      <td>
        <p>輸入或對應匯入資產的使用者ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 匯入時間戳記]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00</code>的日期。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 建立資產外部XMP開發設定檔案

此動作模組支援兩個工作流程：上傳資產的外部XMP開發設定檔案，或透過從其他資產的外部xmp開發設定檔案複製來建立外部XMP開發設定檔案。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 內容長度（位元組）]</td>
      <td>
        <p>輸入或對應內容的長度（位元組）。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 上傳新的或複製XMP/develop檔案]</td>
      <td>
        <p>選取您是上傳新檔案，還是從現有資產複製檔案。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應您要建立資產的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應您要上傳或複製檔案的資產ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL XMP/develop file]連結</td>
      <td>
        <p>輸入或對應連結至您要上傳或複製的檔案。</p><p>如果複製檔案，則此檔案必須為JSON；如果上傳檔案，則必須為XML。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 產生原始檔案的轉譯

此動作模組會非同步產生原始檔案的轉譯。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 轉譯型別（以分號分隔）]</td>
      <td>
        <p>輸入您要建立之轉譯的轉譯型別。 如果輸入多個型別，請以分號(；)分隔。 <p>可能的型別：</p><ul><li><code>fullsize</code></li><li><code>2560</code></li></ul></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 內容長度（位元組）]</td>
      <td>
        <p>輸入或對應內容的長度（位元組）。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應您要產生轉譯之目錄的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應您要為其建立檔案轉譯的資產ID。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 取得目錄資產

此動作模組會擷取目錄中單一資產的相關資訊。 目錄必須由使用者擁有，該使用者的認證會顯示在此模組所使用的連線中。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含資產的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應您要擷取資訊之資產的ID。</p>
      </td>
    </tr>
  </tbody>
</table>


#### 取得最新資產外部XMP開發設定檔案

此動作模組會擷取最新的資產外部XMP設定檔案。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對映目錄ID，該目錄包含與XMP開發設定檔案相關聯的資產。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應與XMP開發設定檔案相關聯的資產ID。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 取得最新的資產轉譯

此動作模組會擷取指定型別的最新資產轉譯。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對映目錄ID，該目錄包含您要擷取轉譯的資產。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應您要擷取轉譯之資產的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 轉譯型別]</td>
      <td>
        <p>選取您要擷取的轉譯型別。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 擷取資產

此動作模組會擷取此模組所用連線中，憑證由所代表之使用者所擁有的資產。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含資產的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 開始時間戳記]</td>
      <td>
        <p>輸入或對應時間戳記。 模組會傳回在此時間戳記之後更新的記錄。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 傳回指定時間前擷取的資產]</td>
      <td>
        <p>輸入格式為<code>YYYY-MM-DDT00:00:00</code>的日期。 模組會傳回在此日期之前擷取的結果。</p><p> 此欄位無法與欄位<code>Return assets captured after given time</code>搭配使用。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 傳回指定時間後擷取的資產]</td>
      <td>
        <p>輸入格式為<code>YYYY-MM-DDT00:00:00</code>的日期。 模組會傳回在此日期之前擷取的結果。</p><p> 此欄位無法與欄位<code>Return assets captured before given time</code>搭配使用。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 傳回資產的最大數量]</td>
      <td>
        <p>輸入您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL SHA256原始檔案的雜湊值]</td>
      <td>
        <p>輸入或對映原始檔案的雜湊值。 會傳回具有相符雜湊的Assets。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 隱藏棧疊內的資產？」]</td>
      <td>
        <p>選取「是」以隱藏棧疊內的資產（不會傳回棧疊內的資產）。 選取「否」可將資產包含在結果中的棧疊中。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Asset子型別值]</td>
      <td>
        <p>輸入要傳回的子型別值清單（以分號分隔），或對應。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應最多100個資產ID，以逗號分隔。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 要排除的資產型別]</td>
      <td>
        <p>選取是否要排除完整或不完整的資產。 若要包含所有資產，請將此欄位留空。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 群組值]</td>
      <td>
        <p>輸入或對應以分號分隔的群組值清單。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 名稱值]</td>
      <td>
        <p>輸入或對應以分號分隔的名稱值清單。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 我的最愛狀態]</td>
      <td>
        <p>輸入或對應您要傳回結果的我的最愛狀態。</p>
      </td>
    </tr>
    </tr>
  </tbody>
</table>

### 相簿

* [將資產新增至相簿](#add-assets-to-an-album)
* [建立相簿](#create-an-album)
* [刪除相簿](#delete-an-album)
* [取得相簿](#get-an-album)
* [列出相簿的資產](#list-assets-of-an-album)
* [擷取相簿](#retrieve-albums)
* [更新相簿](#update-album)

#### 將資產新增至相簿

此動作模組會將一或多個資產新增至指定的相簿。 在一個執行週期最多可新增50個資產。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應目錄ID，該目錄包含您要新增資產的相簿。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 相簿ID]</td>
      <td>
        <p>輸入或對應您要新增資產的相簿識別碼。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Assets]</td>
      <td>
        <p>針對您想要新增至相簿的每個資產，按一下<b>新增專案</b>並輸入下列欄位。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應您要新增至相簿的資產ID</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 此資產是否為專輯封面？]</td>
      <td>
        <p>選取是否要將此資產顯示為代表相簿的影像。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 順序]</td>
      <td>
        <p>指定資產的順序。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 服務裝載]</td>
      <td>
        <p>輸入或對應您要納入資產的任何中繼資料。 這必須是單一文字字串，最大長度為1-24個字元。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 遠端ID]</td>
      <td>
        <p>輸入資產的識別碼。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 建立相簿

此動作模組會在Lightroom中建立新相簿。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應您要建立相簿的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 相簿ID]</td>
      <td>
        <p>輸入或對應新相簿的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Subtype]</td>
      <td>
        <p>選取相簿的子型別。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 服務ID]</td>
      <td>
        <p>輸入建立相簿之服務的API金鑰。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 使用者建立日期]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00Z</code>的日期。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 使用者更新日期]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00Z</code>的日期。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 專輯名稱]</td>
      <td>
        <p>輸入或對應新相簿的名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 封面ID]</td>
      <td>
        <p>輸入或對應要當作此相簿封面的資產ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 父系ID]</td>
      <td>
        <p>輸入或對應此相簿的父系識別碼。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 服務裝載]</td>
      <td>
        <p>以字串形式輸入或對應相簿中繼資料。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 遠端ID]</td>
      <td>
        <p>輸入資產的識別碼。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 建立日期]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00Z</code>的日期。</p>
      </td>
    <tr>
      <td role="rowheader">[!UICONTROL 更新日期]</td>
      <td>
        <p>輸入或對應格式為<code>YYYY-MM-DDT00:00:00-00:00Z</code>的日期。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 專輯已刪除嗎？]</td>
      <td>
        <p>如果刪除了外部附屬內容，則啟用此選項。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL of location to edit ailiated content]</td>
      <td>
        <p>如果有使用者可以編輯此相簿內容的URL，請在此輸入URL。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL of location to view affiliated content]</td>
      <td>
        <p>如果有使用者可以檢視此相簿內容的URL，請在此輸入URL。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 刪除相簿

此動作模組會刪除相簿。

已刪除的相簿必須由目前要刪除該相簿的相同使用者端應用程式所建立，而且它必須是子型別`project`或`project_set`。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含要刪除之相簿的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 相簿ID]</td>
      <td>
        <p>輸入或對應您要刪除的相簿識別碼。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 刪除子專輯？]</td>
      <td>
        <p>選取是否要刪除已刪除相簿的子相簿。</p>
      </td>
    </tr>
  </tbody>
</table>

### 取得相簿

此動作模組會擷取指定的相簿。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含您要擷取之相簿的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 相簿ID]</td>
      <td>
        <p>輸入或對應您要擷取的相簿ID。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 列出相簿的資產

此動作模組會擷取指定相簿中的資產清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含相簿的目錄識別碼。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 相簿ID]</td>
      <td>
        <p>輸入或對應您要列出其資產的相簿ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 在時間前擷取Assets]</td>
      <td>
        <p>輸入格式為<code>YYYY-MM-DDT00:00:00</code>的日期。 模組會傳回在此日期之前擷取的結果。</p><p> 此欄位無法與欄位<code>Return assets captured after given time</code>搭配使用。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Capture Assets After Time]</td>
      <td>
        <p>輸入格式為<code>YYYY-MM-DDT00:00:00</code>的日期。 模組會傳回在此日期之前擷取的結果。</p><p> 此欄位無法與欄位<code>Return assets captured before given time</code>搭配使用。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 結束資產順序值]</td>
      <td>
        <p>輸入或對應結束資產的順序值。</p><p> 此欄位只能與欄位<code>Capture Assets After Time</code>搭配使用。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 起始資產順序值]</td>
      <td>
        <p>輸入或對映起始資產的順序值。</p><p> 此欄位只能與欄位<code>Capture Assets BEfore Time</code>搭配使用。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">要傳回的Assets號碼[!UICONTROL (1-500)]</td>
      <td>
        <p>輸入您希望模組在每個案例執行週期中傳回的最大記錄數。 此數字必須介於1到500之間。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 隱藏棧疊內的資產？」]</td>
      <td>
        <p>選取「是」以隱藏棧疊內的資產（不會傳回棧疊內的資產）。 選取「否」可將資產包含在結果中的棧疊中。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 子型別值（以分號分隔）]</td>
      <td>
        <p>輸入要傳回的子型別值清單（以分號分隔），或對應。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 旗標值（以分號分隔）]</td>
      <td>
        <p>輸入要傳回的標幟值清單（以分號分隔），或對應。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 要包含的其他資料欄位（以分號分隔）]</td>
      <td>
        <p>若包含資產，則會包含所有欄位，否則僅傳回id和自我href連結。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 要排除的資產型別]</td>
      <td>
        <p>選取是否要排除完整或不完整的資產。 若要包含所有資產，請將此欄位留空。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資產ID]</td>
      <td>
        <p>輸入或對應最多100個資產ID，以逗號分隔。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 根據簡報篩選器篩選出專輯資產]</td>
      <td>
        <p>此欄位設為「true」時，會根據相簿上設定的簡報篩選器篩選出所有相簿資產。 使用此引數，無論簡報篩選器中的設定為何，都會篩選掉已拒絕的資產。 為album_filters設定「true」以外的任何值時，不會套用簡報篩選器。 預設行為是顯示所有資產。 此引數不能與旗標引數一起使用。 </p>
      </td>
    </tr>
  </tbody>
</table>

#### 擷取相簿

此動作模組會擷取指定目錄中的相簿清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含您要擷取之相簿的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 子型別]</td>
      <td>
        <p>輸入要傳回的子型別值清單（以分號分隔），或對應。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目前結果前面的相簿名稱]</td>
      <td>
        <p>如果您要分頁結果，請輸入或對應上一頁最後一張相簿的名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 要傳回的相簿數]</td>
      <td>
        <p>設定Workfront Fusion在一個執行週期內傳回的最大資產數量。 此欄位的預設值為100。如果限制邊界處的多個相簿具有相同的<code>name_after</code>值，則此模組可能會傳回比此限制更多的相簿。</p>
      </td>
    </tr>
  </tbody>
</table>

#### 更新相簿

此動作模組會更新指定的相簿。

更新的相簿必須是由目前進行更新的相同使用者端應用程式所建立，而且必須是子型別`project`或`project_set`。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Lightroom]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-lightroom" class="MCXref xref" >建立與[!DNL Adobe Lightroom]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 目錄ID]</td>
      <td>
        <p>輸入或對應包含要更新之相簿的目錄ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 相簿ID]</td>
      <td>
        <p>輸入或對應您要更新的相簿識別碼。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">其他欄位</td>
      <td>
      <td>如需此模組中其他欄位的說明，請參閱本文中的<a href="#create-an-album" class="MCXref xref" >建立相簿</a>。</td>
      </td>
    </tr>
  </tbody>
</table>

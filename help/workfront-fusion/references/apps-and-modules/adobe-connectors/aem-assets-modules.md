---
title: Adobe Experience Manager Assets 模組
description: 透過適用於 Adobe Workfront Fusion 的 Adobe Experience Manager Assets 連接器，您可以建立、上傳和更新資產，以及複製或移動資料夾和資產。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: d4bdc4005a3b7b22d64adc8ca1d20bcf534ddfd1
workflow-type: ht
source-wordcount: '3734'
ht-degree: 100%

---

# Adobe Experience Manager Assets 模組

透過適用於 Adobe Workfront Fusion 的 Adobe Experience Manager Assets 連接器，您可以建立、上傳和更新資產，以及複製或移動資料夾和資產。

如需關於 Adobe Experience Manager Assets 連接器的簡介影片，請參閱：

* [Adobe Experience Manager Assets](https://video.tv.adobe.com/v/3427034/){target=_blank}

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

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

* 您必須具備 Adobe Experience Manager Assets 帳戶才能使用這些模組。
* 您必須在 Adobe Developer Console 中設定伺服器對伺服器流程。

  關於在 Adobe Developer Console 中設定伺服器對伺服器流程的說明，請參閱[為伺服器端 API 產生存取權杖](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=zh-Hant#the-server-to-server-flow)。
* 您的 Adobe Experience Manager 技術帳戶必須擁有寫入權限。

  關於將寫入權限新增至您的 Adobe Experience Manager 技術帳戶的說明，請參閱 Adobe Experience Manager 文件中的[服務認證](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials)。

## Adobe Experience Manager Assets API 資訊

Adobe Experience Manager Assets 連接器會使用以下項目：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.8.61</td> 
  </tr>
 </tbody> 
 </table>

## 將 Adobe Experience Manager Assets 連接至 Workfront Fusion {#connect-adobe-experience-manager-assets-to-workfront-fusion}

若要為您的 Adobe Experience Manager Assets 模組建立連線：

1. 按一下「連線」方框旁的「新增」。

2. 選取要建立的連線類型：

   * **AEM Assets as a Cloud Service**

     此設定需要取自 Adobe Admin Console 的資訊。

   * **AEM Assets Basic (Adobe Managed Services)**

     此設定需要使用者名稱和密碼。

3. 針對您正在連立的連線類型填寫相關欄位。

   若為 AEM Assets as a Cloud Service，請參閱[設定 AEM Assets as a Cloud Service 的連線](#configure-the-connection-for-aem-assets-as-a-cloud-service)。

   若為 AEM Assets Basic (Adobe Managed Services)，請參閱[設定 AEM Assets Basic 的連線](#configure-the-connection-for-aemassets-basic-adobe-managed-services)。

4. 按一下「**繼續**」，儲存連線並返回模組。


### 設定 AEM Assets as a Cloud Service 的連線

>[!NOTE]
>
>* 要填入這些欄位的資訊是在 Adobe Developer Console 上設定伺服器對伺服器流程的過程中產生的。您可以在設定過程中產生的服務認證 JSON 檔案中找到這些值。
>
>   關於在 Adobe Developer Console 上設定伺服器對伺服器流程的說明，請參閱[為伺服器端 API 產生存取權杖](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=zh-Hant#the-server-to-server-flow)。
>
>* 您的 Adobe Experience Manager 技術帳戶必須擁有寫入權限。
>
>   關於將寫入權限新增至您的 Adobe Experience Manager 技術帳戶的說明，請參閱 Adobe Experience Manager 文件中的[服務認證](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials)。


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">連線名稱</td>
                  <td>
                      <p>輸入此連線的名稱。</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">不含結尾斜線的執行個體 URL</td>
                  <td>輸入 Adobe Experience Manager 執行個體的 URL。請勿在 URL 的結尾包含斜線 <code>/</code>。</td>
              </tr>
              <tr>
                  <td role="rowheader">帳戶詳細資訊填寫選項</td>
                  <td>選取是否要提供描述您的帳戶詳細資訊的 JSON，或者要手動輸入詳細資訊。</td>
              </tr>
              <tr>
                  <td role="rowheader">採用 JSON 格式的技術帳戶詳細資訊</td>
                  <td>若提供 JSON，請輸入或貼上描述您的帳戶詳細資訊的 JSON。</td>
              </tr>
              <tr>
                  <td role="rowheader">用戶端 ID</td>
                  <td>若手動輸入詳細資訊，請輸入在伺服器對伺服器設定中產生的用戶端 ID。</td>
              </tr>
              <tr>
                  <td role="rowheader">用戶端密碼</td>
                  <td>若手動輸入詳細資訊，請輸入在伺服器對伺服器設定中產生的用戶端密碼。</td>
              </tr>
              <tr>
                  <td role="rowheader">技術帳戶 ID</td>
                  <td>若手動輸入詳細資訊，請輸入技術帳戶的 ID，也就是用戶端認證 JSON 檔案中的「id」欄位。</td>
              </tr>
              <tr>
                  <td role="rowheader">組織 ID</td>
                  <td class="">若手動輸入詳細資訊，請輸入您組織的 ID，也就是用戶端認證 JSON 檔案中的「org」欄位。</td>
              </tr>
              <tr>
                  <td role="rowheader">Meta 權限範圍</td>
                  <td>輸入在伺服器對伺服器設定中產生的 Meta 權限範圍。</td>
              </tr>
              <tr>
                  <td role="rowheader">私密金鑰</td>
                  <td>輸入在伺服器對伺服器設定中產生的私密金鑰。若要擷取私密金鑰，請按一下「擷取」，然後輸入要擷取的檔案及該檔案的密碼。</td>
              </tr>
              <tr>
                  <td role="rowheader">驗證 URL</td>
                  <td>輸入此帳戶的驗證 URL。</td>
              </tr>
          </tbody>
      </table>


### 設定 AEM Assets Basic (Adobe Managed Services) 的連線

<table style="table-layout:auto"> 
        <col/>
        <col />
        <tbody>
            <tr>
                <td role="rowheader">連線名稱</td>
                <td>
                    <p>輸入此連線的名稱。</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">不含結尾斜線的執行個體 URL</td>
                <td>輸入 Adobe Experience Manager 執行個體的 URL。請勿在 URL 的結尾包含斜線 <code>/</code>。</td>
            </tr>
            <tr>
                <td role="rowheader">使用者名稱</td>
                <td>輸入此連線使用的 AEM Assets 帳戶的使用者名稱。</td>
            </tr>
            <tr>
                <td role="rowheader">密碼</td>
                <td>輸入此連線使用的 AEM Assets 帳戶的密碼。</td>
            </tr>
        </tbody>
    </table>


## Adobe Experience Manager Assets 模組及其欄位

設定 Adobe Experience Manager Assets 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 Adobe Experience Manager Assets 欄位。在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [檔案作業](#files-operations)
* [其他](#other)
* [資產 (作者 API)](#assets-author-api)
* [事件 (作者 API)](#events-author-api)
* [後設資料 (作者 API)](#metadata-author-api)
* [匯入 (作者 API)](#import-author-api)
* [關聯 (作者 API)](#relations-author-api)
* [資料夾 (資料夾 API)](#folders-folders-api)

### 檔案作業

* [完成上傳](#complete-upload)
* [取得預先簽署的儲存空間](#get-presigned-storage)
* [啟動上傳](#initiate-upload)
* [上傳資產](#upload-an-asset)

#### 完成上傳

此動作模組在檔案的所有部分皆上傳後，完成已啟動的上傳。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案名稱</td> 
   <td> <p>輸入或對應所上傳檔案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">上傳權杖</td> 
   <td>輸入或對應在啟動時提供的二進位檔案的上傳權杖。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">MIME 類型</td> 
   <td>輸入或對應已完成檔案的 MIME 類型。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">完整 URI</td> 
   <td>輸入或對應檔案的完整 URI。</td> 
  </tr> 
 </tbody> 
</table>


#### 取得預先簽署的儲存空間

此動作模組會建立暫時的預先簽署 URL，不需要直接的認證即可安全地從 AEM 上傳或下載檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">查詢類型</td> 
   <td> <p>選取您要依據資產的路徑或 ID 來查詢資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產</td> 
   <td>選取前往資產的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">UDID</td> 
   <td>輸入或對應資產的 UDID。</td> 
  </tr> 
 </tbody> 
</table>

#### 啟動上傳

此動作模組會啟動上傳。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">目標</td> 
   <td> <p>選取您要將檔案上傳至哪一個資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案名稱</td> 
   <td> <p>輸入或對應所上傳檔案的名稱</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案大小上限</td> 
   <td>輸入或對應所上傳檔案的大小，以位元組為單位。</td> 
  </tr> 
 </tbody> 
</table>


#### 上傳資產

此動作模組會將資產上傳至您的 Adobe Experience Manager Assets 帳戶。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">目標</td> 
   <td> <p>選取您要將資產上傳至哪一個資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">來源檔案</td> 
   <td>輸入或對應來源檔案的名稱和資料。</td> 
  </tr> 
 </tbody> 
</table>

### 其他


* [複製資料夾或資產](#copy-a-folder-or-asset)
* [建立記錄](#create-a-record)
* [刪除資料夾、資產或轉譯](#delete-a-folder-asset-or-rendition)
* [取得資料夾清單](#get-a-folder-listing)
* [進行自訂的 API 呼叫](#make-a-custom-api-call)
* [移動資料夾或資產](#move-a-folder-or-asset)
* [更新記錄](#update-a-record)



#### 複製資料夾或資產

此動作模組會將資料夾或資產複製到您 Adobe Experience Manager Assets 帳戶中的其他位置。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要複製資料夾或資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾/資產</td> 
   <td>選取或對應您要複製的資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">目標路徑</td> 
   <td>選取或對應前往新資料夾或資產位置的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">所複製資料夾/資產的名稱</td> 
   <td>輸入新資料夾或資產的名稱。Adobe Experience Manager Assets 中顯示的資料夾名稱與原始名稱相同。此處輸入的名稱會出現在新資料夾或資產的 URL 中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">複製子系</td> 
   <td>若複製資料夾，請啟用此選項，以便複製資料夾內任何子資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>啟用此選項，以便覆寫目標位置上與所複製的資料夾或資產擁有相同名稱的任何資料夾或資產。</td> 
  </tr> 
 </tbody> 
</table>



#### 建立記錄

此動作模組會建立資料夾或資產註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">物件類型</td> 
   <td> <p>選取您要建立資料夾或資產註解。</p> 
    <ul> 
     <li> <p>資料夾</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p>名稱</p> <p>輸入資料夾名稱。此名稱會出現在檔案路徑中，因此不得包含空格或其他字元。 </p> </li> 
       <li> <p>標題</p> <p>輸入資料夾的標題，可代替名稱顯示。</p> </li> 
      </ul> </li> 
     <li> <p>資產註解</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p>資產選取範圍</p> <p>選取或對應您要新增註解的資產之 ID。</p> </li> 
       <li> <p>註解</p> <p>輸入註解的文字。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 刪除資料夾、資產或轉譯

此動作模組會刪除資料夾、資產或轉譯。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要刪除資料夾、資產或轉譯。</p> 
    <ul> 
     <li> <p>資料夾</p> <p>選取資料夾路徑中的資料夾，以便選取要刪除的資料夾。</p> </li> 
     <li> <p>資產</p> <p>選取資產，先從其路徑中選取資料夾，然後選取要刪除的資產。</p> </li> 
     <li> <p>轉譯</p> <p>選取轉譯路徑中的資料夾，以便選取轉譯。</p> <p>輸入或對應轉譯的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得資料夾清單

此動作模組可檢索現有資料夾及其子系實體 (資料夾或資產) 的呈現方式。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾</td> 
   <td>選取或對應您要檢索的資料夾。若要將子資料夾新增至路徑，請按一下加號圖示並選取子資料夾。</td> 
  </tr> 
 </tbody> 
</table>

#### 進行自訂的 API 呼叫

此動作模組會對 Adobe Experience Manager Assets API 進行自訂的 API 呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>URL</p> </td> 
   <td> <p>輸入相對於 Adobe Experience Manager 基礎 URL 的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>方法</p> </td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">標頭</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion 會自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">查詢字串</td> 
   <td> <p>輸入請求查詢字串。針對每個索引鍵/值配對，按一下「<b>新增項目</b>」並輸入索引鍵和值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">正文</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 移動資料夾或資產

此動作模組會將特定路徑的資產或資料夾移至新位置。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要移動資料夾或資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾/資產</td> 
   <td>選取或對應您要移動的資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">目標路徑</td> 
   <td>選取或對應您要移動資料夾或資產的目標位置之路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">所移動的資料夾/資產的名稱</td> 
   <td>輸入所移動資料夾或資產的新名稱。Adobe Experience Manager Assets 中顯示的資料夾名稱與原始名稱相同。此處輸入的名稱會出現在所移動資料夾或資產的 URL 中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>啟用此選項可覆寫目標位置上與所移動的資料夾或資產具有相同名稱的任何資料夾或資產。</td> 
  </tr> 
 </tbody> 
</table>

#### 更新記錄

此動作模組會更新現有的記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要刪除資產後設資料或資產轉譯。</p> 
    <ul> 
     <li> <p>資產後設資料</p> 
      <ul> 
       <li> <p>選取您要更新其後設資料的資產。</p> </li> 
       <li> <p>輸入資產的新標題。</p> </li> 
      </ul> </li> 
     <li> <p>資產轉譯</p> 
      <ul> 
       <li> <p>選取您要更新其轉譯的資產。</p> </li> 
       <li> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 資產 (作者 API)

* [刪除資產](#delete-asset)
* [取得工作狀態](#get-job-status)

#### 刪除資產

此動作模組會根據資產 ID 刪除單一資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要刪除的資產之 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">強制</td> 
   <td>啟用此選項以便強制刪除資產，即使資產被參照也一樣。</td> 
  </tr> 
 </tbody> 
</table>

#### 取得工作狀態

此動作模組會取得非同步工作的目前狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作 ID</td> 
   <td> <p>輸入或對應您要取得其狀態之工作的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 事件 (作者 API)

#### 監視事件

當 AEM Assets 中發生事件時，此觸發程序模組會啟動一個情境。

此模組包含單一欄位：Webhook。選取供這些事件使用的現有 Webhook，或建立新的 Webhook。

若要建立新的 Webhook：

1. 按一下 Webhook 欄位旁的「**新增**」。
1. 填寫下列欄位：

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">Webhook 名稱</td>
        <td>輸入此 Webhook 的名稱。</td>
       </tr>
       <tr>
         <td role="rowheader">連線</td>
        <td>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</td>
       </tr>
     </tbody>
   </table>

1. 按一下「儲存」，儲存 Webhook 並返回模組。


### 後設資料 (作者 API)

* [取得資產後設資料](#get-asset-metadata)
* [更新資產後設資料](#update-asset-metadata)

#### 取得資產後設資料

此動作模組會檢索指定資產的後設資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要取得其後設資料的資產之 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 更新資產後設資料

此動作模組會更新指定資產的後設資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要更新其後設資料的資產之 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">更新</td> 
   <td> <p>對於您要更新的每個後設資料項目，按一下「<b>新增項目</b>」並選取作業。「新增項目」方框中的其他欄位視所選作業而定。</p> </td> 
  </tr> 
 </tbody> 
</table>


### 匯入 (作者 API)

* [取得匯入工作結果](#get-import-job-results)
* [取得匯入工作狀態](#get-import-job-status)
* [從 URL 上傳資產](#upload-an-asset-from-a-url)

#### 取得匯入工作結果

此動作模組會檢索指定匯入工作的結果。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">匯入工作 ID</td> 
   <td> <p>輸入或對應您要檢索結果的工作之 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得匯入工作狀態

此動作模組會檢索指定匯入工作的狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">匯入工作 ID</td> 
   <td> <p>輸入或對應您要檢索其狀態的工作之 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 從 URL 上傳資產

此動作模組會從指定的 URL 匯入檔案，藉此上傳新資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">標題</td> 
   <td> <p>輸入或對應資產的標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">說明</td> 
   <td> <p>輸入或對應資產的說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">主旨</td> 
   <td> <p>輸入或對應資產的主旨。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">建立者</td> 
   <td> <p>輸入或對應資產的建立者。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">過期日期</td> 
   <td> <p>輸入或對應資產的過期日期。</p><p>如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">類型強制轉換</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">自訂後設資料</td> 
   <td> <p>對於您要新增至資產的每個自訂後設資料項目，按一下「<b>新增項目</b>」，並輸入後設資料的名稱和值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾路徑或 ID</td> 
   <td> <p>選取您要依據路徑或 ID 來指定目標資料夾，然後選取該路徑或輸入 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">要匯入的檔案</td> 
   <td> <p>對於要匯入的每個檔案，按一下<b>「新增項目」並填寫檔案的詳細資訊。<code>Title</code> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"></td> 
   <td> <p></p> </td> 
  </tr> 
 </tbody> 
</table>

### 關聯 (作者 API)

* [建立資產關聯](#create-asset-relations)
* [刪除資產關聯](#create-asset-relations)
* [取得資產關聯類型](#get-asset-relation-types)
* [取得資產關聯](#get-asset-relations)

#### 建立資產關聯

此動作模組會為所選資產建立新的資產關聯。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要與其他資產建立關聯的 ID 資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">關聯的資產</td> 
   <td> <p>對於您要與所選資產建立關聯的每個資產，按一下「<b>新增項目</b>」，然後輸入或對應資產的 ID 及關聯類型。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 刪除資產關聯

此動作模組會刪除資產的資產關聯。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要刪除關聯的 ID 資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">關聯的資產</td> 
   <td> <p>輸入或對應您要刪除的關聯類型。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">提供要刪除的關聯資產的特定 ID</td> 
   <td> <p>若是要刪除一個特定的關聯，請勾選此方框。若未勾選此方框，則會刪除所選類型的所有關聯。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">關聯的資產 ID</td> 
   <td> <p>若要刪除特定關聯，請輸入或對應您要刪除關聯的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### 取得資產關聯類型

此模組會列出指定資產所具備的資產關聯類型清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要列出關聯類型清單的 ID 資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得資產關聯

此模組會列出指定資產的資產關聯清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要列出關聯清單的 ID 資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">關聯類型</td> 
   <td> <p>輸入或對應您要列出關聯的關聯類型清單並以逗號分隔。</p> </td> 
  </tr> 
 </tbody> 
</table>



### 資料夾 (資料夾 API)

* [建立資料夾](#create-folders)
* [依據 ID 刪除資料夾](#delete-a-folder-by-id)
* [依據路徑刪除資料夾](#delete-folders-by-path)
* [取得資料夾工作結果](#get-folders-job-results)
* [取得資料夾工作狀態](#get-folders-job-status)
* [列出資料夾清單](#list-folders)

#### 建立資料夾

此動作模組會在 Adobe Experience Manager Assets 中建立新資料夾。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">要建立的資料夾</td> 
   <td> <p>對於您要建立的每個資料夾，按一下「<b>新增項目</b>」並輸入下列資訊：</p>
   <ul>
   <li><b>新資料夾位置</b><p>選取您要建立新資料夾之位置的路徑。</p></li>
       <li> <b>名稱</b> <p>輸入資料夾名稱。此名稱會出現在檔案路徑中，因此不得包含空格或其他字元。 </p> </li> 
       <li> <b>標題</b> <p>輸入資料夾的標題，可代替名稱顯示。</p> </li> 
   </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 依據 ID 刪除資料夾

此動作模組會刪除具有指定 ID 的 Adobe Experience Manager Assets 資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾 ID</td> 
   <td> 輸入或對應您要刪除的資料夾之 ID。</td>
  </tr> 
 <tr> 
   <td role="rowheader">刪除子資料夾</td> 
   <td> 啟用此選項，以便刪除資料夾及其所有子資料夾。</td>
  </tr> 
 <tr> 
   <td role="rowheader">強制</td> 
   <td> 啟用此選項以便強制刪除資料夾，即使資料夾被參照也一樣。</td>
  </tr> 
 </tbody> 
</table>

#### 依據路徑刪除資料夾

此動作模組會刪除位於指定路徑的 Adobe Experience Manager Assets 資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾路徑</td> 
   <td>對於您要刪除的每個資料夾，按一下「<b>新增項目</b>」並選取資料夾的路徑。</td>
  </tr> 
 <tr> 
   <td role="rowheader">刪除子資料夾</td> 
   <td> 啟用此選項以便刪除資料夾及其所有子資料夾。</td>
  </tr> 
 <tr> 
   <td role="rowheader">強制</td> 
   <td> 啟用此選項以便強制刪除資產，即使資產被參照也一樣。</td>
  </tr> 
 </tbody> 
</table>

#### 取得資料夾工作結果

此模組會檢索 Adobe Experience Manager Assets 資料夾 API 所建立的非同步工作的結果。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作 ID</td> 
   <td> 輸入或對應您要檢索結果的工作之 ID。</td>
  </tr> 
 </tbody> 
</table>

#### 取得資料夾工作狀態

此模組會檢索 Adobe Experience Manager Assets 資料夾 API 所建立的非同步工作的狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作 ID</td> 
   <td> 輸入或對應您要檢索其狀態的工作之 ID。</td>
  </tr> 
 </tbody> 
</table>


#### 列出資料夾清單

此模組會列出指定資料夾的子資料夾清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>關於將 Adobe Experience Manager Assets 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將 Adobe Experience Manager Assets 連接至 Workfront Fusion</a>。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">資料夾路徑或 ID</td> 
   <td> <p>選取您要依據路徑或 ID 來指定目標資料夾，然後選取該路徑或輸入 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
i! I added a lot of modules to the AEM Assets connector and we need new documentation for them. The connector is available in the QA environment. Heres the added modules and a brief description of them, more info about them can be found in the Assets Author Api docs and the Folders Api docs. Im not fully confident that i kept all the best practices for naming things :sweat_smile:, i hope you can take a look at that as well. Let me know if theres anything i can tell about the modules and thanks again in advance!
Author API
Assets
Delete Asset
Deletes an asset when provided an Asset ID, There is a force parameter that when toggled will delete the folder regardless if it's referenced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get assets job status
Given an assets job ID will return the state that the job is currently in (PROCESSING, COMPLETED, etc.)
Events
AEM Assets events
The costumer can create a web hook in this module and register it in the Adobe admin console
Metadata
Get asset metadata
Given asset ID returns assets metadata.
Update asset metadata
Given asset ID, there are 6 patch operations that can be done with the metadata. The operations are visible in the module as well as the documentation.
Import
Get import job results
Given Job ID returns it's result.
Get import job status
Given Job ID returns its status.
Upload an asset from url
Takes global metadata which applies to all the assets and local ones which apply individually.In both it is also possible to specify custom metadata.
Also takes the folder path or folder ID to place the assets there and url-s of the assets.
Relations
Create asset relation
Given asset ID and a list of related asset ID as well as the relation types creates those relationships.
Delete asset relations
Given asset ID and relation type deletes all relations of that type. Can also specify a related asset to target only that.
 there is a checkbox that is checked by default and when unchecked reveals a field where the user can specify the related user ID.
Get asset relation types
Given asset ID returns all the relation types that the asset has.
Get asset relations
Given asset ID returns all relations. Can also specify a specific type of relation.
Folders API
Create folders
Given a list of folders with their path, name, title, creates them.
Delete a folder by ID
Given Folder ID deletes the folder. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Delete folders by path
Given a list of paths, deletes everything in them. There is also a way to specify if it should delete folders recursively and if it should be forced.
Return either nothing if the deletion takes less than a few seconds or a job ID which can be used in another module to track the job of deleting the folder.
Get folders job results
Given job ID returns its result.
Get folders job status
Given job ID returns its status.
List Folders
List folders under the given folder. In the module you can choose the root folder either by ID or by Path.
-->


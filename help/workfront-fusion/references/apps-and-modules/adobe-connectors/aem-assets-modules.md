---
title: Adobe Experience Manager Assets模組
description: 使用適用於Adobe Workfront Fusion的Adobe Experience Manager Assets聯結器，您可以建立、上傳和更新資產，以及複製或行動資料夾和資產。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: 190c35629f1fc1e07eef4110f3f4f771af1065fb
workflow-type: tm+mt
source-wordcount: '3727'
ht-degree: 2%

---

# Adobe Experience Manager Assets模組

使用適用於Adobe Workfront Fusion的Adobe Experience Manager Assets聯結器，您可以建立、上傳和更新資產，以及複製或行動資料夾和資產。

如需Adobe Experience Manager Assets聯結器的簡介影片，請參閱：

* [Adobe Experience Manager Assets](https://video.tv.adobe.com/v/3427034/){target=_blank}

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
   <p>舊版：自動化和整合的Workfront Fusion </p>
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

* 您必須擁有Adobe Experience Manager Assets帳戶才能使用這些模組。
* 您必須在Adobe Developer主控台中設定伺服器對伺服器流程。

  如需在Adobe Developer主控台中設定伺服器對伺服器流量的指示，請參閱[產生伺服器端API的存取權杖](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=zh-Hant#the-server-to-server-flow)。
* 您的Adobe Experience Manager技術帳戶必須擁有寫入許可權。

  如需新增寫入許可權至您Adobe Experience Manager技術帳戶的指示，請參閱Adobe Experience Manager檔案中的[服務認證](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials)。

## Adobe Experience Manager Assets API資訊

Adobe Experience Manager Assets聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.8.61</td> 
  </tr>
 </tbody> 
 </table>

## 將Adobe Experience Manager Assets連線至Workfront Fusion {#connect-adobe-experience-manager-assets-to-workfront-fusion}

若要建立Adobe Experience Manager Assets模組的連線：

1. 按一下「連線」方塊旁的「新增」。

2. 選取要建立的連線型別：

   * **AEM Assets as a Cloud Service**

     此設定需要來自Adobe Admin Console的資訊。

   * **AEM Assets Basic (Adobe Managed Services)**

     此設定需要使用者名稱和密碼。

3. 填寫您要建立之連線型別的欄位。

   若為AEM Assets as a Cloud Service，請參閱[設定AEM Assets as a Cloud Service的連線](#configure-the-connection-for-aem-assets-as-a-cloud-service)。

   若為AEM Assets Basic (Adobe Managed Services)，請參閱[設定AEM Assets Basic的連線](#configure-the-connection-for-aemassets-basic-adobe-managed-services)。

4. 按一下&#x200B;**繼續**&#x200B;以儲存連線並返回模組。


### 設定AEM Assets as a Cloud Service的連線

>[!NOTE]
>
>* 這些欄位的資訊是在Adobe Developer Console上設定伺服器對伺服器流程時產生的。 您可以在設定過程中產生的服務認證JSON檔案中找到這些值。
>
>   如需在Adobe Developer Console上設定伺服器對伺服器流量的指示，請參閱[產生伺服器端API的存取權杖](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=zh-Hant#the-server-to-server-flow)。
>
>* 您的Adobe Experience Manager技術帳戶必須擁有寫入許可權。
>
>   如需新增寫入許可權至您Adobe Experience Manager技術帳戶的指示，請參閱Adobe Experience Manager檔案中的[服務認證](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials)。


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
                  <td role="rowheader">執行個體URL不含結尾斜線</td>
                  <td>輸入Adobe Experience Manager執行個體的URL。 請勿在URL的結尾包含斜線<code>/</code>。</td>
              </tr>
              <tr>
                  <td role="rowheader">帳戶詳細資料填寫選項</td>
                  <td>選取是否要提供描述您帳戶詳細資料的JSON，或是否要手動輸入詳細資料。</td>
              </tr>
              <tr>
                  <td role="rowheader">JSON格式的技術帳戶詳細資料</td>
                  <td>若提供JSON，請輸入或貼上描述您帳戶詳細資料的JSON。</td>
              </tr>
              <tr>
                  <td role="rowheader">用戶端 ID</td>
                  <td>如果手動輸入詳細資料，請輸入在伺服器對伺服器設定中產生的使用者端ID。</td>
              </tr>
              <tr>
                  <td role="rowheader">用戶端密碼</td>
                  <td>如果手動輸入詳細資料，請輸入在伺服器對伺服器設定中產生的使用者端密碼。</td>
              </tr>
              <tr>
                  <td role="rowheader">技術帳戶ID</td>
                  <td>如果手動輸入詳細資料，請輸入技術帳戶的ID。 這是使用者端憑證JSON檔案中的「id」欄位。</td>
              </tr>
              <tr>
                  <td role="rowheader">組織ID</td>
                  <td class="">如果以手動方式輸入明細，請輸入貴組織的識別碼。 這是使用者端認證JSON檔案中的「org」欄位。</td>
              </tr>
              <tr>
                  <td role="rowheader">Meta範圍</td>
                  <td>輸入在伺服器對伺服器設定中產生的Meta範圍。</td>
              </tr>
              <tr>
                  <td role="rowheader">私密金鑰</td>
                  <td>輸入在伺服器對伺服器安裝程式中產生的私密金鑰。 若要擷取私密金鑰，請按一下擷取，然後輸入要擷取的檔案和檔案密碼。</td>
              </tr>
              <tr>
                  <td role="rowheader">驗證 URL</td>
                  <td>輸入此帳戶的驗證URL。</td>
              </tr>
          </tbody>
      </table>


### 設定AEM Assets Basic (Adobe Managed Services)的連線

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
                <td role="rowheader">執行個體URL不含結尾斜線</td>
                <td>輸入Adobe Experience Manager執行個體的URL。 請勿在URL的結尾包含斜線<code>/</code>。</td>
            </tr>
            <tr>
                <td role="rowheader">使用者名稱</td>
                <td>輸入此連線使用的AEM Assets帳戶使用者名稱。</td>
            </tr>
            <tr>
                <td role="rowheader">密碼</td>
                <td>輸入此連線使用的AEM Assets帳戶密碼。</td>
            </tr>
        </tbody>
    </table>


## Adobe Experience Manager Assets模組及其欄位

設定Adobe Experience Manager Assets模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Adobe Experience Manager Assets欄位，視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [檔案作業](#files-operations)
* [其他](#other)
* [Assets （作者API）](#assets-author-api)
* [事件（作者API）](#events-author-api)
* [中繼資料（作者API）](#metadata-author-api)
* [匯入（作者API）](#import-author-api)
* [關係（作者API）](#relations-author-api)
* [資料夾（資料夾API）](#folders-folders-api)

### 檔案作業

* [完成上傳](#complete-upload)
* [取得預先簽署的儲存空間](#get-presigned-storage)
* [啟動上傳](#initiate-upload)
* [上傳資產](#upload-an-asset)

#### 完成上傳

上傳檔案的所有部分後，此動作模組會完成初始的上傳。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案名稱</td> 
   <td> <p>輸入或對應已上傳檔案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">上傳權杖</td> 
   <td>輸入或對應二進位檔的上傳權杖，如初始化所提供。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">MIME型別</td> 
   <td>輸入或對應已完成檔案的MIME型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">完整URI</td> 
   <td>輸入或對應檔案的完整URI。</td> 
  </tr> 
 </tbody> 
</table>


#### 取得預先簽署的儲存空間

此動作模組會建立暫時的預先簽署URL，以便安全地從AEM上傳或下載檔案，而不需要直接的認證。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">查詢型別</td> 
   <td> <p>選取您要依據資產路徑或ID來查詢資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產</td> 
   <td>選取資產的路徑。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">UDID</td> 
   <td>輸入或對應資產的UDID。</td> 
  </tr> 
 </tbody> 
</table>

#### 啟動上傳

此動作模組會起始上傳。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">目標</td> 
   <td> <p>選取您要上傳檔案的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案名稱</td> 
   <td> <p>輸入或對應已上傳檔案的名稱</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案大小上限</td> 
   <td>輸入或對應已上傳檔案的大小（位元組）。</td> 
  </tr> 
 </tbody> 
</table>


#### 上傳資產

此動作模組會將資產上傳至您的Adobe Experience Manager Assets帳戶。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">目標</td> 
   <td> <p>選取您要上傳資產的檔案夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Source檔案</td> 
   <td>輸入或對應來源檔案的名稱和資料。</td> 
  </tr> 
 </tbody> 
</table>

### 其他


* [複製資料夾或資產](#copy-a-folder-or-asset)
* [建立記錄](#create-a-record)
* [刪除資料夾、資產或轉譯](#delete-a-folder-asset-or-rendition)
* [取得資料夾清單](#get-a-folder-listing)
* [進行自訂API呼叫](#make-a-custom-api-call)
* [行動資料夾或資產](#move-a-folder-or-asset)
* [更新記錄](#update-a-record)



#### 複製資料夾或資產

此動作模組會將資料夾或資產複製到Adobe Experience Manager Assets帳戶中的其他位置。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要複製資料夾還是資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾/資產</td> 
   <td>選取或對應您要複製的資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">目的地路徑</td> 
   <td>選取或將路徑對應到新資料夾或資產的位置。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">複製的資料夾/資產的名稱</td> 
   <td>輸入新資料夾或資產的名稱。 Adobe Experience Manager Assets中顯示的資料夾名稱與原始名稱相同。 此處輸入的名稱會出現在新資料夾或資產的URL中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">複製子項</td> 
   <td>如果複製資料夾，請啟用此選項以複製資料夾中的任何子資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>啟用此選項可覆寫目的地位置上與正在複製的資料夾或資產同名的任何資料夾或資產。</td> 
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
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">物件類型</td> 
   <td> <p>選取您想要在資產上建立資料夾或註解。</p> 
    <ul> 
     <li> <p>資料夾</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p>姓名</p> <p>輸入資料夾的名稱。 此名稱會出現在檔案路徑中，因此不得包含空格或其他字元。 </p> </li> 
       <li> <p>標題</p> <p>輸入資料夾的標題，該標題可顯示而非名稱。</p> </li> 
      </ul> </li> 
     <li> <p>資產註解</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p>資產選取範圍</p> <p>選取或對應您要新增註解的資產ID。</p> </li> 
       <li> <p>評論</p> <p>輸入註解的文字。</p> </li> 
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
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要刪除資料夾、資產或轉譯。</p> 
    <ul> 
     <li> <p>資料夾</p> <p>選取資料夾路徑中的資料夾，以選取要刪除的資料夾。</p> </li> 
     <li> <p>資產</p> <p>選取資產路徑中的資料夾，然後選取您要刪除的資產。</p> </li> 
     <li> <p>轉譯</p> <p>選取轉譯路徑中的資料夾，以選取轉譯。</p> <p>輸入或對映轉譯的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得資料夾清單

此動作模組會擷取現有資料夾及其子系實體（資料夾或資產）的表示法。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾</td> 
   <td>選取或對應您要擷取的資料夾。 若要將子資料夾新增至路徑，請按一下加號圖示並選取子資料夾。</td> 
  </tr> 
 </tbody> 
</table>

#### 進行自訂API呼叫

此動作模組會對Adobe Experience Manager Assets API發出自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>URL</p> </td> 
   <td> <p>輸入相對於Adobe Experience Manager基底URL的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>方法</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">標頭</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion會自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">查詢字串</td> 
   <td> <p>輸入請求查詢字串。 對於每個索引鍵/值組，按一下<b>新增專案</b>並輸入索引鍵和值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">內文</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 行動資料夾或資產

此動作模組會將指定路徑的資產或資料夾移至新位置。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要行動資料夾或資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾/資產</td> 
   <td>選取或對應您要移動的資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">目的地路徑</td> 
   <td>選取或將路徑對應至您要行動資料夾或資產的位置。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">已行動資料夾/資產的名稱</td> 
   <td>為移動的資料夾或資產輸入新名稱。 Adobe Experience Manager Assets中顯示的資料夾名稱與原始名稱相同。 此處輸入的名稱會顯示在行動資料夾或資產的URL中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">覆寫</td> 
   <td>啟用此選項可覆寫目的地位置上與所要行動資料夾或資產同名的任何資料夾或資產。</td> 
  </tr> 
 </tbody> 
</table>

#### 更新記錄

此動作模組會更新現有記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要刪除資產中繼資料還是資產轉譯。</p> 
    <ul> 
     <li> <p>資產中繼資料</p> 
      <ul> 
       <li> <p>選取您要更新中繼資料的資產。</p> </li> 
       <li> <p>輸入資產的新標題。</p> </li> 
      </ul> </li> 
     <li> <p>資產轉譯</p> 
      <ul> 
       <li> <p>選取您要更新轉譯的資產。</p> </li> 
       <li> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Assets （作者API）

* [刪除資產](#delete-asset)
* [取得工作狀態](#get-job-status)

#### 刪除資產

此動作模組會依其ID刪除單一資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要刪除之資產的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">強制</td> 
   <td>啟用此選項以強制刪除資產，即使資產被參考亦然。</td> 
  </tr> 
 </tbody> 
</table>

#### 取得工作狀態

此動作模組取得非同步工作的目前狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作ID</td> 
   <td> <p>輸入或對應您要取得其狀態之作業的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 事件（作者API）

#### 觀看活動

此觸發模組會在AEM Assets中發生事件時啟動案例。

此模組包含單一欄位： Webhook。 選取要用於這些事件的現有webhook，或建立新事件。

若要建立新的webhook：

1. 按一下Webhook欄位旁的&#x200B;**新增**。
1. 填寫下列欄位：

   <table>
     <col/>
     <col/>
     <tbody>
       <tr>
         <td role="rowheader">Webhook名稱</td>
        <td>輸入此webhook的名稱。</td>
       </tr>
       <tr>
         <td role="rowheader">連接</td>
        <td>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</td>
       </tr>
     </tbody>
   </table>

1. 按一下儲存，儲存webhook並返回模組。


### 中繼資料（作者API）

* [取得資產中繼資料](#get-asset-metadata)
* [更新資產中繼資料](#update-asset-metadata)

#### 取得資產中繼資料

此動作模組會擷取指定資產的中繼資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要取得中繼資料之資產的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 更新資產中繼資料

此動作模組會更新指定資產的中繼資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要更新中繼資料的資產ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">更新</td> 
   <td> <p>針對您要更新的每個中繼資料專案，按一下[新增專案] <b> </b>並選取作業。 「新增專案」方塊中的其他欄位視選取的作業而定。</p> </td> 
  </tr> 
 </tbody> 
</table>


### 匯入（作者API）

* [取得匯入工作結果](#get-import-job-results)
* [取得匯入工作狀態](#get-import-job-status)
* [從URL上傳資產](#upload-an-asset-from-a-url)

#### 取得匯入工作結果

此動作模組會擷取指定匯入工作的結果。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">匯入工作ID</td> 
   <td> <p>輸入或對應您要擷取結果之作業的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得匯入工作狀態

此動作模組會擷取指定匯入工作的狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">匯入工作ID</td> 
   <td> <p>輸入或對應您要擷取其狀態之作業的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 從URL上傳資產

此動作模組會從指定的URL匯入檔案，上傳新的資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">標題</td> 
   <td> <p>輸入或對應資產的標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">說明</td> 
   <td> <p>輸入或對映資產的說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">主旨</td> 
   <td> <p>輸入或對應資產的主旨。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">建立者</td> 
   <td> <p>輸入或對映資產的建立者。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">到期日</td> 
   <td> <p>輸入或對應資產的到期日。</p><p>如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">自訂中繼資料</td> 
   <td> <p>針對您想要新增至資產的每個自訂中繼資料專案，按一下<b>新增專案</b>並輸入中繼資料的名稱和值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾路徑或ID</td> 
   <td> <p>選取是否要依路徑或ID指定目的地資料夾，然後選取路徑或輸入ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">要匯入的檔案</td> 
   <td> <p>針對您要匯入的每個檔案，按一下<b>新增專案&lt;/&gt;並填寫檔案的詳細資料。<code>Title</code> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"></td> 
   <td> <p></p> </td> 
  </tr> 
 </tbody> 
</table>

### 關係（作者API）

* [建立資產關係](#create-asset-relations)
* [刪除資產關係](#create-asset-relations)
* [取得資產關係型別](#get-asset-relation-types)
* [取得資產關係](#get-asset-relations)

#### 建立資產關係

此動作模組會為選取的資產建立新的資產關係。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要將其他資產與之建立關聯的ID資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">相關資產</td> 
   <td> <p>針對您想要與選取的資產相關的每個資產，按一下<b>新增專案</b>，然後輸入或對應資產的ID與關聯型別。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 刪除資產關係

此動作模組會刪除資產的資產關係。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要從中刪除關係的ID資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">相關資產</td> 
   <td> <p>輸入或對應您要刪除的關係型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">提供要刪除之相關資產的特定ID</td> 
   <td> <p>如果要刪除一個特定關係，請核取此方塊。 如果未核取此方塊，則會刪除所選型別的所有關係。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">相關資產ID</td> 
   <td> <p>如果要刪除特定關係，請輸入或對應要刪除的關係識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### 取得資產關係型別

此模組會列出指定資產所存在的資產關係型別。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要列出其關係型別的ID資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得資產關係

此模組會列出指定資產的資產關係。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td> <p>輸入或對應您要列出關係的ID資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">關係型別</td> 
   <td> <p>輸入或對應要列出關係之關係型別的逗號分隔清單。</p> </td> 
  </tr> 
 </tbody> 
</table>



### 資料夾（資料夾API）

* [建立資料夾](#create-folders)
* [依ID刪除資料夾](#delete-a-folder-by-id)
* [依路徑刪除資料夾](#delete-folders-by-path)
* [取得資料夾工作結果](#get-folders-job-results)
* [取得資料夾工作狀態](#get-folders-job-status)
* [列出資料夾](#list-folders)

#### 建立資料夾

此動作模組會在Adobe Experience Manager Assets中建立新資料夾。



<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">要建立的資料夾</td> 
   <td> <p>針對您要建立的每個資料夾，按一下<b>新增專案</b>並輸入下列資訊：</p>
   <ul>
   <li><b>新資料夾位置</b><p>選取要建立新資料夾之位置的路徑。</p></li>
       <li> <b>名稱</b> <p>輸入資料夾的名稱。 此名稱會出現在檔案路徑中，因此不得包含空格或其他字元。 </p> </li> 
       <li> <b>標題</b> <p>輸入資料夾的標題，該標題可顯示而非名稱。</p> </li> 
   </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 依ID刪除資料夾

此動作模組會刪除具有指定ID的Adobe Experience Manager Assets資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾 ID</td> 
   <td> 輸入或對應您要刪除的資料夾識別碼。</td>
  </tr> 
 <tr> 
   <td role="rowheader">刪除子資料夾</td> 
   <td> 啟用此選項可刪除資料夾及其所有子資料夾。</td>
  </tr> 
 <tr> 
   <td role="rowheader">強制</td> 
   <td> 啟用此選項以強制刪除資料夾，即使參考資料夾亦然。</td>
  </tr> 
 </tbody> 
</table>

#### 依路徑刪除資料夾

此動作模組會刪除指定路徑的Adobe Experience Manager Assets資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">資料夾路徑</td> 
   <td>針對您要刪除的每個資料夾，按一下<b>新增專案</b>並選取資料夾的路徑。</td>
  </tr> 
 <tr> 
   <td role="rowheader">刪除子資料夾</td> 
   <td> 啟用此選項可刪除資料夾及其所有子資料夾。</td>
  </tr> 
 <tr> 
   <td role="rowheader">強制</td> 
   <td> 啟用此選項以強制刪除資產，即使資產被參考亦然。</td>
  </tr> 
 </tbody> 
</table>

#### 取得資料夾工作結果

此模組會擷取Adobe Experience Manager Assets資料夾API建立的非同步作業的結果。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作ID</td> 
   <td> 輸入或對應您要擷取結果之作業的ID。</td>
  </tr> 
 </tbody> 
</table>

#### 取得資料夾工作狀態

此模組會擷取Adobe Experience Manager Assets資料夾API所建立非同步工作的狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作ID</td> 
   <td> 輸入或對應您要擷取其狀態之作業的ID。</td>
  </tr> 
 </tbody> 
</table>


#### 列出資料夾

此模組會列出指定資料夾的子資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將Adobe Experience Manager Assets帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager Assets連線至Workfront Fusion</a>。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">資料夾路徑或ID</td> 
   <td> <p>選取是否要依路徑或ID指定目的地資料夾，然後選取路徑或輸入ID。</p> </td> 
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


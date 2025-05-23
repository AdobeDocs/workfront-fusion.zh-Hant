---
title: Adobe Experience Manager Assets模組
description: 使用 [!DNL Adobe Workfront Fusion]的 [!DNL Adobe Experience Manager Assets] 聯結器，您可以建立、上傳和更新資產，以及複製或行動資料夾和資產。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 361e6c9c-1497-4f47-85bb-503619744968
source-git-commit: 40470e5d2183f690ad65f5e1170f78c37dee8603
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Assets]模組

使用[!DNL Adobe Workfront Fusion]的[!DNL Adobe Experience Manager Assets]聯結器，您可以建立、上傳和更新資產，以及複製或行動資料夾和資產。

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

* 您必須有[!DNL Adobe Experience Manager Assets]帳戶才能使用這些模組。
* 您必須在[!DNL Adobe Developer console]中設定[!UICONTROL 伺服器對伺服器]流程。

  如需在[!DNL Adobe Developer console]中設定[!UICONTROL 伺服器對伺服器]流量的指示，請參閱[產生伺服器端API的存取權杖](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=zh-Hant#the-server-to-server-flow)。
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

## 將[!DNL Adobe Experience Manager Assets]連線至[!DNL Workfront Fusion] {#connect-adobe-experience-manager-assets-to-workfront-fusion}

若要為您的[!DNL Adobe Experience Manager Assets]模組建立連線：

1. 按一下[!UICONTROL 連線]方塊旁的[!UICONTROL 新增]。

2. 選取要建立的連線型別：

   * **[!DNL AEM Assets as a Cloud Service]**

     此組態需要來自[!DNL Adobe Admin Console]的資訊。

   * **[!DNL AEM Assets Basic] ([!DNL Adobe Managed Services])**

     此設定需要使用者名稱和密碼。

3. 填寫您要建立之連線型別的欄位。

   若為[!DNL AEM Assets as a Cloud Service]，請參閱[設定 [!DNL AEM Assets as a Cloud Service]](#configure-the-connection-for-aem-assets-as-a-cloud-service)的連線。

   若為[!UICONTROL AEM Assets Basic] ([!DNL Adobe Managed Services])，請參閱[設定[!UICONTROL AEM Assets Basic]](#configure-the-connection-for-aemassets-basic-adobe-managed-services)的連線。

4. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。


### 設定[!DNL AEM Assets as a Cloud Service]的連線

>[!NOTE]
>
>* 這些欄位的資訊是在[!DNL Adobe Developer Console]上設定[!UICONTROL 伺服器對伺服器]流程時產生的。 您可以在設定過程中產生的服務認證JSON檔案中找到這些值。
>
>   如需在[!UICONTROL Adobe Developer Console]上設定[!UICONTROL 伺服器對伺服器]流量的指示，請參閱[產生伺服器端API的存取權杖](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/generating-access-tokens-for-server-side-apis.html?lang=zh-Hant#the-server-to-server-flow)。
>
>* 您的Adobe Experience Manager技術帳戶必須擁有寫入許可權。
>
>   如需新增寫入許可權至您Adobe Experience Manager技術帳戶的指示，請參閱Adobe Experience Manager檔案中的[服務認證](https://experienceleague.adobe.com/zh-hant/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials)。


<table style="table-layout:auto"> 
          <col/>
          <col/>
          <tbody>
              <tr>
                  <td role="rowheader">[!UICONTROL 連線名稱]</td>
                  <td>
                      <p>輸入此連線的名稱。</p>
                  </td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 執行個體URL，不含尾隨斜線]</td>
                  <td>輸入您[!DNL Adobe Experience Manager]執行個體的URL。 請勿在URL的結尾包含斜線<code>/</code>。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 帳戶詳細資料填寫選項]</td>
                  <td>選取是否要提供描述您帳戶詳細資料的JSON，或是否要手動輸入詳細資料。</td>
              </tr>
              <tr>
                  <td role="rowheader">&lbrack;！UICONTROL技術帳戶詳細資料（JSON格式）</td>
                  <td>若提供JSON，請輸入或貼上描述您帳戶詳細資料的JSON。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 使用者端ID]</td>
                  <td>如果手動輸入詳細資料，請輸入在[!UICONTROL 伺服器對伺服器]設定中產生的使用者端ID。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
                  <td>如果手動輸入詳細資料，請輸入在[!UICONTROL 伺服器對伺服器]設定中產生的使用者端密碼。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 技術帳戶ID]</td>
                  <td>如果手動輸入詳細資料，請輸入技術帳戶的ID。 這是使用者端憑證JSON檔案中的「[!UICONTROL id]」欄位。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 組織ID]</td>
                  <td class="">如果以手動方式輸入明細，請輸入貴組織的識別碼。 這是使用者端憑證JSON檔案中的「[!UICONTROL org]」欄位。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 中繼範圍]</td>
                  <td>輸入在[!UICONTROL 伺服器對伺服器]安裝程式中產生的中繼範圍。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 私密金鑰]</td>
                  <td>輸入在[!UICONTROL 伺服器對伺服器]安裝程式中產生的私密金鑰。 若要擷取私密金鑰，請按一下[!UICONTROL 擷取]，然後輸入要擷取的檔案和檔案密碼。</td>
              </tr>
              <tr>
                  <td role="rowheader">[!UICONTROL 驗證URL]</td>
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
                <td role="rowheader">[!UICONTROL 連線名稱]</td>
                <td>
                    <p>輸入此連線的名稱。</p>
                </td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 執行個體URL，不含尾隨斜線]</td>
                <td>輸入您[!DNL Adobe Experience Manager]執行個體的URL。 請勿在URL的結尾包含斜線<code>/</code>。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 使用者名稱]</td>
                <td>輸入此連線使用的[!DNL AEM Assets]帳戶使用者名稱。</td>
            </tr>
            <tr>
                <td role="rowheader">[!UICONTROL 密碼]</td>
                <td>輸入此連線使用的[!DNL AEM Assets]帳戶密碼。</td>
            </tr>
        </tbody>
    </table>


## [!DNL Adobe Experience Manager Assets]模組及其欄位

當您設定[!DNL Adobe Experience Manager Essentials]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe Experience Manager Essentials]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [複製資料夾或資產](#copy-a-folder-or-asset)
* [建立記錄](#create-a-record)
* [刪除資料夾、資產或轉譯](#delete-a-folder-asset-or-rendition)
* [取得資料夾清單](#get-a-folder-listing)
* [進行自訂API呼叫](#make-a-custom-api-call)
* [行動資料夾或資產](#move-a-folder-or-asset)
* [更新記錄](#update-a-record)
* [上傳資產](#upload-an-asset)

### [!UICONTROL 複製資料夾或資產]

此動作模組會將資料夾或資產複製到Adobe Experience Manager Assets帳戶中的其他位置。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要複製資料夾還是資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾] / [!UICONTROL 資產]</td> 
   <td>選取或對應您要複製的資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 目的地路徑]</td> 
   <td>選取或將路徑對應到新資料夾或資產的位置。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 複製資料夾的名稱] / [!UICONTROL 資產]</td> 
   <td>輸入新資料夾或資產的名稱。 在[!DNL Adobe Experience Manager Assets]中顯示的資料夾名稱與原始名稱相同。 此處輸入的名稱會出現在新資料夾或資產的URL中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 複製子項]</td> 
   <td>如果複製資料夾，請啟用此選項以複製資料夾中的任何子資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 覆寫]</td> 
   <td>啟用此選項可覆寫目的地位置上與正在複製的資料夾或資產同名的任何資料夾或資產。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 建立記錄]

此動作模組會建立資料夾或資產註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 物件型別]</td> 
   <td> <p>選取您想要在資產上建立資料夾或註解。</p> 
    <ul> 
     <li> <p>[!UICONTROL 資料夾]</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p>[!UICONTROL 名稱]</p> <p>輸入資料夾的名稱。 此名稱會出現在檔案路徑中，因此不得包含空格或其他字元。 </p> </li> 
       <li> <p>[!UICONTROL 標題]</p> <p>輸入資料夾的標題，該標題可顯示而非名稱。</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL 資產註解]</p> <p>填寫下列欄位：</p> 
      <ul> 
       <li> <p>[!UICONTROL 資產選擇]</p> <p>選取或對應您要新增註解的資產ID。</p> </li> 
       <li> <p>[!UICONTROL 註解]</p> <p>輸入註解的文字。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 刪除資料夾、資產或轉譯]

此動作模組會刪除資料夾、資產或轉譯。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要刪除資料夾、資產或轉譯。</p> 
    <ul> 
     <li> <p>[!UICONTROL 資料夾]</p> <p>選取資料夾路徑中的資料夾，以選取要刪除的資料夾。</p> </li> 
     <li> <p>[!UICONTROL 資產] </p> <p>選取資產路徑中的資料夾，然後選取您要刪除的資產。</p> </li> 
     <li> <p>[!UICONTROL 轉譯]</p> <p>選取轉譯路徑中的資料夾，以選取轉譯。</p> <p>輸入或對映轉譯的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 取得資料夾清單]

此動作模組會擷取現有資料夾及其子系實體（資料夾或資產）的表示法。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾]</td> 
   <td>選取或對應您要擷取的資料夾。 若要將子資料夾新增至路徑，請按一下加號圖示並選取子資料夾。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 進行自訂API呼叫]

此動作模組會對[!DNL Adobe Experience Manager Assets] API發出自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於[!DNL Adobe Experience Manager]基底URL的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串] </td> 
   <td> <p>輸入請求查詢字串。 對於每個索引鍵/值組，按一下<b>[!UICONTROL 新增專案]</b>並輸入[!UICONTROL 索引鍵]和[!UICONTROL 值]。</p> </td> 
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

### [!UICONTROL 行動資料夾或資產]

此動作模組會將指定路徑的資產或資料夾移至新位置。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要行動資料夾或資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資料夾] / [!UICONTROL 資產]</td> 
   <td>選取或對應您要移動的資料夾或資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 目的地路徑]</td> 
   <td>選取或將路徑對應至您要行動資料夾或資產的位置。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 已行動資料夾的名稱] / [!UICONTROL 資產]</td> 
   <td>為移動的資料夾或資產輸入新名稱。 在[!DNL Adobe Experience Manager Assets]中顯示的資料夾名稱與原始名稱相同。 此處輸入的名稱會顯示在行動資料夾或資產的URL中。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 覆寫]</td> 
   <td>啟用此選項可覆寫目的地位置上與所要行動資料夾或資產同名的任何資料夾或資產。</td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 更新記錄]

此動作模組會更新現有記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要刪除資產中繼資料還是資產轉譯。</p> 
    <ul> 
     <li> <p>[!UICONTROL 資產中繼資料]</p> 
      <ul> 
       <li> <p>選取您要更新中繼資料的資產。</p> </li> 
       <li> <p>輸入資產的新標題。</p> </li> 
      </ul> </li> 
     <li> <p>[!UICONTROL 資產轉譯]</p> 
      <ul> 
       <li> <p>選取您要更新轉譯的資產。</p> </li> 
       <li> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 上傳資產]

此動作模組會將資產上傳至您的[!DNL Adobe Experience Manager Assets]帳戶。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Adobe Experience Manager Assets]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-assets-to-workfront-fusion" class="MCXref xref">將[!DNL Adobe Experience Manager Assets]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 目的地]</td> 
   <td> <p>選取您要上傳資產的檔案夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source檔案]</td> 
   <td>輸入或對應來源檔案的名稱和資料。</td> 
  </tr> 
 </tbody> 
</table>

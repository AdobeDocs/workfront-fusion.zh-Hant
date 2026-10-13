---
title: AWS S3 模組
description: '[!DNL Adobe Workfront Fusion AWS] S3模組可讓您對S3儲存貯體執行作業。'
author: Becky
feature: Workfront Fusion
exl-id: 6b2d9dd5-0b33-4297-aea0-aba26072b26a
TQID: 'https://experienceleague.adobe.com/FDkre6osF2kT7Kz-5VGradQLa7GPSJ6MHPH9-FgM-ag'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 7c25013f7a94000651e8331199ad985d40651ae3
workflow-type: tm+mt
source-wordcount: '2637'
ht-degree: 16%
---
# AWS S3 模組

[!DNL Adobe Workfront Fusion AWS] S3模組可讓您對S3儲存貯體執行作業。

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
   <p>作業型：適用於擁有作業型授權的組織</p>
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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!UICONTROL AWS S3]模組，您必須有[!DNL Amazon Web Service]帳戶。

## AWS S3 API資訊

AWS S3聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td><pre><code>https://s3.&#123;&#123;parameters.region&#125;&#125;.amazonaws.com</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.5.21</td> 
  </tr>
 </tbody> 
 </table>

## 將 [!DNL AWS] 連接至 Workfront Fusion {#connect-aws-to-workfront-fusion}

* [使用同盟連線將AWS連線至Workfront Fusion](#connect-aws-to-workfront-fusion-using-a-federated-connection)
* [使用API使用者將AWS連線至Workfront Fusion](#connect-aws-to-workfront-fusion-using-an-api-user)

### 使用同盟連線將AWS連線至Workfront Fusion

+++ 展開以檢視此連線型別的指示。

* [使用同盟連線將AWS連線至Workfront Fusion的必要條件](#prerequisites-to-connecting-aws-to-workfront-fusion-using-a-federated-connection)
* [將Workfront Fusion新增為AWS中的身分提供者](#add-workfront-fusion-as-an-identity-provider-in-aws)
* [建立IAM角色](#create-the-iam-role)
* [在Workfront Fusion中建立連線](#create-the-connection-in-workfront-fusion)
* [將連線新增至角色的信任原則](#add-the-connection-to-the-roles-trust-policy)
* [驗證連線](#verify-the-connection)
* [疑難排解](#troubleshooting)

同盟連線可讓Workfront Fusion存取您的AWS帳戶，而不需要您在Fusion中建立IAM使用者或儲存存取金鑰。
而是要將Workfront Fusion註冊為AWS帳戶中的信任身分提供者，並設定允許哪一個Fusion連線使用特定IAM角色。 連線執行時，Fusion會顯示短暫的身分證明，而AWS會傳回自行過期的暫時憑證。 不會建立、儲存或旋轉任何長效金鑰。

>[!NOTE]
>
>設定此連線需要兩次造訪AWS主控台。 您先建立角色，然後在Workfront Fusion中建立連線，然後返回AWS完成信任原則。 這是因為信任原則的一部分會識別一個特定連線，而該識別碼在建立連線之前並不存在。

#### 使用同盟連線將AWS連線至Workfront Fusion的必要條件

若要建立此連線，您需要下列專案：

* 在AWS IAM中建立身分提供者以及建立與編輯角色的許可權。 這通常表示原則或同等原則。 如果您沒有此存取權，請詢問雲端上的某人或
安全團隊為您完成AWS步驟。
* 能夠在Workfront Fusion中建立連線。


#### 將Workfront Fusion新增為AWS中的身分提供者

此步驟會告知Workfront Fusion所發行的權杖值得信任。 您為每個AWS帳戶執行此動作一次。 如果您組織中的某人已新增此提供者，請跳至[建立IAM角色](#create-the-iam-role)。

1. 登入AWS主控台，並移至&#x200B;**IAM** > **身分識別服務提供者**。
1. 選取&#x200B;**新增提供者**。
1. 對於提供者型別，請選取&#x200B;**OpenID Connect**。
1. 在提供者URL中輸入下列內容，然後選取&#x200B;**取得指紋**：

   ```
   https://oidc.automations.adobe.com
   ```

1. 在對象中，輸入下列內容：

   ```
   sts.amazonaws.com
   ```

1. 選取&#x200B;**新增提供者**。
1. 繼續[建立IAM角色](#create-the-iam-role)。

#### 建立IAM角色

角色會定義在您的AWS帳戶中允許連線的功能。 您可以為每個連線建立一個角色，以便可以獨立授予和撤銷每個連線的存取權。

1. 在IAM中，移至&#x200B;**角色**&#x200B;並選取&#x200B;**建立角色**。
1. 對於信任的實體型別，請選取&#x200B;**網頁身分識別**。
1. 在身分提供者中，選取`oidc.automations.adobe.com`。
1. 在對象中，選取`sts.amazonaws.com`。
1. 選取&#x200B;**下一步**，然後附加此連線所需的許可權原則。
僅授予連線實際使用的許可權。 例如，只讀取下列專案的連線：
一個儲存貯體不需要`AmazonS3FullAccess`。
1. 為角色提供一個清晰的、可辨識的名稱。 例如 `WorkfrontFusionFederatedConnection`。
1. 選取&#x200B;**建立角色**。
1. 開啟您剛建立的角色，並從「摘要」區域複製其ARN。 看起來像這樣： `arn:aws:iam::123456789012:role/WorkfrontFusionFederatedConnection`

1. 繼續[在Workfront Fusion](#create-the-connection-in-workfront-fusion)中建立連線。

#### 在Workfront Fusion中建立連線

1. 在模組的連線設定畫面中，選取同盟連線型別。
1. 輸入您在[建立IAM角色](#create-the-iam-role)中複製的角色ARN。
1. 選取「**建立**」。
Workfront Fusion會顯示三個值。 您可以在下一個程式中使用它們。

<table>
  <tr>
    <td>核發者</td>
    <td>一律為<code>https://oidc.automations.adobe.com</code>。 這符合您在AWS中新增的身分提供者。</td>
  </tr>
  <tr>
    <td>主旨</td>
    <td>識別這個連線。 它看起來像<code>fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964</code>。 您建立的每個連線都不同。</td>
  </tr>
  <tr>
    <td>客群</td>
    <td>一律為<code>sts.amazonaws.com</code>。</td>
  </tr>
</table>

1. 請保持此面板開啟並複製主旨值。

   >[!NOTE]
   >
   >請勿關閉面板或選取「取消」。 連線要等到您完成其餘程式後才會完成。 如果關閉面板，您必須刪除連線並重新開始，因為新的連線會收到新的主旨。

1. 繼續[將連線新增至角色的信任原則](#add-the-connection-to-the-roles-trust-policy)。

#### 將連線新增至角色的信任原則

在您完成此程式之前，角色一般會信任Workfront Fusion，但尚未允許此特定連線使用它。

1. 在新的瀏覽器標籤中，返回AWS主控台並開啟您建立的角色。
1. 選取&#x200B;**信任關係**&#x200B;標籤，然後選取&#x200B;**編輯信任原則**。
1. 以下列專案取代原則，並以您自己的值取代：

   * 將`123456789012`取代為您的AWS帳戶ID
   * 將`sub`值取代為您從Workfront Fusion複製的主旨。


   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow", 
         "Principal": {
           "Federated": "arn:aws:iam::123456789012:oidc-provider/oidc.automations.adobe.com"
       },
       "Action": "sts:AssumeRoleWithWebIdentity", "Condition": {
        "StringEquals": {
          "oidc.automations.adobe.com:sub": "fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964", 
          "oidc.automations.adobe.com:aud": "sts.amazonaws.com"
        }
       }
      }
    ]
   }
   ```

1. 選取&#x200B;**更新原則**。
1. 繼續[驗證連線](#verify-the-connection)。

>[!TIP]
>
>若要讓多個連線使用相同的角色，請將主體以陣列列出。 如果Token符合清單中的任一值，AWS可允許使用該角色：
>
>```
>"oidc.automations.adobe.com:sub": [ "fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964", "fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:29011"
>]
>```
>
>請勿以萬用字元取代子值。 如此一來，組織中的所有連線都能使用角色，包括其他人稍後建立的連線


#### 驗證連線

1. 返回Workfront Fusion瀏覽器索引標籤，其中連線面板仍處於開啟狀態。
1. 按一下「**儲存**」。

   Workfront Fusion聯絡AWS，後者會檢查信任原則並傳回暫時憑證。 如果所有專案皆已正確設定，連線將會成功驗證，您可以繼續設定模組。
   如果驗證失敗，面板會保持開啟並顯示錯誤。 請更正AWS中的問題，然後再次選取「儲存」。 您不需要重新建立連線，而且主旨不會變更。

從這時開始，連線就會更新自己的認證。 沒有要旋轉的索引鍵，也沒有您需要維護的過期專案。

#### 疑難排解


<table>
  <tr>
    <th>錯誤</th>
    <th>其含義</th>
    <th>檢查內容</th>
  </tr>
  <tr>
    <td>InvalidIdentityToken</td>
    <td>AWS無法比對權杖與已註冊的身分提供者。</td>
    <td>請確認您已將「新增Workfront Fusion」中所述的身分提供者新增為AWS中的身分提供者，並確認其URL完全為https://oidc.automations.adobe.com，且沒有尾隨斜線。</td>
  </tr>
  <tr>
    <td>AccessDenied擔任角色</td>
    <td>身分提供者已註冊，但信任原則不符合此連線。</td>
    <td>檢查信任原則中的子值是否為與Workfront Fusion中顯示的主旨相同的字元對字元，且aud為sts.amazonaws.com。 從不同連線複製的主體是最常見的原因。</td>
  </tr>
  <tr>
    <td>連線可正常運作，之後會失敗</td>
    <td> </td>
    <td>檢查角色的許可權原則是否已變更，或角色是否已刪除並重新建立。 重新建立角色不會變更其ARN，但會重設其信任原則。</td>
  </tr>
</table>

+++

### 使用API使用者將AWS連線至Workfront Fusion

+++ 展開以檢視此連線型別的指示。

若要將[!DNL AWS S3]連線至Workfront Fusion，您必須將您的[!DNL AWS]帳戶連線至Workfront Fusion。 若要這麼做，您必須先在[!DNL AWS] [!UICONTROL IAM]中建立API使用者。

1. 登入您的[!DNL AWS] [!UICONTROL IAM]帳戶。
1. 瀏覽至&#x200B;**[!UICONTROL 識別與存取管理]** > **[!UICONTROL 存取管理]** > **[!UICONTROL 使用者]**。

1. 按一下&#x200B;**[!UICONTROL 新增使用者]**。
1. 輸入新使用者的名稱，並在[!UICONTROL 存取型別]區段中選取&#x200B;**[!UICONTROL 程式化存取]**&#x200B;選項。
1. 按一下&#x200B;**[!UICONTROL 直接附加現有原則]**，然後在搜尋列中搜尋&#x200B;**[!UICONTROL AmazonS3FullAccess]**。 當它出現時，按一下它，然後按一下&#x200B;**[!UICONTROL 下一步]**。

1. 繼續其他對話方塊畫面，然後按一下[建立使用者]。**&#x200B;**
1. 複製提供的&#x200B;**[!UICONTROL 存取金鑰識別碼]**&#x200B;和&#x200B;**[!UICONTROL 秘密存取金鑰]**。

1. 前往Workfront Fusion並開啟[!DNL AWS S3]模組的&#x200B;**[!UICONTROL 建立連線]**&#x200B;對話方塊。
1. 在步驟7的個別欄位中輸入[!UICONTROL 存取金鑰識別碼]和[!UICONTROL 秘密存取金鑰]，然後按一下[繼續]&#x200B;**[!UICONTROL 以建立連線]**。

已建立連線。 您可以繼續設定模組。

+++

## [!DNL AWS S3] 模組及其欄位

* [動作](#actions)
* [搜尋](#searches)

當您設定 [!DNL AWS S3] 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL AWS S3] 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [搜尋](#searches)

### 動作

* [[!UICONTROL 建立貯體]](#create-bucket)
* [[!UICONTROL 取得檔案]](#get-file)
* [[!UICONTROL 進行API呼叫]](#make-an-api-call)
* [[!UICONTROL 上傳檔案]](#upload-file)

#### [!UICONTROL 建立貯體]

此動作模組會在AWS中建立貯體。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>關於將您的 [!DNL AWS] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將 [!DNL AWS] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 名稱] </td> 
   <td> <p>輸入新儲存貯體的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 區域] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱AWS檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">區域端點</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得檔案]

此動作模組會從貯體下載檔案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>關於將您的 [!DNL AWS] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將 [!DNL AWS] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 區域] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">區域端點</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>選取要從中下載檔案的貯體。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 路徑]</p> </td> 
   <td> <p>輸入檔案的路徑。 範例：<code>/photos/2019/February/image023.jpg</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行API呼叫]

此動作模組會對AWS S3 API進行自訂呼叫。

如需[!DNL Amazon S3] API的詳細討論，請參閱[[!DNL Amazon S3] [!UICONTROL REST] API簡介](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html)。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線] </td> 
   <td> <p>關於將您的 [!DNL AWS] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將 [!DNL AWS] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 區域] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">區域端點</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL URL]</td> 
   <td> <p>輸入主機URL。 路徑必須相對於<code> https://s3.&lt;selected-region>.amazonaws.com/</code>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的[!UICONTROL HTTP]要求方法。 如需詳細資訊，請參閱Adobe Workfront Fusion</a>中的<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">[!UICONTROL HTTP]要求方法。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 標頭]</td> 
   <td> <p>新增請求標頭。 對於每個要新增的標頭，按一下<b>新增專案</b>並輸入標頭。 您可以使用以下常見的請求標頭。 如需更多要求標頭，請參閱<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/RESTCommonRequestHeaders.html">[!DNL AWS S3] API檔案</a>。</p> <p>Workfront Fusion 會自動新增授權標頭。</p> 
    <table style="table-layout:auto">
     <col> 
     <col> 
     <thead> 
      <tr> 
       <th>標頭名稱</th> 
       <th> <p> 說明</p> </th> 
      </tr> 
     </thead> 
     <tbody> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Length]</p> </td> 
       <td> <p>根據RFC 2616的訊息長度（沒有標頭）。 載入XML的[!UICONTROL PUT]和作業（例如記錄和ACL）需要此標頭。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-Type]</p> </td> 
       <td> <p>資源的內容型別（若請求內容位於內文中）。 範例：<code>text/plain</code>。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Content-MD5]</p> </td> 
       <td> <p>根據RFC 1864，訊息的base64已編碼128位元MD5摘要（沒有標頭）。 此標頭可用作訊息完整性檢查，以確認資料與原來傳送的資料相同。 雖然這是選擇性的，但建議您使用[!UICONTROL Content-MD5]機製作為端對端的完整性檢查。 如需[!UICONTROL REST]要求驗證的詳細資訊，請參閱AWS檔案中的<a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html?r=1821">簽署及驗證REST要求</a>。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL 日期]</p> </td> 
       <td> <p>根據請求者的目前日期和時間。 範例：<code>Wed, 01 Mar 2006 12:00:00 GMT</code>。 當您指定<code>Authorization </code>標頭時，必須指定<code>x-amz-date</code>或<code>Date </code>標頭。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL Expect]</p> </td> 
       <td> <p>當您的應用程式使用[!UICONTROL 100-continue]時，它會在收到確認後才傳送要求內文。 如果郵件根據標題遭到拒絕，則不會傳送郵件內文。 此標頭只有在傳送內文時才能使用。</p> <p>有效值： [!UICONTROL 100-continue]</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL 主機]</p> </td> 
       <td> <p>對於路徑樣式要求，值為<code>s3.amazonaws.com</code>。 對於虛擬樣式要求，值為<code>BucketName.s3.amazonaws.com</code>。 如需詳細資訊，請參閱AWS檔案中的<a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html">虛擬託管</a>。</p> <p>HTTP 1.1需要此標頭（大部分的Toolkit會自動新增此標頭）；HTTP/1.0要求則選填。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-content-sha256]</p> </td> 
       <td> <p>使用簽名版本4驗證請求時，此標頭會提供請求承載的雜湊。 以區塊上傳物件時，請將值設為<code>STREAMING-AWS4-HMAC-SHA256-PAYLOAD</code>，表示簽章僅涵蓋標題且沒有裝載。 如需詳細資訊，請參閱AWS檔案中的<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-streaming.html">授權標頭的簽章計算</a>。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-date]</p> </td> 
       <td> <p>根據請求者的目前日期和時間。 範例：<code>Wed, 01 Mar 2006 12:00:00 GMT</code>。 當您指定<code>Authorization </code>標頭時，必須指定<code>x-amz-date</code>或<code>Date </code>標頭。 如果您同時指定兩者，則以<code>x-amz-date</code>標頭指定的值優先。</p> </td> 
      </tr> 
      <tr> 
       <td role="rowheader"> <p>[!UICONTROL x-amz-security-token]</p> </td> 
       <td> <p>此標題可用於下列情況：</p> 
        <ul> 
         <li>提供[!DNL Amazon DevPay]作業的安全性權杖。 每個使用[!DNL Amazon DevPay]的請求都需要兩個<code>x-amz-security-token</code>標頭：一個用於產品權杖，另一個用於使用者權杖。 當[!DNL Amazon S3]收到驗證要求時，會將計算的簽章與提供的簽章做比較。 用來計算簽章的多值標頭格式不正確，可能會導致驗證問題。</li> 
         <li>提供使用臨時安全性憑證時的安全性權杖。 使用您從IAM取得的臨時安全性認證提出請求時，您必須使用此標頭提供安全性權杖。 若要深入瞭解臨時安全性認證，請前往提出要求。</li> 
        </ul> <p>使用[!DNL Amazon DevPay]的請求和使用臨時安全性認證簽署的請求需要此標頭。</p> </td> 
      </tr> 
     </tbody> 
    </table> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 查詢字串]</td> 
   <td> <p>新增所需的查詢字串，例如引數或表單欄位。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：   <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳檔案]

此動作模組會將檔案上傳至AWS S3貯體。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>關於將您的 [!DNL AWS] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將 [!DNL AWS] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 區域] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">區域端點</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 資料夾] </p> </td> 
   <td> <p>指定您要上傳檔案的目標資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Headers] （選擇性）</p> </td> 
   <td> <p> 針對您要新增的每個標頭，按一下<b>新增專案</b>並輸入標頭的鍵和值。</p><p> 如需可用的標頭，請參閱AWS檔案中的<a href="https://docs.aws.amazon.com/AmazonS3/latest/API/API_PutObject.html">PutObject</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL 列出檔案]](#list-files)
* [[!UICONTROL 列出資料夾]](#list-folders)

#### [!UICONTROL 列出檔案]

從指定位置傳回檔案清單。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>關於將您的 [!DNL AWS] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將 [!DNL AWS] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 區域] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">區域端點</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>選取您要搜尋檔案的[!DNL Amazon S3]儲存貯體。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 前置詞]</p> </td> 
   <td> <p> 輸入要在其中查閱檔案之資料夾的路徑，例如 <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出資料夾]

從指定位置傳回資料夾清單。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>關於將您的 [!DNL AWS] 帳戶連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-aws-to-workfront-fusion" class="MCXref xref">將 [!DNL AWS] 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 區域] </td> 
   <td> <p>選取您的區域端點。 如需詳細資訊，請參閱[!DNL AWS]檔案中的<a href="https://docs.aws.amazon.com/general/latest/gr/rande.html#regional-endpoints">區域端點</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bucket] </td> 
   <td> <p>選取您要搜尋資料夾的[!DNL Amazon S3]貯體。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 前置詞] （選擇性）</p> </td> 
   <td> <p> 要在其中查閱資料夾的資料夾路徑，例如 <code>workfrontfusion/work.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

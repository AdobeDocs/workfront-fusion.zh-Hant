---
title: HTTP >建立JWT請求模組
description: Adobe Workfront Fusion HTTP >發出JWT請求模組會傳送HTTP(S)請求至URL，並以Fusion自動為您簽署的JSON Web權杖來授權它。
author: Becky
feature: Workfront Fusion
exl-id: 2f8c0b0d-085a-4b49-b350-4fd4cca1d0a7
TQID: 'https://experienceleague.adobe.com/'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 5e6403abee4e5767da9134529b9e88070bad5f44
workflow-type: tm+mt
source-wordcount: '1437'
ht-degree: 11%
---
# [!UICONTROL HTTP] > [!UICONTROL 發出JWT請求]模組

Adobe Workfront Fusion [!UICONTROL HTTP] > [!UICONTROL 發出JWT請求]模組會傳送HTTP(S)請求給URL，並授權它使用JSON Web權杖(JWT)，模組會在每次呼叫時為您簽署。 接著會以處理標準[!UICONTROL HTTP] > [!UICONTROL 提出要求]模組相同的方式處理回應。

此模組的行為類似標準[!UICONTROL 提出要求]模組，主要差異在於：它會自動從您提供的宣告簽署JWT，並將其新增至要求，預設為`Authorization: Bearer <token>`。

使用此模組來呼叫任何需要已簽署JWT以進行驗證的API，例如需要以共用機密(HMAC)或私密金鑰(RSA/ECDSA)簽署的短期持有人權杖的服務，而不需在單獨的步驟中建立該權杖。

如果API使用OAuth 2.0、基本驗證、API金鑰或使用者端憑證，請改用相符的專用HTTP模組。

>[!NOTE]
>
>如果您要連線至目前沒有專用聯結器的Adobe產品，建議您使用Adobe Authenticator模組。
>
>如需詳細資訊，請參閱[Adobe Authenticator模組](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md)。

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 建立JWT連線

此模組需要JWT連線。 連線會儲存簽署資料，因此秘密或私密金鑰不必出現在情境中。

### 在Fusion中建立JWT連線

1. 新增[!UICONTROL HTTP] > [!UICONTROL 將JWT請求]模組新增至您的情境。
1. 按一下&#x200B;**[!UICONTROL 連線]**&#x200B;欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 設定連線欄位：

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader"><p>連線名稱</p></td>
      <td><p>輸入此連線的名稱。</p></td>
     </tr>
     <tr>
      <td role="rowheader"><p>演演算法</p></td>
      <td>
       <p>選取連線的簽署演演算法。</p>
       <ul>
        <li><code>HS256</code></li>
        <li><code>HS384</code></li>
        <li><code>HS512</code></li>
        <li><code>RS256</code></li>
        <li><code>RS384</code></li>
        <li><code>RS512</code></li>
        <li><code>PS256</code></li>
        <li><code>PS384</code></li>
        <li><code>PS512</code></li>
        <li><code>ES256</code></li>
        <li><code>ES384</code></li>
        <li><code>ES512</code></li>
       </ul>
      </td>
     </tr>
     <tr>
      <td role="rowheader"><p>Secret</p></td>
      <td>
       <p>輸入簽署金鑰。</p>
       <ul>
        <li>對於<code>HS*</code>演演算法，請使用共用機密字串。</li>
        <li>對於<code>RS*</code>、<code>PS*</code>和<code>ES*</code>演演算法，請使用PEM編碼的私密金鑰。</li>
       </ul>
      </td>
     </tr>
    </tbody>
   </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

>[!IMPORTANT]
>
>JWT連線只會以一個演演算法簽署。 如果您的案例需要多個簽署演演算法，請為每個演演算法建立個別的連線。 這符合現有的獨立JWT應用程式行為。

## [!UICONTROL HTTP] > [!UICONTROL 發出JWT請求]模組及其欄位

當您設定[!UICONTROL HTTP] > [!UICONTROL 發出JWT請求]模組時，Adobe Workfront Fusion會依照欄位在模組UI中的顯示順序，顯示下列欄位。 在模組中，粗體標題表示那是必要欄位。 除非您選取&#x200B;**[!UICONTROL 顯示進階設定]**，否則標示為進階的欄位會隱藏。

<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader"><p>[!UICONTROL 連線]</p></td>
   <td><p>選取現有的JWT連線或建立新連線。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL URL]</p></td>
   <td><p>要求的目標URL。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL 方法]</p></td>
   <td><p>HTTP方法，例如GET、POST、PUT、PATCH或DELETE。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL 標頭]</p></td>
   <td><p>索引鍵/值格式的自訂請求標頭。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[!UICONTROL 查詢字串]</p></td>
   <td><p>索引鍵/值格式的查詢字串引數。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL主體型別]</p></td>
   <td><p>要求內文的編碼方式。 選項包括Raw、application/x-www-form-urlencoded和multipart/form-data。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL剖析回應]</p></td>
   <td><p>啟用時，Fusion會根據回應內容型別來剖析回應內文。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL JWT裝載（宣告）]</p></td>
   <td><p>JWT裝載中包含的宣告金鑰/值配對。 保留的宣告<code>exp</code>、<code>iat</code>和<code>nbf</code>必須是NumericDate — 自Unix紀元以來的秒數。 宣告值會保留其JSON型別，因此數字會保留數字，而布林值會保留布林值。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL逾時] （進階）</p></td>
   <td><p>指定要求逾時秒數(1-300)。 預設值為40秒。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL重試計數] （進階）</p></td>
   <td><p>指定當請求因可重試的錯誤而失敗時，請求應該重試的次數。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL其他重試狀態碼] （進階）</p></td>
   <td><p>指定應視為可重試的其他HTTP狀態代碼。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL與其他HTTP模組共用Cookie] （進階）</p></td>
   <td><p>啟用此選項即可將伺服器的Cookie與案例中的所有HTTP模組共用。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL自我簽署憑證] （進階）</p></td>
   <td><p>如果您想要使用自我簽署憑證的TLS，請上傳憑證。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL拒絕使用未驗證（自我簽署）憑證的連線] （進階）</p></td>
   <td><p>啟用此選項可拒絕使用未驗證TLS憑證的連線。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL遵循重新導向] （進階）</p></td>
   <td><p>啟用此選項可在3xx回應中跟隨URL重新導向。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL停用將多個相同的查詢字串索引鍵序列化為陣列] （進階）</p></td>
   <td><p>依預設，Workfront Fusion會針對與陣列相同的URL查詢字串引數索引鍵處理多個值。 例如，<code>www.test.com?foo=bar&amp;foo=baz</code>將轉換為<code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code>。 啟動此選項以停用此功能。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL要求壓縮內容] （進階）</p></td>
   <td><p>啟用此選項以請求網站的壓縮版本。 新增<code>[!UICONTROL Accept-Encoding]</code>標頭以要求壓縮內容。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL使用雙向TLS] （進階）</p></td>
   <td><p>啟用此選項以在HTTP請求中使用雙向TLS。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL符號選項] （進階）</p></td>
   <td><p>針對您想要新增至要求的每個符號選項，按一下<b>新增專案</b>並輸入引數的名稱和值。</p><p>傳遞給JWT簽署者的其他選項，例如<code>expiresIn</code>、<code>issuer</code>、<code>audience</code>、<code>subject</code>和<code>keyid</code>。 <code>jsonwebtoken</code>資料庫會解譯<code>expiresIn</code>等期間值。 純數字會被視為毫秒，因此請使用單位字串（例如<code>"1h"</code>或<code>"3600s"</code>）來明確顯示。 演演算法是從連線中取得的，並且無法在此處覆寫。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL標頭名稱] （進階）</p></td>
   <td><p>輸入或對應接收已簽署JWT的請求標頭名稱。 預設值： <code>Authorization</code>。 標頭名稱不可包含點(<code>.</code>)，因為點狀名稱遭到拒絕，且無法在請求記錄中遮罩。</p></td>
  </tr>
  <tr>
   <td role="rowheader"><p>[！UICONTROL權杖型別] （進階）</p></td>
   <td><p>輸入或對應置於Token之前的驗證配置，例如<code>Bearer</code>。 將此項保留空白可傳送不含前置詞的原始權杖。</p></td>
  </tr>
 </tbody>
</table>

## 如何建置權杖

1. 模組會收集[!UICONTROL JWT裝載（宣告）]欄位中的宣告。
1. 保留宣告，例如<code>費用</code>，<code>iat</code>，和<code>nbf</code> 會轉換為NumericDate值。
1. 模組會套用[!UICONTROL 簽署選項]，並使用連線的演演算法簽署權杖。
1. 簽署的權杖會放置在由[!UICONTROL 標頭名稱]定義的請求標頭中。
1. 如果設定了[!UICONTROL Token Type]，模組會在權杖前加上前置詞。 例如，<code>Bearer eyJ...</code>.
1. 已傳送要求，且回應處理方式與標準[!UICONTROL HTTP] > [!UICONTROL 提出要求]模組相同。

簽署的權杖會在除錯和錯誤記錄中自動遮罩，因此永遠不會公開。

## 範例

### 連線

- 演演算法： `HS256`
- 密碼： `my-shared-secret`

### 模組設定

- URL： `https://api.example.com/v1/orders`
- 方法： `GET`
- JWT裝載（宣告）：
  - `sub` = `service-account-42`
  - `iss` = `make-integration`
- 簽署選項：
  - `expiresIn` = `1h`
- 標頭名稱： `Authorization`
- 權杖型別： `Bearer`

### 結果

模組會傳送請求，其標頭類似於：

```text
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

## 常見問題集/疑問

### 為什麼我的Token過期這麼快？

您可能輸入了`expiresIn`的空數字，例如`3600`。 `jsonwebtoken`資料庫會將純數字解譯為毫秒。 請改用單位字串，例如`"1h"`或`"3600s"`。

### 代號何時建立？

模組會在每次模組執行時簽署全新JWT，而不是當您建立連線時。 連線只會儲存簽署材料和演演算法，因此宣告（例如`iat`和`exp`）會反映該模組執行的時間。

如果請求在同一模組執行中重試，Fusion會對這些重試嘗試重複使用相同的已簽署權杖，而不是為每次嘗試簽署新的權杖。 因此，非常短的`expiresIn`值可能會在重試發生之前過期，並導致重試以傳送已過期的Token。 若要避免此情況，請使用清除的單位字串，例如`"1h"`或`"3600s"`，並避免權杖存留期過短。

### 我可以根據每個請求變更演演算法嗎？

否。 演演算法會由連線固定。 如果您需要不同的演演算法，請建立不同的JWT連線。

### 我可以在自訂標頭中傳送Token嗎？

是。 將[!UICONTROL 標頭名稱]欄位設定為自訂名稱，但它不能包含點(`.`)。

### 我可以傳送不含`Bearer`的原始權杖嗎？

是。 將[!UICONTROL Token型別]保留空白。

### 記錄檔中是否顯示權杖？

否。 已簽署的權杖會在偵錯和錯誤記錄中自動遮罩。


>[!NOTE]
>
>技術備註：簽署使用`jsonwebtoken`程式庫並映象獨立JWT應用程式的簽署行為，因此相同的輸入會產生與獨立JWT應用程式相同的權杖。

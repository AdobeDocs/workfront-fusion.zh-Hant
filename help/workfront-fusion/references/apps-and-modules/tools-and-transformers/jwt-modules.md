---
title: jwt模組
description: ' [!DNL Adobe Workfront Fusion] [!UICONTROL JWT]應用程式提供根據提供的演演算法建立JWT權杖的模組。'
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
source-git-commit: e1e15985db9683525250d1f9f9276224b2baf0e6
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# [!UICONTROL JWT]模組

[!DNL Adobe Workfront Fusion] [!UICONTROL JWT]應用程式提供根據提供的演演算法建立JWT權杖的模組。

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
   <p>不需要Workfront Fusion授權。</p>
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

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## JWT API資訊

JWT聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
   <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.1.5</td> 
  </tr>
 </tbody> 
 </table>

## JWT模組及其欄位

### 產生JWT

此模組會根據選取的演演算法產生JWT。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Algorithm]</td> 
   <td> <p>選取您要用來產生JWT的演演算法。</p> <ul>
   <li><b>HS256</b>：使用SHA-256雜湊演演算法的HMAC</li>
   <li><b>HS384</b>：使用SHA-384雜湊演演算法的HMAC</li>
   <li><b>HS512</b>：使用SHA-512雜湊演演算法的HMAC</li>
   <li><b>RS256</b>：使用SHA-256雜湊演演算法的RSASSA-PKCS1-v1_5</li>
   <li><b>RS384</b>：使用SHA-384雜湊演演算法的RSASSA-PKCS1-v1_5</li>
   <li><b>RS512</b>：使用SHA-512雜湊演演算法的RSASSA-PKCS1-v1_5</li>
   <li><b>PS256</b>：使用SHA-256雜湊演演算法的RSASSA-PSS （僅限節點^6.12.0或&gt;=8.0.0）</li>
   <li><b>PS384</b>：使用SHA-384雜湊演演算法的RSASSA-PSS （僅限節點^6.12.0或&gt;=8.0.0）</li>
   <li><b>PS512</b>：使用SHA-512雜湊演演算法的RSASSA-PSS （僅限節點^6.12.0或&gt;=8.0.0）</li>
   <li><b>ES256</b>：使用P-256曲線和SHA-256雜湊演演算法的ECDSA</li>
   <li><b>ES384</b>：使用P-384曲線和SHA-384雜湊演演算法的ECDSA</li>
   <li><b>ES512</b>：使用P-521曲線和SHA-512雜湊演演算法的ECDSA</li>
   </ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Payload] </td> 
   <td> <p>針對您要新增的每個裝載專案，按一下<b>新增專案</b>並輸入專案的索引鍵和值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Options] </td> 
   <td> <p>針對您要新增的每個選項專案，按一下<b>新增專案</b>並輸入專案的索引鍵和值。</p> <p>下列鍵可供使用：
   <ul>
   <li><b>演演算法</b>： （預設： RS256）</li>
   <li><b>expiresIn</b>：以秒或描述時間範圍的字串表示（例如2天、10h、7d）。 數值會解譯為秒數。 如果您使用字串，請務必提供時間單位（天、小時等），否則預設會使用毫秒單位（120等於120毫秒）。</li>
   <li><b>notBefore</b>：以秒為單位表示，或是描述時間範圍的字串（例如2天、10h、7d）。 數值會解譯為秒數。 如果您使用字串，請務必提供時間單位（天、小時等），否則預設會使用毫秒單位（120等於120毫秒）。
</li>
   <li><b>對象</b></li>
   <li><b>簽發者</b></li>
   <li><b>jwtid</b></li>
   <li><b>主旨</b></li>
   <li><b>noTimestamp</b></li>
   <li><b>頁首</b></li>
   <li><b>keyid</b></li>
   <li><b>mutatePayload</b>：如果<code>true</code>，則簽署函式將直接修改裝載物件。 如果在宣告套用至裝載後、但在裝載編碼為Token之前，您需要該裝載的原始參考，這個功能會很好用。</li>
   <li><b>allowInsecureKeySizes</b>：如果<code>true</code>，則允許模數低於2048的私密金鑰用於RSA。</li>
   <li><b>allowInvalidAsymmetricKeyTypes</b>：如果<code>true</code>，則允許不符合指定演演算法的非對稱金鑰。 此選項僅供回溯相容性使用，應避免使用。</li>
   </ul>
   </td> 
  </tr> 
 </tbody> 
</table>

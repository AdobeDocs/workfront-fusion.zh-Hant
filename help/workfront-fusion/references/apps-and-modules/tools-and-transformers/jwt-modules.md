---
title: jwt模組
description: Adobe Workfront Fusion [!UICONTROL JWT]應用程式提供根據提供的演演算法建立JWT權杖的模組。
author: Becky
feature: Workfront Fusion
exl-id: 380f60db-b2ec-411a-86ee-0d5699f19b41
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---

# [!UICONTROL JWT]模組

Adobe Workfront Fusion [!UICONTROL JWT]應用程式提供根據提供的演演算法建立JWT權杖的模組。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

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
   <td role="rowheader">[！UICONTROL演演算法]</td> 
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
   <td role="rowheader">[！UICONTROL裝載] </td> 
   <td> <p>針對您要新增的每個裝載專案，按一下<b>新增專案</b>並輸入專案的索引鍵和值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Options] </td> 
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

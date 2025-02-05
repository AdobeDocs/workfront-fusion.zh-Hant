---
title: HTTP &amp；gt；建立請求模組
description: Adobe Workfront Fusion HTTP &amp；gt；發出請求模組是一個通用模組，可讓您設定HTTP請求並將其提交至伺服器。 接收的HTTP回應隨後會包含在輸出套件組合中。
author: Becky
feature: Workfront Fusion
exl-id: 42f6176e-86e0-489e-868b-66823a932daf
source-git-commit: 5a95b2c191d4e6d8750dc57a47923f416612b4a9
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 1%

---

# [!UICONTROL HTTP] > [!UICONTROL Make a request]模組

[!DNL Adobe Workfront Fusion] [!UICONTROL HTTP] > [!UICONTROL Make a request module]是通用模組，可讓您設定HTTP要求並將其提交至伺服器。 接收的HTTP回應隨後會包含在輸出套件組合中。

>[!NOTE]
>
>如果您要連線至目前沒有專用聯結器的Adobe產品，建議您使用Adobe Authenticator模組。
>
>如需詳細資訊，請參閱[Adobe Authenticator模組](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-authenticator-modules.md)。

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

## [!UICONTROL HTTP] > [!UICONTROL Make a request]模組組態

當您設定[!UICONTROL HTTP] > [!UICONTROL Make a request]模組時，[!DNL Adobe Workfront Fusion]會顯示下列欄位。 模組中的粗體標題表示必填欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Evaluate all states as errors (except for 2xx and 3xx)] </td> 
   <td> <p>使用此選項來設定錯誤處理。</p> <p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">新增錯誤處理</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL] </td> 
   <td> <p>輸入您要傳送請求的URL，例如API端點或網站。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers] </td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 例如， <code>{"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p> 輸入所需的查詢索引鍵/值組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Body type]</p> </td> 
   <td> <p>HTTP內文是HTTP交易訊息中傳輸的資料位元組，緊接在標題之後（如果有任何要使用的話）。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Raw]</strong> </p> <p>Raw內文型別通常適用於大多數HTTP內文要求，即使在開發人員檔案未指定要傳送的資料的情況下亦然。</p> <p>在[!UICONTROL Content type]欄位中指定剖析資料的表單。</p> <p>儘管選取了內容型別，資料仍會以開發人員檔案規定或要求的任何格式輸入。</p> </li> 
     <li> <p><strong>[!UICONTROL Application/x-www-form-urlencoded]</strong> </p> <p>此內文型別使用<code>[!UICONTROL application/x-www-form-urlencoded]</code>為[!UICONTROL POST]資料。</p> <p>對於<code>application/x-www-form-urlencoded</code>，傳送至伺服器的HTTP訊息內文基本上是一個查詢字串。 索引鍵和值是以索引鍵/值組來編碼，以<code>&amp;</code>分隔，並在索引鍵和值之間使用<code>=</code>。 </p> <p>針對二進位資料，請改用<code>[!UICONTROL multipart/form-data]</code>。</p> 
      <div class="example" data-mc-autonum="<b>Example: </b>">
       <span class="autonumber"><span><b>範例： </b></span></span> 
       <p>產生的HTTP要求格式範例：</p> 
       <p><code>field1=value1&amp;field2=value2</code> </p> 
      </div> </li> 
     <li> <p><strong>[!UICONTROL Multipart/form-data]</strong> </p> <p>[!UICONTROL  Multipart/form-data]是用於傳送檔案和資料的HTTP多部分要求。 它通常用於將檔案上傳到伺服器。</p> <p>新增要在請求中傳送的欄位。 每個欄位都必須包含索引鍵/值組。</p> 
      <ul> 
       <li> <p><strong>[!UICONTROL Text]</strong> </p> <p>輸入要在要求內文中傳送的索引鍵和值。</p> </li> 
       <li> <p><strong>[!UICONTROL File]</strong> </p> <p>輸入金鑰，並指定您要在要求內文中傳送的來源檔案。</p> <p>對應您要從上一個模組上傳的檔案（例如[!UICONTROL HTTP] &gt;[!UICONTROL Get a File]或[!UICONTROL Google Drive] &gt;下載檔案），或手動輸入檔案名稱和檔案資料。</p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Parse response]</p> </td> 
   <td> <p>啟用此選項以自動剖析回應並轉換JSON和XML回應。</p> <p>在使用剖析JSON或XML內容之前，請手動執行一次模組，以便模組可以識別回應內容並允許您將它對應到後續模組中。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL User name]</p> </td> 
   <td> <p> 如果您要使用基本授權傳送請求，請輸入使用者名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Password] </td> 
   <td> <p>如果要使用基本授權傳送請求，請輸入密碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timeout] </td> 
   <td> <p>指定要求逾時秒數(1-300)。 預設值為40秒。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Share cookies with other HTTP modules]</td> 
   <td> <p> 啟用此選項即可將伺服器的Cookie與案例中的所有HTTP模組共用。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-signed certificate]</td> 
   <td> <p>若要新增自我簽署憑證：</p>
          <ol>
            <li value="1">
              <p>按一下<b>[!UICONTROL Extract]</b>。</p>
            </li>
            <li value="2">
              <p>選取要解壓縮的檔案型別。</p>
            </li>
            <li value="3">
              <p>選取包含或憑證的檔案。</p>
            </li>
            <li value="4">
              <p>輸入檔案的密碼。</p>
            </li>
            <li value="5">
              <p>按一下<b>[!UICONTROL Save]</b>以擷取檔案並返回模組設定。</p>
            </li>
          </ol>
</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reject connections that are using unverified (self-signed) certificates] </td> 
   <td> <p>啟用此選項可拒絕使用未驗證TLS憑證的連線。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow redirect]</td> 
   <td> <p> 啟用此選項可在3xx回應中跟隨URL重新導向。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Follow all redirects] </td> 
   <td> <p>啟用此選項後，URL重新導向後面會包含所有回應代碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Disable serialization of multiple same query string keys as arrays]</p> </td> 
   <td> <p>根據預設，[!DNL Workfront Fusion]會處理與陣列相同的URL查詢字串引數索引鍵的多個值。 例如，<code>www.test.com?foo=bar&amp;foo=baz</code>將轉換為<code>www.test.com?foo[0]=bar&amp;foo[1]=baz</code>。 啟動此選項以停用此功能。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Request compressed content]</td> 
   <td> <p> 啟用此選項以請求網站的壓縮版本。</p> <p>新增<code>[!UICONTROL Accept-Encoding]</code>標頭以要求壓縮內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Use Mutual TLS]</td> 
   <td> <p>啟用此選項以在HTTP請求中使用雙向TLS。</p> <p>如需雙向TLS的詳細資訊，請參閱<a href="/help/workfront-fusion/references/apps-and-modules/universal-connectors/use-mtls-in-http-modules.md" class="MCXref xref">在HTTP模組中使用雙向TLS</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**範例：**&#x200B;此範例說明如何設定模組以使用JSON裝載提交[!UICONTROL POST]請求：

![進行要求範例](/help/workfront-fusion/references/apps-and-modules/assets/make-a-request-example-350x522.png)

我們不建議直接在[!UICONTROL Request content]欄位中混合使用JSON片段與運算式和專案，因為這會導致無效的JSON。

>[!ENDSHADEBOX]

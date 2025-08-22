---
title: HTTP >其他模組
description: Adobe Workfront Fusion HTTP應用程式提供各種模組，用於根據超文字傳輸通訊協定(HTTP)通訊協定進行通訊。 HTTP是全球資訊網資料通訊的基礎。 您可以使用模組下載網頁和檔案、呼叫Webhook和API端點等。
author: Becky
feature: Workfront Fusion
exl-id: 7db97e6e-262d-4be2-823b-423f56a7d886
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---

# HTTP >其他模組

Adobe Workfront Fusion [!UICONTROL HTTP]應用程式提供各種模組，以供根據超文字傳輸通訊協定(HTTP)通訊協定進行通訊。 HTTP是全球資訊網資料通訊的基礎。 您可以使用模組下載網頁和檔案、呼叫Webhook和API端點等。

模組的正確選擇取決於您要存取的資源所使用的驗證/授權機制。 以下是模組的範例

* **提出要求**：主要用於不使用任何驗證或授權型別的資源
* **提出基本驗證要求**：針對使用[!DNL HTTP]基本驗證(BA)的資源
* **提出OAuth 2.0要求**：針對使用OAuth 2.0授權通訊協定的資源
* **提出使用者端憑證驗證要求**：針對採用需要使用者端憑證之授權通訊協定的資源
* **提出API金鑰授權要求**：針對採用API金鑰授權的資源

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

## 請求模組

如需特定請求模組指示，請參閱下列文章：

* [[!UICONTROL HTTP] > [!UICONTROL 提出要求]模組](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL 發出基本授權要求]模組](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-basic-auth-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL 發出OAuth 2.0請求]模組](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-oauth-2-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL 發出使用者端憑證授權要求]模組](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-a-client-cert-auth-request.md)
* [[!UICONTROL HTTP] > [!UICONTROL 發出API金鑰授權要求]](/help/workfront-fusion/references/apps-and-modules/universal-connectors/http-module-make-an-api-key-auth-request.md)

## 其他動作模組

* [[!UICONTROL 取得檔案]](#get-a-file)
* [[!UICONTROL 解析目標URL]](#resolve-a-target-url)

### [!UICONTROL 取得檔案]

此動作模組會從指定的URL下載檔案。 下載檔案後，您可以使用情境中的其他模組進一步處理檔案（對應檔案資料）。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL將所有狀態評估為錯誤（2xx和3xx除外）] </td> 
   <td> <p>使用此選項來設定錯誤處理。</p> <p>如需詳細資訊，請參閱Adobe Workfront Fusion中的<a href="/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md" class="MCXref xref">錯誤處理</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL URL] </td> 
   <td> <p>輸入或對應您要下載之檔案的URL。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL與其他HTTP模組共用Cookie] </td> 
   <td> <p>如果您希望此網站的Cookie對其他模組可用，請啟用此選項。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 解析目標URL]

此動作模組會解析HTTP重新導向鏈結並傳回目標URL。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL URL] </td> 
   <td> <p>輸入或對應您要解析的URL，例如[!DNL bit.ly] URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL方法] </td> 
   <td> <p>選取您要使用[！UICONTROL HEAD]方法或[！UICONTROL GET]方法。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 疊代器模組

### [!UICONTROL 擷取標頭]

此模組會以個別的套件組合，從指定的HTTP模組傳回每個標題（名稱和值）。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source模組]</td> 
   <td> <p> 選取您要從中擷取標題的模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 產生JSON Web權杖(JWT)

您可使用內建函式產生JWT權杖：

標頭:

![JWT標頭](/help/workfront-fusion/references/apps-and-modules/assets/jwt-header-350x19.png)

複製貼上的程式碼(&amp;P)：

```
{{replace(replace(replace(base64("{""alg"":""HS256"",""typ"":""JWT""}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

裝載：

![JWT承載](/help/workfront-fusion/references/apps-and-modules/assets/jwt-payload-350x17.png)

複製貼上的程式碼(&amp;P)：

```
{{replace(replace(replace(base64("{""iss"":""key"",""exp"":" + (timestamp + 60) + "}"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

Token：

![JWT權杖](/help/workfront-fusion/references/apps-and-modules/assets/jwt-token-350x15.png)

複製貼上的程式碼(&amp;P)：

```
{{1.value}}.{{2.value}}.{{replace(replace(replace(sha256(1.value + "." + 2.value; "base64"; "secret"); "/=/g"; emptystring); "/\+/g"; "-"); "/\//g"; "_")}}
```

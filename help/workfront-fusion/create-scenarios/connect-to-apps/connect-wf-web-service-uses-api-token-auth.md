---
title: 將 Adobe Workfront Fusion 連接至使用 API 權杖授權的網頁服務
description: 有些服務不允許整合解決方案（例如Adobe Workfront Fusion）建立您可在情境中輕鬆使用的應用程式。
author: Becky
feature: Workfront Fusion
exl-id: 4a8ac816-52de-41e8-96d7-1c8cde2ebe32
TQID: https://experienceleague.adobe.com/y1H-y57MvK4LScn9Z6sUYuua3kr3iqyY-ElYkmCgxrI
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 985
ht-degree: 15%

---

# 將 Adobe Workfront Fusion 連接至使用 API 權杖授權的網頁服務

有些服務不允許整合解決方案（例如Adobe Workfront Fusion）建立您可在情境中輕鬆使用的應用程式。

此情況的因應措施是使用「HTTP >提出請求」模組，將所需的服務（應用程式）連線至Workfront Fusion。

本文說明如何使用API金鑰/API權杖將幾乎任何Web服務連線至Workfront Fusion。

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
   <p>聯結器型（舊版）：若要連線至Workfront產品系列以外的應用程式，您必須使用Workfront Fusion進行工作自動化和整合 </p>
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

## 連線到使用API權杖的網站服務

對於大多數Web服務，透過API權杖連線服務的程式都類似。

1. 在網站服務網站上建立應用程式，如本文中[建立新應用程式並取得API權杖](#create-a-new-application-and-obtain-the-api-token)一節所述。
1. 取得API金鑰或API權杖。
1. 新增Workfront Fusion的HTTP >為情境製作請求模組。
1. 根據網站服務的API檔案設定模組，並執行此案例，如本文中[設定HTTP模組](#set-up-the-http-module)一節所述。

>[!NOTE]
>
>此範例會連線至Pushover通知服務。

## 建立新應用程式並取得API權杖

>[!NOTE]
>
>網站服務有多種不同的方式來建立和分發API金鑰或API權杖。 如需有關取得所需Web服務的API金鑰和權杖的指示，請前往該服務的網站並搜尋「API金鑰」或「API權杖」。
>
>我們提供的說明僅包括取得Pushover API金鑰的內容，以作為您可能會找到的內容範例。

1. 登入您的Pushover帳戶。
1. 按一下頁面底部的&#x200B;**建立應用程式/API權杖**。
1. 填寫應用程式資訊，然後按一下&#x200B;**建立應用程式**。
1. 將提供的API權杖儲存在安全的地方。 Workfront Fusion HTTP >建立請求模組以連線至所需的Web服務（在此例中為Pushover）時，您需要它。

## 設定HTTP模組

若要將Web服務連線至您的Workfront Fusion案例，您需要在案例中使用「HTTP >提出請求」模組，並根據網站服務的API檔案設定模組。

1. 新增HTTP >向情境提出請求模組。
1. 若要使用Workfront Fusion推送訊息，請依照以下方式設定HTTP模組。

   >[!NOTE]
   >
   >這些模組設定對應至Pushover Web服務API檔案。 其他Web服務的設定可能不同。 例如，API權杖可以插入到Header而不是Body欄位。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> URL</td> 
      <td> <p><code>https://api.pushover.net/1/messages.json</code> </p> <p>URL欄位包含您可以在網站服務的API檔案中找到的端點。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> 方法</td> 
      <td> <p><code>POST</code> </p> <p>使用的方法取決於對應的端點。 用於推送訊息的Pushover端點使用POST方法。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> 標頭</p> </td> 
      <td> <p>某些網站服務可能會使用標頭來指定API權杖驗證或其他引數。 在我們的範例中，情況並非如此，因為推播訊息的Pushover端點會針對所有請求型別使用Body （請參閱下文）。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> 查詢字串</p> </td> 
      <td> <p>某些Web服務可能會使用查詢字串來指定其他引數。 在我們的範例中，情況並非如此，因為Pushover Web服務對所有請求型別都使用Body （請參閱下文）。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> 內文型別</p> </td> 
      <td> <p><code>Raw</code> </p> <p>此設定可讓您在下方的「內容型別」欄位中選取JSON內容型別。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> 內容類型</p> </td> 
      <td> <p><code>JSON (application/json)</code> </p> <p>JSON是Pushover應用程式所需的內容型別。 這可能與其他網站服務不同。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p> 要求內容</p> </td> 
      <td> <p>以JSON格式輸入Body要求內容。 您可以使用JSON &gt;建立JSON模組，如本文中<a href="#map-the-json-body-using-the-json--create-json-module" class="MCXref xref">使用JSON &gt;建立JSON模組</a>對應JSON內文所述。 或者，您可以手動輸入JSON內容，如<a href="#enter-the-json-body-manually" class="MCXref xref">在本文章中手動輸入JSON內文</a>中所述。</p> <p>請參閱網站服務的API檔案，瞭解該Web服務所需的引數。</p> </td>

   </tr> 
    </tbody> 
   </table>

## 手動輸入JSON內文

以JSON格式指定引數和值。

>[!BEGINSHADEBOX]

**範例：**

```
{"user":"12345c2ecu1hq42ypqzhswbyam34",
"token":"123459evz8aepwtxydndydgyumbfx",
"message":"Hello World!",
"title":"The Push Notification"}
```

>[!ENDSHADEBOX]

此範例包含下列資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p> 使用者</p> </td> 
   <td> <p>您的使用者金鑰。 這可在您的Pushover儀表板中找到。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> token </td> 
   <td> <p>您建立的Pushover應用程式是由您產生的API Token/API金鑰。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> 訊息 </td> 
   <td> <p>傳送至裝置的推播通知文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> 標題 </td> 
   <td> <p>（選用）您的訊息標題。 如果未輸入值，則會使用您的應用程式名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用「JSON >建立JSON模組」對應JSON內文

建立JSON模組使得指定JSON更容易。 它也能讓您以動態方式定義值。

如需JSON模組的詳細資訊，請參閱[JSON模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/json-modules.md)。

1. 輸入或對應您要建立JSON的值。

   ![JSON值](/help/workfront-fusion/create-scenarios/connect-to-apps/assets/json-values-350x288.png)

1. 將JSON >建立JSON模組連線至HTTP >建立請求模組。
1. 將JSON字串從建立JSON模組對應至「HTTP >提出請求」模組中的「請求內容」欄位。

當您執行情境時，推播通知會傳送至已在您的Pushover帳戶中註冊的裝置。

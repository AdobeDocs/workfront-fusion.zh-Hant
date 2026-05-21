---
title: 建立連線
description: 連線必須符合其所連線之應用程式或Web服務的API所設定的需求。 因此，設定連線的指示會因應用程式或Web服務而異。 本文可協助您識別並找出將Adobe Workfront Fusion連線至您所選應用程式或Web服務的指示。
author: Becky
feature: Workfront Fusion
exl-id: 281403a6-6f88-4976-8a10-1d0848ef9b35
TQID: https://experienceleague.adobe.com/qjxlwSzWy6FmnASQrhjVKe8A4VyBpw0aBHkNwgQpo3A
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 24%

---

# 建立連線

連線必須符合其所連線之應用程式或Web服務的API所設定的需求。 因此，設定連線的指示會因應用程式或Web服務而異。 本文可協助您識別並找出將Adobe Workfront Fusion連線至您所選應用程式或Web服務的指示。

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

## 連線到不需要設定的應用程式或Web服務

在大多數情況下，您可以使用模組來建立連線，幾乎沒有或完全沒有額外資訊。 Workfront Fusion會自動處理驗證。

如需建立連線的說明，不需特別考量，請參閱[建立連線 — 基本說明](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)。

## 連線至Adobe應用程式或服務

若要連線至Adobe應用程式或服務，您可能需要來自Adobe Admin Console的資訊，例如您的組織ID或技術帳戶ID。

您也可以使用Adobe Authenticator模組，透過單一連線來連線至任何Adobe API。 這可讓您更輕鬆地連線至尚未具備專用Fusion聯結器的Adobe產品。

如需具體說明，請參閱聯結器的[文章](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-adobe-products)。

## 連線至[!DNL Microsoft]應用程式或Web服務

Workfront Fusion中的大部分[!DNL Microsoft]應用程式都可讓您建立連線，而不需要額外的資訊。

下列情況需要建立連線的額外步驟：

* 使用Microsoft Dynamics 365模組。

  如需指示，請參閱[Microsoft Dynamics 365模組](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/microsoft-dynamics-365-modules.md)。

* 使用HTTP模組連線至Microsoft Graph API

  如需指示，請參閱[呼叫MS Graph REST API](/help/workfront-fusion/create-scenarios/connect-to-apps/call-the-ms-graph-rest-api.md)。

## 連線至[!DNL Google]應用程式或Web服務

連線至[!DNL Google]應用程式的程式可能會因您使用的[!DNL Google]帳戶型別而有所不同。 此外，當您連線到Workfront Fusion時，[!DNL Google]安全性措施可能需要額外的設定。

如需詳細資訊，請參閱：

* [使用自訂 OAuth 用戶端將 Adobe Workfront Fusion 連接至 Google Services](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)
* [使用更新後的安全性措施將 Adobe Workfront Fusion 連接至 Google Services](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-google-with-new-security-measures.md)

## 需要其他設定的其他應用程式

部分應用程式和服務未遵循Workfront Fusion連線的基本設定。 您可以在文章中找到針對該應用程式連線這些應用程式的指示。

如需具體說明，請參閱聯結器的[文章](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#connectors-for-third-party-applications)。

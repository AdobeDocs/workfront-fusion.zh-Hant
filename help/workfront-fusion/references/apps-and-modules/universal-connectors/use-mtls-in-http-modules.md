---
title: 在Adobe Workfront Fusion的HTTP模組中使用雙向TLS
description: 您可以在Adobe Workfront Fusion HTTP模組中使用Mutual TLS，讓資訊交易的兩端都能驗證對方的身分。
author: Becky
feature: Workfront Fusion
exl-id: 1e0b4c3b-9a0b-491d-aaf2-0011d8386abe
source-git-commit: 54c368d335b30f55cab19595a5b4740dde6013a7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 0%

---

# 在Adobe Workfront Fusion的HTTP模組中使用雙向TLS

## 雙向TLS總覽

透過網際網路傳送資料時，請務必確保資料到達或來自正確位置，而且只有預期的收件者才能讀取。 啟用TLS後，使用者端（要求資訊的電腦）會使用憑證來驗證伺服器的身分（提供資訊的電腦）。 如此可建立安全的HTTP連線。

雙向TLS可讓此身分確認雙向進行。 當伺服器傳送其憑證以驗證其身分給使用者端時，也會要求使用者端的憑證。 這可確保伺服器不會將資訊傳送給可能會誤用的網站或使用者。

>[!INFO]
>
>**範例：**
>
>* **TLS**：當使用者在瀏覽器中輸入「MyGreatBank.com」時，他們想要確定自己會前往「我的偉大銀行」，而不是可能會濫用或銷售其銀行資訊的網站。 他們還想確認自己的銀行帳戶資訊已加密。
>
>   當瀏覽器（使用者端）連線至MyGreatBank.com （伺服器）時，TLS需要MyGreatBank.com的憑證才能驗證其身分。 憑證是由憑證授權單位所提供，例如[!DNL DigiCert]或[!DNL Thawte]。 因為瀏覽器信任憑證授權單位，所以允許連線。
>
>* **雙向TLS**： MySoftware.com是需要來自MyGreatBank.com API的資訊的軟體使用者端。 MyGreatBank只允許受信任的使用者端連線到其伺服器。 因此，除了驗證MyGreatBank.com身分的常規TLS之外，TLS/憑證授權程式也會驗證MySoftware.com的要求。

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
   <td role="rowheader">Adobe Workfront Fusion授權</td> 
   <td>
   <p>作業型：無Workfront Fusion授權需求</p>
   <p>以聯結器為基礎（舊版）：用於工作自動化和整合的Workfront Fusion </p>
   </td> 
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

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 提供您的Workfront Fusion公開憑證

當您使用HTTP要求連線至Web服務時，Web服務通常需要Workfront Fusion公開憑證才能驗證。 這可讓Web服務比較HTTP要求中顯示的憑證與檔案上的憑證，藉此確保憑證位於Web服務的允許清單上。

如需將Adobe Workfront Fusion公開憑證上傳至Web服務的指示，請參閱Web服務的檔案。

>[!NOTE]
>
>除了憑證外，您可能需要提供其他資訊。 如需網站服務需求的資訊，請參閱網站服務的API檔案。

您可以使用以下連結下載Workfront Fusion公開憑證。 若要尋找您的資料中心，請參閱貴組織允許清單中「設定Fusion的IP位址」一文中的[識別您的資料中心](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)。

### 2025年憑證

>[!IMPORTANT]
>
>* 這些Workfront Fusion公開憑證將於&#x200B;**2026年4月4日** （美國和EU）或&#x200B;**2025年11月25日** (Azure)到期。 您的憑證過期後，您需要將新的憑證上傳到Web服務。 建議您：
>
>   * 記下到期日，並設定提醒給自己，以便上傳憑證至您的Web服務。
>   * 將此頁面加入書籤，即可輕鬆尋找新憑證。
>
>* 這些是非萬用字元mTLS憑證。

| 資料中心 | 下載連 | 有效日期 |
|---|---|---|
| 美國資料中心 | [下載Workfront Fusion US Certificate 2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-us-mtls-certificate.pem) | 2025年3月3日至2026年4月4日 |
| 歐盟資料中心 | [下載Workfront Fusion EU憑證2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-eu-mtls-certificate.pem) | 2025年3月3日至2026年4月4日 |
| Azure叢集 | [下載Workfront Fusion Azure憑證2025](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/2025-certs/fusion-prod-az-mtls-certificate.pem) | 2024年10月24日至2025年11月25日 |

<!--

### Certificates for 2024

>[!IMPORTANT]
>
>* We recommend installing the certificates for 2025, available above.
>* These Workfront Fusion public certificates expire on **May 7, 2025**. After yours expires you will need to upload a new certificate to the web service. We recommend that you:
>
>   * Make note of the expiration date and set a reminder for yourself to upload the certificate to your web service.
>   * Bookmark this page to easily find the new certificates.
>
>* These are non-wildcard mTLS certificates.

| Datacenter | Download link | Dates valid |
|---|---|---|
| US Datacenter | [Download Workfront Fusion Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-us-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |
| EU Datacenter | [Download Workfront Fusion EU Certificate 2024](/help/workfront-fusion/references/apps-and-modules/universal-connectors/assets/fusion-prod-eu-mtls-certificate.pem) | April 5, 2024 to May 7, 2025 |

-->

## 在Workfront Fusion HTTP模組中啟用雙向TLS

所有Workfront Fusion [!UICONTROL HTTP]要求模組都可選擇啟用雙向TLS。

若要在[!UICONTROL HTTP]要求模組中啟用雙向TLS：

1. 將[!UICONTROL HTTP]要求模組新增至您的情境。
1. 開始設定模組。

   如需設定[!UICONTROL HTTP]要求模組的說明，請參閱[通用聯結器](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)下的適當文章。

1. 啟用&#x200B;**[!UICONTROL 在模組底部附近顯示進階設定]**。
1. 啟用&#x200B;**[!UICONTROL 使用雙向TLS]**。

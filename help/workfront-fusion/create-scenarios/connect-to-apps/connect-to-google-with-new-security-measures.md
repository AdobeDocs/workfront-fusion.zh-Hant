---
title: 使用更新的安全性措施將Adobe Workfront Fusion連線至Google服務
description: Google已引進對使用者如何使用其API的限制。 本文會說明如何將Adobe Workfront Fusion連線至Google，並說明這些更新安全性措施。
author: Becky
feature: Workfront Fusion
exl-id: eac7ba26-664e-464c-b05c-8c2ebf407fb3
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# 使用更新的安全性措施將Adobe Workfront Fusion連線至Google服務

Google已引進對使用者如何使用其API的限制。 本文會說明如何將Adobe Workfront Fusion連線至Google，並說明這些更新安全性措施。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件 
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
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront計畫：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## Google服務限制

Google自2020年6月1日起對使用者使用其API的方式加以限制。 這些安全性措施可保護Google使用者，避免在Google上洩漏或濫用其個人資料。

這些限制與Gmail和Google Drive應用程式有關。

如需這些限制的詳細資訊，請參閱[Google API服務使用者資料原則](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes)中的「特定API範圍的其他需求」

若要存取受限範圍，連線的服務(Adobe Workfront Fusion或透過API存取使用者資料的任何其他服務)必須經過驗證，並且必須具備評估函，以證明服務在使用資料方面的安全性與透明度。 Workfront Fusion符合Google對於存取受限制範圍的所有要求。 不過，Workfront Fusion中大部分的協力廠商連線服務都沒有評估單，因此不符合Google條款。 因此，Workfront Fusion不得將資料傳送至這些服務。

## Google服務限制的例外

有一些例外情況可能會將資料傳送至未核准的第三方服務，該服務沒有評定函，但不會違反任何新限制。 這些差異主要在於Google Workspace與Workfront Fusion OAuth使用者端、Google Workspace與其他OAuth使用者端，或@gmail.com和@googlemail.com。

* [Google Workspace與Workfront Fusion OAuth使用者端](#google-workspace-with-workfront-fusion-oauth-client)
* [Google Workspace與其他OAuth使用者端](#google-workspace-with-another-oauth-client)
* [@gmail.com和@googlemail.com](#gmailcom-and-googlemailcom)

### Google Workspace與Workfront Fusion OAuth使用者端

Workfront Fusion使用全網域安裝例外狀況。 全網域安裝適用於Google Workspace使用者，可讓使用者整合未核准的服務，沒有任何限制。 如果您是Google Workspace使用者，不必執行任何其他步驟，可以直接連線至未核准的服務。

### Google Workspace與其他OAuth使用者端

偏好使用自己OAuth使用者端而非Workfront Fusion OAuth使用者端的Google Workspace使用者，可透過內部使用方法連線至Google服務。 此選項適用於進階使用者。 如需指示，請參閱[使用自訂OAuth使用者端將Adobe Workfront Fusion連線至Google Services](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)。

### @gmail.com和@googlemail.com {#gmailcom-and-googlemailcom}

透過@gmail.com或@googlemail.com存取Google服務的使用者，可透過「個人使用」方法連線至Google服務。 此選項適用於進階使用者。 如需指示，請參閱[使用自訂OAuth使用者端將Adobe Workfront Fusion連線至Google Services](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)。

## 常見問題集

* [Adobe Workfront Fusion中的哪些應用程式會受到影響？](#what-apps-in-adobe-workfront-fusion-are-affected)
* [我有Google Workspace帳戶嗎？](#do-i-have-a-g-suite-account)
* [如果我是@gmail.com或@googlemail.com使用者，怎麼辦？](#what-should-i-do-if-im-gmailcom-or-googlemailcom-user)
* [如果我是Google Workspace使用者，怎麼辦？](#what-should-i-do-if-im-a-g-suite-user)

### Adobe Workfront Fusion中的哪些應用程式會受到影響？ {#what-apps-in-adobe-workfront-fusion-are-affected}

Google Drive、Gmail和電子郵件（已連線至Gmail帳戶）。

### 我有Google Workspace帳戶嗎？ {#do-i-have-a-g-suite-account}

如果您的電子郵件地址結尾為@gmail.com或@googlemail.com，則您的帳戶不是Google Workspace帳戶。 如果您的Google帳戶以自訂網域(例如@my-company.com)結尾，則它是Google Workspace帳戶。

### 如果我是@gmail.com或@googlemail.com使用者，怎麼辦？ {#what-should-i-do-if-im-gmailcom-or-googlemailcom-user}

這些新限制僅適用於整合Google Drive或Gmail時。 如果您想要連線至Google Drive或Gmail，您可以

* 切換至Google Workspace

  或

* 建立自訂OAuth使用者端。 此選項適用於進階使用者。

  如需指示，請參閱[使用自訂OAuth使用者端將Adobe Workfront Fusion連線至Google Services](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-fusion-to-google-using-oauth.md)。

如果您想要整合Google Drive或Gmail以外的任何其他服務，則這些限制不適用。

### 如果我是Google Workspace使用者，怎麼辦？ {#what-should-i-do-if-im-a-g-suite-user}

沒有必要的動作。

---
title: Microsoft SQL Server模組
description: 您可以使用 [!DNL Adobe Workfront Fusion] 連線至Microsoft SQL Server。
author: Becky
feature: Workfront Fusion
exl-id: 8f3293f7-8b45-4e42-8ad8-f9d4969b63fd
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# [!DNL Microsoft SQL Server]模組

您可以使用[!DNL Adobe Workfront Fusion]連線至[!UICONTROL Microsoft SQL Server]。

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
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 正在將[!DNL Microsoft SQL Server]服務連線到[!DNL Workfront Fusion]

如需有關將您的[!DNL Microsoft SQL Server]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) — 基本指示

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## 使用[!DNL Microsoft SQL Server]模組

您可以透過預存程式，直接在資料庫伺服器上執行自訂邏輯。 [!DNL Adobe Workfront Fusion]會動態載入輸入/輸出引數及記錄集的介面，以便每個引數或值都可以個別對應。 開始設定案例之前，請確定您用來連線至資料庫的帳戶具有`INFORMATION_SCHEMA.ROUTINES`和`INFORMATION_SCHEMA.PARAMETERS`檢視的讀取存取權。

當[!DNL Fusion]建立與[!DNL SQL server]目的地的連線時，[!DNL Fusion]使用者會識別主機（裝載伺服器的網域名稱或IP位址）和連線埠。 [!DNL Fusion]可以連線到任何可用的主機和連線埠。

如需[!DNL Workfront Fusion]使用的特定IP位址的詳細資訊，請參閱[用於存取的IP位址 [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)

若要深入瞭解如何建立預存程式，請參閱[!DNL Microsoft SQL Server]檔案。

>[!NOTE]
>
>[!DNL Workfront Fusion]不支援多個記錄集。 系統只會處理第一個專案。

## 疑難排解錯誤[!UICONTROL ER_LOCK_WAIT_TIMEOUT：超過鎖定等待逾時；請嘗試重新啟動交易]

使用多個模組修改相同資料時，會發生此錯誤。 這是由SQL交易所造成。

執行任何SQL模組時，它會啟動交易。 交易在案例完全執行後完成。

如果另一個模組嘗試存取相同的資料，則必須等到前一個交易完成。 由於第一個交易將在案例完成後完成，因此第二個交易永遠無法開始。

### 解決方案：

開啟自動提交。 自動認可會在模組執行完成後立即完成（認可）每個交易。

1. 按一下畫面底部的[!UICONTROL 案例設定]圖示![案例設定圖示](/help/workfront-fusion/references/apps-and-modules/assets/scenario-settings-icon.png)。
1. 按一下&#x200B;**[!UICONTROL 自動認可]**&#x200B;核取方塊。
1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;以儲存情境設定。

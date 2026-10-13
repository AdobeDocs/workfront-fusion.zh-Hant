---
title: SharePoint模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Microsoft SharePoint Online的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
TQID: 'https://experienceleague.adobe.com/WmECfdPt-a3l2-WT9LMX2HB-7-p-BLIO4F2i3OAc7D0'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
    internal-label: APIs
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: c9bf5c68e4977027944114c35414fa5f46ea8751
workflow-type: tm+mt
source-wordcount: '5853'
ht-degree: 10%
---
# Microsoft SharePoint Online 模組

在Adobe Workfront Fusion案例中，您可以自動化使用Microsoft SharePoint Online的工作流程，並將其連結至多個協力廠商應用程式和服務。

關於建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)之下的文章。

關於模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)之下的文章。

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用Microsoft SharePoint Online模組，您必須擁有Microsoft SharePoint Online帳戶。

## SharePoint API資訊

SharePoint聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 版本</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.14.2</td> 
  </tr>
 </tbody> 
 </table>

## 將Microsoft SharePoint Online連線至Workfront Fusion {#connect-microsoft-sharepoint-online-to-workfront-fusion}

* [使用 [!DNL Microsoft] 帳戶將Microsoft SharePoint Online連線至Workfront Fusion](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-microsoft-account)
* [使用進階設定將Microsoft SharePoint Online連線至Workfront Fusion](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-advanced-settings)
* [使用憑證授權將Microsoft SharePoint Online連線至Workfront Fusion](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-certificate-authorization)
* [使用服務主體將Microsoft SharePoint Online連線至Workfront Fusion](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-service-principal)

### 使用[!DNL Microsoft]帳戶將Microsoft SharePoint Online連線至Workfront Fusion

+++ 展開以檢視使用Microsoft帳戶將Microsoft SharePoint Online連線至Workfront Fusion的說明。

您可以使用您的[!DNL Microsoft]帳戶建立與Microsoft SharePoint Online的連線。 如需有關將您的[!DNL Sharepoint]帳戶連線到Workfront Fusion的說明，請參閱[建立與Adobe Workfront Fusion的連線 — 基本說明](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)。

+++

### 使用進階設定將Microsoft SharePoint Online連線至Workfront Fusion

+++ 展開以檢視使用進階設定將Microsoft SharePoint Online連線至Workfront Fusion的說明。

若要在連線中包含認證，請啟用「顯示進階設定」選項。 對於這類連線，您需要使用者端ID、使用者端密碼和租使用者ID。

1. 在任何SharePoint模組中，按一下[連線]欄位附近的&#x200B;**[!UICONTROL [新增]**]以開啟&#x200B;**[!UICONTROL [建立連線]**]方塊。
1. 按一下&#x200B;**[!UICONTROL 顯示進階設定]**。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線類型]</p> </td> 
      <td>若要使用使用者端認證，請選取<b>Microsoft 365電子郵件</b>。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線名稱]</p> </td> 
      <td>輸入此連線的名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 用戶端 ID]</p> </td> 
      <td>輸入您要連線之SharePoint應用程式的使用者端ID。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL使用者端密碼]</p> </td> 
      <td>輸入您要連線之SharePoint應用程式的使用者端密碼。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL租使用者ID]</p> </td> 
      <td>輸入您要連線之SharePoint應用程式的租使用者ID。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**繼續**」，儲存連線並返回模組。

+++

### 使用憑證授權將Microsoft SharePoint Online連線至Workfront Fusion

+++ 展開以檢視使用憑證授權將Microsoft SharePoint Online連線至Workfront Fusion的說明。

您可以使用憑證授權來連線至SharePoint。

>[!IMPORTANT]
>
>若要使用憑證授權，您必須先在Microsoft Entra中建立應用程式，然後上傳憑證。
>
>如需指示，請參閱Microsoft檔案中的[如何設定Microsoft Entra憑證式驗證的憑證授權單位](https://learn.microsoft.com/en-us/entra/identity/authentication/how-to-configure-certificate-authorities)。

1. 在任何SharePoint模組中，按一下[連線]欄位附近的&#x200B;**[!UICONTROL [新增]**]以開啟&#x200B;**[!UICONTROL [建立連線]**]方塊。
1. 按一下&#x200B;**[!UICONTROL 顯示進階設定]**。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線類型]</p> </td> 
      <td>若要使用憑證授權，請選取<b>Microsoft SharePoint Online （憑證驗證）</b>。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線名稱]</p> </td> 
      <td>輸入此連線的名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 用戶端 ID]</p> </td> 
      <td>輸入您要連線之SharePoint應用程式的使用者端ID。 </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL指紋]</p> </td> 
      <td>輸入您要連線的SharePoint應用程式指紋。</td> 
     </tr> 
      <tr>
        <td role="rowheader">[!UICONTROL 私密金鑰]</td>
        <td>
          <p>輸入在Microsoft中建立憑證時產生的憑證或私密金鑰。 </p>
          <p>若要擷取您的私密金鑰或憑證：</p>
          <ol>
            <li>
              <p>按一下「<b>[!UICONTROL 擷取]</b>」。</p>
            </li>
            <li>
            <p>選取您要擷取憑證或私密金鑰。</li>
            <li>
              <p>選取要擷取的檔案類型。</p>
            </li>
            <li>
              <p>選取包含私密金鑰或憑證的檔案。</p>
            </li>
            <li>
              <p>輸入檔案的密碼。</p>
            </li>
            <li>
              <p>按一下「<b>[!UICONTROL 儲存]</b>」，擷取檔案並返回連線設定。</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody> 
   </table>

1. 按一下「**繼續**」，儲存連線並返回模組。

+++

### 使用服務主體將Microsoft SharePoint Online連線至Workfront Fusion

+++ 展開以檢視使用服務主體將Microsoft SharePoint Online連線至Workfront Fusion的說明。

您可以建立使用服務主體（應用程式API連線）而不是個人帳戶的連線。 如果您希望連線以應用程式或服務身分執行，而非以特定人員執行（例如，如果該人員離開公司或變更其密碼，整合不會中斷），則此功能會很有用。

>[!IMPORTANT]
>
>此連線型別僅適用於[進行API呼叫](#make-an-api-call)模組。 其他SharePoint模組需要本文所述的其他連線型別之一。

* [使用服務主體將Microsoft SharePoint Online連線到Workfront Fusion的先決條件](#prerequisites-to-connecting-microsoft-sharepoint-online-to-workfront-fusion-using-a-service-principal)
* [在Microsoft Entra ID中建立應用程式註冊](#create-the-app-registration-in-microsoft-entra-id)
* [建立使用者端密碼](#create-a-client-secret)
* [授予API許可權](#grant-api-permissions)
* [收集您的連線詳細資料](#collect-your-connection-details)
* [建立連線](#create-the-connection)

#### 使用服務主體將Microsoft SharePoint Online連線到Workfront Fusion的先決條件

您需要Microsoft Entra ID中的&#x200B;**全域管理員**、**應用程式管理員**&#x200B;或&#x200B;**有特殊許可權的角色管理員**&#x200B;存取權，才能註冊應用程式並授予其許可權。 如果您沒有此存取權，請要求您IT或身分團隊中的某人為您完成這些步驟。

繼續[在Microsoft Entra ID](#create-the-app-registration-in-microsoft-entra-id)中建立應用程式註冊。

#### 在Microsoft Entra ID （服務主體）中建立應用程式註冊

1. 登入[!DNL Microsoft Entra]系統管理中心。
1. 移至&#x200B;**[!UICONTROL 應用程式註冊]** > **[!UICONTROL 新註冊]**。
1. 為應用程式提供一個清晰且可辨識的名稱。 例如 `Make - SharePoint Integration`。
1. 將&#x200B;**[!UICONTROL 重新導向URI]**&#x200B;保留空白。 此連線不涉及任何人透過瀏覽器登入。
1. 選取&#x200B;**[!UICONTROL 註冊]**。
1. 繼續[建立使用者端密碼](#create-a-client-secret)。

#### 建立使用者端密碼（服務主體）

1. 在您的新應用程式註冊中，移至&#x200B;**[!UICONTROL 憑證與密碼]**。
1. 選取&#x200B;**[!UICONTROL 新增使用者端密碼]**、新增說明，並選擇到期期間。
1. 選取&#x200B;**[!UICONTROL 新增]**。
1. 立即複製密碼的&#x200B;**[!UICONTROL 值]**。 它只會顯示一次。 如果您在複製它之前瀏覽離開，則必須建立一個新的專案。
1. 繼續[授予API許可權](#grant-api-permissions)。

#### 授予API許可權（服務主體）

>[!IMPORTANT]
>
>BECKY CHECK ME：不同於Azure DevOps，Microsoft Graph直接在此步驟中支援應用程式許可權。 在發佈此區段之前，請先確認進行API呼叫模組所需的確切許可權（例如網站許可權範圍），並據此更新下列步驟。

1. 在您的應用程式註冊中，移至&#x200B;**[!UICONTROL API許可權]**。
1. 選取&#x200B;**[!UICONTROL 新增許可權]**，然後選取&#x200B;**[!UICONTROL Microsoft圖表]**。
1. 選取&#x200B;**[!UICONTROL 應用程式許可權]**。
1. 選取API呼叫所需的許可權或許可權，然後選取&#x200B;**[!UICONTROL 新增許可權]**。
1. 選取&#x200B;**[!UICONTROL 為您的組織]**&#x200B;授予管理員同意，然後確認。
1. 繼續[收集您的連線詳細資料](#collect-your-connection-details)。

#### 收集您的連線詳細資料（服務主體）

從應用程式註冊的&#x200B;**[!UICONTROL 總覽]**&#x200B;頁面，請注意下列值。 在模組中建立連線時，請輸入這些連線。

<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader">[！UICONTROL租使用者ID]</td>
   <td>在概觀頁面上，標示為<b>目錄（租使用者） ID</b>。</td>
  </tr>
  <tr>
   <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
   <td>在概觀頁面上，標示為<b>應用程式（使用者端） ID</b>。</td>
  </tr>
  <tr>
   <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
   <td>您在<a href="#create-a-client-secret" class="MCXref xref">中複製的值建立使用者端密碼</a>。</td>
  </tr>
 </tbody>
</table>

繼續[建立連線](#create-the-connection)。

#### 建立連線（服務主體）

1. 在[!UICONTROL 進行API呼叫]模組中，按一下[連線]欄位附近的&#x200B;**[!UICONTROL 新增]**&#x200B;以開啟&#x200B;**[!UICONTROL 建立連線]**&#x200B;方塊。
1. 按一下&#x200B;**[!UICONTROL 顯示進階設定]**。
1. 在[!UICONTROL 連線型別]欄位中，選取&#x200B;**[!UICONTROL 服務主體]**。
1. 輸入下列：

   * [!UICONTROL 租使用者識別碼]
   * [!UICONTROL 使用者端識別碼]
   * [!UICONTROL 使用者端密碼]

1. 按一下「**繼續**」，儲存連線並返回模組。

   如果一切設定正確，連線都會成功驗證。

+++

### 使用同盟連線將Microsoft SharePoint Online連線至Adobe Workfront Fusion

+++ 展開以檢視使用同盟連線將Microsoft SharePoint Online連線至Adobe Workfront Fusion的說明。

同盟連線的運作方式與服務主體連線類似，只是它不使用使用者端密碼。
與其儲存秘密，不如告訴Microsoft Entra ID信任Workfront Fusion針對某個特定連線所發行的權杖。 連線執行時，Fusion會提供短暫的身分證明，且Microsoft Entra ID會傳回存取權杖。 因為沒有使用者端密碼，所以沒有到期的專案，也沒有要輪換或儲存的密碼。

>[!NOTE]
>
>設定此連線需要兩次造訪Microsoft Entra管理中心。 您先註冊應用程式，然後在Workfront Fusion中建立連線，然後返回Microsoft Entra ID以新增同盟認證。 這是因為同盟認證會識別一個特定連線，而該識別碼在建立連線之前並不存在。

* [使用同盟連線將Microsoft SharePoint Online連線至Workfront Fusion的必要條件](#prerequisites-to-connecting-microsoft-sharepoint-online-to-workfront-fusion-using-a-federated-connection)
* [在Microsoft Entra ID （同盟連線）中建立應用程式註冊](#create-the-app-registration-in-microsoft-entra-id-federated-connection)
* [授予API許可權（同盟連線）](#grant-api-permissions-federated-connection)
* [收集您的連線詳細資料（同盟連線）](#collect-your-connection-details-federated-connection)
* [在Workfront Fusion （同盟連線）中建立連線](#create-the-connection-in-workfront-fusion-federated-connection)
* [在Microsoft Entra ID （Federated連線）中新增同盟認證](#add-the-federated-credential-in-microsoft-entra-id-federated-connection)
* [驗證連線（同盟連線）](#verify-the-connection-federated-connection)
* [疑難排解](#troubleshooting)

#### 使用同盟連線將Microsoft SharePoint Online連線至Workfront Fusion的必要條件

您需要Microsoft Entra ID中的全域管理員、應用程式管理員或特殊許可權角色管理員存取權，才能註冊應用程式、授予其許可權並新增同盟認證。 如果您沒有此存取權，請要求您IT或身分團隊中的某人為您完成這些步驟。

#### 在Microsoft Entra ID （同盟連線）中建立應用程式註冊

1. 登入Microsoft Entra管理中心。
1. 前往「應用程式註冊>新註冊」。
1. 為應用程式提供一個清晰且可辨識的名稱。 例如 `Workfront Fusion SharePoint Integration`。
1. 將重新導向URI保留空白。 此連線不涉及任何人透過瀏覽器登入。
1. 選取&#x200B;**註冊**。
請勿建立使用者端密碼。 同盟連線不使用。
1. 繼續授予API許可權。


#### 授予API許可權（同盟連線）

1. 在您的應用程式註冊中，移至&#x200B;**API許可權**。
1. 選取&#x200B;**新增許可權**，然後選取&#x200B;**Microsoft圖表**。
1. 選取&#x200B;**應用程式許可權**。
1. 選取API呼叫所需的許可權或許可權，然後選取&#x200B;**新增許可權**。
1. 選取&#x200B;**為您的組織授予管理員同意**，然後確認。
1. 繼續[收集您的連線詳細資料](#collect-your-connection-details-federated-connection)。


#### 收集您的連線詳細資料（同盟連線）

1. 從應用程式註冊的「概觀」頁面，請注意下列值。 在模組中建立連線時，請輸入這些連線。

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[！UICONTROL租使用者ID]</td>
      <td>在概觀頁面上，標示為<b>目錄（租使用者） ID</b>。</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
      <td>在概觀頁面上，標示為<b>應用程式（使用者端） ID</b>。</td>
     </tr>
    </tbody>
   </table>

1. 繼續[在Workfront Fusion](#create-the-connection-in-workfront-fusion-federated-connection)中建立連線。

#### 在Workfront Fusion （同盟連線）中建立連線

1. 在「進行API呼叫」模組中，按一下「連線」欄位附近的b ，以開啟「建立連線」方塊。
1. 按一下（同盟連線）。
1. 在連線型別欄位中，選取同盟連線型別。
1. 輸入下列：

   * 租使用者ID
   * 用戶端 ID

1. 選取「**建立**」。
Workfront Fusion會顯示三個值。 您可以在下一個程式中使用它們。

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[！UICONTROL Issuer]</td>
      <td>一律為<code>https://oidc.automations.adobe.com</code>。</td>
     </tr>
     <tr>
      <td role="rowheader">[！UICONTROL主旨]</td>
      <td>識別這個連線。 它看起來像<code>fusion:6e5b1c2a345bd8d1ed98b6b4f1459818:28964</code>。 您建立的每個連線都不同。</td>
     </tr>
     <tr>
      <td role="rowheader">[！UICONTROL對象]</td>
      <td>一律為<code>api://AzureADTokenExchange</code>。</td>
     </tr>
    </tbody>
   </table>


1. 讓此面板保持開啟狀態，並複製&#x200B;**主旨**&#x200B;值。

   >[!NOTE]
   >
   >請勿關閉面板或選取「取消」。 連線要等到您完成其餘程式後才會完成。 如果關閉面板，您必須刪除連線並重新開始，因為新的連線會收到新的主旨。


1. 繼續[在Microsoft Entra ID](#add-the-federated-credential-in-microsoft-entra-id-federated-connection)中新增Federated認證。

#### 在Microsoft Entra ID （Federated連線）中新增同盟認證

此程式會取代使用者端密碼。 它會通知Microsoft Entra ID接受Workfront Fusion針對這個連線所發行的代號。

1. 在新的瀏覽器標籤中，返回Microsoft Entra管理中心並開啟您的應用程式註冊。
1. 移至&#x200B;**憑證與密碼** > **同盟認證**。
1. 選取&#x200B;**新增認證**。
1. 在Federated認證案例中，選取&#x200B;**其他簽發者**。
1. 輸入下列：

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
     <tr>
      <td role="rowheader">[！UICONTROL Issuer]</td>
      <td><code>https://oidc.automations.adobe.com</code>.</td>
     </tr>
     <tr>
      <td role="rowheader">[！UICONTROL主體識別碼]</td>
      <td>您從Workfront Fusion複製的主體。 完全貼上，不新增空格。</td>
     </tr>
     <tr>
      <td role="rowheader">[!UICONTROL 名稱]</td>
      <td>可識別此連線的名稱，以便您稍後尋找。 例如 <code>workfront-fusion-connection-28964</code>。</td>
     </tr>
     <tr>
      <td role="rowheader">[！UICONTROL對象]</td>
      <td><code>api://AzureADTokenExchange</code>. 這通常會為您填入。 保留預設值。</td>
     </tr>
    </tbody>
   </table>

1. 選取&#x200B;**新增**。
1. 繼續[驗證連線](#verify-the-connection-federated-connection)。


#### 驗證連線（同盟連線）

1. 返回Workfront Fusion瀏覽器索引標籤，其中連線面板仍處於開啟狀態。
2. 選取&#x200B;**「儲存」**。

   * 如果所有專案皆已正確設定，連線將會成功驗證，您可以繼續設定模組。
   * 如果驗證失敗，面板會保持開啟並顯示錯誤。 請更正Microsoft Entra ID中的問題，然後再次選取「儲存」。 您不需要重新建立連線，而且主旨不會變更。


#### 疑難排解


<table style="table-layout:auto">
 <col>
 <col>
 <tbody>
  <tr>
   <td role="rowheader">連線驗證失敗，發生無效的使用者端或無效的請求錯誤</td>
   <td>Microsoft Entra ID無法比對權杖與同盟認證。 檢查簽發者是否剛好是<code>https://oidc.automations.adobe.com</code>，沒有結尾斜線，而且主旨識別碼與Workfront Fusion中顯示的主旨完全相同（字元對字元）。 從不同連線複製的主體是最常見的原因。</td>
  </tr>
  <tr>
   <td role="rowheader">連線會驗證，但API呼叫會傳回403</td>
   <td>身分值得信任，但應用程式沒有您呼叫所需的Microsoft Graph許可權。 返回授予API許可權、新增所需的應用程式許可權並授予管理員同意。</td>
  </tr>
  <tr>
   <td role="rowheader">您無法新增其他同盟認證</td>
   <td>您已達到該應用程式註冊的20個同盟認證限制。 註冊其他應用程式並針對其建立進一步的連線。</td>
  </tr>
 </tbody>
</table>

+++

## Microsoft SharePoint模組及其欄位

當您設定Microsoft SharePoint Online模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Microsoft SharePoint Online欄位，視您應用程式或服務中的存取層級等因素而定。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [磁碟機專案](#drive-item)
* [項目](#item)
* [清單](#list)
* [頁面(Beta)](#page-beta)
* [網站](#site)
* [其他](#other)

### 磁碟機專案

* [建立檔案](#create-a-file)
* [建立檔案（舊版）](#create-a-file-legacy)
* [建立資料夾](#create-a-folder)
* [取得檔案](#get-a-file)
* [取得資料夾](#get-a-folder)
* [更新資料夾或檔案](#update-a-folder-or-a-file)
* [監視資料夾專案](#watch-folder-items)

#### 建立檔案

此模組會傳回在SharePoint中建立檔案。 此模組的效能優於建立檔案（舊版）模組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別要擷取變更的資料夾位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立檔案之位置的<strong>[！UICONTROL站台識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要建立檔案的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案] </td>
      <td><p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p></td>
  </tr>  </tbody> 
</table>



#### 建立檔案（舊版）

此模組會在SharePoint中建立檔案。

為獲得更好的效能，建議您使用[建立檔案](#create-a-file)模組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別要擷取變更的資料夾位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立檔案之位置的<strong>[！UICONTROL站台識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要建立檔案的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
      <td><p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p></td>
  </tr>  </tbody> 
</table>

#### 建立資料夾

此動作模組會在SharePoint中建立新資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取要如何識別要建立的資料夾位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立資料夾位置的<strong>[！UICONTROL站台識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要建立資料夾的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾名稱]</td> 
   <td>輸入或對應新資料夾的名稱。</td> 
  </tr>
  </tbody> 
</table>

#### 取得檔案

此動作模組會擷取指定的SharePoint檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別要取得之檔案的位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要擷取的檔案，輸入或對應<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL檔案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取檔案的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### 取得資料夾

此模組已擷取有關指定資料夾的詳細資料

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和檔案ID]</td> 
   <td> <p>選取您要如何識別要取得之檔案的位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要擷取的資料夾，輸入或對映<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL資料夾路徑]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取資料夾的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### 更新資料夾或檔案

此動作模組會更新資料夾或檔案的中繼資料

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和檔案ID]</td> 
   <td> <p>選取您要如何識別要取得之檔案的位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要擷取的資料夾或檔案，輸入或對應<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL資料夾或專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取資料夾的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
  </tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td>針對您要更新的每個中繼資料欄位，按一下<b>新增專案</b>並輸入欄位的路徑和值。</td> 
  <tr>
</tbody> 
</table>

#### 監視資料夾專案

當您選取的資料夾中有專案更新時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別要取得之檔案的位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在出現的欄位中輸入或對映<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取要監視的資料夾位置。 </p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入Workfront Fusion應在一個情境執行週期中傳回的最大專案數。</td> 
  <tr>
  </tr>
</tbody> 
</table>

### 項目

* [[!UICONTROL 複製專案]](#copy-an-item)
* [[!UICONTROL 建立專案]](#create-an-item)
* [[!UICONTROL 刪除專案]](#delete-an-item)
* [[!UICONTROL 取得專案]](#get-an-item)
* [取得詳細資料](#get-details)
* [[!UICONTROL 清單專案]](#list-items)
* [[!UICONTROL 移動專案]](#move-an-item)
* [[!UICONTROL 更新專案]](#update-an-item)
* [[!UICONTROL 觀看專案] （已排程）](#watch-items-scheduled)


#### [!UICONTROL 複製專案]

此動作模組會複製SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸入站台、磁碟機和資料夾ID</td> 
   <td> <p>選取您要如何識別包含您要複製之專案的場地和磁碟機。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要複製之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>在「專案型別」欄位中，選取您要移動欄位或資料夾。  選取包含您要複製之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL目的地ID]</td> 
   <td> 輸入或對應您要複製專案的資料夾識別碼。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新名稱]</td> 
   <td>輸入或對應專案新復本的名稱。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立專案]

此動作模組會在SharePoint清單中建立新專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL建立專案]</td> 
   <td> <p>選取您要如何識別網站及要建立專案的磁碟機。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立專案的<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL清單識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要建立專案之清單的網站，然後選取清單。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td>針對您想要為新專案設定的每個欄位，按一下<b>新增專案</b>，然後輸入欄位索引鍵（可識別欄位）以及您想要新專案在該欄位中的值。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除專案]

此動作模組會刪除SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL更新專案]</td> 
   <td> <p>選取您要如何識別網站以及包含您要刪除之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要刪除之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要刪除之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得專案]

此動作模組會傳回指定專案的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得專案]</td> 
   <td> <p>選取您要如何識別網站以及包含您要取得之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要傳回資料之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取專案之清單的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得詳細資料

此模組從指定的URL取得專案詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">網頁URL</td> 
   <td> 輸入或對應您要擷取其詳細資訊之專案的URL。 </td> 
  </tr> 
</tbody> 
</table>

#### [!UICONTROL 清單專案]

此動作模組會擷取指定清單中所有專案的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL清單專案]</td> 
   <td> <p>選取您要如何識別要從中擷取專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要列出專案的清單，輸入或對映<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL清單識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要從中擷取專案的清單的網站，然後選取清單。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大專案數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 移動專案]

此動作模組會複製SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸入站台、磁碟機和資料夾ID</td> 
   <td> <p>選取您要如何識別網站以及包含您要移動之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要移動的專案，輸入或對映<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>在「專案型別」欄位中，選取您要移動欄位或資料夾。 選取包含您要複製之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL目的地ID]</td> 
   <td> 輸入或對應您要移動專案的資料夾識別碼。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新名稱]</td> 
   <td>輸入或對應已移動專案的名稱。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新專案]

此動作模組會更新SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL更新專案]</td> 
   <td> <p>選取您要如何識別包含您要更新之專案的場地與清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要更新之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要更新之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 欄位]</td> 
   <td>針對您想要更新新專案的每個欄位，按一下<b>新增專案</b>，然後輸入欄位索引鍵（可識別欄位）以及您想要專案在該欄位擁有的新值。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看專案] （已排程）

此觸發模組會在建立或修改專案時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL監看清單]</td> 
   <td>選取您要依建立時間（新專案）還是依修改時間（更新專案）來監視清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站和清單ID]</td> 
   <td> <p>選取您要如何識別要觀看的網站和清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要觀看的<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL清單識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要觀看的網站，然後選取清單。 這些下拉式清單只會擷取追蹤的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大專案數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 清單

* [[!UICONTROL 建立清單]](#create-a-list)
* [[!UICONTROL 取得清單]](#get-a-list)
* [[!UICONTROL 清單清單]](#list-lists)
* [[!UICONTROL 觀看清單]](#watch-lists)

#### [!UICONTROL 建立清單]

此動作模組會在SharePoint中建立新清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站ID]</td> 
   <td> <p>選取您要如何識別要建立清單的網站。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立清單的<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取您要建立清單的網站。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL顯示名稱]</td> 
   <td>輸入或對應新清單的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 說明]</td> 
   <td>輸入或對應新清單的說明。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新增欄]</td> 
   <td>針對您想要為新清單設定的每個資料行，按一下<b>新增專案</b>，輸入欄位的<strong>[！UICONTROL名稱]</strong>，然後選取您想要新資料行具有的值<strong>[！UICONTROL型別]</strong>。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得清單]

此動作模組會傳回指定清單的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得清單]</td> 
   <td> <p>選取您要如何識別網站以及包含您要取得之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要傳回的<strong>[！UICONTROL網站識別碼]</strong>與<strong>清單識別碼</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取之清單的網站，然後選取清單。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清單清單]

此動作模組會擷取指定網站中所有專案的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL清單清單]</td> 
   <td> <p>選取您要如何識別要從中擷取清單的網站。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應包含您要傳回清單的<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取之清單的網站。 下拉式清單只會擷取您關注的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大清單數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看清單]

此觸發模組會在建立或修改清單時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL監看清單]</td> 
   <td>選取您要依建立時間（新專案）還是依修改時間（更新專案）來監視清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站ID]</td> 
   <td> <p>選取您要如何識別要監視清單的網站。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您想要監視清單的<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要觀看的網站。 下拉式清單只會擷取您追蹤的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大清單數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 頁面(Beta)

>[!NOTE]
>
>[!DNL Microsoft Graph]中`beta`版本的API可能會變更。 不支援在生產應用程式中使用這些API。

* [取得頁面](#get-a-page)
* [清單頁面](#list-pages)
* [發佈頁面](#publish-a-page)
* [觀看頁面](#watch-pages)

#### [!UICONTROL 取得頁面]

此動作模組會傳回指定頁面的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得頁面]</td> 
   <td> <p>選取您要如何識別要擷取的頁面。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL頁面識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取之頁面的網站，然後選取頁面。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 清單頁面

此模組會擷取所有頁面的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL清單頁面]</td> 
   <td> <p>選取您要如何識別要列出的頁面。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應包含您要列出之頁面的網站<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要列出頁面的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大頁數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 發佈頁面

此動作模組會發佈所選頁面的最新版本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL發佈頁面]</td> 
   <td> <p>選取您要如何識別要發佈的頁面。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL頁面識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要發佈之頁面的網站，然後選取頁面。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看頁面

此觸發模組會在指定網站上修改頁面時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站ID]</td> 
   <td> <p>選取您要如何識別要列出的頁面。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應包含您要觀看之頁面的網站<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取包含您要觀看之頁面的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大頁數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 網站

* [[!UICONTROL 取得網站]](#get-a-site)
* [[!UICONTROL 搜尋網站]](#search-sites)

#### [!UICONTROL 取得網站]

此動作模組會傳回指定網站的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得網站]</td> 
   <td> <p>選取您要如何識別要擷取的頁面。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取您要擷取的網站。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋網站]

此動作模組會依您指定的引數搜尋網站。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">顯示名稱的[！UICONTROL關鍵字]</td> 
   <td> <p>輸入或對應您要搜尋網站的搜尋字詞。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大網站數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [取得變更](#get-changes)
* [進行API呼叫](#make-an-api-call)
* [監視事件](#watch-events)

#### 取得變更

此模組會擷取SharePoint資料夾中的新增、更新和刪除專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別包含您要更新之專案的場地與磁碟機。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在出現的欄位中輸入或對映<strong>[！UICONTROL站台識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含要更新專案的網站，然後選取磁碟機，再選取資料夾。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Token]</td> 
   <td> 代號會識別模組應該從何時開始擷取變更。  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行API呼叫]

您可以透過此模組進行自訂的 API 呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Microsoft SharePoint Online帳戶連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於 <code>https://graph.microsoft.com</code> 的路徑。 範例：<code> /beta/sites</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。 例如 <code>{"Content-type":"application/json"}</code>。 Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p> 以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 類型]</td> 
   <td>選取您要在API呼叫中傳送的資料型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 監視事件

在SharePoint中新增、更新或刪除專案時，此即時觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
  <!--
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Microsoft SharePoint Online account to Workfront Fusion, see <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect Microsoft SharePoint Online to Workfront Fusion</a> in this article.</p> </td> 
  </tr> 
-->
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>選取現有的webhook，或按一下「新增」並輸入連線以建立新的webhook。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

---
title: Jira 模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Jira軟體的工作流程，並將其連線到多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: b74a3618-c4a1-4965-a88d-1643bfab12db
source-git-commit: e65d868dc2165cbe800600f271f6b03d0a906cb4
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 20%

---

# Jira 模組

>[!NOTE]
>
>這些指示適用於新版的Jira聯結器，其標籤只是Jira。 如需有關舊版Jira Cloud和Jira Server聯結器的說明，請參閱[Jira軟體模組](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-software-modules.md)。

在Adobe Workfront Fusion案例中，您可以自動化使用Jira的工作流程，並將其連線到多個第三方應用程式和服務。

Jira聯結器可用於Jira Cloud和Jira Data Server。

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
   <p>作業型：無 Workfront Fusion 授權要求</p>
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

* 若要使用Jira模組，您必須擁有Jira帳戶。
* 您必須有權存取Jira Developer Console，才能在Jira中建立OAuth2應用程式。

## 將Jira連線至Workfront Fusion

建立與Jira的連線的程式會因您是要建立基本連線還是OAuth2連線而有所不同。

* [建立與Jira的OAuth2連線](#create-an-oauth2-connection-to-jira)
* [建立與Jira的基本連線](#create-a-basic-connection-to-jira)

### 建立與Jira的OAuth2連線

若要建立與Jira的OAuth2連線，您必須先在Jira中建立應用程式，才能在Fusion中設定連線。

* [在Jira中建立OAuth2應用程式](#create-an-oauth2-application-in-jira)
* [在Fusion中設定OAuth2連線](#configure-the-oauth2-connection-in-fusion)

#### 在Jira中建立OAuth2應用程式

>[!IMPORTANT]
>
>您必須擁有Jira Developer Console的存取權，才能為Jira連線建立和設定OAuth2應用程式。

1. 移至[Jira Developer Console](https://developer.atlassian.com/console.myapps/)。
1. 在[我的應用程式]區域中，按一下[建立]****，然後選取[OAuth 2.0整合]**。**
1. 輸入整合的名稱，同意開發人員條款，然後按一下[建立]。****

   應用程式隨即建立，您就會進入應用程式設定區域。
1. 按一下左側導覽面板中的&#x200B;**許可權**。
1. 在[許可權]區域中，找到&#x200B;**Jira API**&#x200B;行。
1. 按一下Jira API行中的[新增]****，然後按一下同一行中的[繼續]****。
1. 啟用下列範圍：

   * 檢視Jira問題資料(`read:jira-work`)
   * 檢視使用者設定檔(`read:jira-user`)
   * 建立和管理問題(`write:jira-work`)

1. 在左側導覽中，按一下&#x200B;**授權**。
1. 在OAuth 2.0授權的行中按一下&#x200B;**新增**。
1. 在&#x200B;**回呼URL**&#x200B;欄位中，根據您的Workfront Fusion資料中心，輸入下列其中一個URL：

   | Fusion資料中心 | 回呼 URL |
   |---|---|
   | US | `https://app.workfrontfusion.com/oauth/cb/workfront-jira2` |
   | 歐盟 | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira2` |
   | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira2` |

1. 在左側導覽中，按一下&#x200B;**設定**。
1. （選擇性）在[描述]欄位中輸入描述，然後按一下該欄位下的&#x200B;**儲存變更**。
1. 從[設定]區域將[使用者端ID]和[使用者端密碼]複製到安全位置，或在Fusion中設定連線時保持此頁面開啟。
1. 繼續[在Fusion](#configure-the-oauth2-connection-in-fusion)中設定OAutt2連線

#### 在Fusion中設定OAuth2連線

1. 在任何Jira模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 設定下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>連線類型</p> </td> 
      <td> <p>選取<b>OAuth 2</b>。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>連線名稱</p> </td> 
      <td> <p>輸入新連線的名稱。</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">服務URL</td>
      <td>輸入您的Jira執行個體URL。 這是您用來存取Jira的URL。</td>
     </tr>
     <tr>
      <td role="rowheader">Jira帳戶型別</td>
       <td>選取您要連線至Jira Cloud或Jira Datacenter。</td>
     </tr>
     <tr> 
      <td role="rowheader">用戶端 ID</td> 
      <td> <p>輸入您在<a href="#create-an-oauth2-application-in-jira" class="MCXref xref" data-mc-variable-override="">中建立之Jira應用程式的使用者端ID在Jira</a>中建立OAuth2應用程式。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">用戶端密碼</td> 
      <td> <p>輸入您在<a href="#create-an-oauth2-application-in-jira" class="MCXref xref" data-mc-variable-override="">在Jira</a>中建立OAuth2應用程式時，所建立Jira應用程式的使用者端密碼。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">其他範圍</td> 
      <td>輸入任何其他要新增至此連線的範圍。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API 版本</td> 
      <td>選取您要此連線連線的Jira API版本。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

### 建立與Jira的基本連線

建立與Jira的基本連線會有所不同，具體取決於您是要建立與Jira Cloud還是Jira資料中心的連線。

* [建立與Jira雲端的基本連線](#create-a-basic-connection-to-jira-cloud)
* [建立與Jira資料中心的基本連線](#create-a-basic-connection-to-jira-data-center)

#### 建立與Jira雲端的基本連線

>[!IMPORTANT]
>
> 若要建立與Jira Cloud的基本連線，您必須擁有Jira API權杖。
>如需取得Jira API Token的指示，請參閱Atlassian檔案中的[管理Atlassian帳戶的API Token](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account)。


1. 在任何Jira模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 設定下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>連線類型</p> </td> 
      <td> <p>選擇您要建立基本連線還是OAuth 2連線。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>連線名稱</p> </td> 
      <td> <p>輸入新連線的名稱。</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">服務URL</td>
      <td>輸入您的Jira執行個體URL。 這是您用來存取Jira的URL。</td>
     </tr>
     <tr>
      <td role="rowheader">Jira帳戶型別</td>
       <td>選取您要連線至Jira Cloud或Jira Datacenter。</td>
     </tr>
     <tr> 
      <td role="rowheader">電子郵件</td> 
      <td>輸入您的電子郵件地址。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API Token</td> 
      <td>輸入您的API Token。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API 版本</td> 
      <td>選取您要此連線連線的Jira API版本。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

#### 建立與Jira資料中心的基本連線

>[!IMPORTANT]
>
> 若要建立與Jira資料中心的基本連線，您必須擁有Jira個人存取權杖(PAT)。
>如需取得Jira個人存取權杖的指示，請參閱Atlassian檔案中的[管理Atlassian帳戶的API權杖](https://confluence.atlassian.com/enterprise/using-personal-access-tokens-1026032365.html)。
>如需建立PAT時的考量事項，請參閱本文中的[設定您的PAT](#configure-your-pat)。

1. 在任何Jira模組中，按一下[連線]欄位旁的&#x200B;**新增**。
1. 設定下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>連線類型</p> </td> 
      <td> <p>選擇您要建立基本連線還是OAuth 2連線。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>連線名稱</p> </td> 
      <td> <p>輸入新連線的名稱。</p> </td> 
     </tr> 
     <tr>
      <td role="rowheader">服務URL</td>
      <td>輸入您的Jira執行個體URL。 這是您用來存取Jira的URL。</td>
     </tr>
     <tr>
      <td role="rowheader">Jira帳戶型別</td>
       <td>選取您要連線至Jira Cloud或Jira Datacenter。</td>
     </tr>
     <tr> 
      <td role="rowheader">PAT （個人存取權杖）</td> 
      <td>輸入您的Jira個人存取權杖。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">API 版本</td> 
      <td>選取您要此連線連線的Jira API版本。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

##### 設定您的PAT

若要建立與Jira資料中心的基本連線，您必須擁有Jira個人存取權杖(PAT)。

如需取得Jira個人存取權杖的指示，請參閱Atlassian檔案中的[管理Atlassian帳戶的API權杖](https://confluence.atlassian.com/enterprise/using-personal-access-tokens-1026032365.html)。

設定PAT時，您可能需要下列資訊

* 重新導向URL

  | Fusion資料中心 | 重新導向 URL |
  |---|---|
  | US | `https://app.workfrontfusion.com/oauth/cb/workfront-jira` |
  | 歐盟 | `https://app-eu.workfrontfusion.com/oauth/cb/workfront-jira` |
  | Azure | `https://app-az.workfrontfusion.com/oauth/cb/workfront-jira` |

* 檔案設定

若要使用PAT，您必須在檔案`jira/bin/WEB-INF/classes`的檔案`jira-config.properties`中啟用下列專案：

* `jira.rest.auth.allow.basic = true`
* `jira.rest.csrf.disabled = true`

如果此檔案不存在，您必須建立它。

## Jira模組及其欄位

設定Jira模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能會顯示其他Jira欄位，視您應用程式或服務中的存取層級等因素而定。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

#### 留意記錄

此觸發模組會在新增、更新或刪除記錄時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Webhook</td> 
   <td> <p>選取您要用來監視記錄的webhook，或建立新的webhook。 </p> <p>若要建立新的 Webhook：</p> 
    <ol> 
     <li>按一下<strong>新增</strong></li> 
     <li>輸入webhook的名稱。</li> 
     <li> 選取您要用於webhook的連線。 <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </li> 
     <li> <p>選取您要軟體監視的記錄型別：</p> 
      <ul> 
       <li>問題</li> 
       <li>註解 </li> 
       <li>工作記錄檔 </li> 
       <li>專案 </li> 
       <li>Sprint</li> 
       <li>附件 </li> 
      </ul> </li> 
     <li>選取將觸發此情境的一或多個事件型別。</li> 
     <li>輸入此模組的Jira查詢語言篩選器。<p>如需有關JQL的詳細資訊，請參閱Atlassian說明網站上的<a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a>。 </p></li>
     <li>按一下<b>儲存</b>以儲存webhook。 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [將問題新增至衝刺](#add-issue-to-sprint)
* [建立記錄](#create-a-record)
* [自訂API呼叫](#custom-api-call)
* [刪除記錄](#delete-a-record)
* [下載附件](#download-an-attachment)
* [讀取記錄](#read-a-record)
* [更新記錄](#update-a-record)

#### 將問題新增至衝刺

此動作模組會將一或多個問題新增至衝刺。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">衝刺ID</td> 
   <td>輸入或對應您想要新增問題的衝刺(Sprint)的Sprint ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">問題ID</td> 
   <td>針對您想要新增至衝刺的每個問題或金鑰，按一下「<b>新增專案</b>」並輸入問題ID或金鑰。 在一個模組中最多可輸入50個。</td> 
  </tr> 
 </tbody> 
</table>

#### 建立記錄

此動作模組會在Jira中建立新記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要模組建立的記錄型別。</p> 
    <ul> 
     <li>附件</li> 
     <li>註解</li> 
     <li>問題</li> 
     <li>專案</li> 
     <li>Sprint </li> 
     <li>工作記錄檔</li> 
     <li>使用者</li> 
     <li>展示板</li> 
     <li>類別</li> 
     <li>篩選器</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td> 填寫其他欄位。 可用欄位取決於所選的記錄型別。 </td> 
  </tr> 
 </tbody> 
</table>

#### 自訂API呼叫

此動作模組可讓您對Jira API進行自訂的已驗證呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td>輸入相對於<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">方法</td> 
   td&gt; <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">標頭</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p> Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">查詢字串</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">正文</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### 刪除記錄

此動作模組會刪除指定的記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要模組刪除的記錄型別。 </p> 
    <ul> 
     <li>註解</li> 
     <li>問題</li> 
     <li>專案</li> 
     <li>Sprint </li> 
     <li>工作記錄檔</li> 
     <li>附件</li> 
     <li>展示板</li> 
     <li>類別</li> 
     <li>篩選器</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">（記錄型別）ID</td> 
   <td>輸入或對應您要刪除之記錄的ID或金鑰。</td> 
  </tr> 
 </tbody> 
</table>

#### 下載附件

此動作模組會下載指定的附件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID</td> 
   <td>輸入或對應您要下載之附件的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### 讀取記錄

此動作模組會從Jira中的指定記錄讀取資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您希望模組讀取的Jira記錄型別。</p> 
    <ul> 
     <li>附件</li> 
     <li>註解</li> 
     <li>問題</li> 
     <li>專案</li> 
     <li>Sprint </li> 
     <li>工作記錄檔</li> 
     <li>使用者</li> 
     <li>展示板</li> 
     <li>類別</li> 
     <li>篩選器</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸出</td> 
   <td>選取您要接收的輸出。 根據「記錄型別」欄位中選取的記錄型別，可使用輸出選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">（記錄型別） ID</td> 
   <td> <p>輸入或對應您要模組讀取之記錄的唯一Jira ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 更新記錄

此動作模組會更新現有記錄，例如問題或專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要模組更新的記錄型別。 當您選取記錄型別時，該記錄型別專屬的其他欄位會出現在模組中。</p> 
    <ul> 
     <li>註解</li> 
     <li>問題</li> 
     <li>專案</li> 
     <li>Sprint </li> 
     <li>轉換問題</li> 
     <li>類別 </li> 
     <li>篩選器 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID或金鑰</td> 
   <td>輸入或對應您要更新的記錄ID或金鑰。</td> 
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td> 填寫其他欄位。 可用欄位取決於所選的記錄型別。 </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

>[!IMPORTANT]
>
>舊版Jira聯結器使用的搜尋模組可能會導致以下錯誤：
>
>`[410] The requested API has been removed. Please migrate to the /rest/api/3/search/jql API. A full migration guideline is available at https://developer.atlassian.com/changelog/#CHANGE-2046`
>
>這是因為Jira端已棄用。
>
>如果您遇到此錯誤，您可以使用新聯結器的搜尋模組來取代舊版Jira聯結器的搜尋模組。 請注意，新的聯結器可讓您選取使用的API版本。 建立連線時，請務必選取V3。
>
> 新Jira聯結器中的![API版本選項](/help/workfront-fusion/references/apps-and-modules/assets/jira-version-option.png)
>
>請注意：
>
>* 只有搜尋模組會受到影響。 目前，Fusion聯結器使用的其他Jira API端點不會受到此淘汰的影響。
>
>* 地理轉出可能會導致不一致。 Atlassian正在地區範圍內推出這項變更，這表示有些Jira Cloud執行個體可能仍會暫時支援較舊的端點。 這可能會導致環境間的行為不一致。

#### 搜尋記錄

此搜尋模組會在Jira中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境內之後的模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連線</td> 
   <td> <p>如需有關將Jira帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Jira連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> <p>選取您要模組搜尋的記錄型別。 當您選取記錄型別時，該記錄型別專屬的其他欄位會出現在模組中。</p> 
    <ul> 
     <li>問題</li> 
     <li>專案</li> 
     <li>使用者</li> 
     <li>Sprint</li> 
     <li>展示板</li> 
     <li>工作記錄檔</li> 
     <li>註解</li> 
     <li>轉換問題</li> 
     <li>類別</li> 
    </ul> </td> 
  <tr> 
   <td role="rowheader"> <p>最大結果</p> </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中擷取的記錄數上限。</p> </td> 
  </tr> 
   <tr> 
    <td role="rowheader">位移</td> 
    <td> 輸入或對應您要擷取其詳細資訊的第一個專案ID。 這是分頁記錄的方式。 如果您輸入第5000個專案作為位移，模組會傳回專案5000-9999。</td> 
   </tr>
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td> 填寫其他欄位。 可用欄位取決於所選的記錄型別。 </td> 
  </tr> 
 </tbody> 
</table>

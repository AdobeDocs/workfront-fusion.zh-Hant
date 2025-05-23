---
title: Jira軟體模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動化使用 [!DNL Jira] 軟體的工作流程，以及將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 92cac080-d8f6-4770-a6a6-8934538c978b
source-git-commit: 40470e5d2183f690ad65f5e1170f78c37dee8603
workflow-type: tm+mt
source-wordcount: '2208'
ht-degree: 1%

---

# [!DNL Jira Software]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Jira Software]的工作流程，並將其連線至多個協力廠商應用程式和服務。

這些指示適用於Jira Cloud和Jira伺服器模組。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

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

## 先決條件

若要使用[!DNL Jira]模組，您必須有[!DNL Jira]帳戶。

## Jira API資訊

Jira聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"></td> 
   <td> Jira Cloud</td> 
   <td> Jira伺服器</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersion</td> 
   <td> 2</td> 
   <td> 2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">apiVersionAgile</td> 
   <td> 1.0 </td> 
   <td> 1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>1.7.29</td> 
   <td>1.0.19</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Jira Software]連線至[!DNL Workfront Fusion]

您的連線方式是以您使用[!DNL Jira Cloud]或[!DNL Jira Server]為基礎。

* [連線 [!DNL Jira Cloud] 至Workfront Fusion](#connect-jira-cloud-to-workfront-fusion)
* [連線 [!DNL Jira Server] 至 [!DNL Workfront Fusion]](#connect-jira-server-to-workfront-fusion)

### 將[!DNL Jira Cloud]連線至[!DNL Workfront Fusion]

將[!DNL Jira Cloud]連線至[!DNL Workfront Fusion]

若要將[!DNL Jira Software]連線到[!DNL Workfront Fusion]，您必須建立API權杖，並將它連同您的服務URL和使用者名稱插入到[!DNL Workfront Fusion]中的[!UICONTROL 建立連線]欄位。

#### 在[!DNL Jira]中建立API權杖

1. 在Jira中建立API權杖。

   如需指示，我們建議您在Jira檔案中搜尋「建立API權杖」。
1. 建立權杖後，將權杖複製到安全位置。

   >[!IMPORTANT]
   >
   >關閉此對話方塊後，您無法再次檢視權杖。
1. 將產生的Token儲存在安全的地方。
1. 繼續[在 [!DNL Workfront Fusion]](#configure-the-jira-api-token-in-workfront-fusion)中設定 [!DNL Jira] API Token。

#### 在[!DNL Workfront Fusion]中設定[!DNL Jira] API權杖

1. 在[!DNL Workfront Fusion]的任何[!DNL Jira Cloud]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 指定下列資訊：

   * **環境**
   * **型別**
   * **[!UICONTROL 服務URL]：**&#x200B;這是您用來存取Jira帳戶的基本URL。 範例： `yourorganization.atlassian.net`
   * **[!UICONTROL 使用者名稱]**
   * **[!UICONTROL API Token]：**&#x200B;這是您在本文章的[在 [!DNL Jira]](#create-an-api-token-in-jira)區段中建立API Token所建立的API Token。

1. 按一下[!UICONTROL 繼續]以建立連線並返回模組。

### 將[!DNL Jira Server]連線至[!DNL Workfront Fusion]

若要授權[!DNL Workfront Fusion]與[!DNL Jira Server]之間的連線，您需要您的消費者金鑰、私密金鑰和服務URL。 您可能需要連絡您的[!DNL Jira]管理員以取得此資訊。

* [為您的 [!DNL Jira] 連線產生公開和私密金鑰](#generate-public-and-private-keys-for-your-jira-connection)
* [將使用者端應用程式設定為 [!DNL Jira]中的消費者](#configure-the-client-app-as-a-consumer-in-jira)
* [建立與 [!DNL Workfront Fusion]中的 [!DNL Jira] 伺服器或Jira資料中心的連線](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)

#### 為您的[!DNL Jira]連線產生公開和私密金鑰

若要取得您[!DNL Workfront Fusion Jira]連線的私密金鑰，您必須產生公開和私密金鑰。 這是透過電腦終端機完成的。 您可以在[開始]功能表或電腦搜尋列（不是瀏覽器搜尋列）中搜尋終端機，以找出您的終端機。

1. 在您的終端機中，執行下列`openssl`命令。

   * `openssl genrsa -out jira_privatekey.pem 1024`

     這個指令會產生1024位元私密金鑰。

   * `openssl req -newkey rsa:1024 -x509 -key jira_privatekey.pem -out jira_publickey.cer -days 365`

     這個命令會建立X509憑證。

   * `openssl pkcs8 -topk8 -nocrypt -in jira_privatekey.pem -out jira_privatekey.pcks8`

     這個命令會將私密金鑰（PKCS8格式）擷取到`jira_privatekey.pcks8`檔案。

   * `openssl x509 -pubkey -noout -in jira_publickey.cer  > jira_publickey.pem`

     這個命令會將公開金鑰從憑證擷取到`jira_publickey.pem`檔案。

     >[!NOTE]
     >
     >如果您使用Windows，您可能需要手動將公開金鑰儲存至`jira_publickey.pem`檔案：
     >
     >1. 在終端機中，執行以下命令：
     >   
     >   `openssl x509 -pubkey -noout -in jira_publickey.cer`
     >   
     >1. 複製終端機輸出，包括`-------BEGIN PUBLIC KEY--------`和`-------END PUBLIC KEY--------`。
     >   
     >1. 將終端機輸出貼到名為`jira_publickey.pem`的檔案中。


1. 繼續[將使用者端應用程式設定為 [!DNL Jira]](#configure-the-client-app-as-a-consumer-in-jira)中的消費者

#### 在[!DNL Jira]中將使用者端應用程式設定為消費者

1. 登入您的[!DNL Jira]執行個體。
1. 在左側導覽面板中，按一下&#x200B;**[!UICONTROL [!DNL Jira]設定]** ![Jira設定圖示](/help/workfront-fusion/references/apps-and-modules/assets/jira-settings-icon.png) > **[!UICONTROL 應用程式]**> **[!UICONTROL 應用程式連結]**。
1. 在&#x200B;**[!UICONTROL 輸入您要連結的應用程式URL]**&#x200B;欄位中，輸入

   ```
   https://app.workfrontfusion.com/oauth/cb/workfront-jiraserver-oauth1
   ```

1. 按一下&#x200B;**[!UICONTROL 建立新連結]**。 忽略「沒有從您輸入的URL收到回應」錯誤訊息。
1. 在&#x200B;**[!UICONTROL 連結應用程式]**&#x200B;視窗中，在&#x200B;**[!UICONTROL 消費者金鑰]**&#x200B;與&#x200B;**[!UICONTROL 共用機密]**&#x200B;欄位中輸入值。

   您可以選擇這些欄位的值。

1. 將&#x200B;**[!UICONTROL 消費者金鑰]**&#x200B;和&#x200B;**[!UICONTROL 共用機密]**&#x200B;欄位的值複製到安全位置。

   您稍後在設定過程中會需要這些值。

1. 請依照以下說明填寫URL欄位：

   | 欄位 | 說明 |
   |---|---|
   | [!UICONTROL 要求權杖URL] | `<Jira base url>/plugins/servlet/oauth/request-token` |
   | [!UICONTROL 授權URL] | `<Jira base url>/plugins/servlet/oauth/authorize` |
   | [!UICONTROL 存取權杖URL] | `<Jira base url>/plugins/servlet/oauth/access-token` |

1. 選取&#x200B;**[!UICONTROL 建立連入連結]**&#x200B;核取方塊。
1. 按一下&#x200B;**[!UICONTROL 繼續]**。
1. 在&#x200B;**[!UICONTROL 連結應用程式]**&#x200B;視窗中，填寫下列欄位：

   <table style="table-layout:auto"> 
    <col data-mc-conditions=""> 
    <col data-mc-conditions=""> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 消費者金鑰]</p> </td> 
      <td> 將您複製的消費者金鑰貼入安全位置。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 消費者名稱]</td> 
      <td>輸入您選擇的名稱。 此名稱僅供您參考。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 公開金鑰]</td> 
      <td>從您的<code>[!DNL jira_publickey.pem]</code>檔案貼入公開金鑰。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**。
1. 繼續[在 [!DNL Workfront Fusion]](#create-a-connection-to-jira-server-or-jira-data-center-in-workfront-fusion)中建立與 [!DNL Jira Server] 或 [!DNL Jira Data Center] 的連線

#### 在[!DNL Workfront Fusion]中建立與[!DNL Jira Server]或[!DNL Jira Data Center]的連線

>[!NOTE]
>
>使用[!DNL Jira Server]應用程式連線至[!DNL Jira Server]或[!DNL Jira Data Center]。

1. 在[!DNL Workfront Fusion]的任何[!DNL Jira Server]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 在[!UICONTROL 建立連線]面板中，填寫下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線名稱]</p> </td> 
      <td> <p>輸入連線的名稱。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 環境]</p> </td> 
      <td> <p>選取您使用生產或非生產環境。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 型別]</p> </td> 
      <td> <p>選取您是使用服務帳戶還是個人帳戶。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 消費者金鑰]</td> 
      <td>貼入您複製到<a href="#configure-the-client-app-as-a-consumer-in-jira" class="MCXref xref">中安全位置的消費者金鑰在[!DNL Jira]</a>中將使用者端應用程式設定為消費者</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Private Key]</td> 
      <td>從您在<a href="#generate-public-and-private-keys-for-your-jira-connection" class="MCXref xref">產生您連線[!DNL Jira]的公開和私密金鑰</a>中建立的<code>[!DNL jira_privatekey.pcks8]</code>檔案貼上私密金鑰。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!DNL Service URL]</td> 
      <td>輸入您的[!DNL Jira]執行個體URL。 範例： <code>yourorganization.atlassian.net</code></td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

## [!DNL Jira Software]模組及其欄位

當您設定[!DNL Jira Software]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Jira Software]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)

### 觸發程序

#### [!UICONTROL 觀看記錄]

此觸發模組會在新增、更新或刪除記錄時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td> <p>選取您要用來監視記錄的webhook。 </p> <p>若要新增webhook：</p> 
    <ol> 
     <li value="1">按一下<strong>[!UICONTROL 新增]</strong></li> 
     <li value="2">輸入webhook的名稱。</li> 
     <li value="3"> <p>選取您要用於webhook的連線。 </p> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </li> 
     <li value="4"> <p>選取您要軟體監視的記錄型別：</p> 
      <ul> 
       <li>[!UICONTROL 註解] </li> 
       <li>[!UICONTROL 問題]</li> 
       <li>[!UICONTROL 專案] </li> 
       <li>[!UICONTROL Sprint]</li> 
      </ul> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 新增問題至衝刺]](#add-issue-to-sprint)
* [[!UICONTROL 建立記錄]](#create-a-record)
* [[!UICONTROL 自訂API呼叫]](#custom-api-call)
* [[!UICONTROL 刪除記錄]](#delete-a-record)
* [[!UICONTROL 下載附件]](#download-an-attachment)
* [[!UICONTROL 讀取記錄]](#read-a-record)
* [[!UICONTROL 更新記錄]](#update-a-record)

#### [!UICONTROL 新增問題至衝刺]

此動作模組會將一或多個問題新增至衝刺。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sprint ID]</td> 
   <td>輸入或對應您想要新增問題的衝刺(Sprint)的Sprint ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 問題ID或金鑰]</td> 
   <td>對於您想要檢視體驗的每個問題或金鑰，請按一下<b>[!UICONTROL 新增專案]</b>並輸入問題ID或金鑰。 在一個模組中最多可輸入50個。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立記錄]

此動作模組會在Jira中建立新記錄。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組建立的記錄型別，然後填寫專屬於該記錄型別的其他欄位，顯示在模組中。</p> 
    <ul> 
     <li>[!UICONTROL 附件]</li> 
     <li>[!UICONTROL 註解]</li> 
     <li>[!UICONTROL 問題]</li> 
     <li>[!UICONTROL 專案]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 自訂API呼叫]

此動作模組可讓您對[!DNL Jira Software] API進行自訂的已驗證呼叫。 使用此模組建立其他[!DNL Jira Software]模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>&lt;Instance URL>/rest/api/2/ </code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png">  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除指定的記錄。

您指定記錄的ID。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組刪除的記錄型別。 </p> 
    <ul> 
     <li>[!UICONTROL 附件]</li> 
     <li>[!UICONTROL 註解]</li> 
     <li>[!UICONTROL 問題]</li> 
     <li>[!UICONTROL 專案]</li> 
     <li>[!UICONTROL Sprint] </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID或金鑰]</td> 
   <td>輸入或對應您要刪除之記錄的ID或金鑰。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 下載附件]

此動作模組會下載特定附件。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td>輸入或對應您要下載之附件的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 讀取記錄]

此動作模組從[!DNL Jira Software]中的單一記錄讀取資料。

您指定記錄的ID。

模組會傳回與記錄相關聯的任何標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您希望模組讀取的[!DNL Jira]記錄型別。</p> 
    <ul> 
     <li>[!UICONTROL 附件]</li> 
     <li>[!UICONTROL 問題]</li> 
     <li>[!UICONTROL 專案]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL 使用者]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸出]</td> 
   <td>選取您要接收的輸出。 根據「[!UICONTROL 記錄型別]」欄位中選取的記錄型別，可使用輸出選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID]</td> 
   <td> <p>輸入或對應您要模組讀取之記錄的唯一[!DNL Jira Software]識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新記錄]

此動作模組會更新現有記錄，例如問題或專案。

您指定記錄的ID。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組更新的記錄型別。 當您選取記錄型別時，該記錄型別專屬的其他欄位會出現在模組中。</p> 
    <ul> 
     <li>[!UICONTROL 註解]</li> 
     <li>[!UICONTROL 問題]</li> 
     <li>[!UICONTROL 專案]</li> 
     <li>[!UICONTROL Sprint] </li> 
     <li>[!UICONTROL 轉換問題]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL ID或金鑰]</td> 
   <td>輸入或對應您要更新之記錄的ID或金鑰，然後填寫專屬於該記錄型別的其他欄位，即會顯示在模組中。</td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

* [[!UICONTROL 清單記錄]](#list-records)
* [[!UICONTROL 搜尋記錄]](#search-for-records)

#### [!UICONTROL 清單記錄]

此搜尋模組會擷取符合您搜尋查詢的特定型別的所有專案

您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組列出的記錄型別。 當您選取記錄型別時，該記錄型別專屬的其他欄位會出現在模組中。</p> 
    <ul> 
     <li>[!UICONTROL 註解]</li> 
     <li>[!UICONTROL 問題]</li> 
     <li>[!UICONTROL 專案]</li> 
     <li>[!UICONTROL Sprint問題]</li> 
     <li>[!UICONTROL Worklog]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 最大結果]</p> </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中擷取的記錄數上限。</p> </td> 
  </tr> <!--
   <tr> 
    <td role="rowheader">Offset</td> 
    <td> Enter or map the ID of the first item you want to retrieve details for. This is a way to paginate the records. If you enter the 5000th item as the offset, the module would return items 5000-9999.</td> 
   </tr>
  --> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋記錄]

此搜尋模組會在[!DNL Jira Software]中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Jira Software]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-jira-software-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將[!DNL Jira Software]連線到[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 記錄型別]</td> 
   <td> <p>選取您要模組搜尋的記錄型別。 當您選取記錄型別時，該記錄型別專屬的其他欄位會出現在模組中。</p> 
    <ul> 
     <li>[!UICONTROL 問題]</li> 
     <li> <p>[!UICONTROL Issues by JQL （Jira查詢語言）] </p> <p>如需有關JQL的詳細資訊，請參閱Atlassian說明網站上的<a href="https://www.atlassian.com/blog/jira-software/jql-the-most-flexible-way-to-search-jira-14#:~:text=JQLstandsforJiraQuery,projectmanagers%2Candbusinessusers.">JQL</a>。 </p> </li> 
     <li>[!UICONTROL 專案]</li> 
     <li>&lbrack;！UICONTROL專案（按問題）</li> 
     <li>[!UICONTROL 使用者]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

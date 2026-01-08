---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: 使用範本連結Adobe Workfront Fusion和Jira
description: 使用這些範本自動化Adobe Workfront Fusion和Jira之間的工作流程。
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
source-git-commit: aa3bdd7d14c86085c36e3859f6d53c0cadb28920
workflow-type: tm+mt
source-wordcount: '4075'
ht-degree: 3%

---

# 使用範本連結Adobe Workfront Fusion和Jira

Adobe Workfront Fusion提供可自動化Fusion和Jira之間常用工作流程的範本。

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
   <td role="rowheader">產品</td> 
   <td>
   <p>Workfront：如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</p><p>Jira：您必須擁有Jira Cloud的授權</p>
   </td> 
  </tr>
  <tr> 
   <td role="rowheader">存取層級設定</td> 
   <td> <p>Workfront：建立使用者、自訂表單和自訂欄位的許可權。</p> <p>Jira：建立使用者和自訂欄位，以及修改畫面和Webhook的許可權。</td> 
  </tr> 
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 先決條件

### Workfront

* 您必須在Adobe Developer Console上擁有技術帳戶。

  如需相關資訊與指示，請參閱Adobe檔案中的[技術帳戶設定](https://developer.adobe.com/cloud-storage/guides/getting-started/technical-account-setup)。
* 您必須套用系統管理員許可權到Adobe Admin Console產品設定檔區域中的技術帳戶。

  如需資訊與指示，請參閱[使用Adobe Admin Console在Workfront中建立系統管理員](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/admin-console#create-system-administrators-in-workfront-with-the-adobe-admin-console)

### Jira

如果您使用Jira的OAuth2授權（建議），您必須在[https://developer.atlassian.com/console](https://developer.atlassian.com/console)設定OAuth2應用程式。 如需資訊與指示，請參閱Jira模組文章中的[建立與Jira](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#create-an-oauth2-connection-to-jira)的OAuth2連線。

<!--

When configuring this application, you will need the following scopes:

* `read:jira-work` 
* `read:jira-user`
* `write:jira-work`

-->

## 假設

這些模組會假設如下：

* Workfront是整體行銷活動專案的真實來源
* 技術團隊正在使用Jira，完成在Workfront開始的專案的一部分。
* 並非所有Jira使用者都能存取Workfront，反之亦然。
* Workfront和Jira在雲端中託管。

## 資料模型（欄位對應）


| Workfront | Jira | 方向 | 附註 |
|---|---|---|---|
| 物件ID | WF ID * | WF → Jira | 在Jira問題建立時 |
| Jira金鑰* | 問題索引鍵 | Jira → WF | 在Jira問題建立時 |
| Jira URL * | - | Jira → WF | WF中的使用者可點按連結至Jira |
| - | WF連結* | WF → Jira | Jira中的使用者可點按連結至WF |
| 名稱 | 摘要 | WF → Jira |  |
| 說明 | 說明 | WF → Jira |  |
| 狀態 | WF狀態 | WF → Jira | WF狀態 |
| Jira狀態* | 狀態 | Jira → WF | Jira狀態 |
| 規劃完成日期 | 到期日期 | WF → Jira | 規劃完成日期 |
| 附註 | 註解 | WF ↔ Jira | 雙向複製 |
| 文件 | 附件 | WF → Jira | 作為問題建立的附件和建立後新檔案的註解。 |

\*這些欄位已設定為此整合設定的一部分。 如需指示，請參閱[在Workfront、Jira和Workfront Fusion中設定先決條件](/help/workfront-fusion/create-and-manage-templates/use-jira-scenario-templates.md#configure-prerequisites-in-workfront-jira-and-workfront-fusion)。

## 在Workfront、Jira和Workfront Fusion中設定先決條件

若要使用Jira整合範本，您必須執行下列設定：

* [設定Jira](#configure-jira)
* [設定Workfront](#configure-workfront)
* [在Workfront Fusion中設定連線](#configure-connections-in-workfront-fusion)

### 設定Jira

若要使用這些模組，必須在Jira中建立下列專案：

* 系統整合使用者
* 三個特定自訂欄位

#### 在Jira中建立系統整合使用者

1. 在Jira中，建立名為系統整合使用者的特定使用者。 此使用者應該僅由Workfront Fusion使用，而不應該代表人類使用者。 Workfront Fusion連線將會使用此使用者的認證。

#### 在Jira中建立必要的自訂欄位

此整合預期連線到的Jira帳戶中會有三個特定欄位。 如果沒有這些欄位，整合將會失敗

1. 在Jira中，移至&#x200B;**設定** （齒輪圖示）並選取&#x200B;**工作專案**。
1. 在左側導覽中，選取&#x200B;**自訂欄位**。
1. 在熒幕的右上角，按一下&#x200B;**建立自訂欄位。**
1. 建立下列欄位：

   | 欄位名稱 | 欄位類型 |
   |---|---|
   | WF ID | 文字欄位（單行） |
   | WF狀態 | 文字欄位（單行） |
   | WF連結 | url欄位 |

   如需有關在Jira中建立連結的資訊，請參閱有關建立欄位的Jira檔案。
1. 將新建立的欄位新增到與您的Jira專案關聯的畫面。

   如需Jira中熒幕的資訊，請參閱關於設定工作專案熒幕的Jira檔案。


### 設定Workfront

若要使用這些模組，必須在Workfront中建立下列專案：

* 系統整合使用者
* 特定自訂表格

#### 在Workfront中建立系統整合使用者

1. 在Workfront中，建立系統整合使用者。 此使用者僅供Workfront Fusion使用，不代表人類使用者。 指派給此使用者的任務將觸發將Workfront與Jira同步的情境。

   如需指示，請參閱Workfront檔案中的[新增使用者](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users)。

#### 在Workfront中建立自訂表單

1. 在Workfront中，開始建立自訂表單。

   如需指示，請參閱Workfront檔案中的[建立自訂表單](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form)。
1. 將表單命名為&quot;**JIRA欄位**&quot;。
1. 在自訂表單上包含下列欄位：

| 欄位名稱 | 欄位類型 |
|---|---|
| Jira金鑰 | 單行文字欄位 |
| Jira URL | 單行文字欄位 |
| Jira狀態 | 單行文字欄位 |

1. 新增任何其他您想在Jira和Workfront之間對應的欄位。
1. 儲存自訂表單。

>[!NOTE]
>
>我們建議限制此表單以供其他使用者編輯。 您可以透過確保新增到自訂表單的任何使用者僅擁有檢視存取權來完成此操作。
>
>如需指示，請參閱Workfront檔案中的[共用自訂表單](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/manage-custom-forms/share-access-to-a-custom-form)。

### 在Workfront Fusion中設定連線

您必須先在Jira和Workfront中建立系統整合使用者，才能建立連線。

建立這些連線時，請務必使用已建立之系統整合使用者的認證。

如有需要，您可以在設定範本時建立這些連線。

* 如需建立與Workfront的連線的指示，請參閱Workfront模組一文中的[將Workfront連線到Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#connect-workfront-to-workfront-fusion)。
* 如需建立與Jira連線的說明，請參閱「Jira軟體模組」一文中的[將Jira連線到Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion)。


## 情境

八個現成可用的Jira範本可協助複製常見的工作流程並加速實作。 範本是完全可自訂的，可滿足特定的業務需求，且可隨著需求的發展而擴充。

您不需要實作所有情境。 最低實作需要情境1，這會根據Workfront中的指派建立與JIRA問題的單向整合。  您可以新增其他情境，在Workfront和JIRA之間新增健全性和更雙向的相互連線。  您也可以建立其他案例來處理專案到大型整合或JIRA問題到Workfront問題或任務等案例。

這些範本或範本擴充功能的任何使用都會視為自訂設定，建議您使用Adobe Professional Services或Adobe合作夥伴提供支援和實作。

* **[Workfront至Jira：從Workfront任務或問題指派建立JIRA問題](#scenario-1-workfront-to-jira-create-jira-issue-from-workfront-task-or-issue-assignment)**
* [JIRA至Workfront： JIRA至Workfront：將問題和評論的更新從Jira傳回Workfront](#scenario-2-jira-to-workfront-send-updates-on-issues-and-comments-back-to-workfront-from-jira)
* [Workfront到Jira：將Workfront任務變更為JIRA問題](#scenario-3-workfront-to-jira-changes-to-workfront-task-to-jira-issue)
* Workfront至Jira：將Workfront問題變更為JIRA問題
* Workfront對Jira：在Workfront任務或問題新增備註時在JIRA中建立評論
* Workfront對Jira：在JIRA中建立Workfront任務或問題上已刪除附註的評論
* Workfront對Jira：當有關Workfront任務或問題的新檔案時在JIRA中建立評論
* Workfront對Jira：在JIRA中就Workfront任務或問題上的已刪除檔案建立評論

### 一般引數

設定這些範本時，請使用下列一般引數：

* **JiraBaseURL**： Jira執行個體的基底URL。 範例：`https://myjira.atlassian.net/`
* **wfBaseURL**： Workfront執行個體的基底URL。  通常： `https://<domain>.my.workfront.com`，其中`<domain>`是您特定的Workfront網域名稱。
* **defaultJIRAReporterID**：在JIRA中建立問題的使用者識別碼。 （範例： `557058:5aedf933-2312-40bc-b328-0c21314167f0`）
您可以執行下列任一項作業來取得此ID：
   * 在JIRA中按一下使用者的設定檔，然後檢查瀏覽器中的URL。
（範例`https://myjira.atlassian.net/jira/people/<JiraUserID>`）
   * 在您的JIRA執行個體上執行以下API呼叫，以取得JIRA中特定帳戶的ID：
     `GET /rest/api/3/user/search?query=email@example.com`


### 案例1：Workfront至Jira：從Workfront任務或問題指派建立JIRA問題

此情境會在將Workfront任務或問題指派給系統整合使用者時產生Jira問題。 此情境填寫「摘要」、「說明」、「到期日」、「工作流程狀態」和「工作流程ID」欄位。 建立問題後，此情境也會上傳附件清單，以及與原始任務或問題相關的備註歷史記錄(在Workfront)。

如果已指派Workfront任務，Jira中的問題是任務。 如果指派Workfront問題，則Jira問題是錯誤。

+++**展開以檢視設定案例1:Workfront到Jira的說明：從Workfront任務或問題指派建立JIRA問題**

#### 設定觸發程式模組

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**Workfront to Jira：從Workfront任務或問題指派**&#x200B;範本建立JIRA問題。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。
1. 在第一個模組中，開始新增webhook。
1. 選取您在[在Workfront Fusion](#configure-connections-in-workfront-fusion)中設定連線時所建立的Workfront連線。
1. 在&#x200B;**記錄型別**&#x200B;欄位中，選取`Assignment`。
1. 在&#x200B;**狀態**&#x200B;欄位中，選取`New state`。
1. 使用&#x200B;**And**&#x200B;選項，透過下列操作設定篩選器：

   | 欄位 | 運算子 | 價值 |
   |---|---|---|
   | assignedToID | 等於 | (輸入系統整合使用者的Workfront ID) |
   | 任務ID | 存在 |  |
   | projectID | 等於 | （輸入您希望webhook觀看的一或多個專案的ID） |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 在&#x200B;**記錄來源**&#x200B;欄位中，選取[僅新增記錄]。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 繼續[將範本模組連線至Workfront和Jira](#connect-template-modules-to-workfront-and-jira)

#### 將範本模組連線至Workfront和Jira

1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取您在[在Workfront Fusion中設定連線](#configure-connections-in-workfront-fusion)中所建立的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存與該模組的連線。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取您在[在Workfront Fusion中設定連線](#configure-connections-in-workfront-fusion)中所建立的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存與該模組的連線。
1. 繼續[更新一般引數模組](#update-the-general-parameters-module)。

#### 更新一般引數模組

1. 在範本的第二個模組（設定環境詳細資料）中，針對下列每個變數，按一下&#x200B;**新增專案**&#x200B;並輸入變數的名稱和值

   | 變數名稱 | 變數值 |
   |---|---|
   | defaultJiraReporterID | 輸入當Jira中不存在建立者使用者時的預設使用者ID。 您可以按一下使用者的設定檔，並檢查瀏覽器的URL，以找到此使用者ID。 範例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 輸入您要連線之Jira帳戶的基底URL。 |
   | wfBaseURL | 輸入您要連線之Workfront帳戶的基底URL。 |

1. 繼續在Jira[中](#map-custom-fields-in-jira)對應自訂欄位

#### 對Jira中的自訂欄位。

<!--Awaiting feedback-->

+++

### 案例2：JIRA至Workfront：將問題和評論的更新從Jira傳送回Workfront

此情境會在Jira中建立問題時建立Workfront任務或問題。

>[!NOTE]
>
>此情境需要Jira的OAuth2連線。
>若要使用Jira的OAuth2授權，您必須在[https://developer.atlassian.com/console](https://developer.atlassian.com/console)設定OAuth2應用程式。 如需資訊和指示，請參閱Jira檔案。

+++**展開以檢視設定案例2：從JIRA到Workfront：將問題和評論的更新從Jira傳回Workfront**

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**第2部分：從JIRA到Workfront：將問題和評論的更新從Jira**&#x200B;範本傳回Workfront。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。
1. 在第一個模組中，開始新增webhook。
1. 選取使用系統整合使用者認證的連線，或使用系統整合認證建立與Jira的連線。

* 如需建立與Jira連線的說明，請參閱「Jira軟體模組」一文中的[將Jira連線到Workfront Fusion](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/jira-modules-new.md#connect-jira-to-workfront-fusion)。

1. 設定webhook篩選器

1. 繼續在Jira[中](#configure-a-webhook-in-jira)設定webhook

#### 在Jira中設定webhook

1. 在Jira中，建立webhook。

   如需指示，請參閱Jira檔案中的[Webhooks](https://developer.atlassian.com/server/jira/platform/webhooks/)。

1. 設定webhook時，請使用下列值：

   * **JQL**：專案= &quot;yourProjectName&quot; （其中yourProjectName =您的JIRA專案名稱）
   * **問題**：已建立、已更新
   * **註解**：已建立、已刪除


1. 繼續[將範本模組連線至Workfront和Jira （模組2）](#connect-template-modules-to-workfront-and-jira-module-2)

#### 將範本模組連線至Workfront和Jira （模組2）

1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取您在[在Workfront Fusion中設定連線](#configure-connections-in-workfront-fusion)中所建立的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存與該模組的連線。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取您在[在Workfront Fusion中設定連線](#configure-connections-in-workfront-fusion)中所建立的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存與該模組的連線。
   <!--#### Map custom fields-->

+++

### 案例3：Workfront變更為Jira：Workfront任務變更為JIRA問題

+++**展開以檢視設定案例3：WF對Jira變更（工作）**&#x200B;的說明

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**第3部分：Workfront到Jira：Workfront任務變更為JIRA問題**&#x200B;範本。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。

1. 按一下範本以輸入編輯器。
1. 選取將擁有此情境的組織和團隊。
1. 在第一個模組中，開始新增webhook。
1. 在「連線」欄位中，選取使用系統整合憑證的Workfront連線。
1. 在&#x200B;**記錄型別**&#x200B;欄位中，選取`Task`。
1. 在&#x200B;**狀態**&#x200B;欄位中，選取`New state`。
1. 使用&#x200B;**And**&#x200B;選項，透過下列操作設定篩選器：

   | 欄位 | 運算子 | 價值 |
   |---|---|---|
   | assignedToID | 等於 | 輸入系統整合使用者的Workfront ID |
   | projectID | 等於 | 輸入您希望webhook觀看的一或多個專案的ID。 |
   | DE： Jira金鑰 | 存在 |  |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 在&#x200B;**記錄來源**&#x200B;欄位中，選取`Updated record only`。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 在第二個模組中，設定下列變數，然後按一下&#x200B;**確定**&#x200B;以儲存模組。

   | 變數名稱 | 變數值 |
   |---|---|
   | defaultJiraReporterID | 這是當Jira中不存在建立者使用者時，預設使用者的ID。 您可以按一下使用者的設定檔，並檢查瀏覽器的URL，以找到此使用者ID。 範例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 您要連線之Jira帳戶的基底URL。 |
   | wfBaseURL | 您連線的Workfront帳戶基底URL。 |

1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取使用系統整合認證的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取使用系統整合認證的Jira連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。


+++



### 案例4：Workfront變更為Jira：Workfront問題變更為JIRA問題

此情境會將Workfront問題的更新傳送至先前連線的JIRA問題。

+++**展開以檢視設定案例4：WF對Jira變更（問題）**&#x200B;的說明

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**案例4：WF對Jira變更（問題）**&#x200B;範本。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。

1. 按一下範本以輸入編輯器。
1. 選取將擁有此情境的組織和團隊。
1. 在第一個模組中，開始新增webhook。
1. 在「連線」欄位中，選取使用系統整合憑證的Workfront連線。
1. 在&#x200B;**記錄型別**&#x200B;欄位中，選取`??`。
1. 在&#x200B;**狀態**&#x200B;欄位中，選取`New state`。
1. 使用&#x200B;**And**&#x200B;選項，透過下列操作設定篩選器：

   | 欄位 | 運算子 | 價值 |
   |---|---|---|
   | （問題的更新） |  |  |
   | assignedToID | 等於 | 輸入系統整合使用者的Workfront ID |
   | projectID | 等於 | 輸入您希望webhook觀看的一或多個專案的ID。 |
   | WF ID | 存在 |  |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 在第二個模組中，設定下列變數，然後按一下&#x200B;**確定**&#x200B;以儲存模組。

   | 變數名稱 | 變數值 |
   |---|---|
   | defaultJiraReporterID | 這是當Jira中不存在建立者使用者時，預設使用者的ID。 您可以按一下使用者的設定檔，並檢查瀏覽器的URL，以找到此使用者ID。 範例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 您要連線之Jira帳戶的基底URL。 |
   | wfBaseURL | 您連線的Workfront帳戶基底URL。 |

1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取使用系統整合認證的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取使用系統整合認證的Jira連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。


+++



### 案例5：WF-to-Jira新附註（任務和問題）

+++**展開以檢視設定案例5： WF-to-Jira新備註（任務和問題）的說明**

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**案例5： WF對Jira新備註（任務和問題）**&#x200B;範本。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。
1. 在第一個模組中，開始新增webhook。
1. 在「連線」欄位中，選取使用系統整合憑證的Workfront連線。
1. 在&#x200B;**記錄型別**&#x200B;欄位中，選取`??`。
1. 在&#x200B;**狀態**&#x200B;欄位中，選取`New state`。
1. 使用&#x200B;**And**&#x200B;選項，透過下列操作設定篩選器：

   | 欄位 | 運算子 | 價值 |
   |---|---|---|
   | （建立並更新附註。） |  |  |
   | assignedToID | 等於 | 輸入系統整合使用者的Workfront ID |
   | projectID | 等於 | 輸入您希望webhook觀看的一或多個專案的ID。 |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 在第二個模組中，設定下列變數，然後按一下&#x200B;**確定**&#x200B;以儲存模組。

   | 變數名稱 | 變數值 |
   |---|---|
   | defaultJiraReporterID | 這是當Jira中不存在建立者使用者時，預設使用者的ID。 您可以按一下使用者的設定檔，並檢查瀏覽器的URL，以找到此使用者ID。 範例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 您要連線之Jira帳戶的基底URL。 |
   | wfBaseURL | 您連線的Workfront帳戶基底URL。 |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取使用系統整合認證的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取使用系統整合認證的Jira連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。


+++




### 案例6：WF-to-Jira移除附註（任務和問題）

+++**展開以檢視設定案例6:WF-to-Jira移除附註（任務和問題）**&#x200B;的說明

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**案例6：WF-to-Jira移除附註（任務和問題）**&#x200B;範本。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。
1. 在第一個模組中，開始新增webhook。
1. 在「連線」欄位中，選取使用系統整合憑證的Workfront連線。
1. 在&#x200B;**記錄型別**&#x200B;欄位中，選取`??`。
1. 在&#x200B;**狀態**&#x200B;欄位中，選取`New state`。
1. 使用&#x200B;**And**&#x200B;選項，透過下列操作設定篩選器：

   | 欄位 | 運算子 | 價值 |
   |---|---|---|
   | （在附註上刪除。） |  |  |
   | assignedToID | 等於 | 輸入系統整合使用者的Workfront ID |
   | projectID | 等於 | 輸入您希望webhook觀看的一或多個專案的ID。 |
   | WF ID | 存在 |  |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 在第二個模組中，設定下列變數，然後按一下&#x200B;**確定**&#x200B;以儲存模組。

   | 變數名稱 | 變數值 |
   |---|---|
   | defaultJiraReporterID | 這是當Jira中不存在建立者使用者時，預設使用者的ID。 您可以按一下使用者的設定檔，並檢查瀏覽器的URL，以找到此使用者ID。 範例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 您要連線之Jira帳戶的基底URL。 |
   | wfBaseURL | 您連線的Workfront帳戶基底URL。 |

1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取使用系統整合認證的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取使用系統整合認證的Jira連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。


+++



### 案例7：WF-to-Jira新附件（任務和問題）

+++**展開以檢視設定Scenario 7： WF-to-Jira新附件的指示（任務和問題）**

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**案例7：WF-to-Jira新附件（任務和問題）**&#x200B;範本。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。
1. 在第一個模組中，開始新增webhook。
1. 在「連線」欄位中，選取使用系統整合憑證的Workfront連線。
1. 在&#x200B;**記錄型別**&#x200B;欄位中，選取`??`。
1. 在&#x200B;**狀態**&#x200B;欄位中，選取`New state`。
1. 使用&#x200B;**And**&#x200B;選項，透過下列操作設定篩選器：

   | 欄位 | 運算子 | 價值 |
   |---|---|---|
   | （在檔案上建立。） |  |  |
   | assignedToID | 等於 | 輸入系統整合使用者的Workfront ID |
   | projectID | 等於 | 輸入您希望webhook觀看的一或多個專案的ID。 |

1. 在第二個模組中，設定下列變數。

   | 變數名稱 | 變數值 |
   |---|---|
   | defaultJiraReporterID | 這是當Jira中不存在建立者使用者時，預設使用者的ID。 您可以按一下使用者的設定檔，並檢查瀏覽器的URL，以找到此使用者ID。 範例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 您要連線之Jira帳戶的基底URL。 |
   | wfBaseURL | 您連線的Workfront帳戶基底URL。 |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取使用系統整合認證的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取使用系統整合認證的Jira連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。


+++



### 案例8：WF對Jira移除附件（任務和問題）

+++**展開以檢視設定案例8：WF-to-Jira移除附件（任務和問題）**&#x200B;的說明

1. 按一下左側導覽面板中的&#x200B;**範本**&#x200B;索引標籤![範本圖示](assets/templates-icon.png)。
1. 使用畫面左上角附近的搜尋列來搜尋範本。 您可以依範本名稱或包含的應用程式來搜尋。
1. 按一下&#x200B;**案例8：WF-to-Jira移除附件（任務和問題）**&#x200B;範本。

   範本的檢視隨即開啟，顯示資訊和資料流程的動畫。
1. 在第一個模組中，開始新增webhook。
1. 在「連線」欄位中，選取使用系統整合憑證的Workfront連線。
1. 在&#x200B;**記錄型別**&#x200B;欄位中，選取`??`。
1. 在&#x200B;**狀態**&#x200B;欄位中，選取`New state`。
1. 使用&#x200B;**And**&#x200B;選項，透過下列操作設定篩選器：

   | 欄位 | 運算子 | 價值 |
   |---|---|---|
   | （在檔案上刪除） |  |  |
   | assignedToID | 等於 | 輸入系統整合使用者的Workfront ID |
   | projectID | 等於 | 輸入您希望webhook觀看的一或多個專案的ID。 |

1. 在第二個模組中，設定下列變數。

   | 變數名稱 | 變數值 |
   |---|---|
   | defaultJiraReporterID | 這是當Jira中不存在建立者使用者時，預設使用者的ID。 您可以按一下使用者的設定檔，並檢查瀏覽器的URL，以找到此使用者ID。 範例：`https://myjira.atlassian.net/jira/people/<JiraUserID>` |
   | JiraBaseURL | 您要連線之Jira帳戶的基底URL。 |
   | wfBaseURL | 您連線的Workfront帳戶基底URL。 |

1. 啟用&#x200B;**排除此連線所做的更新**&#x200B;選項。
1. 按一下[儲存]&#x200B;**&#x200B;**&#x200B;儲存webhook，然後按一下[確定]&#x200B;**儲存觸發程式模組。**
1. 在&#x200B;**每個** Workfront模組的「連線」欄位中，選取使用系統整合認證的Workfront連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。
1. 在&#x200B;**每個** Jira模組的「連線」欄位中，選取使用系統整合認證的Jira連線，然後按一下&#x200B;**確定**&#x200B;以儲存模組。


+++


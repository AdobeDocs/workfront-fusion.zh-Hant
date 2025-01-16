---
title: gitlab模組
description: 除了Adobe Workfront授權，Adobe Workfront Fusion還需要Adobe Workfront Fusion授權。
author: Becky
feature: Workfront Fusion
exl-id: fabbadce-5669-4363-834e-6d7428520f62
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '3554'
ht-degree: 0%

---

# [!UICONTROL GitLab]模組

除了Adobe Workfront授權，Adobe Workfront Fusion還需要Adobe Workfront Fusion授權。

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!UICONTROL GitLab]的工作流程，並將其連線至多個協力廠商應用程式和服務。

>[!NOTE]
>
>本文期望讀者對API檔案及一般[!DNL GitLab]功能有一定的瞭解。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
  <td> <p>[!UICONTROL Pro] 或更高</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 將[!DNL GitLab]連線至[!DNL Workfront Fusion] {#connect-gitlab-to-workfront-fusion}

1. 在任何[!DNL Workfront Fusion] [!DNL Gitlab]模組中，按一下連線欄位旁的&#x200B;**[!UICONTROL Add]**。
1. 設定下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Connection name]</td> 
      <td> <p>輸入連線的名稱。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL [!DNL GitLab] URL</td> 
      <td>輸入[!DNL GitLab]執行個體的URL。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Access Token]</td> 
      <td><p>輸入您的[!UICONTROL Private Token]或[!UICONTROL Personal Access Token]。</p><p>如需有關在[!DNL GitLab]中尋找或建立個人存取權杖的資訊，請參閱[!DNL GitLab]檔案中<a href="https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html">個人存取權杖</a>中的「建立個人存取權杖」。</p></td> 
     </tr> 
    </tbody> 
   </table>


1. 按一下&#x200B;**[!UICONTROL Continue]**。
1. 按一下&#x200B;**[!UICONTROL Authorize]**&#x200B;以建立連線並返回模組。

## [!DNL GitLab]模組及其欄位

當您設定[!DNL GitLab]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL GitLab]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 觸發器

+++**[!UICONTROL Watch build status]**

此即時觸發模組會在組建狀態變更時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視建置狀態變更的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commit/MR/issue/snippet comments]**

此即時觸發模組會在認可、合併請求、問題或程式碼片段上產生評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook觀看其註解的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch commits (pushes)]**

此即時觸發模組會在認可推送至存放庫時啟動案例。 此模組不會在推送標籤時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視認可專案的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issue comment]**

此即時觸發模組會在對問題發表評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望Webhook觀看問題註解的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch issues]**

此[!UICONTROL instant trigger]模組在建立問題或更新、關閉或重新開啟現有問題時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視問題的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge requests]**

發生下列其中一種情況時，此立即觸發模組就會啟動案例：

* 已建立新的合併請求
* 現有合併請求已更新、合併或關閉
* 在來源分支中新增認可


<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視合併請求的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch merge request comments]**

此立即觸發模組會在合併要求上產生評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視合併請求註解的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch pipeline status]**

此即時觸發模組會在管道狀態變更時啟動方案。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視管道狀態變更的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch projects]**

此排程觸發模組在新增專案時啟動案例，已驗證的使用者為其中一員。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL GitLab]帳戶連線到[!DNL Workfront] Fusion的說明，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">將[!DNL GitLab]連線到[!DNL Workfront] Fusion</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">最大結果</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中監視的最大記錄數量。</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository branches]**

此排程觸發模組會在新分支新增至存放庫時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL GitLab]帳戶連線到[!DNL Workfront] Fusion的說明，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">將[!DNL GitLab]連線到[!DNL Workfront] Fusion</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">最大結果</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中監視的最大記錄數量。</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch repository tags]**

此即時觸發模組會在存放庫中建立或刪除標籤時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視標籤的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch snippet comments]**

此即時觸發模組會在程式碼片段上產生新評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook觀看其註解的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Watch todos]**

此排程觸發模組會在新增待辦事項時啟動案例。 若未套用任何篩選器，則會在新增新的待辦事項時執行觸發器。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得dos清單](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos)。

+++

+++**[!UICONTROL Watch wiki page]**

此即時觸發模組會在建立或編輯Wiki頁面時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列內容： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望Webhook觀看Wiki頁面的專案</li></ul></li><li>按一下<b>[!UICONTROL Save]</b>儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

### 動作

+++**[!UICONTROL Accept merge request]**

此動作模組會將提交的變更與給定的合併請求合併。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[接受合併要求](https://docs.gitlab.com/ee/api/merge_requests.html#accept-mr)。

+++

+++**[!UICONTROL Cancel a build]**

此動作模組會取消專案的單一建置。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL GitLab]帳戶連線到[!DNL Workfront] Fusion的說明，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">將[!DNL GitLab]連線到[!DNL Workfront] Fusion</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>選取或對應包含您要取消之組建的專案。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td>選取或對應您要取消的組建。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge commit message]</td> 
   <td> 輸入或對應合併的認可訊息。
    </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Should remove source branch]</td> 
   <td>選擇合併完成時是否要移除來源分支。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL Merge when build succeeds]</td> 
   <td>選擇是否在建置完成後立即合併合併合併請求。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL SHA]</td> 
   <td>如果存在，則此SHA必須符合來源分支的HEAD。 如果不相符，合併就會失敗。</td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL Cancel a pipeline's builds]**

此動作模組會取消單一管道的建置。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取消管道的工作](https://docs.gitlab.com/ee/api/pipelines.html#cancel-a-pipelines-jobs)。

+++

+++**[!UICONTROL Cancel merge when pipeline succeeds]**

如果合併請求設為管道成功時合併，此動作模組會取消該動作。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[管道成功時取消合併](https://docs.gitlab.com/ee/api/merge_requests.html)。

+++

+++**[!UICONTROL Cherry pick a commit]**

此動作模組會挑選對指定分支的認可。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[Cherry pick a commit](https://docs.gitlab.com/ee/api/commits.html#cherry-pick-a-commit)。

+++

+++**[!UICONTROL Create a new label]**

此動作模組會為指定的存放庫建立新標籤。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立新標籤](https://docs.gitlab.com/ee/api/labels.html#create-a-new-label)。

+++

+++**[!UICONTROL Create a new pipeline]**

此動作模組會為指定專案建立新的管道。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立新管道](https://docs.gitlab.com/ee/api/pipelines.html#create-a-new-pipeline)。

+++

+++**[!UICONTROL Create a new release]**

此動作模組將發行說明新增至現有的Git標籤。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立版本](https://docs.gitlab.com/ee/api/releases/#create-a-release)。

+++

+++**[!UICONTROL Create a new tag]**

此動作模組會在存放庫中建立新標籤，指向提供的參照。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立新標籤](https://docs.gitlab.com/ee/api/tags.html#create-a-new-tag)。

+++

+++**[!UICONTROL Create a todo]**

此動作模組會針對所選問題為目前使用者建立待辦事項。 目前的使用者是由用於此模組之連線上的認證所識別的使用者。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立待辦事項](https://docs.gitlab.com/ee/api/issues.html#create-a-todo)。

+++

+++**[!UICONTROL Create a todo on a merge request]**

此動作模組會為所選合併請求上的目前使用者建立待辦事項。 目前的使用者是由用於此模組之連線上的認證所識別的使用者。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立待辦事項](https://docs.gitlab.com/ee/api/merge_requests.html#create-a-todo)。

+++

+++**[!UICONTROL Create merge request]**

此動作模組會在專案上建立新的合併請求。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[建立合併要求](https://docs.gitlab.com/ee/api/merge_requests.html#create-mr)。

+++

+++**[!UICONTROL Create new file in repository]**

此動作模組會在選取的存放庫中建立新檔案。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[在存放庫中建立新檔案](https://docs.gitlab.com/ee/api/repository_files.html#create-new-file-in-repository)。

+++

+++**[!UICONTROL Create new issue note]**

此動作模組會為單一專案問題建立問題備註。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[建立新的問題備註](https://docs.gitlab.com/ee/api/notes.html#create-new-issue-note)。

+++

+++**[!UICONTROL Create new merge request note]**

此動作模組會為單一合併請求建立附註。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立新的合併要求備註](https://docs.gitlab.com/ee/api/notes.html#create-new-merge-request-note)。

+++

+++**[!UICONTROL Create a new milestone]**

此動作模組會為專案建立新的里程碑。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立新的里程碑](https://docs.gitlab.com/ee/api/milestones.html#create-new-milestone)。

+++

+++**[!UICONTROL Create new snippet note]**

此動作模組會為單一程式碼片段建立新的附註。 程式碼片段附註是使用者可在程式碼片段中張貼的註解。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立新的程式碼片段備註](https://docs.gitlab.com/ee/api/notes.html#create-new-snippet-note)。

+++

+++**[!UICONTROL Create repository branch]**

此動作模組會建立單一存放庫分支。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立存放庫分支](https://docs.gitlab.com/ee/api/branches.html#create-repository-branch)。

+++

+++**[!UICONTROL Create build variable]**

此動作模組會建立新的組建變數。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[建立變數](https://docs.gitlab.com/ee/api/project_level_variables.html#create-variable)。

+++

+++**[!UICONTROL Delete a merge request]**

此動作模組僅適用於管理員和專案所有者。 它會刪除有問題的合併請求

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[刪除合併要求](https://docs.gitlab.com/ee/api/merge_requests.html#delete-a-merge-request)。

+++

+++**[!UICONTROL Delete existing file in repository]**

此動作模組會從存放庫刪除現有檔案。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[刪除儲存庫中的現有檔案](https://docs.gitlab.com/ee/api/repository_files.html#delete-existing-file-in-repository)。

+++

+++**[!UICONTROL Delete repository branch]**

此動作模組會從存放庫刪除分支。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[刪除存放庫分支](https://docs.gitlab.com/ee/api/branches.html#delete-repository-branch)。

+++

+++**[!UICONTROL Edit issue]**

此動作模組會更新現有的專案問題。 此呼叫也用於將問題標示為已關閉。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[編輯問題](https://docs.gitlab.com/ee/api/issues.html#edit-issue)。

+++

+++**[!UICONTROL Edit Milestone]**
此動作模組會更新現有的專案里程碑。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[編輯里程碑](https://docs.gitlab.com/ee/api/milestones.html#edit-milestone)。

+++

+++**[!UICONTROL Erase a build]**

此動作模組會清除專案的建置（移除工作成品和工作記錄）。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[清除工作](https://docs.gitlab.com/ee/api/jobs.html#erase-a-job)。

+++

+++**[!UICONTROL Get a list of todos]**

此搜尋模組會擷取待辦事項清單。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得dos清單](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos)。

+++

+++**[!UICONTROL Get a single build]**

此動作模組會擷取專案的單一工作。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得單一工作](https://docs.gitlab.com/ee/api/jobs.html#get-a-single-job)。

+++

+++**[!UICONTROL Get a single repository tag]**

此動作模組會擷取由其名稱所決定的特定存放庫標籤。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得單一存放庫標籤](https://docs.gitlab.com/ee/api/tags.html#get-a-single-repository-tag)。

+++

+++**[!UICONTROL Get a specific deployment]**

此動作模組會擷取特定部署。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得特定部署](https://docs.gitlab.com/ee/api/deployments.html#get-a-specific-deployment)。

+++

+++**[!UICONTROL Get all issues assigned to a single milestone]**

此搜尋模組會擷取指派給單一專案里程碑的所有問題。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得指派給單一里程碑的所有問題](https://docs.gitlab.com/ee/api/milestones.html#get-all-issues-assigned-to-a-single-milestone)。

+++

+++**[!UICONTROL Get file from repository]**

此動作模組會擷取存放庫中檔案的相關資訊，例如名稱、大小或內容。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[從儲存庫](https://docs.gitlab.com/ee/api/repository_files.html#get-file-from-repository)取得檔案。

+++

+++**[!UICONTROL Get project users]**

此搜尋模組會擷取專案的使用者。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得專案使用者](https://docs.gitlab.com/ee/api/projects.html#get-project-users)。

+++

+++**[!UICONTROL Get a single issue]**

此動作模組會擷取問題詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>若要建立新連線，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab]到Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project]</td> 
   <td> <p>選取包含您要擷取詳細資訊之問題的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Issue ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊的問題名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Get single issue note]**

此動作模組會擷取特定專案問題的單一附註。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得單一問題備註](https://docs.gitlab.com/ee/api/notes.html#get-single-issue-note)。

+++

+++**[!UICONTROL Get single merge request]**

此動作模組會擷取單一合併請求的相關資訊。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得單一合併要求](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr)。

+++

+++**[!UICONTROL Get single merge request changes]**

此搜尋模組會擷取合併請求的相關資訊，包括其檔案和變更。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得單一合併要求變更](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-changes)。

+++

+++**[!UICONTROL Get single merge request commits]**

此動作模組會擷取合併要求認可清單。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得單一合併要求認可](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-commits)。

+++

+++**[!UICONTROL Get single merge request note]**

此動作模組會針對給定的合併請求傳回單一附註。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得單一合併要求備註](https://docs.gitlab.com/ee/api/notes.html#get-single-merge-request-note)。

+++

+++**[!UICONTROL Get a Milestone]**

此動作模組會擷取里程碑詳細資訊。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得單一里程碑](https://docs.gitlab.com/ee/api/milestones.html#get-single-milestone)。

+++

+++**[!UICONTROL Get single project]**

此動作模組會擷取專案詳細資料。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得單一專案](https://docs.gitlab.com/ee/api/projects.html#get-single-project)。

+++

+++**[!UICONTROL Get single repository branch]**

此動作模組會擷取存放庫分支詳細資訊。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得單一存放庫分支](https://docs.gitlab.com/ee/api/branches.html#get-single-repository-branch)。

+++

+++**[!UICONTROL Get snippet note]**

此模組會擷取指定程式碼片段的單一附註。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得單一代碼片段備註](https://docs.gitlab.com/ee/api/notes.html#get-single-snippet-note)。

+++

+++**[!UICONTROL Get the comments of a commit]**

此搜尋模組會擷取專案中認可專案的註解。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[取得認可](https://docs.gitlab.com/ee/api/commits.html#get-the-comments-of-a-commit)的註解。

+++

+++**[!UICONTROL Get the diff of a commit]**

此動作模組取得專案中認可的diff。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[取得認可](https://docs.gitlab.com/ee/api/commits.html#get-the-diff-of-a-commit)的差異。

+++

+++**[!UICONTROL Keep artifacts]**

防止在設定到期時刪除成品。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[保留成品](https://docs.gitlab.com/ee/api/job_artifacts.html#keep-artifacts)。

+++

+++**[!UICONTROL List all merge request notes]**

此搜尋模組會擷取單一合併請求的所有附註清單。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[列出所有合併請求備註](https://docs.gitlab.com/ee/api/notes.html#list-all-merge-request-notes)。

+++

+++**[!UICONTROL List all snippet notes]**

此模組會取得單一程式碼片段的所有附註清單。 程式碼片段附註是使用者可在程式碼片段中張貼的註解。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[??](https://docs.gitlab.com/ee/api/notes.html#list-all-snippet-notes)。

+++

+++**[!UICONTROL List commit builds]**

此搜尋模組會傳回專案中特定認可的組建清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>若要建立新連線，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab]到Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>選取包含您要列出建置之認可的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Scope]</td> 
   <td> 若要將搜尋限製為以特定狀態建置，請選取狀態。 將此欄位保留空白會傳回認可的所有組建。  </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL List issues]**

此搜尋模組會傳回指定之篩選設定發生的所有問題。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[清單問題](https://docs.gitlab.com/ee/api/issues.html#list-issues)。

+++

+++**[!UICONTROL List Issues That Close on Merge]**

此搜尋模組會擷取將透過合併所提供的合併請求而關閉的所有問題。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出將在合併](https://docs.gitlab.com/ee/api/merge_requests.html#list-issues-that-will-close-on-merge)時關閉的問題。

+++

+++**[!UICONTROL List Labels]**

此搜尋模組會擷取專案中的所有標籤。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[清單標籤](https://docs.gitlab.com/ee/api/labels.html#list-labels)。

+++

+++**[!UICONTROL List merge requests]**

此搜尋模組會依篩選設定擷取所有合併請求。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[列出合併請求](https://docs.gitlab.com/ee/api/merge_requests.html#list-merge-requests)。

+++

+++**[!UICONTROL List Owned Projects]**

此搜尋模組會擷取已驗證身分的使用者設定為擁有者的專案。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出使用者專案](https://docs.gitlab.com/ee/api/projects.html#list-all-projects)。

+++

+++**[!UICONTROL List project builds]**

此搜尋模組會擷取專案中的組建清單。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出專案工作](https://docs.gitlab.com/ee/api/jobs.html#list-project-jobs)。

+++

+++**[!UICONTROL List project deployments]**

此搜尋模組會擷取專案中的部署清單。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出專案部署](https://docs.gitlab.com/ee/api/deployments.html#list-project-deployments)。

+++

+++**[!UICONTROL List project issue notes]**

此搜尋模組會擷取單一問題所有附註的清單。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[列出專案問題說明](https://docs.gitlab.com/ee/api/notes.html#list-project-issue-notes)。

+++

+++**[!UICONTROL List project issues]**

此搜尋模組傳回指定專案中的所有問題。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出專案問題](https://docs.gitlab.com/ee/api/issues.html#list-project-issues)。

+++

+++**[!UICONTROL List project milestones]**

此搜尋模組會擷取專案中的所有里程碑。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出專案里程碑](https://docs.gitlab.com/ee/api/milestones.html#list-project-milestones)。

+++

+++**[!UICONTROL List project pipelines]**

此搜尋模組會擷取專案的所有管道。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出專案管道](https://docs.gitlab.com/ee/api/pipelines.html#list-project-pipelines)。

+++

+++**[!UICONTROL List project repository tags]**

此搜尋模組會從專案擷取存放庫標籤的清單，並依名稱以相反的字母順序排序。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出專案存放庫標籤](https://docs.gitlab.com/ee/api/tags.html#list-project-repository-tags)。

+++

+++**[!UICONTROL List project variables]**

此搜尋模組會擷取專案的變數清單。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出專案變數](https://docs.gitlab.com/ee/api/project_level_variables.html#list-project-variables)。

+++

+++**[!UICONTROL List projects]**

此搜尋模組會擷取已驗證身分的使用者所屬的所有專案。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出所有專案](https://docs.gitlab.com/ee/api/projects.html#list-all-projects)。

+++

+++**[!UICONTROL List repository branches]**

此模組會依搜尋字詞搜尋存放庫分支。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出存放庫分支](https://docs.gitlab.com/ee/api/branches.html#list-repository-branches)。

+++

+++**[!UICONTROL List repository commits]**

此搜尋模組會擷取專案中的存放庫認可清單。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出存放庫認可](https://docs.gitlab.com/ee/api/commits.html#list-repository-commits)。

+++

+++**[!UICONTROL List repository contributors]**

此搜尋模組會擷取存放庫貢獻者清單。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[貢獻者](https://docs.gitlab.com/ee/api/repositories.html#contributors)。

+++

+++**[!UICONTROL List repository tree]**

此搜尋模組會擷取專案中的存放庫檔案和目錄清單。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[列出存放庫樹狀結構](https://docs.gitlab.com/ee/api/repositories.html#list-repository-tree)。

+++

+++**[!UICONTROL Mark a todo as done]**

此動作模組會將ID為目前使用者提供的單一擱置中待辦事項標示為已完成。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[將待辦事項標示為完成](https://docs.gitlab.com/ee/api/todos.html#mark-a-todo-as-done)。

+++

+++**[!UICONTROL Modify existing issue note]**

修改問題的現有附註。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[修改現有問題備註](https://docs.gitlab.com/ee/api/notes.html#modify-existing-issue-note)。

+++

+++**[!UICONTROL Modify existing merge request note]**

修改合併請求的現有附註。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[修改現有的合併要求備註](https://docs.gitlab.com/ee/api/notes.html#modify-existing-merge-request-note)。

+++

+++**[!UICONTROL Modify existing snippet note]**

此動作模組會修改程式碼片段的現有附註。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[修改現有的程式碼片段備註](https://docs.gitlab.com/ee/api/notes.html#modify-existing-snippet-note)。

+++

+++**[!UICONTROL New issue]**

此動作模組會建立新專案問題。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[新問題](https://www.integromat.com/en/help/app/gitlab)。

+++

+++**[!UICONTROL Play a build]**

此動作模組會觸發啟動工作的手動動作。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[播放工作](https://docs.gitlab.com/ee/api/jobs.html#play-a-job)。

+++

+++**[!UICONTROL Post comment to commit]**

此動作模組會新增註解至認可。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[張貼註解以認可](https://docs.gitlab.com/ee/api/commits.html#post-comment-to-commit)。

+++

+++**[!UICONTROL Remove variable]**

此動作模組會移除專案的變數。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[移除變數](https://docs.gitlab.com/ee/api/project_level_variables.html#remove-variable)。

+++

+++**[!UICONTROL Retry a build]**

此動作模組會重試認可中的單一組建。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>若要建立新連線，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL Connect [!DNL GitLab]到Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p>選取包含您要重試之組建的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Build ID]</td> 
   <td> 選取要重試的組建。 </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL Retry Failed Jobs in a Pipeline]**

此動作模組會重試管道中失敗的組建。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[在管道](https://docs.gitlab.com/ee/api/pipelines.html#retry-jobs-in-a-pipeline)中重試工作。

+++

+++**[!UICONTROL Get a Variable]**

此模組會擷取專案特定變數的詳細資訊。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[顯示變數詳細資料](https://docs.gitlab.com/ee/api/project_level_variables.html#show-variable-details)。

+++

+++**[!UICONTROL Update a release]**

此動作模組會更新版本。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[更新版本](https://docs.gitlab.com/ee/api/releases/#update-a-release)。

+++

+++**[!UICONTROL Update merge request]**

此動作模組會更新現有的合併請求。 您可以變更目標分支、標題，或甚至關閉MR。

如需欄位的相關資訊，請參閱[!DNL GitLab]檔案中的[更新合併要求](https://docs.gitlab.com/ee/api/merge_requests.html#update-mr)。

+++

+++**[!UICONTROL Update a Variable]**

此動作模組會更新專案的變數。

如需有關欄位的資訊，請參閱[!DNL GitLab]檔案中的[更新變數](https://docs.gitlab.com/ee/api/project_level_variables.html#update-variable)。

+++

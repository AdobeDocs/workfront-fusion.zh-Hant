---
title: gitlab模組
description: 除了Adobe Workfront授權，Adobe Workfront Fusion還需要Adobe Workfront Fusion授權。
author: Becky
feature: Workfront Fusion
exl-id: fabbadce-5669-4363-834e-6d7428520f62
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '4122'
ht-degree: 1%

---

# [!UICONTROL GitLab]模組

除了Adobe Workfront授權，Adobe Workfront Fusion還需要Adobe Workfront Fusion授權。

在Adobe Workfront Fusion案例中，您可以自動執行使用[!UICONTROL GitLab]的工作流程，並將其連線到多個協力廠商應用程式和服務。

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
   <td role="rowheader">Adobe Workfront計畫*</td>
  <td> <p>[!UICONTROL Pro]或更高版本</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權*</td>
   <td> <p>[!UICONTROL 計畫]，[!UICONTROL 工作]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前授權需求：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版授權要求：[!UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] Adobe Workfront計畫，貴組織必須購買Adobe Workfront Fusion以及Adobe Workfront，才能使用本文所述的功能。 Workfront Fusion包含在[!UICONTROL Ultimate] Workfront計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買Adobe Workfront Fusion和Adobe Workfront，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請聯絡您的Workfront管理員。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 將[!DNL GitLab]連線至Workfront Fusion {#connect-gitlab-to-workfront-fusion}

1. 在任何Workfront Fusion [!DNL Gitlab]模組中，按一下連線欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 設定下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL 連線名稱]</td> 
      <td> <p>輸入連線的名稱。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL [!DNL GitLab]網址]</td> 
      <td>輸入[!DNL GitLab]執行個體的URL。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 存取權杖]</td> 
      <td><p>輸入您的[!UICONTROL 私密權杖]或[!UICONTROL 個人存取權杖]。</p><p>如需有關在[!DNL GitLab]中尋找或建立個人存取權杖的資訊，請參閱<a href="https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html">檔案中</a>個人存取權杖[!DNL GitLab]中的「建立個人存取權杖」。</p></td> 
     </tr> 
    </tbody> 
   </table>


1. 按一下&#x200B;**[!UICONTROL 繼續]**。
1. 按一下&#x200B;**[!UICONTROL 授權]**&#x200B;以建立連線並返回模組。

## [!DNL GitLab]模組及其欄位

當您設定[!DNL GitLab]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL GitLab]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 觸發程序

+++**[!UICONTROL 觀看組建狀態]**

此即時觸發模組會在組建狀態變更時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視建置狀態變更的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看認可/MR/問題/代碼片段評論]**

此即時觸發模組會在認可、合併請求、問題或程式碼片段上產生評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook觀看其註解的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看認可（推送）]**

此即時觸發模組會在認可推送至存放庫時啟動案例。 此模組不會在推送標籤時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視認可專案的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看問題註解]**

此即時觸發模組會在對問題發表評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望Webhook觀看問題註解的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看問題]**

此[!UICONTROL 即時觸發器]模組會在問題建立或現有問題更新、關閉或重新開啟時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視問題的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看合併要求]**

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
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視合併請求的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看合併要求註解]**

此立即觸發模組會在合併要求上產生評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視合併請求註解的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看管道狀態]**

此即時觸發模組會在管道狀態變更時啟動方案。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視管道狀態變更的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看專案]**

此排程觸發模組在新增專案時啟動案例，已驗證的使用者為其中一員。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL GitLab]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">將[!DNL GitLab]連線到Workfront Fusion</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">最大結果</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中監視的最大記錄數量。</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 監視存放庫分支]**

此排程觸發模組會在新分支新增至存放庫時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL GitLab]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">將[!DNL GitLab]連線到Workfront Fusion</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">最大結果</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中監視的最大記錄數量。</p> </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 監視存放庫標籤]**

此即時觸發模組會在存放庫中建立或刪除標籤時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook監視標籤的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看程式碼片段註解]**

此即時觸發模組會在程式碼片段上產生新評論時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望webhook觀看其註解的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 觀看待辦事項]**

此排程觸發模組會在新增待辦事項時啟動案例。 若未套用任何篩選器，則會在新增新的待辦事項時執行觸發器。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos)取得dos清單[!DNL GitLab]。

+++

+++**[!UICONTROL 觀看Wiki頁面]**

此即時觸發模組會在建立或編輯Wiki頁面時啟動案例。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Webhook]</td> 
   <td><p>選取您要用於此觸發器的webhook，或新增新的webhook。 </p><p>若要新增webhook， <ol><li>按一下[!UICONTROL webhook]欄位旁的<b>[!UICONTROL Add]</b>。</li><li>輸入下列： <ul><li>webhook的名稱</li><li>您要用於此webhook的連線</li><li>您希望Webhook觀看Wiki頁面的專案</li></ul></li><li>按一下<b>[!UICONTROL 儲存]</b>以儲存webhook並返回模組。 </td> 
   </tr> 
   </tbody> 
</table>

+++

### 動作

+++**[!UICONTROL 接受合併要求]**

此動作模組會將提交的變更與給定的合併請求合併。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#accept-mr)接受合併要求[!DNL GitLab]。

+++

+++**[!UICONTROL 取消組建]**

此動作模組會取消專案的單一建置。

<table style="table-layout:auto"> 
   <col> 
   <col> 
   <tbody> 
   <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將您的[!DNL GitLab]帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion-connect-gitlab-to-workfront-fusion" class="MCXref xref">將[!DNL GitLab]連線到Workfront Fusion</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 專案ID]</td> 
   <td> <p>選取或對應包含您要取消之組建的專案。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 組建ID]</td> 
   <td>選取或對應您要取消的組建。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 合併認可訊息]</td> 
   <td> 輸入或對應合併的認可訊息。
    </td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 應移除來源分支]</td> 
   <td>選擇合併完成時是否要移除來源分支。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">建置成功時進行[!UICONTROL 合併]</td> 
   <td>選擇是否在建置完成後立即合併合併合併請求。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL SHA]</td> 
   <td>如果存在，則此SHA必須符合來源分支的HEAD。 如果不相符，合併就會失敗。</td> 
   </tr> 
   </tbody> 
</table>

+++

+++**[!UICONTROL 取消管道的組建]**

此動作模組會取消單一管道的建置。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/pipelines.html#cancel-a-pipelines-jobs)取消管道的工作[!DNL GitLab]。

+++

+++**[!UICONTROL 管道成功時取消合併]**

如果合併請求設為管道成功時合併，此動作模組會取消該動作。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html)管道成功時取消合併[!DNL GitLab]。

+++

+++**[!UICONTROL 挑選認可]**

此動作模組會挑選對指定分支的認可。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/commits.html#cherry-pick-a-commit)Cherry pick a commit[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新標籤]**

此動作模組會為指定的存放庫建立新標籤。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/labels.html#create-a-new-label)建立新標籤[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新管道]**

此動作模組會為指定專案建立新的管道。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/pipelines.html#create-a-new-pipeline)建立新管道[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新版本]**

此動作模組將發行說明新增至現有的Git標籤。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/releases/#create-a-release)建立版本[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新的標記]**

此動作模組會在存放庫中建立新標籤，指向提供的參照。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/tags.html#create-a-new-tag)建立新標籤[!DNL GitLab]。

+++

+++**[!UICONTROL 建立待辦事項]**

此動作模組會針對所選問題為目前使用者建立待辦事項。 目前的使用者是由用於此模組之連線上的認證所識別的使用者。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/issues.html#create-a-todo)建立待辦事項[!DNL GitLab]。

+++

+++**[!UICONTROL 在合併要求上建立待辦事項]**

此動作模組會為所選合併請求上的目前使用者建立待辦事項。 目前的使用者是由用於此模組之連線上的認證所識別的使用者。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#create-a-todo)建立待辦事項[!DNL GitLab]。

+++

+++**[!UICONTROL 建立合併要求]**

此動作模組會在專案上建立新的合併請求。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#create-mr)建立合併要求[!DNL GitLab]。

+++

+++**[!UICONTROL 在存放庫中建立新檔案]**

此動作模組會在選取的存放庫中建立新檔案。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/repository_files.html#create-new-file-in-repository)在存放庫中建立新檔案[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新的問題備註]**

此動作模組會為單一專案問題建立問題備註。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#create-new-issue-note)建立新的問題備註[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新的合併要求備註]**

此動作模組會為單一合併請求建立附註。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#create-new-merge-request-note)建立新的合併要求備註[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新的里程碑]**

此動作模組會為專案建立新的里程碑。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/milestones.html#create-new-milestone)建立新的里程碑[!DNL GitLab]。

+++

+++**[!UICONTROL 建立新的程式碼片段備註]**

此動作模組會為單一程式碼片段建立新的附註。 程式碼片段附註是使用者可在程式碼片段中張貼的註解。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#create-new-snippet-note)建立新的程式碼片段備註[!DNL GitLab]。

+++

+++**[!UICONTROL 建立存放庫分支]**

此動作模組會建立單一存放庫分支。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/branches.html#create-repository-branch)建立存放庫分支[!DNL GitLab]。

+++

+++**[!UICONTROL 建立組建變數]**

此動作模組會建立新的組建變數。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/project_level_variables.html#create-variable)建立變數[!DNL GitLab]。

+++

+++**[!UICONTROL 刪除合併要求]**

此動作模組僅適用於管理員和專案所有者。 它會刪除有問題的合併請求

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#delete-a-merge-request)刪除合併要求[!DNL GitLab]。

+++

+++**[!UICONTROL 刪除儲存庫中的現有檔案]**

此動作模組會從存放庫刪除現有檔案。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/repository_files.html#delete-existing-file-in-repository)刪除儲存庫中的現有檔案[!DNL GitLab]。

+++

+++**[!UICONTROL 刪除存放庫分支]**

此動作模組會從存放庫刪除分支。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/branches.html#delete-repository-branch)刪除存放庫分支[!DNL GitLab]。

+++

+++**[!UICONTROL 編輯問題]**

此動作模組會更新現有的專案問題。 此呼叫也用於將問題標示為已關閉。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/issues.html#edit-issue)編輯問題[!DNL GitLab]。

+++

+++**[!UICONTROL 編輯里程碑]**
此動作模組會更新現有的專案里程碑。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/milestones.html#edit-milestone)編輯里程碑[!DNL GitLab]。

+++

+++**[!UICONTROL 清除組建]**

此動作模組會清除專案的建置（移除工作成品和工作記錄）。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/jobs.html#erase-a-job)清除工作[!DNL GitLab]。

+++

+++**[!UICONTROL 取得待辦事項清單]**

此搜尋模組會擷取待辦事項清單。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/todos.html#get-a-list-of-todos)取得dos清單[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一組建]**

此動作模組會擷取專案的單一工作。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/jobs.html#get-a-single-job)取得單一工作[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一存放庫標籤]**

此動作模組會擷取由其名稱所決定的特定存放庫標籤。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/tags.html#get-a-single-repository-tag)取得單一存放庫標籤[!DNL GitLab]。

+++

+++**[!UICONTROL 取得特定部署]**

此動作模組會擷取特定部署。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/deployments.html#get-a-specific-deployment)取得特定部署[!DNL GitLab]。

+++

+++**[!UICONTROL 將所有問題指派給單一里程碑]**

此搜尋模組會擷取指派給單一專案里程碑的所有問題。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/milestones.html#get-all-issues-assigned-to-a-single-milestone)取得指派給單一里程碑的所有問題[!DNL GitLab]。

+++

+++**[!UICONTROL 從存放庫取得檔案]**

此動作模組會擷取存放庫中檔案的相關資訊，例如名稱、大小或內容。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/repository_files.html#get-file-from-repository)從儲存庫[!DNL GitLab]取得檔案。

+++

+++**[!UICONTROL 取得專案使用者]**

此搜尋模組會擷取專案的使用者。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/projects.html#get-project-users)取得專案使用者[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一問題]**

此動作模組會擷取問題詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>若要建立新連線，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL 連線[!DNL GitLab]至Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案]</td> 
   <td> <p>選取包含您要擷取詳細資訊之問題的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 問題ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊的問題名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL 取得單一問題備註]**

此動作模組會擷取特定專案問題的單一附註。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#get-single-issue-note)取得單一問題備註[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一合併要求]**

此動作模組會擷取單一合併請求的相關資訊。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr)取得單一合併要求[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一合併要求變更]**

此搜尋模組會擷取合併請求的相關資訊，包括其檔案和變更。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-changes)取得單一合併要求變更[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一合併要求認可]**

此動作模組會擷取合併要求認可清單。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#get-single-mr-commits)取得單一合併要求認可[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一合併要求備註]**

此動作模組會針對給定的合併請求傳回單一附註。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#get-single-merge-request-note)取得單一合併要求備註[!DNL GitLab]。

+++

+++**[!UICONTROL 取得里程碑]**

此動作模組會擷取里程碑詳細資訊。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/milestones.html#get-single-milestone)取得單一里程碑[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一專案]**

此動作模組會擷取專案詳細資料。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/projects.html#get-single-project)取得單一專案[!DNL GitLab]。

+++

+++**[!UICONTROL 取得單一存放庫分支]**

此動作模組會擷取存放庫分支詳細資訊。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/branches.html#get-single-repository-branch)取得單一存放庫分支[!DNL GitLab]。

+++

+++**[!UICONTROL 取得程式碼片段備註]**

此模組會擷取指定程式碼片段的單一附註。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#get-single-snippet-note)取得單一代碼片段備註[!DNL GitLab]。

+++

+++**[!UICONTROL 取得認可註解]**

此搜尋模組會擷取專案中認可專案的註解。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/commits.html#get-the-comments-of-a-commit)取得認可[!DNL GitLab]的註解。

+++

+++**[!UICONTROL 取得認可差異]**

此動作模組取得專案中認可的diff。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/commits.html#get-the-diff-of-a-commit)取得認可[!DNL GitLab]的差異。

+++

+++**[!UICONTROL 保留成品]**

防止在設定到期時刪除成品。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/job_artifacts.html#keep-artifacts)保留成品[!DNL GitLab]。

+++

+++**[!UICONTROL 列出所有合併請求備註]**

此搜尋模組會擷取單一合併請求的所有附註清單。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#list-all-merge-request-notes)列出所有合併請求備註[!DNL GitLab]。

+++

+++**[!UICONTROL 列出所有程式碼片段備註]**

此模組會取得單一程式碼片段的所有附註清單。 程式碼片段附註是使用者可在程式碼片段中張貼的註解。

如需有關欄位的資訊，請參閱[🔗檔案中的](https://docs.gitlab.com/ee/api/notes.html#list-all-snippet-notes) [!DNL GitLab]。

+++

+++**[!UICONTROL 列出認可組建]**

此搜尋模組會傳回專案中特定認可的組建清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>若要建立新連線，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL 連線[!DNL GitLab]至Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案ID]</td> 
   <td> <p>選取包含您要列出建置之認可的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 範圍]</td> 
   <td> 若要將搜尋限製為以特定狀態建置，請選取狀態。 將此欄位保留空白會傳回認可的所有組建。  </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL 清單問題]**

此搜尋模組會傳回指定之篩選設定發生的所有問題。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/issues.html#list-issues)清單問題[!DNL GitLab]。

+++

+++**[!UICONTROL 列出合併時關閉的問題]**

此搜尋模組會擷取將透過合併所提供的合併請求而關閉的所有問題。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#list-issues-that-will-close-on-merge)列出將在合併[!DNL GitLab]時關閉的問題。

+++

+++**[!UICONTROL 清單標籤]**

此搜尋模組會擷取專案中的所有標籤。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/labels.html#list-labels)清單標籤[!DNL GitLab]。

+++

+++**[!UICONTROL 列出合併請求]**

此搜尋模組會依篩選設定擷取所有合併請求。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#list-merge-requests)列出合併請求[!DNL GitLab]。

+++

+++**[!UICONTROL 列出擁有的專案]**

此搜尋模組會擷取已驗證身分的使用者設定為擁有者的專案。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/projects.html#list-all-projects)列出使用者專案[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案組建]**

此搜尋模組會擷取專案中的組建清單。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/jobs.html#list-project-jobs)列出專案工作[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案部署]**

此搜尋模組會擷取專案中的部署清單。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/deployments.html#list-project-deployments)列出專案部署[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案問題注意事項]**

此搜尋模組會擷取單一問題所有附註的清單。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#list-project-issue-notes)列出專案問題說明[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案問題]**

此搜尋模組傳回指定專案中的所有問題。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/issues.html#list-project-issues)列出專案問題[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案里程碑]**

此搜尋模組會擷取專案中的所有里程碑。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/milestones.html#list-project-milestones)列出專案里程碑[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案管道]**

此搜尋模組會擷取專案的所有管道。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/pipelines.html#list-project-pipelines)列出專案管道[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案存放庫標籤]**

此搜尋模組會從專案擷取存放庫標籤的清單，並依名稱以相反的字母順序排序。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/tags.html#list-project-repository-tags)列出專案存放庫標籤[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案變數]**

此搜尋模組會擷取專案的變數清單。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/project_level_variables.html#list-project-variables)列出專案變數[!DNL GitLab]。

+++

+++**[!UICONTROL 列出專案]**

此搜尋模組會擷取已驗證身分的使用者所屬的所有專案。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/projects.html#list-all-projects)列出所有專案[!DNL GitLab]。

+++

+++**[!UICONTROL 列出存放庫分支]**

此模組會依搜尋字詞搜尋存放庫分支。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/branches.html#list-repository-branches)列出存放庫分支[!DNL GitLab]。

+++

+++**[!UICONTROL 列出存放庫認可]**

此搜尋模組會擷取專案中的存放庫認可清單。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/commits.html#list-repository-commits)列出存放庫認可[!DNL GitLab]。

+++

+++**[!UICONTROL 列出存放庫參與者]**

此搜尋模組會擷取存放庫貢獻者清單。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/repositories.html#contributors)貢獻者[!DNL GitLab]。

+++

+++**[!UICONTROL 列出存放庫樹狀結構]**

此搜尋模組會擷取專案中的存放庫檔案和目錄清單。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/repositories.html#list-repository-tree)列出存放庫樹狀結構[!DNL GitLab]。

+++

+++**[!UICONTROL 將待辦事項標示為完成]**

此動作模組會將ID為目前使用者提供的單一擱置中待辦事項標示為已完成。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/todos.html#mark-a-todo-as-done)將待辦事項標示為完成[!DNL GitLab]。

+++

+++**[!UICONTROL 修改現有問題備註]**

修改問題的現有附註。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#modify-existing-issue-note)修改現有問題備註[!DNL GitLab]。

+++

+++**[!UICONTROL 修改現有的合併要求備註]**

修改合併請求的現有附註。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#modify-existing-merge-request-note)修改現有的合併要求備註[!DNL GitLab]。

+++

+++**[!UICONTROL 修改現有的程式碼片段備註]**

此動作模組會修改程式碼片段的現有附註。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/notes.html#modify-existing-snippet-note)修改現有的程式碼片段備註[!DNL GitLab]。

+++

+++**[!UICONTROL 新問題]**

此動作模組會建立新專案問題。

如需有關欄位的資訊，請參閱[檔案中的](https://www.integromat.com/en/help/app/gitlab)新問題[!DNL GitLab]。

+++

+++**[!UICONTROL 播放組建]**

此動作模組會觸發啟動工作的手動動作。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/jobs.html#play-a-job)播放工作[!DNL GitLab]。

+++

+++**[!UICONTROL 張貼要提交的註解]**

此動作模組會新增註解至認可。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/commits.html#post-comment-to-commit)張貼註解以認可[!DNL GitLab]。

+++

+++**[!UICONTROL 移除變數]**

此動作模組會移除專案的變數。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/project_level_variables.html#remove-variable)移除變數[!DNL GitLab]。

+++

+++**[!UICONTROL 重試組建]**

此動作模組會重試認可中的單一組建。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>若要建立新連線，請參閱本文中的<a href="#connect-gitlab-to-workfront-fusion" class="MCXref xref">[!UICONTROL 連線[!DNL GitLab]至Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案ID]</td> 
   <td> <p>選取包含您要重試之組建的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 組建ID]</td> 
   <td> 選取要重試的組建。 </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL 重試管道中失敗的工作]**

此動作模組會重試管道中失敗的組建。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/pipelines.html#retry-jobs-in-a-pipeline)在管道[!DNL GitLab]中重試工作。

+++

+++**[!UICONTROL 取得變數]**

此模組會擷取專案特定變數的詳細資訊。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/project_level_variables.html#show-variable-details)顯示變數詳細資料[!DNL GitLab]。

+++

+++**[!UICONTROL 更新版本]**

此動作模組會更新版本。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/releases/#update-a-release)更新版本[!DNL GitLab]。

+++

+++**[!UICONTROL 更新合併要求]**

此動作模組會更新現有的合併請求。 您可以變更目標分支、標題，或甚至關閉MR。

如需欄位的相關資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/merge_requests.html#update-mr)更新合併要求[!DNL GitLab]。

+++

+++**[!UICONTROL 更新變數]**

此動作模組會更新專案的變數。

如需有關欄位的資訊，請參閱[檔案中的](https://docs.gitlab.com/ee/api/project_level_variables.html#update-variable)更新變數[!DNL GitLab]。

+++

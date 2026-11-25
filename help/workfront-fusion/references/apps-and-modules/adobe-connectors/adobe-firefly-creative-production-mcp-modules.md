---
title: Adobe Firefly Creative生產MCP模組
description: 透過Adobe Firefly Creative生產MCP模組，您可以從Workfront Fusion案例傳送自然語言提示，讓AI模型使用您選取的Firefly Creative生產工具。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: ee2719b9b3452b9203f2d0f4a550c87ff8a3b433
workflow-type: tm+mt
source-wordcount: '2087'
ht-degree: 5%
---
# Adobe Firefly Creative生產MCP模組

使用Adobe Workfront Fusion中的Adobe Firefly Creative生產MCP聯結器，透過Firefly Creative生產工具處理自然語言請求。

聯結器會探索透過已連線的Firefly模型內容通訊協定(MCP)伺服器可用的工具。 您可以選擇模組可用於請求的工具。 根據Adobe帳戶可用的工具以及您在模組中選取的工具，請求可能會執行下列動作：

* 探索工作流程和動作。
* 撰寫及驗證工作流程。
* 提交執行並檢查其進度。
* 擷取輸出URL。
* 當伺服器的工具支援時，儲存可編輯的工作流程草稿。

此聯結器會鎖定Firefly Creative生產環境。 它不是Firefly主機板聯結器，也不是每個Creative Cloud應用程式的一般聯結器。

如需有關Fusion案例中MCP的詳細資訊，請參閱[將AI提示加入您的案例](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md)。

<!-- BECKY CHECK ME: The request asks you to confirm the customer-facing name of the connector, its beta or release status, its availability, its access requirements, and screenshots with the product and engineering owners before publication. Confirm each item, and add a beta note at the top of the article if the connector is released as a beta. -->

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</p>
   <p>您也必須擁有Adobe Firefly Creative生產存取權，如本文中<a href="#prerequisites">必要條件</a>所述。</p>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 先決條件

使用Adobe Firefly Creative Production MCP模組之前，您必須具備下列條件：

* 在啟用此聯結器的環境中存取Adobe Workfront Fusion。
* 具有Firefly Creative生產存取權和許可權的Adobe帳戶，是請求作業所需的許可權。
* 執行工作流程所需的任何業績或權益。
* 可能是您的Fusion管理員設定的Adobe Managed AI存取，或是您在模組的進階設定中選取的支援LLM金鑰。

Firefly授權和LLM憑證有不同的用途。 選取LLM金鑰不會授與Firefly工具的存取權。

## 將Adobe Firefly Creative Production MCP連線至Workfront Fusion

1. 新增&#x200B;**[!UICONTROL Adobe Firefly Creative Production MCP]** > **[!UICONTROL 處理使用者提示]**&#x200B;至您的情境。
1. 按一下&#x200B;**[!UICONTROL 連線]**&#x200B;欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 在&#x200B;**[!UICONTROL 建立連線]**&#x200B;視窗中，填寫下列欄位：

   <table style="table-layout:auto">
    <col>
    <col>
    <tbody>
      <tr>
        <td role="rowheader">連線名稱</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">環境</td>
        <td>
          <p>無論您是連線到生產或非生產環境，Select皆然。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">類型</td>
        <td>
          <p>選取要連接至服務帳戶或者個人帳戶。</p>
        </td>
      </tr>
    </tbody>
   </table>

1. 按一下「**[!UICONTROL 繼續]**」。
1. 請依照授權流程，使用適當的Adobe帳戶登入，然後授權存取。
1. 返回模組並檢閱為連線載入的工具。

Workfront Fusion會處理OAuth使用者端註冊和權杖管理。 您沒有輸入存取權杖、使用者端ID、使用者端密碼或API金鑰。 您的管理員必須先完成此流程的設定，然後才能連線。

如果授權失敗或您沒有看到預期的工具，請與管理員確認您的存取權以及您環境的設定。

<!-- BECKY CHECK ME: The Environment and Type fields are described the same way as in the Adobe Fusion MCP connection. The screenshot shows only the selected values (Production and Service account). Confirm the available options for each field, and whether a personal account is supported. -->

## Adobe Firefly Creative生產MCP模組及其欄位

### 處理使用者提示

此動作模組會使用您許可的選定LLM和Firefly Creative生產工具處理您的提示。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL LLM機碼] <i>（選擇性，進階）</i></td> 
   <td> <p>將此欄位留空將使用您的Fusion管理員設定的Adobe Managed AI。 若要改用您自己的金鑰，請選取現有的OpenAI、Anthropic或Amazon Basrock金鑰，或按一下<b>[！UICONTROL Add]</b>建立金鑰。</p><p>您的Firefly登入與LLM認證不同。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>模組用於探索和呼叫工具的Adobe Firefly Creative生產連線。 如需指示，請參閱本文中的<a href="#connect-adobe-firefly-creative-production-mcp-to-workfront-fusion" class="MCXref xref">將Adobe Firefly Creative Production MCP連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL唯讀工具] <i>（選擇性）</i></td> 
   <td> <p>Select是伺服器識別為唯讀的工具。 若要選取目前列出的每個工具，請選取<b>Select全部</b>。</p><p>列出的工具數目會顯示在欄位的標籤中。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL寫入/刪除工具] <i>（選擇性）</i></td> 
   <td> <p>Select伺服器未識別為唯讀的工具。 這些操作可以變更資料或執行工作流程。 若要選取目前列出的每個工具，請選取<b>Select全部</b>。</p><p>列出的工具數目會顯示在欄位的標籤中。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL其他工具（未知許可權）] <i>（選擇性）</i></td> 
   <td> <p>Select工具沒有可辨識的唯讀附註。 只有在這些工具可用時，才會顯示此欄位。 啟用這些工具之前，請先檢閱其行為。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL輸入提示]</td> 
   <td> <p>說明您要的工作流程探索、構成或執行。 最大長度為10,000個JavaScript字串單位。 有些字元（包括許多Emoji）會計為兩個單位。</p><p>需要時明確要求執行或發佈。 執行工作流程可能會沖銷銷退折讓。 非同步執行可在執行完成之前傳回批次ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

當您選取&#x200B;**[!UICONTROL 顯示進階設定]**&#x200B;時，**[!UICONTROL LLM索引鍵]**&#x200B;欄位就會顯示。

<!-- BECKY CHECK ME: The screenshot does not show the Other tools (unknown permissions) field, because it appears only when the server returns tools without a read-only annotation. Confirm its label, and confirm the order of the fields. Also confirm that the tool lists are not required. -->

工具清單會因伺服器可用性及您帳戶的存取權而有所不同。 工具數量會顯示在每個選擇器的標籤中。

#### Select此模組可以使用的工具

* 此模組只能使用您選取的工具。
* 如果您將類別保留為空白，模組將不能使用該類別中的工具。
* 如果您將所有類別都保留為空白，則模組將無需任何工具即可處理提示。 它無法存取每個工具。
* **[!UICONTROL Select全部]**&#x200B;會選取目前在該類別中列出的每個工具。 不會自動包含稍後新增的工具。
* 如果選取的工具無法使用或移至其他類別，請再次開啟模組並檢閱您的選取專案。

>[!NOTE]
>
>伺服器的註解有助於分類工具，但不保證許可權。 僅啟用情境所需的工具。

#### 輸出

模組在&#x200B;**[!UICONTROL 資料]**&#x200B;下傳回下列資訊。 您可以在情境中的後續模組中加以對應。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL回應] (<code>data.response</code>)</td> 
   <td> <p>最終文字回應。 其內容取決於提示和工具結果。 不保證是URL或結構化JSON。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL稽核軌跡] (<code>data.auditTrail</code>)</td> 
   <td> <p>有關如何處理提示和工具呼叫的詳細資訊，包括其引數、結果、時間和成功資訊。 根據您組織的資料處理要求處理這些詳細資訊。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL摘要] (<code>data.summary</code>)</td> 
   <td> <p>工具呼叫次數、處理時間及執行狀態。 檢閱摘要以及回應和稽核軌跡，包括任何<code>partial_success</code>結果。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL LLM使用方式] (<code>data.usage</code>)</td> 
   <td> <p>選填。 觀察到LLM回應中的總權杖使用量。 這不是Fusion無法觀察的Firefly伺服器內的提供者帳單、Firefly信用消耗或LLM活動。</p> </td> 
  </tr> 
 </tbody> 
</table>

##### LLM使用狀況欄位

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td><code>status</code></td> 
   <td> <p>下列其中一項：</p><ul><li><code>complete</code>：所有主要Token計數會涵蓋每個觀察到的請求。</li><li><code>partial</code>：缺少部分使用資訊。</li><li><code>unavailable</code>：觀察到請求，但報告沒有可用的使用量。</li><li><code>not_applicable</code>：未觀察到任何LLM要求。</li></ul> </td> 
  </tr> 
  <tr> 
   <td><code>llmRequests</code></td> 
   <td> <p>執行階段觀察到的LLM要求數目。</p> </td> 
  </tr> 
  <tr> 
   <td><code>requestsWithUsage</code></td> 
   <td> <p>觀察到的具有可用Token使用資訊的要求數目。</p> </td> 
  </tr> 
  <tr> 
   <td><code>inputTokens</code>, <code>outputTokens</code>, <code>totalTokens</code></td> 
   <td> <p>總計數。 如果觀察到的任何請求未報告該計數，或沒有觀察到的請求，則每個計數為<code>null</code>。 報告的零值會維持為零。</p> </td> 
  </tr> 
  <tr> 
   <td><code>cacheReadInputTokens</code>, <code>cacheWriteInputTokens</code></td> 
   <td> <p>快取Token的選擇性計數。 如果沒有任何請求報告數字，則會忽略這些欄位。 如果只有部分請求報告了數字，則這些請求為<code>null</code>，如果每個請求都報告一個數字，則為數字。 請勿將這些計數新增至總計。</p> </td> 
  </tr> 
 </tbody> 
</table>

當快取欄位為`null`時，主要使用狀態可以是`complete`。 使用狀態與執行狀態無關。 如果執行階段未提供使用情形資訊，則使用情形集合不存在而非顯示零。

## 模組如何執行

* **部分作業為非同步。** 請求可在輸出可用之前傳回批次ID。 對於較長的作業，請使用個別執行來提交請求，並在稍後檢查其狀態，以及儲存它們之間的批次ID。 請勿依賴只包含此設計URL的回應。
* **錯誤產生模組錯誤。** 授權、驗證及失敗的執行階段處理可能會產生模組錯誤，而非輸出套件組合。 使用Fusion錯誤處理路由。
* **回應未證明成功。** 即使某些作業失敗，模組仍可傳回回應。 在您依賴回應之前，請先檢閱摘要、稽核軌跡及工具結果。
* **輸出URL不是下載的檔案。** 聯結器會傳回文字和工具結果，而非二進位檔案。 若要將檔案放入Fusion，請新增下載URL的HTTP模組。
* **執行工作流程可以使用積分。** 影像產生和工作流程執行可能會消耗積分。 確認適用於您帳戶的使用和權益。 LLM Token用途不是Firefly帳單或信用報告。
* **提示指示不保證單一執行。** 提示中的指示（例如只提交一個批次）無法保證請求只會處理一次。 控制案例中的重試和重複請求。
* **處理具有限制。** 除了案例的執行限制之外，處理作業還有工具、反複和輸出長度限制。 請勿假設模組會不受限制地輪詢。

## 範例

### 探索工作流程而不執行工作流程

Select提供您探索工作流程所需的唯讀工具，然後輸入以下提示：

```text
List the Firefly Creative Production workflows available to my account.
Summarize what each workflow does and what inputs it requires.
Do not create, modify, submit, or publish anything.
```

### 要求一個影像

Select是您撰寫或選擇工作流程、驗證、提交、檢查進度以及擷取輸出所需的工具。 刀具名稱和可用性可能有所不同。 然後輸入如下所示的提示：

```text
Generate one photorealistic image of a black dog on a sunny windowsill.
Submit one generation batch only and check that same batch for completion
within the available execution limits. Do not publish or submit another
generation.

On success, return only the actual downloadable image URL as plain text,
without Markdown, quotes, labels, or explanation. Never invent a URL or
return a workflow or status-page URL instead.

If the run fails or times out, report the failure honestly instead of
returning a URL. Do not generate another image to recover.
```

### 從Workfront任務更新產生影像

在此範例中，以`/firefly `開頭的工作更新會觸發影像產生。 Fusion會下載結果、將其上傳到任務，並新增完成更新。

此案例使用下列流程： Workfront任務更新>命令篩選>讀取任務> Firefly MCP > HTTP下載> Workfront檔案上傳>完成更新。

1. 將&#x200B;**[!UICONTROL Workfront]** > **[!UICONTROL 觀看活動]**&#x200B;新增至情境。 設定&#x200B;**[!UICONTROL Note]**&#x200B;記錄型別、**[!UICONTROL 新增狀態]**&#x200B;事件和&#x200B;**[!UICONTROL 僅新增記錄]**&#x200B;的記錄。
1. 新增要求`newState.noteText`的開頭為`/firefly `且`newState.taskID`為非空白的篩選器。
1. 使用`newState.taskID`新增讀取工作的模組。
1. 新增&#x200B;**[!UICONTROL Adobe Firefly Creative生產MCP]** > **[!UICONTROL 處理使用者提示]**&#x200B;模組。 傳遞請求和Firefly所需的任何工作內容。 將對應文字視為請求的內容，而非變更案例規則的許可權。
1. 檢查Firefly結果。 只有在產生成功且回應是可下載影像的有效允許URL時，才繼續。
1. 新增下載檔案的HTTP模組。 請勿將您的Workfront認證傳送至資產主機。 驗證預期的主機、內容型別和大小。
1. 新增模組以使用原始`newState.taskID`將下載的檔案名稱和二進位資料上傳至工作。
1. 上傳成功後，新增模組以在任務上建立完成更新。 不要以`/firefly`開始更新，因為篩選器會符合它。

例如，使用者將以下更新新增至任務：

```text
/firefly Generate one photorealistic image of a black dog on a sunny windowsill.
```

接著，請求者便可在任務的「檔案」區域中檢閱已上傳的草稿。 人應檢閱影像後再發佈任何內容。

若是生產使用，請使用原始備註的ID來保留每個請求，並搭配可同時執行的重複保護。 儲存已提交批次的ID，以便重試或逾時時恢復狀態檢查而非提交另一個層代。

<!-- BECKY CHECK ME: The example scenario is from the request's draft. Confirm the module names and field labels (Watch Events, Note, New state, New Record Only, and the task, document upload, and update modules) against the current Workfront connector, and add a screenshot of the scenario if one is available. -->

## 疑難排解

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">工作流程仍在執行中</td> 
   <td> <p>部分創意操作為非同步。 若是較長的工作，請在一次執行中提交請求，並在稍後執行中檢查狀態。 在執行之間儲存批次ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">模組報告錯誤</td> 
   <td> <p>授權、驗證及失敗的執行階段處理可能會產生模組錯誤。 將Fusion錯誤處理路由新增到您的情境。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">模組傳回回應，但部分作業失敗</td> 
   <td> <p>檢閱摘要、稽核軌跡及工具結果。 僅回應不會顯示影像已產生或已上傳。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">有URL，但Fusion中沒有檔案</td> 
   <td> <p>聯結器不會下載檔案。 新增下載URL的HTTP模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">選取的工具無法使用</td> 
   <td> <p>開啟模組、重新整理可用工具，並更新您的選擇。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">工作流程需要執行超過一個模組的時間</td> 
   <td> <p>除了案例的執行限制之外，處理作業還有工具、反複和輸出長度限制。 在執行之間分割工作，並儲存批次識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

---
title: Adobe CX Enterprise Coworker模組
description: 在Adobe Workfront Fusion中使用Adobe CX Enterprise Coworker聯結器傳送自然語言提示給同事，並在案例中使用其回應。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 6efe84af0487893a3c33ba2bf6e3db5200f25446
workflow-type: tm+mt
source-wordcount: '1974'
ht-degree: 6%
---
# Adobe CX Enterprise Coworker模組

在Adobe Workfront Fusion中使用Adobe CX Enterprise Coworker聯結器傳送自然語言提示給同事，並在案例中使用其回應。 同事會解譯您的請求，並可使用您帳戶可用的工具來執行工作。

聯結器提供兩個模組：

* **[!UICONTROL 執行提示]**&#x200B;會開始新的要求，預設會等待結果。
* **[!UICONTROL 取得執行狀態]**&#x200B;會檢查您先前啟動的要求。

## 存取權要求

<!-- BECKY CHECK ME: This table is copied from other Fusion connector articles. The source material does not list access requirements, but says you need an Adobe account that has access to Coworker. Confirm the requirements and whether Coworker needs its own license or entitlement. -->

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
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 先決條件

您必須擁有可存取Adobe CX Enterprise Coworker的Adobe帳戶。

## 將Adobe CX Enterprise Coworker連線至Workfront Fusion

使用Adobe帳戶登入，該帳戶可存取Co-worker以及您的請求所需的任何服務。

若要建立連線：

1. 在Adobe Fusion MCP模組中，按一下&#x200B;**連線**&#x200B;欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 填寫下列欄位：

   <table style="table-layout:auto">
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
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
          <p>選取您要連線到生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">類型</td>
        <td>
          <p>選取要連接至服務帳戶或者個人帳戶。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">用戶端 ID</td>
        <td>
          <p>輸入或對應此連線的選擇性覆寫。 否則，請使用此帳戶型別的平台管理的clientId。 為專用的Co-worker帳戶註冊顯示的Fusion回呼URL。</p>
        </td>
      <tr>
        <td role="rowheader">用戶端密碼</td>
        <td>
          <p>輸入或對應此連線的選擇性覆寫。 否則，請使用此帳戶型別的平台管理的clientSecret。 使用針對已設定的IMS環境發行的認證。</p>
        </td>
    </tbody>
   </table>

1. 按一下「**[!UICONTROL 繼續]**」。

如果您無法登入或使用必要的服務，請連絡管理員。

## Adobe CX Enterprise Coworker模組及其欄位

>[!WARNING]
>
>請勿在提示中包含密碼或其他認證。

### 取得執行狀態

此動作模組會檢查由&#x200B;**[!UICONTROL 執行提示字元]**&#x200B;所啟動之工作的目前狀態。

此模組會檢查任務一次。 它不會啟動新任務或持續檢查，直到任務完成。 如果結果仍在等待中，請稍後再次檢查。

>[!NOTE]
>
>請勿將工作ID轉換為數字、舍入或重新格式化。 如果同事在沒有工作識別碼的情況下立即回應原始提示，您就不需要檢查狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL Include原始結果] <i> （選用，進階）</i></td> 
   <td> <p>此選項預設為關閉。 在輸出中包含完整的同事回應。 回應可能包含敏感資訊。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>選取您在原始<b>[！UICONTROL執行提示]</b>執行中所使用的相同連線。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL任務ID]</td> 
   <td> <p>對應<b>[！UICONTROL傳回的工作識別碼執行提示]</b>。 保留為與傳回完全相同的文字。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 執行提示

此動作模組會傳送指示給同事，例如摘要文字或使用您帳戶可用的工具收集資訊。

每次執行都會傳送提示一次，並開始新的交談。 您不需要選取AI模型或提供單獨的AI提供者金鑰。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>選取您的同事連線。 如需指示，請參閱本文中的<a href="#connect-adobe-cx-coworker-to-workfront-fusion" class="MCXref xref">將Adobe CX Enterprise Coworker連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL使用者提示]</td> 
   <td> <p>輸入您的指示。 您可以使用多行，並對應來自舊模組的資訊。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL等待完成] <i> （選用，進階）</i></td> 
   <td> <p>此選項預設為開啟。 如果您希望模組等待工作完成或需要注意，請啟用此選項。 將其關閉以立即傳回初始結果。</p><p>如需詳細資訊，請參閱本文中的<a href="#wait-for-completion">等待完成</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Include原始結果] <i> （選用，進階）</i></td> 
   <td> <p>此選項預設為關閉。 如果您希望模組在輸出中包含完整的Co-worker回應，請啟用此選項。 回應可能包含敏感資訊。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
> 除非您出於特定目的需要完整回應，否則建議將&#x200B;**[!UICONTROL 包含原始結果]**&#x200B;保留為關閉。 原始結果可能包含敏感資訊，不一定是每個動作的完整記錄。 在儲存、共用或傳遞至其他服務之前，請先檢閱原始結果所包含的內容。

#### 等待完成

當&#x200B;**[!UICONTROL 等待完成]**&#x200B;開啟時，模組會在五秒後檢查工作。 如果工作仍在擱置中，模組會再等待五秒鐘，才會再次檢查。 每次檢查都需要一段時間才能收到回應。 檢查狀態時不會再次傳送提示。

當工作完成、失敗、被取消或拒絕，或需要您的輸入或授權時，等待會停止。 如果Co-worker提供立即的答案，模組會傳回答案，而不進行進一步的檢查。

當&#x200B;**[!UICONTROL 等待完成]**&#x200B;關閉時，模組會傳回第一個結果，而不會等待工作完成。 檢查&#x200B;**[!UICONTROL 狀態]**、**[!UICONTROL 已完成]**，以及&#x200B;**[!UICONTROL 需要注意]**，以決定下一步要做什麼。 當第一個結果到達時，任務可能已經完成。

等待受Fusion的模組逾時限制。 如果模組逾時或停止，Co-worker可能會繼續運作。 在這種情況下，您可能無法收到輸出或任務ID。

若需要更長的時間，請關閉等待並儲存初始&#x200B;**[!UICONTROL 工作識別碼]**，以便您稍後可以檢查工作。 逾時後不要再自動執行提示。 第一個請求可能已在進行中，重複它可能會重複變更。


## 模組輸出

兩個模組在完成時都會傳回下列資訊，而不會發生錯誤。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL任務ID]</td> 
   <td> <p>識別任務。 當Co-worker提供立即答案而不建立任務時，這是空的。 使用此值搭配<b>[！UICONTROL Get Execution Status]</b>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL內容ID]</td> 
   <td> <p>識別交談。 這不是繼續交談的輸入。</p><p>如需詳細資訊，請參閱本文中的<a href="#use-previous-answers">使用先前的答案</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 狀態]</td> 
   <td> <p>目前的工作狀態。 請參閱本文中的<a href="#task-states" class="MCXref xref">工作狀態</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL已完成]</td> 
   <td> <p>工作完成或同事提供立即回應時為True。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL需要注意]</td> 
   <td> <p>當同事需要輸入或授權時為True。</p><p>如需詳細資訊，請參閱本文中的<a href="#requests-that-need-attention">需要注意的要求</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL最終助理文字]</td> 
   <td> <p>任務完成時的最終答案。 當任務擱置或需要注意時，這是空的。 完成的回應也可能沒有回應文字。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL文字成品（可能包含中繼文字）]</td> 
   <td> <p>工作期間傳回的文字。 每個專案都可以包含成品ID、名稱和文字。 這些專案不一定是最終答案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL原始結果（選擇加入）]</td> 
   <td> <p>完整回應。 只有在<b>[！UICONTROL Include原始結果]</b>開啟時才包含此專案。</p> </td> 
  </tr> 
 </tbody> 
</table>

使用&#x200B;**[!UICONTROL 最終助理文字]**&#x200B;來取得答案，而非合併所有文字成品。 成品可包括進度說明或其他中繼文字。

### 需要注意的要求

同事可能需要更多資訊或授權，才能繼續。 發生此情況時，**[!UICONTROL 需要注意]**&#x200B;為true，而&#x200B;**[!UICONTROL 已完成]**&#x200B;為false。 將結果遞送給個人，而不是將其視為已完成的工作。

這些模組無法代表您回答後續問題或核准動作。 **[!UICONTROL 取得執行狀態]**&#x200B;可以檢查工作狀態是否已變更，但是它無法解析輸入或授權的要求。

### 使用先前的答案

每&#x200B;**[!UICONTROL 執行提示]**&#x200B;就會開始新的交談。 若要參考之前的答案，請將相關問題和答案以文字的形式加入新提示中。 這會提供同事的內容，但不會繼續先前的交談。

**[!UICONTROL 內容識別碼]**&#x200B;識別與結果相關聯的交談。 您無法提供它給這些模組以繼續交談。

>[!IMPORTANT]
>
>**[!UICONTROL 已完成]**&#x200B;無法保證要求的商務動作成功。 例如，「同事」可能會說明所需的工具無法使用，以此結束。 檢閱答案並驗證任何必要的結果，然後再執行下一個動作。

### 任務狀態

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"><code>submitted</code>, <code>working</code></td> 
   <td> <p>任務擱置中。 <b>[！UICONTROL已完成]</b>為false。 <b>[！UICONTROL執行提示]</b>在等待時繼續等待。 否則，請儲存任務ID並稍後檢視。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>completed</code></td> 
   <td> <p><b>[！UICONTROL已完成]</b>為true。 檢閱<b>[！UICONTROL最終助理文字]</b>和預期的結果。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>input-required</code>, <code>auth-required</code></td> 
   <td> <p>任務需要注意。 <b>[！UICONTROL已完成]</b>為false且<b>[！UICONTROL需要注意]</b>為true。 等候停止。 路由結果以供人力檢閱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"><code>failed</code>, <code>canceled</code>, <code>rejected</code></td> 
   <td> <p>模組回報錯誤而非正常結果。</p> </td> 
  </tr> 
 </tbody> 
</table>

即使模組未傳回任何錯誤，擱置的結果或需要注意的結果也不會成功完成。

## 範例

### 摘要更新

1. 新增&#x200B;**[!UICONTROL 執行提示]**&#x200B;並選取您的連線。
1. 在&#x200B;**[!UICONTROL 使用者提示]**&#x200B;欄位中輸入下列內容：

   ```text
   Summarize the following project update in three bullet points.
   Use only the supplied text; do not call tools or change any records.
   
   The planning workshop is complete. Two dependencies need confirmation.
   The team will review the delivery estimate on Friday.
   ```

1. 保留&#x200B;**[!UICONTROL 等待完成]**&#x200B;開啟，並關閉&#x200B;**[!UICONTROL 包含原始結果]**。
1. 如果&#x200B;**[!UICONTROL 需要注意]**&#x200B;為true，則將結果傳送給人工稽核。 如果&#x200B;**[!UICONTROL 已完成]**&#x200B;為True，請將&#x200B;**[!UICONTROL 最終助理文字]**&#x200B;對應到您的下一個步驟。

AI產生的措辭可能有所不同。 在正確性很重要的地方檢閱結果。

### 稍後再檢查較長的任務

1. 新增&#x200B;**[!UICONTROL 執行提示]**，選取您的連線，然後輸入您的指示。
1. 關閉&#x200B;**[!UICONTROL 等待完成]**。
1. 檢查初始結果。

   * 如果工作完成，則處理結果。
   * 如果任務需要注意，請將結果遞送給檢閱。
   * 如果工作擱置中，請將&#x200B;**[!UICONTROL 工作識別碼]**&#x200B;儲存為文字，並記下您使用的連線。

1. 稍後，使用該連線和工作ID使用&#x200B;**[!UICONTROL 取得執行狀態]**。
1. 如果任務仍在擱置中，請在情境的限制內安排另一次檢查。 完成時處理一次結果，然後分別處理注意事項或錯誤。

不要再執行原始提示以檢查其進度。

## 使用注意事項

* 同事可以使用工具並執行您帳戶允許的動作，包括對記錄的變更。 使用受信任的提示和具有適當存取權的帳戶。
* 這些模組不提供限制個別工具的方法。 「不要變更任何專案」之類的指示說明了您的意圖，但並非強制的唯讀模式。
* 可用的工具和技能因帳戶而異。 聯結器不提供技能選擇器或保證特定動作，例如建立歷程或更新專案。 請勿假設需要核准的請求會在無人參與的情況下完成。
* 聯結器會啟動並檢查同事請求。 它不會監視專案變更或自動儲存其他應用程式的回答。 視需要將適當的觸發器、儲存和後續模組新增到情境中。
* AI產生的答案可能不完整或不準確。 使用重要結果進行變更或決定前，請先驗證這些結果。
* 聯結器不會自動重試失敗的請求。 確定您情境的錯誤處理不會重複出現結果不確定的提示。

## 疑難排解

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">缺少必填欄位</td> 
   <td> <p>選取連線並輸入必要的提示或工作ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">登入失敗或存取遭拒</td> 
   <td> <p>再次登入，然後檢查您的Adobe帳戶是否有權存取同事和所需的服務。 如有需要，請聯絡管理員。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">找不到任務</td> 
   <td> <p>檢查工作ID是否未變更，以及您是否使用原始連線。 新任務可能不會立即顯示。 稍後再檢查狀態，而不是再次傳送提示。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">狀態檢查失敗</td> 
   <td> <p>如果錯誤包含接受的工作ID，請使用<b>[！UICONTROL Get Execution Status]</b>調查該工作。 請勿自動重新啟動提示。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">執行提示逾時或遺失回應</td> 
   <td> <p>即使您沒有收到其ID，任務也可能已經開始。 在您重複請求之前進行調查，以避免重複工作。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Fusion等候逾時</td> 
   <td> <p>同事可能仍在工作。 如果您有任務的ID，則檢查任務。 對於未來的長時間工作，請先關閉等待功能並儲存初始ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">同事或所需服務無法使用</td> 
   <td> <p>與您的管理員共用顯示的錯誤，不含認證或敏感結果內容。</p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- BECKY CHECK ME: Confirm the exact module and field labels in the UI (Run a Prompt, Get Execution Status, User prompt, Wait for completion, Include raw result, Task ID, and the output item names). Also confirm that the module is listed under "Adobe CX Enterprise Coworker" in the app picker. -->

---
title: Adobe Marketo Engage MCP模組
description: Adobe Marketo Engage MCP模組可讓您將自然語言提示傳送至Adobe Marketo Engage的MCP （模型內容通訊協定）伺服器。
author: Becky
feature: Workfront Fusion
exl-id: 3f29ab35-7a90-4afb-a283-4faaacec5b15
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
    internal-label: APIs
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
  - id: e14a7f57-c82c-4874-a495-5d036cbbdc3d
    internal-label: Resource management
subfeature_v2:
  - id: b70a979b-965d-47a9-a360-e7ec2a19b8c1
    internal-label: Digital content and documents
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 9e08c421a53c7ca499715fa8e32be6c10fbde1d9
workflow-type: tm+mt
source-wordcount: '1579'
ht-degree: 9%
---
# Adobe Marketo Engage MCP模組

Adobe Marketo Engage MCP模組可讓您使用AI模型來解譯請求，並呼叫Adobe Marketo Engage自己的工具來完成請求，藉此將自然語言提示傳送至Marketo的MCP （模型內容通訊協定）伺服器。 不像傳統Marketo聯結器，每個模組都會執行一個固定動作，例如「建立銷售機會」，此聯結器具有一個模組，可接受簡單英文版的開放式指示，並讓AI決定需要哪些Marketo操作來滿足它。

此聯結器專門用於Marketo Engage自己的MCP伺服器

若要連線到其他應用程式的MCP，請參閱[將AI提示新增到您的情境](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md)。

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

* 您必須擁有Adobe Marketo Engage帳戶和有效的Marketo例項。

## 將Adobe Marketo Engage MCP連線至Workfront Fusion {#connect-adobe-marketo-engage-mcp-to-workfront-fusion}

您可以直接從Marketo MCP模組內建立與Adobe Marketo Engage執行個體的連線。

1. 在Adobe Marketo Engage MCP模組中，按一下&#x200B;**連線**&#x200B;欄位旁的&#x200B;**新增**。
1. 填寫下列欄位：

   <table style="table-layout:auto">
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
    </col>
    <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
    </col>
    <tbody>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>
          <p>選取您要連線到生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 類型]</td>
        <td>
          <p>選取要連接至服務帳戶或者個人帳戶。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>
          <p>輸入您在Marketo LaunchPoint中建立的Marketo REST API服務使用者端ID。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>
          <p>輸入您在Marketo LaunchPoint中建立之Marketo REST API服務的使用者端密碼。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Munchkin ID]</td>
        <td>
          <p>輸入您的Marketo執行個體的Munchkin ID （例如，'123-ABC-456'）。 Munchkin ID會顯示在Marketo的<b>管理員→Munchkin</b>下。</p>
        </td>
      </tr>
    </tbody>
   </table>

1. 按一下&#x200B;**繼續**&#x200B;以建立連線並返回模組。

>[!IMPORTANT]
>
> * 使用具有情境所需最低角色和許可權的專用API專用Marketo使用者，而不是重複使用管理員帳戶。
> * 建立連線不會驗證認證。 Fusion會在沒有測試呼叫的情況下儲存連線，因此即使值錯誤或輸入錯誤，連線看起來也可以成功建立。 如果認證不正確，當模組首次嘗試連線Marketo或工具清單無法載入時，通常會在稍後顯示失敗。

## 模組：「處理使用者提示」

這是聯結器提供的唯一模組。 案例透過提供以下內容來使用它：

1. **連線** — 上面建立的Marketo連線。
2. **輸入您的提示** — 指示，以純英文顯示（例如，「尋找上週新增至春季網路研討會清單的每個潛在客戶，並告訴我哪些潛在客戶未設定公司名稱」）。
3. **工具** （選擇性） — 如下所述。 只有在選取連線後，這些欄位才會顯示。
4. **LLM金鑰** （選擇性，進階） — 如下所述。

它會將AI的最終答案以文字傳回，加上產生該答案時發生的完整稽核軌跡。

## Adobe Marketo Engage MCP模組及其欄位

### 處理使用者提示

此動作模組會傳送純英文指示至Adobe Marketo Engage的MCP伺服器並傳回AI的回應。

<table style="table-layout:auto"> 
 <col/>
 <col/>
 <tbody>
  <tr>
   <td role="rowheader">LLM索引鍵<i>（選擇性，進階）</i></td>
   <td><p>依預設，此模組會使用Adobe自己的AI服務處理您的提示，而您不需要選取索引鍵。</p><p>若要改用您自己的AI提供者，請選取現有的LLM金鑰，或按一下<b>新增</b>並輸入下列資訊來建立新金鑰：</p>
    <ul>
     <li><b>金鑰名稱</b>：輸入新金鑰的名稱。</li>
     <li><b>LLM</b>：選取與此索引鍵關聯的大型語言模型。 支援的提供者包括OpenAI、Anthropic Claude和Amazon Bedrock。</li>
     <li><b>Key</b>：輸入或對應您所選提供者的API金鑰。</li>
     <li><b>模型</b>：選取金鑰將使用的LLM模型。</li>
     <li><b>其他欄位</b>：請為您的LLM需要的任何其他欄位輸入值。</li>
    </ul>
   </td>
  </tr>
  <tr>
   <td role="rowheader">連線</td>
   <td><p>如需有關將Marketo帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-marketo-engage-mcp-to-workfront-fusion" class="MCXref xref">將Adobe Marketo Engage MCP連線到Workfront Fusion</a>。</p></td>
  </tr>
  <tr>
   <td role="rowheader">使用者提示</td>
   <td><p>以純英文輸入或對應您希望AI執行的指示。</p><p>範例： <i>尋找過去7天內新增至春季網路研討會清單的所有銷售機會，並總結哪些產業最常見。</i></p></td>
  </tr>
 </tbody>
</table>

### 模組輸出

輸出是包含以下內容的單一束：

* 回應： AI的最終回應，如文字。 您可以將此資料對應至後續模組。
* 稽核軌跡：執行的詳細記錄，包括階段作業ID、原始提示、開始和結束時間、總持續時間、整體狀態、最終回應以及「工具呼叫」清單。 每個工具呼叫專案都會記錄Marketo工具執行的專案、引數、輸出、開始和結束時間及持續時間、是否成功以及在序列中的順序。
* 摘要：相同的回合壓縮為計數：工具呼叫總數、成功呼叫、失敗呼叫、處理時間和狀態。

### AI模型

依預設，模組會自動使用Adobe自己的受管AI服務，不需要輸入金鑰或認證。

您可以改為選取特定的LLM金鑰來使用OpenAI、Anthropic Claude或Amazon Bedrock （如果貴組織擁有具有其中一項的帳戶）。

### 選擇AI允許採取的Marketo動作

選取連線後，模組會詢問Marketo MCP伺服器它提供哪些工具，並以多選清單的形式呈現，每個清單都顯示該模組包含多少工具：

* 唯讀工具：僅會查詢某專案且不會變更任何專案的動作，例如尋找銷售機會、列出促銷活動成員或讀取方案的詳細資訊。
* 撰寫/刪除工具：變更某部分的動作，例如建立或更新銷售機會、將某人新增至清單、啟動促銷活動，或核准或傳送電子郵件。
* 其他工具：第三個清單，只有在Marketo伺服器提供未標示為唯讀或非唯讀的工具時才會顯示。 這些會個別顯示，而非假設為安全或不安全。 如果伺服器標示一切，此清單就不會出現。

如果未選取工具，則AI可使用所有工具。 您可以將清單限製為特定動作。 例如，只選取2個特定的「寫入」動作，而保留「唯讀」狀態，表示AI可以自由查詢任何需要的專案，但只能進行這2種特定型別的變更。 將清單保留為空白表示允許該類別中的所有動作。 限制AI需要主動選擇在該類別中允許的特定動作。 如此一來，您便可確保AI不會針對即時行銷資料採取非預期的破壞性動作，同時仍可讓AI自由收集資訊。

由於清單是從Marketo伺服器即時讀取，因此顯示的確切工具可能會隨著Adobe更新該伺服器而變更。

### 沒有持續的交談記錄

此模組的每次執行都是單一、獨立的執行作業。 AI無法提出後續問題並等待回覆。 相反，它必須做出最佳判斷，並一次性給出完整的最終答案。 如果請求模稜兩可，AI會做出合理的假設，將該假設陳述為其答案的一部分，然後繼續。 它不會停止並要求使用者澄清，因為它沒有辦法在單一執行中接收回覆。

AI也會被指示透過工具呼叫來驗證事實，而不是依賴記憶體，因為Marketo資料在上次執行後可能已變更。

AI只會在提示實際要求寫入、更新或刪除動作時才會進行。 它不會採取未要求的動作，包括啟用或停用行銷活動、建立或刪除銷售線索和清單，以及核准或傳送電子郵件，即使在它正在執行使用者要求的其他操作的相同執行中也是如此。

因為每次執行都是獨立的，所以AI沒有先前自行執行的記憶體。 想要多圈、類似聊天體驗的情境必須將該歷史記錄明確提供為新提示的一部分，例如將上一個問題和答案儲存在Fusion的資料存放區，或在模組之間傳遞，並在新提示開始時將其包含為文字，然後是新問題。 沒有會自動記住先前執行的工作階段或交談ID。

## 提示範例

您可以使用類似以下的提示：

* *列出過去7天內加入「第3季產品上市」計畫的銷售機會，並摘要他們來自哪些產業。*
* *檢查「歡迎系列」智慧行銷活動目前是否有效，並告訴我有多少人參加。*
* *尋找我們定價頁面上使用的表單，並告知我哪些欄位標示為必填。*
* *將具有電子郵件`jane@example.com`的銷售機會新增至「VIP客戶」靜態清單。*
* *「春季電子報」計畫中每封電子郵件的效能摘要。*

<!--

## What a content writer should NOT claim

* Connection form: Do not describe the connection as an OAuth or "sign in with Adobe" flow. It is not one. It is three credential fields that the user copies out of Marketo's LaunchPoint and Munchkin admin pages. Screenshots or steps borrowed from the AEM MCP connector docs would be wrong here.
* Credential validation: Do not imply that the connection form validates the credentials. It saves them without testing them.
* Module scope: This is not a substitute for individual Marketo action modules. It is a single, flexible AI-driven module, not a set of deterministic single-purpose modules.
* Reliability: Results are AI-generated and can occasionally be imperfect, even with every safeguard above in place. This is appropriate for automation where a human is not reviewing every single run in real time, but it is not a guarantee of 100% deterministic behavior the way a traditional Marketo module is. This deserves extra emphasis for Marketo specifically, because a write action here can email real customers or alter real lead records.
* Tool restrictions: The read/write tool split limits what categories of Marketo actions the AI can take. It is not a way to sandbox or limit what the AI is capable of reasoning about or discussing in its answer text.
* Tool naming: Do not name specific Marketo MCP tools or actions unless they are verified against the live tool list. This document intentionally describes capability areas, such as leads, lists, campaigns, programs, emails, forms, snippets, and bulk operations, rather than exact tool names, since the server's exact tool set may evolve.
* API limits: Do not state Marketo API rate limits, quotas, or daily call caps as if this connector defines them. Any such limit comes from the user's own Marketo subscription and REST API allowance; verify with the Marketo team before publishing numbers.

## Reference links used while compiling this

* Adobe Marketo Engage MCP server (developer documentation):
  https://experienceleague.adobe.com/zh-hant/docs/marketo-developer/marketo/mcp-server

  -->

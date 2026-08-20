---
title: Adobe Workfront MCP模組
description: 透過Adobe Workfront MCP模組，您可以傳送純英文提示給Adobe Workfront的MCP伺服器，讓AI模型執行要求。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 71573ee33f852111d4541ee61567a51b137c7df5
workflow-type: tm+mt
source-wordcount: 871
ht-degree: 17%

---

# Adobe Workfront MCP模組

Adobe Workfront MCP聯結器是Adobe Workfront自己的模型內容通訊協定(MCP)伺服器的專用Fusion整合。 不像一個典型的聯結器，每個模組都會執行一個固定動作，這個聯結器具有一個模組，這個模組會接受開放式、純英文的指示，並讓AI模型決定需要哪些Workfront操作才能完成它。

例如，您可以輸入提示「尋找所有進度落後且摘要其狀態的我作用中專案」，而模組會傳回合成答案，而不必將數個「取得」和「篩選」模組鏈結在一起。

您可以限制AI可以執行哪些Workfront動作，以便即使自動情景也可以保證不會執行非預期的破壞性動作。

依預設，此模組使用Adobe Managed AI，其使用`claude-sonnet-5`模型。 您可以使用提供的金鑰和其他認證，將模組設定為使用不同的LLM。

如需有關Fusion案例中MCP的詳細資訊，請參閱[將AI提示加入您的案例](/help/workfront-fusion/create-scenarios/add-modules/add-an-ai-prompt-to-your-scenario.md)。

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 將Adobe Workfront MCP連線至Workfront Fusion

Adobe Workfront MCP聯結器使用OAuth 2.0連線至Workfront。 不像其他Workfront聯結器，沒有手動連線欄位（例如主機、使用者端ID或使用者端密碼）需要填寫。

若要建立連線：

1. 在Adobe Workfront MCP模組中，按一下[連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
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
          <p>輸入此連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>選取您要連線到生產或非生產環境。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 類型]</td>
        <td>選取要連接至服務帳戶或者個人帳戶。</td>
      </tr>
    </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

   若您未登入 Workfront，系統會將您導向至登入畫面。 登入並核准存取權。

您會重新導向回Workfront Fusion，而新的連線可在模組中使用。

>[!NOTE]
>
>第一次使用時，連線會自動向Workfront的MCP伺服器註冊自己，並會在您建立的每個後續連線中重複使用該註冊。

## Adobe Workfront MCP模組及其欄位

### 處理使用者提示

此動作模組會使用您指定的語言模型，針對Workfront的MCP伺服器處理純英文提示，並傳回AI的答案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody>

<tr> 
   <td>LLM索引鍵<i>（選擇性，進階）</i></td> 
   <td> <p>依預設，此模組會使用Adobe Managed AI處理您的提示，而您不需要選取索引鍵。</p> <p>若要改用您自己的AI提供者，請選取現有的LLM金鑰，或按一下<b>新增</b>並輸入下列資訊來建立新金鑰：</p>
     <ul>
       <li><b>金鑰名稱</b>：輸入新金鑰的名稱。</li>
       <li><b>LLM</b>：選取與此索引鍵關聯的大型語言模型。 支援的提供者包括OpenAI、Anthropic和Amazon Bedrock。</li>
       <li><b>Key</b>：輸入或對應您所選提供者的API金鑰。</li>
       <li><b>模型</b>：選取金鑰將使用的LLM模型。</li>
       <li><b>其他欄位</b>：請為您的LLM需要的任何其他欄位輸入值。</li>
      </ul>
    </td> 
  </tr>   <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront應用程式連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-workfront-mcp-to-workfront-fusion" class="MCXref xref">將Adobe Workfront MCP連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>唯讀工具<i>（選擇性）</i></td> 
   <td> <p>限制允許AI呼叫哪些唯讀Workfront動作。 如果未選取工具，則允許所有唯讀工具。</p> </td> 
  </tr> 
  <tr> 
   <td>寫入/刪除工具<i>（選擇性）</i></td> 
   <td> <p>輸入允許人工智慧呼叫的寫入或刪除Workfront動作。 如果您將此保留為空白，則允許使用所有寫入和刪除工具。</p> <p>為了確保自動案例不會採取破壞性動作，我們建議將此欄位設為故意的空白選取專案，而非將其保留為不受限制。</p> </td> 
  </tr> 
  <tr> 
   <td>輸入提示</td> 
   <td> <p>以純英文輸入或對應您希望AI執行的指示。</p> <p>範例： <i>尋找指派給我的所有晚於排程的專案。</i></p> </td> 
  </tr>  </tbody> 
</table>

如需您可以為唯讀工具及寫入/刪除工具欄位選取的工具清單，請參閱Workfront檔案中的[Adobe Workfront MCP伺服器工具](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-tools)。

模組會傳回下列資訊，您可在情境中的後續模組中加以對應：

* **回應**： AI的最終答案，以文字顯示。
* **稽核軌跡**：工作階段的記錄，包括原始提示、開始和結束時間，以及每個工具呼叫AI的詳細資料，例如工具名稱、引數、是否成功、持續時間和輸出。
* **摘要**：工作階段的總計，包括嘗試的工具呼叫數目、成功或失敗的數目、總處理時間以及整體狀態。

---
title: Adobe Fusion MCP模組
description: 透過Adobe Fusion MCP模組，您可以傳送純英文提示給Adobe Fusion的MCP伺服器，讓AI模型執行要求。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: 06ba1c54288fff09f866bffa5c3fce7381c71ad2
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 14%
---
# Adobe Fusion MCP模組

Adobe Fusion MCP聯結器會傳送一個純英文提示給Adobe Fusion模型內容通訊協定(MCP)伺服器。 AI模型會解譯您的請求，並呼叫完成請求所需的Fusion工具。

聯結器僅適用於託管的Adobe Fusion MCP伺服器。 您無法將其指向其他MCP伺服器。

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 將Adobe Fusion MCP連線至Workfront Fusion

您可以直接從Adobe Fusion MCP模組內建立連線。

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
    </tbody>
   </table>

1. 按一下「**[!UICONTROL 繼續]**」。

系統會將您重新導向至Adobe的登入頁面。 使用您的Adobe帳戶登入並核准存取權。 您會重新導向回Workfront Fusion，而新的連線可在模組中使用。

## Adobe Fusion MCP模組及其欄位

### 處理使用者提示

此動作模組會傳送純英文提示給Adobe Fusion MCP伺服器。 AI模型會解譯提示、呼叫完成提示所需的Fusion工具並傳回結果。

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
  </tr> 
  <tr> 
   <td>[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Adobe Fusion MCP連線至Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-fusion-mcp-to-workfront-fusion" class="MCXref xref">將Adobe Fusion MCP連線至Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>唯讀工具<i>（選擇性）</i></td> 
   <td> <p>選取特定的唯讀工具以限制AI。 如果未選取任何專案，則允許此類別中的所有唯讀工具。</p> </td> 
  </tr> 
  <tr> 
   <td>寫入/刪除工具<i>（選擇性）</i></td> 
   <td> <p>選取特定的寫入或刪除工具以限制AI。 如果未選取任何專案，則允許此類別中的所有寫入和刪除工具。</p> <p>為了確保自動案例不會採取破壞性動作，我們建議將此欄位設為故意的空白選取專案，而非將其保留為不受限制。</p> </td> 
  </tr> 
  <tr> 
   <td>輸入提示</td> 
   <td> <p>以純英文輸入或對應您希望AI執行的指示。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 限制AI可呼叫的工具

您可以在唯讀工具和寫入/刪除工具欄位中選取工具，以限制AI可以呼叫哪些Fusion工具。

* 如果您將欄位留空，AI可以呼叫該類別中的每個工具。
* 如果兩個欄位都留空，AI可以呼叫Fusion MCP伺服器上的每個工具。

若要防止自動案例執行寫入或刪除動作，請在「唯讀工具」欄位中僅選取您要允許的工具，並在「寫入/刪除工具」欄位中選取至少一個您熟悉AI呼叫的工具。

清單中的工具名稱來自Fusion MCP伺服器。

#### 模組如何處理您的提示

* 模組沒有後續追蹤。 如果您的提示不清楚，AI會做出合理的假設，並在回應中陳述，而不是詢問您問題。
* AI會驗證可以使用工具變更的資訊。
* 除了您的提示要求之外，AI不會採取任何寫入或刪除動作。
* 模組需要有效的連線。 沒有它就無法執行。

#### 輸出

模組會傳回下列資訊，您可在情境中的後續模組中加以對應：

* **回應**： AI的最終答案，以文字顯示。
* **稽核軌跡**：工作階段的記錄，包括呼叫的工具、其引數和結果，以及計時。
* **摘要**：工作階段的總計，包括成功的工具呼叫次數和最終狀態。

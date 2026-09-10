---
title: Adobe Experience Manager MCP模組
description: 透過Adobe Experience Manager MCP模組，您可以傳送純英文提示給Adobe Experience Manager的MCP伺服器，讓AI模型執行要求。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 06271bbe8dd3c5eb7e3c6b45b71e7e0f7fd4d444
workflow-type: tm+mt
source-wordcount: 1020
ht-degree: 11%

---

# Adobe Experience Manager MCP模組

Adobe Experience Manager MCP聯結器是Adobe Experience Manager自己的模型內容通訊協定(MCP)伺服器的專用Fusion整合。 不像傳統聯結器，每個模組都會執行一個固定動作，此聯結器有一個模組可接受開放式、純英文指示，並讓AI模型決定需要哪些Adobe Experience Manager作業才能完成，如網站、數位資產、內容片段、資料夾、內容存放庫和內容AI等領域。

此聯結器專用於Adobe Experience Manager自己的MCP伺服器。 不支援其他不相關的MCP伺服器。 對於聯結器，您可以改為指向任何MCP伺服器，請使用MCP代理程式聯結器。

如需有關MCP代理程式聯結器的資訊，請參閱[MCP代理程式模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/model-context-protocol-mcp-connector.md)。

>[!NOTE]
>
>此模組的回應是由AI產生，有時並不完美，即使有每個可用的安全保護措施。 此模組適用於自動化功能，因為人沒有即時檢閱每個執行，但無法保證您會從傳統Adobe Experience Manager模組獲得確定性行為。

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

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

* 您必須擁有Adobe Experience Manager帳戶才能使用此模組。

## 將Adobe Experience Manager MCP連線至Workfront Fusion {#connect-adobe-experience-manager-mcp-to-workfront-fusion}

Adobe Experience Manager MCP聯結器使用OAuth連線至Adobe Experience Manager。 沒有可手動填寫的連線欄位，例如使用者名稱、密碼或API金鑰。

若要建立連線：

1. 在Adobe Experience Manager MCP模組中，按一下[連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 選取您要連線到生產或非生產環境。
1. 選取您要連線到服務帳戶還是個人帳戶
1. 按一下「**繼續**」。

   系統會將您重新導向至Adobe的登入頁面。
1. 在Adobe登入頁面上，登入並核准存取權。

您會重新導向回Workfront Fusion，而新的連線可在模組中使用。

## Adobe Experience Manager MCP模組及其欄位

目前，Adobe Experience Manager MCP聯結器中只有一個模組。

### 處理使用者提示

此動作模組會傳送純英文指示至Adobe Experience Manager的MCP伺服器並傳回AI的答案。

此模組的每次執行都是單一、獨立的執行，類似於傳送電子郵件而不是進行即時交談。 AI無法提出後續問題並等待您的回覆。 相反地，它會做出最佳判斷並傳回完整的答案。 如果您的提示模稜兩可，AI會將其所做的任何假設陳述為其答案的一部分，而不是停止要求您澄清。

>[!IMPORTANT]
>
>此模組只有在您的提示實際要求寫入或刪除動作時，才會執行寫入或刪除動作。 它不會採取任何您未要求的額外動作，即使是在它執行您確實要求的其他專案的相同執行中。

因為每次執行都是獨立的，模組本身沒有先前執行的記憶體。 若要在多次執行中建立多圈、對話式的體驗，請儲存上一個問題和答案。 您可以使用資料存放區進行此操作，然後在下一個提示的開頭將該記錄作為文字加入，然後是新問題。

如需資料存放區的資訊，請參閱[資料存放區](/help/workfront-fusion/create-scenarios/data-stores/data-store-overview.md)。

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
   <td><p>如需有關將Adobe Experience Manager帳戶連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-adobe-experience-manager-mcp-to-workfront-fusion" class="MCXref xref">將Adobe Experience Manager MCP連線到Workfront Fusion</a>。</p></td>
  </tr>
  <tr>
   <td role="rowheader">使用者提示</td>
   <td><p>以純英文輸入或對應您希望AI執行的指示。</p><p>範例： <i>在行銷資料夾中尋找90天內未更新的所有資產。</i></p></td>
  </tr>
  <tr>
   <td role="rowheader">唯讀工具<i>（選擇性）</i></td>
   <td><p>限制允許AI呼叫哪些唯讀Adobe Experience Manager動作，這些動作只會查詢某些專案，例如尋找資產或讀取頁面內容，永遠不會變更任何專案。</p><p>如果您將此欄位留空，則允許所有唯讀動作。</p></td>
  </tr>
  <tr>
   <td role="rowheader">寫入/刪除工具<i>（選擇性）</i></td>
   <td><p>限制允許AI呼叫的寫入或刪除Adobe Experience Manager動作，這些動作會變更某些專案，例如更新頁面、發佈內容或刪除資產。</p><p>如果您將此欄位留空，則允許所有寫入和刪除動作。 為了確保自動案例不會採取破壞性動作，我們建議將此欄位設為故意的空白選取專案，而非將其保留為不受限制。</p></td>
  </tr>
 </tbody>
</table>

模組會以文字形式傳回AI的最終答案，連同產生該答案時發生的記錄，包括呼叫了哪些工具、每次呼叫是否成功以及處理耗時多長。


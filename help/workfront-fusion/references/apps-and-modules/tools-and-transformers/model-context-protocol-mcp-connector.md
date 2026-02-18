---
title: 模型內容通訊協定(MCP)模組
description: 「模型上下文通訊協定」(MCP)模組可讓您使用MCP處理使用者提示。
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 748055ad-d305-4513-9a5c-9c970b74a96e
source-git-commit: 97abe6bf0ff7b10a139268f02f8a1a24f3e31b47
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 18%

---

# MCP代理程式模組

<!--SET UP REDIRECTS-->

模型上下文通訊協定(MCP)是一種將AI語言模型與其他應用程式安全連線的方法。 您可以設定MCP伺服器，讓AI模型存取應用程式。 然後，您可以向AI模型傳送提示，它可以從應用程式返回資訊。

例如，您可以設定MCP伺服器來連線AI模型與Gmail。 當您傳送提示「Give my last 5 emails from Gmail」時，它可以存取您的Gmail並傳回電子郵件。

「模型上下文通訊協定」(MCP)模組可讓您使用語言模型和MCP伺服器來處理使用者提示。

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

## 先決條件

* 您必須已設定要連線的任何MCP伺服器。
* 您必須擁有所選LLM （大型語言模型）的LLM金鑰。

## 模型內容通訊協定模組及其欄位

### 處理使用者提示

此動作模組會使用您指定的語言模型和MCP伺服器來處理提示。

>[!NOTE]
>
>此模組必須傳回物件。 它不會傳回輸出，例如字串或數字。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>LLM金鑰</td> 
   <td> 選取現有的LLM金鑰，或按一下<b>新增</b>並輸入下列資訊以建立新金鑰： 
     <ul>
       <li><b>金鑰名稱</b>：輸入新金鑰的名稱。</li>
       <li><b>LLM</b>：選取與此索引鍵關聯的大型語言模型。</li>
       <li><b>Key</b>：輸入或對應您所選模型的API金鑰。</li>
       <li><b>模型</b>：選取金鑰將使用的LLM模型。</li>
       <li><b>Token數目上限</b>：輸入或對映LLM在其回應中可產生的最大Token數目。<p>一個語彙基元通常等於四個字元，或一個英文單字的0.75。 「Hello world」會等於兩個權杖，而「Authentication」會等於一到兩個權杖。</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>MCP伺服器</td> 
   <td> <p>針對您想要連線的每個MCP伺服器，按一下[新增] <b></b>並輸入下列資訊： </p> 
     <ul>
       <li><b>連線</b>：選取Fusion用來連線到MCP伺服器的連線。</li>
       <li><b>MCP伺服器主機</b>：輸入MCP伺服器的URL。</li>
       <li><b>MCP伺服器名稱</b>：輸入或對應此MCP伺服器的名稱。</li>
       <li><b>標題</b>：新增任何適用的標題。</li>
       <li><b>MCP伺服器型別</b>：選取伺服器型別。</li>
      </ul>
    </td> 
  </tr> 
  <tr> 
   <td>輸入提示 </td> 
   <td> <p>輸入或對應您要處理的提示。</p> </td> 
  </tr> 
 </tbody> 
</table>



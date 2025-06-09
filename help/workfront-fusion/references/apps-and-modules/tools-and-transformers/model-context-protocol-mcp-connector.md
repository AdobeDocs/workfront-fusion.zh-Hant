---
title: 模型內容通訊協定(MCP)模組
description: 「模型上下文通訊協定」(MCP)模組可讓您使用MCP處理使用者提示。
author: Becky
feature: Workfront Fusion
source-git-commit: d8ae176db714d2b9f041b74a62e8276171745c4b
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---

# 模型內容通訊協定(MCP)模組

模型上下文通訊協定(MCP)是一種將AI語言模型與其他應用程式安全連線的方法。 您可以設定MCP伺服器，讓AI模型存取應用程式。 然後，您可以向AI模型傳送提示，它可以從應用程式返回資訊。

例如，您可以設定MCP伺服器來連線AI模型與Gmail。 當您傳送提示「Give my last 5 emails from Gmail」時，它可以存取您的Gmail並傳回電子郵件。

「模型上下文通訊協定」(MCP)模組可讓您使用語言模型和MCP伺服器來處理使用者提示。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求</p>
   <p>或</p>
   <p>舊版：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 模型內容通訊協定模組及其欄位

當您設定MCP模組時，[!DNL Adobe Workfront Fusion]會顯示下列欄位。 模組中的粗體標題表示必填欄位。

### 處理使用者提示

此動作模組會使用您指定的語言模型和MCP伺服器來處理提示。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 大語言模型(LLM)鍵]</td> 
   <td> <p>輸入或對應您要用於此提示的大型語言模型的API金鑰。 </p> <p>目前僅支援人類API金鑰。</p></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL MCP伺服器]</td> 
   <td> <p>對於您想要讓此提示可用的每個MCP伺服器，按一下[新增專案] </b>，然後輸入伺服器的名稱和主機。<b> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸入提示]</td> 
   <td> <p>輸入或對應大型語言模型的提示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

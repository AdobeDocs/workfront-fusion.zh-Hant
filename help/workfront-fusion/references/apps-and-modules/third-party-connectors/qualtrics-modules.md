---
title: Qualtrics 模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Qualtrics的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 80b441b7-c808-4c4f-b9ff-d614650dbb73
source-git-commit: b4353a0746f4f427c70d0a213e5dde36ff869ab8
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 59%

---

# Qualtrics 模組

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Qualtrics] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

關於建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)之下的文章。

關於模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)之下的文章。

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
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>連接器型 (舊版)：Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL Qualtrics]模組，您必須有[!UICONTROL Qualtrics]帳戶。

## Qualtrics API資訊

Qualtrics聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td><pre><code>https://&#123;&#123;connection.dataCenterCode&#125;&#125;.qualtrics.com/API/v3</code></pre></td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 版本</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.1.1</td> 
  </tr>
 </tbody> 
 </table>

## 正在將[!DNL Qualtrics]連線到Workfront Fusion

您可以直接從[!UICONTROL Qualtrics]模組內建立與您的[!DNL Qualtrics]帳戶的連線。

1. 在任何[!UICONTROL Qualtrics]模組中，按一下[!UICONTROL 連線]欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 輸入下列資訊：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL 連線名稱]</p> </td> 
      <td> <p>輸入新連線的名稱。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL資料中心ID] </td> 
      <td>使用格式<code>&lt;Data Center ID>.qualtrics.com</code>。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL API Key]</td> 
      <td>若要尋找您的API金鑰，請參閱[!DNL Qualtrics]檔案。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**[!UICONTROL 繼續]**」來建立連線並返回模組。

## [!DNL Qualtrics] 模組及其欄位

[!DNL Qualtrics]聯結器可使用下列模組：

* [!UICONTROL 觀看新的問卷回應]
* [!UICONTROL 建立目錄連絡人]
* [!UICONTROL 刪除目錄連絡人]
* [!UICONTROL 取得目錄連絡人]
* [!UICONTROL 更新目錄連絡人]
* [!UICONTROL 透過SMS建立新的意見調查發佈]
* [!UICONTROL 透過電子郵件散發問卷]
* [!UICONTROL 進行API呼叫]
* [!UICONTROL 列出目錄連絡人]

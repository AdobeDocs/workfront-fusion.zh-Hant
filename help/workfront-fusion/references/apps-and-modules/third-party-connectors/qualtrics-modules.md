---
title: Qualtrics模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Qualtrics的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 80b441b7-c808-4c4f-b9ff-d614650dbb73
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 1%

---

# Qualtrics模組

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Qualtrics]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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
   <td> https://{{connection.dataCenterCode}}.qualtrics.com/API/v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.1.1</td> 
  </tr>
 </tbody> 
 </table>

## 正在將[!DNL Qualtrics]連線到Workfront Fusion

您可以直接從[!DNL Qualtrics]Qualtrics[!UICONTROL 模組內建立與您的]帳戶的連線。

1. 在任何[!UICONTROL Qualtrics]模組中，按一下&#x200B;**[!UICONTROL 連線]**&#x200B;欄位旁的[!UICONTROL 新增]。
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
      <td role="rowheader">[!UICONTROL 資料中心ID] </td> 
      <td>使用格式<code>&lt;Data Center ID>.qualtrics.com</code>。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL API Key]</td> 
      <td>若要尋找您的API金鑰，請參閱[!DNL Qualtrics]檔案。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

## [!DNL Qualtrics]模組及其欄位

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

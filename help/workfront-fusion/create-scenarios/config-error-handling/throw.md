---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: errors
title: 設定擲回錯誤因應措施
description: 在某些情況下，您可能會想要強制停止案例執行，然後是「復原」或「認可」階段，或者停止處理路由，並選擇性地將其儲存在「檢視」佇列中，並在Adobe Workfront Fusion中解決未完成的執行。
author: Becky
feature: Workfront Fusion
exl-id: 4bf2a6c7-16b2-4545-9adf-be3947a7017d
source-git-commit: 0668441df8405610488e3e33658635e4cc7db270
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---

# 設定`throw`錯誤因應措施

在某些情況下，您可能會想要強制停止案例執行，然後是「復原」或「認可」階段，或者停止路由處理，並選擇性地將其儲存在未完成執行的佇列中。

目前，錯誤處理指示詞不能用於錯誤處理常式路由的範圍之外，而且Adobe Workfront Fusion不提供可讓您輕鬆有條件產生（擲回）錯誤的模組。

您可以使用下列因應措施，來模擬`throw`錯誤功能。

如需有關未完成執行的資訊，請參閱[在Adobe Workfront Fusion中檢視及解決未完成的執行](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)。

如需錯誤處理指示的資訊，請參閱[指示在 [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/errors/directives-for-error-handling.md)中錯誤處理。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront計畫：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## `throw`的因應措施

若要有條件地擲回錯誤，您可以設定模組，使其在操作期間故意失敗。 一種可能是採用[!UICONTROL JSON] > [!UICONTROL Parse JSON]模組，此模組已設定為選擇性擲回錯誤（在此情況下為`BundleValidationError`）：

![JSON錯誤](assets/json-parse-json.png)

然後，您可以將其中一個錯誤處理指示附加至錯誤處理路由：

* **回覆**：強制案例執行停止並執行回覆階段。
* **認可**：強制案例執行停止並執行認可階段。
* **忽略**：停止處理路由。
* **中斷**：停止處理路由，並將其儲存在未完成執行的佇列資料夾中。

下列範例顯示[!DNL Rollback]指示詞的使用：

![](assets/rollback-directive.png)

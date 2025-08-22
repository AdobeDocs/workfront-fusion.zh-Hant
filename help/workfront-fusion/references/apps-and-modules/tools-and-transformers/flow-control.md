---
title: 流量控制
description: 當您建立或編輯案例時，可以設定設定來控制資料流經案例的方式。
author: Becky
feature: Workfront Fusion
exl-id: b3aed366-c399-44fa-8967-54ecb8647d96
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 2%

---

# 流量控制

當您建立或編輯案例時，可以設定設定來控制資料流經案例的方式。

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
   <p>無Workfront Fusion授權需求</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增:</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 中繼器

您可以使用[!UICONTROL 中繼器]模組來重複指定次數的工作。 [!UICONTROL 中繼器]模組會產生一個接一個的組合。


<table>
    <tr>
        <td>[！UICONTROL初始值]</td>
        <td>輸入或對映您希望模組在第一個反複專案中的值。 預設值為 1。</td>
    </tr>
    <tr>
        <td>[！UICONTROL重複]</td>
        <td>輸入或對應您希望模組重複的次數。 此數字必須大於或等於0，且小於或等於10,000。</td>
    </tr>
    <tr>
        <td>[！UICONTROL步驟]</td>
        <td>這是模組增加值時所使用的數字。 預設值為 1。</td>
    </tr>
</table>

>[!BEGINSHADEBOX]

例如，您可以使用[!UICONTROL 中繼器]模組，傳送主題為「Hello 1」、「Hello 2」等的5封電子郵件，方法是將&#x200B;**[!UICONTROL 電子郵件] >[!UICONTROL 傳送電子郵件]**&#x200B;模組至[!UICONTROL 中繼器]模組。

1. 按一下畫面底部的[!UICONTROL 流量控制項]圖示![流量控制項圖示](/help/workfront-fusion/references/apps-and-modules/assets/flow-control-icon.gif)，然後在顯示的功能表中按一下&#x200B;**[!UICONTROL 中繼器]**。
1. 按一下[!UICONTROL 中繼器]模組，然後在顯示的方塊中按一下&#x200B;**[!UICONTROL 自動連線]**。

   中繼器模組隨即開啟。

1. 在&#x200B;**[!UICONTROL 重複]**&#x200B;欄位中，輸入您希望模組產生的重複（輸出組合）數目。

   在此範例中，您應輸入5。

   ![中繼器](/help/workfront-fusion/references/apps-and-modules/assets/repeater-2-350x207.png)

   每次重複時，專案的值會以&#x200B;**[!UICONTROL 步驟]**&#x200B;欄位中指定的值增加，您可以選取&#x200B;**[!UICONTROL 顯示進階設定]**&#x200B;來檢視該欄位。 此數字預設為1。

1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;以關閉&#x200B;**[!UICONTROL 流量控制]**&#x200B;方塊。

1. 按一下連線至[!UICONTROL 中繼器]模組的應用程式或服務模組。
1. 在出現的方塊中，鍵入要重複的資訊。

   在我們的電子郵件範例中，您會在[!UICONTROL 主旨]方塊中輸入Hello，然後從中繼器模組對應`i`。

   ![中繼器](/help/workfront-fusion/references/apps-and-modules/assets/repeater-3-350x207.png)



>[!NOTE]
>
>重複次數不是由`i`的值決定，因為它在程式設計中會處於回圈中。 模組將重複[!UICONTROL 重複]欄位中指定的次數。 值`i`會隨著[!DNL repeater]模組的每個反複專案而變更，並可對應至之後的模組。 上述範例將`i`的值對應到Hello訊息中，導致訊息顯示「Hello 1」、「Hello 2」等。

>[!ENDSHADEBOX]

## [!UICONTROL 迭代器]

[!UICONTROL 疊代器]是一種特殊的模組，可將陣列轉換為一系列組合。 在[!UICONTROL 疊代器]模組輸出中，每個陣列專案都是個別的組合。 如需詳細資訊，請參閱[疊代器模組](/help/workfront-fusion/references/modules/iterator-module.md)。

## 陣列彙總

陣列彙總器是一種特殊型別的模組，可將數個套件合併為單一套件。 如需詳細資訊，請參閱[彙總器模組](/help/workfront-fusion/references/modules/aggregator-module.md)。

## [!UICONTROL 路由器]

[!UICONTROL 路由器]模組可讓您將流量分支為數個路由，並以不同方式處理每個路由中的資料。 一旦[!UICONTROL 路由器]模組收到套件組合，它會依照路由附加至[!UICONTROL 路由器]模組的順序將其轉送至每個連線的路由。 如需詳細資訊，請參閱Adobe Workfront Fusion中的[路由器模組](/help/workfront-fusion/create-scenarios/add-modules/router-module.md)。

## 指令

錯誤處理指示可讓您控制案例對錯誤的反應方式。

如需錯誤處理指示的資訊，請參閱錯誤處理[的](/help/workfront-fusion/references/errors/directives-for-error-handling.md)指示。


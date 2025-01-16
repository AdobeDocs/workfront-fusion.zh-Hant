---
title: 疊代器模組
description: 疊代器模組是一種特殊的模組，可將陣列轉換為一系列組合。 每個陣列專案都會以個別的套件組合輸出。
author: Becky
feature: Workfront Fusion
exl-id: 43d39955-3dd7-453d-8eb0-3253a768e114
source-git-commit: b7c511c51a2f27292cd0cb754673515e67c8a397
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---

# [!UICONTROL Iterator]模組

[!UICONTROL Iterator]是一種將陣列轉換為一系列組合的模組。 每個陣列專案都會以個別的套件組合輸出。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!DNL Adobe Workfront] 封裝</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權</td> 
   <td> 新增：標準<p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] 授權</td> 
   <td>
   <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
 </tbody> 
</table>


若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## [!UICONTROL Iterator]模組組態

一般疊代器模組有一個欄位，[!UICONTROL Array]欄位。 此欄位包含要轉換或分割為個別套裝的陣列。

![](assets/set-up-iterator.jpg)

其他聯結器可能包含該迭代器特定的迭代器模組。 這些內含Source模組欄位，可讓您選取輸出您要疊代之陣列的模組。

![](assets/specialized-iterators.jpg)

如需詳細資訊，請參閱[設定模組](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md)。

>[!BEGINSHADEBOX]

**範例：**

* 以下案例顯示如何擷取含有附件的電子郵件，並將附件儲存為所選[!DNL Dropbox]資料夾中的單一檔案。

  電子郵件可以包含一系列附件。 第一個模組之後的[!UICONTROL Iterator]模組可讓案例分別處理每個附件。 [!UICONTROL Iterator]模組將附件陣列分割為單一組合。 然後，會將每個附有一個附件的套件一次儲存在選取的[!DNL Dropbox]資料夾中。 疊代器模組中的[!UICONTROL Array]欄位應該包含`Attachments`陣列。

  ![](assets/attachments-array.jpg)

>[!ENDSHADEBOX]


## 疑難排解

### 問題：對應面板未在[!UICONTROL Iterator]模組下顯示可對應專案

當[!UICONTROL Iterator]模組沒有陣列專案結構的相關資訊時，[!UICONTROL Iterator]模組之後的模組中的對應面板只會顯示[!UICONTROL Iterator]模組下的兩個專案： `Total number of bundles`和`Bundle order position`。

![](assets/mapping-panel-doesnt-display.png)

這是因為每個模組都負責提供其輸出專案的相關資訊，以便這些專案能在後續模組的對應面板中正確顯示。 不過，在某些情況下，數個模組可能無法提供此資訊。 例如，[!UICONTROL JSON] > [!UICONTROL Parse JSON]或遺失資料結構的[!UICONTROL Webhooks] > [!UICONTROL Custom Webhook]模組將無法提供資訊。

#### 解決方案

解決方案是手動執行情境。 這會強制模組建立輸出。 然後，Fusion可以將此輸出的格式套用至情境中稍後的模組。

例如，案例包含沒有資料結構的[!UICONTROL JSON] > [!UICONTROL Parse JSON]模組。

![](assets/json-parse-json.png)

連線到此JSON模組的[!UICONTROL Iterator]模組無法將模組的輸出對應到[!UICONTROL Iterator]模組設定面板中的Array欄位。

![](assets/connect-iterator-module.png)

若要解決此問題：

在案例編輯器中手動啟動案例。

>[!NOTE]
>
>若要防止整個案例執行，您可以：
>
>* 在[!UICONTROL JSON] > [!UICONTROL Parse JSON]模組之後取消模組連結，以防止流程繼續進行。
>   或
>* 以滑鼠右鍵按一下[!UICONTROL JSON] > [!UICONTROL Parse JSON]模組，然後從內容功能表中選擇&#x200B;**[!UICONTROL Run this module only]**&#x200B;以僅執行[!UICONTROL JSON] > [!UICONTROL Parse JSON]模組。

執行[!UICONTROL JSON] > [!UICONTROL Parse JSON]之後，它就可以將其輸出的相關資訊提供給所有後續模組，包括疊代器模組。 接著迭代器設定中的對應面板會顯示專案：

![](assets/mapping-panel-displays-items.png)

此外，在[!UICONTROL Iterator]模組之後連線的模組中的對應面板會顯示陣列中包含的專案：

![](assets/items-contained-in-array.png)

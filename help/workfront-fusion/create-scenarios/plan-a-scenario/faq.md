---
title: 情境規劃常見問題集
description: 當您開始在Workfront Fusion中建立案例時，本文中的資訊可能會很有用。
author: Becky
feature: Workfront Fusion
exl-id: 6a1d672d-0bd7-4a3a-b96d-6d8b4c97522d
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 1%

---

# 情境規劃常見問題集

當您開始在Workfront Fusion中建立案例時，本文中的資訊可能會很有用。

## 什麼是情境？

### 解答

案例會定義Adobe Workfront Fusion要執行的一系列步驟。 對於每個情境，您都可以指定資料來源、要使用的資料，以及處理資料的方式。 Fusion可讓您建立簡單或複雜的情境，以便符合您組織的使用案例。

如需案例的詳細資訊，請參閱[案例概觀](/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md)。

## 我可以在一個案例中使用多少模組？

### 解答

您可以在情境中使用任意數量的模組。 您可以將模組分成路由，也可以指定哪些資料應流經每個路由。 您也可以使用一個模組的輸出，作為另一個模組的輸入。

雖然案例中的模組數量沒有限制，但超過150個模組可能會影響案例效能。

如需模組的詳細資訊，請參閱[模組概觀](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md)。

## [!DNL Workfront Fusion]可以使用檔案嗎？

### 解答

是。Workfront Fusion可以接收、儲存、轉換、轉換及加密檔案。 Fusion也提供廣泛的內建功能，讓使用者能夠更有效率、創造性地處理檔案中包含的資料。

如需在Fusion中使用檔案的詳細資訊，請參閱[在模組之間對應檔案](/help/workfront-fusion/create-scenarios/map-data/map-files.md)。

## 有些觸發器允許立即執行情境。 「即時」是什麼意思？

### 解答

情境可以根據您指定的排程間隔執行，例如每小時或每5分鐘執行一次。 有一些特殊的觸發器，稱為即時觸發器(webhook)，可在從指定服務收到資料後立即啟動您的情境。 Fusion會立即處理收到的資料，不會等候下一次排定的執行。

如需輪詢與立即觸發程式之間差異的詳細資訊，請參閱文章模組概觀中的[觸發程式模組](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)。

## 什麼是作業？

### 解答

作業是指模組執行的任何工作。 例如，每次執行觸發程式時，以及每次動作執行工作時，都會發生作業。

某些Fusion計畫是根據您的組織使用的作業數而定。

如需作業的詳細資訊，請參閱[作業](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md)。

## 什麼是資料傳輸？

### 解答

資料傳輸是指透過您的情境傳輸的資料量。 例如，從Workfront擷取100KB的影像，然後將影像上傳至檔案儲存提供者的情境。 此情境中使用的資料量為200KB。

## 什麼是連線？

### 解答

連線是您[!DNL Workfront Fusion]帳戶與您要使用的協力廠商服務之間的連結。 可在編輯案例時建立連線。

如需詳細資訊，請參閱[連線總覽](/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md)。

## 什麼是彙總？

### 解答

[!UICONTROL Aggregator]會將資料合併至單一集合。 例如，將檔案壓縮為zip封存檔並作為電子郵件附件傳送。

如需詳細資訊，請參閱[[!UICONTROL Aggregator]模組](/help/workfront-fusion/references/modules/aggregator-module.md)。

## 如果我讓[!DNL Workfront Fusion]處理包含多個附件的電子郵件，會發生什麼情況？

### 解答

如果您使用[!UICONTROL Email]模組[!UICONTROL Retrieve attachments]，每個附件會透過情境中的其餘模組個別傳送。 類似的模組也可用於同時接收多個檔案的其他應用程式。

---
title: 模組概觀
description: Adobe Workfront Fusion 會劃分五種模組類型：動作模組、搜尋模組、觸發程序模組、彙總器和疊代器。彙總器和疊代器適用於進階情境。
author: Becky
feature: Workfront Fusion
exl-id: 4c8fe028-8425-426d-a006-f0c66871b3cd
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: ht
source-wordcount: '917'
ht-degree: 100%

---

# 模組概觀

Adobe Workfront Fusion 會劃分五種模組類型：

* 動作模組
* 搜尋模組
* 觸發程序模組
* 彙總器
* 疊代器

彙總器和疊代器適用於進階情境。

## 動作模組

動作模組是最常見的模組類型。典型的動作模組會執行一個動作並傳回單一組合包，這個組合包隨後傳遞至下一個模組進行處理。

與觸發程序模組不同，動作模組可以放置在情境的開頭、中間或結尾。

情境可以包含不限數量的動作模組，但大量模組 (超過 150 個) 可能會影響效能。

>[!BEGINSHADEBOX]

**範例：**

* 「**Workfront > [!UICONTROL 上傳檔案]**」會將檔案傳送至 Workfront 並傳回其識別碼。
* 「**[!UICONTROL 影像] > [!UICONTROL 調整大小]**」會收到影像，將影像調整為指定大小，然後將調整大小後的影像傳遞至下一個動作。

>[!ENDSHADEBOX]

動作類型有四個子類型：

* 建立
* 讀取
* 更新
* 刪除

更新子類型包含下列三項作業：

* **清除欄位的內容**。當欄位內容評估為關鍵字 `erase`  (勿與 `empty` 混淆) 時，便會執行此項作業。

  ![關鍵字 Erase](assets/erase-content-of-field.png)

* **讓欄位內容維持不變**。當欄位留空或欄位內容評估為空 (在 JSON 中以 Null 表示) 時，便會執行此項作業。

  ![空的組合包](assets/leave-content-field-unchanged.png)

* **取代欄位的內容**。上述兩種情形以外的所有其他情形皆會執行此項作業。

>[!NOTE]
>
>* 如果您在對應面板中看不到關鍵字 `erase`，表示模組並非更新模組，或者模組尚未更新至應用程式的最新規格。
>* `Empty` 不會變更欄位內容。如果必須清除欄位，您可以使用下列公式：
>
>   ![若為空](assets/formula-ifempty-name-erase.png)
>
>* 目前不支援在內容被評估為空時讓欄位維持不變。

## 搜尋模組

搜尋模組會傳回零個、一個或多個組合包，這些組合包隨後傳遞至下一個模組進行處理。

您可以將搜尋模組放置在情境的開頭、中間或結尾。

情境可以包含不限數量的搜尋模組，但大量模組 (超過 150 個) 可能會影響效能。

>[!BEGINSHADEBOX]

**範例：**

「**Workfront > [!UICONTROL 讀取相關記錄]**」會讀取在特定的上層物件中，符合您指定之搜尋查詢的記錄。

>[!ENDSHADEBOX]

## 觸發程序模組

當特定的服務發生變更時 (例如建立或更新記錄)，觸發程序便會產生組合包。

觸發程序會傳回零個、一個或多個組合包，這些組合包隨後傳遞至下一個模組進行處理。

由於觸發程序會使情境開始執行，所以只能放在情境的開頭。

每個情境只能包含一個觸發程序。

Workfront Fusion 使用兩種類型的觸發程序：輪詢觸發程序和即時觸發程序。

### 輪詢觸發程序

輪詢觸發程序會定期輪詢特定服務，即使在前一次執行情境後沒有變更。我們建議您安排含有輪詢觸發程序的情境定期執行。若變更內容符合觸發程序的設定，觸發程序會傳回包含變更相關資訊的組合包。若沒有符合設定的變更，則觸發程序不會輸出任何組合包。

如需安排情境執行時間的說明，請參閱[安排情境執行時間](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)。

透過輪詢觸發程序，您可以選取觸發程序透過面板應該輸出的第一個組合包，而該面板會在您儲存觸發程序或變更觸發程序設定後自動顯示。此一選取動作只會影響模組的第一次執行。模組執行過一次後，後續的執行只會監視最近一次執行後發生的變更。

如需詳細資訊，請參閱[選擇觸發程序模組的起點](/help/workfront-fusion/create-scenarios/add-modules/choose-where-trigger-module-starts.md)。

>[!BEGINSHADEBOX]

**範例：**

* 「**Workfront > [!UICONTROL 監視記錄]**」會傳回上一次執行情境後新增的記錄。

* 「**[!DNL Google Sheets]> [!UICONTROL 監視列]**」會傳回上一次執行情境後新增的列。

>[!ENDSHADEBOX]

### 即時觸發程序

透過即時觸發程序，服務可以在變更發生後立即通知 Workfront Fusion。我們建議您安排含有即時觸發程序的情境立即執行。

如需相關說明，請參閱[安排情境執行時間](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)。

如需即時觸發程序如何處理傳入資料的詳細資訊，請參閱[即時觸發程序 (Webhook)](/help/workfront-fusion/references/modules/webhooks-reference.md)。

>[!BEGINSHADEBOX]

**範例：**

* 「**Workfront > [!UICONTROL 監視事件]**」會在 Workfront 中發生特定類型的事件 (例如建立任務) 時傳回資訊。
* 「**[!DNL Google Sheets]> [!UICONTROL 監視變更]**」會在每次儲存格更新時傳回資訊。

>[!ENDSHADEBOX]

## 彙總器

彙總器模組會將多個組合包累積成單一組合包。

彙總器只會傳回一個組合包，此組合包隨後傳遞至下一個模組進行後續處理。

彙總器只能放置在情境的中間。

情境可以包含不限數量的彙總器，但大量模組 (超過 150 個) 可能會影響效能。

>[!BEGINSHADEBOX]

**範例：**

* 「**[!UICONTROL 封存] > [!UICONTROL 建立封存]**」會將多個檔案壓縮成 ZIP 封存檔。
* 「**[!UICONTROL CSV] > [!UICONTROL 彙總至 CSV]**」會將 CSV 檔案中的多個字串合併為一列。
* 「**[!UICONTROL 工具] > [!UICONTROL 文字彙總器]**」會將數個字串合併為單一字串。

>[!ENDSHADEBOX]

如需詳細資訊，請參閱[彙總器模組](/help/workfront-fusion/references/modules/aggregator-module.md)。

## 疊代器

疊代器是一種將陣列分割為個別組合包的模組。

疊代器會傳回一個或多個組合包，這些組合包隨後傳遞至下一個模組進行處理。

您只能將疊代器放置在情境的中間。

情境可以包含不限數量的疊代器，但大量模組 (超過 150 個) 可能會影響效能。

>[!BEGINSHADEBOX]

**範例：**

「**[!UICONTROL 電子郵件] > [!UICONTROL 檢索附件]**」會將附件陣列拆分成個別的組合包。

>[!ENDSHADEBOX]

如需詳細資訊，請參閱[疊代器模組](/help/workfront-fusion/references/modules/iterator-module.md)和[對應陣列](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md)。

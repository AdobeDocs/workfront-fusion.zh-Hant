---
name: fusion-doc-request
description: 處理#fusion-documentation Slack範本中的Fusion檔案請求 — 更新此存放庫中的相關Fusion檔案文章，然後在產品檔案Workfront專案中建立相符的工作，並在自訂表單中填入功能說明和格式化發行說明。 當使用者共用Fusion功能的Slack檔案請求對話串/訊息，或針對一個功能說「請更新並建立任務」之類的話時使用。
source-git-commit: 6726c582294758de0bbab19d6014ad80bb66e553
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 0%

---


# Fusion檔案要求

處理`#fusion-documentation` Slack頻道中張貼的循環「來自{person}的新檔案請求」模式：讀取請求、更新檔案，然後在用於先前每種此類請求的相同Workfront自訂表單上建立追蹤任務。

這是與`fusion-release-notes`技能不同的工作流程。 此技能可更新參考文章和建立Workfront任務；它不會在此存放庫中建立或更新每週Fusion版本注意事項頁面，即使請求顯示「需要公告：是」。 只有在使用者分別要求每週發行說明時，才使用`fusion-release-notes`。

## 步驟1：取得請求詳細資料

如果指定了Slack連結，請從URL剖析`channel_id`和`message_ts`，並擷取執行緒（`slack_get_thread_replies`或`slack_read_thread`，視所連線的Slack MCP工具而定 — 如果其中一個失敗，請嘗試兩者）。 保留執行緒的永久連結/URL — 步驟3中需要它。

此環境中的Slack連線不穩定（權杖已過期，工作階段期間中斷連線）。 如果擷取失敗：
- 重試一次。
- 如果仍然失敗，請直接告訴使用者擷取失敗，並要求他們直接貼上請求內容。 不要猜測內容，也不要不假思索地放棄。

請求範本有下列欄位 — 擷取每個欄位：

&#x200B;* **功能標題**
&#x200B;* **說明**
&#x200B;* **要新增至檔案的點** *（有時顯示 — 要求者要涵蓋的特定區段/詳細資訊；視這些為必要，若有提供則為選用）*
&#x200B;* **預計發行日期**
&#x200B;* **需要宣告** *(是/否 — 僅供參考；請參閱上面的備註。 不要在此欄位上動作。)*

如果要求連結至具有完整規格的Confluence Wiki頁面，請先擷取該頁面(`get_wiki_content`)，然後再撰寫檔案。 請勿僅仰賴Slack摘要來取得技術細節（確切的欄位名稱、步驟、UI標籤），請在連結時從Wiki規格提取這些內容。

如果請求改為連結到非Confluence次要來源（例如Experience League社群貼文、支援文章、AI產生的摘要）而不是權威規格，您可能會使用它來填入Slack文字缺少的技術細節，但將其視為低於Slack請求本身的信賴度。 當它與Slack文字衝突或新增時（相同按鈕/欄位的不同名稱，Slack中完全未提及的細節），請勿無訊息地選擇一個 — 使用Slack請求的措辭作為主要來源寫入檔案，並根據步驟2中的指南在HTML註解內標示差異（例如`<!-- BECKY CHECK ME: Slack calls this "Activate," but the linked community post calls it "Reactivate" - confirm against the live UI. -->`）。

## 步驟2：更新檔案

在此存放庫中尋找相關的現有文章（相關模組名稱、UI標籤或設定名稱的問候 — 請勿猜測檔案）。 依照該文章的現有結構、標題層級和房屋樣式，更新它們以反映變更。

&#x200B;* 請勿發明不在Slack要求或連結Wiki規格中的技術細節（確切欄位名稱、許可權範圍、設定步驟）。 如果某專案未確認，請將其內嵌標示為HTML註解（例如`<!-- BECKY CHECK ME: confirm the exact permission scope before publishing -->`），而非猜測 — 不要將它標示為可見的圖說文字。 它不得在已發佈的頁面上呈現。
&#x200B;* 如果這需要全新的文章檔案（不僅是對現有文章檔案的編輯），請遵循此存放庫的現有慣例：前端內容中沒有偽造的`exl-id`/`TQID`，並在建立檔案後將其轉換為CRLF/no-BOM （`Write`工具預設為LF）。
&#x200B;* 將新頁面連線到「目錄」中意指兩者兼而有之，而不僅僅一個 — 頁面可以從子索引連結，同時讀者仍然看不到：
  - 產品區域的主要導覽檔案（例如`help/workfront-fusion/TOC.md`） — 這是實際驅動已發佈導覽樹狀結構的專案。
  - 任何內容中的子索引/登陸頁面也會連結至此類文章（例如，新聯結器模組頁面的`apps-and-modules-toc.md`）。
    明確檢查兩者，並確認新專案位於相同的清單中、位於相同的巢狀層級，因為其最接近的同層級文章位於每個檔案中 — 請勿假設將其新增至一個會遮蓋另一個專案。

## 步驟3：建立Workfront工作

專案： **產品檔案任務 — 需要傳訊的開發問題**。 使用`insights_find_id_by_name` （實體`project`）解析其ID，而非將其硬式編碼，以防其變更 — 請參閱下列已知值以瞭解最後解析的ID。

工作列位：

| 欄位 | 值 |
|---|---|
| `name` | `Becky - {Feature Title}` |
| `projectID` | 從上述專案查詢中 |
| `parentID` | 父系任務識別碼（`parentID`，系統欄位 — 無`DE:`首碼） — 請參閱下面的已知值。 這會使新任務成為子任務，而不是專案中的最上層任務。 |
| `assignedToID` | 目前的使用者，來自`insights_get_current_user` |
| `categoryID` | 產品檔案自訂表單ID — 請參閱以下已知值。 如果不清楚，請在此專案中查詢任何最近同層級任務的`task.task_categoryID`以進行確認。 |
| `description` | **完成Slack訊息文字** （請求範本中的所有欄位，而非轉譯），後面接著連結Slack交談 |
| `DE:Release notes` | 格式化的發行說明，請參閱下方的格式 |
| `DE:Preview Date Known` | `Yes`，預設 |
| `DE:Preview Date` | 預設為要求的&#x200B;**預期發行日期** |
| 產品/區域 | 選取`Fusion` （[產品檔案]表單上的列舉欄位；若不清楚，請使用`insights_search_fields`確認確切的欄位名稱） |

將預覽日期欄位設定為此相同建立呼叫的一部分 — 不要留待稍後或等待詢問。 如果使用者稍後提供不同的日期，或說日期尚未實際知道，請據此更新，但預設為每次都填寫。

`DE:Release notes`欄位的發行說明格式。 一律從`***FUSION***`開始於自己的行，然後是空白行，然後是標題 — 這會一目瞭然地將附註標籤為屬於Fusion （與核心Workfront相反）：

```markdown
***FUSION***

## {Feature Title}

{Description of what changed and why it matters, in second person. A sentence or two is enough for a simple change - use multiple paragraphs and/or a bulleted list for anything with several parts or steps, the same way a full weekly release note would.}

For more information, see [{Article title}](/help/workfront-fusion/{path-to-article}.md).
```

在建立呼叫之前，使用`workfront://tools/create-any-object`呼叫`read_workflow_docs` — 此呼叫會設定自訂欄位和列舉值(`DE:Preview Date Known`)，這需要MCP伺服器的規則。

## 步驟4：確認返回使用者

簡單報告：

&#x200B;* 您變更了哪些doc檔案以及新增了哪些內容。
&#x200B;* 工作名稱和URL。
&#x200B;* 您設定的確切欄位值，包括預覽日期欄位。
&#x200B;* 您未完全放心的任何事情 — 例如Slack無法連線，而您只使用貼上的文字，目標檔案文章模稜兩可，或技術細節不在原始資料中，並被標籤而非猜測。

## 已知值（來自先前執行）

確認這些仍會解決，而不是假設它們是永久性的：

&#x200B;* 專案「產品檔案任務 — 適用於需要傳訊的開發問題」對應至ID `5e69583f00236b9f767c3e3944100ee4`
&#x200B;* 父系任務「Becky - Fusion-Documentation頻道中的任務」對應到ID `6a9b065100003a7554832780c2015e93` （在相同專案中） — 使用`insights_find_id_by_name` （實體`task`）解析，而不是硬式編碼，以防它變更
&#x200B;* 產品檔案自訂表單(`categoryID`)為`5d7275b9000514604bd969d418725843`
&#x200B;* 使用的自訂欄位： `DE:Release notes`、`DE:Preview Date Known`、`DE:Preview Date`

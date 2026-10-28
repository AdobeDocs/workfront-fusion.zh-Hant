---
applyTo: "help/workfront-fusion/**"
source-git-commit: 7c7e80b06b730fd56e581ebf74081f99e04318c0
workflow-type: tm+mt
source-wordcount: '3973'
ht-degree: 1%
---

# Fusion案例編輯器UI重新設計 — 專案附註

> 此檔案是儲存的Claude程式碼記憶體檔案(`fusion-scenario-editor-redesign.md`)的同步復本，因此GitHub Copilot具有相同的內容。 Claude的副本是真實來源 — 無論何時更新，該檔案都應更新以符合相同的編輯/認可。 如果兩者意見不一，請信任Claude記憶體檔案，然後重新同步處理此檔案。
>
> 這是範圍設定的Copilot指示檔案(`.github/instructions/*.instructions.md`)，不是整個存放庫的`.github/copilot-instructions.md`，因此只有當Copilot處理`help/workfront-fusion/`下的檔案時，才會套用它，而不是在存放庫中的每個要求上套用。

Becky正在許多文章中記錄Fusion的情境編輯器UI重新設計（新體驗與傳統體驗）。 這是&#x200B;**動態索引** — 每當擷取新的熒幕擷圖或確認新的UI詳細資料時，請更新此索引（不要只是附加），這樣任何（或任何助理）擷取此工作的人員都可以回答「我們已經有X的熒幕擷圖/事實嗎？」 而不重新衍生它。

分支`becky-updates-to-Fusion-scenario-editor`上發生工作。 主追蹤試算表： `C:\Users\rebeccas\Desktop\Fusion scenario editor UI redesign - affected articles.xlsx` （「受影響的文章」工作表=每個文章的狀態/優先順序；「功能比較」工作表=傳統與新功能比較）。

標幟這些檔案中任何未確認內嵌專案的慣例： `<!-- BECKY CHECK ME: ... -->`會直接在指定位置標幟，絕不會標幟為可見圖說文字。

## 熒幕擷圖詳細目錄（新體驗）

透過絕對路徑跨文章重複使用，而非複製檔案 — 例如`/help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/run-once-new.png`。

**`help/workfront-fusion/get-started-with-fusion/navigate-fusion/assets/`** （來自`scenario-editor.md`重寫 — 共用的UI Chrome圖示，可隨時隨地重複使用）：
`run-once-new.png` （執行一次，僅限圖示）、`save-icon-new.png`、`notes-icon-new.png`、`scheduling-new.png` （底部列排程切換+頻率標籤，例如「資料到達時」）、`auto-align-icon-new.png`、`scenario-editor-new.png` （完整畫布）、`top-bar-new.png`、`controls-new.png`、`tools-new.png`、`favorites-new.png`、`ask-ai-new.png`、`canvas-navigation-new.png`、`search-modules-icon-new.png`、`find-and-replace-icon-new.png`、`snippets-icon-new.png`、`explain-flow-icon-new.png`、`export-blueprint-icon-new.png`、`export-as-headless-template-icon-new.png`、`import-blueprint-icon-new.png`、`previous-version-icon-new.png`、`devtool-icon-new.png`、`scenario-settings-icon-new.png`、`additional-controls-new.png`。

**`help/workfront-fusion/build-practice-scenarios/assets/`** （來自基本案例教學課程）：
`new-placeholder-module.png` （空白畫布預留位置卡片）、`new-connector-picker.png` （應用程式/服務選擇器面板 — 左側類別清單：我的最愛、所有應用程式、Adobe Workfront、Adobe Firefly Services、Adobe Creative &amp; Content、Adobe Cloud Services、Generative AI、內建；搜尋右側）、`new-renamed-module.png`、`new-map-toggle.png`、`new-map-id.png`、`new-execution-bubble.png`、`clock-icon-on-watch-record.png` （卡片上的模組層級排程/時鐘徽章）、`new-map-in-filter.png` （以對應的專案 — ID條件設定篩選視窗）、`new-mapped-update-record.png` （將對應的ID對應至「更新記錄」模組）、`new-text-binary-function.png` （「T」對應面板）， `new-module-output-icon.png` （星型對映面板頁籤）、`new-mapped-name-block.png` （`upper(...)`內的對映名稱塊）。

**`help/workfront-fusion/create-scenarios/add-modules/assets/`**:
`add-a-module-between-modules.png` （用滑鼠右鍵按一下兩個模組→功能表之間的路徑：設定篩選/取消連結/新增路由器/新增模組/新增附註 — 擷取於尚未設定篩選/路由器的路徑，因此可能不是路由特定或承載路徑的完整選項）、`new-filter-setup-xml-example.png` （設定篩選視窗，符合`add-a-filter-to-a-scenario.md`中使用的File-Name-ends-with-.xml範例）、`fallback-route-new.png` （設定篩選視窗，核取並反白顯示，用於router-module.md）、`new-filter-specific-user.png` （在路由路徑上設定篩選視窗，標示為「特定使用者」、「備援」覈取方塊未選中，對映ID條件，橙色高亮顯示框 — 用於router-module.md的「將過濾器新增到新體驗中的路由」分步中）、`new-filter-specific-user-unmarked.png` （相同「特定使用者」過濾器，無高亮顯示框 — 用作router-module.md中if/else示例的`if`一半）、`new-not-specific-user-unmarked.png` （設定過濾器視窗，標籤為「非特定使用者」，已選中回退覈取方塊，無條件，無高亮顯示框 — 用作router-module.md中if/else示例的`else`一半）。

**尚未取得**：目前沒有尚未完成的router-module.md。

**`help/workfront-fusion/create-scenarios/config-error-handling/assets/`**:
`new-add-error-handler-in-menu.png` （以滑鼠右鍵按一下模組→設定內容功能表：僅執行此模組/新增錯誤處理常式/重新命名/複製/複製模組/新增備註/複製模組名稱/應用程式中繼資料/刪除模組 — 反白顯示「新增錯誤處理常式」 — 用於error-handling.md）、`new-error-handling-directives.png` （從錯誤處理常式開啟應用程式/服務選擇器，並選取專用的「錯誤處理」類別，顯示5個指令 — Break、Commit、Ignore、Resume、Rollback — 與左側面板中的一般應用程式類別並列；用於error-handling.md — 重新用於模組與路由器新增的錯誤處理常式）， `new-error-handler-examples-with-numbers.png`錯誤處理程式層次結構演練的示例場景，根據`scenario-editor.md`的畫布檢視切換在&#x200B;**緊湊檢視**&#x200B;中捕獲 — 在error-handling.md中使用；將影象描述為緊湊檢視以提高可讀性)。

**`help/workfront-fusion/get-started-with-fusion/understand-fusion/assets/`**:
`new-scenario-example-unmarked.png` (來源熒幕擷圖Becky已提供，未標籤 — 8模組Excel/Workfront使用者同步案例：監視新增的使用者→路由器→在Workfront中尋找使用者→路由器→ 3個分支[設定現有的使用者ID /在Workfront中建立新使用者→設定新的使用者ID /取得使用者ID變數→將使用者ID上傳至試算表] — 相同案例為傳統案例的`fusion-integration-example.png`和`fusion-glossary.md`的「案例」專案(`entire-scenario-blank.png`)；將此案例保留為相同範例中任何進一步標籤的來源)，`new-entire-scenario-scenario.png`，`new-scenario-trigger.png`，`new-scenario-module.png` `new-scenario-route.png` （全部通過紅色高亮框從以上未標籤的源派生 — 請參見每篇文章的註釋以瞭解確切的框位置）、`new-scenario-connectors.png` （Becky提供的，新Experience聯結器選取器中應用程式清單周圍的紅色框）、`new-scenario-segment.png` （Becky提供的，2個模組的Workfront Watch Events →轉換對象區段，盒裝，後跟未盒裝的Microsoft 365電子郵件模組）、`new-fusion-automation-example.png` (Becky提供的，未標籤，4個模組的Workfront僅示例 — 觀看記錄→獲取專案資訊→獲取「分配給」→建立更新 — 場景與經典的`fusion-template-example.png`相同； `license-automation-vs-integration.md`的「Workfront Fusion for Work Automation示例」部分（如果Becky也希望包含該部分）、`new-module.png` （來自`new-scenario-example-unmarked.png`的「在Workfront中查詢使用者」模組的單卡裁切，通過PowerShell/System.Drawing裁切 — 通常用於`fusion-glossary.md`的「模組」條目，無紅框）、`new-map-single.png`、`new-map-multiple-with-text.png`、`new-map-formula-with-text.png` （新體驗替換`mapping-overview.md`的shadebox示例：單項、帶文本的多個項以及帶多個項和文本的函式）、`new-mapping-panel-blank.png` (中使用的新體驗對映面板螢幕快照`mapping-overview.md`、`new-collection.png`（`mapping-overview.md`中使用的new-experience集合螢幕快照）、`new-collection-dropdown.png`（`mapping-overview.md`中使用並在`map-data-from-one-to-another.md`中重用的new-experience collection-element下拉選單螢幕快照）、`new-array.png`（`mapping-overview.md`中使用的new-experience array螢幕快照）。

**`help/workfront-fusion/create-scenarios/config-scenarios-settings/assets/`**:
`new-scenario-settings-ex-1.png` (2模組範例情境 — 標示為「關注傳入請求……」的關注紀錄 →標示為「將請求轉換為專案」的其他動作 — 用於configure-scenario-settings.md的Max-number-of-cycles範例)、`new-max-number-cycles.png` （在畫布上開啟的「情境設定」面板，透過「控制」區域中的齒輪圖示開啟，「最大週期數」欄位反白顯示值`1` — 用於configure-scenario-settings.md）。

## 確認的新體驗UI事實（不需要熒幕擷圖即可重複使用）

- 將滑鼠停留在模組的右邊緣，→出現&#x200B;**新增另一個模組**&#x200B;按鈕，按一→該按鈕，→開啟應用程式/服務選擇器（與新增第一個模組相同的選擇器）。
- 以滑鼠右鍵按一下模組→設定內容功能表（順序）：僅執行此模組/ **新增錯誤處理常式** /重新命名/複製/複製模組/新增附註/複製對應/複製模組名稱/應用程式中繼資料/ **刪除模組**。 兩者皆確認未變更傳統。
- 用滑鼠左鍵按一下兩個模組之間的路徑，→會直接開啟&#x200B;**設定篩選器**&#x200B;視窗。 以滑鼠右鍵按一下相同路徑，會開啟不同（較完整）的內容選單，而不是以「設定篩選」為選項的選單。
- 用滑鼠右鍵按一下路徑→ **新增路由器**&#x200B;和&#x200B;**新增模組**&#x200B;都是選項（請參閱`add-a-module-between-modules.png`）。
- **複製篩選器** / **貼上篩選器** （透過在已有篩選器的路徑上按一下滑鼠右鍵）仍存在且運作方式相同 — 視覺上重新設定樣式以符合新的卡片畫布，但選項/標籤相同。
- 按一下「路由器」模組本身（未將滑鼠懸停在其邊緣）仍會新增路由 — 確認未變更。
- **訂購路由** （以滑鼠右鍵按一下路由器模組→「訂購路由」→拖放） — 已確認仍然有效，與傳統未變更。
- **停用路由** （以滑鼠右鍵按一下路由的路徑→「停用路由」），以及停用的路由視覺效果（灰色路徑+標籤上的停用路由圖示） — 已確認傳統未變更。
- 路由器模組（「流量控制」>「路由器」）位於新選擇器的&#x200B;**內建**&#x200B;類別下（也出現在「所有應用程式」下，但內建是要在指示中引述的類別）。
- 備援路由：不同於傳統（在路由器模組本身以不同的箭頭標示），新體驗會以路由標籤上的綠色文字顯示&#x200B;**「備援」**&#x200B;來標示備援路由 — 這個事實不需要箭頭標籤熒幕擷圖。
- 錯誤處理常式路由：不同於傳統（透明與實心圓），新體驗會以虛線和紅色&#x200B;**「錯誤處理常式」**&#x200B;標籤標籤錯誤處理常式路由 — 此事實不需要熒幕擷圖。
- 模組名稱更正（實際的Workfront名稱，不是來自舊版草稿的拼字）： **「監看記錄」** （單數，而非「監看記錄」），**「更新記錄」** （非「更新記錄」）。
- **已解決DevTool問題（10/23/26，來自@vtigranyan的發行說明）：**&#x200B;獨立開發人員工具&#x200B;**未**&#x200B;移除。 設計工具中現在內建了七項工具（請參閱下面的[發行說明更新]）；**集中處理模組**、**透過對應**&#x200B;尋找模組，而且&#x200B;**Base64文字轉換程式**&#x200B;仍保留在DevTool中；Base64也可透過`base64()`和二進位轉換函式在對應中使用。 保留`create-a-scenario-workflow.md`中的[開啟DevTool]捷徑列。
- 仍未確認：選擇器的每列資訊圖示、版本V形和右下角快速存取泡泡圖的用途；選擇器的「我的最愛」類別是否與編輯器的「我的最愛」面板相同；如何摺疊/展開路由器（發行說明中未說明的控制項）。 請參閱特徵比較表。

## 為此重新設計所建立的House慣例（適用於所有剩餘文章）

- 完整平行複製：一個H2/H3樹狀結構用於「……在新體驗（建議）」，另一個單獨樹狀結構用於「……在傳統體驗」，具有`(Classic)`個必要尾碼以避免錨點衝突。 在目前有2個以上子系的任何標題下新增迷你目錄。
- 在文章介紹&#x200B;**（不是自己的H2）的**&#x200B;結尾，將「新說明與舊說明」摺疊為單一`>[!NOTE]`，重複使用此確切的措辭，並在連結後面附加「在文章案例編輯器中」：
  > Workfront Fusion正在將案例編輯器轉換為新體驗。 在此轉換期間，傳統體驗和新體驗皆可使用，而且您可以隨時在它們之間切換。 我們建議您使用新體驗。 如需詳細資訊，請參閱文章「情境編輯器」中的[新體驗和傳統體驗](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)。
- 新體驗標題包含`(Recommended)` （例如`## Add a filter in the new experience (Recommended)`）。
- 內容與UI完全無關（例如`add-a-module-basic.md`中的`?moduleId=` URL引數附註），不需要複製 — 使用判斷，但如有不確定（筆記移動前她已推回，但不詢問），請先與Becky核實。
- 如果Becky確認體驗之間的整個程式完全相同（不只是UI無關的備註），則根本不要將其分割成新的/傳統H2/H3 — 使用新的體驗措辭摺疊成單一程式（例如`view-scenario-data-flow.md`的「在執行案例中檢視資料流程」）。 預設的假設仍然是程式不同且需要分割 — 僅在明確確認後收合。
- 對於新視覺效果和傳統視覺效果真正不同的單一說明性熒幕擷圖（不是完整的逐步程式），請勿挑選其中一種或標籤並等待 — 先顯示兩者，新增：緊接在每個影像上方的純文字標籤行（「新體驗」/「傳統體驗」），先顯示新體驗。 先在周圍文章中提及新體驗行為（例如「……在新體驗中以X標籤，或在傳統體驗中以Y標籤」），而不僅僅是在影像標籤中。 檢視`view-scenario-data-flow.md`的執行/輸出指標。
- 將任何未確認的內嵌專案標示為`<!-- BECKY CHECK ME: ... -->` （從不會是可見的圖說文字）。
- 解析文章中的每個旗標後，請在追蹤試算表的「受影響的文章」工作表（欄G）中標示該列`Yes`。 如果只解析部分旗標，請使用`In progress`。 使用`Reopen`來代表`Yes`但其範圍已擴大的資料列（例如，在10/23/26發行說明比較之後）。
- 2026年10月23日新增的試算表標籤：開始為`NEW (10/23/26)`的列/附註（淺黃色列）是發行說明中的新專案；開始為`UPDATED (10/23/26)`的附註（淺橙色儲存格）是附加至現有列的新資訊。 在這些編輯之前備份試算表： `Fusion scenario editor UI redesign - affected articles - BACKUP 2026-10-23.xlsx` （案頭）。

## 發行說明更新(2026-10-23) — @vtigranyan檔案請求的新範圍

Source： Fusion Scenario Designer：新的UI/UX檔案請求；**預計發行版本2026-10-28**；需要宣告。 與2026年10月23日的試算表比較；其中會標籤新的列/附註（請參閱慣例）。 反白顯示：

- **開關：**「嘗試新設計」開關，在畫布的右上角；案例重新載入；已儲存每個使用者&#x200B;**&#x200B;** （不受影響的隊友）；如果組織尚未符合資格，則會隱藏。 意見反應在右上角控制。
- **畫布：**&#x200B;水準卡片（圖示、名稱、說明、模組ID）；路由器=精簡分支圖磚；指示=小型重點卡片；**曲線連結箭號；錯誤處理常式連結虛線**；綠色/黃色/紅色狀態指示器；詳細資訊會以放大方式顯示，模組會簡化為縮小圖示；**精簡檢視** =小型圖磚，更緊的格線，包裝的名稱，不會重新載入（不是「圖示」）；點格會隨情境縮放；**深色模式**；焦點=符合情境；迷你地圖顯示檢視區並支援點選和拖曳。
- **執行/排程：**&#x200B;執行一次、排程及排程開啟/關閉切換為單一精簡控制。
- **摺疊路由器分支** （編輯模式）：隱藏路由，顯示隱藏的路由/模組計數和警告/錯誤嚴重性；與情境一起儲存並與復原/重做搭配使用；搜尋、驗證、即時追蹤和歷程記錄會自動展開；執行檢閱一律會顯示所有內容。
- **模組瀏覽器：**&#x200B;搜尋優先；聯結器符合模組名稱/描述比對的等級；私人、進階、測試版的徽章；聯結器定義的模組群組；新增錯誤處理常式時優先處理的指令。
- **編輯：**&#x200B;復原/重做/全部復原；**尋找和取代** （變數、Source、連線標籤；整個案例或一個模組；預覽受影響的模組；選取列以顯示模組；複製與相同應用程式之一或所有相容模組的連線）；**程式碼片段** （搜尋、標籤、預覽、釘選、排序、拖放、匯入/匯出、與團隊/組織共用、傳送副本給使用者、共用標籤）。
- **一個右側固定**，用於模組設定/檢查/瀏覽、尋找和取代、片段、即時追蹤、要求/回應；巢狀檢視會以&#x200B;**上一步**&#x200B;動作取代目前的面板。
- **即時追蹤：**&#x200B;按時間順序排列的請求+執行活動清單；搜尋、狀態篩選、追蹤最新、清除；如果執行期間已關閉，請重新開啟控制項。 選取請求會顯示模組，並開啟請求/回應詳細資料（操作導覽、標頭/內文、複製原始報告或cURL）。
- **執行歷程記錄** （在編輯器中）：相同的主要/詳細模式；狀態、持續時間、作業、資料大小；狀態篩選器、事件搜尋；上次/下次執行；選取事件會以模組為中心。
- **執行 — 檢閱畫布工具：**&#x200B;移至下一個錯誤或警告（先發生錯誤，然後是警告，由左至右；若無則隱藏）、搜尋模組(Ctrl+K / ⌘K)、唯讀備註切換（僅限案例具有備註時）、說明流程（Esc至停止）、縮放/聚焦/迷你圖、壓縮檢視切換（不變更編輯模式設定；未儲存任何內容）。
- **執行一次/重新觸發程式：**&#x200B;相同的流程（包括原始JSON），重複使用先前的執行輸入，等待webhook； webhook和子案例輸入。
- **暫存偵錯記錄** （案例設定）：下一個1小時/ 1天/下一個執行/下一個10次執行；立即套用而不儲存；顯示「開啟直到」或左邊執行；關閉；自動關閉；每次執行計數（包括沒有新資料的排程執行）。 執行一次一律會保留請求/回應詳細資料。 僅限新設計工具、組織功能標幟，需要編輯許可權。
- **七項現在內建的開發人員工具：**&#x200B;應用程式中繼資料（按一下滑鼠右鍵模組）；複製對應（在來源模組上按一下滑鼠右鍵，貼到相容模組上）；複製篩選器（在篩選連結上按一下滑鼠右鍵，貼到其他連結上）；複製模組名稱/貼上模組名稱（在模組上按一下滑鼠右鍵）；交換連線/交換變數/重新對應來源（尋找和取代→連線/變數/Source索引標籤）。
- **未變更：**&#x200B;藍圖、對應、篩選器、排程、連線、路由器、錯誤處理常式、迭代器、彙總器、指令、執行一次、重新觸發器、執行歷史記錄、未完成執行、驗證、匯入/匯出、複製/貼上、自動對齊、鍵盤驅動編輯。

**已在試算表中重新開啟（欄G = `Reopen`，為`Yes`）：** `scenario-editor.md`，`add-a-module-basic.md`，`router-module.md` （加入摺疊路由器），`add-a-filter-to-a-scenario.md` （以複製/貼上篩選器取代DevTool相依性），`configure-scenario-settings.md` （加入暫存偵錯記錄檔），`view-a-specific-scenario-execution.md`，`view-scenario-execution-history.md`。

**左`Yes`，但已附加驗證備註：** `retrigger-specific-execution.md` （原始JSON /先前的輸入/ webhook選項）、`copy-modules-or-scenarios.md` （內建副本對應/模組名稱的選擇性連結）。

**新文章建立於10/26/26 （試算表列48-50，全部`Yes`；連結自`scenario-editor.md`並新增至`TOC.md`加上資料夾TOC）：** `create-scenarios/add-modules/use-snippets.md` （儲存並重複使用包含程式碼片段的案例區段）、`manage-scenarios/live-trail.md` （使用即時追蹤來檢閱案例執行）以及`manage-scenarios/find-and-replace.md` （尋找並取代案例中的變數、來源和連線）。 新文章省略`exl-id`/`TQID`前置事項（如果管道需要它們則新增）。 `debug-a-scenario.md`個即時追蹤的連結，並尋找及取代。

**狀態更新10/26/26：** `router-module.md`、`configure-scenario-settings.md`、`view-a-specific-scenario-execution.md`和`run-once.md`為`Yes`。 仍然`CHECK ME` （未完成的BECKY CHECK ME註解）： `scenario-editor.md` （第2列和第53列）、`debug-a-scenario.md` （第22列，也需要完整的新建/傳統重新建構）和`view-scenario-execution-history.md` （第33列）。 `add-a-module-basic.md`和`add-a-filter-to-a-scenario.md`仍為`Reopen` （篩選文章不需要編輯；新體驗複製篩選步驟已經存在，因此可將其設定回`Yes`）。

**已取代的舊備註：**&#x200B;先前建議的新文章候選專案為「即時軌跡」、「代碼片段」和「尋找和取代」；它們現在存在（以上）。 **其他新增：** `run-once.md` （執行一次，保留要求/回應）、`manage-connections.md` （推測）、案例編輯器常見問題集內容、視訊稽核範圍、發行說明（版本2026-10-28）。 `debug-a-scenario.md`在DevTool問題中已不再封鎖，但需要重新建構並加上指向內建工具和Live Trail的指標。

## 每個文章的狀態（試算表是真相的來源；以下截至2026-09-22的狀態，除非另有說明 — 請參閱上面的2026-10-23區段以取得重新開啟的列）

完整完成（0個旗標、試算表資料行G標示為`Yes`；`scenario-editor.md`、`add-a-module-basic.md`、`router-module.md`、`add-a-filter-to-a-scenario.md`、`configure-scenario-settings.md`、`view-a-specific-scenario-execution.md`和`view-scenario-execution-history.md`稍後變更為`Reopen`）： `scenario-editor.md`、`create-basic-scenario.md`、`add-trigger-to-basic-scenario.md`、`add-filter-basic-scenario.md`、`add-a-webhook-to-basic-scenario.md`、`use-function-to-build-practice-scenario.md`、`add-a-module-basic.md`、`add-a-filter-to-a-scenario.md`、`router-module.md` （列10）、`error-handling.md` （列15，已重新建構為「將錯誤處理常式新增至模組」和「……to a」的全新/傳統平行H3/H4樹狀結構router」）、`configure-scenario-settings.md`（行20 — 在跟蹤電子表格中標籤`Yes`，尚未更新）、`mapping-overview.md`（行35 — 電子表格現在標籤`Yes`；新增了標準轉換NOTE；所有使用新體驗影象`new-map-single.png`、`new-map-multiple-with-text.png`、`new-map-formula-with-text.png`、`new-mapping-panel-blank.png`、`new-collection.png`、`new-collection-dropdown.png`和`new-array.png`解析的螢幕快照標籤）、`move-modules-to-a-chain.md`（行28 — 電子表格現在標籤`Yes`；新增了標準轉換NOTE；確認了Beta功能的多選互動和移動至鏈新版Experience中的路徑相同，因此無需拆分）。 重新建構為新的/傳統H2/H3分割的「開啟案例設定」 — 新體驗使用現有的`scenario-settings-icon-new.png` （控制項區域，可能位於三點圖示後面），而不是傳統齒輪圖示。 「最大週期數」範例shadebox現在使用新體驗熒幕擷取畫面`new-scenario-settings-ex-1.png` （2模組範例情境，觀看記錄→雜項動作/轉換物件）和`new-max-number-cycles.png` （透過「控制」中的齒輪圖示開啟情境設定面板，反白顯示「最大週期數」欄位）。 第三個熒幕擷圖(`scenario-detail-350x207.png`)已完全捨棄 — 取代為文字：「您可以在「案例詳細資訊」頁面的「歷史記錄」區域中看到已執行的週期。」

`scenario-overview.md` （第34列 — 在追蹤試算表中標示`Yes`，但尚未在該處更新）：完整完成，0個旗標。 純粹的概念文章（沒有逐步「按一下X」的指示），因此不需要新的/傳統H2/H3分割 — 只是新增了標準轉換NOTE。 已解析全部8個原始旗標：
- 透過Becky未標籤的來源`new-scenario-example-unmarked.png`上以PowerShell/System.Drawing繪製的紅色反白方塊的4 （整體案例、觸發器、模組、路由） （裁切+縮放來源而非畫素掃描所找到的座標 — PowerShell 5.1中的填滿/畫素回圈處理在陣列vs純量怪異上持續失敗，而且速度仍然太慢）： `new-entire-scenario-scenario.png`、`new-scenario-trigger.png`、`new-scenario-module.png`、`new-scenario-route.png`。
- 2 （聯結器、案例區段）透過Becky提供的熒幕擷取畫面已標示： `new-scenario-connectors.png`、`new-scenario-segment.png`。
- 透過確認`fusion-integration-example.png` （傳統）解析的1 （整合範例）與`new-scenario-example-unmarked.png`完全相同 — 直接重複使用，沒有新的標籤。
- 1 （範本範例）以Becky未標籤的`new-fusion-automation-example.png`解析，符合傳統範例的`fusion-template-example.png` — 如果Becky也想要使用，也可在`license-automation-vs-integration.md`的「工作自動化的Workfront Fusion範例」區段中重複使用。

`view-scenario-data-flow.md` （第23列 — 在追蹤試算表中標示`Yes`，但尚未在該處更新）：完整完成，0個旗標。 新增標準轉換NOTE。 兩個體驗中的「檢視執行中案例的資料流程」已確認相同（Becky的呼叫 — 這裡不需要新的/傳統分割，不同於大多數其他程式） — 使用新體驗用語摺疊回單一程式（包括「按一下案例上的任何位置以進入案例編輯器」步驟），保持現有傳統熒幕擷圖`assets/currently-running.png`，因為執行歷程記錄面板已確認未變更。 兩個說明性的執行/輸出指標在視覺上確實有不同的體驗，因此 — 不同於常見的單一熒幕擷取畫面交換模式 — 舊熒幕擷取畫面與新熒幕擷取畫面並排顯示，各自上方有純文字標籤（新體驗/傳統體驗，新優先）：執行指標為`assets/new-spinning-icon.png` （模組圖示上的旋轉環）與傳統`assets/ring-around-module.png` （模組周圍的長環）；輸出指標為`assets/new-output-indicator.png`與傳統`assets/data-flow-output.png` （相同的綠色圓形計數 — 泡泡概念，已重新設定）。 此「顯示兩者，加上標籤，新優先，標籤在影像上方」的模式為自家慣例 — 請參閱上文。 描述性段落文字本身也提到了新體驗行為，然後是傳統體驗（例如「……以新體驗中模組圖示上的旋轉圈標籤，或傳統體驗中模組周圍的成長圈標籤。」）  — 新優先順序適用於散文，而不只是影像/標籤順序。

`fusion-glossary.md` （第43列 — 在追蹤試算表中標示`Yes`，但尚未在該處更新）：完整完成，0個旗標。 純字彙表，沒有程式。 在表格前新增標準轉換NOTE。 兩個內嵌影像（原始HTML `<img>`標籤，而非Markdown）均已解析且不需要使用者提供的新熒幕擷取畫面：「案例」專案的`entire-scenario-blank.png`與`new-scenario-example-unmarked.png`完全相同的案例（直接重複使用），而「模組」專案的`module.png`已取代為`new-module.png`，這是相同來源的單卡裁切。

已封鎖（與`debug-a-scenario.md`的處理方式相同 — 已標幟，未編輯超過標幟，欄G留白）： `advanced-error-handling.md` （列16）。 在簡介中新增了標準轉換NOTE，但其兩個範例（「範例：使用篩選器進行錯誤處理」和「巢狀範例」）是單一連續示範Dropbox情境，沒有逐步的「按一下X」內容以分割為新版/舊版 — 熒幕擷取畫面被刻意保留為經典畫面，按照Becky的指示不要零敲碎打。 已內嵌（在「###範例：使用篩選器處理錯誤」之前，以及巢狀`>[!BEGINSHADEBOX]`之前）標幟文章需要新體驗&#x200B;**中建置的**&#x200B;全新範例情境（Becky建議Workfront模組而非Dropbox），而不只是取代現有情境的熒幕擷取畫面。 試算表欄D和F以相同的範圍註記更新；欄G保持空白。

`scenario-execution-flow.md` （列40 — 試算表現在標籤為`Yes`）：完全完成，0個旗標。 新增標準轉換NOTE。 概念文章，因此不需要新的/傳統分割。 以新體驗資產取代三個傳統熒幕擷取畫面： `new-example-execution-flow-wf-only.png`、`new-example-execution-flow-wf-dropbox.png`和`new-Info-processed-bundles.png`。

`flow-control.md` （列42 — 試算表標示為`In progress`）：新增標準轉換NOTE。 在中繼器範例中標示了三個內嵌的熒幕擷取後續作業：用於開啟「流量控制」的熒幕底部`flow-control-icon.gif`路徑，加上兩個中繼器熒幕擷取畫面`repeater-2-350x207.png`和`repeater-3-350x207.png`，所有這些都可能顯示傳統案例編輯器。

截至2026-10-23年，未涵蓋之列的試算表狀態：列9、12-15、17-19、21、27、29-31、36-38、42的`Yes` （即使上述較舊的附註顯示進行中，試算表中的`flow-control.md`仍為`Yes`）。 `Blocked`: `run-scenario-scoring.md`. `On Hold`: `view-and-resolve-incomplete-executions.md`. 空白/未開始： `advanced-error-handling.md` （需要新的範例案例）、`debug-a-scenario.md` （需要重新建構）、`scenario-details.md`、`scenario-execution-cycles-phases.md`、`view-chained-scenario-relationships.md`、`fusion-basics-videos.md`、發行說明列，以及`create-a-scenario-workflow.md` （保留DevTool捷徑列）。

（先前的「試算表尚未更新」備註已過時 — 試算表已針對這些文章進行了更新。）


## 最終狀態同步(2026-10-27) — 取代上述狀態陳述式

試算表（「受影響的文章」，欄G）是真相的來源。 版本：新的案例編輯器體驗，2026-10-28。

**`Yes`（完整）：**&#x200B;以下未列出的所有資料列，包括先前`Reopen`篇文章(`scenario-editor.md`、`add-a-module-basic.md`、`router-module.md`、`add-a-filter-to-a-scenario.md`、`configure-scenario-settings.md`、`view-a-specific-scenario-execution.md`、`view-scenario-execution-history.md`)、10/27編輯的10個以上文章(`scenario-details.md`、`manage-connections.md`、`scenario-execution-cycles-phases.md`、`view-chained-scenario-relationships.md`、`run-once.md`)、三篇新文章和發行說明。

**`OK for now - revisit`：** `advanced-error-handling.md` （範例情境仍舊是傳統情境；有內嵌附註；稍後會在新體驗中重新建置）和`fusion-basics-videos.md` （第45和54列；文章中有視訊稽核註解；可能新增即時追蹤/DevTool逐步解說視訊）。

**`Check after release`：** `debug-a-scenario.md` （即時資料流區段已保留，因為它在新體驗中顯示「沒有可用的事件」，可能是錯誤；請確認是否已從DevTool移除七個內建工具；可能需要新的/傳統分割情境偵錯工具）、`run-scenario-scoring.md`和`view-and-resolve-incomplete-executions.md`。

**新增/變更10/27 （全部由Becky解析）：**
- `debug-a-scenario.md`： DevTool左側導覽現在有第四個專案，**DevTool說明** （問號圖示）；「工具」面板有&#x200B;**依名稱搜尋工具**&#x200B;欄位和選取工具提示；所有10個工具保留在DevTool中； DevTool會從「控制項」三點功能表或透過在畫布的空白區域按一下滑鼠右鍵來開啟； Scenario Debugger步驟已展開（包含ID徽章的模組清單、依名稱或ID搜尋、循環/作業、要求標題/要求內文/回應標題/回應內文標籤，**複製RAW**&#x200B;和&#x200B;**複製cURL**）。
- `add-a-module-basic.md`：搜尋優先選擇器、具有&#x200B;**後退**&#x200B;的右側面板、徽章（私人、進階、測試版）、聯結器定義的模組群組、新增錯誤處理常式時的優先指令。 仍未確認：選擇器資訊圖示、版本>形箭號、快速存取泡泡。
- `scenario-editor.md`： **意見反應**&#x200B;按鈕（右上角，緊鄰壓縮檢視）已新增到「編輯」動作；「案例」設定列連結到「暫時」偵錯記錄；切換器是每個使用者都有，可能不是每個組織都有。
- `scenario-details.md`和`view-chained-scenario-relationships.md`現在使用`/help/workfront-fusion/manage-scenarios/assets/new-exit-editing-arrow.png`。
- `manage-connections.md`個要尋找和取代的連結。
- 發行說明： `fusion-product-releases/fusion-releases-2026/fusion-2026-10-26.md` （10月26日當週），已新增至`fusion-release-activity.md`和`TOC.md`。

**發行後開啟後續追蹤：**&#x200B;新區段和文章的熒幕擷取畫面；如何摺疊/展開路由器；如何從編輯器開啟[執行歷程記錄]面板；選擇器資訊圖示/V形/泡泡；選擇器與[編輯器我的最愛]；重新擷取`scenario-execution-cycles-phases.md` （ACID徽章）、`scenario-details.md`中的傳統熒幕擷取畫面，以及`advanced-error-handling.md`中的DataError篩選器。

**存放庫備註：**&#x200B;除非詢問，否則不會認可；~466個檔案僅因行結尾(CRLF)而顯示為已修改；請勿從沙箱執行`git status` （它可以留下`.git/index.lock`）。

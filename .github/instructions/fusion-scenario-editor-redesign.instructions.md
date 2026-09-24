---
applyTo: "help/workfront-fusion/**"
source-git-commit: e3e28f86494207dd5e674a2882887d00da6a0c61
workflow-type: tm+mt
source-wordcount: '2352'
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
`new-scenario-example-unmarked.png` (來源熒幕擷圖Becky已提供，未標籤 — 8模組Excel/Workfront使用者同步案例：監視新增的使用者→路由器→在Workfront中尋找使用者→路由器→ 3個分支[設定現有的使用者ID /在Workfront中建立新使用者→設定新的使用者ID /取得使用者ID變數→將使用者ID上傳至試算表] — 相同案例為傳統案例的`fusion-integration-example.png`和`fusion-glossary.md`的「案例」專案(`entire-scenario-blank.png`)；將此案例保留為相同範例中任何進一步標籤的來源)，`new-entire-scenario-scenario.png`，`new-scenario-trigger.png`，`new-scenario-module.png` `new-scenario-route.png` （全部通過紅色高亮框從以上未標籤的源派生 — 請參見每篇文章的註釋以瞭解確切的框位置）、`new-scenario-connectors.png` （Becky提供的，新Experience聯結器選取器中應用程式清單周圍的紅色框）、`new-scenario-segment.png` （Becky提供的，2個模組的Workfront Watch Events →轉換對象區段，盒裝，後跟未盒裝的Microsoft 365電子郵件模組）、`new-fusion-automation-example.png` (Becky提供的，未標籤，4個模組的Workfront僅示例 — 觀看記錄→獲取專案資訊→獲取「分配給」→建立更新 — 場景與經典的`fusion-template-example.png`相同； `license-automation-vs-integration.md`的「Workfront Fusion for Work Automation示例」部分（如果Becky也希望包含該部分），`new-module.png` （來自`new-scenario-example-unmarked.png`的「在Workfront中查詢使用者」模組的單卡裁切，通過PowerShell/System.Drawing裁切 — 通常用於`fusion-glossary.md`的「模組」條目，無紅色框）。

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
- 仍未確認並封鎖`debug-a-scenario.md` +其他幾篇文章： **DevTool**&#x200B;是否從新體驗中移除（傳聞時未見，尚無其他詳細資料 — 請參閱功能比較表「DevTool」列）。

## 為此重新設計所建立的House慣例（適用於所有剩餘文章）

- 完整平行複製：一個H2/H3樹狀結構用於「……在新體驗（建議）」，另一個單獨樹狀結構用於「……在傳統體驗」，具有`(Classic)`個必要尾碼以避免錨點衝突。 在目前有2個以上子系的任何標題下新增迷你目錄。
- 在文章介紹&#x200B;**（不是自己的H2）的**&#x200B;結尾，將「新說明與舊說明」摺疊為單一`>[!NOTE]`，重複使用此確切的措辭，並在連結後面附加「在文章案例編輯器中」：
  > Workfront Fusion正在將案例編輯器轉換為新體驗。 在此轉換期間，傳統體驗和新體驗皆可使用，而且您可以隨時在它們之間切換。 我們建議您使用新體驗。 如需詳細資訊，請參閱文章「情境編輯器」中的[新體驗和傳統體驗](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)。
- 新體驗標題包含`(Recommended)` （例如`## Add a filter in the new experience (Recommended)`）。
- 內容與UI完全無關（例如`add-a-module-basic.md`中的`?moduleId=` URL引數附註），不需要複製 — 使用判斷，但如有不確定（筆記移動前她已推回，但不詢問），請先與Becky核實。
- 如果Becky確認體驗之間的整個程式完全相同（不只是UI無關的備註），則根本不要將其分割成新的/傳統H2/H3 — 使用新的體驗措辭摺疊成單一程式（例如`view-scenario-data-flow.md`的「在執行案例中檢視資料流程」）。 預設的假設仍然是程式不同且需要分割 — 僅在明確確認後收合。
- 對於新視覺效果和傳統視覺效果真正不同的單一說明性熒幕擷圖（不是完整的逐步程式），請勿挑選其中一種或標籤並等待 — 先顯示兩者，新增：緊接在每個影像上方的純文字標籤行（「新體驗」/「傳統體驗」），先顯示新體驗。 先在周圍文章中提及新體驗行為（例如「……在新體驗中以X標籤，或在傳統體驗中以Y標籤」），而不僅僅是在影像標籤中。 檢視`view-scenario-data-flow.md`的執行/輸出指標。
- 將任何未確認的內嵌專案標示為`<!-- BECKY CHECK ME: ... -->` （從不會是可見的圖說文字）。
- 解析文章中的每個旗標後，請在追蹤試算表的「受影響的文章」工作表（欄G）中標示該列`Yes`。 如果只解析部分旗標，請使用`In progress`。

## 每個文章的狀態（截至2026-09-22）

完整完成（0個旗標，試算表資料行G標示為`Yes`）： `scenario-editor.md`、`create-basic-scenario.md`、`add-trigger-to-basic-scenario.md`、`add-filter-basic-scenario.md`、`add-a-webhook-to-basic-scenario.md`、`use-function-to-build-practice-scenario.md`、`add-a-module-basic.md`、`add-a-filter-to-a-scenario.md`、`router-module.md` （列10）、`error-handling.md` （列15，已針對「將錯誤處理常式新增至模組」和「……新增至路由器」重新建構為新的/傳統並行H3/H4樹狀結構）、`configure-scenario-settings.md` （列20 — 在追蹤試算表中標示為`Yes`，尚未更新）。 重新建構為新的/傳統H2/H3分割的「開啟案例設定」 — 新體驗使用現有的`scenario-settings-icon-new.png` （控制項區域，可能位於三點圖示後面），而不是傳統齒輪圖示。 「最大週期數」範例shadebox現在使用新體驗熒幕擷取畫面`new-scenario-settings-ex-1.png` （2模組範例情境，觀看記錄→雜項動作/轉換物件）和`new-max-number-cycles.png` （透過「控制」中的齒輪圖示開啟情境設定面板，反白顯示「最大週期數」欄位）。 第三個熒幕擷圖(`scenario-detail-350x207.png`)已完全捨棄 — 取代為文字：「您可以在「案例詳細資訊」頁面的「歷史記錄」區域中看到已執行的週期。」

`scenario-overview.md` （第34列 — 在追蹤試算表中標示`Yes`，但尚未在該處更新）：完整完成，0個旗標。 純粹的概念文章（沒有逐步「按一下X」的指示），因此不需要新的/傳統H2/H3分割 — 只是新增了標準轉換NOTE。 已解析全部8個原始旗標：
- 透過Becky未標籤的來源`new-scenario-example-unmarked.png`上以PowerShell/System.Drawing繪製的紅色反白方塊的4 （整體案例、觸發器、模組、路由） （裁切+縮放來源而非畫素掃描所找到的座標 — PowerShell 5.1中的填滿/畫素回圈處理在陣列vs純量怪異上持續失敗，而且速度仍然太慢）： `new-entire-scenario-scenario.png`、`new-scenario-trigger.png`、`new-scenario-module.png`、`new-scenario-route.png`。
- 2 （聯結器、案例區段）透過Becky提供的熒幕擷取畫面已標示： `new-scenario-connectors.png`、`new-scenario-segment.png`。
- 透過確認`fusion-integration-example.png` （傳統）解析的1 （整合範例）與`new-scenario-example-unmarked.png`完全相同 — 直接重複使用，沒有新的標籤。
- 1 （範本範例）以Becky未標籤的`new-fusion-automation-example.png`解析，符合傳統範例的`fusion-template-example.png` — 如果Becky也想要使用，也可在`license-automation-vs-integration.md`的「工作自動化的Workfront Fusion範例」區段中重複使用。

`view-scenario-data-flow.md` （第23列 — 在追蹤試算表中標示`Yes`，但尚未在該處更新）：完整完成，0個旗標。 新增標準轉換NOTE。 兩個體驗中的「檢視執行中案例的資料流程」已確認相同（Becky的呼叫 — 這裡不需要新的/傳統分割，不同於大多數其他程式） — 使用新體驗用語摺疊回單一程式（包括「按一下案例上的任何位置以進入案例編輯器」步驟），保持現有傳統熒幕擷圖`assets/currently-running.png`，因為執行歷程記錄面板已確認未變更。 兩個說明性的執行/輸出指標在視覺上確實有不同的體驗，因此 — 不同於常見的單一熒幕擷取畫面交換模式 — 舊熒幕擷取畫面與新熒幕擷取畫面並排顯示，各自上方有純文字標籤（新體驗/傳統體驗，新優先）：執行指標為`assets/new-spinning-icon.png` （模組圖示上的旋轉環）與傳統`assets/ring-around-module.png` （模組周圍的長環）；輸出指標為`assets/new-output-indicator.png`與傳統`assets/data-flow-output.png` （相同的綠色圓形計數 — 泡泡概念，已重新設定）。 此「顯示兩者，加上標籤，新優先，標籤在影像上方」的模式為自家慣例 — 請參閱上文。 描述性段落文字本身也提到了新體驗行為，然後是傳統體驗（例如「……以新體驗中模組圖示上的旋轉圈標籤，或傳統體驗中模組周圍的成長圈標籤。」）  — 新優先順序適用於散文，而不只是影像/標籤順序。

`fusion-glossary.md` （第43列 — 在追蹤試算表中標示`Yes`，但尚未在該處更新）：完整完成，0個旗標。 純字彙表，沒有程式。 在表格前新增標準轉換NOTE。 兩個內嵌影像（原始HTML `<img>`標籤，而非Markdown）均已解析且不需要使用者提供的新熒幕擷取畫面：「案例」專案的`entire-scenario-blank.png`與`new-scenario-example-unmarked.png`完全相同的案例（直接重複使用），而「模組」專案的`module.png`已取代為`new-module.png`，這是相同來源的單卡裁切。

已封鎖（與`debug-a-scenario.md`的處理方式相同 — 已標幟，未編輯超過標幟，欄G留白）： `advanced-error-handling.md` （列16）。 在簡介中新增了標準轉換NOTE，但其兩個範例（「範例：使用篩選器進行錯誤處理」和「巢狀範例」）是單一連續示範Dropbox情境，沒有逐步的「按一下X」內容以分割為新版/舊版 — 熒幕擷取畫面被刻意保留為經典畫面，按照Becky的指示不要零敲碎打。 已內嵌（在「###範例：使用篩選器處理錯誤」之前，以及巢狀`>[!BEGINSHADEBOX]`之前）標幟文章需要新體驗&#x200B;**中建置的**&#x200B;全新範例情境（Becky建議Workfront模組而非Dropbox），而不只是取代現有情境的熒幕擷取畫面。 試算表欄D和F以相同的範圍註記更新；欄G保持空白。

未開始：追蹤試算表中的其他所有專案（`debug-a-scenario.md`在DevTool確認時遭到封鎖；其餘專案則未遭觸及）。

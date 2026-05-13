---
name: document-fusion-module
description: 將新的Adobe Workfront Fusion聯結器模組新增至help/workfront-fusion/references/apps-and-modules/底下的適當聯結器文章中，加以記錄。 當使用者要求新增、記錄或說明新的Fusion模組時使用，或是當使用者提供Fusion模組設定面板的熒幕擷取畫面，且希望更新對應的文章時使用。
source-git-commit: 976db79104d226a16a35dc04e8c8cb111eb745db
workflow-type: tm+mt
source-wordcount: '1609'
ht-degree: 0%

---


# 記錄Fusion聯結器模組

使用此技能將一個或多個新模組新增到Workfront Fusion Connector文章（例如，`adobe-firefly-modules.md`、`adobe-photoshop-modules.md`、`azure-dev-ops.md`）。

## 必要輸入（每個模組）

在填入任何模組的欄位之前，使用者&#x200B;**必須**&#x200B;提供以下所有內容。 如果有任何遺失，請先停止並詢問再繼續。

1. **模組名稱** — 與Fusion UI中顯示的名稱完全相同（例如，`Generate adaptive composite`）。
2. **聯結器文章路徑** — 代理程式找到此專案並向使用者確認（請參閱階段1）。
3. **基礎API作業的API URL**。 這是必要專案，以便可根據API規格交叉參考每個欄位的用途。
4. **標準檢視中模組組態面板的熒幕擷圖** （`Show advanced settings` **未勾選**）。
5. **進階檢視中模組組態面板的熒幕擷圖** （`Show advanced settings` **已勾選**），或模組沒有進階欄位的明確陳述式。

## 工作流程

這是一個多階段的程式。 步調很重要 — 與使用者&#x200B;*合作，而不是在他們之前*。 確認每個階段邊界的進度，並隨時接受更正。

### 階段1 — 工作範圍

1. **詢問這是否為一個模組或多個模組**： *「您是否要將單一模組或多個模組新增至聯結器文章？」*

2. **根據答案預先收集每個模組名稱**：
   - **單一模組**：詢問其在Fusion UI中顯示的確切名稱。
   - **多個模組**：一次詢問所有名稱，或是詢問列出這些名稱的聯結器熒幕擷圖（例如，Fusion中的聯結器概觀畫面，顯示每個模組的圖磚標籤）。 無論如何，請在結束此步驟時，提供每個要新增新模組的確認清單。

3. **根據模組所隱含的聯結器名稱搜尋`help/workfront-fusion/references/apps-and-modules/`，自行尋找聯結器文章**。 使用`Glob`或`Grep`工具。

4. **與使用者確認文章路徑**： *「根據模組名稱，這應該在`help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-firefly-modules.md`之內。 正確嗎？&quot;*

5. **閱讀聯結器文章**&#x200B;以瞭解其現有結構和慣例。 請注意：
   - 標題樣式（通常為句子大小寫中的`### Module name`）
   - 現有模組順序（通常按字母順序）
   - `Connection`列的措辭
   - 巢狀欄位的寫入方式（例如，`Image > Source`）
   - 任何現有的註腳或註解慣例

### 階段2 — 將每個模組的預留位置放在前面

即使只有一個新模組，這也能為使用者提供清晰的視覺藍圖。 如果有多個新模組，請立即放置所有模組。

針對每個新模組，在字母位置插入預留位置區段：

```markdown
### Module name

<!-- PLACEHOLDER: Add description of the Module name module here. -->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>For instructions on creating a connection to [!DNL Connector Name], see <a href="#create-a-connection-to-connector-name" class="MCXref xref" >Create a connection to [!DNL Connector Name]</a> in this article.</td> 
  </tr> 
  <!-- PLACEHOLDER: Add field rows for the Module name module here. -->
 </tbody> 
</table>
```

向使用者顯示已新增的預留位置清單（例如「新增的預留位置：產生最適化複合、使用Image5產生影像、產生精確複合、產生視訊」）。 接著詢問您要從哪個開始： *&quot;您想從哪個開始？&quot;*

### 階段3 — 每個模組的檔案回圈

對於每個模組，請先完全完成此回圈，然後再繼續進行下一個模組：

#### 3a。 取得API URL

詢問使用者API URL： *「請共用`<module name>`基礎API作業的API URL。」*

擁有時：
- 在URL上嘗試`WebFetch`。
- 如果頁面是空的/JS轉譯（與Adobe Developer檔案通用），請尋找相關的功能指南頁面（通常位於`.../guides/how-tos/...` URL）並改為擷取。
- 如果還是不走運，請將作業名稱回覆為`WebSearch`。

將您學到的任何內容用作背景內容，以便稍後提供欄位說明。 不要將其傾印到使用者上；只要簡短確認即可： *&quot;取得API內容 — 準備好使用標準檢視熒幕擷圖。&quot;*

#### 3b. 取得標準檢視熒幕擷圖

詢問： *&quot;請與`Show advanced settings`**取消核取**&#x200B;共用模組設定面板的熒幕擷圖。 處理完標準欄位後，我會要求進階檢視，但暫時不要傳送。」*

#### 3c. 記錄標準欄位

使用標準檢視熒幕擷圖，從上到下擷取每個可見欄位。 針對每個欄位：

1. 使用欄位的確切UI標籤作為列標題。 針對群組欄位，與` > `聯結：

   ```
   [!UICONTROL Background > Image > Source]
   ```

2. 閱讀熒幕擷圖欄位下方的協助程式文字（灰色/黃色標題）。 以它作為說明的基礎。
3. 從步驟3a互動參照API內容，以識別欄位代表的意義（例如，`background.fillAreaMask`是「將放置物件的背景區域」）。
4. 將&#x200B;**什麼欄位是** （來自API）與&#x200B;**如何提供** （來自UI協助程式文字和欄位型別）結合以撰寫說明。

略過熒幕擷圖中未顯示的任何欄位，即使API支援此欄位。 不要發明欄位。

標準欄位就緒後，向使用者簡短摘要標準欄位（例如「新增的標準欄位：連線、提示、外觀比例……」），然後移至步驟3d。

#### 3d 取得進階檢視熒幕擷圖

詢問： *&quot;現在，請與`Show advanced settings`**核取**&#x200B;共用模組設定面板的熒幕擷圖。 如果模組沒有進階欄位，請這麼說，我們將略過前面。」*

#### 3e. 記錄進階欄位

使用進階檢視熒幕擷圖：

1. 識別&#x200B;*不是*&#x200B;的欄位已經在標準檢視中 — 這些是進階欄位。
2. 對於每個進階欄位，請遵循與步驟3c相同的說明程式。
3. 將`*`附加至`<td role="rowheader">`內的欄位名稱：

   ```html
   <td role="rowheader">[!UICONTROL Seeds]*</td>
   ```

4. 在結束`</table>`後，在其自己的行上新增此註腳：

   ```markdown
   * These fields are advanced fields, and do not display unless you select **[!UICONTROL Show advanced settings]**.
   ```

如果使用者說模組沒有進階欄位，請完全略過步驟3d和3e。

#### 3f. 草稿模組說明

現在（不要再往前），根據API內容和欄位意思，以一句草稿取代區段頂端的說明預留位置。 一律提供草稿供使用者檢閱：

> *&quot;我草擬此描述： &#39;...&#39;。 想要使用它、編輯它或取代它嗎？&quot;*

#### 3g。 每個模組總結

向使用者提供模組已記錄欄位的最終摘要（標準+進階），並顯示任何未完成的問題：

- 熒幕擷取畫面中是否有任何欄位被切斷？
- 模組說明是否可接受？
- 任何專案應該標示為過時或值得注意？

請等候確認，再說模組已完成。 然後詢問： *&quot;準備好繼續下一模組嗎？&quot;* （或「我們已經完成這篇聯結器文章」。）

### 階段4 — 最終驗證

在記錄所有模組後，逐一進行此檢查清單：

- [ ]模組標題為`### ` (H3)且使用句子大小寫。
- [ ]模組會依其同層級模組的字母順序顯示。
- [ ]第一列為`Connection`，且使用標準的連線連結措辭。
- [ ]每個記錄的欄位都會顯示在使用者的熒幕擷取畫面中。
- [ ]進階欄位標有`*`，而且表格下方有單一註腳。
- [ ]沒有單獨從API發明的欄位。
- [ ] Source下拉式清單說明使用確切的UI選項標籤（請參閱下方的「Source欄位慣例」）。
- [ ]模組說明是單句摘要，說明模組的功能。

## Source欄位慣例

Fusion聯結器中的影像來源欄位通常會呈現包含兩個選項的下拉式清單。 **使用使用者熒幕擷圖中所顯示的確切標籤** — 不同世代的模組使用不同的措辭：

| 如果下拉式清單顯示…… | 使用此格式 |
|---|---|
| **上傳影像**&#x200B;和&#x200B;**影像URL** （較新的模組） | `<ul><li><b>Upload Image</b><p>Upload the image, or map the image file from a previous module.</p></li><li><b>Image URL</b><p>Enter or map the URL of the image.</p></li></ul>` |
| **檔案**&#x200B;和&#x200B;**預先簽署的URL** （較舊的模組） | `<ul><li><b>File</b><p>Select a source file from a previous module, or map the source file's reference image file name and reference image file.</p></li><li><b>Presigned URL</b><p>Enter or map the URL of the source image.</p></li></ul>` |

如果熒幕擷圖未顯示開啟的下拉式清單選項，請要求使用者共用它們。

## 欄位說明樣式

- 比對同一篇文章中現有模組專案的聲音和結構。
- 保持說明簡短：通常每個欄位一兩個句子就夠了。
- 針對從其他欄位參考的任何UI欄位名稱使用`[!UICONTROL ...]`標籤。
- 常值使用`<code>...</code>` (`<code>en-US</code>`， `<code>0.0</code>`)。
- 針對數值範圍欄位，明確指出允許的範圍： *&quot;輸入介於0到1之間的數字……&quot;*。
- 對於包含分散式選項的下拉式清單，請以`<b>Option</b>`後面接著`<p>`說明的`<ul>`來列舉。

## 常見欄位和建議的說明

重複使用這些動作，以維持模組間的一致性：

**種子** （當欄位透過[新增]專案允許多個種子值時）：
> 按一下&#x200B;**新增專案**&#x200B;以新增種子值，然後輸入或對應整數。 每個變數使用一個種子。 如果同時提供這兩個值，則種子值的計數必須符合&#x200B;**變數數目**&#x200B;值。

**變數數目** （以熒幕擷圖中的實際範圍取代範圍）：
> 輸入介於[分鐘]到[最大]之間的數字。 模組會產生此數量的[輸出型別]變數。

**限制** （標準Fusion執行週期限制；只有在熒幕擷圖中顯示時才會包含）：
> 輸入或對應您希望模組在一個執行週期內使用的最大結果數量。

**地區設定**：
> 輸入或對應語言與地區代碼，將產生的內容量身訂做特定的國家/地區和語言。 地區必須以ISO 639-1語言代碼和ISO 3166-1區域提供。 範例：`en-US`

## 隨時接受更正

使用者可能會在流程中更正先前的工作 — 種子措辭、下拉式標籤、欄位定位、進階/標準分割等。將任何更正視為權威性且無需後推即可更新。 修正後，簡短摘要變更內容。

如果使用者引入新的慣例中間流程（例如，「讓我們使用`*`標籤進階欄位並新增註腳」），請將其用於工作階段的其餘部分，並將其回溯套用至已記錄的任何模組。

## 如果資訊發生衝突，該怎麼辦

當API規格和UI不同意（這經常發生）：

1. **信任UI**，因為這是使用者在Fusion中實際看到的內容。
2. **請注意您回覆使用者的差異**，以便他們決定是否進一步調查。
3. **不要在文章本文中發明說明** — 請如實說明UI中的內容。

如果使用者的兩個熒幕擷取畫面相互矛盾（例如，其中一個顯示`Blend`，另一個顯示相同模組的`Harmonization`），請先停止並詢問哪個熒幕擷取畫面是正確的，再開始撰寫。 交叉參考API規格，識別可能屬於不同模組的熒幕擷取畫面。

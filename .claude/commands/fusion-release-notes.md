---
name: fusion-release-notes
description: 建立新的Workfront Fusion每週發行說明頁面，並將其連結至發行活動概觀頁面和目錄。 當使用者想要撰寫、新增或草擬新的Fusion版本注意事項或每週發行頁面，或要求為版本記錄新的Fusion功能時使用。 請勿在product-announcements/product-releases中使用Workfront (Quicksilver)發行說明 — 針對這些使用發行說明 — formatter。
source-git-commit: 59a8d8ee83906bc16fc627bd348accc4e588cf9b
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 1%

---


# Fusion發行說明

在`help/workfront-fusion/fusion-product-releases/`中建立新的每週Adobe Workfront **Fusion**&#x200B;發行說明頁面，並從兩個可發現位置連結該頁面：發行活動概觀頁面和`help/workfront-fusion/TOC.md`。

這是與`release-notes-formatter`技能處理的Quicksilver （核心Workfront）發行說明不同的系統：

| | Fusion發行說明（這項技能） | Quicksilver發行說明(`release-notes-formatter`) |
|---|---|---|
| 步調 | 每週 | 每季 |
| 目錄 | `help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/` | `help/quicksilver/product-announcements/product-releases/` |
| 每個功能的日期圖說文字 | 否 — 頁面標題包含周 | 是 — 每個功能`>[!NOTE]`個區塊 |
| 索引頁面 | `fusion-release-activity.md` （依年/月） | `{YY}-q{N}-release-overview.md` （依季度） |

## 步驟1：收集特徵

詢問使用者（如果尚未提供）本週的功能/變更清單，以及每個功能/變更清單：

- 簡短的功能標題
- 清楚說明變更內容及重要原因
- 連結到的說明文章（確認路徑存在 — 請勿猜測）
- 需要使用者/管理員動作還是已過時（需要`>[!IMPORTANT]`圖說文字）

## 步驟2：決定檔案名稱和日期

- 尋找檔案說明當週的星期一（或發行日期），如有模稜兩可，請向使用者確認。
- 檔案路徑： `help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md`
  - `{M}`和`{D}`沒有&#x200B;**前導零**： `fusion-2026-7-20.md`，而不是`fusion-2026-07-20.md`。
  - 如果year資料夾尚不存在，請建立它。
- 在建立新頁面之前，請先檢查該周的頁面是否已存在。

## 步驟3：撰寫頁面

### Frontmatter

```yaml
---
title: Workfront Fusion release activity Week of {Month} {Day}, {Year}
description: Workfront Fusion release activity Week of {Month} {Day}, {Year}
author: {Author}
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
---
```

規則：
- `title`和`description`相同。
- 在日期(`July 20, 2026`)中一律包含逗號，即使某些較舊的頁面會省略該逗號 — 請勿複製該不一致之處。
- **每個新頁面都使用`hidefromtoc: true`。 不要新增`exl-id`或`TQID`.** 這些會在發佈頁面後指派；發明一個是錯誤的。 （自2026年中起的頁面全都遵循此模式 — 如果您需要檢查範例，請參閱`_fusion-release-notes-reference.md`。）

### 正文

```markdown
# Workfront Fusion release activity: Week of {Month} {Day}, {Year}

This page describes all enhancements made in Adobe Workfront Fusion the week of {Month} {Day}, {Year}.

For a list of all recent changes, see [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

For a list of recent bug fixes in Workfront Fusion, see the [Workfront Maintenance Updates](https://experienceleague.adobe.com/en/docs/workfront-known-issues/releases/current-updates) page and check for any updates labeled Workfront Fusion Maintenance Update.

## {Feature title}

Feature description paragraph(s) — what changed, why, and how it affects existing scenarios/configurations if relevant.

For more information, see [{Help article title}](/help/workfront-fusion/{path-to-article}.md).

## {Next feature title}

...
```

附註:
- 每個功能各一個H2，依使用者提供給他們的順序（頁面內沒有強制的最新優先排序 — 只需一週）。
- 沒有每個功能的`>[!NOTE]`日期圖說文字 — 頁面標題已經包含日期。
- 如果功能需要執行動作或屬於重大變更/淘汰，請直接在H2下方、說明之前新增`>[!IMPORTANT]`圖說文字：

  ```markdown
  ## {Feature title}
  
  >[!IMPORTANT]
  >
  >**Action Required: {short summary of what the user must do and by when}**
  >
  >{Details of the requirement.}
  
  {Regular description paragraph(s).}
  ```
- 每個功能都應以「如需詳細資訊，請參閱[...]」結尾 相關說明文章的連結。 確認存放庫中存在連結目標。

## 步驟4：將頁面新增至綜覽索引

編輯`help/workfront-fusion/fusion-product-releases/fusion-release-activity.md`：

- 尋找`## Fusion releases in {current year}`區段（它是&#x200B;**not**，包裝在`+++`可摺疊區塊中 — 僅摺疊過去的年份）。
- 直接在年度標題下尋找或建立發行月份的`### {Month} {Year}`標題。
  - 如果月標題尚不存在，請將它新增到上個月&#x200B;**以上** （最新月份在前）。
- 將新頁面新增為該月標題下的&#x200B;**第一個**&#x200B;專案符號（最新的一週優先）：

  ```markdown
  * [Workfront Fusion release activity: Week of {Month} {Day}, {Year}](/help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md)
  ```
- 如果這是新年的第一版，請在前一年標題上方新增新的`## Fusion releases in {YYYY}`標題，並在`+++ **Click to open**` / `+++`可摺疊區塊中包裝&#x200B;*previous*&#x200B;年的區段（如果尚未包裝） （僅目前年份保持展開）。

## 步驟5：將頁面新增至目錄

編輯`help/workfront-fusion/TOC.md`：

- 尋找目前年度的`* Fusion releases - {YYYY} {#fusion-releases-{YYYY}}`，巢狀位於`* Fusion release activity {#fusion-release-activity}`下方。
- 將新頁面新增為該標題下的&#x200B;**第一個**&#x200B;專案（最新的第一個），符合現有的縮排（8個空格）：

  ```markdown
        * [Workfront Fusion release activity: Week of {Month} {Day}, {Year}](/help/workfront-fusion/fusion-product-releases/fusion-releases-{YYYY}/fusion-{YYYY}-{M}-{D}.md)
  ```
- 如果目前年份的標題尚不存在，請在前一年標題上方新增`* Fusion releases - {YYYY} {#fusion-releases-{YYYY}}`。
- **不要**&#x200B;新增`{hide-from-toc}`首碼至新專案 — 僅用於較舊的專案一旦超過可見導覽的期限（請參閱下列已知的不一致性）。

### 要觀察的已知不一致（不要復寫）

- 有數個2026年初的目錄專案誤巢狀於`Fusion releases - 2025`標題下，即使頁面本身是2026年發行版本。 新增專案時，一定要仔細檢查它是否落在符合&#x200B;**它自己的年份**&#x200B;的標題下，而不是在上一個專案出現的地方。
- 有些較舊的頁面標題/H1會在年份之前省略逗號（`July 13 2026`而非`July 13, 2026`）。 在新頁面中一律使用逗號。

## 步驟6：最終檢查清單

- [ ]檔案建立在正確的路徑中，日期中沒有前導零
- [ ] Frontmatter使用`hidefromtoc: true`，不是發明的`exl-id`/`TQID`
- [ ]標題/說明相符，日期包含逗號
- [ ]每個功能都有說明和已驗證的「詳細資訊」連結
- [ ]需要動作/取代功能有`>[!IMPORTANT]`圖說文字
- [ ]新頁面已新增為`fusion-release-activity.md`中正確年/月下的最新專案
- [ ]新頁面已新增為`TOC.md`中正確年份標題下的最新專案
- [ ]必要時建立新年/月標題，並在`fusion-release-activity.md`中摺疊上一年

## 其他資源

如需完整有效範例（簡單的多功能周，以及具有`>[!IMPORTANT]`動作必要圖說文字），請參閱`.claude/commands/_fusion-release-notes-reference.md`。

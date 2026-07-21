---
source-git-commit: 59a8d8ee83906bc16fc627bd348accc4e588cf9b
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---
# Fusion發行說明參考範例

根據`fusion-release-notes`技能的實際最近頁數
`help/workfront-fusion/fusion-product-releases/fusion-releases-2026/`.

---

## 範例1：直接的多功能周

根據`fusion-2026-6-22.md`。

```markdown
---
title: Workfront Fusion release activity Week of June 22, 2026
description: Workfront Fusion release activity Week of June 22, 2026
author: Becky
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
---
# Workfront Fusion release activity: Week of June 22, 2026

This page describes all enhancements made in Adobe Workfront Fusion the week of June 22, 2026.

For a list of all recent changes, see [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

For a list of recent bug fixes in Workfront Fusion, see the [Workfront Maintenance Updates](https://experienceleague.adobe.com/en/docs/workfront-known-issues/releases/current-updates) page and check for any updates labeled Workfront Fusion Maintenance Update.

## Create custom JavaScript packages to use in scenarios

To provide better flexibility and control of your scenarios, we've added the ability to create a custom JavaScript packages that you can then use in scenarios. You can create custom packages in the Packages area of Fusion. You then add functions or variables from these packages to your scenarios in the form of an Adobe App Builder module.

Packages include functions, along with any variables or dependencies the functions rely on. You can also test functions in your package before using them in your scenarios

Because custom packages work through Adobe App Builder, your organization must have an Adobe App Builder license to use them.

For more information on using custom functions in Fusion, see [Use custom function packages](/help/workfront-fusion/create-scenarios/map-data/use-custom-function-packages.md).

## View changes between scenario versions

To make it easier to understand changes between scenario versions, we've added the ability to view and compare those changes. Now you can bring up a window that displays specific changes between two selected versions of the same scenario.

For more information, see [View and manage scenario versions](/help/workfront-fusion/manage-scenarios/restore-a-scenario-version.md).
```

---

## 範例2：含有必要動作/取代圖說文字的周

根據`fusion-2026-3-9.md`。

```markdown
---
title: Workfront Fusion release activity Week of March 9, 2026
description: Workfront Fusion release activity Week of March 9, 2026
author: Becky
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
---
# Workfront Fusion release activity: Week of March 9, 2026

This page describes all enhancements made in Adobe Workfront Fusion the week of March 9, 2026.

For a list of all recent changes, see [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md).

For a list of recent bug fixes in Workfront Fusion, see the [Workfront Maintenance Updates](https://experienceleague.adobe.com/en/docs/workfront-known-issues/releases/current-updates) page and check for any updates labeled Workfront Fusion Maintenance Update.

## Log in to Fusion through Adobe IMS

>[!IMPORTANT]
>
>**Action Required: Migrate to IMS Login for Adobe Workfront Fusion by April 15.**
>
>To ensure that you will be able to log in after April 15, your Fusion administrator must migrate you to Adobe IMS. Please contact your Fusion administrator to be migrated.

As part of our ongoing security enhancements, Adobe is deprecating the legacy username and password login method for Adobe Workfront Fusion. Effective **April 15**, the legacy login flow **will no longer be supported**.

Going forward, access to Adobe Workfront Fusion will require authentication through the Adobe Identity Management System (IMS) login flow.

For instructions on provisioning access through the Adobe Admin Console, see [Add users to Adobe Workfront Fusion through the Adobe Admin Console](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/add-fusion-users-admin-console.md).

If you have questions or need assistance with the migration process, please contact your Adobe representative.

## New route labels

To make it easier to identify routes, we've added labels. Now, routes are labeled in the order they execute. Fallback and error handling routes are also labeled. Route labels also display any filters used for that route.

For more information on routes, see [Add a Router module and configure routes](/help/workfront-fusion/create-scenarios/add-modules/router-module.md).
```

---

## 概觀頁面(`fusion-release-activity.md`)更新模式

將2026年7月20日當週新增至現有的2026年7月月月區段：

```markdown
## Fusion releases in 2026

### July 2026

* [Workfront Fusion release activity: Week of July 20, 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-20.md)
* [Workfront Fusion release activity: Week of July 13 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-13.md)
```

開始全新的年（僅限範例 — 請在第一版{YYYY+1}發佈時執行此操作）：

```markdown
## Fusion releases in 2027

### January 2027

* [Workfront Fusion release activity: Week of January 4, 2027](/help/workfront-fusion/fusion-product-releases/fusion-releases-2027/fusion-2027-1-4.md)

## Fusion releases in 2026

+++ **Click to open**

### December 2026
...
+++
```

---

## TOC.md更新模式

將2026年7月20日當週新增為最新專案：

```markdown
* Fusion release activity {#fusion-release-activity}
    * [Adobe Workfront Fusion release activity](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)
    * Fusion releases - 2026 {#fusion-releases-2026}
        * [Workfront Fusion release activity: Week of July 20, 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-20.md)
        * [Workfront Fusion release activity: Week of July 13 2026](/help/workfront-fusion/fusion-product-releases/fusion-releases-2026/fusion-2026-7-13.md)
        ...
```

---

## 現有頁面中的已知不一致（僅供參考 — 請勿將這些內容複製到新頁面）

1. **在TOC.md**&#x200B;中放置錯誤的年份標題 — 2026年1月–2月專案目前位於`Fusion releases - 2025`標題下，而非`Fusion releases - 2026`。 這是既存的錯誤，不是預期的結構。
2. **在year**&#x200B;前遺漏逗號 — 像`fusion-2026-7-13.md`這樣的頁面在title/description/H1中使用「July 13 2026」，而不是「July 13， 2026」。 在新頁面中一律包含逗號。
3. **`hidefromtoc`與`exl-id`/`TQID`** — 從`fusion-2026-4-27.md`開始往上的頁面帶有`exl-id` （有時有`TQID`）；從`fusion-2026-5-4.md`開始往上的頁面使用`hidefromtoc: true`代替。 新頁面應該遵循較新的模式（`hidefromtoc: true`，而不是`exl-id`/`TQID`），因為這些識別碼稍後由發佈管道指派。
4. TOC.md **中的**`{hide-from-toc}`&#x200B;首碼 — 用來在已轉譯導覽中舊專案離開最近檢視時取消強調。 請勿將此專案新增至全新專案。

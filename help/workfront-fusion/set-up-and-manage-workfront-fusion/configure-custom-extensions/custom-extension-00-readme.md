---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 自訂UI擴充功能：文章索引
description: Workfront Fusion中的自訂擴充功能
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 3%

---


# 自訂UI擴充功能：文章索引

Fusion可以在介面中顯示您自己的Web UI。 您可以建立稱為擴充功能的小型網頁應用程式，並將其發佈至Adobe，接著該應用程式就會顯示為Fusion導覽中的按鈕。 當使用者按一下時，您的UI會載入到Fusion的主要區域，並自動收到有關登入者的資訊、他們工作的組織和團隊等等。

Fusion檔案的這個區段會逐步引導您完成整個程式，而不需假設您之前有使用Adobe App Builder或前端架構的經驗。 它也會包含必要的程式碼，以及該程式碼的解釋。

## 何時使用本指南

如果您想要將自訂畫面或工具新增到Fusion，請使用此指南。 您不需要成為開發人員專家。 您確實需要習慣將命令複製到終端機並編輯一些文字檔案。

若要建立自訂UI擴充功能，您需要Adobe ID以及Adobe組織的存取權（與您用來登入Fusion的存取權相同）。

## 您將建置的內容

在本指南結束時，您將擁有：

1. 免費的Adobe **App Builder**&#x200B;專案。 這是擴充功能的所在位置。
1. 可呈現自訂UI的小型網頁應用程式。
1. 該網頁應用程式已連線至Fusion的其中一個擴充點，因此會顯示在Fusion導覽中。
1. 您的UI會從Fusion讀取即時上下文（例如目前的使用者、組織和團隊），並在使用者切換組織或團隊時回應。
1. 擴充功能已發佈，方便組織中的其他使用者檢視。

<!--

## How it works, in one picture

```
  Fusion (the "Host")                         Your extension (the "Guest")
  ───────────────────────────────                         ──────────────────────────────
  Left navigation                             A web app hosted by Adobe
   └── Organization                            (App Builder + UI Extensibility)
       └── [Your extension button]  ── click ──▶ Fusion opens your UI in an iframe
                                              and sends it live context:
                                               * signed-in user
                                               * active organization
                                               * active team
                                               * Adobe IMS identifiers
```

Fusion is the **host**. Your extension is the **guest**. They run in separate browser frames and talk to each other through Adobe's **UI Extensibility SDK** (no custom networking required on your side).

-->

## 目錄

第一次以順序閱讀頁面。 稍後您可以直接跳到您需要的位置。

| # | 頁面 | 涵蓋範圍 |
| --- | ------ | ---------------- |
| 1 | [概覽和重要概念](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md) | 辭彙表、架構以及每個Fusion擴充點的用途。 |
| 2 | [設定您的工具和Adobe帳戶](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-02-set-up-tools-account.md) | Node.js、Adobe I/O CLI、登入並在Adobe Developer Console中建立專案。 |
| 3 | [建立專案並針對Fusion進行設定](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md) | 使用`aio`命令列產生一般App Builder專案（不是產品專屬範本）。 然後，將您的專案指向Fusion擴充功能點並註冊您的Widget。 |
| 5 | [建置UI](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md) | 呈現您的自訂畫面並透過Fusion完成連線（「交握」）。 |
| 6 | [Fusion內容參考](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md) | 每個欄位Fusion都會傳送給您、其含義以及如何對變更做出反應。 |
| 7 | [發佈您的擴充功能](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md) | 建置、部署，並讓您的擴充功能顯示在Fusion中。 |
| 8 | [疑難排解](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md) | 最常見錯誤的修正。 |
| 9 | [示範逐步解說](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-09-demo-walkthrough.md) | 一個線性、複製並貼上的指令碼：來自一般Experience Cloud殼層範本的支架，→重新鎖定目標至Fusion →，然後部署至Stage→在Fusion中執行。 最適合即時示範。 |
| 10 | [呼叫Workfront和Fusion API](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md) | 使用執行階段動作Proxy，從您的擴充功能呼叫後端API而不點選瀏覽器CORS。 涵蓋`require-adobe-auth`、Fusion v3標頭及運作範例。 |

## 可用性注意事項

Fusion目前會公開這些擴充點：

* `fusion/nav-organization/1` — 顯示在&#x200B;**組織**&#x200B;區段下。
* `fusion/nav-team/1` — 顯示在&#x200B;**團隊**&#x200B;區段下。

您必須先為您的Adobe組織將擴充點上線，才能發佈其中一個。 如果您的發佈步驟失敗，指出擴充點「不存在」，請參閱[疑難排解](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-08-troubleshooting.md)。

## Adobe官方檔案

本指南是Fusion專屬的。 對於基礎平台，標準參考為：

* [UI擴充性概觀](https://developer.adobe.com/uix/docs/)
* [UI擴充功能開發流程](https://developer.adobe.com/uix/docs/guides/development-flow/)
* [UI擴充功能管理（發佈/核准/撤銷）](https://developer.adobe.com/uix/docs/guides/publication/)
* [Adobe App Builder快速入門](https://developer.adobe.com/app-builder/docs/getting_started/)

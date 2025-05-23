---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion發行活動： 2020年11月16日當週
description: 本頁說明2020年11月16日當週在Adobe Workfront Fusion中所做的所有增強功能。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
hidefromtoc: true
exl-id: 69e4a458-fd32-4dcd-be43-19a9467cf678
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Workfront Fusion發行活動： 2020年11月16日當週

本頁說明2020年11月16日當週在Adobe Workfront Fusion中所做的所有增強功能。

如需所有最近變更的清單，請參閱[Adobe Workfront Fusion發行活動](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)。

如需Workfront Fusion中最近的錯誤修正清單，請參閱[Workfront維護更新](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=zh-Hant)頁面，並檢查任何標示為Workfront Fusion維護更新的更新。

## Jira雲端聯結器的更新

為了擴展您使用Jira Cloud Connector的方式，我們已新增三個模組：

* 將問題新增至衝刺
* 清單記錄
* 搜尋記錄

我們也更新了現有的模組，以支援「Sprint」物件型別。 之前，您只能透過自訂API呼叫模組存取「Sprint」物件。

## 執行ID現在可用於場景中的對應

「對應」面板現在提供案例的執行ID。 此ID代表案例的特定執行，且可當作中繼資料使用。 例如，執行ID可以與Fusion建立的記錄一起儲存，以便您稍後可以確定哪個Fusion執行建立了記錄。 您可以在「一般函式」下的對應面板中找到執行ID。

## Workfront Fusion 2.0案例的鍵盤快速鍵

為了更方便建立情境，我們新增了一些鍵盤快速鍵：

* Ctrl/Cmd+Shift+Enter：執行案例一次
* Ctrl/Cmd + Shift + S：儲存案例

## Office 365 Excel聯結器的更新

為了擴展您使用Office 365 Excel聯結器的方式，我們已新增一些模組。 現在您可以：

* 從活頁簿的變更觸發模組
* 搜尋或下載活頁簿
* 列出工作表、工作表列、表格或表格列
* 更新表格或工作表列
* 刪除表格或工作表列
* 擷取表格的中繼資料
* 進行自訂API呼叫

先前可用的模組仍會存在於應用程式中。


## 在您的Workfront應用程式連線中使用OAuth 2.0

我們已更新Workfront聯結器，改用OAuth 2.0。此更新表示在Workfront應用程式連線中變更更容易。 例如，如果連線發生變更（例如密碼），您就不需要更新案例中的每個個別連線。 此外，OAuth2還提供其他優點，例如改善安全性及使用單一登入(SSO)的功能。

現有連線目前不需要任何變更。 不過，如果您想利用OAuth 2.0的優點，可以重新授權現有的連線。

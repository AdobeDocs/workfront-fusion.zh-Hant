---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion 發行活動：2022 年 11 月 7 日當週
description: 本頁說明2022年11月7日當週在Adobe Workfront Fusion中所做的所有增強功能。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9d58abd0-1fe7-43c8-a1ea-2fadea738590
TQID: https://experienceleague.adobe.com/iigr0fKWxXA-DvvPZVjZvIQ3s-dW6XUBWgMYaxoGZRs
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 233
ht-degree: 25%

---

# Workfront Fusion 發行活動：2022 年 11 月 7 日當週

**Webhook佇列最佳化**

此發行版本已最佳化Fusion的webhook佇列。 接受webhook的服務現在與佇列和其他處理序分開。 此變更讓Fusion能夠以更快、更一致的速率處理webhook佇列。

在此變更實作期間，我們能夠更清楚瞭解已排入佇列的webhook事件的預期記錄處理時間。 Fusion的webhook檢視器頁面預計不會超過1分鐘。

若要檢視目前排入佇列的Webhook事件，請在左側導覽中導覽至Webhook。 分子中帶有數字的卡車圖示表示該webhook的佇列事件。 按一下卡車圖示以檢視已排入佇列的事件。


**未使用的Webhook現在將會停用或刪除**

我們已對Workfront Fusion處理未使用Webhook的方式進行一些變更。 現在，如果符合下列任一條件，Webhook就會自動停用：

* webhook已超過5天未連線至任何案例。
* 僅在非使用中的情境中使用 Webhook，而非使用中狀態已經超過 30 天。

如果停用的 Webhook 未連接任何情境，且處於停用狀態已超過 30 天，則會自動刪除和取消註冊。

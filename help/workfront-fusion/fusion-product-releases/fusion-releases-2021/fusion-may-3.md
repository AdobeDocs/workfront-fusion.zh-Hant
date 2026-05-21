---
product-previous: workfront-fusion
content-type: release-notes
product-area: workfront-integrations
navigation-topic: fusion-release-activity
title: Workfront Fusion 發行活動：2021 年 5 月 3 日當週
description: 本頁說明2021年5月3日當週在Adobe Workfront Fusion中所做的所有增強功能。
author: Luke
feature: Product Announcements, Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 8858fc79-5eda-4938-9bb5-c05be38f02bc
TQID: https://experienceleague.adobe.com/GZ5W-9Q1Y9M-cCVN1CupZVs8GuQPy4Dusifz-5sxJm8
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 273
ht-degree: 20%

---

# Workfront Fusion 發行活動：2021 年 5 月 3 日當週

本頁說明2021年5月3日當週在Adobe Workfront Fusion中所做的所有增強功能。

如需所有近期變更的清單，請參閱 [Adobe Workfront Fusion 發行活動](/help/workfront-fusion/fusion-product-releases/fusion-release-activity.md)。

如需 Workfront Fusion 中近期的錯誤修正清單，請參閱 [Workfront 維護更新](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=zh-Hant)頁面，並檢查任何標示為 Workfront Fusion 維護更新的更新。

## Salesforce聯結器現在可以使用SOQL進行搜尋

Salesforce >搜尋記錄模組現在可選擇使用SOQL （Salesforce物件查詢語言）進行搜尋。 您也可以使用先前可用的選項（SOSL和簡單搜尋）進行搜尋。

## Azure DevOps聯結器中的新連線型別所需的範圍較少

為了增強安全性，我們已在Workfront Fusion Azure DevOps聯結器中新增了聯結器型別。 現在，當您在Azure DevOps模組中建立連線時，可以從兩種連線型別中進行選擇：

* Azure DevOps

  這個新的連線型別將範圍限製為Workfront Fusion特別需要的範圍。

* Azure DevOps （要求所有領域）

  這是舊版連線型別，會要求與Azure DevOps連線時可用的所有範圍。

建議您在使用Azure DevOps的所有新情境中使用Azure DevOps連線型別。 我們也建議您變更現有案例中的任何Azure DevOps模組，以使用新的連線型別。 舊版Azure DevOps （要求所有範圍）連線型別近期將停止使用。

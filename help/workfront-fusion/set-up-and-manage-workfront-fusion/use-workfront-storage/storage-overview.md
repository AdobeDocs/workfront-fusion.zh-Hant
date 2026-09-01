---
title: 儲存空間概觀
description: 儲存是Workfront Fusion中的頁面，可讓團隊直接存取其Adobe Enterprise Storage Management (ESM)儲存庫，讓使用者瀏覽資料夾、上傳和下載檔案、檢視版本記錄和建立自動化案例。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: d5568479d43bd5518adae5b66b132b4075e7f356
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 2%

---

# 儲存空間概觀

<!--Add to navigation articles once this goes to production-->

Workfront Fusion中的「儲存」區域可讓團隊直接存取其Adobe企業儲存管理(ESM)存放庫。 使用者可以瀏覽資料夾、上傳和下載檔案、檢視版本記錄和建立自動化案例，所有這些操作都不需要離開Fusion。

儲存空間為團隊所有，且組織必須加入Adobe Identity Management系統(IMS)，才能存取Adobe儲存空間。

Fusion Storage中的檔案會映象至Adobe Files (adobe.com/files)，因此任何可以在Adobe Files中存取的檔案都可以在Fusion Storage中存取。

如需使用「儲存」的指示，請參閱：

* [初始化儲存空間](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/initialize-storage.md)
* [在Workfront Fusion中檢視及管理儲存空間](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/view-and-manage-storage-in-workfront-fusion.md)
* [上傳檔案至儲存空間](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/upload-files-to-storage.md)
* [從儲存體下載檔案](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/download-files-from-storage.md)
* [從儲存中刪除檔案](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/delete-files-from-storage.md)
* [檢視儲存體中的檔案版本記錄](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/view-storage-file-version-history.md)
* [從儲存空間建立案例](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/create-scenarios-from-storage.md)

## 儲存先決條件

若要使用Workfront Fusion儲存區域，必須滿足以下條件：

* 組織已加入&#x200B;**Adobe Identity Management系統(IMS)**
* 組織有&#x200B;**可用的Adobe儲存空間**
* 使用者已登入&#x200B;**正確的Adobe IMS組織** （符合所選Fusion組織的組織）
* 使用者的帳戶具有Adobe儲存空間的&#x200B;**存取權**

## 字彙表

使用時

| 術語 | 定義 |
| ------ | ----------- |
| **存放庫** | Adobe ESM中的頂層儲存容器，通常會對應至專案或工作區 |
| **Connection** | Fusion和Adobe儲存體之間的安全連結，在初始化期間自動建立。 使用具有自動權杖重新整理功能的Adobe IMS驗證 |
| **ESM** | 企業儲存空間管理，Adobe的雲端檔案儲存空間服務 |
| **IMS** | Adobe Identity Management系統，Adobe的驗證與身分平台 |

<!--

## UI Reference — Key Screens

### 1. Initialization Screen

* Cloud icon with **"Adobe Storage"** heading
* Description text explaining the feature
* **"Initialize Storage"** button (primary action)
* Error variants for access restriction, org mismatch, access denied, no storage found

### 2. Repository List

* Table with **Name** and **Region** columns
* **"Open"** action button per row

### 3. File Browser

* Breadcrumb navigation bar
* **"Upload File"** dropdown button (with "Upload File" and "Upload File in Scenario" options)
* File/folder table with **Name**, **Type**, **Size**, **Created** columns
* Floating action bar on file selection with: **Download**, **Download in Scenario**, **Versions**, **Delete**
* Upload/download progress banners (top-right corner)

### 4. Version History Panel

* Right-side slide-out panel
* Version list with date, version badge, and download button per entry
* **"current"** label on the latest version

-->

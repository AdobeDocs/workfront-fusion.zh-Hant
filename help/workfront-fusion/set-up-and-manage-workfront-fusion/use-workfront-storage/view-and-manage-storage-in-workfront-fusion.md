---
title: 在Workfront Fusion中檢視及管理儲存空間
description: 儲存區域會列出可用的存放庫，並讓您瀏覽資料夾和檔案。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: a2632cb3184cd555555136288e78ab1e05e4ea9d
workflow-type: tm+mt
source-wordcount: 330
ht-degree: 1%

---

# 在Workfront Fusion中檢視及管理儲存空間

Workfront Fusion中的「儲存」區域可讓您在Adobe雲端儲存空間中檢視存放庫並與之互動。

如需儲存的概述，請參閱[儲存概述](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/storage-overview.md)。

>[!TIP]
>
>您必須先初始化存放裝置，才能看到存放庫。 如需指示，請參閱[初始化存放裝置](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/initialize-storage.md)。

## 檢視存放庫、資料夾和檔案

1. 在Workfront Fusion中，按一下左側導覽中的&#x200B;**儲存空間**。
存放庫清單隨即開啟。

   如果只有一個可用存放庫，則直接開啟存放庫。

1. 按一下任何存放庫上的&#x200B;**開啟**&#x200B;以瀏覽其內容。

   開啟存放庫會顯示存放庫中的資料夾。
1. 按一下資料夾以開啟並顯示其「檔案」。
1. 若要向上導覽至資料夾結構，請按一下階層連結。


>[!NOTE]
>
>空白資料夾會顯示訊息： *「此資料夾是空的」*

## 管理多個儲存體連線

一個團隊可以有多個Adobe儲存體連線。

1. 在Workfront Fusion中，按一下左側導覽中的&#x200B;**儲存空間**。
當有多個連線存在時，索引標籤會出現在「儲存體」頁面的頂端，並標示每個連線的名稱。
1. 若要切換到其他連線的存放庫，請按一下該連線的索引標籤。

如果連線變成無效（例如其Token過期且無法重新整理），則會自動篩選掉，且不會顯示為索引標籤。 Fusion排程的權杖重新整理可讓連線自動有效。

## 檔案資訊

表格中的每個檔案都顯示：

| 欄 | 說明 |
| -------- | ------------- |
| **名稱** | 帶有檔案圖示的檔案名稱。 |
| **類型** | 副檔名徽章，例如PNG、PDF或JPG。 |
| **大小** | 檔案大小。 如果檔案最近上傳，且後端仍在處理中，則顯示&#x200B;*「正在處理……」*。 |
| **已建立** | 建立日期。 |

存在多個版本時，檔案也會顯示&#x200B;**版本徽章** （例如`v2`、`v3`）。

## 表格控制項

* **搜尋/篩選**：使用全域搜尋列依名稱篩選檔案。
* **排序**：按一下資料行標題進行排序。
* **分頁**：選擇每頁10、25、50或100個專案。 預設值為25。

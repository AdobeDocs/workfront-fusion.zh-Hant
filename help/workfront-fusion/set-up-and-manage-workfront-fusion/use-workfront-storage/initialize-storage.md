---
title: 初始化儲存空間
description: 當使用者第一次導覽到儲存體時，他們會看到初始化畫面，該畫面會代表團隊建立與Adobe儲存體的安全連線。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: a2632cb3184cd555555136288e78ab1e05e4ea9d
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 0%

---

# 在Workfront Fusion中初始化儲存體

必須先初始化Fusion Storage區域，您才能在Adobe雲端儲存空間中檢視存放庫、資料夾和檔案。

如需儲存的概述，請參閱[儲存概述](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/storage-overview.md)。

## 初始化儲存空間

1. 在Workfront Fusion中，按一下左側導覽中的&#x200B;**儲存空間**。
1. 按一下&#x200B;**初始化儲存裝置**。

Fusion會代表團隊自動建立與Adobe儲存體的安全連線。

建立連線後，Fusion會載入團隊的儲存機制。

## 疑難排解初始化

| 訊息 | 原因 | 使用者應該做什麼 |
| -------- | -------- | ------------------------ |
| **存取受限制** | 組織未加入Adobe IMS。 | 請聯絡組織管理員以完成IMS上線。 |
| **組織不符** | 使用者已登入其他Adobe組織，而不是在Fusion中選取的組織。 | 登出，然後使用正確的Adobe IMS組織重新登入。 |
| **拒絕存取** | 使用者的帳戶沒有必要的許可權，或組織無法使用Adobe儲存空間。 | 向組織管理員確認帳戶許可權。 解析後，按一下&#x200B;**重試**。 |
| **找不到存放裝置** | 已建立連線，但找不到存放庫。 | 驗證是否已為組織布建Adobe儲存空間。 驗證後，按一下&#x200B;**載入儲存裝置**&#x200B;以重試。 |

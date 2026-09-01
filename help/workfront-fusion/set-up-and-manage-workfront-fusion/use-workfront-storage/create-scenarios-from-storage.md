---
title: 從儲存空間建立案例
description: 儲存裝置與Fusion的案例產生器整合，因此您可以直接從「儲存裝置」頁面建立預先設定的案例，以下載或上傳檔案。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: aef1685cb25c0cdcb0dcdf9b0c73fb482d392e5f
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 0%

---

# 從儲存空間建立案例

如需儲存的概述，請參閱[儲存概述](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-workfront-storage/storage-overview.md)。

儲存裝置與Fusion的情境產生器整合。 從「儲存」頁面，使用者可以建立將下載所選檔案的情境。

## 在情境中下載

1. 在Workfront Fusion中，按一下左側導覽中的&#x200B;**儲存空間**。
1. 導覽至包含您要下載情境中的檔案的存放庫。
1. 選取檔案，然後按一下動作列中的&#x200B;**「在案例中下載」**。

然後Fusion會建立名為&#x200B;**「下載{fileName}」**&#x200B;的新情境。 此情境會在單獨的瀏覽器標籤中開啟。

此情境已預先設定：

* 使用中的連線。
* 預先選取的存放庫、資料夾和檔案。
* 產生預先簽署之下載URL的模組。
* 從該URL擷取檔案的HTTP模組。
* 預設排程間隔為15分鐘。

## 在情境中上傳檔案

1. 在Workfront Fusion中，按一下左側導覽中的&#x200B;**儲存空間**。
1. 導覽至存放庫和檔案夾，其中包含您要下載的案例檔案。
1. 在資料夾內瀏覽時，按一下&#x200B;**「上傳檔案」**&#x200B;下拉式清單。
1. 選取&#x200B;**「上傳情境中的檔案」**。

然後Fusion會建立名為&#x200B;**「上傳至{folderName}」**&#x200B;的新情境。 此情境會在新的瀏覽器標籤中開啟。 您必須新增模組以提供您要上傳的檔案，例如「Workfront >下載檔案」模組。

此情境已預先設定：

* 使用中的連線。
* 預先選取的存放庫和資料夾。
* 產生具有預留位置檔案名稱之預先簽署之上傳URL的模組。
* 預設排程間隔為15分鐘。


---
title: API 概觀
description: 應用程式介面 (API) 是應用程式和服務互相進行通訊的方式。Fusion 使用 API 與您連接的應用程式進行通訊。每個應用程式都有個別的 API。
author: Becky
feature: Workfront Fusion
source-git-commit: 95cdc14b313a3f76d6feebabb59f72b4277ae9e4
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 91%

---

# Fusion 中的 API 概觀

<!--Add me to TOCs-->

應用程式介面 (API) 是應用程式和服務互相進行通訊的方式。Fusion 會使用 API 與您所連接的應用程式進行通訊。

應用程式的所有者建立並控制 API。例如，Adobe 的 Workfront 團隊擁有 Workfront API，而 Microsoft 擁有 Microsoft Graph API。API 的所有者會定義可以透過 API 執行哪些動作。

>[!NOTE]
>
>Workfront Fusion有自己的API，可用於在Fusion中自動化操作，例如管理連線、鉤點、情境、執行、記錄和其他核心自動化資源。
>如需Workfront Fusion API的相關檔案，請參閱[Workfront Fusion API](https://developer.adobe.com/workfront-fusion-apis/)。

## 考量事項

因為由 API 的所有者而非 Fusion 定義 API 的功能，所以我們必須進行一些重要考量：

* **您可以使用 Fusion 連接至具有公開 API 的任何應用程式或服務**，無論 Fusion 是否提供該應用程式或服務的專用連接器。您可以使用 Fusion 的通用連接器，將這些應用程式或服務引入您的情境中。

  如需通用連接器的清單，請參閱[通用連接器](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)。

* **所有者對應用程式 API 所做的變更可能會影響 Fusion 功能。**&#x200B;如果變更達到一定的重大程度，Fusion 可能需要更新模組或連線類型，或在極端情況下，可能要為應用程式建立新的連接器。

  關於這些極端情況 (稱為「重大變更」) 的詳細資訊，請參閱這篇文章中的[重大變更](#breaking-changes)。


## 重大變更

發生重大變更的常見原因是棄用，即 API 所有者不再提供某個 API 的部分或全部功能。發生此情況時，Fusion 團隊會盡一切努力快速調整 Fusion 功能，以便與應用程式的新版本 API 保持一致。這項調整通常會採用新的模組、連線類型或連接器的形式。

由於您的 Fusion 情境是使用您的特定資料進行設定，因此可能需要更新情境。

* 若變更與驗證或授權有關，您可能需要更新該應用程式的連線。
* 若變更與 API 中的特定動作 (端點) 有關，您可能會需要將與該動作相關的任何模組更新為新版本的模組。
* 若 Fusion 使用的整個 API 版本被棄用，您可能需要將該連接器的所有模組更新至新版本的連接器。

在許多情況下，您可以升級至新版本的模組，而不需要重新設定該模組。

如需關於升級模組的資訊與說明，請參閱[將模組升級為新版本](/help/workfront-fusion/manage-scenarios/update-module-to-new-version.md)。

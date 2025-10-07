---
title: API總覽
description: 應用程式設計介面(API)是應用程式和服務彼此通訊的一種方式。 Fusion會使用API與您連線的應用程式通訊。 每個應用程式都有個別的API。
author: Becky
feature: Workfront Fusion
source-git-commit: 1ee32ad1faa8c105142f85e83f1b522548fc7f93
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Fusion中的API概觀

<!--Add me to TOCs-->

應用程式設計介面(API)是應用程式和服務彼此通訊的一種方式。 Fusion會使用API與您連線的應用程式通訊。

API由應用程式擁有者建立與控制。 例如，Workfront API歸Adobe的Workfront團隊所有，而Microsoft Graph API歸Microsoft所有。 API的擁有者會定義哪些動作可透過API使用。

## 考量事項

API是由其擁有者而非Fusion定義的事實，導致了一些重要的考量：

* **您可以使用Fusion連線到任何具有公用API的應用程式或服務**，無論Fusion是否提供該應用程式或服務的專用聯結器。 您可以使用Fusion的通用聯結器，將這些應用程式或服務帶入您的情境中。

  如需通用聯結器的清單，請參閱[通用聯結器](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)

* **擁有者對應用程式API所做的變更可能會影響Fusion功能。**&#x200B;如果變更足夠嚴重，Fusion可能需要更新模組或連線型別，或在極端情況下可能會為應用程式建立新的聯結器。

  如需這些極端情況（稱為「重大變更」）的詳細資訊，請參閱本文中的[重大變更](#breaking-changes)。


## 重大變更

API擁有者從可用性移除部分或全部API時，中斷變更的常見原因是棄用。 發生此情況時，Fusion團隊會盡一切努力快速將Fusion功能與應用程式的API新版本重新調整。 這通常採用新模組、連線型別或聯結器的形式。

由於您的Fusion案例是使用特定資料設定的，因此您可能需要更新案例。

* 如果變更與驗證或授權有關，您可能需要更新該應用程式的連線。
* 如果變更與API中的特定動作（端點）相關，您可能需要將與該動作相關的模組更新為模組的新版本。
* 如果不建議使用Fusion使用的整個API版本，您可能需要將該聯結器的所有模組更新為新版本的聯結器。

在許多情況下，您可以升級至模組的新版本，而不需要重新設定該模組。

如需升級模組的資訊與指示，請參閱[將模組升級為新版本](/help/workfront-fusion/manage-scenarios/update-module-to-new-version.md)。

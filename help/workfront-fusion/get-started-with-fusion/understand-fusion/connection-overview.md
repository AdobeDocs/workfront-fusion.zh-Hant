---
title: 連線概觀
description: 大部分的應用程式都必須建立連線，以便 Adobe Workfront Fusion 能夠透過連線，根據特定情境的設定，與指定的第三方服務進行通訊。
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: ht
source-wordcount: '315'
ht-degree: 100%

---

# 連線概觀

Workfront Fusion 要求大部分應用程式建立連線，而其使用此連線與指定的第三方服務通訊。

例如，若您要建立從 Workfront 檢索資訊的情境，則您必須授予權限以便 Workfront Fusion 能夠存取您的 Workfront 帳戶。

連線代表 Fusion 用於存取應用程式的授權和權限。您可以為情境中使用的每個應用程式建立一個或多個連線，並可以在多個模組或情境中使用相同的連線。

大部分的連線只用於單一應用程式。例如，Workfront 連線不能用於 [!UICONTROL Salesforce] 模組。部分 [!DNL Adobe] 應用程式可以共用連線。如需詳細資訊，請參閱列於 [Fusion 應用程式及其模組參考資料：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)中，關於那些應用程式的文章。

連線的擁有者為團隊。團隊的所有成員都可以存取團隊的連線，而團隊外部的使用者則無權存取團隊的連線。

## 存取權

對於每個連線，Workfront Fusion 只需要成功完成特定情境所需的存取權。例如，若您建立一個要從 Workfront 下載文件的情境，Workfront Fusion 不會要求給予建立新專案的權限。之後，如果您發現需要建立專案，可以更新連線或建立可以建立專案的新連線。

並非所有服務都允許您限制對特定任務的存取權。在這些情況下，Workfront Fusion 必須要求授予完整存取權。關於如何限制 Workfront Fusion 存取您在這些服務上註冊之帳戶的詳細資訊，請參閱列於 [Fusion 應用程式及其模組參考資料：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)中的應用程式特定文件。

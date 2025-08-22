---
title: 連線總覽
description: 對於大部分應用程式而言，必須建立連線，讓Adobe Workfront Fusion可以根據特定情境的設定與指定的協力廠商服務通訊。
author: Becky
feature: Workfront Fusion
exl-id: 01132df7-4cc0-4ff3-b4d7-607a06558735
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# 連線總覽

Workfront Fusion需要連線才能執行大部分的應用程式。  它會使用此連線與指定的協力廠商服務通訊。

例如，如果您想建立可從Workfront擷取資訊的情境，您必須授予Workfront Fusion存取您的Workfront帳戶的許可權。

連線代表Fusion用來存取應用程式的授權和許可權。 您可以為案例中使用的每個應用程式建立一個或多個連線，並可以在多個模組或案例中使用相同的連線。

大部分的連線只用於單一應用程式。 例如，Workfront連線不能用於[!UICONTROL Salesforce]模組。 有些[!DNL Adobe]應用程式可以共用連線。 如需詳細資訊，請參閱列於[Fusion應用程式及其模組參考之這些應用程式的文章：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

連線為團隊所擁有。 團隊的所有成員都可以存取團隊的連線，而團隊外部的使用者無權存取團隊的連線。

## 存取權

對於每個連線，Workfront Fusion只需要成功完成特定案例所需的存取許可權。 例如，如果您建立案例以從Workfront下載檔案，Workfront Fusion不會要求建立新專案的許可權。 稍後，如果您發現需要建立專案，可以更新連線或建立可以建立專案的新連線。

並非所有服務都允許您限制對特定任務的存取。 在這些情況下，Workfront Fusion必須具備完整存取許可權。 如需有關如何限制Workfront Fusion存取您在這些服務上註冊之帳戶的詳細資訊，請參閱[Fusion應用程式及其模組參考中列出的應用程式特定檔案：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

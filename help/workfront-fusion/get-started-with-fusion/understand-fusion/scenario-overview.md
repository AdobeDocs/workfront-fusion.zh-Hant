---
title: 情境概觀
description: Adobe Workfront Fusion 需要 Adobe Workfront 授權以及 Adobe Workfront Fusion 授權。
author: Becky
feature: Workfront Fusion
exl-id: de81ad4c-27e5-4b6c-acf0-f01a8c85922e
source-git-commit: 34dad92019ca855f40698d3f3795788698c1cece
workflow-type: ht
source-wordcount: '704'
ht-degree: 100%

---

# 情境概觀

Adobe Workfront Fusion 的角色是將您的流程自動化，讓您的使用者不需要花費太多時間處理例行性任務。其將應用程式和服務內部及兩者之間的動作連結起來，並建立一個自動轉移和轉換您的資料的情境。您建立的情境會監視應用程式或服務中的資料，並處理該資料以便提供您想要的結果。

情境由一系列模組所組成，這些模組會指出如何在應用程式內轉換資料，或在應用程式和網頁服務之間如何轉移資料。

## 情境元素概觀

情境是由不同的元素建置而成。認識這些元素的術語，便可以更輕鬆地使用相關文件。

* [情境](#scenario)
* [觸發程序](#trigger)
* [模組](#module)
* [路由](#route)
* [情境區段](#scenario-segment)
* [連接器](#connector)

### 情境

**情境**&#x200B;是由使用者建立的一系列自動化步驟，目的在於移動和操作資料。「情境」一詞指的是一整組相連的步驟。

![情境](assets/entire-scenario-scenario.png)

### 觸發程序

情境由&#x200B;**觸發程序**&#x200B;啟動。觸發程序會監視新的和更新的資料，並在模組中設定的某些條件適用時啟動情境。觸發程序可設定為依排程 (輪詢)，或每當資料有所變更時 (即時) 啟動一個情境。

![觸發程序](assets/scenario-trigger.png)

### 模組

觸發程序之後接著是許多&#x200B;**模組**。模組代表情境中執行特定動作的單一步驟。模組經過設定並鏈結在一起以建立情境。

![模組](assets/scenario-module.png)

### 路由

情境可分拆成多個&#x200B;**路由**。路由是情境的一個部分，而特定的資料組合包可能會使用或不使用此路由。路由是使用路由器模組和篩選器所設定。

![路由](assets/scenario-route.png)

### 情境區段

情境區段是情境的一個部分，其中包含全部連接至相同應用程式的一系列連續模組。情境區段通常代表應用程式中簡短的工作流程。

![情境區段](assets/scenario-segment.png)

### 連接器

連接器是適用於特定應用程式的一組模組。Workfront Fusion 提供許多常用工作應用程式 (例如 Workfront、Salesforce 和 Jira) 的連接器，以及可用於任何網頁服務的通用連接器。

![連接器](assets/scenario-connectors.png)

## 範例

展開下列區段以檢視情境範例及其說明。

+++**在 Adobe Workfront 中將流程自動化**

您可以利用 Workfront Fusion 在 Workfront 內部將簡單或複雜的工作流程自動化，節省時間並確保流程執行的一致性。

在範例中，當 Workfront 的「任務」或「問題」中的指定欄位發生變更時，就會觸發此情境。觸發後，情境會取得相關專案中的資訊，並為指派至專案特定角色的人員建立量身打造的更新。

![範本範例](assets/fusion-template-example.png)

+++

+++**將 Workfront 連接至其他應用程式或網頁服務**

>[!NOTE]
>
>如果您的組織使用舊版授權模型，則必須擁有 Workfront Fusion for Work Automation and Integration 授權才能連接至其他應用程式。

Workfront Fusion 可連接至其他應用程式和網頁服務。您可以存取、匯入、操作或匯出其他應用程式的資料，並將這些資料與 Workfront 整合或在應用程式之間互相整合。

許多應用程式都有專屬的 Workfront Fusion 連接器。若您要存取的應用程式沒有專用連接器，可以使用 Workfront Fusion 的 HTTP 或 SOAP 模組，透過應用程式的 API 與其連接。

在此範例中，將使用者新增至 [!DNL Excel] 試算表時會觸發情境。情境會檢查使用者是否在 Workfront 中。若沒有，則情境會在 Workfront 中建立使用者，並將其 Workfront 使用者 ID 加入到試算表中。

![整合範例](assets/fusion-integration-example.png)

如需專用連接器的清單，請參閱 [Fusion 應用程式及其模組參考資料：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。


>[!IMPORTANT]
>
>Adobe Workfront Fusion 可以連接至幾乎任何網頁服務。如果您要使用的應用程式沒有專用的 Workfront Fusion 連接器，可以使用通用連接器連接至應用程式或服務。
>
>如需通用連接器的清單，請參閱[通用連接器](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)

+++

## 參考資料

* 如需 Workfront Fusion 所使用詞語的字彙表，請參閱 [Adobe Workfront Fusion 字彙表](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md)。
* 若要開始建置練習情境，請參閱[建立基本情境](/help/workfront-fusion/build-practice-scenarios/create-basic-scenario.md)。
* 如需建立和管理情境的詳細資訊，請參閱下列文章：
   * [建立情境](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)
   * [管理情境](/help/workfront-fusion/manage-scenarios/manage-scenarios-toc.md)

---
title: 即時觸發器(webhook)
description: 許多服務都會提供Webhook，以便在服務發生特定變更時傳送即時通知。 若要處理這些通知，建議您使用立即觸發程式。 本文說明Adobe Workfront Fusion中即時觸發器的使用及功能。
author: Becky
feature: Workfront Fusion
exl-id: 5bfda2b2-dc1c-4ff6-9236-b480bfda2e58
source-git-commit: 45efeecd1758e302f57498bab842594800a84c1d
workflow-type: tm+mt
source-wordcount: '1272'
ht-degree: 10%

---

# 即時觸發器(webhook)

許多服務都會提供Webhook，以便在服務發生特定變更（事件）時立即傳送通知。 若要處理這些事件，建議您使用立即觸發程式。 即時觸發程式會在指定聯結器的模組清單中顯示`Instant`標籤。

![即時](assets/instant.png)

>[!TIP]
>
>您可以檢查聯結器中的模組清單，以檢視它是否有立即觸發程式，或者您可以檢查[Fusion應用程式及其模組參考](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)下的聯結器檔案。
>
>如需Adobe Workfront即時觸發程式檔案，請參閱Workfront模組一文中的[觸發器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#triggers)。

如果聯結器不包含webhook，您可以執行下列任一項作業：

* 使用Webhook模組建立自訂Webhook。
如需詳細資訊，請參閱[Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)。
* 使用輪詢觸發程式定期輪詢服務。
如需詳細資訊，請參閱[排程情境](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)

如需Workfront Fusion中Webhook的影片簡介，請參閱：

* [Webhook簡介](https://video.tv.adobe.com/v/3427025/){target=_blank}
* [中繼Webhook](https://video.tv.adobe.com/v/3427030/){target=_blank}

## 存取權要求

+++ 展開以檢視這篇文章中所述功能的存取權要求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront 封裝</td> 
   <td> <p>任何 Adobe Workfront Workflow 封裝及任何 Adobe Workfront Automation and Integration 封裝</p><p>Workfront Ultimate</p><p>Workfront Prime 和 Select 封裝，以及額外購買的 Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront 授權</td> 
   <td> <p>標準</p><p>工作或更高層級</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 檢視webhook詳細資料

您可以在Webhooks區域中檢視Webhooks清單。

1. 若要開啟Webhooks區域，請按一下左側導覽中的Webhooks圖示![Webhooks](assets/webhooks-icon.png)。

   在這裡，您可以看到Webhook清單。

   ![Webhook清單](assets/list-of-webhooks.png)

1. 若要搜尋特定webhook，請在「搜尋」方塊中輸入搜尋字詞。
1. 若要複製webhook，請按一下該webhook的列URL附近的復製圖示![複製webhook圖示](assets/copy-webhook-icon.png)。
1. 若要設定webhook的優先順序，請按一下「優先順序」欄中的下拉式清單，然後選取新的優先順序。

   優先順序較高的Webhook會先處理，如果背景工作集區有許多自動作業在競爭資源，則此功能會很有幫助。
1. 若要停用或啟用webhook，請停用或啟用該webhook列中「狀態」欄的切換。
1. 若要檢視webhooks佇列是否已滿，請核取完整佇列欄。 此資料欄中的數字是目前在佇列中的專案數。
1. 若要檢視webhook所處理的作業，請按一下該webhook的[完整佇列]資料欄中的&#x200B;**作業**。
1. 若要檢視webhook是否已過期，請檢查「過期」欄。 過期的Webhook未附加至任何案例，或是在120小時內未收到任何事件。
1. 若要檢視使用webhook的情境，請按一下該webhook「情境」欄中的&#x200B;**情境**&#x200B;按鈕。
1. 若要檢視用於此webhook的連線，請按一下該webhook的[連線]欄中的&#x200B;**連線**&#x200B;按鈕。
1. 若要隱藏欄或顯示先前隱藏的欄，請按一下&#x200B;**欄**&#x200B;圖示![欄圖示](assets/glist-column.png)並核取或取消核取欄名稱。
1. 若要檢視與Workfront webhook相關的活動訂閱，請核取webhook旁的方塊，並選取頁面底部的&#x200B;**顯示詳細資料**。

   >[!NOTE]
   >
   > 事件訂閱詳細資料僅適用於在新Workfront聯結器中建立的Workfront Webhook。 Webhook詳細資料目前不適用於其他聯結器。


## 排程即時觸發程式

當您設定立即觸發程式時，系統會提示您選取它何時執行。

![排程設定](assets/schedule-setting.png)

選取`Immediately`以在Workfront Fusion收到來自服務的新事件時立即執行案例。 這些事件會立即傳送到佇列中，然後在案例中一次處理一個，順序與接收資料的順序相同。

當案例執行時，系統會計算佇列中等待的擱置事件總數，而案例執行的週期與擱置事件的數量相同，每個週期會處理一個事件。

如需有關週期的詳細資訊，請參閱[案例執行、週期和階段](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md)。

>[!NOTE]
>
>* 週期與案例執行不同。 一個案例執行中可以有多個週期。
>* 當您使用排定執行`Immediately`的立即觸發程式執行案例時，將會套用下列例外：
>
>     * 根據定價計畫，兩次執行之間的間隔不受最小間隔的限制。
>
>       例如，一旦案例完成執行，就會再次檢查webhook的佇列。 如果有任何擱置中的Webhook，情境會立即再次執行，並再次處理所有擱置中的Webhook。
>   
>     * 「最大週期數」情境設定會忽略並設為100，這表示在單一情境執行期間不會處理超過100個擱置中的Webhook （每個週期為1個事件）。
>


如果您使用[!UICONTROL 立即]以外的任何其他排程設定，情境會依您指定的間隔執行。 由於間隔期間可在佇列中收集到數個webhook，因此建議將[!UICONTROL 最大週期數]選項設定為比預設1更高的值，以便在一個案例執行中處理更多webhook：

1. 按一下案例底部的[!UICONTROL 案例設定]圖示![案例設定圖示](assets/scenario-settings-icon.png)。
1. 在出現的&#x200B;**[!UICONTROL 情境設定]**&#x200B;面板中，在&#x200B;**[!UICONTROL 最大週期數]**&#x200B;欄位中輸入數字，以指示每次執行情境時，您要從佇列中執行的事件數。

佇列中剩餘的事件將在下次執行案例時處理，最多可達在「最大週期數」欄位中設定的數量。

## Webhook 護欄

為確保良好的效能，Workfront Fusion為Webhook設定了下列護欄。

### 速率限制

目前的速率限製為每秒5個Webhook。 如果超過限制，則會傳回`429`狀態代碼。

### 非作用中Webhook的到期

已超過120小時未指派給任何情境的webhook會被移除。

### Webhook裝載

Workfront Fusion 會儲存 Webhook 承載長達 30 天。在建立webhook裝載超過30天後存取該裝載會導致錯誤[!UICONTROL `Failed to read file from storage.`]

### 錯誤處理

當您的案例中出現具有立即觸發器的錯誤時，案例：

* 當案例設定為立即執行[!UICONTROL 立即]時立即停止。
* 當案例設定為依排程執行時，在3次不成功嘗試（3個錯誤）後停止。

如果案例執行期間發生錯誤，事件會在立即觸發器的復原階段重新放入佇列。 在這種情況下，您可以修正情景並再次執行。

如需詳細資訊，請參閱案例執行、週期和階段一文中的[回覆](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback)。

如果您的案例中存在Webhook回應模組，則會將錯誤傳送至Webhook回應。 Webhook回應模組一律在最後執行（當Scenario設定中的[!UICONTROL 自動認可]選項未啟用時）。

如需詳細資訊，請參閱文章Webhooks中的[回應Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md#responding-to-webhooks)。

### Webhook停用

若符合下列任一條件，Webhook 便會自動停用：

* webhook已超過5天未連線至任何案例。
* 僅在非使用中的情境中使用 Webhook，而非使用中狀態已經超過 30 天。

如果停用的Webhook未連線至任何案例，且已停用狀態超過30天，則會自動刪除及取消註冊。

## 自訂Webhook

您可以建立自己的Webhook。 如需詳細資訊，請參閱[Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)。

## 資源

如需有關週期的詳細資訊，請參閱[案例執行、週期和階段](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md)。

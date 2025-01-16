---
content-type: reference
title: 錯誤型別
description: 有時候，執行情境期間可能會發生錯誤。 如果服務因無法連線至服務而無法使用，或驗證失敗，通常就會發生這種情況。 本文會討論您可能會遇到的常見錯誤。
author: Becky
feature: Workfront Fusion
exl-id: abf5f844-d13b-416e-a8b8-2d4ee1786262
source-git-commit: d618d5c4b2306a3b940af7e402f93ced988095a3
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 1%

---

# 錯誤型別

有時候，執行情境期間可能會發生錯誤。 如果服務因無法連線至服務而無法使用，或驗證失敗，通常就會發生這種情況。

[!DNL Adobe Workfront Fusion]會區分幾種基本錯誤型別。 錯誤的型別會決定Fusion案例的下一個動作。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!DNL Adobe Workfront] 封裝</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權</td> 
   <td> 新增：標準<p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Adobe Workfront Fusion] 授權</td> 
   <td>
   <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
 </tbody> 
</table>


若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 連線錯誤

`ConnectionError`

連線錯誤是最常見的錯誤之一。 原因通常是因各種原因導致第三方服務無法使用，例如超載、維護或中斷。 此錯誤的預設處理方式取決於發生錯誤的模組。

* 如果第一個模組發生錯誤，則會終止案例的執行並顯示警告訊息。 然後[!DNL Workfront Fusion]會不斷嘗試以遞增的時間間隔重新執行案例。 如果所有嘗試都失敗，[!DNL Workfront Fusion]會停用此情境。
* 如果連線錯誤發生在第一個模組以外的其他模組，則後續步驟取決於情景進階設定中的「允許儲存不完整的執行」選項：

   * 如果已啟用此選項，則案例的執行會被移至[!UICONTROL Incomplete executions]資料夾，[!DNL Workfront Fusion]會重複嘗試以遞增的時間間隔重新執行案例。 如果所有嘗試都失敗，執行將保留在「未完成執行」資料夾中，等待使用者手動解析。

     如需不完整執行的詳細資訊，請參閱[檢視並解決不完整的執行](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)。
   * 如果停用此選項，則案例的執行會以錯誤結束，然後是復原階段。 然後[!DNL Workfront Fusion]會不斷嘗試以遞增的時間間隔重新執行案例。 如果所有嘗試都失敗，[!DNL Workfront Fusion]會停用此情境。

  如需「允許儲存未完成的執行」設定的詳細資訊，請參閱「設定案例設定」一文中的[允許儲存未完成的執行](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions)。

### 增加時間間隔

在錯誤發生時增加兩次嘗試間隔的演演算法稱為指數輪詢。 遞增時間間隔的設定如下：

1. 10 分鐘
1. 1 小時
1. 3 小時
1. 12 小時
1. 24 小時

增加時間間隔有助於防止經常執行的案例在多次失敗的嘗試上使用操作。

>[!BEGINSHADEBOX]

**範例：**

案例包含[!DNL Google Sheets]觸發程式[!UICONTROL Watch Rows]。 由於在[!DNL Workfront Fusion]啟動案例時進行維護，[!DNL Google Sheets]在30分鐘內無法使用，因此無法擷取新列。 此情境會停止，並在10分鐘後重試。 因為[!DNL Google Sheets]仍然無法使用，[!DNL Workfront Fusion]仍無法取得新資料列的資訊。 此情境的下一次執行排程在1小時內。 [!DNL Google Sheets]此時再次可用，情境已成功執行。

>[!ENDSHADEBOX]

## 資料錯誤

`DataError`

當專案未正確對應且未通過在[!DNL Workfront Fusion]端或第三方服務端執行的驗證時，會產生資料錯誤。

如果發生此錯誤，則會將場景（最多到模組失敗的位置）移至不完整執行資料夾，您可以在其中疑難排解問題。 不過，此情境不會停止，而是會繼續根據其排程執行。 若要在資料錯誤出現時停止執行案例，請啟用「案例設定」面板中的循序處理選項。

如果您尚未啟用案例設定中的[!UICONTROL Allow storing incomplete executions]選項，則案例的執行會因錯誤而終止，並會執行復原。

## 重複資料錯誤

`DuplicateDataError`

如果[!DNL Workfront Fusion]嘗試將相同的組合插入不允許重複資料的服務兩次，則會產生重複資料錯誤。 如果發生此錯誤，[!DNL Workfront Fusion]會以處理資料錯誤的方式進行。

如需詳細資訊，請參閱本文中的[資料錯誤](#data-error)。


## 無效的存取Token錯誤

`InvalidAccessTokenError`

當[!DNL Workfront Fusion]無法存取您向協力廠商服務註冊的帳戶時，會發生無效的存取權杖錯誤。 這通常發生在您在管理指定服務時撤銷[!DNL Workfront Fusion]的存取權時，但使用該服務的情境會依排程繼續執行。

如果發生此錯誤，情境執行會立即停止。 從發生錯誤的模組開始的其餘情境會移至不完整執行資料夾。

## 速率限制錯誤

`RateLimitError`

如果超過指定服務設定的限制，就會產生速率限制錯誤。 如果發生此錯誤，[!DNL Workfront Fusion]會以與連線錯誤相同的方式進行。

如需詳細資訊，請參閱本文中的[連線錯誤](#connection-error)。

## 不完整的資料錯誤

`IncompleteDataError`

只有觸發器會發生不完整的資料錯誤。 如果觸發器無法從指定服務下載所需資料，則會產生此錯誤。

如果案例以`IncompleteDataError`終止，其進一步的行為將取決於其[!UICONTROL Max number of consecutive errors]的設定。

如需詳細資訊，請參閱「設定案例設定」一文中的[連續錯誤數](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors)。

>[!BEGINSHADEBOX]

**範例：**

案例已設定[!DNL Workfront]觸發器[!UICONTROL Watch Record]來監視檔案。 此情境會在您上傳大型檔案（例如長影片）時執行。 由於[!UICONTROL Workfront Fusion]嘗試在視訊仍在上傳至Workfront時下載視訊，因此案例會以`IncompleteDataError`終止。

>[!ENDSHADEBOX]

## 執行階段錯誤

`RuntimeError`

在案例執行期間出現且不屬於這些錯誤型別之一的任何錯誤都會報告為`RunTimeError`。

如果案例以`RuntimeError`結束，其進一步的行為取決於[!UICONTROL Max number of consecutive errors]設定。

如需詳細資訊，請參閱「設定案例設定」一文中的[連續錯誤數](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors)。


>[!NOTE]
>
>如果案例從立即觸發程式開始並遇到此錯誤，則會忽略[!UICONTROL Max number of consecutive errors]的設定，並立即停用案例。
>如需詳細資訊，請參閱文章模組概觀中的[即時觸發器](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#instant-triggers)。

## 不一致性錯誤

`InconsistencyError`

如果在認可或倒回階段發生這些錯誤，則案例會以「不一致錯誤」結束。

如果此錯誤出現在案例中，案例的執行會立即停止。

## 警告

執行案例時，您可能會收到警告訊息，通知您發生問題。 警告不會阻止案例成功完成。

例如，當超過允許的檔案大小上限，且已停用[!UICONTROL Enable data loss]選項時，可能會出現警告。

## 資源

如需對應的詳細資訊，請參閱[對應概觀](/help/workfront-fusion/get-started-with-fusion/understand-fusion/mapping-overview.md)。

如需有關未完成執行的資訊，請參閱[檢視並解決未完成的執行](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)。

如需情境設定面板的相關資訊，請參閱[設定情境設定](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md)。

如需排程的相關資訊，請參閱[排程情境](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)。

如需案例階段的資訊，請參閱[案例執行、週期和階段](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md)。

如需「啟用資料遺失」選項的詳細資訊，請參閱「設定案例設定」一文中的[啟用資料遺失](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss)。

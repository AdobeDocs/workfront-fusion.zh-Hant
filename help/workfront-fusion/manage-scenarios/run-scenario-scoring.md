---
title: 執行案例評分專家
description: 情境評分專家可協助您確保情境的設定方式遵循最佳實務。 它會檢查您的情境並提供其結構和組織的建議。
author: Becky
feature: Workfront Fusion
exl-id: b668e7f6-dac5-4ac9-b3f3-109f70eaa2c4
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# 執行案例評分專家

>[!IMPORTANT]
>
>情境評分專家已暫時停用。

情境評分專家可協助您確保情境的設定方式遵循最佳實務。 它會檢查您的情境並提供其結構和組織的建議。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前： [！UICONTROL Work]或更高版本</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增:</p> <ul><li>[！UICONTROL Select]或[！UICONTROL Prime] Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li><li>[！UICONTROL Ultimate] Workfront計畫：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定*</td> 
   <td> 
     <p>您必須是組織的Workfront Fusion管理員。</p>
     <p>您必須是團隊的Workfront Fusion管理員。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 執行案例評分專家

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要執行「案例評分專家」的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下畫面底部附近的情境評分專家圖示![情境評分專家](assets/scoring-expert-icon.png)。

   「情境評分專家」面板隨即開啟。
1. 按一下&#x200B;**評估**。

情境評分專家傳回滿分10分，並顯示哪些檢查通過或失敗。 如果檢查失敗，案例評分專家會提供建議，說明如何確保案例符合這些檢查。

![案例分數](assets/scenario-score.png)

## 案例評分檢查

「情境評分專家」會使用以下檢查：

* 案例必須命名為。
* 所有模組都必須加上標籤。
* 此案例必須依設定的排程執行。

  如需指示，請參閱[排程情境](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)。
* 情境藍圖大小必須小於5 MB。

  如需詳細資訊，請參閱[融合效能護欄](/help/workfront-fusion/references/scenarios/fusion-performance-guardrails.md#scenarios)。
* 若使用Workfront即時觸發程式模組，則必須加以篩選。

  如需指示，請參閱Workfront > [觀看活動[!UICONTROL 模組]中的](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules)活動訂閱篩選器。

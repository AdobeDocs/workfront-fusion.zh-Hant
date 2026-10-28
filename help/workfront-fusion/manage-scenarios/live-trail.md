---
title: 使用即時追蹤來檢閱案例執行
description: 即時軌跡會顯示案例執行情形，將模組請求和執行活動合併到一個清單中。 您可以開啟任何作業的請求和回應詳細資料。
author: Becky
feature: Workfront Fusion
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
source-git-commit: 94449f8511d7480f1a4fc0ac6e8db9b067977abd
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 17%
---

# 使用即時追蹤來檢閱案例執行

即時軌跡會顯示案例的執行情形。 它結合模組請求，並以一個時間順序清單執行活動，因此您可以跟著在案例編輯器中的執行，在不離開畫布的情況下檢視哪裡出了問題。

>[!NOTE]
>
>此功能僅在新的案例編輯器體驗中可用。 如需詳細資訊，請參閱文章「情境編輯器」中的[新體驗和傳統體驗](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)。

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
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 開啟即時軌跡

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要檢閱的情境。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 開始執行情境，例如按一下&#x200B;**執行一次**。



即時軌跡會在畫布右側的面板中開啟。 如果您在執行期間關閉面板，畫面右側的小索引標籤可讓您再次開啟面板，而不會遺失已擷取的事件。

## 在Live Trail中檢閱活動

即時軌跡會列出模組請求，並按照其發生的順序執行活動。 您可以：

* 搜尋清單。
* 依狀態篩選清單。
* 繼續執行時追蹤最新事件。
* 清除目前的軌跡。

## 檢視要求和回應詳細資料

1. 在「即時軌跡」中，按一下您要檢視其詳細資訊的請求。

   提出請求的模組會顯示在畫布上，而請求和回應詳細資訊會在面板中開啟。

1. 檢閱詳細資料。 詳細資料檢視包括：

   * 模組操作之間的導覽
   * 請求標頭與內文
   * 回應標頭與內文

1. （選擇性）按一下&#x200B;**複製原始**&#x200B;或&#x200B;**複製cURL**，複製詳細資料以在其他地方使用：

   * 複製請求和回應的原始報表。
   * 複製請求的cURL命令。

1. 若要返回清單，請按一下面板左上角的向後箭頭。

## 請確定已提供請求和回應詳細資料

不會針對每個排程或觸發的執行保留請求和回應詳細資料，因為它們會佔用大量儲存空間。

* 執行一次，一律會保留請求和回應詳細資料。
* 對於案例的定期執行，在您要檢查的執行之前，開啟案例設定中的臨時偵錯記錄。 如需詳細資訊，請參閱「設定案例設定」一文中的[暫存偵錯記錄檔](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#temporary-debug-logs)。

如果您從執行歷史記錄中開啟執行，並且請求和回應面板沒有資料，面板會將您導向臨時偵錯記錄設定。

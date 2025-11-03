---
content-type: reference
title: 錯誤處理的指示
description: 本文說明可用於在Adobe Workfront Fusion案例中處理錯誤的指示。
author: Becky
feature: Workfront Fusion
exl-id: d7b0141f-d99d-4ab7-a60f-ed552a76f05d
source-git-commit: 99621f57da1eb294834a0eacfe527dcf017408e9
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 15%

---

# 錯誤處理的指示

錯誤處理指令可讓您選擇案例發生錯誤時發生的情形。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

+++##錯誤處理的指令

Workfront Fusion中有以下錯誤處理指示。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>復原</p> <p> <img src="assets/rollback.png"> </p> </td> 
   <td> <ul><li><p>案例執行會立即停止。</li><li>所有模組都會啟動復原階段，嘗試將所有模組回復到其初始狀態。 </li><li>後續模組不會處理。</p></li><li> <p>在大多數情況下，案例會在案例設定下指定的連續錯誤數之後停用。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors" class="MCXref xref">連續錯誤數</a>。</p> </li><li><p>案例執行狀態會標示為「錯誤」。</p></li></ul> <p><b>注意</b>：如果沒有將錯誤處理常式路由附加到模組，而且未勾選<a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions" class="MCXref xref">允許儲存不完整的執行</a>允許儲存在[!UICONTROL 案例設定]下的不完整執行設定，則這是預設行為。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>認可</p> <p> <img src="assets/commit.png"> </p> </td> 
   <td> <ul><li><p>案例執行會立即停止。</li><li>認可階段在所有模組上啟動。 </li><li>後續模組不會處理。</p></li><li> <p>會忽略所有未處理的組合。</p> </li><li><p>情境執行狀態標記為「成功」。 </p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>繼續</p> <p> <img src="assets/resume.png"> </p> </td> 
   <td> <ul><li><p>指定替代輸出並提供給發生錯誤的模組。</p> </li><li><p>後續模組會進行處理。</p></li><li> <p>情境執行狀態標記為「成功」。</p></li></ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>忽略</p> <p> <img src="assets/ignore.png"> </p> </td> 
   <td><ul><li> <p>忽略錯誤。</li><li> 後續模組不會處理。</p> </li><li><p>若有未處理的套件，情境執行將按正常情況繼續。</p> </li><li><p>情境執行狀態標記為「成功」。</p> </li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>中斷</p> <p> <img src="assets/break.png"> </p> </td> 
   <td><ul><li> <p>情境執行的狀態儲存在未完成執行作業的佇列中，而錯誤可以手動解決。如需詳細資訊，請參閱<a href="/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md" class="MCXref xref">檢視並解決不完整的執行</a>。</p> <p>不過，也有一些例外。 如需詳細資訊，請參閱「設定案例設定」一文中的<a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow" class="MCXref xref">允許儲存未完成的執行</a></a>。</p></li><li> <p>後續模組不會處理。</p></li><li> <p>若有未處理的套件，情境執行將按正常情況繼續。</p> </li><li><p>停用[!UICONTROL 自動完成執行]選項時，案例執行狀態會標示為「警告」。</p></li></ul> <p>如需詳細資訊，請參閱本文中的<a href="#break" class="MCXref xref">[!UICONTROL 分頁符號]</a>一節</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>重試</p> <p> <img src="assets/retry.png"> </p> </td> 
   <td> <p>在某些情況下，當失敗的原因可能隨著時間推移而過去時，重新執行失敗模組可能會很有用。</p> <p>Workfront Fusion目前不提供Retry指示詞，不過可採取數個因應措施來模擬其功能。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/config-error-handling/retry.md" class="MCXref xref">重試錯誤處理</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* 錯誤處理指示不能用於錯誤處理路由之外。
>* Workfront Fusion目前不提供Throw模組，該模組可讓您輕鬆依條件產生（擲回）錯誤，不過暫行解決方法可模擬其功能。
>
>  如需詳細資訊，請參閱[設定`throw`錯誤解決方法](/help/workfront-fusion/create-scenarios/config-error-handling/throw.md)。

## 資源

* 如需有關復原和復原階段的資訊，請參閱案例執行、循環和階段一文中的[復原](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#rollback)。
* 如需有關「認可」階段的資訊，請參閱案例執行、週期和階段一文中的[認可](/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md#commit)。

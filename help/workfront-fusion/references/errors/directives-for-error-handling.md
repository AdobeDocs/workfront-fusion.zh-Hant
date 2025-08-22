---
content-type: reference
title: 錯誤處理的指示
description: 本文說明可用於在Adobe Workfront Fusion案例中處理錯誤的指示。
author: Becky
feature: Workfront Fusion
exl-id: d7b0141f-d99d-4ab7-a60f-ed552a76f05d
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 15%

---

# 錯誤處理的指示

錯誤處理指令可讓您選擇案例發生錯誤時發生的情形。

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
   <td> 新增：標準<p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Adobe Workfront Fusion]授權</td> 
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
 </tbody> 
</table>


若要瞭解您擁有的計畫、授權型別或存取權，請聯絡您的Workfront管理員。

如需Adobe Workfront Adobe Workfront Fusion的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 錯誤處理的指示

Workfront Fusion中有以下錯誤處理指示。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>復原</p> <p> <img src="assets/rollback.png"> </p> </td> 
   <td> <ul><li><p>案例執行會立即停止。</li><li>所有模組都會啟動復原階段，嘗試將所有模組回復到其初始狀態。 </li><li>後續模組不會處理。</p></li><li> <p>在大多數情況下，案例會在案例設定下指定的連續錯誤數之後停用。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#number-of-consecutive-errors" class="MCXref xref">連續錯誤數</a>。</p> </li><li><p>案例執行狀態會標示為「錯誤」。</p></li></ul> <p><b>注意</b>：如果沒有將錯誤處理常式路由附加到模組，而且未勾選<a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions" class="MCXref xref">允許儲存不完整的執行</a>允許儲存在[！UICONTROL案例設定]下的不完整執行設定，則這是預設行為。</p> </td> 
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
   <td><ul><li> <p>情境執行的狀態儲存在未完成執行作業的佇列中，而錯誤可以手動解決。如需詳細資訊，請參閱<a href="/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md" class="MCXref xref">檢視並解決不完整的執行</a>。</p> <p>不過，也有一些例外。 如需詳細資訊，請參閱「設定案例設定」一文中的<a href="/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow" class="MCXref xref">允許儲存未完成的執行</a></a>。</p></li><li> <p>後續模組不會處理。</p></li><li> <p>若有未處理的套件，情境執行將按正常情況繼續。</p> </li><li><p>停用[！UICONTROL自動完成執行]選項時，案例執行狀態會標示為「警告」。</p></li></ul> <p>如需詳細資訊，請參閱本文中的<a href="#break" class="MCXref xref">[！UICONTROL分頁符號]</a>一節</p> </td> 
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

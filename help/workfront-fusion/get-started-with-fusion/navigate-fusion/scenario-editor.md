---
title: 案例編輯器
description: 情境編輯器可讓您在視覺介面中建立和編輯情境。
author: Becky
feature: Workfront Fusion
exl-id: 47ccecf0-751c-4026-96a9-329c33cb6801
source-git-commit: f968b9141173725160cea36575ad4e02a09a5e3f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 16%

---

# 案例編輯器

情境編輯器可讓您在視覺介面中建立和編輯情境。

![案例編輯器](assets/scenario-editor.jpg)

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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 開啟案例編輯器並新增模組：

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]** ![案例圖示](assets/scenarios-icon.png)。
1. 按一下問號圖示![問號圖示](assets/question-mark-full-size.png)，然後尋找並按一下您要開始使用的應用程式或服務。 如需設定模組的詳細資訊，請參閱[設定模組](/help/workfront-fusion/create-scenarios/add-modules/configure-a-modules-settings.md)。

## 可用的案例編輯器動作

### 執行您的情境

| 動作 | 詳細資料 |
|----------|----------|
| 測試執行情境 | 在啟用情景之前，請驗證情景是否以您預期的方式執行。 一旦啟用，情境將會根據其排程執行。 如果一切未如預期般執行，請參閱[新增錯誤處理](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md)以瞭解如何處理錯誤。 |

![執行案例按鈕](assets/run-your-scenario.png)

### 排程

| 動作 | 詳細資料 |
|----------|----------|
| 排程情境 | 依預設，一個案例每15分鐘執行一次。 您可以定義已啟動案例執行的時間和頻率，以變更此專案。 融合情境可以排程為每5分鐘執行一次。 如需詳細資訊，請參閱[排程情境](/help/workfront-fusion/create-scenarios/config-scenarios-settings/schedule-a-scenario.md)。 |

![排程面板](assets/scheduling-scenario-editor.png)

### 控制項

您可能需要按一下「控制項」區域中的三點圖示，才能檢視其中的部分控制項。

| 動作 | 詳細資料 |
|----------|----------|
| 儲存 <p>![儲存圖示](assets/save-icon.png)</p> | 儲存您的情境後，三點選單底下將顯示新版本，以備您日後需要存取時使用。 先前儲存的案例版本僅可使用60天。 |
| 案例設定 <p>![案例設定圖示](assets/scenario-settings-icon.png)</p> | 情境設定面板包含情境的進階設定。 如需有關可用設定的詳細資訊，請參閱[設定案例設定](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md)。 |
| 附註  <p>![筆記圖示](assets/notes-icon.png)</p> | 記錄情境。 其他使用者在情境中時可以檢視這些附註。 |
| 自動對齊 <p>![自動對齊圖示](assets/auto-align-icon.png)</p> | 自動對齊案例中的模組。 |
| 搜尋模組![搜尋模組](assets/search-modules-icon.png)  </p> | 輸入搜尋字詞以尋找模組，然後按一下要帶到該模組的搜尋結果。 您可以依模組名稱、ID、型別或應用程式來搜尋。 |
| 說明流程  <p>![說明流程圖示](assets/explain-flow-icon.png) </p> | 檢視移動點顯示資料如何流經情境的動畫。 |
| DevTool <p>![DevTool圖示](assets/devtool-icon.png)</p> | 使用DevTool，您可以檢查案例的所有手動執行、檢閱所有已執行的操作，並檢視每個已執行API呼叫的詳細資訊。 您可以檢視導致錯誤的模組、操作或單一回應，並運用該知識來調整您的案例。 如需詳細資訊，請參閱[偵錯案例](/help/workfront-fusion/manage-scenarios/debug-a-scenario.md)。 |
| 匯出Blueprint  <p>![匯出Bluepring圖示](assets/export-blueprint-icon.png) </p> | 匯出目前案例的藍圖。 |
| 匯入Blueprint  <p>![匯入Blueprint圖示](assets/import-blueprint-icon.png) </p> | 匯入先前匯出的情境藍圖。 |
| 先前版本  <p>![舊版圖示](assets//previous-version-icon.png) </p> | 檢視此情境的早期版本。 |

![控制項面板](assets/controls-editor-scenario.png)

### 工具

| 動作 | 詳細資料 |
|----------|----------|
| 流量控制 | 設定設定以控制資料流經的方式。 如需詳細資訊，[檢視需要的連結]。 |
| 工具 | 工具區段包含數個可增強案例的實用模組。 如需詳細資訊，[檢視需要的連結]。 |
| 文字剖析器 | 使用文字剖析器工具來剖析文字，以用於其他案例模組。 文字剖析器不需要連線。 如需詳細資訊，[檢視需要的連結]。 |

![工具面板](assets/tools-scenario-editor.png)

### 我的最愛

您可以使用我的最愛圖示來新增您經常使用的模組。

![我的最愛面板](assets/favorites-scenario-editor.png)

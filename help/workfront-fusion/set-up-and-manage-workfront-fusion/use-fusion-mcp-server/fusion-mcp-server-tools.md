---
title: Adobe Workfront Fusion MCP伺服器工具
description: Adobe Workfront Fusion MCP伺服器提供給AI代理平台和同事的工具參考清單。
source-git-commit: 322a34df48a5218bc045e6cac6a5a8b3837e8c2e
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 7%
---

# Adobe Workfront Fusion MCP伺服器工具


本文列出Adobe Workfront Fusion MCP伺服器向連線的AI代理程式公開的工具。 代理程式會在您要求尋找、檢查、建立、執行、更新或刪除Fusion專案時，代表您呼叫這些工具。

每個支援的表面都提供相同的工具：在Claude、ChatGPT、Copilot或您自己的代理程式中使用的自訂MCP連線；以及在Fusion右側邊欄中的獨立和Co-worker。 如需設定，請參閱[設定Adobe Workfront Fusion MCP伺服器](configure-fusion-mcp-server.md)。

代理程式會使用您的Adobe ID、Fusion組織角色和團隊角色在Fusion中運作。 只有當您在Fusion中有對應的許可權時，工具才能運作。 Adobe對代理程式對您的Fusion資料進行的變更概不負責。

## 讀取和寫入動作

每個工具分類為：

* **讀取**：擷取資訊而不變更任何專案，例如列出案例或取得執行。
* **寫入**：建立、變更、執行或刪除Fusion資料，例如複製案例或清除webhook佇列。

## 組織工具

作用中的組織會套用至目前作業階段中的所有其他工具。

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出組織 | `fusion_orgs_list` | 讀取 | 列出您可以存取的Fusion組織，包含ID、區域（區域）和標籤。 |
| 設定使用中組織 | `fusion_orgs_set` | Session | 切換目前工作階段的使用中組織。 不會變更任何Fusion資料 |

## 案例工具

### 情境

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出案例 | `fusion_scenarios_list` | 讀取 | 列出組織中的案例。 |
| 取得情境 | `fusion_scenarios_get` | 讀取 | 傳回情境，包括其完整的藍圖。 |
| 取得案例相依性 | `fusion_scenarios_getDependencies` | 讀取 | 傳回連線、金鑰、資料存放區、資料結構，以及Webhook情境的藍圖參照。 |
| 尋找相依案例 | `fusion_scenarios_dependents` | 讀取 | 尋找參考指定webhook、資料存放區、資料結構、連線、索引鍵或案例的案例。 在變更或刪除資源之前進行影響分析很有用。 |
| 驗證Blueprint | `fusion_scenarios_validate_blueprint` | 讀取 | 在結構上對團隊驗證Blueprint （模組參考、連線、必填欄位），而不儲存任何內容。 |
| 建立情境 | `fusion_scenarios_create` | 寫入 | 使用選填的名稱、說明、資料夾、排程和循序處理，從Blueprint在團隊中建立情境。 |
| 原地複製案例 | `fusion_scenarios_clone` | 寫入 | 將案例複製到相同或不同的群組中。 跨專案團隊進行複製時，您可以將每個連線、webhook、資料存放區、資料結構和金鑰對應到目標資源。 選擇性地從上次處理的記錄繼續。 |
| 更新案例 | `fusion_scenarios_update` | 寫入 | 變更名稱、說明、資料夾、排程或作用中狀態（啟用/停用）。 也可以還原已刪除的情境。 |
| 執行案例一次 | `fusion_scenarios_execute` | 寫入 | 執行案例一次，並等待結果（最多逾時），傳回狀態和任何錯誤訊息。 不支援即時（webhook觸發）情況。 |
| 刪除情境 | `fusion_scenarios_delete` | 寫入 | 刪除情境。 刪除的情境可以使用&#x200B;**更新情境**&#x200B;還原。 |

提示範例：

* _行銷團隊中的哪些作用中情境在6個月內未編輯？_
* _「Salesforce → Workfront同步」案例使用哪些連線？_
* _將「潛在客戶獲取」複製Sales Team，並在Sales Salesforce連線中進行交換。_
* _在我匯入此Blueprint之前先驗證它。_
* _執行一次[夜間報告]，並告訴我是否成功。_

### 案例版本

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出案例版本 | `fusion_scenario_versions_list` | 讀取 | 列出案例的已儲存版本。 依`version`、`createdAt`、`comment`篩選。 |
| 取得案例版本 | `fusion_scenario_versions_get` | 讀取 | 傳回特定版本的Blueprint和中繼資料。 |

提示範例：

* _此情境的第12版與第14版之間有何變更？_

### 資料夾

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出資料夾清單 | `fusion_folders_list` | 讀取 | 列出案例資料夾，其中包含案例計數。 |
| 建立資料夾 | `fusion_folders_create` | 寫入 | 在團隊中建立資料夾。 |
| 重新命名資料夾 | `fusion_folders_update` | 寫入 | 重新命名資料夾。 |
| 刪除資料夾 | `fusion_folders_delete` | 寫入 | 刪除資料夾。 |

## 執行工具

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出執行 | `fusion_executions_list` | 讀取 | 列出案例或不完整執行的執行。 依`status`篩選（例如`status==3`錯誤，`status==2`警告）、`timestamp`、`duration`、`bundles`、`operations`、`transfer`。 選擇性地包含檢查回合。 |
| 取得執行 | `fusion_executions_get` | 讀取 | 傳回單一執行及其案例或不完整執行的中繼資料。 |

提示範例：

* _顯示昨天失敗的「發票同步」執行，並摘要錯誤。_
* _此情境的哪個執行使用本週最多的作業？_

## 作業（使用）工具

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 取得作業 | `fusion_operations_get` | 讀取 | 傳回最多1年日期範圍的作業時間序列（依日或月）。 依團隊、案例或套件篩選；依模組、套件、案例或團隊分組。 |
| 取得作業摘要 | `fusion_operations_summary_by_org` | 讀取 | 傳回日期範圍中每個案例和團隊的總作業數，加上整體總數。 |

提示範例：

* _上個月的作業前10個案例。_
* _Salesforce應用程式在第3季使用了多少作業？_

## 連線和重要工具

這些工具只會傳回中繼資料。 它們不會傳回認證、權杖或機密值。

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 搜尋連線 | `fusion_connections_search` | 讀取 | 列出連線。 依`name`、`accountName`、`accountType`、`expire`、`teamId`、`scopesCount`、`editable`、`environmentType`、`authenticationType`篩選。 |
| 取得連線 | `fusion_connections_get` | 讀取 | 傳回單一連線的詳細資料。 |
| 搜尋索引鍵 | `fusion_keys_search` | 讀取 | 列出索引鍵。 依`name`、`typeName`、`teamId`篩選。 |
| 取得金鑰 | `fusion_keys_get` | 讀取 | 傳回單一金鑰的詳細資料。 |

提示範例：

* _哪些連線會在接下來的30天內到期，以及哪些案例會使用這些連線？_

## Webhook工具

### Webhook

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出Webhook | `fusion_hooks_list` | 讀取 | 列出Webhook （鉤點）。 依`name`、`teamId`、`type`、`enabled`、`gone`、`typeName`、`scenarioId`、`priority`、`detached`等篩選。 |
| 取得webhook | `fusion_hooks_get` | 讀取 | 傳回webhook的設定、擁有者繫結和外部參照。 |
| 尋找相依的Webhook | `fusion_hooks_dependents` | 讀取 | 尋找參考指定連線的Webhook。 |

### Webhook佇列

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | -------- | --- |
| 取得佇列統計資料 | `fusion_queue_stats` | 讀取 | 傳回已排入佇列的事件數、佇列限制，以及是否已啟用webhook。 |
| 清單佇列 | `fusion_queue_list` | 讀取 | 列出等待處理的已接收webhook事件。 |
| 取得佇列專案 | `fusion_queue_get` | 讀取 | 傳回單一佇列的事件，包括其解碼的裝載。 |
| 刪除佇列專案 | `fusion_queue_delete` | 寫入 | 刪除特定的佇列事件（最多50個）或清除佇列，選擇性地排除某些事件。 無法刪除目前處理中的事件。 |

提示範例：

* _「表單提交」webhook正在備份嗎？_
* _顯示排入佇列之最舊事件的承載。_

## 資料存放區和資料結構工具

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出資料存放區 | `fusion_datastores_list` | 讀取 | 列出具有記錄計數、大小和大小上限的資料存放區。 |
| 取得資料存放區 | `fusion_datastores_get` | 讀取 | 傳回資料存放區的中繼資料與使用方式、連結的資料結構，以及嚴格驗證設定。 |
| 列出資料存放區記錄 | `fusion_data_list` | 讀取 | 使用位移分頁從資料存放區讀取記錄（索引鍵+ JSON資料）。 |
| 尋找相依資料存放區 | `fusion_datastores_dependents` | 讀取 | 尋找使用指定資料結構的資料存放區。 |
| 搜尋資料結構 | `fusion_data_structures_search` | 讀取 | 列出資料結構。 依`name`、`strict`、`teamId`篩選。 |
| 取得資料結構 | `fusion_data_structures_get` | 讀取 | 傳回資料結構，包括其完整欄位規格。 |

提示範例：

* _哪些資料存放區已佔用80%以上？_
* _顯示[客戶地圖]資料存放區中的前20筆記錄。_

## 活動記錄工具

| 工具 | 名稱 | 動作 | 說明 |
| --- | --- | --- | --- |
| 列出活動記錄 | `fusion_activity_logs_list` | 讀取 | 列出組織的稽核事件（誰做了什麼、對哪個實體做了什麼、何時做了什麼）。 依`entity` （例如`scenario`、`connection`、`webhook`、`data store`、`user`）、`action` （例如`created`、`deleted`、`updated`、`transferred ownership`）、使用者、團隊和時間戳記。 |
| 匯出活動記錄 | `fusion_activity_logs_export` | 讀取 | 使用相同的篩選器將活動記錄匯出為CSV或XLSX。 |

提示範例：

* _過去7天刪除情境的訪客是誰？_
* _將本季的所有連線變更匯出至Excel。_

## 同事

本文中的所有工具都可在輔助程式中使用，包括獨立和Fusion右側邊欄，但須受相同的讀取/寫入設定和您的許可權限制。

## 如何更新工具

當Adobe發行新版Fusion MCP伺服器時，連線的代理程式會自動擷取更新的工具集。 您不需要重新連線。


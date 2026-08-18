---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: Fusion內容參考
description: Fusion內容參考
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 757
ht-degree: 8%

---

# Fusion內容參考

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

當您的UI呼叫`attach(...)`時，Fusion會共用描述目前工作階段的&#x200B;**內容**&#x200B;物件。 此頁面列出每個欄位、其含義以及Fusion和Adobe IMS識別碼的相關性。

## 如何閱讀內容

* **初始值：** `connection.sharedContext.get("<key>")`
* **更新：**&#x200B;接聽`contextchange`事件。 最新的物件到`event.detail.context`。

如需完整的程式碼模式，請參閱[建置自訂擴充功能UI](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-05-build-ui-procedure.md)。

```js
const organization = connection.sharedContext.get("organization");
const fusionOrgId  = organization?.id;        // Fusion's organization id
const imsOrgId     = connection.sharedContext.get("imsOrgId"); // Adobe IMS org id
```

## 最上層索引鍵

| 索引鍵 | 類型 | 說明 |
| ----- | ------ | ------------- |
| `imsToken` | 字串 | 登入使用者的Adobe **IMS存取權杖**。 將此作為`Bearer`權杖使用，以代表使用者呼叫Adobe或Fusion API。 **因為這是敏感專案，所以請勿記錄或顯示。** |
| `imsOrgId` | 字串 | Adobe **IMS組織ID**，格式為`XXXXXXXXXXXX@AdobeOrg`。 |
| `imsUserId` | 字串 | 登入使用者的Adobe **IMS使用者ID**。 |
| `organization` | 物件 | **完全作用中的Fusion組織**。 如需詳細資訊，請參閱本文中的[`organization`欄位](#organization-fields)。 |
| `team` | 物件\|未定義 | **完整作用中的Fusion團隊**，當一個團隊作用中（永遠與`fusion/nav-team/1`相關）時。 如需詳細資訊，請參閱本文中的[`team`欄位](#team-fields)。 |
| `user` | 物件 | **完整登入的Fusion使用者**。 如需詳細資訊，請參閱本文中的[`user`欄位](#user-fields)。 |

### Fusion ID和IMS ID

每個實體都有&#x200B;**Fusion ID** （由Fusion自己的API使用），以及其中存在的&#x200B;**Adobe IMS ID** （由Adobe平台API使用）：

| 實體 | Fusion ID | Adobe IMS ID |
| -------- | ----------- | -------------- |
| 組織 | `organization.id` | `imsOrgId` （也公開為`organization.externalOrgId`） |
| 團隊 | `team.id` | *（團隊僅限Fusion；無IMS ID）* |
| 使用者 | `user.id` | `imsUserId` |

## `organization`欄位

這些欄位可在使用中組織記錄中找到。 大部分的擴充功能只需要`id`、`name`和識別碼。

| 欄位 | 類型 | 說明 |
| ------- | ------ | ------------- |
| `id` | 字串 | Fusion組織ID。 |
| `name` | 字串 | 組織顯示名稱 |
| `externalOrgId` | 字串 | Adobe IMS組織ID （與`imsOrgId`的值相同）。 |
| `externalId` | 字串 | Fusion整合使用的外部識別碼 |
| `countryId` | 字串 | 國家/地區設定ID。 |
| `timezoneId` | 字串 | 時區設定ID |
| `serviceName` | 字串 | 服務/計畫識別碼 |
| `teamIds` | 字串[] | 此組織中團隊的ID |
| `license` | 物件 | 計畫限制和權益，例如作業、資料傳輸、使用者座位和功能標幟 |
| `scenariosCount` | 數字 | 組織中的案例總數 |
| `activeScenarios` | 數字 | 目前使用中的案例 |
| `activeApps` | 數字 | 作用中的應用程式或連線數目 |
| `operations`, `operationsExt` | 數字 | 作業使用量計數器 |
| `transfer`, `transferExt` | 數字 | 資料傳輸使用量計數器 |
| `isPaused` | 布林值 | 組織是否已暫停 |
| `isDeleted` | 布林值 | 組織是否標籤為已刪除 |
| `imsEnabled` | 布林值 | 組織是否已連結至Adobe IMS |
| `usersCount` | 數字 | 組織中的使用者人數 |
| `nextReset` | 字串（日期） | 下次重設使用計數器時。 檢視[日期](#dates) |

## `team`欄位

當團隊處於活動狀態時，這些欄位就會出現。 您必須提供後援以備團隊為`undefined`時使用（例如在未選取團隊的組織層級畫面上）。

| 欄位 | 類型 | 說明 |
| ------- | ------ | ------------- |
| `id` | 字串 | Fusion團隊ID。 |
| `name` | 字串 | 群組顯示名稱。 |
| `organizationId` | 字串 | 此團隊所屬組織的Fusion ID。 |
| `country` | 字串 | 團隊國家設定。 |
| `timezone` | 字串 | 團隊時區。 |
| `license` | 物件 | 團隊層級的限制和權益。 |
| `activeScenarios` | 數字 | 團隊中的作用中案例。 |
| `activeApps` | 數字 | 團隊中的作用中應用程式或連線。 |
| `scenarioDrafts` | 布林值 | 案例草稿是否已啟用。 |
| `isDeleted` | 布林值 | 團隊是否標籤為已刪除。 |
| `created` | 字串（日期） | 建立團隊的時間。 檢視[日期](#dates)。 |

## `user`欄位

這些欄位適用於登入的Fusion使用者。

| 欄位 | 類型 | 說明 |
| ------- | ------ | ------------- |
| `id` | 字串 | Fusion使用者ID。 |
| `name` | 字串 | 完整名稱。 |
| `email` | 字串 | 電子郵件地址。 |
| `avatar` | 字串 | 顯示圖片影像URL。 |
| `locale` | 字串 | 使用者地區設定，例如`en`。 |
| `language` | 字串 | 偏好語言（設定後）。 |
| `timezone` | 字串 | 時區名稱。 |
| `timezoneId` | 字串 | 時區設定識別碼。 |
| `countryId` | 字串 | 國家/地區設定ID。 |
| `localeId` | 字串 | 地區設定識別碼。 |
| `features` | 物件 | 每個使用者的功能標幟（例如`allow_apps`， `public_templates`）。 |
| `usersAdminsRoleId` | 字串 | 使用者的管理員角色ID （如適用）。 |

>[!NOTE]
>
> `user`物件可能包含其他內部欄位。 您應該僅依賴此處記錄的欄位。 其他欄位可以變更而不另行通知，並且某些驗證相關的欄位不得記錄或顯示。

## 日期

內容在到達您的擴充功能之前已序列化，因此&#x200B;**日期欄位會以字串** （ISO 8601，例如`"2026-06-24T00:00:00.000Z"`）送達，而非JavaScript `Date`物件。 您可以視需要轉換這些專案：

```js
const resetDate = new Date(context.organization.nextReset);
```

## 內容更新

Fusion會在下列情況重新傳送整個內容（透過`contextchange`）：

* 使用者&#x200B;**切換組織**，
* 使用者&#x200B;**切換群組**，或
* **登入使用者的**&#x200B;資訊已變更。

一律重新讀取您在`contextchange`處理常式內使用的所有金鑰，而非假設只有一個值已變更。

## 安全性最佳實務

* **永不記錄、顯示或保留`imsToken`。** 將其視為密碼。
* 僅透過HTTPS將權杖作為`Bearer`權杖傳送給信任的Adobe/Fusion端點。
* 請勿儲存超出功能需求之內容中的個人資料。

## 使用權杖來呼叫API

若要將`imsToken` （加`organization.id` / `team.id`）轉換為真正的Workfront或
Fusion資料中，由於CORS會封鎖，因此您無法直接從瀏覽器呼叫這些API
it. 改為透過小型App Builder執行階段動作路由呼叫。 另請參閱
[正在呼叫Workfront和Fusion API](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-10-calling-apis.md)。


若要繼續建立自訂擴充功能的程式，請參閱[發佈您的擴充功能](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-07-publish.md)。

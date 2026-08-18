---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 設定UI擴充功能工具和帳戶
description: 設定UI擴充功能工具和帳戶
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
source-wordcount: 500
ht-degree: 0%

---


# 設定UI擴充功能工具和帳戶

您必須先設定工具和帳戶，才能為Workfront Fusion建立UI擴充功能。 此作業只需要執行一次。

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

<!--Access requirements-->

## 先決條件

若要設定UI擴充性工具和帳戶，您需要下列專案：

* **可存取Adobe組織的Adobe ID**。 這是您用來登入Fusion的帳戶。
* **開發人員存取App Builder。** 您的組織管理員可能需要授予&#x200B;**開發人員**&#x200B;角色，並將您新增至包含App Builder的&#x200B;**產品設定檔**。 如果命令在稍後以「您不是開發人員」失敗或無法看見您的組織，請要求Adobe組織管理員新增您。
* **系統管理員** <!--Adobe? Fusion?--> （可能是您團隊中的其他人）以進行最終發行步驟。 建立及部署只需要開發人員角色，但&#x200B;**提交擴充功能以進行核准/發佈需要系統管理員角色**。

  如需Adobe存取層級的詳細資訊，請參閱
  在Adobe檔案中[如何取得存取權](https://developer.adobe.com/uix/docs/guides/get-access/)。

* **您可以安裝軟體**&#x200B;並執行終端機命令（macOS、Windows或Linux）的電腦。

## 安裝節點.js

Adobe工具會在&#x200B;**Node.js**&#x200B;上執行。 您必須安裝&#x200B;**LTS**&#x200B;版本（18或20）。

1. 移至<https://nodejs.org>並下載&#x200B;**LTS**&#x200B;安裝程式。
1. 執行安裝程式並接受預設值。
1. 開啟終端機並執行，確認運作正常：

   ```sh
   node --version
   npm --version
   ```

   您應該會看到版本號碼（例如`v20.17.0`和`10.x`）。

1. （條件式）如果找不到`node`，請關閉並重新開啟您的終端機，或重新啟動您的電腦。

1. 繼續[安裝Adobe I/O CLI (`aio`)](#install-the-adobe-io-cli-aio)。

>[!TIP]
>
>* 如果您使用多個Node版本，則使用`nvm`等版本管理員會很方便，但這是選擇性的。
>* Adobe CLI需要Node 18或更新版本。 非常新的非LTS版本偶爾可能會造成問題，因此我們建議您使用LTS。

## 安裝Adobe I/O CLI (`aio`)

您用來建立、建置和發佈擴充功能的命令列工具稱為`aio`。

若要全域安裝：

1. 在命令列上使用下列`npm`命令。

   ```sh
   npm install -g @adobe/aio-cli
   ```

1. 使用下列命令確認是否已安裝它：

   ```sh
   aio --version
   ```

   您應該會看到`@adobe/aio-cli/11.x.x`之類的內容。

1. 繼續[登入Adobe](#sign-in-to-adobe)。

>[!NOTE]
>
> 如果您在macOS/Linux上看到許可權錯誤，請&#x200B;**不**&#x200B;使用`sudo`。 請改為修正npm的全域檔案夾許可權，或使用安裝在主目錄中的Node版本管理員。

## 登入Adobe

1. 使用以下命令將CLI連線至您的Adobe帳戶：

   ```sh
   aio login
   ```

1. 在開啟的瀏覽器視窗中，使用您的Adobe ID登入並核准存取權。

1. 登入成功後，請關閉瀏覽器標籤並返回終端機。

1. （選擇性）若要稍後登出（例如切換帳戶），請使用命令： `aio logout`。
1. 繼續[確認您使用中的組織](#confirm-your-active-organization)。

## 確認您使用中的組織

檢查CLI指向哪個組織：

```sh
aio console org list      # see organizations you can use
aio console where         # see your currently selected org/project/workspace
```

如果您屬於數個組織，請選取正確的組織：

```sh
aio console org select
```

您現在已準備好建立專案。

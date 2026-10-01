---
title: 設定Adobe Workfront Fusion MCP伺服器
description: 將Adobe Workfront Fusion連線至與MCP相容的AI代理平台或同事（獨立版或在Fusion右側邊欄中）。
source-git-commit: 6d447c16d199c69ae670f59bb56cf79464cbe057
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 0%
---

# 設定Adobe Workfront Fusion MCP伺服器

Adobe Workfront Fusion MCP伺服器可讓您在支援的AI代理平台上，透過自然語言對話處理Fusion組織的情境、執行、連線、Webhook、資料儲存等等。

如需Adobe Workfront Fusion MCP伺服器中可用的工具清單，請參閱[Adobe Workfront Fusion MCP伺服器工具](/help/workfront-fusion/set-up-and-manage-workfront-fusion/use-fusion-mcp-server/fusion-mcp-server-tools.md)。

## 支援的AI代理平台

Fusion MCP伺服器可與任何支援Model Context Protocol (MCP)和具有OAuth的遠端（可串流的HTTP） MCP伺服器的AI代理平台搭配使用。

>[!NOTE]
>
> Adobe目前不在Claude聯結器目錄或ChatGPT應用程式/外掛程式目錄中發佈Workfront Fusion聯結器。 如本文所述，若要搭配Claude、ChatGPT或Microsoft Copilot使用Fusion，請根據URL將其新增為&#x200B;**自訂MCP伺服器**。

本文將逐步說明下列專案的連線步驟：

* [Adobe同事](#use-fusion-with-coworker)： Fusion右側邊欄中的同事作為獨立工作者和同事
* [Claude](#connect-fusion-to-claude)：自訂聯結器
* [ChatGPT](#connect-fusion-to-chatgpt)：自訂MCP伺服器
* [自訂MCP解決方案](#connect-fusion-to-a-custom-mcp-solution)

>[!IMPORTANT]
>
>如果您使用不同的MCP相容平台，例如Gemini、Cursor或VS Code，請遵循該平台的檔案來新增自訂MCP伺服器。 當系統提示MCP伺服器URL時，請輸入：
>
>```
>https://mcp.fusion.adobe.com/mcp
>```

## 先決條件

在將Fusion連線到AI代理平台之前，您必須：

* 擁有使用中的Adobe Workfront Fusion授權，並存取至少一個Fusion組織。
* 擁有Fusion使用者角色和團隊角色，可授予您要使用之資料的存取權。
* 使用Adobe ID （Adobe Identity Management系統、IMS）登入。
* 可以存取相容於MCP的AI代理平台，或存取同事。

## 搭配同事使用Fusion

同事是Adobe的AI代理程式。 Fusion內建在Co-worker中，因此您不需要輸入MCP URL或註冊OAuth應用程式。 您可以在兩個位置使用Co-worker with Fusion：

* [同事（獨立）](#use-fusion-in-coworker)：搭配其他Adobe應用程式使用Fusion。
* [Fusion右側邊欄中的同事](#use-coworker-in-the-fusion-right-rail)：在Fusion UI內的面板中開啟同事。

兩者都使用相同的Fusion MCP工具、您的Adobe ID和Fusion許可權。 「讀取」或「寫入」MCP工具設定會同時套用在這兩個工具中。 破壞性動作（例如刪除、清除佇列或覆寫）一律會要求確認。

### 在同事中使用Fusion

1. 開啟同事。
2. 開啟&#x200B;**自訂** > **整合**
3. 尋找&#x200B;**fusion-mcp**&#x200B;並按一下&#x200B;**測試**。
4. 如果您可以存取多個Fusion組織，則會自動選取該組織。 如有需要，您可以要求同事稍後切換組織。

### 在Fusion右側邊欄中使用同事

在Fusion中，同事會在右側邊欄中開啟

1. 登入Workfront Fusion。
2. 按一下右側邊欄中的&#x200B;**同事**&#x200B;圖示。
3. 在面板中提出問題。

### 提示範例

* *顯示過去24小時內無法執行的所有案例。*
* *列出本週建立或刪除的所有情境，依最近的順序排序。*
* *此情境在做什麼？*
* *為什麼此執行失敗？*

## 將Fusion連線至Claude

將Fusion新增為自訂聯結器。

>[!NOTE]
>
> 在Claude Team/Enterprise中，您必須是擁有者才能新增自訂聯結器。 如需詳細資訊，請參閱Claude檔案中的[使用遠端MCP開始使用自訂聯結器](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)。

1. 登入[克勞德](https://claude.ai)。
2. 在左側功能表中，選取&#x200B;**自訂**。
3. 選取&#x200B;**聯結器**。
4. 選取&#x200B;**+**，然後選取&#x200B;**新增自訂聯結器**。
5. 輸入名稱（例如「Workfront Fusion」）和MCP伺服器URL：

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

6. 按一下&#x200B;**連線**。
7. 登入。 選取設定檔和Fusion組織。

對於Claude程式碼，您可以從命令列新增伺服器：

```
claude mcp add --transport http fusion-mcp https://mcp.fusion.adobe.com/mcp
```

## 將Fusion連線到ChatGPT

將Fusion新增為自訂MCP伺服器。

### ChatGPT Desktop或程式碼

1. 在ChatGPT中，開啟&#x200B;**設定**。
2. 按一下&#x200B;**外掛程式**。
3. 按一下&#x200B;**新增伺服器**。
4. 輸入伺服器的名稱。
5. 針對型別，選取&#x200B;**可串流的HTTP**。
6. 輸入MCP伺服器URL：

   ```
   https://mcp.fusion.adobe.com/mcp
   ```

7. 按一下「**儲存**」。
8. 按一下新伺服器的&#x200B;**驗證**&#x200B;並登入。
9. 請確定伺服器旁的切換開關已開啟。

### 網頁上的ChatGPT

1. 登入[ChatGPT](https://chatgpt.com)。
2. 移至[https://chatgpt.com/plugins](https://chatgpt.com/plugins)。 （可能需要在&#x200B;**設定**&#x200B;下啟用開發人員模式；在商業/企業計畫中，管理員必須允許自訂聯結器。）
3. 按一下&#x200B;**+**。
4. 輸入&#x200B;**名稱**。
5. 針對&#x200B;**連線**，選取&#x200B;**伺服器URL**，並輸入MCP伺服器URL。
6. 保留&#x200B;**驗證**&#x200B;設定為&#x200B;**OAuth**。
7. 閱讀風險訊息並選取核取方塊。
8. 按一下「**建立**」，然後使用您的登入。

## 將Fusion連線至自訂MCP解決方案

如果您正在建置自己的應用程式或代理程式，請直接連線到Fusion MCP伺服器。

## 切換到其他Fusion組織

您不需要中斷連線即可變更組織。 Fusion MCP伺服器可以在工作階段中切換作用中組織：

* _我有哪些Fusion組織？_
* _切換至1234組織。_

代理程式使用`fusion_orgs_list`和`fusion_orgs_set`。 切換器只適用於目前的交談/工作階段。 位於不同資料中心區域（例如，美國和EU）的組織都可透過相同的MCP URL使用。

## 疑難排解設定和驗證

| 問題 | 可能的原因 | 修正 |
| --- | --- | --- |
| 在Claude或ChatGPT目錄中找不到Fusion聯結器。 | Adobe不會發佈Fusion的目錄聯結器。 | 使用本文中的URL新增Fusion作為自訂MCP伺服器。 |
| 您不能在Claude或ChatGPT中新增自訂聯結器。 | 您的計畫會將自訂聯結器限製為擁有者或管理員。 | 請要求您的Claude或ChatGPT管理員新增聯結器或允許自訂MCP伺服器。 |
| 您已連線，但看不到任何資料或資料錯誤。 | 錯誤的Fusion組織為作用中。 | 要求代理程式列出您的組織並切換至正確的組織。 |
| 驗證失敗或連線已停止運作。 | 工作階段過期或連線錯誤。 | 中斷伺服器連線並重新連線。 |
| 您會看到MCP存取被停用的訊息。 | 您的Fusion組織的MCP存取已關閉。 | 請要求您的Fusion管理員啟用它。 |
| 代理程式可讀取情境，但無法建立、執行、更新或刪除情境。 | 寫入MCP工具已停用，或您的團隊角色不允許使用。 | 請要求Fusion管理員啟用寫入工具，或授予您必要的團隊角色。 |
| 自訂應用程式驗證遭拒。 | 回呼URL不在授權清單上。 | 請要求您的管理員新增精確的回呼URL。 |
| Fusion未列在Co-worker中，或Fusion右側邊欄中缺少Co-worker。 | 您的組織未啟用此功能。<!-- BECKY CHECK ME: confirm whether this is the correct admin guidance before publishing. --> | 請連絡您的Fusion管理員。 |

## 常見問題

### 是否有適用於Claude或ChatGPT的官方Fusion聯結器？

目前不可以。 使用自訂MCP伺服器URL。 Co-worker （獨立式和Fusion右側邊欄中的）已內建Fusion。

### 我可以使用多個Fusion組織嗎？

是。 您可以在對話期間切換使用中組織，而不需要重新連線。

### 代理程式可以代表我做什麼？

代理程式會使用您的Fusion角色和團隊許可權，以您身分來扮演您的角色。 它無法存取您在Fusion中無法存取的任何內容。 破壞性動作需要明確確認。

### 代理程式是否看到我的連線密碼？

否。 連線和金鑰工具會傳回中繼資料（名稱、型別、範圍、有效期），而非認證或密碼值。

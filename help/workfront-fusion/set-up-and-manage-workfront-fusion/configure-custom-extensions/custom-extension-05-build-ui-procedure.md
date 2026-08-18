---
product-previous: workfront-fusion
product-area: workfront-integrations
keywords: Fusion
navigation-topic: workfront-fusion-navigation-topic
title: 建立自訂擴充功能UI
description: 建立自訂擴充功能UI
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: bbc94bb0-7432-44c5-8000-9aea25916b28
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
source-git-commit: a9dd86f7dc4070ad98c7c4a526a6a38939097940
workflow-type: tm+mt
source-wordcount: 440
ht-degree: 0%

---


# 建立自訂擴充功能UI

>[!NOTE]
>
>本文假設您已熟悉軟體開發工具。

此程式說明如何使用Fusion建置使用者實際看到的畫面，以及完成&#x200B;**連線（「交握」）**。

在此過程中，請務必記得您的擴充功能會在兩個框架中執行：隱藏的&#x200B;**註冊**&#x200B;框架與可見的&#x200B;**UI**&#x200B;框架。

如需與自訂擴充功能相關的框架資訊，請參閱[包含在UI擴充功能中的框架](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-01-overview.md#frames-included-in-a-ui-extension)。

如需建立登入框架的相關指示，請參閱[建立UI擴充性的專案](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md)。

## 在兩個影格之間繞線

兩個框架載入相同的`index.html`；小型前端路由器會根據URL決定要顯示哪個元件。

1. 在`web-src/src/components/App.js`中設定路由。 重要部分為：

   ```jsx
   import { HashRouter as Router, Routes, Route } from "react-router-dom";
   import ExtensionRegistration from "./ExtensionRegistration";
   import DashboardWidget from "./DashboardWidget";
   
   export default function App() {
     return (
       <Router>
         <Routes>
           {/* Background frame: registers the extension with Fusion */}
           <Route index element={<ExtensionRegistration />} />
           <Route path="index.html" element={<ExtensionRegistration />} />
   
           {/* Visible frame: the URL you returned from getWidget() */}
           <Route path="my-widget" element={<DashboardWidget />} />
         </Routes>
       </Router>
     );
   }
   ```

   這些路由對應到先前的設定，如下所示：

   * 預設路由(`index`)會轉譯&#x200B;**`ExtensionRegistration`**，即呼叫`register(...)`的隱藏框架。
   * `my-widget`路由會轉譯&#x200B;**`DashboardWidget`**，您的可見使用者介面。 這符合您在[上一頁](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-03-04-create-project-configure-fusion.md)中從`getWidget()`傳回的`url: "/index.html#/my-widget"`。

   >[!NOTE]
   >
   > **路由和`getWidget` URL必須一致。** 如果您變更路由名稱，也請變更`url`，否則Fusion將載入空白頁面。

1. 繼續[完成與`attach`](#complete-the-handshake-with-attach)的交握。

## 使用`attach`完成交握

這是您可見UI中最重要的一行。 Fusion開啟您的UI框架時，會等待該框架「簽入」。 您的程式碼會呼叫`attach({ id })`以簽入。

**如果省略，Fusion會逾時**&#x200B;並發生錯誤，例如&#x200B;*&quot;正在等待來自目標iframe的初始訊息。&quot;*

1. 將下列專案新增至`web-src/src/components/DashboardWidget.js`：

   ```jsx
   import { useEffect, useState } from "react";
   import { attach } from "@adobe/uix-guest";
   import { extensionId } from "./Constants";
   
   export default function DashboardWidget() {
     const [connection, setConnection] = useState(null);
   
     useEffect(() => {
       // Tell Fusion this UI frame is ready. Required.
       attach({ id: extensionId })
         .then(setConnection)
         .catch((e) => console.error("attach failed", e));
     }, []);
   
     if (!connection) {
       return <p>Connecting to Fusion...</p>;
     }
   
     return <h2>Hello from my Fusion extension!</h2>;
   }
   ```

   此程式碼會執行下列動作：

   * Fusion回應後，`attach({ id })`會傳回&#x200B;**連線物件**。 我們建議您儲存此專案，因為您將在下一個步驟中使用此專案來讀取Fusion傳送的內容。
   * 在連線解析之前，簡短「連線……」 訊息便會顯示。
   * 使用您在`Constants.js`中設定的&#x200B;**相同`extensionId`**。

   此時，您具有有效的擴充功能：它會註冊、附加及顯示訊息。 之後的所有事都與使用Data Fusion有關。

1. 繼續[讀取內容Fusion共用](#read-the-context-fusion-shares)。

## 讀取內容Fusion共用

附加後，連線會公開&#x200B;**共用內容**，其中包含目前使用者、組織和團隊的相關資訊。 您可以使用`connection.sharedContext.get("<key>")`讀取個別值：

```jsx
const orgId = connection.sharedContext.get("imsOrgId");
const organization = connection.sharedContext.get("organization"); // full Fusion org
const user = connection.sharedContext.get("user");                 // full Fusion user
```

此範例顯示一個完整的、被動的範例，當使用者切換組織或團隊時也會更新：

```jsx
import { useEffect, useState } from "react";
import { attach } from "@adobe/uix-guest";
import { extensionId } from "./Constants";

const KEYS = ["imsOrgId", "imsUserId", "organization", "team", "user"];

function readContext(source) {
  // sharedContext behaves like a Map (.get); the change event gives a plain object.
  const get =
    typeof source.get === "function" ? (k) => source.get(k) : (k) => source[k];
  return Object.fromEntries(KEYS.map((k) => [k, get(k)]));
}

export default function DashboardWidget() {
  const [context, setContext] = useState(null);

  useEffect(() => {
    let cleanup = () => {};
    attach({ id: extensionId })
      .then((connection) => {
        // 1) initial values
        setContext(readContext(connection.sharedContext));

        // 2) react to org/team/user changes pushed by Fusion
        const onChange = (event) =>
          setContext(readContext(event?.detail?.context ?? connection.sharedContext));
        connection.addEventListener("contextchange", onChange);
        cleanup = () => connection.removeEventListener?.("contextchange", onChange);
      })
      .catch((e) => console.error("attach failed", e));
    return () => cleanup();
  }, []);

  if (!context) return <p>Connecting to Fusion...</p>;

  return (
    <div>
      <h2>{context.organization?.name ?? "No organization"}</h2>
      <p>Signed in as {context.user?.name} ({context.user?.email})</p>
      <p>IMS org: {context.imsOrgId}</p>
    </div>
  );
}
```

請記住以下事項：

* **在`attach`之後立即從`connection.sharedContext.get(key)`讀取初始值**。
* **訂閱`contextchange`**&#x200B;以保持同步。 Fusion會在作用中組織、團隊或使用者變更時觸發此事件。 新值於`event.detail.context`到達。

如需金鑰的完整清單，每個金鑰所包含的內容都包含在[Fusion內容參考](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)中。

若要繼續設定自訂擴充功能的程式，請移至[Fusion內容參考](/help/workfront-fusion/set-up-and-manage-workfront-fusion/configure-custom-extensions/custom-extension-06-context-reference.md)。

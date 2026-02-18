---
title: 在您的情境中新增AI提示
description: 您可以在情境中加入AI提示，此提示會連線至您的
author: Becky
feature: Workfront Fusion
source-git-commit: 09e8ca28c12990a699816671d07f85288d973bc7
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---

# 將AI提示新增至您的情境

您可以使用結合大型語言模型(LLM)的「模型上下文通訊協定」(MCP)，在情境中加入AI提示。 在MCP代理程式模組中設定這些專案，您可以使用人工智慧來設定高效率、安全且有彈性的工作流程。

>[!NOTE]
>
>此功能與使用AI將模組新增到情境的功能不同。
>
>如需使用AI新增模組的資訊，請參閱[使用AI產生案例區段](/help/workfront-fusion/create-scenarios/add-modules/add-a-module-with-ai.md)。

## 模型內容通訊協定概觀

模型上下文通訊協定(MCP)是一種將AI語言模型與其他應用程式安全連線的方法。 您可以設定MCP伺服器，讓AI模型存取應用程式。 然後，您可以向AI模型傳送提示，它可以從應用程式返回資訊。

例如，您可以設定MCP伺服器來連線AI模型與Gmail。 當您傳送提示「Give my last 5 email from Gmail」給大型語言模型時，它會剖析該提示並傳送給Gmail MPC伺服器，然後伺服器可以存取您的Gmail並傳回電子郵件。

「MCP代理程式」模組可讓您使用語言模型和MCP伺服器來處理使用者提示。

## 在您的Fusion案例中使用MCP的優點

在情境中使用MCP可提供下列優點：

* 在情境中使用MCP可減少思考所有情境和動作可能變體的需求。 透過使用提示，您就不需要使用規則運算式或剖析資料來說明這些變化。
* 您可以使用對應自先前模組的元素，或對應面板中的其他函式，提供提示的前後關聯。
* 使用提示比使用特定模組建置情境更有效率、更靈活，因為它可以在提示上使用推理，並從可用的前後關聯中選取最佳動作過程。
* 因為您設定模組可連線的MCP伺服器，所以您可以控制該伺服器的安全性，而且可以確定安全性符合您組織的需求。

>[!NOTE]
>
>可用的功能取決於MCP伺服器中可用的工具，而不受Fusion控制。

## 將AI提示新增至您的情境

您可以使用MCP代理程式模組，將AI提示新增到您的情境。

如需指示，請參閱[MCP代理程式模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/model-context-protocol-mcp-connector.md)。

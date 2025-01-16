---
title: HTTP要求方法
description: 當您在模組中設定API呼叫時，必須選取HTTP要求方法。 本文會介紹可用的方法，以及選取每個方法的原因。
author: Becky
feature: Workfront Fusion
exl-id: 481131c9-356a-4c62-a653-d6bba9be5be8
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# HTTP要求方法

當您在模組中設定API呼叫時，必須選取HTTP要求方法。 本文會介紹可用的方法，以及選取每個方法的原因。

## HTTP方法

使用下列其中一個HTTP方法。

* **[!UICONTROL GET]**：根據您的引數從網頁伺服器擷取資料。 [!UICONTROL GET]要求指定資源的表示法，並在成功時收到包含所要求內容的[!UICONTROL 200 OK]回應訊息。
* **[!UICONTROL POST]**：根據您的引數傳送資料至網頁伺服器。 [!UICONTROL POST]個要求包含上傳檔案之類的動作。 多個[!UICONTROL POST]可能會產生與單一[!UICONTROL POST]不同的結果，因此請小心不要無意間傳送多個[!UICONTROL POST]。如果[!UICONTROL POST]成功，您會收到[!UICONTROL 200 OK]回應訊息。
* **[!UICONTROL PUT]**：根據您的引數，將資料傳送至網頁伺服器的位置。 [!UICONTROL PUT]個要求包含上傳檔案之類的動作。 [!UICONTROL PUT]與[!UICONTROL POST]之間的差異在於PUT為等冪，這表示單一成功[!UICONTROL PUT]的結果與許多相同的[!UICONTROL PUT]相同。如果PUT成功，您會收到200回應訊息（通常是201或204）。
* **[!UICONTROL PATCH]**： （部分API呼叫模組無法使用）根據您的引數，將部分修改套用至網頁伺服器上的資源。 [!UICONTROL PATCH]不是等冪，這表示多個[!UICONTROL PATCH]的結果可能會產生非預期的後果。 如果[!UICONTROL PATCH]成功，您將會收到200則回應訊息（通常是204）。
* **[!UICONTROL DELETE]**：根據您的引數（如果資源存在），從網頁伺服器刪除指定的資源。 如果[!UICONTROL DELETE]成功，您會收到「200確定」回應訊息。

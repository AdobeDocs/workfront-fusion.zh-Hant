---
title: 編輯Webhook
description: 您可以編輯Workfront和Workfront Planning聯結器的現有Webhook。
author: Becky
feature: Workfront Fusion
source-git-commit: 2561c911b9b542a7b143fae745baf4e1de45be38
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# 編輯Webhook

您可以編輯現有的Webhook。 使用這些webhook的案例會使用新的配置來進行，如此一來，就不需要建立新的webhook並將其手動指派給所有受影響的案例。

只能為下列聯結器編輯Webhook：

* Workfront
* Workfront 規劃

>[!IMPORTANT]
>
>更新webhook時，請考量下列事項：
>
>* Workfront事件訂閱會將編輯後的webhook視為新訂閱。 系統不會保留先前webhook設定的事件訂閱歷史記錄，因為這會視為個別的事件訂閱。
>* 從舊事件訂閱切換到新事件訂閱可能不會完全同步。 因此，可能會收到事件兩次（如果新訂閱在舊訂閱停止之前開始執行），或錯過事件（如果舊訂閱在新訂閱開始執行之前停止）。

## 編輯webhook

您可以從案例或Webhooks清單中編輯Webhook。

### 在情境中編輯webhook

>[!NOTE]
>
>此功能僅適用於具有Workfront或Workfront Planning即時觸發程式模組的案例。

1. 移至包含您要編輯的webhook的情境。
1. 在情境的觸發程式模組中，按一下Webhook欄位旁的下拉式清單，然後選取&#x200B;**編輯專案**。

   webhook的設定視窗會開啟，並填入現有設定。

1. 對webhook進行任何所需的編輯。
1. 按一下「**儲存**」來儲存此 Webhook 並返回模組。

### 從Webhook清單編輯Webhook

1. 在左側導覽中，選取&#x200B;**Webhooks** ![Webhooks圖示](assets/webhooks-icon.png)。
1. 按一下您要編輯的webhook旁的核取方塊。
1. 在熒幕底部的藍色橫幅中，按一下&#x200B;**編輯**。
1. 對webhook進行任何所需的編輯。
1. 按一下&#x200B;**儲存**&#x200B;以儲存webhook並返回Webhook清單。


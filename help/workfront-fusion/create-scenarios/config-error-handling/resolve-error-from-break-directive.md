---
title: 解決Break指示詞處理的錯誤
description: 有時候，如果故障原因可能很快解決，則重新執行失敗的模組會很有用。
author: Becky
feature: Workfront Fusion
exl-id: d568942c-2cd5-430c-bdbf-e1496da25b50
source-git-commit: 55fe4bc46bc50ad9ccfd1b234e89028cf3cd12d5
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# 解決Break指示詞處理的錯誤

當錯誤由Break指令處理時，會在Incomplete executions資料夾中建立記錄。 此記錄會儲存案例執行的狀態，以及先前模組的資料。 記錄會參考引發錯誤的模組，並包含模組收到作為輸入之資料的相關資訊。 對於導致錯誤的每個資料束，都會建立個別記錄。

如需詳細資訊，請參閱[檢視並解決不完整的執行](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)。

## 解決由Break指示詞造成的錯誤

您可以手動解決錯誤，方法是更新情境（如果需要）並執行一次該情境。

您也可以設定情境，透過重新執行情境來自動處理不完整的執行。 若要設定模組以處理未完成的執行：

1. 按一下左側面板中的&#x200B;**[!UICONTROL Scenarios]**&#x200B;索引標籤。
1. 選取您要新增因應措施的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下&#x200B;**流量控制**&#x200B;圖示![流量控制](assets/flow-control-icon.png)並選取&#x200B;**中斷**。
1. 在Break模組內，啟用&#x200B;[!UICONTROL **自動完成執行**]&#x200B;選項。
1. 在&#x200B;**嘗試次數**&#x200B;欄位中，輸入或對應您希望模組重試執行的嘗試次數上限

   此數字必須介於1到100之間。
1. 在&#x200B;**嘗試間隔**&#x200B;欄位中，輸入或對應每次重試之間的分鐘數。

啟用此選項後，當發生錯誤時，會擷取不完整的執行（在[!UICONTROL Interval between attempts]欄位中指定的時間之後）並使用原始輸入資料執行。 這將重複執行，直到模組執行完成且沒有錯誤，或直到達到指定的嘗試次數。

>[!NOTE]
>
>如果初始重試嘗試失敗，重試間隔會每隔一次嘗試以指數方式增加。


當啟用自動完成執行選項時，案例執行會標示為「成功」，因為「中斷」錯誤處理常式的自動重試會自動處理問題。 在此情況下，使用者不會收到有關失敗執行的電子郵件。

當關閉自動完成執行選項時，該執行會標示為「警告」。

在「不完整的執行」下儲存的執行有一些例外，並且由於某些錯誤型別，不可能自動重試案例執行。

## 資源

如需詳細資訊，請參閱「設定案例設定」一文中的[允許儲存不完整的執行](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#allow-storing-incomplete-executions)。

---
title: 檢視和解決未完成的執行
description: '[!UICONTROL 未完成的執行]資料夾會儲存由於錯誤而未成功完成的案例執行。 每個儲存的不完整執行都可以手動或自動解析。'
author: Becky
feature: Workfront Fusion
exl-id: 8891b4d7-a39a-4f14-8521-8c2ca186ca6e
source-git-commit: ad304117fb6e9d1320b8e50d71a162609dc6e6f4
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 5%

---

# 檢視和解決未完成的執行

[!UICONTROL 未完成的執行]資料夾會儲存由於錯誤而未成功完成的案例執行。 每個儲存的不完整執行都可以手動或自動解析。

>[!NOTE]
>
>預設會停用未完成執行的儲存。 若要啟用它，請在案例進階設定中啟用[!UICONTROL 允許儲存未完成的執行]選項。
>
>如需案例設定的詳細資訊，請參閱[設定案例設定](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md)。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 封裝</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權</td> 
   <td> <p>新增：[！UICONTROL Standard]</p><p>或</p><p>目前： [！UICONTROL Work]或更高版本</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>[！UICONTROL Select]或[！UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>已包含[！UICONTROL Ultimate] [!DNL Workfront]計畫： [!DNL Workfront Fusion]。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定*</td> 
   <td> 
     <p>您必須是組織的[!DNL Workfront Fusion]管理員。</p>
     <p>您必須是團隊的[!DNL Workfront Fusion]管理員。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 檢視未完成的執行

如果模組在操作期間遇到錯誤，則會將新的未完成執行新增到未完成執行資料夾。 每個未完成的執行都包含情境的藍圖，以及可對應到失敗模組的所有組合。 按一下案例詳細資訊頁面上的[!UICONTROL 未完成執行]索引標籤，即可開啟未完成執行清單。

<!--

![Incomplete executions tab](assets/incomplete-executions-tab-350x102.png)

-->

如需詳細資訊，請參閱本文中的[導致不完整執行的錯誤](#errors-resulting-into-incomplete-executions)。

>[!NOTE]
>
>每個組織未解決的不完整執行資料夾的目前大小限製為500 MB。 如果貴組織超過此限制，您可能會看到下列錯誤：
>
>`"There is NOT ENOUGH SPACE to add a bundle to the IEQ. The reason is: Too many incomplete executions."`
>
>如需詳細資訊，請參閱「設定案例設定」一文中的[啟用資料遺失](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#enable-data-loss)。


## 從「未完成的執行」索引標籤解決未完成的執行

儲存新的未完成執行時，您可以依照以下方式解決它：

1. 開啟受影響的案例。
1. 按一下&#x200B;**[!UICONTROL 未完成的執行]**&#x200B;標籤。
1. 找出您要解析的未完成執行，然後按一下&#x200B;**[!UICONTROL 詳細資料]**。
1. 開啟模組的記錄，其中顯示所有模組的操作。
1. 找出失敗的作業，然後按一下&#x200B;**[!UICONTROL 解決]**：

   ![解析按鈕](assets/resolve-btn-350x188.png)



## 從「歷史記錄」標籤解決未完成的執行

如果您想在嘗試解析未完成的執行之前檢視所有模組作業的記錄，可以從[!UICONTROL History]資料夾解析未完成的執行：

1. 開啟受影響的案例。
1. 按一下「**[!UICONTROL 歷程記錄]**」標籤。
1. 找到案例的失敗執行，然後按一下&#x200B;**[!UICONTROL 詳細資料]**。
1. 開啟模組的記錄，其中顯示所有模組的操作。
1. 找出失敗的作業，然後按一下&#x200B;**[!UICONTROL 解決]**：

   ![解析按鈕](assets/resolve-btn-350x188.png)

## 與未完成執行相關的選項

[!UICONTROL 情境設定]面板中的下列選項決定是否要儲存不完整的執行，以及如何儲存：

* 允許儲存未完成的執行
* 循序處理
* 啟用資料遺失

如需這些選項的詳細資訊，請參閱[設定案例設定](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md)。

## 導致不完整執行的錯誤

有幾種型別的錯誤會導致儲存不完整的執行。 這些可能包括：

* 驗證錯誤是由不完整或錯誤的資料所引起，主要是因為遺漏了專案，而該專案預期會成功處理通過模組的所有資料。
* 由於暫時或長期的連線失敗（例如在連線至電子郵件或遠端FTP伺服器期間），導致最終目的地無法使用而發生錯誤。

若是情境中第一個模組發生錯誤，會馬上停止執行，不會儲存任何未完成的執行作業。

如果任何其他模組發生錯誤，且沒有附加錯誤處理常式路由，則會發生下列其中一種情況：

* 針對下列錯誤型別，儲存具有自動重試的不完整執行記錄：

   * `ConnectionError`
   * `RateLimitError`
   * `OutOfSpaceError`
   * `ModuleTimeoutError`

* 針對下列錯誤型別，儲存了未完成且未自動重試的執行記錄：

   * `DataError`
   * `InvalidConfigurationError`
   * `InvalidAccessTokenError`
   * `UnexpectedError`
   * `MaxFileSizeExceededError`
   * `MaxResultsExceededError`

* 如果錯誤類型不是上述任何一項，則執行失敗。

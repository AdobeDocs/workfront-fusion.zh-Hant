---
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: scenarios
title: 管理鎖定的案例
description: 管理 [!DNL Adobe Workfront Fusion]中鎖定的案例
author: Becky
feature: Workfront Fusion
exl-id: b5e92bdc-cc1d-4b22-8c5f-42cc279d5590
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 1%

---

# 管理鎖定的案例

在某些情況下，情境可能會暫時鎖定在[!DNL Workfront Fusion]。 鎖定的情況將在2-4小時內自動解鎖。 您可以手動解鎖情境，但通常不建議這麼做。

鎖定案例的原因有很多：

* Workfront Fusion不支援平行處理排程情境。 這些案例會在案例執行開始時鎖定，並在完成時解除鎖定。 如果執行中斷，情境可能不會解除鎖定。 當使用者手動強制停止情景或發生系統問題時，可能會發生這種情況。

* Workfront Fusion工程團隊可能會鎖定情境，因為它會導致效能或其他問題。

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
   <td> <p>新增： [!UICONTROL Standard]</p><p>或</p><p>目前： [!UICONTROL Work]或更高</p> </td> 
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
   <p>新增：</p> <ul><li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li></ul>
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


## 解鎖鎖定的案例

鎖定的情境會從鎖定的時間起2-4小時解鎖。 在排程自動解鎖案例之前，您可以手動解鎖案例。

>[!WARNING]
>
>手動解鎖情境可能會導致情境執行中的錯誤。 我們建議只有在情境因在設計情境時執行和停止執行而鎖定時，才手動解鎖情境。 在其他情況下，我們建議您等待案例自動解除鎖定。


若要手動解除鎖定鎖定的案例：

1. 移至鎖定案例的案例詳細資訊頁面。
1. 按一下畫面右上角的&#x200B;**[!UICONTROL Options]**。
1. 選取&#x200B;**[!UICONTROL Unlock execution]**。
1. 按一下&#x200B;**[!UICONTROL Unlock]**。
   ![](assets/unlock-scenario.png)

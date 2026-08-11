---
title: 設定通知選項
description: 在團隊層級設定電子郵件通知選項。
author: Becky
feature: Workfront Fusion
exl-id: 570a09fc-01a9-4952-8a2b-8bfdd86d0bd8
TQID: https://experienceleague.adobe.com/-HytP4gfrhiiSn-dg5ndg1YC6NTMC-NURYzSFgO5kIo
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 90a58033e240271b88d01b9daef9763f38264056
workflow-type: tm+mt
source-wordcount: 665
ht-degree: 13%

---

# 設定通知選項

在您使用Adobe Unified Shell的組織中，您會透過Adobe通知區域接收通知。

如果您的組織尚未移轉至Adobe Unified Shell，您可以選擇團隊收到的通知。 在團隊層級上設定通知。

您可以控制針對哪些情況傳送通知：

* 警告時通知： Fusion會在案例執行記錄警告時傳送通知。
* 發生錯誤時通知：當案例執行失敗時，Fusion會傳送通知。
* 停用案例時通知：當案例自動停用（例如發生太多連續錯誤後）時，Fusion會傳送通知。

您可以在團隊或案例層級設定通知。 案例層級通知會覆寫在團隊層級設定的通知。 也就是說，如果案例設定直接與團隊設定衝突，則會遵循案例設定。 團隊通知設定會顯示該設定是否有任何覆寫。

依預設，Workfront Fusion中會啟用所有通知型別。

>[!IMPORTANT]
>
>若要接收來自Workfront Fusion的任何通知，您必須在Adobe CX Enterprise通知設定中啟用Fusion通知。 您可以按一下畫面右上角的通知鈴鐺並按一下設定圖示來存取這些設定。

## 存取權要求

+++ 展開以檢視這篇文章中所述功能的存取權要求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront 封裝</td> 
   <td> <p>任何 Adobe Workfront Workflow 封裝及任何 Adobe Workfront Automation and Integration 封裝</p><p>Workfront Ultimate</p><p>Workfront Prime 和 Select 封裝，以及額外購買的 Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront 授權</td> 
   <td> <p>標準</p><p>工作或更高層級</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">角色</td> 
   <td> 
     <p>您必須是要為其調整通知設定的Fusion組織和團隊的成員。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 檢視及管理團隊層級的通知設定

1. 在Workfront Fusion中，按一下左側導覽中的&#x200B;**團隊概觀**。
1. 按一下&#x200B;**通知選項**&#x200B;標籤。

   「通知」選項清單隨即開啟。 如果有任何覆寫，覆寫次數會出現在該設定旁。

1. （條件式）如果有任何覆寫，若要檢視哪些案例覆寫專案團隊通知設定，請按一下該設定的三點功能表。

   您可以按一下此功能表中的情境，直接前往該情境。

   ![覆寫案例功能表](assets/view-notification-override.png)

1. 若要還原通知型別的預設設定，請參閱文章中的[還原通知預設值](#restore-notification-defaults)。

系統會自動儲存通知選項清單的變更。

## 設定案例層級通知設定

個別情境的通知設定是在該情境的「情境設定」面板中設定。

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要新增篩選的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下案例底部的[!UICONTROL 案例設定]圖示![案例設定圖示](assets/scenario-settings-icon.png)。
1. 在「情境設定」面板中，按一下面板底部的&#x200B;**顯示進階設定**。
1. 調整&#x200B;**警告時通知**、**錯誤時通知**&#x200B;以及&#x200B;**當案例停用時通知**&#x200B;設定。
1. 按一下&#x200B;**確定**&#x200B;以儲存並結束案例設定。

## 還原通知預設值

您可以從「通知選項」標籤將群組通知設定還原為預設值。 這會將通知選項設定為已啟用，並移除該通知型別的所有案例通知覆寫。

如果通知型別目前設定為預設值，則不會顯示&#x200B;**還原為預設值**&#x200B;圖示。

1. 在Workfront Fusion中，按一下左側導覽中的&#x200B;**團隊概觀**。
1. 按一下&#x200B;**通知選項**&#x200B;標籤。

   「通知」選項清單隨即開啟。 如果通知型別目前未設定為預設值，則該通知型別會顯示「還原為預設值」圖示。

   ![還原為預設可見](assets/restore-notification-defaults.png)

1. 若要還原該通知型別的預設設定，包括任何案例覆寫，請按一下該通知型別的&#x200B;**重設為預設值**&#x200B;圖示![重設為預設值](assets/restore-default-icon.png)。

系統會自動儲存通知選項清單的變更。

<!--

## Set notification options

If your organization is not on the Adobe Unified Shell, you can set notification settings directly in Fusion.

Email notification options are set on the team level.

1. In the left navigation panel, click **[!UICONTROL Team]**
1. Select the **[!UICONTROL Notification Options]** tab.
1. Enable the notifications that you want the team to receive.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">'[!UICONTROL Warning in scenario run]'</td> 
      <td> <p>Receive an email when there is a warning in a scenario run</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Errors in scenario run]</td> 
      <td>Receive an email when there is an error in a scenario run.</td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[!UICONTROL Scenario deactivation]</p> </td> 
      <td><p>Receive an email when a scenario deactivates.</p><p>In some cases, a scenario might be deactivated by the Workfront Fusion engineering team because the scenario is causing performance or other issues. In these cases, you do not receive notifications in Workfront Fusion. </p></td>

</tr>
</tbody>
</table>

Changes to notification options save automatically.

-->

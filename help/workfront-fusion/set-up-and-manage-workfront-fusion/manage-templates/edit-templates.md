---
content-type: reference
title: 編輯範本
description: 本文說明如何編輯Fusion範本。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 473dba8b-faa4-432f-9357-c2146e86b261
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---

# 編輯範本

Adobe Workfront Fusion範本是預先建立的情境，旨在自動化和簡化各種工作流程。 這些範本可協助您快速設定整合和自動化，而不需要從頭開始建立所有內容。

如果您是管理員，則擁有檢視、修改、重新命名、發佈、核准和刪除其他人建立的範本的許可權。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
  <col>
  <col>
  <tbody>
    <tr>
      <td role="rowheader">Adobe Workfront計畫</td>
      <td><p>任何</p></td>
    </tr>
    <tr data-mc-conditions="">
      <td role="rowheader">Adobe Workfront授權</td>
      <td><p>新增：標準</p><p>或</p><p>目前： [！UICONTROL Work]或更高版本</p></td>
    </tr>
    <tr>
      <td role="rowheader">Adobe Workfront Fusion授權**</td>
      <td>
        <p>目前：無Workfront Fusion授權需求。</p>
        <p>或</p>
        <p>舊版：任何</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">產品</td>
      <td>
        <p>新增:</p>
        <ul>
          <li>[！UICONTROL Select]或[！UICONTROL Prime] Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li>
          <li>[！UICONTROL Ultimate] Workfront計畫：包含Workfront Fusion。</li>
        </ul>
        <p>或</p>
        <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
      </td>
    </tr>
  </tbody>
</table>

<!--
For more detail about the information in this table, see [Access requirements in Workfront documentation](/help/quicksilver/administration-and-setup/add-users/access-levels-and-object-permissions/access-level-requirements-in-documentation.md). 

For information on Adobe Workfront Fusion licenses, see [Adobe Workfront Fusion licenses](../../workfront-fusion/get-started/license-automation-vs-integration.md). -->

+++

## 以管理員身分編輯Workfront Fusion範本

1. 按一下左側導覽面板中的&#x200B;**[!UICONTROL 管理]**&#x200B;以開啟[!UICONTROL 管理]區域。
1. 按一下左側導覽面板中的&#x200B;**[!UICONTROL 所有範本]**。
1. 按一下您要編輯的範本右邊的&#x200B;**[!UICONTROL 詳細資料]**。
1. （選擇性）按一下右上角的&#x200B;**選項**&#x200B;並選取&#x200B;**重新命名**，以重新命名範本。
1. （選擇性）若要變更範本的語言，請按一下[建立新範本] **** [案例設定]圖示![，然後從[語言]下拉式清單中選取語言。](assets/fusion-scenario-settings-icon.png)

   >[!IMPORTANT]
   >
   >「語言」選項對應於系統設定中可用的語言，並且只與公用範本的名稱及其說明有關。 一旦範本已儲存，您就無法變更範本語言。

1. （選擇性）若要編輯範本描述，請按一下&#x200B;**[!UICONTROL 設定範本]** ![案例設定圖示](assets/fusion-scenario-settings-icon.png)，然後輸入描述。
1. 以建立標準情境時的相同方式，新增或編輯應用程式、模組和工具。

   若要新增內容說明至模組，請參閱本文中的[設定[!UICONTROL 精靈]功能](#set-up-wizard-functionality)。

   <!--For more information on building a scenario, see [Create a scenario in Adobe Workfront Fusion](../../../workfront-fusion/scenarios/create-a-scenario.md).-->

   >[!NOTE]
   >
   >如果您的範本包含需要新增連線、憑證或其他隱私權敏感資訊的模組，則此資訊不會與範本使用者共用。

1. （選擇性）按一下&#x200B;**[!UICONTROL 執行一次]**&#x200B;以測試範本。
1. 按一下&#x200B;**[!UICONTROL 儲存]**&#x200B;圖示![儲存圖示](assets/save-icon.png)。


## 設定[!UICONTROL 精靈]功能

[!DNL Workfront Fusion template] [!UICONTROL 精靈]可讓您為範本的未來使用者提供模組中所使用特定欄位的相關指示或資訊。

1. 按一下新增至範本的模組，以檢視模組的欄位。
1. 找到您要新增[!UICONTROL 精靈]資訊的欄位，並在該欄位下方啟用&#x200B;**[!UICONTROL 在精靈]**&#x200B;中使用。
1. 在[!UICONTROL 說明]欄位中輸入您想要讓使用者看到的資訊。
1. （選擇性）若要讓使用者在使用範本時看到此文字，請啟用&#x200B;**[!UICONTROL 使用作為預設值]**。
1. 針對您想要提供資訊的每個欄位，重複步驟2至4。
1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;以儲存變更並關閉模組。

發佈程式與標準使用者的情況相同。 如需詳細資訊，請參閱[發佈與共用範本](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md)區段。

## 範本狀態

您可以在範本名稱下方檢查範本頁面上的狀態。

可使用下列狀態：

* **[!UICONTROL 私人]**：此範本僅對範本作者及其團隊可見。
* **[!UICONTROL 已發佈]**：此範本僅對範本作者及其團隊可見。 發佈後，您可以視需要傳送範本以供核准。 您也可以複製分享連結。
* **[!UICONTROL 已核准]**： [!UICONTROL 公用範本]索引標籤中的所有Workfront Fusion使用者都可以看見此範本。 您也可以按一下熒幕右上角的[!UICONTROL 選項]，以複製分享連結。

您也可以從[!UICONTROL 團隊範本]標籤檢查狀態。 如果範本已發佈，其範本名稱右側會出現圖示。

* **眼睛圖示**：範本已發佈；團隊可以看見它。
* **黃色核取記號圖示**：範本已發佈；它僅對團隊可見；它正在等候核准以新增至公用範本索引標籤。
* **綠色核取記號圖示**：此範本可在「公用範本」標籤中使用，且任何Workfront Fusion使用者都可以看到。 [!UICONTROL 團隊範本]索引標籤中仍會顯示它。 範本作者或其團隊成員仍可編輯它。

沒有圖示的範本具有[!UICONTROL 私人]狀態。 它們不會發佈，僅對團隊可見。

## 找出範本的SVG資訊

1. 按一下左側導覽面板中的&#x200B;**[!UICONTROL 管理]**&#x200B;以開啟[!UICONTROL 管理]區域。
1. 按一下左側導覽面板中的&#x200B;**[!UICONTROL 範本]**。
1. 按一下要尋找資訊的範本。
1. 按一下右上角的&#x200B;**選項**。
1. 選取&#x200B;*SVG圖表*。

您可以在此處檢視SVG圖表和SVG程式碼。

---
title: 建立新範本
description: 您可以在 [!DNL Adobe] Workfront Fusion中建立新的情境範本。
author: Becky
feature: Workfront Fusion
exl-id: 9cb9bd04-e9ae-4162-a1b9-d71566582b7a
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 0%

---

# 建立新範本

您可以在[!DNL Adobe] Workfront Fusion中建立新的情境範本。

>[!TIP]
>
>建立新範本之前，您可以檢查[!UICONTROL 公用範本]標籤，確認您要建立的範本尚未可用。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>新增：標準</p><p>或</p><p>目前： [!UICONTROL Work]或更高版本</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增:</p> <ul><li>[!UICONTROL Select]或[!UICONTROL Prime] Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li><li>[!UICONTROL Ultimate] Workfront計畫：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 建立新範本

您可以使用與建立情境類似的程式來建立範本。 Fusion管理員也可以從現有的案例建立範本。

* [建立範本](#build-a-template)
* [從情境建立範本](#create-a-template-from-a-scenario)

### 建立範本

1. 按一下左側導覽面板中的&#x200B;**[!UICONTROL 範本]** ![範本圖示](assets/templates-icon.png)。
1. 按一下右上角的&#x200B;**[!UICONTROL 建立新範本]**。
1. （選擇性）取代左上角的預設&#x200B;**[!UICONTROL 新範本名稱]**&#x200B;以重新命名範本。
1. （選擇性）若要變更範本的語言，請按一下&#x200B;**[!UICONTROL 設定範本]** ![案例設定圖示](assets/scenario-settings-icon.png)，然後從[語言]下拉式清單中選取語言。

   >[!IMPORTANT]
   >
   >「語言」選項對應於系統設定中可用的語言，並且只與公用範本的名稱及其說明有關。 一旦範本已儲存，您就無法變更範本語言。

1. （選擇性）若要輸入範本的說明，請按一下&#x200B;**[!UICONTROL 設定範本]** ![案例設定圖示](assets/scenario-settings-icon.png)並輸入說明。
1. 使用與將模組新增至情境相同的程式，新增應用程式、模組及工具。

   如需指示，請參閱[新增模組](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md)下的文章。

   若要新增內容說明至模組，請參閱本文中的[設定精靈功能](#set-up-wizard-functionality)。

   如需建立案例的詳細資訊，請參閱[建立案例的工作流程](/help/workfront-fusion/create-scenarios/plan-a-scenario/create-a-scenario-workflow.md)。

   >[!NOTE]
   >
   >如果您的範本包含需要新增連線、憑證或其他隱私權敏感資訊的模組，則此資訊不會與範本使用者共用。

1. （選擇性）按一下&#x200B;**[!UICONTROL 執行一次]**&#x200B;以測試您的範本。
1. 按一下&#x200B;**[!UICONTROL 儲存]**&#x200B;圖示![儲存圖示](assets/save-icon.png)以儲存範本。

當您儲存範本時，您的團隊成員可以看到它。 如果您希望範本可在團隊外部存取，您必須提交要求以核准並發佈。 要求會傳送給Adobe Workfront Fusion團隊進行核准。 在核准後，您團隊以外的其他人可以存取範本。

如需有關發佈範本的資訊，請參閱[發佈和共用Adobe Workfront Fusion範本](/help/workfront-fusion/create-and-manage-templates/publish-and-share-fusion-templates.md)。

### 從情境建立範本

>[!NOTE]
>
>您必須是Fusion管理員才能從案例建立範本。

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要建立範本的情境。
1. 按一下頁面右上角附近的&#x200B;**管理員**&#x200B;下拉式清單。
1. 選取&#x200B;**復製為範本**。

   情境會複製到新範本頁面中。
1. （選擇性）取代左上角的預設&#x200B;**[!UICONTROL 新範本名稱]**&#x200B;以重新命名範本。
1. （選擇性）若要變更範本的語言，請按一下&#x200B;**[!UICONTROL 設定範本]** ![案例設定圖示](assets/scenario-settings-icon.png)，然後從[語言]下拉式清單中選取語言。

   >[!IMPORTANT]
   >
   >「語言」選項對應於系統設定中可用的語言，並且只與公用範本的名稱及其說明有關。 一旦範本已儲存，您就無法變更範本語言。

1. （選擇性）若要輸入範本的說明，請按一下&#x200B;**[!UICONTROL 設定範本]** ![案例設定圖示](assets/scenario-settings-icon.png)並輸入說明。
1. 視需要編輯應用程式、模組和工具，使用與將模組新增至情境相同的程式。

   如需指示，請參閱[新增模組](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md)下的文章。

   若要新增內容說明至模組，請參閱本文中的[設定[!UICONTROL 精靈]功能](#set-up-wizard-functionality)。

   >[!NOTE]
   >
   >如果您的範本包含需要新增連線、憑證或其他隱私權敏感資訊的模組，則此資訊不會與範本使用者共用。

1. （選擇性）按一下&#x200B;**[!UICONTROL 執行一次]**&#x200B;以測試您的範本。
1. 按一下&#x200B;**[!UICONTROL 儲存]**&#x200B;圖示![儲存圖示](assets/save-icon.png)。

## 設定[!UICONTROL 精靈]功能 {#set-up-wizard-functionality}

[!DNL Workfront Fusion template] [!UICONTROL 精靈]可讓您為範本的未來使用者提供模組中所使用特定欄位的相關指示或資訊。

1. 建立範本時，按一下範本中新增的模組以檢視模組的欄位。
1. 找到您要新增[!UICONTROL 精靈]資訊的欄位，並為該欄位啟用&#x200B;**[!UICONTROL 在精靈中使用]**。
1. 在[!UICONTROL 說明]欄位中輸入您想要讓使用者看到的資訊。
1. （選擇性）若要讓使用者在使用範本時看到此文字，請啟用&#x200B;**[!UICONTROL 使用作為預設值]**。
1. 針對您想要提供資訊的每個欄位，重複步驟2至4。
1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;以儲存變更並關閉模組。

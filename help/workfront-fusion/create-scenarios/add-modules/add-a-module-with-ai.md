---
title: 使用AI產生案例區段
description: 您可以使用AI輸入文字提示，說明您需要案例的區段做什麼。 然後Fusion會產生一個或多個模組來執行這些動作，您可以在情境中使用這些模組。
author: Becky
feature: Workfront Fusion
exl-id: d231e33a-6033-4e3c-b1d4-7034797c45a5
source-git-commit: 9d29abc82a3bb09affc4d17d7ea214d7bb850294
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 1%

---

# 使用AI產生案例區段

<!--DO NOT DELETE - linked through CSH-->

<!--Check if this is in GA before repo goes live. If not, hide this article.-->

<!--Check if they need to have signed the rider and stuff-->

您可以使用AI輸入文字提示，說明您需要案例的區段做什麼。 然後Fusion會產生一個或多個模組來執行這些動作，您可以在情境中使用這些模組。

產生的案例區段包含單一聯結器的模組。 若要產生不同聯結器的模組，請建立個別提示，然後加入案例中的案例區段。

和從AI產生的任何專案一樣，我們建議您仔細檢查並測試產生的模組，以確保模組如預期般執行。

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
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

您的組織必須符合下列必要條件，才能使用此功能：

* 貴組織必須已參與Workfront AI Assistant Beta計畫。
* Adobe必須為貴組織的檔案擁有已簽署的AdobeGen AI合約。

  如需簽署合約的詳細資訊，請參閱Workfront檔案中AI助理概觀一文中的[簽署AdobeGen AI合約](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/basics/ai-assistant/ai-assistant-overview#sign-the-adobe-gen-ai-agreement)。

## 目前支援的AI模組應用程式

Fusion AI目前可以產生連線到以下應用程式的模組：

* Adobe Firefly
* Azure OpenAI
* Microsoft Graph
* Adobe Workfront規劃
* Adobe Analytics
* Adobe PDF服務
* AdobeMarketo
* AdobeFrame.io
* Dropbox
* NetSuite
* Google 日曆
* 阿特拉斯大Jira
* GitLab
* Spotify
* 位元貯體
* OpenAI
* Slack

## 產生模組

1. 按一下左側面板中的&#x200B;**[!UICONTROL Scenarios]**&#x200B;索引標籤。
1. 選取您要新增模組的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下熒幕右上角附近的&#x200B;**AI小幫手**&#x200B;圖示![AI小幫手圖示](assets/ai-assistant-icon.png)。
1. 在AI助理面板中輸入文字提示。

   如需提示的相關提示，請參閱本文中[為案例區段建立提示的相關提示](#tips-for-creating-prompts-for-scenario-segments)。

   AI助理會產生模組或模組集。
1. （視條件而定）如有需要，請將應用程式的API Token新增至模組。
1. 檢查模組，確定模組已針對適當的應用程式和動作進行設定。
1. （視條件而定）如果產生的案例區段未附加至您的案例，請將其拖曳至適當位置。

我們建議測試這些模組，以確保它們按預期執行。

## 為案例區段建立提示的提示

文字提示應至少包含下列資訊：

* 您連線到的應用程式
* 您要執行的一個或多個動作

>[!IMPORTANT]
>
>您可以一次產生多個模組，但一次只能為一個應用程式產生模組。

>[!BEGINSHADEBOX]

**範例**：

* `Delete the records 'xyz-123', 'xyz-456', 'xyz-789' from Adobe Workfront Planning`
這包括應用程式`Workfront Planning`和動作`delete records`。 此提示會建立三個模組，每個要刪除的記錄各一個。
* `Change campaign summary of the record 'xyz-123' from Adobe Workfront Planning`
這包括應用程式`Workfront Planning`和動作`change campaign summary`。
* `Get all field details in the record type with ID 'test-record' from Adobe Workfront Planning`
這包括應用程式`Workfront Planning`和動作`get field details`。

下列範例不正確：

* `Generate an image in Adobe Firefly and upload it to Dropbox`

  此範例不正確，因為它包含多個應用程式

>[!ENDSHADEBOX]

建立文字提示時，請考量下列事項：

* 使用直接、簡單的語言。
* 檢查並測試您的案例區段。 如果無法如預期執行，請調整您的提示，然後再試一次。

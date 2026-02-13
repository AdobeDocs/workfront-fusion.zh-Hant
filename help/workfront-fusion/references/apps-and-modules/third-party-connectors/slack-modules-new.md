---
title: Slack 模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Slack的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 4c14fa36-8333-40d6-bd0a-fc6b0d9f4410
source-git-commit: 88147d0305595e1d0d388f510ed43fc5beaa4b64
workflow-type: tm+mt
source-wordcount: '4581'
ht-degree: 12%

---

# [!DNL Slack] 模組

>[!IMPORTANT]
>
>本文介紹2025年11月17日發行的新型Slack聯結器中的可用模組。
>
>如需有關舊版Slack聯結器的資訊，請參閱[[!DNL Slack] 模組（舊版）](/help/workfront-fusion/references/apps-and-modules/third-party-connectors/slack-modules.md)。

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Slack]的工作流程，並將其連線至多個協力廠商應用程式和服務。

關於建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)之下的文章。

關於模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)之下的文章。

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
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>連接器型 (舊版)：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

* 若要使用 [!DNL Slack] 模組，您必須擁有 [!DNL Slack] 帳戶。
* 如果您正在建立OAuth@連線，您必須將下列URL新增至貴組織的允許清單：
   * 機器人Token： `https://oauth.app.workfrontfusion.com/oauth/cb/slack3`
   * 使用者權杖：` https://oauth.app.workfrontfusion.com/oauth/cb/slack2`

## Slack API資訊

Slack聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td>{{ifempty(parameters.domain， 'https://slack.com/api/')}}</td> 
  </tr>
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v4.0.15</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Slack] 模組及其欄位

當您設定[!DNL Slack]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Slack] 欄位。在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [訊息](#messages)
* [檔案](#files)
* [管道](#channels)
* [回應](#reactions)
* [星級](#stars)
* [已儲存的專案](#saved-items)
* [圖釘](#pins)
* [使用者](#users)
* [提醒](#reminders)
* [活動](#events)
* [輪廓](#profile)
* [其他](#other)

### 訊息

+++ **[!UICONTROL 建立訊息]**

此動作模組會建立新訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL輸入管道ID或名稱]</p> </td> 
   <td> <p>選擇您要如何選取要建立訊息的頻道。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL頻道ID或名稱]</strong>欄位中，輸入或對應您要張貼訊息的頻道ID或名稱。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取管道型別，然後選取管道。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 文字]</p> </td> 
   <td> <p>輸入要建立的訊息文字內容。</p> <p>注意：如需有關文字格式的詳細資訊，請參閱<a href="https://api.slack.com/reference/surfaces/formatting">檔案中的</a>格式化應用程式表面的文字[!DNL Slack]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL區塊]</td> 
   <td>區塊是可重複使用的元件，可用於自訂及組織您的訊息。 如需有關區塊的詳細資訊，請參閱<a href="https://api.slack.com/block-kit">檔案中的</a>區塊套件[!DNL Slack]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL執行緒訊息ID （時間戳記）]</td> 
   <td>如果新訊息為回覆，請輸入您要回覆的訊息時間戳記。 請勿輸入已經是回覆之訊息的時間戳記。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL回覆廣播]</td> 
   <td> <p>如果同時符合下列兩個條件，請選取<strong>[！UICONTROL是]</strong>：</p> 
    <ul> 
     <li> <p>新訊息是其他訊息的回覆</p> </li> 
     <li> <p>您希望頻道中的所有人都能看到新訊息</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL連結名稱]</p> </td> 
   <td> <p>啟用此選項以允許名稱和管道使用<code>@username</code>或<code>#channel</code>格式。 </p> <p>如需詳細資訊，請參閱<a href="https://api.slack.com/docs/formatting">檔案中的</a>格式化應用程式介面的文字[!DNL Slack]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL剖析訊息文字]</p> </td> 
   <td> <p>啟用此選項以允許自動剖析。 </p> <p>如需詳細資訊，請參閱<a href="https://api.slack.com/docs/formatting">檔案中的</a>格式化應用程式介面的文字[!DNL Slack]。</p> <p>注意：如果您在原始訊息中使用[！UICONTROL連結名稱]或[！UICONTROL剖析訊息文字]選項，您也應在執行[！UICONTROL更新訊息]模組時指定這些選項。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL使用Markdown]</p> </td> 
   <td> <p>啟用此選項以允許[!DNL Slack]在文字中使用Markdown。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL展開主要是文字型內容]</p> </td> 
   <td> <p>啟用此選項以允許展開主要是文字型內容。 </p> <p>如需在[!DNL Slack]中展開的相關詳細資訊，請參閱<a href="https://api.slack.com/reference/messaging/link-unfurling">檔案中的</a>在訊息中展開連結[!DNL Slack]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL展開媒體內容]</p> </td> 
   <td> <p>啟用此選項可允許展開媒體內容。 </p> <p>如需在[!DNL Slack]中展開的相關詳細資訊，請參閱<a href="https://api.slack.com/reference/messaging/link-unfurling">檔案中的</a>在訊息中展開連結[!DNL Slack]。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 刪除訊息]**

此動作模組會刪除指定的訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應管道ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID （時間戳記）]</td> 
   <td> <p> 輸入或對應您要刪除之訊息的時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如Watch私人頻道模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取得私人頻道訊息]**

此動作模組會從選取的頻道擷取訊息的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Channel]</p> </td> 
   <td> <p>選取包含訊息的頻道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL訊息ID （時間戳記）]</p> </td> 
   <td> <p> 輸入或對應您要擷取相關資訊之訊息的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Public Channel]模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取得公用頻道訊息]**

此動作模組會從指定的公用通道傳回具有特定ID的訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>選取包含訊息的頻道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID （時間戳記）]</td> 
   <td> <p> 輸入或對應您要擷取相關資訊之訊息的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Public Channel]模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 列出回覆]**

此動作模組會擷取張貼至交談的訊息執行緒。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取包含您要擷取回覆之訊息的頻道型別，然後選取頻道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL父訊息ID （時間戳記）]</td> 
   <td> <p> 輸入或對應您要擷取回覆之訊息的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Public Channel]模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大回複數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 搜尋訊息]**

此搜尋模組會傳回符合搜尋查詢的訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Query]</td> 
   <td> <p>輸入搜尋依據的查詢。 </p> <p>如需有關從對應面板建立公式的資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中使用內建函式來對應專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL排序依據] </td> 
   <td> <p>選取您要依分數或時間戳記來排序傳回的訊息。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>選取您要依遞增或遞減來排序訊息。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 更新訊息]**

此動作模組可讓您編輯現有訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL輸入管道ID或名稱]</p> </td> 
   <td> <p>選擇您希望如何選取所要的訊息。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL頻道ID或名稱]</strong>欄位中，輸入或對應包含訊息的頻道ID或頻道，然後輸入訊息的<strong>[！UICONTROL時間戳記（訊息ID）]</strong>。.</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取管道型別，然後選取管道，再選取訊息。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 文字]</p> </td> 
   <td> <p>輸入要更新的訊息的新文字內容。</p> <p>如需詳細資訊，請參閱<a href="https://api.slack.com/docs/formatting">檔案中的</a>格式化應用程式介面的文字[!DNL Slack]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL區塊]</td> 
   <td>區塊是可重複使用的元件，可用於自訂及組織您的訊息。 如需有關區塊的詳細資訊，請參閱<a href="https://api.slack.com/block-kit">檔案中的</a>區塊套件[!DNL Slack]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL連結名稱]</p> </td> 
   <td> <p>啟用此選項以允許名稱和管道使用<code>@username</code>或<code>#channel</code>格式。 </p> <p>如需詳細資訊，請參閱<a href="https://api.slack.com/docs/formatting">檔案中的</a>格式化應用程式介面的文字[!DNL Slack]。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL剖析訊息文字]</p> </td> 
   <td> <p>啟用此選項以允許自動剖析。 </p> <p> 如需詳細資訊，請參閱<a href="https://api.slack.com/docs/formatting">檔案中的</a>格式化應用程式介面的文字[!DNL Slack]。</p> <p>注意：如果您在原始訊息中使用[！UICONTROL連結名稱]或[！UICONTROL剖析訊息文字]選項，您也應在執行更新訊息模組時指定這些選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 觀看直接訊息]**

此觸發模組會在新訊息新增至直接訊息時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Channel] </td> 
   <td> <p>選取您要觀看新訊息的直接訊息交談。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大訊息數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 觀看多方直接訊息]**

此觸發模組會在新訊息新增至多方直接訊息通道時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Channel] </td> 
   <td> <p>選取您要觀看新訊息的直接訊息交談。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大訊息數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL 觀看私人頻道訊息]**

此觸發模組會在新訊息新增至私人頻道（群組）時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Channel] </td> 
   <td> <p>選取您要觀看新訊息的私人頻道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大訊息數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++**[!UICONTROL 觀看公開頻道訊息]**

此觸發模組會在新訊息新增至公用頻道時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Channel] </td> 
   <td> <p>選取您要觀看新訊息的公共頻道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大訊息數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 檔案

+++ **[!UICONTROL 刪除檔案]**

此動作模組會傳回刪除指定的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案 ID]</td> 
   <td> <p>輸入或對應您要刪除之檔案的ID。 </p> <p>注意：可以使用其他模組（例如[!DNL Watch Files]模組）擷取檔案識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取得檔案]**

此動作模組會傳回指定檔案的相關詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案 ID]</td> 
   <td> <p>輸入或對應您要擷取的檔案ID。 </p> <p>注意：可以使用其他模組（例如[!DNL Watch Files]模組）擷取檔案識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 列出檔案]**

此動作模組會根據指定的篩選器傳回檔案清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 類型] </td> 
   <td> <p>選取您要擷取的檔案型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL頻道型別]</p> </td> 
   <td> <p>選取代表您要列出檔案之通道的通道型別，然後選取通道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL建立者]</td> 
   <td> <p>選取使用者，只傳回由指定使用者建立的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL起始日期]</td> 
   <td>輸入您要傳回檔案的最早日期。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL結束日期]</td> 
   <td>輸入您想要傳回檔案的最晚日期。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大檔案數。</td> 
  </tr> 
 </tbody> 
</table>

+++

<!--

+++ **[!UICONTROL Download a File]**

This action module downloads a file from a URL. It must follow the [!UICONTROL Slack] >[!UICONTROL Get a File] module in a scenario.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL private download]</td> 
   <td> <p>Map the <b>[!UICONTROL URL Private download]</b> value from the [!DNL Slack] >[!UICONTROL Get a File] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

+++ **[!UICONTROL 上傳檔案]**

此動作模組會建立檔案或將檔案上傳到[!DNL Slack]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道]</td> 
   <td> <p>針對您想要上傳檔案的每個管道，按一下<b>[！UICONTROL新增專案]</b>，然後選取管道型別和管道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 來源檔案]</td> 
   <td>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL標題]</td> 
   <td>輸入您要上傳之檔案的標題</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL執行緒ID （時間戳記）]</td> 
   <td> <p>如果您上傳檔案作為回覆，請輸入或對應您要回覆的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel]模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL初始註解]</td> 
   <td> <p>輸入或對應引入檔案的訊息文字。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 觀看檔案]**

此觸發模組會在新增檔案時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 類型]</td> 
   <td>選取您要模組觀看的檔案型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td> <p>選取您要觀看檔案的頻道型別，然後選取頻道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL建立者]</td> 
   <td> <p>選取使用者，只傳回由指定使用者建立的檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大檔案數。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 管道

+++ **[!UICONTROL 封存頻道]**

此動作模組會封存頻道。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應您要封存之管道的ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 建立頻道]**

此動作模組會建立新管道。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 名稱]</p> </td> 
   <td> <p>輸入或對映新管道的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL為私人]</td> 
   <td>啟用此選項可將新頻道設定為私人。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取得頻道]**

此動作模組會傳回工作區管道的相關資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應您要擷取相關資訊之管道的ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 加入頻道]**

此動作模組會將使用者加入管道。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應您要加入之管道的ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 離開頻道]**

此動作模組會從頻道中移除使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應您要離開之管道的ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 列出頻道]**

此搜尋模組會傳回工作區中所有頻道的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL排除已封存的]</p> </td> 
   <td> <p>選取「[！UICONTROL是]」以在結果中排除已封存的管道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 類型] </td> 
   <td> <p>選取您要擷取的管道型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>設定每個案例執行週期中您希望模組傳回的最大通道數。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 列出頻道]**&#x200B;中的成員

此搜尋模組會傳回所選頻道中的使用者清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取包含要列出之成員的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private Channel]</td> 
   <td>選取您要列出成員的管道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>設定您希望模組在每個案例執行週期中傳回的成員數目上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 設定頻道用途]**

此動作模組會變更頻道的用途

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要變更用途的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] /User / [！UICONTROL多個IM頻道]</td> 
   <td>選取您要變更用途的頻道或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL用途]</td> 
   <td>輸入或對映頻道的新用途。 此欄位不支援格式設定或連結。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 設定頻道主題]**

此動作模組會變更頻道的主題

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要變更主題的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] / [！UICONTROL User] / [！UICONTROL Multiple IM Channel]</td> 
   <td>選取您要變更主題的頻道或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL主題]</td> 
   <td>輸入或對映頻道的新主題。 此欄位不支援格式設定或連結。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取消封存頻道]**

此動作模組會取消封存頻道。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應您要取消封存之管道的ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 回應

+++ **[!UICONTROL 新增回應]**

此動作模組會新增對專案的回應。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要新增回應的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] / [！UICONTROL User] / [！UICONTROL多個IM通道]</td> 
   <td>選取您要新增回應的頻道或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID （時間戳記）]</td> 
   <td> <p> 輸入或對應您要新增回應的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel]模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL反應（表情符號）名稱]</td> 
   <td>輸入或對應您要用於回應的表情符號名稱。 範例：<code>thumbsup</code>。 </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 列出回應]**

此動作模組會傳回使用者作出的反應。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL使用者]</p> </td> 
   <td> <p>選取做出您要列出的回應的使用者。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大回應數。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 移除回應]**

此動作模組會移除專案的反應。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要從中移除回應的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] / [！UICONTROL User] / [！UICONTROL多個IM通道]</td> 
   <td>選取您要從中移除回應的頻道或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID]</td> 
   <td> <p> 輸入或對應您要移除反應的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel]模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL反應（表情符號）名稱]</td> 
   <td>輸入或對應您要從訊息中移除的Emoji名稱。 範例：<code>thumbsup</code>。 </td> 
  </tr> 
 </tbody> 
</table>

+++

### 星級

+++ **[!UICONTROL 新增星星]**

此動作模組會使得頻道成為星級頻道。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要新增星號的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] / [！UICONTROL User] / [！UICONTROL多個IM通道]</td> 
   <td>選取您要新增星號的頻道或使用者。</td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 移除星號]**

此動作模組會從星形色版中移除星形。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要新增星號的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] / [！UICONTROL User] / [！UICONTROL多個IM通道]</td> 
   <td>選取您要新增星號的頻道或使用者。</td> 
  </tr> 
 </tbody> 
</table>

+++

### 已儲存的專案

+++ **[!UICONTROL 移除已儲存的專案]**

此動作模組會從儲存的專案中移除專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID （時間戳記）]</td> 
   <td> <p> 輸入或對應您要從儲存的專案移除之訊息的時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel]模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案 ID]</td> 
   <td> <p>輸入或對應您要從儲存的專案移除的檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 儲存專案]**

此動作模組會將專案新增至已儲存的專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID （時間戳記）]</td> 
   <td> <p> 輸入或對應您要儲存之訊息的時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel]模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案 ID]</td> 
   <td> <p>輸入或對應您要儲存的檔案。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 圖釘

+++ **[!UICONTROL 釘選專案]**

此動作模組將專案釘選至管道。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要釘選專案的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] / [！UICONTROL Multiple IM channel] / [！UICONTROL User]</td> 
   <td>選取您要將專案釘選到的管道或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID]</td> 
   <td> <p> 輸入或對應您要釘選的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel]模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取消釘選專案]**

此動作模組會從頻道取消釘選專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要取消釘選專案的來源管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private] / [！UICONTROL Multiple IM channel] / [！UICONTROL User]</td> 
   <td>選取您要取消釘選專案的來源頻道或使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID]</td> 
   <td> <p> 輸入或對應您要取消釘選的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel]模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 使用者

+++ **[!UICONTROL 取得使用者]**

此動作模組會擷取有關工作區成員的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL使用者ID]</p> </td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之使用者的使用者ID。</p> <p>注意：可以使用其他模組（例如[!DNL List Users]模組）擷取使用者ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 邀請使用者]**

此動作模組邀請1-30名使用者使用公開或私人頻道。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要邀請使用者的管道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private channel]</td> 
   <td>選取您要邀請使用者加入的管道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 使用者]</td> 
   <td> <p>選取您要新增至管道的使用者。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 啟動使用者]**

此動作模組會從頻道移除使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頻道型別]</td> 
   <td>選取您要移除使用者的頻道型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Public] / [！UICONTROL Private channel]</td> 
   <td>選取您要移除使用者的頻道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 使用者]</td> 
   <td> <p>選取您要從頻道移除的使用者。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 列出使用者]**

此動作模組會傳回工作區中所有使用者的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 限制]</p> </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的使用者數目上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 搜尋使用者]**

此動作模組會使用單一使用者的電子郵件地址來擷取有關該使用者的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL電子郵件] </p> </td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之使用者的電子郵件地址。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 觀看使用者]**

此觸發模組會在新使用者新增至[!DNL Slack]工作區時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>設定每個案例執行週期中您希望模組傳回的最大使用者數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 提醒

<!--

+++ **[!UICONTROL List Reminders]**

This action module returns a list of all reminders created by or given to the currently authenticated user.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Limit]</p> </td> 
   <td> <p>Enter or map the maximum number of reminders you want the module to return during each scenario execution cycle.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a Reminder]**

This action module retrieves details about a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to retrieve details for.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

+++ **[!UICONTROL 建立提醒]**

此動作模組會建立提醒。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 文字]</td> 
   <td>輸入或對應提醒的內容</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL時間]</td> 
   <td> <p>輸入或對應此提醒應該發生的日期和時間。 輸入下列其中一項： </p> 
    <ul> 
     <li> <p>Unix時間戳記（從現在起最多五年）</p> </li> 
     <li> <p>提醒前的秒數（若在24小時內） </p> </li> 
     <li> <p>自然語言說明（範例：「15分鐘內」或「每星期四」）</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL使用者] </p> </td> 
   <td> <p>選取接收提醒的使用者。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

<!--

+++ **[!UICONTROL Complete a Reminder]**

This action module completes a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to complete.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Delete a Reminder]**

This action module deletes a specific reminder.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>For instructions about connecting your [!DNL Slack] account to [!DNL Workfront Fusion], see <a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">Create a connection to [!DNL Adobe Workfront Fusion] - Basic instructions</a>.</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Reminder ID]</p> </td> 
   <td> <p>Enter or map the Reminder ID of the reminder you want to delete.</p> <p>Note: The Reminder ID can be retrieved using another module, such as the [!UICONTROL List Reminders] module.</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

-->

### 活動

+++ **[!UICONTROL 新事件]**

這個立即觸發程式會在建立新訊息或其他事件時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Webhook]</p> </td> 
   <td> <p>選取您要使用的webhook。</p> <p>或</p> <p>建立新的webhook。</p> 
    <ol> 
     <li value="1"> <p>按一下「<b>[!UICONTROL 新增]</b>」。</p> </li> 
     <li value="2"> <p>選取事件型別。</p> </li> 
     <li value="3"> <p>選取或新增連線。 如需有關將[!DNL Slack]帳戶連線至[！UICONTROL Workfront Fusion]的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[！UICONTROL Adobe Workfront Fusion]的連線 — 基本說明</a></p> </li> 
     <li value="4"> <p>如果出現提示，請選取您要觀看的頻道。</p> </li> 
     <li value="5"> <p>按一下<b>[！UICONTROL儲存]</b>以儲存webhook並返回模組。</p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 輪廓

+++ **[!UICONTROL 設定狀態]**

此動作模組會更新使用者的目前狀態。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL狀態文字]</p> </td> 
   <td> <p>輸入或對應狀態文字。 考慮以下事項：</p> 
    <ul> 
     <li> <p>您最多可輸入100個字元。</p> </li> 
     <li> <p>您可以使用標示或其他格式，例如使用者提及。</p> </li> 
     <li> <p>您可以使用格式<code>:emojiname:</code>在狀態文字中加入emoji。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL狀態emoji]</td> 
   <td> <p>輸入或對應您要用來代表您狀態的Emoji。 使用格式<code>:emojiname:</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL狀態過期]</td> 
   <td>輸入或對應您想要狀態到期的日期和時間。 如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref" data-mc-variable-override="">類型強制轉換</a>。</td> 
  </tr> 
 </tbody> 
</table>

+++

### 其他

+++ **[!UICONTROL 進行API呼叫]**

您可以利用此動作模組，對 [!DNL Slack] API 進行已驗證的自訂呼叫。如此一來，您就可以建立其他 [!DNL Slack] 模組無法完成的資料流程自動化。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於 <code>https://slack.com/api/</code> 的路徑。範例：<code>/users/identity</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   td&gt; <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!UICONTROL Workfront Fusion] 會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL基底URL]</td> 
   <td>選取您要用於API呼叫的基本URL。</td> 
  </tr> 
 </tbody> 
</table>

+++

## 術語

下列術語在設定[!DNL Slack]模組時可能很有用：

* **DM**： [!UICONTROL 直接訊息]
* **IM**： [!UICONTROL 立即訊息]
* **私人頻道**：先前為[!UICONTROL 群組]
* **直接訊息**：先前為[!UICONTROL IM]
* **頻道**： API檔案中的[!UICONTROL 交談]，[!UICONTROL 應用程式中的]頻道[!DNL Slack]。

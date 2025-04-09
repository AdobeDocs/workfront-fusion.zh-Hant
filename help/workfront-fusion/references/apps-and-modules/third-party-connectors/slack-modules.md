---
title: Slack模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Slack的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: c9c68a4c-f592-42d1-b15f-a525b9aa3944
source-git-commit: eb0518ba0d1a0c758cb547e362c722f4be3674c7
workflow-type: tm+mt
source-wordcount: '1954'
ht-degree: 0%

---

# [!DNL Slack]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Slack]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

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
   <td> <p>新增：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前：無Workfront Fusion授權需求</p>
   <p>或</p>
   <p>舊版：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL Slack]模組，您必須有[!DNL Slack]帳戶。

## Slack API資訊

Slack聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td>{{ifempty(parameters.domain， 'https://slack.com/api/')}}</td> 
  </tr>
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v4.0.15</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Slack]模組及其欄位

當您設定[!DNL Slack]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Slack]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [訊息](#messages)
* [交談](#channels)
* [其他](#other)

### 訊息

* [建立訊息](#create-a-message)
* [刪除訊息](#delete-a-message)
* [取得私人頻道訊息](#get-a-private-channel-message)
* [取得公開頻道訊息](#get-a-public-channel-message)
* [更新訊息](#update-a-message)
* [觀看私人頻道訊息](#watch-private-channel-messages)
* [觀看公開頻道訊息](#watch-public-channel-messages)

### [!UICONTROL 建立訊息]

此動作模組會建立新訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
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
   <td role="rowheader"> <p>[！UICONTROL Text]</p> </td> 
   <td> <p>輸入要建立的訊息文字內容。</p> <p>注意：如需有關文字格式的詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/reference/surfaces/formatting">格式化應用程式表面的文字</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL作為使用者]</td> 
   <td>啟用此選項可將訊息張貼為擁有此模組連線所使用的認證的使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL執行緒訊息ID （時間戳記）]</td> 
   <td>如果新訊息為回覆，請輸入您要回覆之訊息的時間戳記。 請勿輸入已經是回覆之訊息的時間戳記。</td> 
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
   <td role="rowheader">[！UICONTROL附件]</td> 
   <td>針對您想要附加至郵件的每個專案，按一下<b>新增專案</b>並填入專案的詳細資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL圖示表情符號]</td> 
   <td>輸入或對應Emoji做為此訊息的圖示，格式為<code>:icon-name:</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL圖示URL]</td> 
   <td>輸入或對映要當作此訊息圖示使用的影像URL。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL連結名稱]</p> </td> 
   <td> <p>啟用此選項以允許名稱和管道使用<code>@username</code>或<code>#channel</code>格式。 </p> <p>如需詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/docs/formatting">格式化應用程式介面的文字</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL剖析訊息文字]</p> </td> 
   <td> <p>啟用此選項以允許自動剖析。 </p> <p>如需詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/docs/formatting">格式化應用程式介面的文字</a>。</p> <p>注意：如果您在原始訊息中使用[！UICONTROL連結名稱]或[！UICONTROL剖析訊息文字]選項，您也應在執行[！UICONTROL更新訊息]模組時指定這些選項。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL使用Markdown]</p> </td> 
   <td> <p>啟用此選項以允許[!DNL Slack]在文字中使用Markdown。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL展開主要是文字型內容]</p> </td> 
   <td> <p>啟用此選項以允許展開主要是文字型內容。 </p> <p>如需在[!DNL Slack]中展開的相關詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/reference/messaging/link-unfurling">在訊息中展開連結</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL展開媒體內容]</p> </td> 
   <td> <p>啟用此選項可允許展開媒體內容。 </p> <p>如需在[!DNL Slack]中展開的相關詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/reference/messaging/link-unfurling">在訊息中展開連結</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL使用者名稱]</td> 
   <td>指定用來張貼訊息的使用者名稱。 若未指定使用者名稱，則會使用「機器人」名稱。</td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL 刪除訊息]

此動作模組會刪除指定的訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應管道ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID]</td> 
   <td> <p> 輸入或對應您要刪除之訊息的時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如Watch Private Channel訊息模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL作為使用者]</td> 
   <td> <p> 啟用此選項以連線中所用認證的使用者身分刪除訊息。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得私人頻道訊息]

此動作模組會從選取的頻道擷取訊息的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入（對應）管道ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL訊息ID （時間戳記）]</p> </td> 
   <td> <p> 輸入或對應您要擷取相關資訊之訊息的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Private Channel Messages]模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得公用頻道訊息]**

此動作模組會從指定的公用通道傳回具有特定ID的訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應管道ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訊息ID （時間戳記）]</td> 
   <td> <p> 輸入或對應您要擷取相關資訊之訊息的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Public Channel Messages]模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新訊息]

此動作模組可讓您編輯現有訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter a channel ID or name]</p> </td> 
   <td> <p>Choose how you want to select the message you want to .</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>In the <strong>[!UICONTROL Channel ID or name]</strong> field, enter or map the Channel ID or of the channel that contains the message, then enter the <strong>[!UICONTROL Time Stamp (Message ID)]</strong> of the message.</p> <p>Note: The Channel ID can be retrieved using the [!UICONTROL List Channels] module.</p> </li> 
     <li> <p><strong>[!UICONTROL Select from the list]</strong> </p> <p>Select the type of channel, then select the channel, then select the message.</p> </li> 
    </ul> </td> 
  </tr> -->
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應包含您要更新之訊息的頻道ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL訊息ID （時間戳記）]</p> </td> 
   <td> <p> 輸入或對應您要擷取相關資訊之訊息的訊息時間戳記。</p> <p>注意：時間戳記可使用其他模組擷取，例如[！UICONTROL Watch Public Channel Messages]模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Text]</p> </td> 
   <td> <p>輸入要更新的訊息的新文字內容。</p> <p>如需詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/docs/formatting">格式化應用程式介面的文字</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL作為使用者]</td> 
   <td>啟用此選項以擁有此模組連線所使用之認證的使用者身分更新訊息。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL附件]</td> 
   <td>針對您想要附加至郵件的每個專案，按一下<b>新增專案</b>並填入專案的詳細資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL連結名稱]</p> </td> 
   <td> <p>啟用此選項以允許名稱和管道使用<code>@username</code>或<code>#channel</code>格式。 </p> <p>如需詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/docs/formatting">格式化應用程式介面的文字</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL剖析訊息文字]</p> </td> 
   <td> <p>啟用此選項以允許自動剖析。 </p> <p> 如需詳細資訊，請參閱[!DNL Slack]檔案中的<a href="https://api.slack.com/docs/formatting">格式化應用程式介面的文字</a>。</p> <p>注意：如果您在原始訊息中使用[！UICONTROL連結名稱]或[！UICONTROL剖析訊息文字]選項，您也應在執行更新訊息模組時指定這些選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 觀看私人頻道訊息]

此觸發模組會在新訊息新增至私人頻道（群組）時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Channel] </td> 
   <td> <p>選取您要觀看新訊息的私人頻道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>設定在一個執行週期內[!DNL Workfront Fusion]將傳回的最大訊息數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看公開頻道訊息]

此觸發模組會在新訊息新增至公用頻道時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Channel] </td> 
   <td> <p>選取您要觀看新訊息的公共頻道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>設定在一個執行週期內[!DNL Workfront Fusion]將傳回的最大訊息數。</p> </td> 
  </tr> 
 </tbody> 
</table>



### 交談

* [取得頻道](#get-a-channel)
* [清單頻道](#list-channels)
* [在頻道中列出成員](#list-members-in-channel)

#### [!UICONTROL 取得頻道]

此動作模組會傳回工作區管道的相關資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL管道ID]</p> </td> 
   <td> <p>輸入或對應您要擷取相關資訊之管道的ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </td> 
  </tr> 
 </tbody>

#### [!UICONTROL 列出頻道]

此搜尋模組會傳回工作區中所有頻道的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL排除已封存的]</p> </td> 
   <td> <p>選取「[！UICONTROL是]」以在結果中排除已封存的管道。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL型別] </td> 
   <td> <p>選取您要擷取的管道型別。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>設定在一個執行週期內[!DNL Workfront Fusion]將傳回的最大通道數。</p> </td> 
  </tr> 
 </tbody> 
</table>
</table>

#### [!UICONTROL 列出頻道]中的成員

此搜尋模組會傳回所選頻道中的使用者清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
<tr> 
   <td role="rowheader"> <p>[！UICONTROL輸入管道ID或名稱]</p> </td> 
   <td> <p>選擇您希望如何選取所要的訊息。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL管道ID或名稱]</strong>欄位中，輸入或對應您要列出使用者之管道或管道的ID。</p> <p>注意：頻道ID可使用[！UICONTROL清單頻道]模組擷取。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取管道型別，然後選取管道。</p> </li> 
    </ul> </td> 
  </tr>
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>設定在一個執行週期內[!DNL Workfront Fusion]將傳回的成員數目上限。</p> </td> 
  </tr> 
 </tbody> 
</table>


### 其他

#### [!UICONTROL 進行API呼叫]

此動作模組可讓您對[!DNL Slack] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Slack]模組無法完成的資料流程自動化。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Slack]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL URL]</td> 
   <td>輸入相對於<code>https://slack.com/api/</code>的路徑。 範例： <code>/users/identity</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL方法]</td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[！UICONTROL Workfront Fusion]會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL基底URL]</td> 
   <td>選取您要用於API呼叫的基本URL。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳送存取權杖]</td> 
   <td>選取您要以標頭或查詢引數的形式傳送存取權杖。</td> 
  </tr> 
 </tbody> 
</table>

## 術語

下列術語在設定[!DNL Slack]模組時可能很有用：

* **DM**： [!UICONTROL 直接訊息]
* **IM**： [!UICONTROL 立即訊息]
* **私人頻道**：先前為[!UICONTROL 群組]
* **直接訊息**：先前為[!UICONTROL IM]
* **頻道**： API檔案中的[!UICONTROL 交談]，[!DNL Slack]應用程式中的[!UICONTROL 頻道]。

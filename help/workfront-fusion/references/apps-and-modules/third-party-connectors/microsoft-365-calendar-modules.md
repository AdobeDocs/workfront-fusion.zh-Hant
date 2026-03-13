---
title: Microsoft Office 365行事曆
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Microsoft Office 365行事曆的工作流程，並將其連線到多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: fdecf740-e735-4569-b1a2-7c25c751ba42
source-git-commit: 413736673426c1a77dac9f15defa43d4348638b5
workflow-type: tm+mt
source-wordcount: '2047'
ht-degree: 21%

---

# [!DNL Microsoft Office 365 Calendar]

在 Adobe Workfront Fusion 情境中，您可以將使用 [!DNL Microsoft Office 365 Calendar] 的工作流程自動化，以及將其連接至多個第三方應用程式和服務。

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

若要使用 [!DNL Microsoft Office 365 Calendar] 模組，您必須擁有 [!DNL Microsoft Office 365 Calendar] 帳戶。

## Microsoft Office 365行事曆API資訊

Microsoft Office 365行事曆聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 版本</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v2.0.10</td> 
  </tr>
 </tbody> 
 </table>

## 正在將[!DNL Office 365 Calendar]服務連線到Workfront Fusion

如需有關將您的[!DNL Office 365 Calendar]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) — 基本指示

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## [!DNL Microsoft Office 365 Calendar] 模組及其欄位

當您設定 [!DNL Microsoft Office 365 Calendar] 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Microsoft Office 365 Calendar] 欄位。在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [活動](#event)
* [行事曆](#calendar)
* [其他](#other)

### 活動

* [[!UICONTROL 建立事件]](#create-an-event)
* [[!UICONTROL 刪除事件]](#delete-an-event)
* [[!UICONTROL 取得事件]](#get-an-event)
* [[!UICONTROL 搜尋事件]](#search-events)
* [[!UICONTROL 更新事件]](#update-an-event)
* [[!UICONTROL 監視事件]](#watch-events)

#### [!UICONTROL 建立事件]

此操作模組會建立新事件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>有關將[!DNL Office 365]帳戶連接到WorkfrontFusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe WorkfrontFusion的連接 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL主題]</td> 
   <td> <p>輸入或映射建立事件的標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL開始日期]</td> 
   <td> 輸入事件以組合日期和時間表示形式開始的單個時間點。 使用格式<code>{date}T{time}</code>；例如，<code>2017-08-29T04:00:00.0000000</code>。 如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">類型強制轉換</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL結束日期]</td> 
   <td> 輸入事件以組合日期和時間表示結束的單個時間點。 使用格式<code>{date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">類型強制轉換</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL提醒於]</td> 
   <td>選取是否要為此事件啟用提醒。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL提醒]</td> 
   <td>輸入或對應提醒觸發時，事件開始前的分鐘數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL重要性]</td> 
   <td> <p>選取此事件的重要性。</p> 
    <ul> 
     <li>[！UICONTROL低]</li> 
     <li>[！UICONTROL Medium]</li> 
     <li>[！UICONTROL高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL敏感度] </td> 
   <td> <p>選取此事件的敏感度。</p> 
    <ul> 
     <li><strong>[！UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[！UICONTROL Personal]</strong> </p> <p>The recipient sees a "[!UICONTROL Please treat this as Personal]" message.</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>收件者看到「[！UICONTROL請將此視為私人]」訊息。 收件者的收件匣規則不會轉寄或重新導向此事件。</p> </li> 
     <li> <p><strong>[！UICONTROL機密檔案]</strong> </p> <p>收件者看到「[！UICONTROL請將此視為機密]」訊息。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL內文內容型別]</td> 
   <td>選取內文內容是純文字還是HTML。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL內文內容]</td> 
   <td>輸入或對應與事件相關之訊息的正文。 它可以是HTML或文字格式（如上方[！UICONTROL內文內容型別]欄位中所指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL位置]</td> 
   <td> <p>輸入或對應事件位置詳細資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">已要求[！UICONTROL回應]</td> 
   <td>選取<strong>[！UICONTROL是]</strong>以要求受邀者傳送回應給活動邀請。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL顯示為]</td> 
   <td> <p>選取您想要讓檢視您行事曆的人員看到事件的方式。</p> 
    <ul> 
     <li>[！UICONTROL自由]</li> 
     <li>[！UICONTROL Tentative]</li> 
     <li>[！UICONTROL忙碌]</li> 
     <li>[！UICONTROL外出]</li> 
     <li>[！UICONTROL在其他地方工作]</li> 
     <li>[！UICONTROL未知]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL出席者]</p> </td> 
   <td> <p>針對您想要邀請的每個出席者，按一下[新增專案] <b> </b>並輸入下列專案：</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL名稱]</strong> </p> <p>Enter or map the attendee's name.</p> </li> 
     <li> <p><strong>[!UICONTROL電子郵件]</strong> </p> <p>輸入或映射與會者的電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL類別]</td> 
   <td>對於您希望事件顯示為日曆上的每個類別，按一下<b>添加項</b>，然後輸入或映射該類別。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an Event]

This action module deletes an existing event.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL事件ID]</td> 
   <td> <p>輸入或映射要刪除的事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 獲取事件]

此操作模組檢索指定事件的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>有關將[!DNL Office 365]帳戶連接到WorkfrontFusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe WorkfrontFusion的連接 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL事件ID]</td> 
   <td> <p>輸入或映射要檢索有關詳細資訊的事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜索事件]

此搜索模組在選定日曆中建立、更新、刪除、啟動或結束事件時保留事件的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>有關將[!DNL Office 365]帳戶連接到WorkfrontFusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe WorkfrontFusion的連接 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL行事曆群組ID]</td> 
   <td>選取包含您要觀看活動之日曆的[！UICONTROL日曆群組]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL行事曆]</td> 
   <td> <p>選取您要觀看的特定行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td> <p>設定篩選條件以篩選結果。 您可以依下列屬性篩選：</p> 
    <ul> 
     <li>[！UICONTROL主旨]</li> 
     <li>[！UICONTROL事件ID]</li> 
     <li>[！UICONTROL建立日期時間]</li> 
     <li>[！UICONTROL上次修改日期時間]</li> 
     <li>[！UICONTROL Body Preview]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Order by]</td> 
   <td> <p>選取您要如何排序結果。</p> 
    <ul> 
     <li><strong>[!UICONTROL Subject]</strong>, ascending or descending</li> 
     <li><strong>[!UICONTROL Created Date Time]</strong>, ascending or descending</li> 
     <li><strong>[!UICONTROL Last Modified Date Time]</strong>, ascending or descending</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入Workfront Fusion在一個案例執行週期中應傳回的最大事件數。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新事件]

此動作模組會更新現有事件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL事件ID]</td> 
   <td>輸入、對應或選取您要更新之事件的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL主旨]</td> 
   <td> <p>輸入或對應事件的新標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL開始日期]</td> 
   <td> 輸入事件在合併的日期和時間表示中開始時的單一時間點。 使用格式<code>{date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">類型強制轉換</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL結束日期]</td> 
   <td> 輸入事件以組合日期和時間表示結束的單個時間點。 使用格式<code>({date}T{time}</code>；例如，<code>2017-08-29T04:00:00.0000000</code>。 如需支援之日期和時間格式的清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">類型強制轉換</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL提醒開]</td> 
   <td>選擇是否要為此事件激活提醒。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL提醒]</td> 
   <td>輸入或對應提醒觸發時，事件開始前的分鐘數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL重要性]</td> 
   <td> <p>選取此事件的重要性。</p> 
    <ul> 
     <li>[!UICONTROL低]</li> 
     <li>[！UICONTROL Medium]</li> 
     <li>[!UICONTROL高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL敏感度] </td> 
   <td> <p>選擇此事件的敏感度。</p> 
    <ul> 
     <li><strong>[!UICONTROL正常]</strong> </li> 
     <li> <p><strong>[！UICONTROL Personal]</strong> </p> <p>The recipient sees a "[!UICONTROL Please treat this as Personal]" message.</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>收件者看到「[！UICONTROL請將此視為私人]」訊息。 收件者的收件匣規則不會轉寄或重新導向此事件。</p> </li> 
     <li> <p><strong>[！UICONTROL機密檔案]</strong> </p> <p>收件人看到「[!UICONTROL請將此視為機密」消息。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL正文內容類型]</td> 
   <td>選擇與事件關聯的消息的正文內容是純文字檔案還是HTML。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL正文內容]</td> 
   <td>輸入或對應與事件相關之訊息的正文。 它可以是HTML或文本格式（如上面[!UICONTROL正文內容類型]欄位中指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL位置]</td> 
   <td> <p>輸入事件位置詳細資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！請求的UICONTROL響應]</td> 
   <td>選擇<strong>[!UICONTROL是]</strong>以請求被邀請者向事件邀請發送響應。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL顯示為]</td> 
   <td> <p>選取您想要讓檢視您行事曆的人員看到事件的方式。</p> 
    <ul> 
     <li>[！UICONTROL自由]</li> 
     <li>[！UICONTROL Tentative]</li> 
     <li>[！UICONTROL忙碌]</li> 
     <li>[！UICONTROL外出]</li> 
     <li>[！UICONTROL在其他地方工作]</li> 
     <li>[!DNL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL出席者]</p> </td> 
   <td> <p>新增活動的出席者。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL名稱]</strong> </p> <p>輸入出席者的名稱。</p> </li> 
     <li> <p><strong>[！UICONTROL電子郵件]</strong> </p> <p>輸入出席者的電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL類別]</td> 
   <td>Enter or map the categories that you want the event to display as on the calendar.</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 監視事件]

This trigger module retrieves details of an event when the event is created, updated, deleted, started, or ended in the selected calendar.

>[!NOTE]
>
>To watch for deleted occurrences of an event series, select [!UICONTROL By Updated Time] in the [!UICONTROL Watch events] field. 此模組不會監視已刪除的單一事件或刪除的事件系列。


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL觀看活動]</td> 
   <td> <p>選取您要如何觀看活動。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL By Created Time]</strong> </p> <p>觀看新活動。</p> </li> 
     <li> <p><strong>[！UICONTROL （按更新時間）]</strong> </p> <p>觀看更新事件。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL行事曆群組ID]</td> 
   <td>選取包含您要觀看活動之日曆的[！UICONTROL日曆群組]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL行事曆]</td> 
   <td> <p>選擇要監視的特定日曆。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td>設定篩選條件以按主題、事件ID或正文篩選結果。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入在一個方案執行週期中，WorkfrontFusion應返回的最大消息數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 行事曆

* [[!UICONTROL 建立行事曆]](#create-a-calendar)
* [[!UICONTROL 刪除行事曆]](#delete-a-calendar)
* [[!UICONTROL 取得行事曆]](#get-a-calendar)
* [[!UICONTROL 列出行事曆]](#list-calendars)
* [[!UICONTROL 更新行事曆]](#update-a-calendar)



#### [!UICONTROL 建立日曆]

此操作模組在Office 365帳戶中建立新日曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>有關將[!DNL Office 365]帳戶連接到WorkfrontFusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe WorkfrontFusion的連接 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL日曆名稱]</td> 
   <td> <p>Enter a name for the new calendar.</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Calendar]

This action module deletes an existing calendar.

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL日曆ID]</td> 
   <td>輸入要刪除的日曆的[!UICONTROL日曆] ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 獲取日曆]

此操作模組檢索有關單個日曆的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>有關將[!DNL Office 365]帳戶連接到WorkfrontFusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe WorkfrontFusion的連接 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL日曆ID]</td> 
   <td> <p>輸入或映射要檢索有關詳細資訊的日曆的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出日曆]

此搜索模組檢索所有已驗證用戶的日曆的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL行事曆群組ID]</td> 
   <td>選取包含要列出之行事曆的[！UICONTROL行事曆群組]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入Workfront Fusion應在一個情境執行週期中傳回的最大行事曆數。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新行事曆]

此動作模組會編輯現有行事曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL行事曆ID]</td> 
   <td>為您要更新的行事曆輸入[！UICONTROL行事曆ID]。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新行事曆名稱]</td> 
   <td> <p>輸入行事曆的新名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### [!UICONTROL 進行API呼叫]

您可以透過此模組進行自訂的 API 呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於 <code>https://graph.microsoft.com</code> 的路徑。範例：<code> /v1.0/me/events</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。例如 <code>{"Content-type":"application/json"}</code>。Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p> 以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：   <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

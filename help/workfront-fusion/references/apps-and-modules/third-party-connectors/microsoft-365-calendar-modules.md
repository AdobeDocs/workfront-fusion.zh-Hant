---
title: Microsoft Office 365行事曆
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Microsoft Office 365行事曆的工作流程，並將其連線到多個第三方應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: fdecf740-e735-4569-b1a2-7c25c751ba42
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '2050'
ht-degree: 0%

---

# [!DNL Microsoft Office 365 Calendar]

在Adobe Workfront Fusion案例中，您可以自動化使用[!DNL Microsoft Office 365 Calendar]的工作流程，並將其連線至多個協力廠商應用程式和服務。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權</td> 
   <td>
   <p>作業型：無Workfront Fusion授權需求</p>
   <p>以聯結器為基礎（舊版）：用於工作自動化和整合的Workfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL Microsoft Office 365 Calendar]模組，您必須有[!DNL Microsoft Office 365 Calendar]帳戶。

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
   <td role="rowheader">API版本</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
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

## [!DNL Microsoft Office 365 Calendar]模組及其欄位

當您設定[!DNL Microsoft Office 365 Calendar]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Microsoft Office 365 Calendar]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [活動](#event)
* [行事曆](#calendar)
* [其他](#other)

### 活動

* [[!UICONTROL 建立事件]](#create-an-event)
* [[!UICONTROL 刪除事件]](#delete-an-event)
* [[!UICONTROL 取得事件]](#get-an-event)
* [[!UICONTROL 搜尋事件]](#search-events)
* [[!UICONTROL 更新事件]](#update-an-event)
* [[!UICONTROL 觀看活動]](#watch-events)

#### [!UICONTROL 建立事件]

此動作模組會建立新事件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 主旨]</td> 
   <td> <p>輸入或對應已建立事件的標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 開始日期]</td> 
   <td> 輸入事件在合併的日期和時間表示中開始時的單一時間點。 使用格式<code>{date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結束日期]</td> 
   <td> 當事件以合併的日期和時間表示結束時，請輸入單一時間點。 使用格式<code>{date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提醒於]</td> 
   <td>選取是否要為此事件啟用提醒。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提醒]</td> 
   <td>輸入或對應提醒觸發時，事件開始前的分鐘數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 重要性]</td> 
   <td> <p>選取此事件的重要性。</p> 
    <ul> 
     <li>[!UICONTROL 低]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL 高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 敏感度] </td> 
   <td> <p>選取此事件的敏感度。</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>收件者看到「[!UICONTROL 請將此視為個人]」訊息。</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>收件者看到「[!UICONTROL 請將此視為私人]」訊息。 收件者的收件匣規則不會轉寄或重新導向此事件。</p> </li> 
     <li> <p><strong>[!UICONTROL 機密檔案]</strong> </p> <p>收件者看到「[!UICONTROL 請將此視為機密]」訊息。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容型別]</td> 
   <td>選取內文內容是純文字還是HTML。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容]</td> 
   <td>輸入或對應與事件相關之訊息的正文。 它可以是HTML或文字格式（如上方[!UICONTROL 內文內容型別]欄位中所指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 位置]</td> 
   <td> <p>輸入或對應事件位置詳細資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">已要求[!UICONTROL 回應]</td> 
   <td>選取<strong>[!UICONTROL 是]</strong>以要求受邀者傳送回應給活動邀請。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示為]</td> 
   <td> <p>選取您想要讓檢視您行事曆的人員看到事件的方式。</p> 
    <ul> 
     <li>[!UICONTROL 自由]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL 忙碌]</li> 
     <li>[!UICONTROL 外出]</li> 
     <li>[!UICONTROL 在其他地方工作]</li> 
     <li>[!UICONTROL 未知]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 出席者]</p> </td> 
   <td> <p>針對您想要邀請的每個出席者，按一下[新增專案] <b> </b>並輸入下列專案：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入或對應出席者的名稱。</p> </li> 
     <li> <p><strong>[!UICONTROL 電子郵件]</strong> </p> <p>輸入或對應出席者的電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 類別]</td> 
   <td>對於您要在行事曆上顯示事件的每個類別，按一下<b>新增專案</b>，然後輸入或對應類別。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除事件]

此動作模組會刪除現有事件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 事件ID]</td> 
   <td> <p>輸入或對應您要刪除之事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得事件]

此動作模組會擷取指定事件的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 事件ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋事件]

此搜尋模組會在所選行事曆中建立、更新、刪除、開始或結束事件時，擷取事件的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆群組ID]</td> 
   <td>選取包含您要觀看活動之日曆的[!UICONTROL 日曆群組]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆]</td> 
   <td> <p>選取您要觀看的特定行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td> <p>設定篩選條件以篩選結果。 您可以依下列屬性篩選：</p> 
    <ul> 
     <li>[!UICONTROL 主旨]</li> 
     <li>[!UICONTROL 事件ID]</li> 
     <li>[!UICONTROL 建立日期時間]</li> 
     <li>[!UICONTROL 上次修改日期時間]</li> 
     <li>[!UICONTROL Body Preview]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>選取您要如何排序結果。</p> 
    <ul> 
     <li><strong>[!UICONTROL 主旨]</strong>，遞增或遞減</li> 
     <li><strong>[!UICONTROL 建立日期時間]</strong>，遞增或遞減</li> 
     <li><strong>[!UICONTROL 上次修改日期時間]</strong>，遞增或遞減</li> 
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
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 事件ID]</td> 
   <td>輸入、對應或選取您要更新之事件的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 主旨]</td> 
   <td> <p>輸入或對應事件的新標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 開始日期]</td> 
   <td> 輸入事件在合併的日期和時間表示中開始時的單一時間點。 使用格式<code>{date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 結束日期]</td> 
   <td> 當事件以合併的日期和時間表示結束時，請輸入單一時間點。 使用格式<code>({date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提醒於]</td> 
   <td>選取是否要為此事件啟用提醒。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 提醒]</td> 
   <td>輸入或對應提醒觸發時，事件開始前的分鐘數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 重要性]</td> 
   <td> <p>選取此事件的重要性。</p> 
    <ul> 
     <li>[!UICONTROL 低]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL 高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 敏感度] </td> 
   <td> <p>選取此事件的敏感度。</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>收件者看到「[!UICONTROL 請將此視為個人]」訊息。</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>收件者看到「[!UICONTROL 請將此視為私人]」訊息。 收件者的收件匣規則不會轉寄或重新導向此事件。</p> </li> 
     <li> <p><strong>[!UICONTROL 機密檔案]</strong> </p> <p>收件者看到「[!UICONTROL 請將此視為機密]」訊息。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容型別]</td> 
   <td>選取與事件相關之訊息的內文內容為純文字還是HTML。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容]</td> 
   <td>輸入或對應與事件相關之訊息的正文。 它可以是HTML或文字格式（如上方[!UICONTROL 內文內容型別]欄位中所指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 位置]</td> 
   <td> <p>輸入事件地點詳細資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">已要求[!UICONTROL 回應]</td> 
   <td>選取<strong>[!UICONTROL 是]</strong>以要求受邀者傳送回應給活動邀請。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 顯示為]</td> 
   <td> <p>選取您想要讓檢視您行事曆的人員看到事件的方式。</p> 
    <ul> 
     <li>[!UICONTROL 自由]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL 忙碌]</li> 
     <li>[!UICONTROL 外出]</li> 
     <li>[!UICONTROL 在其他地方工作]</li> 
     <li>[!DNL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 出席者]</p> </td> 
   <td> <p>新增活動的出席者。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入出席者的名稱。</p> </li> 
     <li> <p><strong>[!UICONTROL 電子郵件]</strong> </p> <p>輸入出席者的電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 類別]</td> 
   <td>輸入或對應您希望事件在行事曆上顯示的類別。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看活動]

在所選行事曆中建立、更新、刪除、開始或結束事件時，此觸發程式模組會擷取事件的詳細資料。

>[!NOTE]
>
>若要觀看事件序列的已刪除事件，請在[!UICONTROL 觀看事件]欄位中選取[!UICONTROL 依更新時間]。 此模組不會監視已刪除的單一事件或刪除的事件系列。


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 觀看活動]</td> 
   <td> <p>選取您要如何觀看活動。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By Created Time]</strong> </p> <p>觀看新活動。</p> </li> 
     <li> <p><strong>[!UICONTROL （按更新時間）]</strong> </p> <p>觀看更新事件。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆群組ID]</td> 
   <td>選取包含您要觀看活動之日曆的[!UICONTROL 日曆群組]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆]</td> 
   <td> <p>選取您要觀看的特定行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td>設定篩選條件，依主旨、事件ID或本文篩選結果。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入Workfront Fusion在一個案例執行週期中應傳回的最大訊息數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 行事曆

* [[!UICONTROL 建立行事曆]](#create-a-calendar)
* [[!UICONTROL 刪除行事曆]](#delete-a-calendar)
* [[!UICONTROL 取得行事曆]](#get-a-calendar)
* [[!UICONTROL 列出行事曆]](#list-calendars)
* [[!UICONTROL 更新行事曆]](#update-a-calendar)



#### [!UICONTROL 建立行事曆]

此動作模組會在您的Office 365帳戶中建立新的行事曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆名稱]</td> 
   <td> <p>輸入新行事曆的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除行事曆]

此動作模組會刪除現有的行事曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆ID]</td> 
   <td>輸入您要刪除之行事曆的[!UICONTROL 行事曆] ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得行事曆]

此動作模組會擷取單一行事曆的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊的行事曆的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出行事曆]

此搜尋模組會擷取所有已驗證使用者行事曆的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆群組ID]</td> 
   <td>選取包含要列出之行事曆的[!UICONTROL 行事曆群組]。</td> 
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
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 行事曆ID]</td> 
   <td>為您要更新的行事曆輸入[!UICONTROL 行事曆ID]。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 新行事曆名稱]</td> 
   <td> <p>輸入行事曆的新名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### [!UICONTROL 進行API呼叫]

此模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於<code>https://graph.microsoft.com</code>的路徑。 範例：<code> /v1.0/me/events</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 例如 <code>{"Content-type":"application/json"}</code>。Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p> 以標準JSON物件的形式新增API呼叫的查詢。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：   <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>">  
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

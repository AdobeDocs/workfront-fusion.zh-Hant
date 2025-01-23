---
title: Microsoft Office 365行事曆
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Microsoft Office 365行事曆的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: fdecf740-e735-4569-b1a2-7c25c751ba42
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '1585'
ht-degree: 0%

---

# [!DNL Microsoft Office 365 Calendar]

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Microsoft Office 365 Calendar]的工作流程，並將其連線至多個協力廠商應用程式和服務。

若要搭配[!DNL Adobe Workfront Fusion]使用[!DNL Office 365 Calendar]，必須有[!DNL Office 365 Excel]帳戶。 您可以在[www.office.com](https://www.office.com/)建立一個。

如需有關將您的Office 365帳戶連線到[!DNL Workfront Fusion]的說明，請參閱[建立與Adobe的連線 [!DNL Workfront Fusion]  — 基本說明](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

在您授與同意後，系統會將您重新導向回[!UICONTROL Workfront Fusion]管理頁面，您可在此繼續建立您的情境。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
  <td> <p>[!UICONTROL Pro] 或更高</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 先決條件

若要使用[!DNL Microsoft Office 365 Calendar]模組，您必須有[!DNL Microsoft Office 365 Calendar]帳戶。

## Microsoft Office 365行事曆API資訊

Microsoft Office 365行事曆聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
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

## 正在將[!DNL Office 365 Calendar]服務連線到[!DNL Workfront Fusion]

如需有關將您的[!DNL Office 365 Calendar]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線 — 基本指示](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## [!DNL Microsoft Office 365 Calendar]模組及其欄位

當您設定[!DNL Microsoft Office 365 Calendar]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Microsoft Office 365 Calendar]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [事件](#event)
* [行事曆](#calendar)
* [其他](#other)

### 事件

* [[!UICONTROL Watch Events]](#watch-events)
* [[!UICONTROL Search Events]](#search-events)
* [[!UICONTROL Get an Event]](#get-an-event)
* [[!UICONTROL Create an Event]](#create-an-event)
* [[!UICONTROL Update an Event]](#update-an-event)
* [[!UICONTROL Delete an Event]](#delete-an-event)

#### [!UICONTROL Watch Events]

在所選行事曆中建立、更新、刪除、開始或結束事件時，此觸發程式模組會擷取事件的詳細資料。

>[!NOTE]
>
>若要觀看事件序列遭刪除的事件，請在[!UICONTROL Watch events]欄位中選取[!UICONTROL By Updated Time]。 此模組不會監視已刪除的單一事件或刪除的事件系列。


<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watch events]</td> 
   <td> <p>選取您要如何觀看活動。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL By Created Time]</strong> </p> <p>觀看新活動。</p> </li> 
     <li> <p><strong>[!UICONTROL By Updated Time]</strong> </p> <p>觀看更新事件。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>選取包含您要觀看活動之行事曆的[!UICONTROL calendar group]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar]</td> 
   <td> <p>選取您要觀看的特定行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td>設定篩選條件，依主旨、事件ID或本文篩選結果。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td> <p>輸入在一個案例執行週期中[!DNL Workfront Fusion]應傳回的最大訊息數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Search Events]

此搜尋模組會在所選行事曆中建立、更新、刪除、開始或結束事件時，擷取事件的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>選取包含您要觀看活動之行事曆的[!UICONTROL calendar group]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar]</td> 
   <td> <p>選取您要觀看的特定行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Filter]</td> 
   <td> <p>設定篩選條件以篩選結果。 您可以依下列屬性篩選：</p> 
    <ul> 
     <li>[!UICONTROL Subject]</li> 
     <li>[!UICONTROL Event ID]</li> 
     <li>[!UICONTROL Created Date Time]</li> 
     <li>[!UICONTROL Last Modified Date Time]</li> 
     <li>[!UICONTROL Body Preview]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>選取您要如何排序結果。</p> 
    <ul> 
     <li><strong>[!UICONTROL Subject]</strong>，遞增或遞減</li> 
     <li><strong>[!UICONTROL Created Date Time]</strong>，遞增或遞減</li> 
     <li><strong>[!UICONTROL Last Modified Date Time]</strong>，遞增或遞減</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>輸入在一個案例執行週期中[!DNL Workfront Fusion]應傳回的最大事件數。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Event]

此動作模組會擷取指定事件的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create an Event]

此動作模組會建立新事件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>輸入或對應已建立事件的標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start date]</td> 
   <td> 輸入事件在合併的日期和時間表示中開始時的單一時間點。 使用格式<code>({date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End date]</td> 
   <td> 當事件以合併的日期和時間表示結束時，請輸入單一時間點。 使用格式<code>{date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder on]</td> 
   <td>選取是否要為此事件啟用提醒。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder]</td> 
   <td>輸入或對應提醒觸發時，事件開始前的分鐘數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>選取此事件的重要性。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sensitivity] </td> 
   <td> <p>選取此事件的敏感度。</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>收件者看到"[!UICONTROL Please treat this as Personal]"訊息。</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>收件者看到"[!UICONTROL Please treat this as Private]"訊息。 收件者的收件匣規則不會轉寄或重新導向此事件。</p> </li> 
     <li> <p><strong>[!UICONTROL Confidential]</strong> </p> <p>收件者看到"[!UICONTROL Please treat this as Confidential]"訊息。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content type]</td> 
   <td>選取內文內容是純文字還是HTML。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td>輸入或對應與事件相關之訊息的正文。 它可以是HTML或文字格式（如上方[!UICONTROL Body Content Type]欄位中所指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Location]</td> 
   <td> <p>輸入事件地點詳細資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Response requested]</td> 
   <td>選取<strong>[!UICONTROL Yes]</strong>以要求受邀者傳送活動邀請的回應。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show as]</td> 
   <td> <p>選取您想要讓檢視您行事曆的人員看到事件的方式。</p> 
    <ul> 
     <li>[!UICONTROL Free]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL Busy]</li> 
     <li>[!UICONTROL Out of office]</li> 
     <li>[!UICONTROL Working elsewhere]</li> 
     <li>[!UICONTROL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attendees]</p> </td> 
   <td> <p>新增活動的出席者。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>輸入出席者的名稱。</p> </li> 
     <li> <p><strong>[!UICONTROL Email]</strong> </p> <p>輸入出席者的電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Category]</td> 
   <td>輸入或對應您希望事件在行事曆上顯示的類別。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an Event]

此動作模組會更新現有事件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td>輸入、對應或選取您要更新之事件的ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subject]</td> 
   <td> <p>輸入或對應已建立事件的標題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start date]</td> 
   <td> 輸入事件在合併的日期和時間表示中開始時的單一時間點。 使用格式<code>{date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL End date]</td> 
   <td> 當事件以合併的日期和時間表示結束時，請輸入單一時間點。 使用格式<code>({date}T{time}</code>；例如<code>2017-08-29T04:00:00.0000000</code>。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder on]</td> 
   <td>選取是否要為此事件啟用提醒。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reminder]</td> 
   <td>輸入或對應提醒觸發時，事件開始前的分鐘數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Importance]</td> 
   <td> <p>選取此事件的重要性。</p> 
    <ul> 
     <li>[!UICONTROL Low]</li> 
     <li>[!UICONTROL Medium]</li> 
     <li>[!UICONTROL High]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Sensitivity] </td> 
   <td> <p>選取此事件的敏感度。</p> 
    <ul> 
     <li><strong>[!UICONTROL Normal]</strong> </li> 
     <li> <p><strong>[!UICONTROL Personal]</strong> </p> <p>收件者看到"[!UICONTROL Please treat this as Personal]"訊息。</p> </li> 
     <li> <p><strong>[!UICONTROL Private]</strong> </p> <p>收件者看到"[!UICONTROL Please treat this as Private]"訊息。 收件者的收件匣規則不會轉寄或重新導向此事件。</p> </li> 
     <li> <p><strong>[!UICONTROL Confidential]</strong> </p> <p>收件者看到"[!UICONTROL Please treat this as Confidential]"訊息。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content type]</td> 
   <td>選取與事件相關之訊息的內文內容為純文字還是HTML。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body content]</td> 
   <td>輸入或對應與事件相關之訊息的正文。 它可以是HTML或文字格式（如上方[!UICONTROL Body Content Type]欄位中所指定）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Location]</td> 
   <td> <p>輸入事件地點詳細資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Response requested]</td> 
   <td>選取<strong>[!UICONTROL Yes]</strong>以要求受邀者傳送活動邀請的回應。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Show as]</td> 
   <td> <p>選取您想要讓檢視您行事曆的人員看到事件的方式。</p> 
    <ul> 
     <li>[!UICONTROL Free]</li> 
     <li>[!UICONTROL Tentative]</li> 
     <li>[!UICONTROL Busy]</li> 
     <li>[!UICONTROL Out of office]</li> 
     <li>[!UICONTROL Working elsewhere]</li> 
     <li>[!DNL Unknown]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attendees]</p> </td> 
   <td> <p>新增活動的出席者。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Name]</strong> </p> <p>輸入出席者的名稱。</p> </li> 
     <li> <p><strong>[!UICONTROL Email]</strong> </p> <p>輸入出席者的電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Category]</td> 
   <td>輸入或對應您希望事件在行事曆上顯示的類別。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an Event]

此動作模組會刪除現有事件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>輸入或對應您要刪除之事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 行事曆

* [[!UICONTROL List Calendars]](#list-calendars)
* [[!UICONTROL Get a Calendar]](#get-a-calendar)
* [[!UICONTROL Create a Calendar]](#create-a-calendar)
* [[!UICONTROL Update a Calendar]](#update-a-calendar)
* [[!UICONTROL Delete a Calendar]](#delete-a-calendar)

#### [!UICONTROL List Calendars]

此搜尋模組會擷取所有已驗證使用者行事曆的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar Group ID]</td> 
   <td>選取包含您要列出之行事曆的[!UICONTROL calendar group]。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit]</td> 
   <td>輸入在一個案例執行週期內應傳回行事曆[!DNL Workfront Fusion]的最大數目。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Calendar]

此動作模組會擷取單一行事曆的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊的行事曆的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create a Calendar]

此動作模組會在您的Google帳戶中建立新行事曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar name]</td> 
   <td> <p>輸入新行事曆的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Calendar]

此動作模組會編輯現有行事曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td>輸入您要更新之行事曆的[!UICONTROL Calendar ID]。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New Calendar name]</td> 
   <td> <p>輸入新行事曆的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Calendar]

此動作模組會刪除現有的行事曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar ID]</td> 
   <td>輸入您要刪除行事曆的[!UICONTROL Calendar] ID。</td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### [!UICONTROL Make an API Call]

此模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於<code>https://graph.microsoft.com</code>的路徑。 範例：<code> /v1.0/me/events</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增要求的標頭。例如，<code>{"Content-type":"application/json"}</code>。 [!DNL Workfront Fusion]為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
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

---
title: Google行事曆模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Google Calendar的工作流程，並將其連結到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 6e514204-cd8e-4f30-bbbb-b8fbe48fc670
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '2723'
ht-degree: 0%

---

# [!DNL Google Calendar]模組

在Adobe Workfront Fusion案例中，您可以自動執行使用[!UICONTROL Google行事曆]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront計畫*</td>
  <td> <p>[!UICONTROL Pro]或更高版本</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權*</td>
   <td> <p>[!UICONTROL 計畫]，[!UICONTROL 工作]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>目前授權需求：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版授權要求：[!UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] Adobe Workfront計畫，貴組織必須購買Adobe Workfront Fusion以及Adobe Workfront，才能使用本文所述的功能。 Workfront Fusion包含在[!UICONTROL Ultimate] Workfront計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買Adobe Workfront Fusion和Adobe Workfront，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請聯絡您的Workfront管理員。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 先決條件

若要使用[!DNL Google Calendar]模組，您必須有[!DNL Google]帳戶。

## Google日曆API資訊

Google Calendar聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://www.googleapis.com/calendar/v3</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v3 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v5.4.5</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Google Calendar]模組及其欄位

當您設定[!DNL Google Calendar]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Google Calendar]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [觸發程序](#triggers)
* [動作](#actions)
* [迭代器](#iterators)

### 觸發程序

* [觀看活動](#watch-events)
* [觀看活動（即時）](#watch-events-instant)

#### 觀看活動

此觸發器模組會在您指定的行事曆中新增、更新、刪除、開始或結束新事件時執行情境。 模組會傳回與一個或多個記錄相關聯的所有標準欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Calendar]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 行事曆] </td> 
   <td> <p>選取您希望模組使用的行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 手錶]</td> 
   <td> <p>選擇您是隻想觀看新活動，還是想觀看新活動和所有變更。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 顯示已刪除的事件]</td> 
   <td> <p>啟用此選項以包含已刪除的事件。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query] </td> 
   <td> <p>輸入要傳回結果的文字。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 最大事件數]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內處理的最大事件數（每個案例執行的重複數量）。 如果該值設定得太高，則在指定的第三方服務端可能會中斷連線（逾時）。 Workfront Fusion對此沒有影響。 我們建議您設定較低的值，並為最大週期數定義較高的值，或是更頻繁地執行情境。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看活動（即時）

此觸發模組使用mailhook建立電子郵件地址，您可將其作為事件的邀請者。 模組會根據收到電子郵件地址邀請的事件啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Mailhook] </td> 
   <td> <p>選取您要用於此模組的mailhook。 若要建立新的mailhook，請按一下[新增] <b></b>，然後輸入您要用於mailhook的連線。</p><p>如需有關將您的[!DNL Google Calendar]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 最大事件數]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內處理的最大事件數（每個案例執行的重複數量）。 如果該值設定得太高，則在指定的第三方服務端可能會中斷連線（逾時）。 Workfront Fusion對此沒有影響。 我們建議您設定較低的值，並為最大週期數定義較高的值，或是更頻繁地執行情境。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [建立行事曆](#create-a-calendar)
* [建立事件](#create-an-event)
* [刪除事件](#delete-an-event)
* [取得事件](#get-events)
* [更新事件](#update-an-event)

#### 建立行事曆

此動作模組會建立與帳戶關聯的行事曆。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Calendar]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 色彩] </td> 
   <td> <p>選取與行事曆關聯的顏色。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 行事曆名稱] </td> 
   <td> <p>輸入或對應新行事曆的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立事件]

此動作模組會建立事件。

您可以指定事件的行事曆和引數。

模組會傳回事件的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>如需有關將您的[!DNL Google Calendar]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 行事曆]</td> 
   <td> <p>選取您要顯示事件的行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 色彩]</td> 
   <td>選取事件在行事曆上顯示的顏色。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 事件名稱]</td> 
   <td> <p> 輸入或對應事件的名稱。 </p> <p>注意：如果您在[!UICONTROL 建立事件]欄位中選取[!UICONTROL 快速新增]，您可以包含事件的日期和時間，而Workfront Fusion會針對該日期和時間建立事件。 範例： <code>Appointment at Capitol Hill on June 3rd 10am-10:25am</code>。 如果您選取[!UICONTROL 快速新增]，但未在事件名稱中加入日期和時間，則事件將從目前時間建立並持續一小時。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 全天事件]</td> 
   <td>如果事件是全天事件（不需要開始和結束時間），則啟用此選項。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 開始日期]</td> 
   <td> <p>輸入或對應事件的開始日期和時間。 </p> <p>如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 結束日期]</td> 
   <td> <p> 輸入或對應事件的結束日期和時間。 </p> <p>如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 說明]</td> 
   <td>輸入或對應事件的說明。 此欄位支援HTML。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 位置]</td> 
   <td>以文字形式輸入事件的位置。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 使用此事件的預設提醒設定]</td> 
   <td>啟用此選項以使用預設提醒設定。 如果您在[!UICONTROL Reminder]欄位中設定自訂提醒，此值會設為「否」。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 提醒] </td> 
   <td> <p>新增事件提醒。 對於每個要新增的提醒，按一下<b>新增專案</b>，然後選取要提醒的方法，並定義要提醒的事件之前的時間長度（分鐘）。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 出席者]</td> 
   <td>將出席者新增至活動。 為每位出席者按一下<b>新增出席者</b>，然後輸入或對應其名稱與電子郵件地址。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 顯示為]</td> 
   <td>選取您希望檢視您行事曆的人員在此活動期間將您視為「忙碌」或「可用」。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 可見性] </td> 
   <td> <p>選取此事件的可見性。 </p> 
    <ul> 
     <li> <p><b>[!UICONTROL 預設值]</b></p> <p>事件具有您在行事曆設定中設定的可見度。</p> </li> 
     <li> <p><b>[!UICONTROL Public]</b></p> <p>與該行事曆共用之任何人都可以看見此事件。</p> </li> 
     <li> <p><b>[!UICONTROL Private]</b></p> <p>只有與會者可看見此活動。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 傳送有關事件建立的通知]</td> 
   <td> <p>選取是否將建立新事件的通知傳送給所有來賓、非[!DNL Google Calendar]來賓，或不要傳送給任何人。</p> <p>提示：我們建議僅在移轉使用案例中使用[!UICONTROL 無]選項。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 來賓可以修改事件]</td> 
   <td> <p>如果您希望來賓能夠修改此事件，請啟用此選項。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 遞回]</td> 
   <td>新增您要套用至此事件的任何遞回規則。 每個規則都需要有[!UICONTROL RRULE]、[!UICONTROL EXRULE]、[!UICONTROL RDATE]和[!UICONTROL EXDATE]行的清單，才能處理週期性事件。 請注意，此欄位中不允許有[!UICONTROL DTSTART]和[!UICONTROL DTEND]行；事件的開始和結束時間是在開始和結束欄位中指定。 單一事件或週期性事件的例項會省略此欄位。 如需詳細資訊，請參閱<a href="https://tools.ietf.org/html/rfc5545#section-3.8.5">RFC5545</a>。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除事件]

此動作模組會刪除事件。

您可以指定日曆和事件ID。

模組會傳回事件的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Calendar]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 行事曆]</td> 
   <td> <p>選取包含您要刪除之事件的行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 事件ID]</td> 
   <td> <p> 輸入先前建立的[!DNL Google Calendar]要刪除之事件的事件ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得事件]

此模組會根據您指定的條件，擷取所選行事曆中事件的相關資訊。

您可以指定搜尋的行事曆和引數。

模組會傳回事件的ID及任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>如需有關將您的[!DNL Google Calendar]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 行事曆]</td> 
   <td> <p>選取您要擷取事件的行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 開始日期]</td> 
   <td> <p> 輸入或對應事件開始的日期。 此模組也會擷取在此日期之前開始的、在輸入開始日期仍然發生的事件。 </p> <p>如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 結束日期]</td> 
   <td> <p> 輸入或對應事件結束的日期。 </p> <p> 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 單一事件]</td> 
   <td> <p> 啟用此選項可將週期性事件視為單一例項。 例如，如果您有每週會議且已啟用此選項，模組會以個別事件的形式傳回每週的會議。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Query]</td> 
   <td> <p>輸入或對應您要搜尋的搜尋字詞。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Order by]</td> 
   <td> <p>選取結果中傳回事件的順序。</p> 
    <ul> 
     <li><strong>[!UICONTROL 開始時間]</strong>：依開始日期和時間（升序）排序。 這僅在查詢單一事件時可用。</li> 
     <li><strong>[!UICONTROL 更新時間]</strong>：依上次修改時間排序（升序）。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 傳回事件數上限]</td> 
   <td> <p>設定Workfront Fusion在一個執行週期內傳回的最大事件數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新事件]

此動作模組會變更現有事件。

您可以指定日曆和事件ID。

模組會傳回事件的ID和任何關聯欄位，以及連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Google Calendar]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 行事曆] </td> 
   <td> <p>選取您要使用的行事曆。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 事件ID] </td> 
   <td> <p>輸入先前建立的[!DNL Google Calendar]事件中要更新的事件ID。</p> </td> 
  </tr>   <tr> 
   <td>[!UICONTROL 事件名稱]</td> 
   <td> <p> 輸入或對應事件的名稱。 </p> <p>注意：如果您在[!UICONTROL 建立事件]欄位中選取[!UICONTROL 快速新增]，您可以包含事件的日期和時間，而Workfront Fusion會針對該日期和時間建立事件。 範例： <code>Appointment at Capitol Hill on June 3rd 10am-10:25am</code>。 如果您選取[!UICONTROL 快速新增]，但未在事件名稱中加入日期和時間，則事件將從目前時間建立並持續一小時。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 全天事件]</td> 
   <td>如果事件是全天事件（不需要開始和結束時間），則啟用此選項。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 開始日期]</td> 
   <td> <p>輸入或對應事件的開始日期和時間。 </p> <p>如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 結束日期]</td> 
   <td> <p> 輸入或對應事件的結束日期和時間。 </p> <p>如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 說明]</td> 
   <td>輸入或對應事件的說明。 此欄位支援HTML。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 位置]</td> 
   <td>以文字形式輸入事件的位置。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 使用此事件的預設提醒設定]</td> 
   <td>啟用此選項以使用預設提醒設定。 如果您在[!UICONTROL Reminder]欄位中設定自訂提醒，此值會設為「否」。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 提醒] </td> 
   <td> <p>新增事件提醒。 對於每個要新增的提醒，按一下<b>新增專案</b>，然後選取要提醒的方法，並定義要提醒的事件之前的時間長度（分鐘）。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 出席者]</td> 
   <td>將出席者新增至活動。 為每位出席者按一下<b>新增出席者</b>，然後輸入或對應其名稱與電子郵件地址。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 顯示為]</td> 
   <td>選取您希望檢視您行事曆的人員在此活動期間將您視為「忙碌」或「可用」。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 可見性] </td> 
   <td> <p>選取此事件的可見性。 </p> 
    <ul> 
     <li> <p><b>[!UICONTROL 預設值]</b></p> <p>事件具有您在行事曆設定中設定的可見度。</p> </li> 
     <li> <p><b>[!UICONTROL Public]</b></p> <p>與該行事曆共用之任何人都可以看見此事件。</p> </li> 
     <li> <p><b>[!UICONTROL Private]</b></p> <p>只有與會者可看見此活動。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 傳送有關事件建立的通知]</td> 
   <td> <p>選取是否將建立新事件的通知傳送給所有來賓、非[!DNL Google Calendar]來賓，或不要傳送給任何人。</p> <p>提示：我們建議僅在移轉使用案例中使用[!UICONTROL 無]選項。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 來賓可以修改事件]</td> 
   <td> <p>如果您希望來賓能夠修改此事件，請啟用此選項。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 遞回]</td> 
   <td>新增您要套用至此事件的任何遞回規則。 每個規則都需要有[!UICONTROL RRULE]、[!UICONTROL EXRULE]、[!UICONTROL RDATE]和[!UICONTROL EXDATE]行的清單，才能處理週期性事件。 請注意，此欄位中不允許有[!UICONTROL DTSTART]和[!UICONTROL DTEND]行；事件的開始和結束時間是在開始和結束欄位中指定。 單一事件或週期性事件的例項會省略此欄位。 如需詳細資訊，請參閱<a href="https://tools.ietf.org/html/rfc5545#section-3.8.5">RFC5545</a>。</td> 
  </tr>

</tbody> 
</table>

### 迭代器

#### 重複附件

此動作模組會逐一檢視事件的附件，並將每個附件輸出到單獨的套件組合中。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source模組] </td> 
   <td> 在此案例中選取模組，該模組會輸出包含您要疊代之附件的事件。 </td> 
  </tr> 
 </tbody> 
</table>

#### 反複傳送出席者

此動作模組針對某個活動逐一檢視與會者，並將每個與會者輸出為單獨的組合。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Source模組] </td> 
   <td> 在此情境中選取模組，該模組會輸出包含您要疊代之出席者的事件。 </td> 
  </tr> 
 </tbody> 
</table>





## 在事件之前觸發案例

您可以在事件之前的指定時間觸發案例，並透過標準[!DNL Google Calendar]電子郵件提醒和[!UICONTROL Webhook] >[!UICONTROL 自訂mailhook]模組提供協助。

1. 使用[!UICONTROL Google行事曆] >[!UICONTROL 更新活動]模組將電子郵件提醒新增至您的活動：

   ![在事件之前觸發情境](/help/workfront-fusion/references/apps-and-modules/assets/trigger-scen-before-event-350x209.png)

1. 從[!UICONTROL Webhook] >[!UICONTROL 自訂mailhook]模組開始建立新情境。

   1. 複製mailhook的電子郵件地址。
   1. 儲存情境並執行情境。

1. 在[!DNL Gmail]中，將[!DNL Google Calendar]電子郵件提醒重新導向至mailhook的電子郵件地址：

   1. 開啟您的&#x200B;**[!UICONTROL [!DNL Gmail]設定]**。
   1. 開啟&#x200B;**[!UICONTROL 轉送和POP/IMAP]**&#x200B;標籤。
   1. 按一下&#x200B;**[!UICONTROL 新增轉寄地址].**
   1. 貼上複製的郵件鉤子的電子郵件地址，按&#x200B;**[!UICONTROL 下一步]**，在快顯視窗中按&#x200B;**[!UICONTROL 繼續]**&#x200B;進行確認，然後按一下&#x200B;**[!UICONTROL 確定]**。

   1. 在Workfront Fusion中，切換至應透過接收確認電子郵件來完成執行的新情境。
   1. 按一下模組上方的泡泡圖示，檢查模組的輸出。
   1. 展開`Text`專案並複製確認代碼：

      ![確認代碼](/help/workfront-fusion/references/apps-and-modules/assets/confirmation-code-350x252.png)

   1. 在Gmail中，將確認代碼貼到編輯方塊中，然後按一下&#x200B;**[!UICONTROL 驗證]**：

      ![貼上程式碼](/help/workfront-fusion/references/apps-and-modules/assets/paste-code-350x46.png)

   1. 開啟&#x200B;**[!UICONTROL 篩選器和封鎖的地址]**&#x200B;索引標籤。
   1. 按一下&#x200B;**[!UICONTROL 建立新篩選器]**。
   1. 為來自`     calendar-notification@google.com`的所有電子郵件設定篩選器，然後按一下&#x200B;**[!UICONTROL 建立篩選器]**：
   1. 選取&#x200B;**[!UICONTROL 將其轉寄至]**，並從清單中選擇Mailhook的電子郵件地址。
   1. 按一下&#x200B;**[!UICONTROL 建立篩選器]**&#x200B;以建立篩選器。

1. （選擇性）在Workfront Fusion中，在[!UICONTROL Webhooks] >[!UICONTROL 自訂mailhook]模組之後新增[!UICONTROL 文字剖析器] > [!UICONTROL 符合模式]模組，以剖析電子郵件的HTML程式碼，取得您所需的任何資訊。

   例如，您可以依照以下方式設定模組，以取得事件的ID：

   *模式*： `<meta itemprop="eventId/googleCalendar" content="(?<evenitID>.*?)"/>`

   *文字*：從`HTML content`Webhook[!UICONTROL &#x200B; >]自訂mailhook[!UICONTROL 模組輸出的]專案。

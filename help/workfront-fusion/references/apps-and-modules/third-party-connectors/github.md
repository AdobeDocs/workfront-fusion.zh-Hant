---
title: github模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用GitHub的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: d9e6c26c-8770-40bc-a83a-8c05f86e4a3f
source-git-commit: 363df430b8cc3133961e77d3bd5934490440314c
workflow-type: tm+mt
source-wordcount: '1959'
ht-degree: 0%

---

# [!DNL GitHub]模組

在Adobe Workfront Fusion情境中，您可以自動執行使用[!UICONTROL GitHub]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!DNL GitHub]模組，您必須有[!DNL GitHub]帳戶。

## 將[!DNL GitHub]連線至Workfront Fusion

如需有關將您的[!DNL GitHub]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) — 基本指示

## [!DNL GitHub]模組及其欄位。

當您設定[!DNL GitHub]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL GitHub]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)

### 觸發程序

* [[!UICONTROL 觀看註解]](#watch-comments)
* [[!UICONTROL 監視分支]](#watch-forks)
* [[!UICONTROL 觀看問題]](#watch-issues)
* [[!UICONTROL 觀看提取要求]](#watch-pull-requests)
* [[!UICONTROL 監視存放庫]](#watch-repositories)

#### [!UICONTROL 觀看註解]

此觸發模組會在新增評論或修改現有評論時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取您要監看的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 問題編號]</td> 
   <td>如果您只想搜尋針對特定問題所做的新註解，以限制搜尋，請輸入問題編號。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回問題數上限]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內傳回的最大評論數量。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 手錶]</td> 
   <td>選取您是要只觀看新註解，還是要觀看註解和所有變更。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 監視分支]

此觸發模組會在建立新復本時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取您要監視分支的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回分叉的最大數量]</td> 
    <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大分叉數目。</td>
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看問題]

此觸發模組會在新增問題或修改現有問題時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 我要觀看]</td> 
   <td>選取您要監視與此帳戶關聯的所有存放庫，還是隻想監視一個存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>如果您只選擇在一個存放庫監視問題，請選取您要監視的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回問題數上限]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內傳回的問題數上限。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 手錶]</td> 
   <td>選擇您是隻想監視新問題，還是隻想監視新問題和所有變更。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 篩選器]</td> 
   <td> <p>您可以透過與問題的關聯方式來篩選您要關注的問題。</p> 
    <ul> 
     <li>[!UICONTROL 所有問題]</li> 
     <li>[!UICONTROL 僅指派給我的問題]</li> 
     <li>[!UICONTROL 僅限我建立的問題]</li> 
     <li>[!UICONTROL 僅問題提及我]</li> 
     <li>[!UICONTROL 僅限我訂閱更新的問題]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 狀態]</td> 
   <td>選擇您是隻想監視未完成的問題，還是隻想監視關閉的問題。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td>針對您要新增的每個標籤，按一下[新增專案] <b>並輸入標籤。 </b>模組會監視這些標籤的問題。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看提取要求]

新增新的提取請求或修改現有的提取請求時，此模組就會觸發。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取您要監看的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回的提取要求數上限]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內傳回的提取要求數上限。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 狀態]</td> 
   <td>選取您是否要觀看&lbrack;！UICONTROL僅開啟提取請求、[!UICONTROL 僅關閉提取請求]或所有提取請求。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 手錶]</td> 
   <td>選取您是否只想監視新的提取請求，或想監視新的提取請求和所有變更。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 監視存放庫]

此觸發模組會在建立或修改存放庫時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回存放庫的最大數量]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內傳回的最大存放庫數量。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 手錶]</td> 
   <td>選取您要監視新存放庫和所有變更，還是隻監視新存放庫。</td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 新增受指派人]](#add-assignees)
* [[!UICONTROL 新增標籤至問題]](#add-labels-to-an-issue)
* [[!UICONTROL 建立註解]](#create-a-comment)
* [[!UICONTROL 建立問題]](#create-an-issue)
* [[!UICONTROL 取得問題]](#get-an-issue)
* [[!UICONTROL 列出註解]](#list-comments)
* [[!UICONTROL 從問題中移除標籤]](#remove-a-label-from-an-issue)
* [[!UICONTROL 移除被指定者]](#remove-assignees)
* [[!UICONTROL 搜尋問題]](#search-for-an-issue)
* [[!UICONTROL 更新問題]](#update-an-issue)

#### [!UICONTROL 新增受指派人]

此模組會將受指派人新增至指定問題

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取包含您要新增受指派人之問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 受託人]</td> 
   <td>選取您要指派給問題的人員。 可用的受指派人包括擁有存放庫寫入許可權的任何人，以及擁有存放庫讀取許可權的組織成員。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要新增受指派人之問題的問題編號。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 新增標籤至問題]

此模組向問題新增標籤。 標籤是在存放庫層級上定義，而且只能由擁有存放庫寫入許可權的人建立。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取包含您要新增標籤之問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td>選取您要新增至問題的標籤。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要新增標籤的問題編號。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立註解]

此模組會針對指定問題建立評論。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取包含您要建立註解之問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要建立評論之問題的問題編號。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>輸入或對應註解的內容。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立問題]

此模組會在選取的存放庫中建立新問題。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取您想要建立問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 受託人]</td> 
   <td>選取您要指派給問題的人員。 可用的受指派人包括擁有存放庫寫入許可權的任何人，以及擁有存放庫讀取許可權的組織成員。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 里程碑]</td> 
   <td>選取您要與新問題關聯的里程碑。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td>選取您要套用至新問題的任何標籤。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標題]</td> 
   <td>輸入或對應新問題的標題。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>輸入或對應問題本文，例如說明或其他資訊</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得問題]

此模組會擷取有關指定問題的詳細資料

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取包含您要擷取其詳細資訊之問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要擷取詳細資訊的問題編號。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出註解]

此模組會列出指定問題的所有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取包含您要列出其註釋之問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要列出註解之問題的問題編號。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 始自]</td> 
   <td>模組將傳回在此日期之後建立的註解。 如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回評論的最大數量]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內傳回的最大評論數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 從問題中移除標籤]

此模組會從問題中移除單一標籤。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取包含您要移除其標籤之問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td>選取您要從問題中移除的標籤。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要移除標籤之問題的問題編號。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 移除被指定者]

此模組會從指定的問題中移除受指派人。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取包含您要移除被指定者之問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 受託人]</td> 
   <td>選取您要從問題中移除的人員。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要移除受指派人之問題的問題編號。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋問題]

此模組會搜尋符合您搜尋條件的問題。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回問題數上限]</td> 
   <td> <p> 設定Workfront Fusion在一個週期內傳回的問題數上限。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 排序依據]</td> 
   <td> <p>選取您要如何排序搜尋結果。</p> 
    <ul> 
     <li> <p>[!UICONTROL 最佳符合] </p> </li> 
     <li>[!UICONTROL 建立日期]</li> 
     <li>[!UICONTROL 更新日期]</li> 
     <li>[!UICONTROL 評論數]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 排序方向]</td> 
   <td> <p>選取升序或降序。 </p> <p>對於日期，選取<strong>[!UICONTROL 降序]</strong>將會先傳回最近的日期。 </p> <p>若為[!UICONTROL 評論數]，選取<strong>[!UICONTROL 降序]</strong>將會先傳回評論數最多的問題。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query]</td> 
   <td>輸入或對應您的搜尋查詢。 如需搜尋選項的詳細說明，請參閱<a href="https://docs.github.com/en/github/searching-for-information-on-github/searching-issues-and-pull-requests">說明網站上的</a>搜尋問題和提取要求[!DNL GitHub]。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新問題]

此模組會更新現有的[!DNL GitHub]問題。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL GitHub]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 存放庫]</td> 
   <td>選取您要更新問題的存放庫。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 受託人]</td> 
   <td>選取您要指派給問題的人員。 可用的受指派人包括擁有存放庫寫入許可權的任何人，以及擁有存放庫讀取許可權的組織成員。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 里程碑]</td> 
   <td>選取您要與問題關聯的里程碑。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標籤]</td> 
   <td>選取您要套用至問題的任何標籤。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 編號]</td> 
   <td>輸入或對應您要更新之問題的問題編號。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 狀態]</td> 
   <td>選取您要將問題更新到的狀態。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標題]</td> 
   <td>輸入或對應問題的新標題。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td>輸入或對應問題的新內文，例如說明或其他資訊</td> 
  </tr> 
 </tbody> 
</table>

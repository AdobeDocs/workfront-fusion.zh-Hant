---
title: 格線模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Trello的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 5df5cd2b-ad4c-4a02-9d0c-7cee35232f93
source-git-commit: 899fc717f5107433d6f1aea31c4d079243a85822
workflow-type: tm+mt
source-wordcount: '5213'
ht-degree: 0%

---

# [!UICONTROL 格線]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!UICONTROL Trello]的工作流程，並將其連線到多個協力廠商應用程式和服務。

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

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL Trello]模組，您必須有[!UICONTROL Trello]帳戶。

## Trello API資訊

Trello聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://api.trello.com/1</td>
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v4.12.37</td> 
  </tr>
 </tbody> 
 </table>

## 將[!UICONTROL Trello]連線至[!DNL Workfront Fusion]

如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱[建立與 [!DNL Adobe Workfront Fusion] 的連線 — 基本指示](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## [!UICONTROL 格線]模組及其欄位

當您設定[!UICONTROL Trello]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位之外，根據您在應用程式或服務中的存取層級等因素，可能會顯示其他[!UICONTROL 格線]欄位。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [展示板](#boards)
* [清單](#lists)
* [卡片](#cards)
* [成員](#members)
* [檢查清單](#checklists)
* [標籤](#labels)
* [評論](#comments)

### 展示板

+++ **[!UICONTROL 封存或取消封存展示板]**

此動作模組會關閉（封存）或重新開啟（取消封存）您指定的展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL展示板ID]</td> 
   <td> <p> 輸入或對應您要關閉或重新開啟之展示板的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL封存或取消封存]</td> 
   <td> <p> 選取您要關閉（封存）或重新開啟（取消封存）展示板。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 指派成員給討論區]**

此動作模組會將成員指派給您指定的展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL展示板ID]</td> 
   <td> <p> 選取您要新增成員的展示板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL電子郵件地址]</td> 
   <td> <p> 輸入或對應您要新增至展示板的成員電子郵件地址。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL成員型別]</p> </td> 
   <td> <p>選取您希望新成員成為的成員型別。</p> 
    <ul> 
     <li><strong>[！UICONTROL管理員]</strong>：展示板管理員可以在展示板上執行任何展示板動作。</li> 
     <li><strong>[！UICONTROL Normal]</strong>：一般成員只是展示板的成員。</li> 
     <li><strong>[！UICONTROL觀察者]</strong>：觀察者是具有展示板唯讀存取許可權的成員。 <br>觀察者僅適用於具有[！UICONTROL Trello Business Class]的團隊。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL全名]</td> 
   <td> <p> 輸入或對應您要新增至展示板的使用者全名。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 建立展示板]**

此動作模組會使用選取的設定建立新展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
   <td> <p>輸入或對映新展示板的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL說明]</td> 
   <td> <p>視需要輸入或對應展示板說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL組織ID]</p> </td> 
   <td> <p>輸入或對映組織的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL許可權層級]</p> </td> 
   <td> <p>面板的每個許可權層級都有不同的投票和註解規則。 例如，如果您的展示板是[！UICONTROL Private]，而您將投票和註解規則設為[！UICONTROL All]，則會收到錯誤。 </p> <p>每個許可權層級的投票和註解僅限下列群組：</p> 
    <ul> 
     <li><strong>[！UICONTROL Private]</strong>： 
      成員、成員和觀察者</li> 
     <li><strong>[！UICONTROL，針對組織]</strong>： 
      成員、成員和觀察員、組織成員</li> 
     <li><strong>[！UICONTROL Public]</strong>： 
      成員、成員和觀察者、組織成員、全部</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Voting]</p> </td> 
   <td> <p>選取選項，指定可以投票給此展示板的對象。 如需許可權層級的投票限制，請參閱[！UICONTROL許可權層級]欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL註解]</p> </td> 
   <td> <p>選取選項，指定可以對此展示板的卡片加上註解的人。 如需許可權等級的限制，請參閱[！UICONTROL許可權等級]欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL邀請]</p> </td> 
   <td> <p>選取可以邀請其他人加入此討論區的人員。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL自我聯結]</p> </td> 
   <td> <p>選取專案團隊成員可以自己加入討論區，還是必須邀請他們。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL預設標籤]</p> </td> 
   <td> <p>選取是否使用新展示板的預設標籤集。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL預設清單]</p> </td> 
   <td> <p>選擇是否將預設清單集新增到展示板([！UICONTROL To Do]、[！UICONTROL Doing]、[！UICONTROL Done])。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL展示板來源ID]</p> </td> 
   <td> <p>選取或對應您要複製到新展示板中的展示板ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL卡蓋]</p> </td> 
   <td> <p>如果要啟用主機板的卡蓋，請選取<strong>[！UICONTROL是]</strong>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL背景]</p> </td> 
   <td> <p>選取背景或自訂背景的顏色。</p> <p>注意：自訂背景僅適用於[！UICONTROL Trello Gold and Business Class]訂閱者。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL背景ID]</td> 
   <td> <p> 如果您已在[！UICONTROL Background]欄位中選取使用自訂背景，請輸入或對應您要使用之背景的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL卡過時]</p> </td> 
   <td> <p>在兩種卡片老化模式之間選取。 </p> 
    <ul> 
     <li><strong>[！UICONTROL海盜模式]</strong>：卡片隨著年齡增長，會撕裂、變黃，像舊海盜地圖一樣破裂。</li> 
     <li><strong>[！UICONTROL一般模式]</strong>：卡片隨著年齡增長而逐漸變透明。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 編輯展示板]**

此動作模組會編輯現有展示板的設定。

>[!SUCCESS]
>
><table style="table-layout:auto">
<col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL展示板ID]</p> </td> 
   <td> <p>輸入或對應您要模組建立之展示板的唯一[！UICONTROL Trello] ID。 您可以使用其他模組（例如「看板」模組）來擷取看板ID</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/watch-boards.png"> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新名稱]</td> 
   <td> <p> 輸入或對映展示板的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新說明]</td> 
   <td> <p> 輸入或對映新的展示板說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL組織ID]</p> </td> 
   <td> <p>輸入或對應您要模組編輯之展示板的唯一[！UICONTROL Trello] ID。  </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訂閱] </td> 
   <td> <p>選取選項，以指定擁有此模組使用之連線的使用者是否已訂閱展示板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL許可權層級]</p> </td> 
   <td> <p>面板的每個許可權層級都有不同的投票和註解規則。 例如：如果您的展示板是[！UICONTROL Private]，而您將投票和註解規則設為[！UICONTROL All]，則會收到錯誤。 </p> <p>每個許可權層級的投票和註解僅限下列群組：</p> 
    <ul> 
     <li><strong>[！UICONTROL Private]</strong>： 
      成員、成員和觀察者</li> 
     <li><strong>[！UICONTROL，針對組織]</strong>： 
      成員、成員和觀察員、組織成員</li> 
     <li><strong>[！UICONTROL Public]</strong>： 
      成員、成員和觀察者、組織成員、全部</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Voting]</p> </td> 
   <td> <p>選取選項，指定可以投票給此展示板的對象。 如需許可權層級的投票限制，請參閱[！UICONTROL許可權層級]欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL註解]</p> </td> 
   <td> <p>選取選項，指定可以對此展示板的卡片加上註解的人。 如需許可權等級的限制，請參閱[！UICONTROL許可權等級]欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL邀請] </td> 
   <td> <p>選取可以邀請其他人加入此討論區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL自我聯結]</td> 
   <td> <p> 選取專案團隊成員可以自己加入討論區，還是必須邀請他們。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL卡蓋]</td> 
   <td> <p> 選取是否應該在此展示板上顯示卡片封面。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL背景] </td> 
   <td> <p>選取背景或自訂背景的顏色。</p> <p>注意：自訂背景僅適用於[！UICONTROL Trello Gold and Business Class]訂閱者。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL背景ID]</td> 
   <td> <p> 如果您已在[！UICONTROL Background]欄位中選取使用自訂背景，請輸入或對應您要使用之背景的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL卡過時]</p> </td> 
   <td> <p>在兩種卡片老化模式之間選取。 </p> 
    <ul> 
     <li><strong>[！UICONTROL海盜模式]</strong>：卡片隨著年齡增長，會撕裂、變黃，像舊海盜地圖一樣破裂。</li> 
     <li><strong>[！UICONTROL一般模式]</strong>：卡片隨著年齡增長而逐漸變透明。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL日曆摘要已啟用]</td> 
   <td> <p> 選取是否啟用行事曆摘要。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL &lt;Color&gt;標簽名稱]</td> 
   <td> <p> 指定名稱給所需的顏色標籤。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL封存] </td> 
   <td> <p>選取選項以指示是否要封存（關閉）展示板。 </p> </td> 
  </tr> 
 </tbody> 
</table>


+++

+++ **[!UICONTROL 取得展示板]**

此動作模組會擷取展示板的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL展示板ID]</p> </td> 
   <td> <p>輸入或對應您要擷取相關資訊之展示板的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!DNL Search for Boards]**

此搜尋模組會擷取您指定之主機板的相關資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Query] </td> 
   <td> <p>輸入或對應您要取得相關資訊之面板的名稱（或名稱的一部分）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回展示板的最大數量]</td> 
   <td> <p> 輸入在一個執行週期內板[!DNL Workfront Fusion]將傳回的最大數量。 此值必須小於或等於1000。</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Partial] </p> </td> 
   <td> <p>依預設，此模組會搜尋成員內容，以找出與查詢中每個字完全相符的內容。 啟用[！UICONTROL Partial]時，模組會尋找以查詢中任何字開頭的內容。</p> <p> 例如，如果您使用「開發」一詞來尋找標題為「我的開發狀態報告」的展示板，依預設，您需要搜尋整個單詞。 如果您已啟用[！UICONTROL Partial]，則可以搜尋「dev」，但無法搜尋「velopment」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Boards] </td> 
   <td> <p>輸入「我的」，或對應以逗號分隔的展示板ID清單。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 從展示板取消指派成員]**

此動作模組會從展示板移除成員。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL展示板ID]</td> 
   <td> <p> 輸入（對應或選取）您要移除使用者的展示板識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL成員] </td> 
   <td> <p>選取要從展示板移除的成員。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 看板]**

此觸發模組在新版板加入後開始一個案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大版面數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 清單

+++ **[!UICONTROL 建立清單]**

此動作模組會在您指定的展示板上建立清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL展示板ID]</td> 
   <td> <p> 輸入或對應您要建立清單之展示板的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
   <td> <p>輸入或對應新清單的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL位置] </td> 
   <td> <p>選取您要將清單新增到卡片頂端還是將其附加到卡片底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL複製清單]</td> 
   <td> <p> 如果您要複製清單，請選取要如何輸入要複製的清單ID。</p> 
    <ul> 
     <li> <p><strong>手動輸入</strong> </p> <p>在<strong>[！UICONTROL清單識別碼]</strong>欄位中，輸入或對應您要複製的清單識別碼。<br></p> </li> 
     <li> <p><strong>選取</strong> </p> <p>選取包含要複製清單的展示板，然後選取清單。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 編輯清單]**

此動作模組會編輯現有清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL清單ID]</td> 
   <td> <p> 輸入或對應您要更新的清單ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
   <td> <p>輸入或對映清單的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL展示板ID]</td> 
   <td> <p> 對應或選取您要移動清單的展示板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL位置] </td> 
   <td> <p>選取您要將清單新增到卡片頂端還是將其附加到卡片底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL已訂閱]</td> 
   <td> <p>如果您想要將作用中成員訂閱至清單，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取得清單]**

此動作模組會擷取有關特定清單的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL清單ID]</p> </td> 
   <td> <p>輸入或對應您要擷取相關資訊之清單的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 觀看卡片移至清單]**

將卡片移至特定清單時，此觸發模組會啟動。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Board]</td> 
   <td>選取包含您要觀看卡片清單的展示板。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL清單]</td> 
   <td>選取您要觀看卡片的清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 卡片

+++ **[!UICONTROL 新增附件]**

此動作模組會將附件新增至選取的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID]</td> 
   <td> <p> 選取您要如何輸入要新增附件的卡片ID。</p> 
    <ul> 
     <li> <p><strong>手動輸入</strong> </p> <p>在<strong>[！UICONTROL卡片識別碼]</strong>欄位中，輸入或對應您要新增附件的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要新增附件的卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL附件型別]</p> </td> 
   <td> <p>選取您要直接上傳檔案，或提供檔案的URL。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL檔案]</strong> </p> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
     <li> <p><strong>[！UICONTROL URL]</strong> </p> <p>輸入檔案的URL，並提供附件的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 封存或取消封存卡片]**

此動作模組會封存卡片或將卡片傳回展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL卡片ID]</td> 
   <td> <p> 輸入或對應您要封存或傳回展示板的卡片ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL封存或取消封存]</td> 
   <td> <p> 選取您要關閉卡片（封存）還是將其傳回展示板（取消封存）。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 建立卡片]**

此動作模組會在選取的清單中建立卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入清單ID]</td> 
   <td> <p> 選取您要如何輸入要新增卡片之清單的ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL清單識別碼]</strong>欄位中，輸入或對應您要新增卡片之清單的識別碼。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要新增卡片之清單的展示板，然後選取清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL標籤] </td> 
   <td> <p>針對您想要新增至卡片的每個標籤，按一下<b>新增專案</b>並輸入標籤識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL成員]</td> 
   <td>針對您想要新增至卡片的每個成員，按一下<b>新增專案</b>並輸入成員的識別碼。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
   <td> <p>輸入新卡的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL說明]</p> </td> 
   <td> <p>輸入卡片的說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL位置] </td> 
   <td> <p>選擇您要將卡片新增到清單頂部或將卡片附加到清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL到期日期]</td> 
   <td> <p> 輸入卡片的到期日。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL到期完成]</td> 
   <td> <p> 啟用此選項以在到期日將卡片標示為完成。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL檔案URL]</td> 
   <td> <p>輸入或對應您要新增為卡片附件的檔案URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Source檔案]</p> </td> 
   <td> <p>輸入或對應您要新增為卡片附件的檔案資訊。 從先前的模組中選取檔案，或對應檔案名稱和資料</p> 
     <p>注意：每個附件有10 MB的檔案上傳限制。 但是，[！UICONTROL Business Class]和[！UICONTROL Trello Gold]成員的每個附件有250 MB的檔案上傳限制。</p> 
     </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL複製卡]</td> 
   <td> <p> 如果您要建立新卡片作為現有卡片的復本，請選取要如何輸入您要複製的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL卡片識別碼]</strong>欄位中，輸入或對應您要複製的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要複製卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 編輯卡片]**

此動作模組會編輯現有卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID]</td> 
   <td> <p> 選取要如何輸入您要編輯的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL卡片ID]</strong>欄位中，輸入或對應您要編輯的卡片ID。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要編輯卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新名稱]</td> 
   <td> <p>輸入或對映卡片的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL新說明]</p> </td> 
   <td> <p>輸入或對映卡片的新說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL移動卡片]</p> </td> 
   <td> <p>選取面板或面板，並列出您要移動卡片的位置。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL標籤] </td> 
   <td> <p>針對您想要新增至卡片的每個標籤，按一下<b>新增專案</b>並輸入標籤識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL位置] </td> 
   <td> <p>選擇您要將卡片新增到清單頂端，還是要將[！UICONTROL]卡片附加到清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL到期日期]</td> 
   <td> <p> 輸入卡片的到期日。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL到期完成]</td> 
   <td> <p> 啟用此選項以在到期日將卡片標示為完成。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL成員] </td> 
   <td> <p>針對您想要新增至卡片的每個成員，按一下<b>新增專案</b>，然後輸入或對應成員的識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL附件封面ID]</p> </td> 
   <td> <p>輸入或對應您要卡片用作封面的影像附件ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL訂閱] </td> 
   <td> <p>選取是否應該訂閱卡片的成員。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL封存] </td> 
   <td> <p>選取選項以指出是否要封存（關閉）卡片。 </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 取得卡片]**

此動作模組會擷取所選卡片的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL展示板ID]</td> 
   <td> <p>輸入包含您要擷取詳細資訊之卡片之展示板的ID。 這可讓您檢視展示板的自訂欄位名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID]</td> 
   <td> <p> 選取您要如何輸入要擷取詳細資訊的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL卡片ID]</strong>欄位中，輸入或對應您要擷取其詳細資訊的卡片ID。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要擷取詳細資訊之卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 搜尋卡片]**

此動作模組會傳回符合搜尋查詢的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Board] </td> 
   <td> <p>選取您要搜尋的面板。 如果未選取面板，則會搜尋所有面板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Query]</p> </td> 
   <td> <p>輸入搜尋查詢。 您可以使用以下搜尋運運算元來縮小搜尋範圍：</p> 
    <ul> 
     <li><code><strong>-operator</strong></code> <p>您可以將「 — 」新增到任何運運算元以進行負數搜尋，例如<code>[!UICONTROL -has:members]</code>以搜尋卡片，而不指派任何成員。</p> </li> 
     <li><code><strong>@name</strong></code> <p>傳回指派給成員的卡片。 您也可以使用<code>member:</code>。 使用<code>@me</code>僅包含您的卡片。</p> </li> 
     <li><code><strong>#label</strong></code> <p>傳回已標籤的卡片。 您也可以使用<code>label:</code>。 例如，<code>label:"FIX IT"</code>會傳回標籤為「FIX IT」的卡片。</p> </li> 
     <li><code><strong>board:id</strong></code> <p>傳回特定展示板中的卡片。 例如，<code>board:Trello</code>會傳回展示板名稱中有[！UICONTROL Trello]的卡片。</p> </li> 
     <li><code><strong>list:name</strong></code> <p>傳回清單中名為「name」的卡片。</p> </li> 
     <li><code><strong>has:attachments</strong></code> <p>傳回含附件的卡片。 <code>has</code>：運運算元也可以搭配其他屬性使用，例如<code>has:description</code>、<code>has:cover</code>、<code>has:members</code>或<code>has:stickers</code>。</p> </li> 
     <li><code><strong>due:day</strong></code> <p>傳回24小時內到期的卡片。 <code>due:</code>運運算元也可以搭配其他時間範圍使用，例如<code>due:week</code>、<code>due:month</code>或<code>due:overdue</code>。 您也可以搜尋特定的日期範圍。 例如，新增<code>due:14</code>到搜尋會包含未來14天到期的卡片。</p> </li> 
     <li><code><strong>created:day</strong></code> <p>傳回過去24小時內建立的卡片。 <code> created:</code>運運算元也可以搭配其他時間範圍使用，例如<code>created:week</code>或<code>created:month</code>。 您也可以搜尋特定的日期範圍。 例如，將<code>created:14</code>新增至搜尋會包含過去14天內建立的卡片。</p> </li> 
     <li><code><strong>edited:day</strong></code> <p>傳回過去24小時內編輯的卡片。 <code>edited:</code>運運算元也可以搭配其他時間範圍使用，例如<code>edited:week</code>或<code>edited:month</code>。 您也可以搜尋特定的日期範圍。 例如，將<code>edited:21</code>新增至搜尋會包含過去21天內編輯的卡片。</p> </li> 
     <li><code><strong>description:</strong>, <strong>checklist:</strong>, <strong>comment:</strong>, and <strong>name:</strong></code> <p>傳回符合卡片說明、核取清單、註解或名稱文字的卡片。 例如，<code>comment:"FIX IT"</code>會在註解中傳回含有「FIX IT」的卡片。</p> </li> 
     <li><code><strong>is:open</strong> and <strong>is:archived</strong></code> <p>傳回已開啟或封存的卡片。 若兩者皆未指定，則[！UICONTROL Trello]會傳回這兩種型別。</p> </li> 
     <li><code><strong>is:starred</strong> </code> <p>僅包含星形主機板上的卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回卡片的最大數量]</td> 
   <td> <p> 輸入或對應您希望[!DNL Workfront Fusion]在一個執行週期內傳回的卡片數目上限。 此值必須小於或等於1000。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Partial] </td> 
   <td> <p>依預設，此模組會搜尋成員內容，以找出與查詢中每個字完全相符的內容。 啟用[！UICONTROL Partial]時，模組會尋找以查詢中任何字開頭的內容。</p> <p> 例如，如果您使用「開發」一詞來尋找標題為「我的開發狀態報告」的展示板，依預設，您需要搜尋整個單詞。 如果您已啟用[！UICONTROL Partial]，則可以搜尋「dev」，但無法搜尋「velopment」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL卡片] </td> 
   <td> <p>若要搜尋特定卡片，請按一下[新增專案] <b>並新增卡片識別碼。</b></p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 看卡片]**

此觸發模組會在新增卡片時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Watched物件]</td> 
   <td> <p>選取您要觀看卡片的位置。</p> 
    <ul> 
     <li><strong>[！UICONTROL所有卡片]</strong> </li> 
     <li> <p>特定主機板上的<strong>卡片</strong> </p> <p>選取您要觀看卡片的展示板</p> </li> 
     <li> <p><strong>[！UICONTROL卡片位於特定清單]</strong> </p> <p>選取包含您要觀看卡片清單的展示板，然後選取清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 成員

+++ **[!UICONTROL 新增成員到卡片]**

此動作模組會將指定的成員新增至指定的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL輸入卡片ID和成員ID]</p> </td> 
   <td> <p>選擇您要如何輸入卡片ID和成員ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應<strong>[！UICONTROL卡片ID]</strong>與<strong>[！UICONTROL成員ID]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要新增成員的卡片的展示板，然後選取包含卡片的清單、卡片本身以及您要新增至卡片的成員。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 指派成員給討論區]**

請參閱[!UICONTROL 展示板]下的[將成員指派給展示板](#boards)。

+++

+++ **[!UICONTROL 搜尋成員]**

此動作模組會擷取[!UICONTROL Trello]成員的資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Query] </td> 
   <td> <p>輸入您要尋找之使用者的名稱或使用者名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Partial] </td> 
   <td> <p>依預設，此模組會搜尋成員內容，以找出與查詢中每個字完全相符的內容。 啟用[！UICONTROL Partial]時，模組會尋找以查詢中任何字開頭的內容。</p> <p> 例如，如果您使用「開發」一詞來尋找標題為「我的開發狀態報告」的展示板，依預設，您需要搜尋整個單詞。 如果您已啟用[！UICONTROL Partial]，則可以搜尋「dev」，但無法搜尋「velopment」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回成員的最大數目]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 從展示板取消指派成員]**

請參閱「[!UICONTROL 面板]下的[從面板](#boards)取消指派成員」。

+++

### 檢查清單

+++ **[!UICONTROL 建立檢查清單]**

此動作模組會在選取的卡片上建立檢查清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID]</td> 
   <td> <p> 選取您要如何輸入要新增檢查清單之卡片的ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL卡片ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的識別碼。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含卡片的展示板，您要在此新增檢查清單，然後選取包含卡片的清單，然後選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
   <td> <p>輸入或對映檢查清單的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL位置] </td> 
   <td> <p>選擇您要將檢查清單新增到卡片頂端，還是要將檢查清單附加到卡片底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL輸入檢查清單ID]</p> </td> 
   <td> <p>如果您是透過複製現有的檢查清單來建立檢查清單，請輸入或對應要複製到新檢查清單中的來源檢查清單ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 建立檢查清單專案]**

此動作模組會將專案新增至特定檢查清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入檢查清單ID]</td> 
   <td> <p> 如果您要複製現有的檢查清單來建立新的檢查清單，請選取要如何輸入要新增專案的檢查清單ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL檢查清單ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的ID。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要新增檢查清單之卡片的展示板，然後選取包含卡片的清單，再選取卡片，然後選取檢查清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL專案名稱]</p> </td> 
   <td> <p>輸入或對應新專案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL位置]</p> </td> 
   <td> <p>選擇您要將專案新增到檢查清單頂端還是[！UICONTROL append]新增到清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL已核取]</p> </td> 
   <td> <p>如果您要將專案新增為已核取的專案，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 編輯檢查清單專案]**

此動作模組會編輯現有的檢查清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID與檢查清單專案ID]</td> 
   <td> <p> 選取您要如何輸入卡片ID以及您要編輯專案的檢查清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL檢查清單ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的ID。</p> <p>在<strong>[！UICONTROL檢查清單專案識別碼]</strong>欄位中，輸入或對映檢查清單識別碼。</p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要新增檢查清單之卡片的展示板，然後選取包含卡片的清單，再選取卡片，然後選取檢查清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL檢查清單ID]</td> 
   <td>選取或對應您要移動檢查清單專案的檢查清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL專案名稱]</p> </td> 
   <td> <p>輸入或對應新專案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL位置]</p> </td> 
   <td> <p>選取您要將專案新增至檢查清單頂端或附加至檢查清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL狀態]</p> </td> 
   <td> <p>選取檢查清單專案是完整或不完整。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 標籤

+++ **[!UICONTROL 新增標籤至卡片]**

此動作模組會將標籤新增至選取的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID]</td> 
   <td> <p> 選取您要如何輸入要新增檢查清單之卡片的ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL卡片ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的識別碼。 在<strong>[！UICONTROL標籤ID]</strong>欄位中，輸入或對應您要新增之標籤的識別碼。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含卡片的展示板，您要在此新增檢查清單，然後選取包含卡片的清單，然後選取卡片。 </p> <p>選取您要新增至卡片的標籤。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 評論

+++ **[!UICONTROL 在卡片中建立註解]**

此動作模組會將註解新增至選取的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID]</td> 
   <td> <p> 選取您要如何輸入要在其中新增註解的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL卡片ID]</strong>欄位中，輸入或對應您要新增註解的卡片ID。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要新增註解之卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL註解] </td> 
   <td> <p>輸入或對應您要新增至所選卡片的註解。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 在卡片中列出註解]**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入卡片ID]</td> 
   <td> <p> 選取您要如何輸入要在其中新增註解的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在<strong>[！UICONTROL卡片ID]</strong>欄位中，輸入或對應您要新增註解的卡片ID。<br></p> </li> 
     <li> <p><strong>[！UICONTROL Select]</strong> </p> <p>選取包含您要新增註解之卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回評論的最大數量]</td> 
   <td> <p> 輸入在一個執行週期內[!DNL Workfront Fusion]將傳回的最大註解數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL始自] </td> 
   <td> <p>設定建立註解的期間的開始日期。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Before] </td> 
   <td> <p>設定建立註解的期間的結束日期。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL 觀看註解]**

此觸發模組會在新增評論時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[！UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Watched物件]</td> 
   <td> <p>選取您要觀看註解的位置。</p> 
    <ul> 
     <li><strong>[！UICONTROL所有卡片]隨處</strong> </li> 
     <li> <p><strong>[！UICONTROL Board]</strong> </p> <p>選取您要觀看評論的展示板</p> </li> 
     <li> <p><strong>[！UICONTROL清單]</strong> </p> <p>選取包含您想要觀察其註解的清單的展示板，然後選取該清單。</p> </li> 
     <li><strong>[！UICONTROL卡]</strong> </li> 
     <li>選取包含您要觀看其註解之卡片的展示板，然後選取包含該卡片的清單，再選取該卡片。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大註解數。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

## [!UICONTROL 格線]物件識別碼

* [如何在 [!DNL Trello]中找到卡片的ID或短連結](#how-to-find-the-id-or-the-shortlink-of-a-card-in-trello)
* [如何在 [!DNL Trello]中尋找其他物件的ID](#how-to-find-ids-of-other-objects-in-trello)

### 如何在[!DNL Trello]中找到卡片的ID或短連結

如果您想要編輯卡片或建立新註解，您必須知道卡片的ID或其短連結。 您可以從[!UICONTROL 新卡片]觸發器的輸出取得此資訊。 開啟卡片並按一下[!UICONTROL 共用]按鈕，也可以取得卡片的短連結。 在[!UICONTROL 之後URL結尾的]連結至此卡片`https://trello.com/c/`方塊中，可以找到短連結。

![共用及更多](/help/workfront-fusion/references/apps-and-modules/assets/share-and-more-350x575.png)

### 如何在[!DNL Trello]中尋找其他物件的ID

面板、清單和註解ID只能使用觸發器取得。 [!DNL `trello.com`]網站未顯示這些ID。

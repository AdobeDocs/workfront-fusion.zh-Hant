---
title: 格線模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Trello的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 5df5cd2b-ad4c-4a02-9d0c-7cee35232f93
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '4259'
ht-degree: 0%

---

# [!UICONTROL Trello]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!UICONTROL Trello]的工作流程，並將其連線至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

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

如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱[建立連線到 [!DNL Adobe Workfront Fusion]  — 基本指示](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

## [!UICONTROL Trello]模組及其欄位

當您設定[!UICONTROL Trello]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!UICONTROL Trello]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

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

+++ **[!UICONTROL Watch Boards]**

此觸發模組在新版板加入後開始一個案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>在一個執行週期內傳回的展示板數目上限[!DNL Workfront Fusion]。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a Board]**

此動作模組會使用選取的設定建立新展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入或對映新展示板的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description]</td> 
   <td> <p>視需要輸入或對應展示板說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Organization ID]</p> </td> 
   <td> <p>輸入或對映組織的ID。 組織ID可使用其他模組來擷取，例如「觀看活動」模組。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/id-of-org.png"> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Permission level]</p> </td> 
   <td> <p>面板的每個許可權層級都有不同的投票和註解規則。 例如：如果您的展示板是[!UICONTROL Private]，而您將投票與註解規則設為[!UICONTROL All]，則會收到錯誤。 </p> <p>每個許可權層級的投票和註解僅限下列群組：</p> 
    <ul> 
     <li><strong>[!UICONTROL Private]</strong>： 
      —&gt;成員、成員和觀察者</li> 
     <li><strong>[!UICONTROL For organization]</strong>： 
      —&gt;成員、成員和觀察者、組織成員</li> 
     <li><strong>[!UICONTROL Public]</strong>： 
      —&gt;成員、成員和觀察者、組織成員、全部</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Voting]</p> </td> 
   <td> <p>選取選項，指定可以投票給此展示板的對象。 如需許可權層級的投票限制，請參閱[!UICONTROL Permission level]欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Comments]</p> </td> 
   <td> <p>選取選項，指定可以對此展示板的卡片加上註解的人。 請參閱[!UICONTROL Permission level]欄位以註解許可權層級的限制。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Invitations]</p> </td> 
   <td> <p>選取可以邀請其他人加入此討論區的人員。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Self-join]</p> </td> 
   <td> <p>選取專案團隊成員可以自己加入討論區，還是必須邀請他們。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Default labels]</p> </td> 
   <td> <p>選取是否使用新展示板的預設標籤集。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Default lists]</p> </td> 
   <td> <p>選擇是否要新增預設清單集至展示板([!UICONTROL To Do]、[!UICONTROL Doing]、[!UICONTROL Done])。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Board source ID]</p> </td> 
   <td> <p>選取或對應您要複製到新展示板中的展示板ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Card Covers]</p> </td> 
   <td> <p>若要啟用主機板的卡片蓋，請選取<strong>[!UICONTROL Yes]</strong>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Background]</p> </td> 
   <td> <p>選取背景或自訂背景的顏色。</p> <p>注意：自訂背景僅適用於[!UICONTROL Trello Gold and Business Class]位訂閱者。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Card aging]</p> </td> 
   <td> <p>在兩種卡片老化模式之間選取。 </p> 
    <ul> 
     <li><strong>[!UICONTROL Regular]</strong>：卡片隨著年齡的增長而逐漸增加透明度。 </li> 
     <li><strong>[!UICONTROL Pirate]</strong>：卡片隨著年齡增長，會撕裂、變黃和裂開，就像舊版海盜地圖一樣。</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Edit a Board]**

此動作模組會編輯現有展示板的設定。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Board ID]</p> </td> 
   <td> <p>輸入或對應您要模組建立之面板的唯一[!UICONTROL Trello] ID。 您可以使用其他模組（例如「看板」模組）來擷取看板ID</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/watch-boards.png"> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td> <p> 輸入或對映展示板的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New description]</td> 
   <td> <p> 視需要輸入或對映新的展示板說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Organization ID]</p> </td> 
   <td> <p>輸入或對應您要模組編輯之展示板的唯一[!UICONTROL Trello] ID。 您可以使用其他模組（例如[!DNL Watch Activities]模組）擷取展示板ID。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/org-id.png"> </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribe] </td> 
   <td> <p>選取一個選項，以指定是否將代理使用者訂閱到展示板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Permission level]</p> </td> 
   <td> <p>面板的每個許可權層級都有不同的投票和註解規則。 例如：如果您的展示板是[!UICONTROL Private]，而您將投票與註解規則設為[!UICONTROL All]，則會收到錯誤。 </p> <p>每個許可權層級的投票和註解僅限下列群組：</p> 
    <ul> 
     <li><strong>[!UICONTROL Private]</strong>： 
      —&gt;成員、成員和觀察者</li> 
     <li><strong>[!UICONTROL For organization]</strong>： 
      —&gt;成員、成員和觀察者、組織成員</li> 
     <li><strong>[!UICONTROL Public]</strong>： 
      —&gt;成員、成員和觀察者、組織成員、全部</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Voting]</p> </td> 
   <td> <p>選取選項，指定可以投票給此展示板的對象。 如需許可權層級的投票限制，請參閱[!UICONTROL Permission level]欄位。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Comments]</p> </td> 
   <td> <p>選取選項，指定可以對此展示板的卡片加上註解的人。 請參閱[!UICONTROL Permission level]欄位以註解許可權層級的限制。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Invitations] </td> 
   <td> <p>選取可以邀請其他人加入此討論區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Self-join]</td> 
   <td> <p> 選取專案團隊成員可以自己加入討論區，還是必須邀請他們。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Card covers]</td> 
   <td> <p> 選取是否應該在此展示板上顯示卡片封面。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background] </td> 
   <td> <p>選取背景或自訂背景的顏色。</p> <p>注意：自訂背景僅適用於[!UICONTROL Trello Gold and Business Class]位訂閱者。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Background ID]</td> 
   <td> <p> 如果您已在[!UICONTROL Background]欄位中選取使用自訂背景，請輸入或對應您要使用之背景的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Card aging]</p> </td> 
   <td> <p>在兩種卡片老化模式之間選取。 </p> 
    <ul> 
     <li><strong>[!UICONTROL Regular]</strong>：卡片隨著年齡的增長而逐漸增加透明度。 </li> 
     <li><strong>[!UICONTROL Pirate]</strong>：卡片隨著年齡增長，會撕裂、變黃和裂開，就像舊版海盜地圖一樣。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Calendar feed enabled]</td> 
   <td> <p> 選取是否啟用行事曆摘要。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL <Color> label name]</td> 
   <td> <p> 指定名稱給所需的顏色標籤。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive] </td> 
   <td> <p>選取選項以指示是否要封存（關閉）展示板。 </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a Board]**

此動作模組會擷取展示板的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Board ID]</p> </td> 
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
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query] </td> 
   <td> <p>輸入或對應您要取得相關資訊之面板的名稱（或名稱的一部分）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned boards]</td> 
   <td> <p> 輸入在一個執行週期內板[!DNL Workfront Fusion]將傳回的最大數量。 此值必須小於或等於1000。</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Partial] </p> </td> 
   <td> <p>依預設，此模組會搜尋成員內容，以找出與查詢中每個字完全相符的內容。 啟用[!UICONTROL Partial]時，模組會尋找查詢中以任何字開頭的內容。</p> <p> 例如，如果您使用「開發」一詞來尋找標題為「我的開發狀態報告」的展示板，依預設，您需要搜尋整個單詞。 如果您已啟用[!UICONTROL Partial]，則可以搜尋「dev」而非「velopment」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Boards] </td> 
   <td> <p>輸入「我的」，或對應以逗號分隔的展示板ID清單。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Archive or Unarchive a Board]**

此動作模組會關閉或重新開啟您指定的展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> 輸入或對應您要關閉或重新開啟之展示板的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive or unarchive]</td> 
   <td> <p> 選取您要關閉（封存）或重新開啟（取消封存）展示板。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Assign a Member to a Board]**

此動作模組會將成員指派給您指定的展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> 選取您要新增成員的展示板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Email address]</td> 
   <td> <p> 輸入或對應您要新增至展示板的成員電子郵件地址。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Member type]</p> </td> 
   <td> <p>選取要新增至展示板的成員型別。</p> 
    <ul> 
     <li><strong>[!UICONTROL Admin]</strong>：展示板管理員可以在展示板上執行任何展示板動作。</li> 
     <li><strong>[!UICONTROL Normal]</strong>：一般成員只是委員會成員。</li> 
     <li><strong>[!UICONTROL Observer]</strong>：觀察者是對展示板具有唯讀存取許可權的成員。 <br>觀察者僅適用於具有[!UICONTROL Trello Business Class]的團隊。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Full name]</td> 
   <td> <p> 輸入要新增至展示板的使用者全名。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Unassign a Member from a Board]**

此動作模組會從展示板移除成員。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> 輸入（對應或選取）您要移除使用者的展示板識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Member] </td> 
   <td> <p>選取要從展示板移除的成員。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 清單

+++ **[!UICONTROL Watch cards moved to a list]**

將卡片移至特定清單時，此觸發模組會啟動。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board]</td> 
   <td>選取包含您要觀看卡片清單的展示板。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List]</td> 
   <td>選取您要觀看卡片的清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>在一個執行週期內傳回的卡片數目上限[!DNL Workfront Fusion]。</p>  </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a List]**

此動作模組會在您指定的展示板上建立清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> 輸入或對應您要建立清單之展示板的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入或對應新清單的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>選取您要將清單新增到卡片頂端還是將其附加到卡片底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy list]</td> 
   <td> <p> 選取要如何輸入要複製的清單ID。</p> 
    <ul> 
     <li> <p><strong>手動輸入</strong> </p> <p>在<strong>[!UICONTROL List ID]</strong>欄位中，輸入或對應您要複製的清單識別碼。<br></p> </li> 
     <li> <p><strong>選取</strong> </p> <p>選取包含要複製清單的展示板，然後選取清單。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Edit a List]**

此動作模組會編輯現有清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL List ID]</td> 
   <td> <p> 輸入或對應您要更新的清單ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入或對映清單的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p> 對應或選取您要移動清單的展示板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>選取您要將清單新增到卡片頂端還是將其附加到卡片底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribed]</td> 
   <td> <p>如果您想要將作用中成員訂閱至清單，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a List]**

此動作模組會擷取有關特定清單的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL List ID]</p> </td> 
   <td> <p>輸入或對應您要擷取相關資訊之清單的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 卡片

+++ **[!UICONTROL Watch cards]**

此觸發模組在新增卡片時啟動。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watched object]</td> 
   <td> <p>選取您要觀看卡片的位置。</p> 
    <ul> 
     <li><strong>[!UICONTROL All cards]</strong> </li> 
     <li> <p>特定主機板上的<strong>卡片</strong> </p> <p>選取您要觀看卡片的展示板</p> </li> 
     <li> <p><strong>[!UICONTROL Cards on specific list]</strong> </p> <p>選取包含您要觀看卡片清單的展示板，然後選取清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>在一個執行週期內傳回的卡片數目上限[!DNL Workfront Fusion]。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a card]**

此動作模組會在選取的清單中建立卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a list ID]</td> 
   <td> <p> 選取您要如何輸入要新增卡片之清單的ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL List ID]</strong>欄位中，輸入或對應您要新增卡片之清單的識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含要複製清單的展示板，然後選取清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels] </td> 
   <td> <p>針對您想要新增至卡片的每個標籤，輸入標籤的ID。 例如，可以使用[!UICONTROL Retrieve Labels]模組擷取識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Members]</td> 
   <td>針對您想要新增至卡片的每個成員，輸入成員的ID。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入新卡的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Description]</p> </td> 
   <td> <p>輸入卡片的說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>選取您要將卡片新增到清單頂端，還是要將卡片[!UICONTROL append]新增到清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due date]</td> 
   <td> <p> 輸入卡片的到期日。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due complete]</td> 
   <td> <p> 啟用此選項以在到期日標籤卡片完成。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL File URL]</td> 
   <td> <p>輸入或對應您要新增為卡片附件的檔案URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Source file]</p> </td> 
   <td> <p>輸入或對應您要新增為卡片附件的檔案資訊。</p> 
    <ul> 
     <li>[!UICONTROL File name]：輸入或對應檔案名稱，包括副檔名。</li> 
     <li> 
     <p>從先前的模組中選取檔案，或對應檔案名稱和資料</p> 
     <p>注意：每個附件有10 MB的檔案上傳限制。 但是，[!UICONTROL Business Class]和[!UICONTROL Trello Gold]成員每個附件的檔案上傳限製為250 MB。</p> 
     </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Copy card]</td> 
   <td> <p> 選取要如何輸入您要複製之卡片的ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要複製的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要複製卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Edit a Card]**

此動作模組會編輯現有卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter Card ID]</td> 
   <td> <p> 選取要如何輸入您要編輯的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要編輯的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要編輯卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL New name]</td> 
   <td> <p>輸入或對映卡片的新名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL New description]</p> </td> 
   <td> <p>輸入或對映卡片的新說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Move a card]</p> </td> 
   <td> <p>選取面板或面板，並列出您要移動卡片的位置。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Labels] </td> 
   <td> <p>新增您要新增至卡片的任何標籤的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>選取您要將卡片新增到清單頂端，還是要將卡片[!UICONTROL append]新增到清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due date]</td> 
   <td> <p> 輸入卡片的到期日。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Due complete]</td> 
   <td> <p> 如果已啟用此選項，卡片會在到期日標示為完成。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Members] </td> 
   <td> <p>新增或對應您要新增至卡片的任何成員ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachment cover ID]</p> </td> 
   <td> <p>輸入或對應您要卡片用作封面的影像附件ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Subscribe] </td> 
   <td> <p>選取是否應該訂閱卡片的成員。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive] </td> 
   <td> <p>選取選項以指出是否要封存（關閉）卡片。 </p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Get a Card]**

此動作模組會擷取所選卡片的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board ID]</td> 
   <td> <p>輸入包含您要擷取詳細資訊之卡片之展示板的ID。 這可讓您檢視展示板的自訂欄位名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter card ID]</td> 
   <td> <p> 選取您要如何輸入要擷取詳細資訊的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要擷取其詳細資訊的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要擷取詳細資訊之卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Search for Cards]**

此動作模組會傳回符合搜尋查詢的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Board] </td> 
   <td> <p>選取您要搜尋的面板。 如果未選取面板，則會搜尋所有面板。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Query]</p> </td> 
   <td> <p>輸入搜尋查詢。 您可以使用以下搜尋運運算元來縮小搜尋範圍：</p> 
    <ul> 
     <li><code><strong>-operator</strong></code> <p>您可以將「 — 」新增到任何運運算元以進行負數搜尋，例如<code>[!UICONTROL -has:members]</code>以搜尋卡片，而不指派任何成員。</p> </li> 
     <li><code><strong>@name</strong></code> <p>傳回指派給成員的卡片。 您也可以使用<code>member:</code>。 使用<code>@me</code>僅包含您的卡片。</p> </li> 
     <li><code><strong>#label</strong></code> <p>傳回已標籤的卡片。 您也可以使用<code>label:</code>。 例如，<code>label:"FIX IT"</code>會傳回標籤為「FIX IT」的卡片。</p> </li> 
     <li><code><strong>board:id</strong></code> <p>傳回特定展示板中的卡片。 例如，<code>board:Trello</code>會傳回展示板名稱中包含[!UICONTROL Trello]的卡片。</p> </li> 
     <li><code><strong>list:name</strong></code> <p>傳回清單中名為「name」的卡片。</p> </li> 
     <li><code><strong>has:attachments</strong></code> <p>傳回含附件的卡片。 <code>has</code>：運運算元也可以搭配其他屬性使用，例如<code>has:description</code>、<code>has:cover</code>、<code>has:members</code>或<code>has:stickers</code>。</p> </li> 
     <li><code><strong>due:day</strong></code> <p>傳回24小時內到期的卡片。 <code>due:</code>運運算元也可以搭配其他時間範圍使用，例如<code>due:week</code>、<code>due:month</code>或<code>due:overdue</code>。 您也可以搜尋特定的日期範圍。 例如，新增<code>due:14</code>到搜尋會包含未來14天到期的卡片。</p> </li> 
     <li><code><strong>created:day</strong></code> <p>傳回過去24小時內建立的卡片。 <code> created:</code>運運算元也可以搭配其他時間範圍使用，例如<code>created:week</code>或<code>created:month</code>。 您也可以搜尋特定的日期範圍。 例如，將<code>created:14</code>新增至搜尋會包含過去14天內建立的卡片。</p> </li> 
     <li><code><strong>edited:day</strong></code> <p>傳回過去24小時內編輯的卡片。 <code>edited:</code>運運算元也可以搭配其他時間範圍使用，例如<code>edited:week</code>或<code>edited:month</code>。 您也可以搜尋特定的日期範圍。 例如，將<code>edited:21</code>新增至搜尋會包含過去21天內編輯的卡片。</p> </li> 
     <li><code><strong>description:</strong>, <strong>checklist:</strong>, <strong>comment:</strong>, and <strong>name:</strong></code> <p>傳回符合卡片說明、核取清單、註解或名稱文字的卡片。 例如，評論：「FIX IT」會在評論中傳回含有「FIX IT」的卡片。</p> </li> 
     <li><code><strong>is:open</strong> and <strong>is:archived</strong></code> <p>傳回已開啟或封存的卡片。 若兩者皆未指定，[!UICONTROL Trello]會傳回兩種型別。</p> </li> 
     <li><code><strong>is:starred</strong> </code> <p>僅包含星形主機板上的卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned cards]</td> 
   <td> <p> 在一個執行週期內傳回的卡片數目上限[!DNL Workfront Fusion]。 此值必須小於或等於1000。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Partial] </td> 
   <td> <p>依預設，此模組會搜尋成員內容，以找出與查詢中每個字完全相符的內容。 啟用[!UICONTROL Partial]時，模組會尋找查詢中以任何字開頭的內容。</p> <p> 例如，如果您使用「開發」一詞來尋找標題為「我的開發狀態報告」的展示板，依預設，您需要搜尋整個單詞。 如果您已啟用[!UICONTROL Partial]，則可以搜尋「dev」而非「velopment」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Cards] </td> 
   <td> <p>新增您要特別搜尋的任何卡片。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Archive or Unarchive a Card]**

此動作模組會封存卡片或將卡片傳回展示板。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Card ID]</td> 
   <td> <p> 輸入或對應您要封存或傳回展示板的卡片ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Archive or unarchive]</td> 
   <td> <p> 選取您要關閉卡片（封存）還是將其傳回展示板（取消封存）。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Add an Attachment]**

此動作模組會將附件新增至選取的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter card ID]</td> 
   <td> <p> 選取您要如何輸入要擷取詳細資訊的卡片ID。</p> 
    <ul> 
     <li> <p><strong>手動輸入</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要擷取其詳細資訊的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要擷取詳細資訊之卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Attachment type]</p> </td> 
   <td> <p>選取您要直接上傳檔案，或提供檔案的URL。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL File]</strong> </p> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
     <li> <p><strong>[!UICONTROL URL]</strong> </p> <p>輸入檔案的URL，並提供附件的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 成員

+++ **[!UICONTROL Assign a Member to a Board]**

請參閱[面板](#boards)下的[!UICONTROL Assign a Member to a Board]。

+++

+++ **[!UICONTROL Unassign a Member from a Board]**

請參閱[面板](#boards)下的[!UICONTROL Unassign a Member from a Board]。

+++

+++ **[!UICONTROL Add a Member to a Card]**

此動作模組會將指定的成員新增至指定的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter card ID and member ID]</p> </td> 
   <td> <p>選擇您要如何輸入卡片ID和成員ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>輸入或對應<strong>[!UICONTROL Card ID]</strong>與<strong>[!UICONTROL Member ID]</strong>。</p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要新增成員的卡片的展示板，然後選取包含卡片的清單、卡片本身以及您要新增至卡片的成員。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Search for Members]**

此動作模組會擷取[!UICONTROL Trello]成員的資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query] </td> 
   <td> <p>輸入您要尋找之使用者的全名或使用者名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Partial] </td> 
   <td> <p>依預設，此模組會搜尋成員內容，以找出與查詢中每個字完全相符的內容。 啟用[!UICONTROL Partial]時，模組會尋找查詢中以任何字開頭的內容。</p> <p> 例如，如果您使用「開發」一詞來尋找標題為「我的開發狀態報告」的展示板，依預設，您需要搜尋整個單詞。 如果您已啟用[!UICONTROL Partial]，則可以搜尋「dev」而非「velopment」。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned members]</td> 
   <td> <p> 在一個執行週期內傳回的成員數目上限[!DNL Workfront Fusion]。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 檢查清單

+++ **[!UICONTROL Create a Checklist]**

此動作模組會在選取的卡片上建立檢查清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a card ID]</td> 
   <td> <p> 選取您要如何輸入要新增檢查清單之卡片的ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的ID。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含卡片的展示板，您要在此新增檢查清單，然後選取包含卡片的清單，然後選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入或對映檢查清單的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Position] </td> 
   <td> <p>選擇您要將檢查清單新增到卡片頂端，還是要將[!UICONTROL append the]檢查清單新增到卡片底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Enter checklist ID]</p> </td> 
   <td> <p>輸入或對應您要複製到新清單中的來源檢查清單ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a Checklist Item]**

此動作模組會將專案新增至特定檢查清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter checklist ID]</td> 
   <td> <p> 選取您要如何輸入要新增專案的檢查清單ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Checklist ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的ID。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要新增檢查清單之卡片的展示板，然後選取包含卡片的清單，再選取卡片，然後選取檢查清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Item name]</p> </td> 
   <td> <p>輸入或對應新專案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Position]</p> </td> 
   <td> <p>選擇您要將專案新增到檢查清單頂端還是[!UICONTROL append]新增到清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Checked]</p> </td> 
   <td> <p>如果您要將專案新增為已核取的專案，請啟用此選項。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Edit a Checklist Item]**

此動作模組會編輯現有的檢查清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a Card ID and Checklist Item ID]</td> 
   <td> <p> 選取您要如何輸入卡片ID以及您要編輯專案的檢查清單。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Checklist ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的ID。</p> <p>在<strong>[!UICONTROL Checklist Item ID]</strong>欄位中，輸入或對映檢查清單的ID。</p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要新增檢查清單之卡片的展示板，然後選取包含卡片的清單，再選取卡片，然後選取檢查清單。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Checklist ID]</td> 
   <td>選取或對應您要移動檢查清單專案的檢查清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Item name]</p> </td> 
   <td> <p>輸入或對應新專案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Position]</p> </td> 
   <td> <p>選取您要將專案新增至檢查清單頂端或附加至檢查清單底部。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL State]</p> </td> 
   <td> <p>選取檢查清單專案是完整或不完整。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 標籤

+++ **[!UICONTROL Add a Label to a Card]**

此動作模組會將標籤新增至選取的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter card ID]</td> 
   <td> <p> 選取您要如何輸入要新增檢查清單之卡片的ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要新增檢查清單之卡片的ID。 在<strong>[!UICONTROL Label ID]</strong>欄位中，輸入或對應您要新增之標籤的識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含卡片的展示板，您要在此新增檢查清單，然後選取包含卡片的清單，然後選取卡片。 </p> <p>選取您要新增至卡片的標籤。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

+++

### 評論

+++ **[!UICONTROL Watch Comments]**

當指定位置中有新註解時，擷取註解詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Watched object]</td> 
   <td> <p>選取您要觀看註解的位置。</p> 
    <ul> 
     <li><strong>[!UICONTROL All cards]每個地方</strong> </li> 
     <li> <p><strong>[!UICONTROL Board]</strong> </p> <p>選取您要觀看評論的展示板</p> </li> 
     <li> <p><strong>[!UICONTROL List]</strong> </p> <p>選取包含您想要觀察其註解的清單的展示板，然後選取該清單。</p> </li> 
     <li><strong>[!UICONTROL Card]</strong> </li> 
     <li>選取包含您要觀看其註解之卡片的展示板，然後選取包含該卡片的清單，再選取該卡片。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>在一個執行週期內傳回的註解數目上限[!DNL Workfront Fusion]。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL Create a Comment in a Card]**

此動作模組會將註解新增至選取的卡片。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a card ID]</td> 
   <td> <p> 選取您要如何輸入要在其中新增註解的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要新增註解的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要新增註解之卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment] </td> 
   <td> <p>輸入要新增到所選卡片的註解。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

+++ **[!UICONTROL List Comments in a Card]**

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!UICONTROL Trello]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Enter a card ID]</td> 
   <td> <p> 選取您要如何輸入要在其中新增註解的卡片ID。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Enter manually]</strong> </p> <p>在<strong>[!UICONTROL Card ID]</strong>欄位中，輸入或對應您要新增註解的卡片識別碼。<br></p> </li> 
     <li> <p><strong>[!UICONTROL Select]</strong> </p> <p>選取包含您要新增註解之卡片的展示板，然後選取包含卡片的清單，再選取卡片。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Maximum number of returned comments]</td> 
   <td> <p> 輸入在一個執行週期內[!DNL Workfront Fusion]將傳回的最大註解數。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Since] </td> 
   <td> <p>設定建立註解的期間的開始日期。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Before] </td> 
   <td> <p>設定建立註解的期間的結束日期。 如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">在[!DNL Adobe Workfront Fusion]</a>中鍵入強制。</p> </td> 
  </tr> 
 </tbody> 
</table>

+++

## [!UICONTROL Trello]物件識別碼

* [如何在 [!DNL Trello]中找到卡片的ID或短連結](#how-to-find-the-id-or-the-shortlink-of-a-card-in-trello)
* [如何在 [!DNL Trello]中尋找其他物件的ID](#how-to-find-ids-of-other-objects-in-trello)

### 如何在[!DNL Trello]中找到卡片的ID或短連結

如果您想要編輯卡片或建立新註解，您必須知道卡片的ID或其短連結。 您可以從[!UICONTROL New Card]觸發器的輸出取得此資訊。 也可以透過開啟卡片並按一下[!UICONTROL Share]按鈕來取得卡片的短連結。 可以在`https://trello.com/c/`之後URL結尾的[!UICONTROL Link to this card]方塊中找到短連結。

![共用及更多](/help/workfront-fusion/references/apps-and-modules/assets/share-and-more-350x575.png)

### 如何在[!DNL Trello]中尋找其他物件的ID

面板、清單和註解ID只能使用觸發器取得。 [!DNL trello.com]網站未顯示這些ID。

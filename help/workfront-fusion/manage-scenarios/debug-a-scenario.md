---
title: 情境偵錯
description: Adobe Workfront Fusion Devtool可讓您瞭解情境並疑難排解。 Devtool將額外的面板新增至Chrome開發人員工具。 使用此偵錯工具面板，您可以檢查案例的所有手動執行、檢閱所有已執行的操作，並檢視每個已執行API呼叫的詳細資訊。 您可以檢視導致錯誤的模組、操作或單一回應，並運用該知識來調整您的案例。
author: Becky
feature: Workfront Fusion
exl-id: 34215370-27e3-4c28-8bd1-a16268900b86
TQID: 'https://experienceleague.adobe.com/7NXYVXxbQvgKnqvRUNV-ySBApe9kl-Kn57sSKCh4NLE'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '1962'
ht-degree: 5%
---
# 情境偵錯

Adobe Workfront Fusion Devtool可協助您瞭解情境並進行疑難排解。 使用Devtool，您可以檢查案例的所有手動執行、檢閱所有已執行的操作，並檢視每個已執行API呼叫的詳細資訊。 您可以檢視導致錯誤的模組、操作或單一回應，並運用該知識來調整您的案例。

>[!NOTE]
>
>在機密案例、自動執行和成功操作中，偵錯工具面板中的登入將會受到限制或無法使用。

>[!NOTE]
>
>在新版Experience中，有數個DevTool工具內建在情境編輯器中，因此您無需開啟DevTool即可使用它們：
>
>| 工具 | 在何處可找到新體驗 |
>| ---------- | ---------- |
>| 取得應用程式中繼資料 | 以滑鼠右鍵按一下模組，然後選取&#x200B;**應用程式中繼資料**。 |
>| 複製對應 | 在來源模組上按一下滑鼠右鍵，選取&#x200B;**複製對應**，然後貼到相容的模組上。 |
>| 複製篩選器 | 以滑鼠右鍵按一下篩選的連結，選取&#x200B;**複製篩選器**，然後貼到其他連結上。 |
>| 複製模組名稱 | 以滑鼠右鍵按一下模組，然後選取&#x200B;**複製模組名稱**&#x200B;或&#x200B;**貼上模組名稱**。 |
>| 交換連線 | 開啟[尋找和取代]，然後使用&#x200B;**連線**&#x200B;索引標籤。 |
>| 交換變數 | 開啟[尋找和取代]，然後使用&#x200B;**變數**&#x200B;索引標籤。 |
>| 重新對應來源 | 開啟[尋找和取代]，然後使用&#x200B;**Source**&#x200B;索引標籤。 |
>
>這些工具仍可在DevTool的&#x200B;**工具**&#x200B;標籤上取得，同時還可取得「焦點」模組、「依對應尋找模組」和Base 64。 您也可以在對應中使用`base64()`和二進位轉換函式。
>
>您也可以直接從[即時軌跡](/help/workfront-fusion/manage-scenarios/live-trail.md)及案例編輯器中的執行歷程記錄檢視要求與回應詳細資料。 如需尋找和取代的詳細資訊，請參閱[尋找和取代情境中的變數、來源和連線](/help/workfront-fusion/manage-scenarios/find-and-replace.md)。
<!-- BECKY CHECK ME: DevTool screenshots (10/27/26) show all ten tools still on the Tools tab, so this note now says the seven built-in tools are available in both places. The release notes implied only Focus a module, Find modules by mapping, and Base 64 would remain. Confirm after release whether the other seven are removed from the DevTool, and update this note and the Tools section if so.  -->
<!-- BECKY CHECK ME: note added from the 10/23/26 release notes; the DevTool is NOT being removed. This article still needs a fuller restructure (new/classic split for the seven tools, Live Trail section or separate article). Confirm the menu labels. -->

如需Fusion Devtool的影片簡介和逐步解說，請參閱

* [Fusion Development Tool](https://video.tv.adobe.com/v/3427031/){target=_blank}
* [Devtool逐步說明](https://experienceleague.adobe.com/docs/workfront-learn/tutorials-workfront/fusion/troubleshooting-and-error-handling/dev-tool-walkthrough.html?lang=en)

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
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 存取Devtool

如果您在Adobe Unified Shell中使用Fusion，或已更新至新的Fusion體驗，您可以從案例編輯器存取Devtool。

### 存取新體驗中的Devtool

1. 前往您要偵錯之情境的「情境編輯器」。

   若要尋找Scenario編輯器，請參閱[Scenario編輯器](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md)。

1. 按一下「控制項」區域中的三點圖示，然後選取&#x200B;**DevTool**。

或:

1. 前往您要偵錯之情境的「情境編輯器」。
1. 以滑鼠右鍵按一下頁面的空白區域（而不是模組）。
1. 選取&#x200B;**開啟Devtool**。

DevTool會在畫佈下方的面板中開啟。

<!-- BECKY CHECK ME: new-experience access steps from your 10/27/26 notes (three-dot menu in Controls, or right-click). Confirm the menu label ('DevTool') and the 'panel below the canvas' description, and add a screenshot. I assumed the Helper tools icon steps below apply to the classic experience only; confirm. -->

### 存取經典體驗中的Devtool

1. 按一下靠近熒幕底部的&#x200B;**協助程式工具** ![協助程式工具](assets/debugger-icon.png)圖示。

或:

1. 前往您要偵錯之情境的「情境編輯器」。

   若要尋找Scenario編輯器，請參閱[Scenario編輯器](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md)。

1. 以滑鼠右鍵按一下頁面的空白區域（而不是模組）。
1. 選取&#x200B;**開啟Devtool**。

## 使用Workfront Fusion Devtool

Workfront Fusion Devtool分為3個主要區段，另加一個說明連結。 您可以在Devtool視窗的左側面板中找到這些專案。

* [即時資料流](#live-stream)
* [案例偵錯工具](#scenario-debugger)
* [工具](#tools)
* **DevTool說明**：按一下問號圖示以開啟有關DevTool的文章。

<!-- BECKY CHECK ME: the DevTool left panel now has a fourth item, 'DevTool help' (question mark icon), per your 10/27/26 screenshots. Confirm the label, that it opens this article or another one, and whether to apply this to the classic experience too. Retake the left-panel screenshot. -->

### Live Stream

即時資料流會在您的情境中按一下「執行一次」時，顯示背景中發生的情形。

<!-- BECKY CHECK ME: HOLD: in the new experience, Live Stream shows a 'no events available' message even while a scenario is running, which may be a bug. No updates have been made to this section. Re-test after release before changing anything here. If it is intended behavior, this section may need to point to Live Trail instead. -->

1. 按一下&#x200B;**[!UICONTROL 即時資料流]**&#x200B;圖示![即時資料流圖示](assets/live-stream-icon.png)以開啟即時資料流區段。
1. 執行下列任一項作業：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <thead> 
     <tr> 
      <th>動作</th> 
      <th>指示</th> 
     </tr> 
    </thead> 
    <tbody> 
     <tr> 
      <td role="rowheader">檢視請求資訊</td> 
      <td> <p>您可以檢視情境中每個模組的下列資訊</p> 
       <ul> 
        <li> <p>請求標頭（API端點URL、http方法、呼叫請求的時間和日期、請求標頭以及查詢字串）</p> </li> 
        <li> <p>要求內文</p> </li> 
        <li> <p>回應標頭</p> </li> 
        <li> <p>回應內文</p> </li> 
       </ul> <p>若要檢視此資訊，請按一下Workfront Fusion Devtool右側面板中適當的標籤。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>依內容搜尋事件</p> </td> 
      <td> <p>在Workfront Fusion Devtool左側面板的搜尋欄位中輸入搜尋字詞，以僅顯示包含搜尋字詞的請求。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>清除請求清單 </p> </td> 
      <td> <p>按一下Devtool左面板右上角的垃圾桶圖示，清除Workfront Fusion Devtool所記錄的請求清單。 </p> </td> 
     </tr> 
     <!--
     <tr>
      <td role="rowheader"> <p>Enable Console Logging</p> </td> 
      <td> <p>Click the computer icon <img src="assets/console-computer-icon.png"> in the top-right corner of the Devtool's left panel.</p> <p>Logging in the console is enabled when the computer icon is green.</p> </td> 
     </tr>
     -->
     <tr> 
      <td role="rowheader"> <p>以原始JSON格式或cURL擷取請求</p> </td> 
      <td> 
       <ul> 
        <li> <p><strong>原始JSON</strong> </p> <p>按一下Devtool右窗格右上角的<strong>[！UICONTROL Copy RAW]</strong>。</p> </li> 
        <li> <p><strong>cURL</strong> </p> <p>按一下Devtool右窗格右上角的<strong>[！UICONTROL Copy cURL]</strong>。</p> </li> 
       </ul> </td> 
     </tr> 
    </tbody> 
   </table>

### 案例偵錯工具

>[!NOTE]
>
>若要從發生錯誤的案例中快速前往偵錯工具，您可以在模組輸出的錯誤訊息中按一下&#x200B;**「取得詳細資料」**。
>
>![在模組輸出中取得詳細資料](assets/go-to-debugger.png)

情境偵錯工具適用於較複雜的情境。 它會顯示案例執行的歷史記錄，並可讓您依據模組名稱或ID來搜尋模組。

1. 按一下&#x200B;**[!UICONTROL 情境偵錯工具]**&#x200B;圖示![偵錯工具圖示](assets/scenario-debugger-icon.png)以開啟情境偵錯工具。

   案例偵錯工具會列出您案例中的模組。 每個模組會顯示其名稱、應用程式和動作，以及具有模組ID的編號徽章。

1. （選擇性）在&#x200B;**依名稱或識別碼搜尋模組**&#x200B;欄位中輸入搜尋字詞（名稱或模組識別碼）。
1. 按一下模組名稱。

   模組最近執行的週期會列在模組清單旁。 如果模組沒有執行資料，案例偵錯工具會顯示&#x200B;**找不到結果**。

1. 展開循環，然後按一下作業。

   每個作業都會顯示是否成功，以及花費的時間長度，例如，持續時間為0毫秒的&#x200B;**作業1**。

1. 檢閱請求的詳細資料。 使用標籤來檢視：

   * **要求標頭**： API端點URL、呼叫要求時的HTTP方法以及要求標頭。
   * **要求內文**
   * **回應標頭**
   * **回應內文**

1. （選擇性）若要複製要求，請按一下[複製RAW] **或[複製cURL]**。****

<!-- BECKY CHECK ME: Scenario Debugger steps expanded from your 10/27/26 new-experience DevTool screenshots. Confirm: (1) the 'Search modules by Name or ID' label; (2) that the module list sub-labels, badge (module ID), cycle/operation layout, and 'No Result found' state are described correctly; (3) the tab names, since Response Body was partly hidden behind the Copy buttons in the screenshot; (4) whether Copy RAW and Copy cURL copy the request only or the request and response; (5) whether the classic experience's Scenario Debugger looks the same, or this needs a new/classic split. The screenshot also shows a collapsed 'Live trail' tab with an event count on the right edge of the editor; see the Live Trail article. Retake the Scenario Debugger screenshots. -->

### 工具

Workfront Fusion Devtool提供的工具可讓您更輕鬆設定情境。

1. 按一下&#x200B;**[!UICONTROL 工具]**&#x200B;圖示![主控台工具圖示](assets/console-tools-icon.png)以開啟工具。
1. （選擇性）若要尋找工具，請在&#x200B;**依名稱搜尋工具**&#x200B;欄位中輸入其名稱。
1. 選取您要使用的工具
1. 設定欄位，如下所述。
1. 按一下&#x200B;**[!UICONTROL 執行]**。

在選取工具之前，面板右側會提示您選取工具。 「工具」標籤底部的連結會帶您前往有關DevTool的文章。

<!-- BECKY CHECK ME: added from your 10/27/26 screenshots: the 'Search tool by name' field, the select-a-tool prompt, and the link to the DevTool article. Confirm the field label and link destination; retake the Tools screenshot. -->

工具及其欄位：

* [焦點模組](#focus-a-module)
* [依對應尋找模組](#find-modules-by-mapping)
* [取得應用程式中繼資料](#get-app-metadata)
* [複製對應](#copy-mapping)
* [複製篩選器](#copy-filter)
* [複製模組名稱](#copy-module-name)
* [交換連線](#swap-connection)
* [交換變數](#swap-variable)
* [基底64](#base-64)
* [重新對應Source](#remap-source)

#### [!UICONTROL 焦點模組]

依照ID開啟指定模組的設定。

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL模組ID]</td>
        <td>輸入模組的ID以開啟其設定。</td>
    </tr>
</table>

#### [!UICONTROL 依對應尋找模組]

可讓您搜尋指定字詞的模組值。 輸出包含模組ID，其中包含您搜尋的字詞。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Keyword]</td> 
   <td> <p> 輸入您要搜尋的字詞。 </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL僅使用值]</p> </td> 
   <td> <p>啟用此選項以僅搜尋模組欄位的值。</p> <p>停用此選項亦可搜尋模組欄位的名稱。</p> <p>搜尋會透過名稱和標籤引數來執行。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得應用程式中繼資料]

依應用程式的模組名稱或ID擷取應用程式的中繼資料。 例如，在您需要知道情境中使用的應用程式版本時，這很有用。

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL Source模組]</td>
        <td>選取您要擷取中繼資料的模組。</td>
    </tr>
</table>

#### [!UICONTROL 複製對應]

將值從來源模組複製到目標模組。

>[!CAUTION]
>
>請務必設定正確的來源和目標模組。 如果您選取不同型別的模組，則會刪除目標模組中的值。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source模組]</td> 
   <td> <p> 選取模組或輸入您要從中複製欄位值的模組ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL目標模組]</p> </td> 
   <td> <p>選取模組或輸入您要插入來源模組值的模組ID。</p> <p>重要：目標模組中的值將被覆寫。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 複製篩選器]

將篩選設定從來源模組複製到目標模組。

>[!NOTE]
>
>複製動作會在所選模組左側的篩選器上執行。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source模組]</td> 
   <td> <p> 選取模組或輸入您要從中複製篩選值的模組ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL目標模組]</p> </td> 
   <td> <p>選取模組或輸入要從來源模組插入篩選值之模組的ID。</p> <p>重要：目標模組中的值將被覆寫。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL Preserve Fallback Route setting]</p> </td> 
   <td> <p>來源篩選器已設定為遞補路由。 啟用此選項也可以將目標篩選器設定為遞補路由。</p> </td> 
  </tr> 
 </tbody> 
</table>


#### [!UICONTROL 複製模組名稱]

將所選模組的名稱複製到剪貼簿。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL模組] </td> 
   <td> <p>選取您要複製名稱的模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 交換連線]

在同一個應用程式的案例中，將來源模組的連線複製到每個模組。

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL Source模組]</td>
        <td>選取模組或輸入您要複製連線的模組ID。</td>
    </tr>
</table>

#### [!UICONTROL 交換變數]

搜尋情境中的指定變數，並以新變數取代。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL要尋找的變數]</td> 
   <td> <p> 從情境中的變數模組中找出您要取代的變數藥丸，並將其複製到此（[！UICONTROL要尋找的變數]）欄位。 在欄位中，它會顯示為雙大括弧。 範例：<code>&#123;&#123;5.value&#125;&#125;</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL取代為]</p> </td> 
   <td> <p>從情境中的變數模組，找出您要取代變數的變數藥丸，並將其複製到此（[！UICONTROL要尋找的變數]）欄位。 在欄位中，它會顯示為雙大括弧。 範例：<code>&#123;&#123;5.value&#125;&#125;</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL模組]</p> </td> 
   <td> <p>選取您要取代變數的變數模組。 如果未選取任何模組，則變數會在整個案例中被取代。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 基底64]

可讓您將輸入的資料編碼為Base64或解碼Base64。 部分請求會編碼為Base64。 當您想要搜尋編碼請求中的特定資料時，此工具會很有用。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL操作] </td> 
   <td> <p>選取您要將資料從[！UICONTROL Raw Data]欄位編碼為Base64，還是要將Base64解碼為Raw Data。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL原始資料]</p> </td> 
   <td> <p> 根據上面[！UICONTROL Operation]欄位中選取的選項，輸入您要編碼為Base64的資料，或如果您要解碼為原始資料，則輸入Base64。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 重新對應Source]

可讓您將對應來源從一個模組變更為另一個模組。

您必須先將要作為來源模組的模組新增至情境中的路由。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source模組] </td> 
   <td> <p> 選取您要取代的模組，作為情境中其他模組的對應來源。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL目標模組]</p> </td> 
   <td> <p>選取要作為新對應來源的模組。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL要編輯的模組]</p> </td> 
   <td> <p>如果您不想要變更整個案例中的對應，請選取您要變更其對應的模組。 </p> </td> 
  </tr> 
 </tbody> 
</table>

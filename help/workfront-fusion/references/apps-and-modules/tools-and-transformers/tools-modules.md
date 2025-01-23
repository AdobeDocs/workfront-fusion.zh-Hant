---
title: 工具
description: ' [!DNL Adobe Workfront Fusion Tools] 區段包含數個可增強您的情境的實用模組。'
author: Becky
feature: Workfront Fusion
exl-id: d9425f5b-4f4a-42da-9aca-1c1783be5fa7
source-git-commit: 757580687ff5d1617f83432952d9870bd697925e
workflow-type: tm+mt
source-wordcount: '1962'
ht-degree: 0%

---

# [!UICONTROL Tools]

[!DNL Adobe Workfront Fusion Tools]區段包含數個可增強您的情境的實用模組。

可從應用程式清單或熒幕底部的[!UICONTROL Tools]圖示![](/help/workfront-fusion/references/apps-and-modules/assets/tools-icon-small.png)取得[!UICONTROL Tools]模組。

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
   <p>不需要Workfront Fusion授權。</p>
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

## [!UICONTROL Tools]及其欄位

* [觸發程序](#triggers)
* [動作](#actions)
* [彙總](#aggregators)
* [轉換器](#transformers)

### 觸發程序

#### [!UICONTROL Basic trigger]

此模組可讓您建立自訂觸發器，並定義其輸入組合。

例如，您可以將此模組用於排程傳送至指定電子郵件地址的連絡人或任何其他清單（例如[!UICONTROL Email] >[!UICONTROL Send an Email]或[!DNL Gmail] >[!UICONTROL Send an Email]模組），或作為您想要時觸發的簡單提醒。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Bundle]</td> 
   <td> <p>新增陣列專案以建立自訂組合。 陣列由名稱 — 值配對組成。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL Get Multiple Variables]](#get-multiple-variables)
* [[!UICONTROL Get Variable]](#get-variable)
* [[!UICONTROL Increment function]](#increment-function)
* [[!UICONTROL Set Multiple Variables]](#set-multiple-variables)
* [[!UICONTROL Set Variable]](#set-variable)
* [[!UICONTROL Sleep]](#sleep)

#### [!UICONTROL Get Multiple Variables]

此模組會擷取先前由[!UICONTROL Set Variable]或[!UICONTROL Set Multiple Variables]模組建立的值。

此模組可讀取在情境中任何位置設定的變數，即使變數設定在與[!UICONTROL Get Multiple Variables]模組所在不同的路由中。 唯一的要求是[!UICONTROL Tools] > [!UICONTROL Set Variable]或[!UICONTROL Tools] > [!UICONTROL Set Multiple Variable]模組必須在[!UICONTROL Tools] > [!UICONTROL Get Multiple Variables]模組之前執行。 如需模組執行順序的詳細資訊，請參閱 [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md)中的[路由器模組。

<table style="table-layout:auto">
    <tr>
        <td>[!UICONTROL Variables]</td>
        <td>新增您想要模組取得的變數。</td>
    </tr>
    <tr>
        <td>[!UICONTROL Variable name]</td>
        <td>針對您新增的每個變數，對應您要取得之變數的名稱。</td>
    </tr>
</table>

>[!INFO]
>
>**範例：**&#x200B;下列是[!UICONTROL Set]/[!UICONTROL Get (multiple) variable(s)]模組的可能用法：
>
>* 儲存計算值以供稍後使用，即使是在不同的路由中。 當值用於多個模組且計算值的公式過於複雜時，這個用法很有用。
>* 對公式進行偵錯。 如果模組中使用的公式似乎未提供正確的結果，請複製公式並將其貼到您在相關模組之前插入的[!UICONTROL Set Variable]模組中。 在[!UICONTROL Set Variable]模組之後中斷模組連線，並執行情境。 驗證[!UICONTROL Set Variable]模組的輸出、調整或簡化公式、再次執行案例，並持續執行，直到問題解決為止。


#### [!UICONTROL Get Variable]

此模組會擷取先前由[!UICONTROL Set Variable]或[!UICONTROL Set Multiple Variables]模組建立的值。

此模組可讀取在情境中任何位置設定的變數，即使變數設定在與[!UICONTROL Get Variable]模組所在不同的路由中。 唯一的要求是[!UICONTROL Tools] > [!UICONTROL Set Variable]或[!UICONTROL Tools] > [!UICONTROL Set Multiple Variables]模組必須在[!UICONTROL Tools] > [!UICONTROL Get Variable]模組之前執行。 如需模組執行順序的詳細資訊，請參閱 [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/add-modules/router-module.md)中的[路由器模組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Variable name]</td> 
   <td> <p>對應您希望模組取得的變數名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Increment function]

此模組會傳回每個模組作業後以1為單位遞增的值。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Reset a value]</td> 
   <td> <p>選取您想要模組增加值的時機。 </p> 
    <ul> 
     <li>[!UICONTROL After one cycle]</li> 
     <li>[!UICONTROL After one scenario run]</li> 
     <li>[!UICONTROL Never]</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**範例：**
>
>此模組的用途之一，是實作任務、銷售機會、電子郵件等的「循環配置資源」指派給群組中的使用者。 演演算法會以某種合理的順序從群組選擇受指派人，通常會從清單的頂端移至底端。 當演演算法到達清單結尾時，它會將下一個指派指派給位於清單頂端的使用者，並繼續進行清單下方的指派。
>
>下列案例會在每個奇數位案例執行後向第一個收件者傳送電子郵件，並在每個偶數位案例執行後向第二個收件者傳送電子郵件。
>
>![](/help/workfront-fusion/references/apps-and-modules/assets/example-email-350x246.gif)
>
>1. 若要建立此情境：
>1. 將模組的&#x200B;**[!UICONTROL Reset a value]**&#x200B;欄位設定為「永不」。
>1. 設定奇數的路由。 使用等於`1`的模數數學函式設定此路由的篩選器：
>
>   ![](/help/workfront-fusion/references/apps-and-modules/assets/odd-350x459.png)
>
>  **附註**：別忘了將[!UICONTROL Equal to]運運算元從預設的[!UICONTROL Text]運運算元變更為[!UICONTROL Numeric]運運算元。
>
>1. 使用等於`0`的模數數學函式設定偶數值的路徑：
>
>增量函式會在每次案例執行時新增一次。 篩選器會檢查增量並根據其值採取行動，確保電子郵件平均散發。

#### [!UICONTROL Set Multiple Variables]

此模組會建立可由路由中其他模組對應的變數。 變數也可以對應到情境中任何路由的[!UICONTROL Get Variable]或[!UICONTROL Get Multiple Variables]模組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Variables]</td> 
   <td>新增您想要模組設定的變數。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable name] </td> 
   <td>針對每個變數，輸入變數名稱。 在其他模組中對應變數時，會顯示此名稱。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable value] </td> 
   <td>針對每個變數，輸入變數的值。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable lifetime] </td> 
   <td> <p>選取您想要變數維持有效期（保持相同值）的時間。</p> 
    <ul> 
     <li><strong>[!UICONTROL One cycle]</strong>：變數僅對一個週期有效。 在收到一個案例執行中的多個Webhook時很有用（更多Webhook =更多週期）。 </li> 
     <li><strong>[!UICONTROL One execution]</strong>：變數對一個案例執行有效。 一個執行可以包含一個或多個週期。</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Set Variable]

此模組會建立變數，該變數可由路由中的其他模組進行對應。 變數也可以對應到情境中任何路由的[!UICONTROL Get Variable]或[!UICONTROL Get Multiple Variables]模組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Variable name] </td> 
   <td>輸入變數名稱。 在其他模組中對應變數時，會顯示此名稱。 </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable lifetime] </td> 
   <td> <p>選取您想要變數維持有效期（保持相同值）的時間。</p> 
    <ul> 
     <li><strong>[!UICONTROL One cycle]</strong>：變數僅對一個週期有效。 在收到一個案例執行中的多個Webhook時很有用（更多Webhook =更多週期）。 </li> 
     <li><strong>[!UICONTROL One execution]</strong>：變數對一個案例執行有效。 一個執行可以包含一個或多個週期。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Variable value] </td> 
   <td>輸入或對應變數的值。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Sleep]

此模組可讓您將情境流程延遲最多300秒（5分鐘）。

例如，如果您想要降低[!DNL target]服務伺服器負載，或想在傳送大量簡訊或電子郵件時模擬人的行為，此函式就十分實用。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Delay]</p> </td> 
   <td> <p>輸入案例將暫停的秒數。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!TIP]
>
>如果您想要將流量暫停更長的一段時間，我們建議將您的案例分割為兩個案例：
>
>* 第一個案例會包含暫停前的零件。
>* 第二個案例會包含其後的零件。
>
>第一個案例最終會將所有必要資訊連同目前的時間戳記一起儲存在資料存放區中。 第二種情況會定期檢查資料存放區，找出時間戳記早於預期延遲的記錄、擷取記錄、完成資料的處理，並從資料存放區移除記錄。
>
><!--For more information on data stores, see [Data Stores in [!DNL Adobe Workfront Fusion]]().-->
>
>如需特定資料存放區模組的詳細資訊，請參閱[[!UICONTROL Data store]模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/data-store-modules.md)。

### 彙總

* [[!UICONTROL Numeric aggregator]](#numeric-aggregator)
* [[!UICONTROL Table aggregator]](#table-aggregator)
* [[!UICONTROL Text aggregator]](#text-aggregator)

#### [!UICONTROL Numeric aggregator]

此模組可讓您擷取數值，然後套用其中一個選取的函式(SUM、AVG、COUNT、MAX、MIN)，並將結果傳回一個套件組合。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>選取您要從中彙總欄位的模組。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Aggregate function]</p> </td> 
   <td> <p>選取您要用來彙總值的函式。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>定義要將彙總輸出分組依據的運算式。 此運算式可包含一或多個對應專案。 接著，會使用此運算式的值，將彙總資料分隔成群組。 每個群組會輸出一個獨立的組合，內含索引鍵（運算式）和值（彙總值）。 您可以在後續模組中使用該索引鍵作為篩選條件。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>啟用此選項可在沒有結果時停止情境。</td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Value]</p> </td> 
   <td> <p>輸入或對應您要彙總的值。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Table aggregator]

此模組會使用指定的欄和列分隔符號（可讓您建立表格），將所接收組合之所選欄位的值合併為單一組合。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>選取您要從中彙總欄位的模組。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Aggregated fields]</td> 
   <td> <p> 從上面選取的模組中選取包含要彙總至一個組合中的值的欄位。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Column separator]</p> </td> 
   <td> <p>選取或輸入將分隔結果束中欄位值欄的分隔符號型別。 如果您選取[!UICONTROL Other]，請在分隔符號欄位中輸入要用來分隔值的字元。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Row separator]</p> </td> 
   <td> <p>選取或輸入將分隔結果束中欄位值列的分隔符號型別。 如果您選取[!UICONTROL Other]，請在分隔符號欄位中輸入要用來分隔值的字元。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>定義要將彙總輸出分組依據的運算式。 此運算式可包含一或多個對應專案。 接著，彙總的資料會使用此運算式的值分隔成群組。 每個群組會輸出一個獨立的組合，內含索引鍵（運算式）和值（彙總值）。 您可以在後續模組中使用該索引鍵作為篩選條件。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>選取此選項可在沒有結果時停止情境。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Text aggregator]

此模組將來自所接收套裝的選定欄位的值合併至單一套裝。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Source module]</p> </td> 
   <td> <p>選取您要從中彙總欄位的模組。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Row separator]</p> </td> 
   <td> <p>選取或輸入將分隔結果束中欄位值列的分隔符號型別。 如果您選取[!UICONTROL Other]，請在分隔符號欄位中輸入要用來分隔值的字元。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Group by]</p> </td> 
   <td> <p>定義包含一或多個對應專案的運算式。 彙總資料會以相同運算式的值分隔在「群組」底下。 每個群組都會輸出為個別的組合，其中包含含運算式和彙總文字的索引鍵。 如此一來，您便可將索引鍵用作後續模組中的篩選條件。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Text]</td> 
   <td> <p> 輸入或對應您要模組彙總的文字。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>選取此選項可在沒有結果時停止情境。</td> 
  </tr> 
 </tbody> 
</table>

>[!INFO]
>
>**範例：**&#x200B;您可以使用文字彙總將更多值（例如客戶名稱或附註）插入單一套件組合中，並傳送包含電子郵件內文或電子郵件主旨中所有值的電子郵件。

### 轉換器

* [[!UICONTROL Compose a string]](#compose-a-string)
* [[!UICONTROL Convert the encoding of the text]](#convert-the-encoding-of-the-text)
* [[!UICONTROL Switch]](#switch)

#### [!UICONTROL Compose a string]

將任何值轉換為字串資料型別（文字）。 例如，當對應（如二進位資料）時，可讓對應更容易。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p>輸入或對應您要轉換成文字的資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Convert the encoding of the text]

將輸入的輸入文字（或二進位資料）轉換為選取的編碼。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Input data]</p> </td> 
   <td> <p>輸入或對應您要轉換的內容。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Input data codepage]</td> 
   <td> <p>選取輸入資料的編碼型別。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Output data codepage]</p> </td> 
   <td> <p>選取目標（輸出）資料的編碼型別。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Switch]

檢查輸入值，找出與提供的值清單相符的專案。 根據結果傳回輸出。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td> <p>[!UICONTROL Input]</p> </td> 
   <td> <p>輸入您要計算的運算式。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Use regular expressions to match]</td> 
   <td> <p>啟用此選項以使用規則運算式。 模組會根據規則運算式來判斷案例，而非完全相符。</p> 
    <div> 
     <p>規則運算式是一系列字元，其中每個字元都是具有特殊意義的中繼字元，或是具有常值含義的規則字元。 這些字元和中繼字元會識別可用來搜尋文字的模式。 例如，如果您想要搜尋名稱，可以設定規則運算式來搜尋由兩個以大寫字母開頭的連續字片語成的模式。 規則運算式是搜尋和處理文字的強大工具。</p> 
     <p>有關規則運算式的討論不在本文的討論範圍內。 我們建議使用下列資源：</p> 
     <ul> 
      <li>如需完整的中繼字元清單，請參閱MDN網頁檔案中的<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions">規則運算式</a>。</li> 
      <li>如需有關如何建立規則運算式的教學課程，我們建議<a href="https://regexone.com/">RegexOne</a>。</li> 
      <li>若要嘗試規則運算式，我們建議使用<a href="https://regex101.com/">規則運算式101</a>網站。 在左側面板中選取ECMAScript (JavaScript) FLAVOR 。</li> 
     </ul> 
    </div> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Cases] </td> 
   <td> <p>如果輸入包含輸入至[!UICONTROL Pattern]欄位的值，則會傳回輸入至[!UICONTROL Output]欄位的值。</p> <p>如果輸入不符合您在[!UICONTROL Pattern]欄位中設定的任何值，則會發生下列其中一種情況：</p> 
    <ul> 
     <li>傳回[!UICONTROL Else]欄位的值</li> 
     <li>如果[!UICONTROL Else]欄位中沒有值，則不會傳回任何輸出。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Else]</p> </td> 
   <td> <p>輸入當不符合案例欄位中設定的條件時傳回的值。 </p> </td> 
  </tr> 
 </tbody> 
</table>

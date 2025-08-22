---
title: 文字剖析器
description: 您可以使用「文字剖析器」工具來剖析文字，以供其他Adobe Workfront Fusion案例模組使用。 文字剖析器不需要連線。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: 885d714e-fc09-41a2-89dc-ebe29a355e43
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 0%

---

# [!UICONTROL 文字剖析器]

您可以使用[!UICONTROL 文字剖析器工具]來剖析文字，以供其他Adobe Workfront Fusion案例模組使用。 [!UICONTROL 文字剖析器]不需要連線。

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
   <p>無Workfront Fusion授權需求</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增:</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 文字剖析器API資訊

文字剖析器聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v2</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL 文字剖析器]模組及其欄位

當您設定[!UICONTROL 文字剖析器]模組時，Adobe Workfront Fusion會顯示下列欄位。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 轉換器

* [[!UICONTROL 從HTML取得元素]](#get-elements-from-html)
* [[!UICONTROL 從文字取得元素]](#get-elements-from-text)
* [[!UICONTROL HTML至文字]](#html-to-text)
* [[!UICONTROL 符合模式]](#match-pattern)
* [[!UICONTROL Replace]](#replace)

#### [!UICONTROL 從HTML取得元素]

從HTML程式碼中擷取所需的元素。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL即使模組找不到符合專案，仍繼續執行路由]</td> 
   <td> <p>啟用此選項以確保模組未傳回任何結果時不會停止案例。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL元素型別]</td> 
   <td> <p> 選取您要從HTML程式碼擷取的元素型別。 </p> 
    <ul> 
     <li>[！UICONTROL Image]</li> 
     <li>[！UICONTROL連結]</li> 
     <li>[！UICONTROL iFrame元素]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL HTML] </td> 
   <td> <p>輸入或對應您要從中擷取指定元素型別的HTML程式碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 從文字取得元素]

根據指定的模式剖析文字中的元素。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL輸入文字]</td> 
   <td> <p>輸入或對應您要剖析的文字。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL模式]</td> 
   <td> <p>選取反映您要從文字中剖析之元素的圖樣。</p> <p>若要輸入自訂規則運算式，請從清單中選取「自訂」，然後在「自訂規則運算式」欄位中輸入自訂運算式。</td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL忽略重複發生次數]</td> 
   <td> <p>核取此方塊以忽略重複出現的文字元素。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL HTML至文字]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL HTML] </td> 
   <td> <p>輸入要轉換為純文字的HTML程式碼。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL分行符號] </td> 
   <td> <p>選取新行的型別（分行符號）。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[！UICONTROL大寫標題]</p> </td> 
   <td> <p>啟用此選項可將標題標籤內的文字（如&lt;h2&gt; &lt;/h2&gt;）轉換為大寫文字。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 符合模式]

[!UICONTROL 符合模式]模組可讓您從指定文字中尋找和擷取符合搜尋模式的字串元素。 此模組使用規則運算式（也稱為regex或regexp）。

規則運算式是一系列字元，其中每個字元都是具有特殊意義的中繼字元，或是具有常值含義的規則字元。 這些字元和中繼字元會識別可用來搜尋文字的模式。 例如，如果您想要搜尋名稱，可以設定規則運算式來搜尋由兩個以大寫字母開頭的連續字片語成的模式。 規則運算式是搜尋和處理文字的強大工具。

有關規則運算式的討論不在本文的討論範圍內。 我們建議使用下列資源：

* 如需完整的中繼字元清單，請參閱MDN網頁檔案中的[規則運算式](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)。
* 如需有關如何建立規則運算式的教學課程，我們建議[RegexOne](https://regexone.com/)。
* 若要嘗試規則運算式，我們建議使用[規則運算式101](https://regex101.com/)網站。 在左側面板中選取ECMAScript (JavaScript) FLAVOR 。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL模式] </td> 
   <td> <p>輸入規則運算式模式。 </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span> <code>[+-]?(\d+(\.\d+)?|\.\d+)([eE][+-]?\d+)?</code>會擷取所提供文字中的所有數字。</p> <p>注意：  <p>此模式應該包含至少一個括弧<code>()</code>中的擷取群組。 如果模式不包含任何擷取群組，則輸出組合為空白。</p> </p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL全域符合]</td> 
   <td> <p>啟用此選項以擷取文字中的所有相符專案。 每個相符專案都會以個別的套裝輸出。 如果停用此選項，模組只會擷取第一個專案。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL區分大小寫]</td> 
   <td> <p> 啟用此選項讓此模組將文字視為區分大小寫。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Multiline] </td> 
   <td> <p>啟用此選項可確保開始和結束中繼字元（<code>^</code>和<code>$</code>）符合每行的開頭或結尾，而不只是整個輸入字串的開頭或結尾。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL單行]</td> 
   <td>啟用此選項以確保句點(.)符合新行字元(<code>\n</code>)。</td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL即使模組未傳回任何結果，仍繼續執行路由]</td> 
   <td> <p>啟用此選項以確保模組未傳回任何結果時不會停止案例。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Text] </td> 
   <td> <p>輸入或對應您要符合圖樣的文字。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Replace]

搜尋指定值或規則運算式的輸入文字，並將結果取代為新值。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL模式] </td> 
   <td> <p>輸入搜尋字詞。 您也可以使用規則運算式。 如需規則運算式的詳細資訊，請參閱<a href="#match-pattern" class="MCXref xref">[！UICONTROL比對模式]</a>模組。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL新值]</td> 
   <td> <p> 輸入您要取代搜尋字詞的值。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL全域符合]</td> 
   <td> <p>啟用此選項以擷取文字中的所有相符專案。 每個相符專案都會以個別的套裝輸出。 如果停用此選項，模組只會擷取第一個專案。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL區分大小寫]</td> 
   <td> <p> 啟用此選項讓此模組將文字視為區分大小寫。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Multiline] </td> 
   <td> <p>啟用此選項可確保開始和結束中繼字元（<code>^</code>和<code>$</code>）符合每行的開頭或結尾，而不只是整個輸入字串的開頭或結尾。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL單行]</td> 
   <td>啟用此選項以確保句點(.)符合新行字元(<code>\n</code>)。</td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Text] </td> 
   <td> <p>輸入要搜尋的文字。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 資料清除

資料擷取（有時稱為網頁擷取、資料擷取或網頁收集）是從網站收集資料，並將其儲存在本機資料庫或試算表中的程式。 如果您想從網站刮取資料，但不熟悉規則運算式，則可使用資料刮取工具。

如果資料刮取工具提供REST API，您可以透過我們的通用[[!UICONTROL HTTP]模組](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md#universal-connectors)和[Webhooks](/help/workfront-fusion/references/apps-and-modules/universal-connectors/webhooks-updated.md)模組連線到它。

## 文字剖析器疑難排解

如果您無法取得文字剖析器以產生任何輸出，請使用此資訊。

>[!BEGINSHADEBOX]

範例：

模組應剖析檔案檔案「filename.docx」的檔案型別，且檔案名稱的副檔名從DOCX到PDF再到CSV。

您可以在此情況下選擇使用的運算式是[!DNL \..+]

此規則運算式通常會產生完全相符的結果。

不過，在文字剖析器中實作此運算式不會產生相符專案：

![沒有相符項](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-you-dont-get-a-match-350x365.png)

原因在於「i」僅顯示每個相符項的相符數，因此在此例中，我們有2個相符項，因此「i」後面有一個數值1和2。 此情況下的使用案例是，如果您只需要比對或傳遞資料至篩選器，就可以指定由數值表示的值（第二個相符值）。

![符合](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-matches-350x355.png)

為了能夠取得您在要剖析的零件中新增方括弧所需的相符值（例如，從「filename.docx」 — 「docx」中擷取），然後根據我們用於此案例的規則運算式情境，方括弧應套用在\上。(.+)

這會擷取DOCX、將其置於群組中，並保留「」。 盡情享受吧。

![取得相符專案](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-get-matches-350x592.png)

在下圖所示的輸出中，擷取群組將符合任何字元（行終止元除外）。

![輸出](/help/workfront-fusion/references/apps-and-modules/assets/text-parser-output-350x389.png)

另一個同時納入regex的因應措施是使用取代函式

`{{replace("abcdefghijklmno pqr stuvw xyz.docx"; "/.\./"; ".")}}`

然後將`abcdefghijklmno pqr stuvw xyz.docx`取代為您的實際檔案名稱變數。

>[!ENDSHADEBOX]

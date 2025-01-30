---
title: Microsoft Word範本模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Microsoft Word範本的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: a5ba5634-226b-4886-a4f1-3a14948c1605
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 0%

---

# [!DNL Microsoft Word Template]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Microsoft Word Templates]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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
   <p>目前：無Workfront Fusion授權需求。</p>
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

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要搭配[!DNL Adobe Workfront Fusion]使用[!DNL Miscrosoft Word Templates]，必須有[!DNL Office 365]帳戶。 您可以在`www.office.com`建立一個。



## 正在將[!DNL Office]服務連線到[!DNL Workfront Fusion]

如需有關將您的[!DNL Office]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線 — 基本指示](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## 使用[!DNL Microsoft Word Templates]模組

您可以使用[!DNL Microsoft Word Template]模組將來自多個網站服務的資料合併到[!DNL Microsoft Word]檔案中。

例如，您可以使用此[!DNL Microsoft Word]範本：

](/help/workfront-fusion/references/apps-and-modules/assets/word-template-before-filled-350x62.png)之前的![Word範本

若要建立此檔案：

![已填入Word範本](/help/workfront-fusion/references/apps-and-modules/assets/word-template-exampled-filled-350x85.png)

## 關於值標籤

[!DNL Microsoft Word]範本是一般[!DNL Microsoft Word]檔案（.docx檔案），其文字中有特殊標籤，可決定合併或填入資料的位置和方式。 有三種型別的標籤：

* [簡單值標籤](#simple-value-tag)
* [條件標籤](#condition-tag)
* [回圈標籤](#loop-tag)

### 簡單值標籤 {#simple-value-tag}

簡單值標籤只會被對應的值取代。 標籤名稱與[!UICONTROL Key]欄位的值相對應，該值放在雙大括弧內；例如`{{name}}`。

**範例：**&#x200B;若要建立顯示「嗨，Petr！」的檔案，您可以使用[!DNL Microsoft Word Template]模組來建立下列範本：

```
> Hi {{name}}!
```

若要這麼做，您需設定模組，如下所示：

![Word範本簡單值](/help/workfront-fusion/references/apps-and-modules/assets/word-template-simple-value-350x286.png)

### 條件標籤 {#condition-tag}

您可以使用條件標籤來繞排文字，這些文字只有在符合某些條件時才應呈現。 若要繞排文字，請將其置於開始和結束條件標籤之間，例如「hasPhone」（如果條件為資料是否包含電話號碼）。 開始標簽名稱會加上雜湊符號#，而結束標簽名稱會加上斜線/ ，如下列範例所示。

**範例：**&#x200B;若要在輸入資料包含電話號碼但沒有電子郵件地址時產生包含客戶電話號碼的檔案，您可以使用[!DNL Microsoft Word Template]模組並建立下列範本：

```
> {{#hasPhone}}Phone: {{phone}} {{/hasPhone}}
> {{#hasEmail}}Email: {{email}} {{/hasEmail}}
```

若要這麼做，您需設定模組，如下所示：

![條件式Word範本](/help/workfront-fusion/references/apps-and-modules/assets/word-template-conditional-350x501.png)

在檔案中，電話號碼會顯示如下：

```
> Phone: 4445551234
```

### 回圈標籤 {#loop-tag}

您可以使用回圈標籤（也稱為節標籤）來重複文字的節。 將文字置於開啟和關閉回圈標籤之間，以繞排文字。 開始標簽名稱會加上雜湊符號#；結束標簽名稱會加上斜線/。

**範例：**&#x200B;若要產生列出客戶清單中每個連絡人姓名和電話號碼的檔案，您可以使用[!DNL Microsoft Word Template]模組並建立下列範本：

```
> {{#contact}}
>     {{name}}, {{phone}}
> {{/contact}}
```

若要這麼做，您需設定模組，如下所示：


![填寫檔案](/help/workfront-fusion/references/apps-and-modules/assets/word-template-fill-out-a-document-350x732.png)

此模組將建立以下檔案：

```
> Jan Toman, 4445551234
> Eduard Salo, 4445552345
```

## [!DNL Microsoft Word Template]模組

這些模組不需要連線。

* [填寫檔案](#fill-out-a-document)
* [以批次資料填入檔案](#fill-a-document-with-a-batch-of-data)

### [!UICONTROL Fill out a document] {#fill-out-a-document}

此轉換器模組可讓您使用您指定的資料填入檔案。 它可與簡單值標籤、條件標籤或回圈標籤搭配使用。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start delimiter of the text being replaced]</td> 
   <td> <p>輸入要標示取代文字開頭的字元。 </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>輸入<code>&#91;&#91;</code>以取代<code>[[replace_me]]</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL End delimiter of the text being replaced]</p> </td> 
   <td> <p>輸入要標示取代文字結尾的字元。 </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>輸入要取代的<code>&#93;&#93;</code> <code>[[replace_me]]</code></p>。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p> 從先前的模組中選取來源檔案，或對應來源檔案的資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of filled out file]</td> 
   <td>輸入目標輸出檔案的檔案名稱（包括副檔名）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Data source]</td> 
   <td> <p>選取選項以指出您使用的資料來自表單還是原始資料集合（未處理的電腦資料）。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values]</td> 
   <td> <p>這必須是集合陣列，其中：</p> 
    <ul> 
     <li>每個集合都對應一個資料專案，並包含一個專案 <code>entry</code></li> 
     <li>專案<code>entry </code>包含<code>key </code>的集合，並且 <code>value</code></li> 
     <li>專案<code>key </code>包含標籤的名稱</li> 
     <li>專案<code>value </code>包含標籤的值</li> 
    </ul> 
    <p>若要新增專案：</p>
    <ol> 
     <li> 按一下<b>[!UICONTROL Add Item]</b>。 </li> 
     <li>選取專案的值型別。</li> 
     <li>新增名稱和值。 如需詳細資訊，請參閱本文所選值型別的範例。 
      <ul> 
       <li><a href="#simple-value-tag" class="MCXref xref">簡單值標籤</a></li> 
       <li><a href="#condition-tag" class="MCXref xref">條件標籤</a></li> 
       <li><a href="#loop-tag" class="MCXref xref">回圈標籤</a></li> 
      </ul></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Fill a document with a batch of data] {#fill-a-document-with-a-batch-of-data}

如果您的資料專案為個別的組合，此彙總模組相當實用。 使用此模組，您可以輕鬆設定值欄位所需的結構，並將專案對應至每個值專案。 相較於填寫檔案模組，使用資料模組批次填寫檔案中的值欄位僅允許包含變數的單一專案。

如果您的資料專案為陣列，您也可以使用此模組，方法是使用&#x200B;*疊代器*&#x200B;模組將陣列的內容轉換為一系列組合。

系統會為每個傳入的套件組合建立並填入實際值。 範本會在處理所有輸入組合後產生。

此彙總模組對於建立清單或報告特別實用。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source Module]</td> 
   <td>選取作為文字來源的模組。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Start delimiter of the text being replaced]</td> 
   <td> <p>輸入要標示取代文字開頭的字元。 </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>輸入<code>&#91;&#91;</code>以取代<code>[[replace_me]]</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL End delimiter of the text being replaced]</p> </td> 
   <td> <p>輸入要標示取代文字結尾的字元。 </p> <p class="example" data-mc-autonum="<b>Example: </b>"><span class="autonumber"><span><b>範例： </b></span></span>輸入<code>&#93;&#93;</code>以取代<code>[[replace_me]]</code>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Group by]</td> 
   <td> 定義包含一或多個對應專案的運算式。 彙總資料會以相同運算式的值分隔在「群組」底下。 每個群組都會輸出為個別的組合，其中包含含運算式和彙總文字的索引鍵。 如此一來，您便可將索引鍵用作後續模組中的篩選條件。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Stop processing after an empty aggregation]</td> 
   <td>啟用此選項可在彙總不含任何組合時停止處理。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source file]</td> 
   <td> <p> 從先前的模組中選取來源檔案，或對應來源檔案的資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name of filled out file]</td> 
   <td>輸入目標輸出檔案的檔案名稱（包括副檔名）。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Values]</td> 
   <td> <p>這必須是集合陣列，其中：</p> 
    <ul> 
     <li>每個集合都對應一個資料專案，並包含一個專案 <code>entry</code></li> 
     <li>專案<code>entry </code>包含<code>key </code>的集合，並且 <code>value</code></li> 
     <li>專案<code>key </code>包含標籤的名稱</li> 
     <li>專案<code>value </code>包含標籤的值</li> 
    </ul> 
    <p>若要新增專案：</p>
    <ol> 
     <li> 按一下<b>[!UICONTROL Add Item]</b>。 </li> 
     <li>選取專案的值型別。</li> 
     <li>新增名稱和值。 如需詳細資訊，請參閱本文所選值型別的範例。 
      <ul> 
       <li><a href="#simple-value-tag" class="MCXref xref">簡單值標籤</a></li> 
       <li><a href="#condition-tag" class="MCXref xref">條件標籤</a></li> 
       <li><a href="#loop-tag" class="MCXref xref">回圈標籤</a></li> 
      </ul></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

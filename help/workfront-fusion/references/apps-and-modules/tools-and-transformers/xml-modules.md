---
title: XML
description: XML應用程式可讓您透過XML &amp；剖析XML模組來剖析XML格式文字，並將它轉換為套件組合，讓其他模組可以使用該資料。 您也可以透過XML &amp；gt；建立XML模組將組合轉換為XML格式文字
author: Becky
feature: Workfront Fusion
exl-id: ab323361-cd04-4dcc-ab02-0fb468334fdb
source-git-commit: 4697ea1449f77ddb8648658990098b3b4bc58ad2
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 2%

---

# XML

[!UICONTROL XML]應用程式可讓您透過[!UICONTROL XML] > [!UICONTROL 剖析XML]模組來剖析XML格式文字，並將它轉換成組合以供其他模組使用。 您也可以透過[!UICONTROL XML] > [!UICONTROL 建立XML]模組，將組合轉換為XML格式文字

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
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

+++



## 建立XML

[!UICONTROL XML] > [!UICONTROL 建立XML]模組會將組合轉換為XML格式文字。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 資料結構]</p> </td> 
   <td> <p>資料結構描述產生的XML結構。 如果您有想要建立的XML範例，則可以使用它來產生資料結構：</p> 
    <ol> 
     <li value="1">按一下<strong>[!UICONTROL Add]</strong>按鈕。</li> 
     <li value="2">按一下<strong>[!UICONTROL 產生器]</strong>按鈕。</li> 
     <li value="3">將XML範例複製並貼到「範例資料」欄位中。</li> 
     <li value="4">按一下<strong>[!UICONTROL 儲存]</strong>按鈕。</li> 
     <li value="5">確認已成功產生資料結構。</li> 
     <li value="6">按一下<strong>[!UICONTROL 儲存]</strong>以儲存資料結構。</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 根元素名稱]</td> 
   <td>輸入XML根專案的名稱。 預設值為 <code>root</code>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Doctype系統ID]</td> 
   <td>輸入要在<code>!DOCTYPE SYSTEM</code>宣告中使用的檔案名稱</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Doctype公共ID]</td> 
   <td>輸入要在<code>!DOCTYPE PUBLIC</code>宣告中使用的檔案名稱</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 長條Xml宣告]</td> 
   <td>啟用此選項以移除XML宣告<code>&lt;?xml ... ?&gt;</code>和<code>&lt;!DOCTYPE ... &gt;</code>，並只保留XML根專案及其內容。</td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**範例：**

典型的使用案例是將資料從[!DNL Google] >試算表轉換為XML。

1. 將[!DNL Google Sheets] > [!UICONTROL 選取情境中的列]模組以擷取資料。 設定模組以從[!DNL Google]試算表中擷取列。 將&#x200B;**[!UICONTROL 傳回資料列數目上限]**&#x200B;設定為小數，但大於一個以供測試之用（例如，三個）。 執行[!DNL Google Sheets]模組，方法為用滑鼠右鍵按一下該模組，然後選擇&#x200B;**[!UICONTROL 僅執行此模組]**。 驗證模組的輸出。
1. 在[!UICONTROL 模組之後連線]陣列彙總[!DNL Google Sheets]模組。 在模組的設定中，選擇[!DNL Google Sheets]Source節點&#x200B;**[!UICONTROL 欄位中的]**&#x200B;模組。 讓其他欄位維持目前的狀態。
1. 在[!UICONTROL 陣列彙總]模組之後連線[!UICONTROL XML] > [!UICONTROL 建立XML]模組。

   模組的設定需要說明XML輸出結構的資料結構。 按一下「**[!UICONTROL 新增]**」按鈕，開啟資料結構設定。 建立此資料結構的最簡單方法是從XML範例自動產生它。

1. 按一下&#x200B;**[!UICONTROL 產生器]**&#x200B;按鈕，然後將您的XML範例貼到[!UICONTROL 範例資料]欄位：

   ![範例資料欄位](/help/workfront-fusion/references/apps-and-modules/assets/sample-data-field-350x146.png)

1. 按一下「**[!UICONTROL 儲存]**」。

   資料結構中的「規格」欄位現在包含產生的結構。
1. 將您的資料結構名稱變更為更具體的名稱，然後按一下[儲存]。**&#x200B;**

   對應至根陣列屬性的欄位會顯示為JSON模組設定中的可對應欄位。
1. 按一下欄位旁的&#x200B;**[!UICONTROL 對應]**&#x200B;按鈕，並將來自`Array[]`陣列彙總[!UICONTROL 輸出的]專案對應至該欄位：
1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;關閉XML模組的安裝程式。
1. 開啟[!UICONTROL 陣列彙總]模組的設定。 將&#x200B;**[!UICONTROL 目標結構]**&#x200B;從「自訂」變更為XML模組的欄位，此欄位對應到父XML專案。將專案從[!DNL Google Sheets]模組對應到適當的欄位。
1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;以關閉陣列彙總模組的設定。
1. 執行情境。

   XML模組會輸出正確的XML檔案。

1. 開啟[!DNL Google Sheets]模組的設定，並增加[!UICONTROL 傳回資料列數目上限]數字，使其大於試算表中的資料列數目，以處理所有資料。

   產生的XML可以儲存至[!DNL Dropbox]、透過電子郵件以附件傳送、透過FTP上傳至伺服器等等。

>[!ENDSHADEBOX]

### 新增XML屬性

如果您想要將屬性新增至複雜節點（將包含其他節點的節點），您必須在自訂資料結構中為複雜附註新增名稱為`_attributes`的集合。 此集合將會對應至節點屬性。 如果您想要新增屬性至文位元組點（例如： `<node attr="1">abc</node>`），您必須在自訂資料結構中新增屬性的集合`_attributes`，以及此節點的節點值的文字屬性`_value`。

```
{
   "name": "node",
   "type": "collection",
   "spec": [
      {
         "name": "_attributes",
         "type": "collection"
         "spec": [
            {
               "name": "attr1",
               "type": "text"
            }
         ]
      },
      {
         "name": "_value",
         "type": "text"
      }
   ]
}
```

## [!UICONTROL 剖析XML]

[!UICONTROL XML] > [!UICONTROL 剖析XML]模組會剖析XML格式文字，並輸出包含從XML擷取之所有資訊的單一組合。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 資料結構]</p> </td> 
   <td> <p>資料結構說明XML的結構，以便在下列模組的對應面板中可取得模組的輸出。</p> <p>如果您有想要剖析的XML範例，則可以用它來產生資料結構：</p> 
    <ol> 
     <li value="1">按一下<strong>[!UICONTROL Add]</strong>按鈕。</li> 
     <li value="2">按一下<strong>[!UICONTROL 產生器]</strong>按鈕。</li> 
     <li value="3">將XML範例複製並貼到<strong>[!UICONTROL 範例資料]</strong>欄位中。</li> 
     <li value="4">按一下<strong>[!UICONTROL 儲存]</strong>。</li> 
     <li value="5">確認已成功產生資料結構。</li> 
     <li value="6"> <p>按一下<strong>[!UICONTROL 儲存]</strong>按鈕以儲存資料結構。</p> <p>您可以略過步驟2至5來提供空白的資料結構。 如果資料結構是空的，至少執行一次模組後，才能在對應面板中取得模組的輸出。</p> </li> 
    </ol> <p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md" class="MCXref xref">資料結構</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 保留數字為文字]</td> 
   <td>啟用此選項以確保數字保持為文字（字串）值。 否則，數字會轉換為數字值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL XML]</p> </td> 
   <td> <p>輸入或對應您要剖析的XML格式文字。</p> <p>如果您使用公式，請確定其結果值型別為（或可自動強製為）[!UICONTROL Text]資料型別。 </p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/if-you-use-a-formula-350x164.png" style="width: 350;height: 164;"> </p> <p>如果結果值型別為[!UICONTROL Buffer] （二進位資料），請使用<code>toString()</code>函式將其轉換為Text資料型別。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制性</a>和<a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">專案資料型別</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!BEGINSHADEBOX]

**範例：**

若要從URL下載XML檔案並剖析其內容：

1. 建立新情境。
1. 新增[!UICONTROL HTTP] > [!UICONTROL 取得檔案]模組
1. 開啟模組的設定，並依照以下方式設定：

   **URL**： XML檔案的URL （例如`https://siftrss.com/f/rqLy05ayMBJ`）

   ![XML檔案範例](/help/workfront-fusion/references/apps-and-modules/assets/url-of-xml-file-350x184.png)的URL

1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;以儲存並關閉模組的設定。
1. 新增[!UICONTROL XML] > [!UICONTROL 剖析XML]模組，在[!UICONTROL HTTP] > [!UICONTROL 取得檔案]模組後將其連線，並依照下列方式設定：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL 資料結構]</td> 
      <td> 
       <ol> 
        <li value="1">按一下<strong>[!UICONTROL Add]</strong>按鈕。</li> 
        <li value="2">按一下<strong>[!UICONTROL 產生器]</strong>按鈕。</li> 
        <li value="3">在網頁瀏覽器中，開啟新的標籤或視窗。</li> 
        <li value="4">將您第三個步驟中使用的URL放在位址列中，並擷取XML檔案。</li> 
        <li value="5">選取所有XML文字，並將其複製到剪貼簿。</li> 
        <li value="6">關閉標籤或視窗並返回您的案例。</li> 
        <li value="7">將複製的XML文字貼到「範例資料」欄位中。</li> 
        <li value="8">按一下<strong>[!UICONTROL 儲存]</strong>。</li> 
        <li value="9">確認已成功產生資料結構。</li> 
        <li value="10">按一下<strong>[!UICONTROL 儲存]</strong>以儲存資料結構。</li> 
       </ol> <p>您可以略過步驟2到9，以提供空白的資料結構。 如果資料結構是空的，至少執行一次模組後，才能在對應面板中取得模組的輸出。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL XML]</td> 
      <td> <p>將[!UICONTROL HTTP] &gt; [!UICONTROL Get a file]模組輸出中的<code>Data </code>專案對應到欄位中。 使用<code>toString()</code>函式將其值從[!UICONTROL Buffer] （二進位資料）型別轉換為[!UICONTROL Text]資料型別。</p> <p>您可以將公式的程式碼複製並貼到欄位中： <code>&#123;&#123;toString(1.data)&#125;&#125;</code></p> <p>如需有關Buffer和Text資料型別的詳細資訊，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">專案資料型別</a>。</p> <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/paste-formula-code-350x99.png"> </p> </td> 
     </tr> 
    </tbody> 
   </table>

>[!ENDSHADEBOX]

### [!UICONTROL 剖析XML屬性]

依預設，[!UICONTROL XML] > [!UICONTROL 剖析XML]模組會將特殊集合`_attributes`中的屬性當作具有這些屬性的節點的子系。 如果節點是文位元組點，且節點具有屬性，則會新增兩個特殊屬性：屬性為`_attributes`，節點文字內容為`_value`。

>[!BEGINSHADEBOX]

**範例：**&#x200B;這個XML：

```
<root attr="1">
<node attr="ABC">Hello, World</node>
</root>
```

會轉換為此套件組合：

![XML已轉換為組合](/help/workfront-fusion/references/apps-and-modules/assets/xml-converted-to-bundle.png)

>[!ENDSHADEBOX]

## 疑難排解：無法從[!UICONTROL 剖析XML]模組對應資料

請確定資料結構的定義正確。 或者，您可以使用空的資料結構並至少執行一次模組以處理XML輸入。

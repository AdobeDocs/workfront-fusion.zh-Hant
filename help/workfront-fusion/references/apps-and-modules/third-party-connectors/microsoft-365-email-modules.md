---
title: Microsoft Office 365電子郵件
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Microsoft Office 365電子郵件的工作流程，並將其連線至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 5d4072ba-c598-4347-a42f-c59c7add0a1b
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '2823'
ht-degree: 0%

---

# [!DNL Microsoft Office 365 Email]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動處理使用[!UICONTROL Microsoft Office 365電子郵件]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用[!DNL Microsoft Office 365 Email]模組，您必須有[!DNL Microsoft Office 365 Email]帳戶。

## Microsoft Office 365電子郵件API資訊

Microsoft Office 365電子郵件聯結器使用下列專案：

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
   <td>v2.6.5</td> 
  </tr>
 </tbody> 
 </table>

## 正在將[!DNL Office 365 Email]服務連線到[!DNL Workfront Fusion]

如需有關將您的[!DNL Office 365 Email]帳戶連線到[!UICONTROL Workfront Fusion]的指示，請參閱[建立與[!UICONTROL Adobe Workfront Fusion]的連線](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md) — 基本指示

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## [!DNL Microsoft Office 365 Email]模組及其欄位

當您設定[!DNL Microsoft Office 365 Email]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Microsoft Office 365 Email]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [訊息](#message)
* [草稿訊息](#draft-message)
* [附件](#attachment)
* [其他](#other)

### 訊息

* [[!UICONTROL 建立並傳送訊息（舊版）]](#create-and-send-a-message)
* [[!UICONTROL 刪除訊息]](#delete-a-message)
* [[!UICONTROL 取得訊息]](#get-a-message)
* [[!UICONTROL 移動訊息]](#move-a-message)
* [[!UICONTROL 搜尋訊息]](#search-messages)
* [[!UICONTROL 觀看訊息]](#watch-messages)



#### [!UICONTROL 建立並傳送訊息（舊版）]

此動作模組會建立並傳送電子郵件訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 主旨]</td> 
   <td> <p>輸入或對映訊息的主旨行。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容]</td> 
   <td> <p>輸入或對應電子郵件的郵件內文。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 重要性]</td> 
   <td> <p>選取電子郵件的重要性</p> 
    <ul> 
     <li>[!UICONTROL 低]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL 高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 至收件者]</p> </td> 
   <td> <p>針對您想要傳送電子郵件的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC收件者]</p> </td> 
   <td> <p><p>針對您想要傳送電子郵件復本給的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 密件副本收件者]</p> </td> 
   <td> <p>對於您想要傳送電子郵件復本給的每個收件者，不允許其他收件者檢視其名稱或電子郵件地址，請按一下[新增專案] <b></b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 附件]</p> </td> 
   <td> <p>針對您想要新增至電子郵件的每個附件，按一下<b>新增專案</b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source檔案]</strong> </p> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet郵件標頭]</td> 
   <td> <p>針對您想要新增至電子郵件的每個標題，按一下<b>新增專案</b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入頁首的名稱</p> </li> 
     <li> <p><strong>[!UICONTROL 值]</strong> </p> <p>輸入頁首的值。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除訊息]

此動作模組會刪除現有的電子郵件訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL 訊息ID]</td> 
   <td> <p> 選取或對應您要刪除之訊息的ID。</p> </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得訊息]

此動作模組取得特定訊息的中繼資料

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 訊息ID]</td> 
   <td> <p> 選取或對應您要擷取中繼資料的訊息ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 取得MIME內容]</td> 
   <td>啟用此選項以擷取有關訊息MIME內容的資料。 [!UICONTROL MIME]內容可能包含影像、音訊、視訊或其他型別的檔案。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 移動訊息]

此動作模組會將電子郵件移至信箱中選取的資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 訊息ID]</td> 
   <td> <p> 選取或對應您要移至其他資料夾的郵件ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 郵件資料夾] </td> 
   <td> <p>選取或對應您要移動郵件的資料夾識別碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋訊息]

此搜尋模組會根據特定條件來搜尋訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
    <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
<tr> 
   <td role="rowheader">[!UICONTROL 郵件資料夾]</td> 
   <td> <p>選取包含您要搜尋之郵件的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋]</td> 
   <td>輸入您的搜尋查詢。 如需如何撰寫搜尋查詢的詳細資訊，請參閱[!DNL Microsoft]支援文章<a href="https://support.microsoft.com/en-us/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=en-us&amp;rs=en-us&amp;ad=us">在[!DNL Outlook.com]</a>中搜尋郵件和人員。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Order by]</td> 
   <td> <p>選取您要如何排序結果：</p> 
    <ul> 
     <li>[!UICONTROL 主旨（遞增或遞減）]</li> 
     <li>[!UICONTROL 建立的日期時間（升序或降序）]</li> 
     <li>[!UICONTROL 上次修改的日期時間（升序或降序）]</li> 
     <li>[!UICONTROL 收到日期時間（升序或降序）]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入在一個案例執行週期中[!DNL Workfront Fusion]應傳回的最大訊息數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看訊息]

此觸發模組會在傳送或接收新電子郵件訊息時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 監視訊息]</p> </td> 
   <td> <p>選取您要觀看的訊息：</p> 
    <ul> 
     <li>[!UICONTROL Only Unread]</li> 
     <li>[!UICONTROL 唯讀]</li> 
     <li>[!UICONTROL All]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 郵件資料夾]</td> 
   <td> <p>選取包含您要觀看之郵件的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 搜尋]</td> 
   <td>輸入您的搜尋查詢。 模組會傳回符合此查詢的訊息。 如需如何撰寫搜尋查詢的詳細資訊，請參閱[!DNL Microsoft]支援文章<a href="https://support.microsoft.com/en-us/office/search-mail-and-people-in-outlook-com-88108edf-028e-4306-b87e-7400bbb40aa7?ui=en-us&amp;rs=en-us&amp;ad=us">在[!DNL Outlook.com]</a>中搜尋郵件和人員。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入在一個案例執行週期中[!DNL Workfront Fusion]應傳回的最大訊息數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 草稿訊息

* [建立草稿訊息](#create-a-draft-message)
* [傳送草稿訊息](#send-a-draft-message)
* [更新訊息](#update-a-message)

#### [!UICONTROL 建立草稿訊息]

此動作模組會建立新的電子郵件訊息作為草稿。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 主旨]</td> 
   <td> <p>輸入訊息的主旨行。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容型別]</td> 
   <td>選取訊息的正文內容是HTML或文字。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容]</td> 
   <td> <p>輸入或對應電子郵件的郵件內文。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 重要性]</td> 
   <td> <p>選取電子郵件的重要性</p> 
    <ul> 
     <li>[!UICONTROL 低]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL 高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 至收件者]</p> </td> 
   <td> <p>針對您想要傳送電子郵件的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC收件者]</p> </td> 
   <td> <p><p>針對您想要傳送電子郵件復本給的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 密件副本收件者]</p> </td> 
   <td> <p>對於您想要傳送電子郵件復本給的每個收件者，不允許其他收件者檢視其名稱或電子郵件地址，請按一下[新增專案] <b></b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 附件]</p> </td> 
   <td> <p>針對您想要新增至電子郵件的每個附件，按一下<b>新增專案</b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source檔案]</strong> </p> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 傳送郵件草稿]

此動作模組會傳送目前處於草稿狀態的電子郵件訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 草稿訊息ID]</td> 
   <td> <p> 選取或對應您要傳送之草稿的訊息ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新訊息]

此動作模組會更新現有訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 輸入訊息ID]</td> 
   <td> <p>選取您要如何識別要更新的訊息：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 手動輸入]</strong> </p> <p>輸入或對映訊息ID。</p> </li> 
     <li> <p><strong>[!UICONTROL 從清單中選取]</strong> </p> <p>選取包含要更新之郵件的資料夾，然後選取郵件</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 主旨]</td> 
   <td> <p>輸入訊息的主旨行。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文內容]</td> 
   <td> <p>輸入電子郵件的郵件內文。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 重要性]</td> 
   <td> <p>選取電子郵件的重要性</p> 
    <ul> 
     <li>[!UICONTROL 低]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL 高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 至收件者]</p> </td> 
   <td> <p>針對您想要傳送電子郵件的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC收件者]</p> </td> 
   <td> <p><p>針對您想要傳送電子郵件復本給的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 密件副本收件者]</p> </td> 
   <td> <p>對於您想要傳送電子郵件復本給的每個收件者，不允許其他收件者檢視其名稱或電子郵件地址，請按一下[新增專案] <b></b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 附件]</p> </td> 
   <td> <p>針對您想要新增至電子郵件的每個附件，按一下<b>新增專案</b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source檔案]</strong> </p> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 將其標籤為已讀]</td> 
   <td>啟用此選項可將更新的訊息標示為已讀取。</td> 
  </tr> 
 </tbody> 
</table>

### 附件

* [[!UICONTROL 下載附件]](#download-an-attachment)
* [[!UICONTROL 列出附件]](#list-attachments)

#### [!UICONTROL 下載附件]

此模組會下載指定的附件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL 訊息ID]</td> 
   <td> <p> 選取或對應包含要下載之附件的郵件ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 附件ID]</td> 
   <td> <p>輸入或對應您要下載之附件的ID。 您可以使用「列出附件」模組來找出此想法。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出附件]

此模組會擷取屬於指定郵件的附件清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 訊息ID]</td> 
   <td> <p> 選取或對應您要擷取附件的郵件ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大附件數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [[!UICONTROL 新增附件]](#add-an-attachment)
* [建立並傳送訊息](#create-and-send-a-message)
* [[!UICONTROL 進行API呼叫]](#make-an-api-call)

#### [!UICONTROL 新增附件]

此模組會將大型附件新增至郵件。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 訊息ID]</td> 
   <td> <p> 選取或對應您要新增附件的郵件識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立並傳送訊息]

此動作模組會建立並傳送電子郵件訊息。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 主旨]</td> 
   <td> <p>輸入或對映訊息的主旨行。</p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL 內文內容]</td> 
   <td> <p>輸入或對應電子郵件的郵件內文。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 重要性]</td> 
   <td> <p>選取電子郵件的重要性</p> 
    <ul> 
     <li>[!UICONTROL 低]</li> 
     <li>[!UICONTROL Normal]</li> 
     <li>[!UICONTROL 高]</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 至收件者]</p> </td> 
   <td> <p>針對您想要傳送電子郵件的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL CC收件者]</p> </td> 
   <td> <p><p>針對您想要傳送電子郵件復本給的每個收件者，按一下[新增專案] <b>並輸入下列內容：</b></p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 密件副本收件者]</p> </td> 
   <td> <p>對於您想要傳送電子郵件復本給的每個收件者，不允許其他收件者檢視其名稱或電子郵件地址，請按一下[新增專案] <b></b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入連絡人的電子郵件地址。</p> </li> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入連絡人的名稱。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 附件]</p> </td> 
   <td> <p>針對您想要新增至電子郵件的每個附件，按一下<b>新增專案</b>並輸入下列內容：</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL Source檔案]</strong> </p> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Internet郵件標頭]</td> 
   <td> <p>新增電子郵件的郵件標題。</p> 
    <ul> 
     <li> <p><strong>[!UICONTROL 名稱]</strong> </p> <p>輸入頁首的名稱</p> </li> 
     <li> <p><strong>[!UICONTROL 電子郵件地址]</strong> </p> <p>輸入頁首的值。</p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL From e-mail address]</td> 
   <td> <p> 若要使用共用電子郵件地址，請在此輸入地址。 用於此模組之連線中使用其認證的使用者必須擁有共用資料夾的存取權。<p>將此欄位留空將使用連線擁有者自己的電子郵件地址。</p></p> </td> 
  </tr> 
   <td role="rowheader">[!UICONTROL 限制]</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行API呼叫]

此模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td> <p>如需有關將您的[!DNL Office 365]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於<code>https://graph.microsoft.com</code>的路徑。 範例：<code> /v1.0/me/messages</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 例如，<code>{"Content-type":"application/json"}</code>。 [!DNL Workfront Fusion]為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p> 以標準JSON物件的形式新增API呼叫的查詢。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

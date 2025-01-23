---
title: 事件模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Cvent的工作流程，並將其連線到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: b7e16180-1db8-4aff-bb7b-69ca98194b00
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 0%

---

# [!DNL Cvent]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Cvent]的工作流程，並將其連線至多個協力廠商應用程式和服務。

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

若要使用[!DNL Cvent]模組，您必須有[!DNL Cvent]帳戶。

## Cvent API資訊

Cvent聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> V200611.ASMX </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.7.14</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Cvent]連線至[!DNL Adobe Workfront Fusion] {#connect-cvent-to-adobe-workfront-fusion}

>[!NOTE]
>
>[!DNL Cvent]模組透過[!UICONTROL SOAP] API運作。 若要建立與[!DNL Cvent]的連線，您必須確定下列事項：
>
>* 您有[!DNL Cvent] API的[!UICONTROL SOAP]存取權。
>* [!DNL Workfront Fusion] IP位址已新增至您組織的允許清單。
>
>  如需[!DNL Workfront Fusion] IP位址的清單，請參閱貴組織的允許清單中的[設定Fusion的IP位址](/help/workfront-fusion/set-up-and-manage-workfront-fusion/set-up-and-manage-orgs-and-teams/set-up-orgs-teams-and-users/set-up-ip-addresses-for-fusion.md)


您可以直接從[!DNL Cvent]模組內建立與您的[!DNL Cvent]帳戶的連線。

1. 在任何[!DNL Cvent]模組中，按一下[!UICONTROL Connection]欄位旁的&#x200B;**[!UICONTROL Add]**。
1. 選取您要連線的區域。

   * [!UICONTROL North America]
   * [!UICONTROL Europe]
   * [!UICONTROL Sandbox]

1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線，並返回模組。

## [!DNL Cvent]模組及其欄位

當您設定[!DNL Cvent]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Cvent]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [搜尋](#searches)

### 動作

* [[!UICONTROL Custom API Call]](#create-meeting-request)
* [[!UICONTROL Read a record]](#read-a-record)
* [[!UICONTROL Register Invitee]](#register-invitee)
* [[!UICONTROL Add Invitee]](#add-invitee)
* [[!UICONTROL Delete Contact]](#delete-contact)
* [[!UICONTROL Update Contact]](#update-contact)
* [[!UICONTROL Create meeting request]](#create-meeting-request)

#### [!UICONTROL Custom API Call]

此動作模組可讓您對[!DNL Cvent] API進行自訂的已驗證呼叫。 如此一來，您就可以建立其他[!DNL Cvent]模組無法完成的資料流程自動化。

當您設定此模組時，會顯示下列欄位。

模組會傳回a狀態代碼，以及API呼叫的標題和正文。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">營運</td> 
   td&gt; <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">內文(XML)</td> 
   <td> <p>輸入或對應API呼叫的正文。 這必須只包含XML。 模組會自動包含驗證標頭。 </p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Read a record]

此動作模組會讀取特定記錄的相關資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td>選取您要讀取之記錄的專案型態。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact] / [!UICONTROL Event] / [!UICONTROL Invitee ID]</td> 
   <td> <p>輸入或對應您要讀取的專案識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Outputs]</td> 
   <td> <p>選取您要納入模組輸出的欄位。 根據您選取的專案型別，可使用欄位。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Register Invitee]

此動作模組會為事件註冊受邀者。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>被邀請者ID</p> </td> 
   <td> <p>輸入或對應您要註冊事件的受邀者ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">事件ID</td> 
   <td> <p>輸入或對應您要註冊受邀者之事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Add Invitee]

此動作模組會邀請連絡人參加活動。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>輸入或對應您要新增至事件的連絡人ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>輸入或對應您要新增連絡人的事件ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete Contact]

此動作模組會刪除Cvent中的單一連絡人。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Contact ID]</td> 
   <td> <p>輸入或對應您要刪除之連絡人的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update Contact]

此動作模組會使用其ID更新現有連絡人。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Contact ID]</p> </td> 
   <td> <p>輸入或對應您要更新的連絡人ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Fields]</td> 
   <td> <p>選取您要輸入資訊的欄位，然後填寫這些欄位的所需值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Custom fields]</td> 
   <td> <p>選取您要輸入資訊的欄位，然後填寫這些欄位的所需值。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create meeting request]

此動作模組會將會議要求新增至您的帳戶。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Form ID]</p> </td> 
   <td> <p>輸入或對應您要用來建立新會議要求的表單ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Meeting Request Fields]</td> 
   <td> <p>選取您要輸入資訊的會議邀請欄位，然後填寫這些欄位的所需值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event Request Fields]</td> 
   <td> <p>選取您要輸入資訊的事件請求欄位，然後填寫這些欄位的所需值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL RFP Request Fields]</td> 
   <td> <p>選取您要輸入資訊的提案請求欄位，然後填寫這些欄位的所需值。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 搜尋

#### [!UICONTROL List records]

此搜尋模組會擷取特定型別之所有記錄的相關資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Connection]</p> </td> 
   <td> <p>如需有關將您的[!DNL Cvent]帳戶連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-cvent-to-adobe-workfront-fusion" class="MCXref xref">將[!DNL Cvent]連線到[!DNL Adobe Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Record type]</p> </td> 
   <td> <p>選取您要列出的記錄型別。</p> 
    <ul> 
     <li> <p>來自您[!DNL Cvent]帳戶的所有事件</p> </li> 
     <li> <p>事件的所有工作階段</p> </li> 
     <li> <p>活動的所有受邀者</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Event ID]</td> 
   <td> <p>如果您要列出被邀請者或工作階段，請輸入或對應與被邀請者或工作階段相關聯之事件的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

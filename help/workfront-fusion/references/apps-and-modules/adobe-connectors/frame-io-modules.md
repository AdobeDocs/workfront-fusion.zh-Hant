---
title: Frame.io模組
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] 帳戶。'
author: Becky
feature: Workfront Fusion
exl-id: 121b145c-d04d-44b9-b673-ea2928e2346d
source-git-commit: 3aa896867bd143c67157fb886fafa37eaee2bc00
workflow-type: tm+mt
source-wordcount: '2128'
ht-degree: 0%

---

# [!DNL Frame.io]模組

[!DNL Adobe Workfront Fusion] [!DNL Frame.io]模組可讓您監視、建立、更新、擷取或刪除您[!DNL Frame.io]帳戶中的資產和註解。

如需Frame.io聯結器的影片簡介，請參閱：

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

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

若要使用[!DNL Frame.io]模組，您必須有[!DNL Frame.io]帳戶

## Frame.io API資訊

Frame.io聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://api.frame.io/v2</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.0.76</td> 
  </tr>
 </tbody> 
 </table>

## 將[!DNL Frame.io]連線至[!UICONTROL Adobe Workfront Fusion]

您可以使用API權杖或使用OAuth 2.0連線至[!DNL Frame.io]。

[使用API權杖連線至 [!DNL Frame.io] ](#connect-to-frameio-using-an-api-token)

[使用OAuth 2.0 PKCE連線至 [!DNL Frame.io] ](#connect-to-frameio-using-oauth-20-pkce)

### 使用API權杖連線到[!DNL Frame.io]

若要使用API權杖將您的[!DNL Frame.io]帳戶連線到[!DNL Workfront Fusion]，您必須在您的[!DNL Frame.io]帳戶中建立API權杖，並將其插入到[!DNL Workfront Fusion] [!DNL Frame.io] [!UICONTROL Create a connection]對話方塊。

1. 登入您的[!DNL Frame.io]帳戶。
1. 前往[!DNL Frame.io]開發人員的&#x200B;**[!UICONTROL Tokens]**&#x200B;頁面。
1. 按一下&#x200B;**[!UICONTROL New]**。
1. 輸入權杖的名稱，選取您要使用的範圍，然後按一下&#x200B;**[!UICONTROL Create]**。
1. 複製提供的Token。
1. 前往[!DNL Workfront Fusion]並開啟[!DNL Frame.io]模組的&#x200B;**[!UICONTROL Create a connection]**&#x200B;對話方塊。
1. 在&#x200B;**[!UICONTROL Connection type]**&#x200B;欄位中，選取&#x200B;**[!DNL Frame.io]**。
1. 輸入您在步驟5中複製的Token至&#x200B;**[!UICONTROL Your [!DNL Frame.io] API Key]**&#x200B;欄位
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線並返回模組。

### 使用OAuth 2.0 PKCE連線至[!DNL Frame.io]

您可以使用OAuth 2.0 PKCE搭配選用的使用者端ID來建立與[!DNL Frame.io]的連線。 如果您想要在連線中包含使用者端ID，您必須在您的[!DNL Frame.io]帳戶中建立OAuth 2.0應用程式。

* [使用OAuth 2.0 PKCE （不含使用者端ID）連線至 [!DNL Frame.io] ](#connect-to-frameio-using-using-oauth-20-pkce-without-client-id)
* [使用OAuth 2.0 PKCE （含使用者端ID）連線至 [!DNL Frame.io] ](#connect-to-frameio-using-using-oauth-20-pkce-with-client-id)

#### 使用OAuth 2.0 PKCE （不含使用者端ID）連線至[!DNL Frame.io]

1. 前往[!DNL Workfront Fusion]並開啟[!DNL Frame.io]模組的&#x200B;**[!UICONTROL Create a connection]**&#x200B;對話方塊。
1. 在&#x200B;**[!UICONTROL Connection type]**&#x200B;欄位中，選取&#x200B;**[!UICONTROL [!DNL Frame.io] OAuth 2.0 PKCE]**。
1. 在&#x200B;**[!UICONTROL Connection name]**&#x200B;欄位中輸入新連線的名稱。
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線並返回模組。

#### 使用OAuth 2.0 PKCE （含使用者端ID）連線至[!DNL Frame.io]

1. 在[!DNL Frame.io]中建立OAuth 2.0應用程式。 如需指示，請參閱[!UICONTROL OAuth 2.0 Code Authorization Flow]上的[!DNL Frame.io]檔案。

   >[!IMPORTANT]
   >
   >在[!DNL Frame.io]中建立OAuth 2.0應用程式時：
   >
   >* 輸入下列專案作為重新導向URI：
   >   
   >     * **美洲/ APAC**： `https://app.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >     * **EMEA**： `https://app-eu.workfrontfusion.com/oauth/cb/frame-io5`
   >
   >* 啟用PCKE選項。


1. 複製提供的`client_id`。
1. 前往[!DNL Workfront Fusion]並開啟[!DNL Frame.io]模組的&#x200B;**[!UICONTROL Create a connection]**&#x200B;對話方塊。
1. 在&#x200B;**[!UICONTROL Connection type]**&#x200B;欄位中，選取&#x200B;**[!UICONTROL [!DNL Frame.io] OAuth 2.0 PKCE]**。
1. 在&#x200B;**[!UICONTROL Connection name]**&#x200B;欄位中輸入新連線的名稱。
1. 按一下&#x200B;**[!UICONTROL Show advanced settings]**。
1. 輸入您在步驟2中複製到&#x200B;**[!UICONTROL Client ID]**&#x200B;欄位的`client_id`。
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線並返回模組。

## [!DNL Frame.io]模組及其欄位

當您設定[!DNL Frame.io]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Frame.io]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [資產](#assets)
* [評論](#comments)
* [專案](#projects)
* [其他](#other)

### 資產

* [[!UICONTROL Create an Asset]](#create-an-asset)
* [[!UICONTROL Delete an Asset]](#delete-an-asset)
* [[!UICONTROL Get an Asset]](#get-an-asset)
* [[!UICONTROL List Assets]](#list-assets)
* [[!UICONTROL Update an Asset]](#update-an-asset)
* [[!UICONTROL Watch Asset Deleted]](#watch-asset-deleted)
* [[!UICONTROL Watch Asset Label Updated]](#watch-asset-label-updated)
* [[!UICONTROL Watch New Asset]](#watch-new-asset)

#### [!UICONTROL Create an Asset]

此動作模組會建立新資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有您要建立資產的專案團隊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>選取專案或對應您要建立資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取資料夾或對應您要建立資產的資料夾之ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>選擇是否要建立資料夾或檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入新檔案或資料夾的名稱。</p> </td> 
  </tr> <!--
   <tr> 
    <td role="rowheader">File Type </td> 
    <td> <p>Select the type of file you want to upload.</p> </td> 
   </tr>
  --> <!--
   <tr> 
    <td role="rowheader">File Size </td> 
    <td> <p>The file size in bytes.</p> </td> 
   </tr>
  --> 
  <tr> 
   <td role="rowheader">[!UICONTROL Source URL] </td> 
   <td> <p>如果建立檔案，請輸入您要上傳之檔案的URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>如果建立檔案，請輸入資產的簡短說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Label] </td> 
   <td> <p>如果建立檔案，請選取檔案是否正在進行中、需要稽核或已核准。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete an Asset]

此動作模組會刪除指定的資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，專案中包含您要刪除的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> 選取包含您要刪除之資產的專案或。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取包含您要刪除之資產的檔案夾</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>選取或對應您要刪除的資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get an Asset]

此動作模組會擷取資產詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對映擁有專案的團隊，專案中包含您要擷取詳細資訊的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> 選取包含您要擷取詳細資訊之資產的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取包含您要擷取詳細資訊之資產的檔案夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>選取資產或對應您要擷取詳細資訊之資產的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Assets]

此搜尋模組會擷取指定專案資料夾中的所有資產。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，專案中包含您想要從中擷取資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> 選取包含您要擷取資產的資料夾的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取您要列出資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的資產最大數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update an Asset]

此動作模組可讓您更新現有資產的名稱、說明或自訂欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有您要更新資產的專案團隊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>選取專案或對應您要更新資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取資料夾或對應您要更新資產的資料夾之ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>輸入或對應您要更新之資產的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Name] </td> 
   <td> <p>輸入更新檔案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Description] </td> 
   <td> <p>輸入已更新資產的簡短說明。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Asset Deleted]

刪除屬於指定團隊的資產時，此觸發模組就會開始案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> 輸入webhook的名稱，例如「已刪除資產」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Asset Label Updated]

此觸發模組會在指定團隊所擁有資產的標籤設定、變更或移除時開始案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> 輸入webhook的名稱，例如「資產狀態已更新」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch New Asset]

在為指定團隊建立新資產時，此觸發模組會啟動案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name]</td> 
   <td> <p> 輸入webhook的名稱，例如「已建立的資產」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 評論

* [[!UICONTROL Create a Comment]](#create-a-comment)
* [[!UICONTROL Delete a Comment]](#delete-a-comment)
* [[!UICONTROL Get a Comment]](#get-a-comment)
* [[!UICONTROL List Comments]](#list-comments)
* [[!UICONTROL Update a Comment]](#update-a-comment)
* [[!UICONTROL Watch Comment Updated]](#watch-comment-updated)
* [[!UICONTROL Watch New Comment]](#watch-new-comment)

#### [!UICONTROL Create a Comment]

此動作模組會新增註解或回覆至資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Type] </td> 
   <td> <p>選取您要建立註解還是回覆註解。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，專案中包含您想要新增註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>選取專案或對應專案ID，專案包含您要新增註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取資料夾或對應包含您要新增註解之資產的資料夾的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>選取或對應您要新增註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>選取或對應您要新增回覆的註解。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> 輸入評論或回覆的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>在影片中輸入評論應連結的影格編號。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Comment]

此動作模組會刪除現有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID]</td> 
   <td> <p> 選取或對映擁有專案的團隊，專案中包含您要從中刪除註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID]</td> 
   <td> <p> 選取專案或對應包含您要從中刪除註解之資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID]</td> 
   <td> <p> 選取包含您要從中刪除註解的資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>輸入或對應包含您要刪除之註解的資產ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>輸入或對應您要刪除之註解的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a Comment]

此動作模組會擷取指定註解的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，該專案包含您要從中擷取資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>選取包含您要擷取資產的資料夾的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取您要列出資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>選取包含您要擷取之註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>選取您要擷取有關詳細資訊的註解。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List Comments]

此搜尋模組會擷取指定資產的所有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，該專案包含您要從中擷取註解的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>選取包含您要從中擷取註解的資料夾的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取包含您要列出註解之資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>選取您要列出註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大註解數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update a Comment]

此動作模組會編輯現有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，專案中包含您要更新註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Project ID] </td> 
   <td> <p>選取包含您要更新註解之資產的專案\。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Folder ID] </td> 
   <td> <p>選取包含您要更新評論之資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Asset ID] </td> 
   <td> <p>選取您要更新註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Comment ID] </td> 
   <td> <p>選取要更新的註解。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Text]</td> 
   <td> <p> 輸入註解的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Timestamp] </td> 
   <td> <p>在評論連結的視訊中輸入影格編號。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Comment Updated]

此觸發模組會在編輯評論時啟動案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>輸入webhook的名稱，例如「編輯的註解」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch New Comment]

此觸發器模組會在建立新評論或回覆時啟動案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook name] </td> 
   <td> <p>輸入webhook的名稱，例如新增註解。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 專案

#### [!UICONTROL List Projects]

此搜尋模組會擷取指定團隊的所有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Team ID] </td> 
   <td> <p>選取或對應您要擷取專案的團隊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Limit] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大專案數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### [!UICONTROL Make an API Call]

此模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於<code>https://api.frame.io</code>的路徑。 範例： <code> /v2/teams</code></p> <p>注意：如需可用端點的清單，請參閱[!DNL Frame.io] API參考。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Method]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String] </td> 
   <td> <p>輸入請求查詢字串。 針對您要包含在查詢字串中的每個引數，按一下<b>[!UICONTROL Add item]</b>並輸入欄位名稱和所要的值。</p> </td> 
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


<!-- 
**Example:** The following API call returns all teams and its details in your [!DNL Frame.io] account:

URL: `/v2/teams`

Method: `GET`

![API call example](/help/workfront-fusion/references/apps-and-modules/assets/api-call-example.png)

The result can be found in the module's Output under Bundle > Body.

In our example, the details of 1 team were returned:

![API call output](/help/workfront-fusion/references/apps-and-modules/assets/api-call-output.png)

-->

---
title: Frame.io模組
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] 帳戶。'
author: Becky
feature: Workfront Fusion
exl-id: 121b145c-d04d-44b9-b673-ea2928e2346d
source-git-commit: 31487c8b5b6efad1e6d7817dfe7dda67eea88e43
workflow-type: tm+mt
source-wordcount: '2586'
ht-degree: 0%

---

# [!DNL Frame.io]個舊模組

>[!IMPORTANT]
>
>本文說明Frame.io聯結器的舊版。 此聯結器用於連線至Frame.io版本3。
>
>如需新（測試版）版Frame.io聯結器的說明，請參閱[Frame.io Beta聯結器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules-new.md)。

[!DNL Adobe Workfront Fusion] [!DNL Frame.io]模組可讓您監視、建立、更新、擷取或刪除您[!DNL Frame.io]帳戶中的資產和註解。

Workfront提供兩個Frame.io聯結器，根據您連線的Frame.io版本而定。

| 聯結器 | Frame.io版本 |
|---|---|
| Frame.io (Beta) | V4 |
| Frame.io （舊版） | V3 |

如需新（測試版）版Frame.io聯結器的說明，請參閱[Frame.io Beta聯結器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules-new.md)。

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
   <td role="rowheader">API 標記</td> 
   <td>v1.0.76</td> 
  </tr>
 </tbody> 
 </table>

## [!UICONTROL 連接至 [!DNL Frame.io] Adobe Systems Workfront Fusion]

您可以使用API權杖或使用OAuth 2.0連線至[!DNL Frame.io]。

[使用API權杖連線至 [!DNL Frame.io] ](#connect-to-frameio-using-an-api-token)

[使用OAuth 2.0 PKCE連線至 [!DNL Frame.io] ](#connect-to-frameio-using-oauth-20-pkce)

### 使用API權杖連線到[!DNL Frame.io]

若要使用API權杖將您的[!DNL Frame.io]帳戶連線到[!DNL Workfront Fusion]，您必須在[!DNL Frame.io]帳戶中建立API權杖，並將其插入到[!DNL Workfront Fusion] [!DNL Frame.io] [!UICONTROL 建立連線]對話方塊。

1. 登入您的[!DNL Frame.io]帳戶。
1. 前往[!DNL Frame.io]開發人員的&#x200B;**[!UICONTROL Token]**&#x200B;頁面。
1. 按一下&#x200B;**[!UICONTROL 新增]**。
1. 輸入權杖的名稱，選取您要使用的範圍，然後按一下[建立]。****
1. 複製提供的Token。
1. 移至[!DNL Workfront Fusion]並開啟[!DNL Frame.io]模組的&#x200B;**[!UICONTROL 建立連線]**&#x200B;對話方塊。
1. 在&#x200B;**[!UICONTROL 連線型別]**&#x200B;欄位中，選取&#x200B;**[!DNL Frame.io]**。
1. 輸入您在步驟5中複製的Token至&#x200B;**[!UICONTROL 您的[!DNL Frame.io] API金鑰]**&#x200B;欄位
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

### 使用OAuth 2.0 PKCE連線至[!DNL Frame.io]

您可以使用OAuth 2.0 PKCE搭配選用的使用者端ID來建立與[!DNL Frame.io]的連線。 如果您想要在連線中包含使用者端ID，您必須在您的[!DNL Frame.io]帳戶中建立OAuth 2.0應用程式。

* [使用OAuth 2.0 PKCE （不含使用者端ID）連線至 [!DNL Frame.io] ](#connect-to-frameio-using-using-oauth-20-pkce-without-client-id)
* [使用OAuth 2.0 PKCE （含使用者端ID）連線至 [!DNL Frame.io] ](#connect-to-frameio-using-using-oauth-20-pkce-with-client-id)

#### 使用OAuth 2.0 PKCE （不含使用者端ID）連線至[!DNL Frame.io]

1. 移至[!DNL Workfront Fusion]並開啟[!DNL Frame.io]模組的&#x200B;**[!UICONTROL 建立連線]**&#x200B;對話方塊。
1. 在&#x200B;**[!UICONTROL 連線型別]**&#x200B;欄位中，選取&#x200B;**[!UICONTROL [!DNL Frame.io]OAuth 2.0 PKCE]**。
1. 在&#x200B;**[!UICONTROL 連線名稱]**&#x200B;欄位中輸入新連線的名稱。
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

#### 使用OAuth 2.0 PKCE （含使用者端ID）連線至[!DNL Frame.io]

1. 在[!DNL Frame.io]中建立OAuth 2.0應用程式。 如需指示，請參閱有關[!UICONTROL OAuth 2.0程式碼授權流程]的[!DNL Frame.io]檔案。

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
1. 移至[!DNL Workfront Fusion]並開啟[!DNL Frame.io]模組的&#x200B;**[!UICONTROL 建立連線]**&#x200B;對話方塊。
1. 在&#x200B;**[!UICONTROL 連線型別]**&#x200B;欄位中，選取&#x200B;**[!UICONTROL [!DNL Frame.io]OAuth 2.0 PKCE]**。
1. 在&#x200B;**[!UICONTROL 連線名稱]**&#x200B;欄位中輸入新連線的名稱。
1. 按一下&#x200B;**[!UICONTROL 顯示進階設定]**。
1. 輸入您在步驟2中複製到&#x200B;**[!UICONTROL 使用者端識別碼]**&#x200B;欄位的`client_id`。
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以建立連線並返回模組。

## [!DNL Frame.io]模組及其欄位

當您設定[!DNL Frame.io]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Frame.io]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [資產](#assets)
* [評論](#comments)
* [專案](#projects)
* [其他](#other)

### 資產

* [[!UICONTROL 建立資產]](#create-an-asset)
* [[!UICONTROL 刪除資產]](#delete-an-asset)
* [[!UICONTROL 取得資產]](#get-an-asset)
* [[!UICONTROL 列出Assets]](#list-assets)
* [[!UICONTROL 更新資產]](#update-an-asset)
* [[!UICONTROL 觀看資產已刪除]](#watch-asset-deleted)
* [[!UICONTROL 觀看資產標籤已更新]](#watch-asset-label-updated)
* [[!UICONTROL 觀看新資產]](#watch-new-asset)

#### [!UICONTROL 建立資產]

此動作模組會建立新資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對應擁有您要建立資產的專案團隊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取專案或對應您要建立資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取資料夾或對應您要建立資產的資料夾之ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL型別] </td> 
   <td> <p>選擇是否要建立資料夾或檔案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
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
   <td role="rowheader">[！UICONTROL Source URL] </td> 
   <td> <p>如果建立檔案，請輸入您要上傳之檔案的URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL說明] </td> 
   <td> <p>如果建立檔案，請輸入資產的簡短說明。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL標籤] </td> 
   <td> <p>如果建立檔案，請選取檔案是否正在進行中、需要稽核或已核准。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除資產]

此動作模組會刪除指定的資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，專案中包含您要刪除的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID]</td> 
   <td> <p> 選取包含您要刪除之資產的專案或。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取包含您要刪除之資產的檔案夾</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>選取或對應您要刪除的資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得資產]

此動作模組會擷取資產詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對映擁有專案的團隊，專案中包含您要擷取詳細資訊的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID]</td> 
   <td> <p> 選取包含您要擷取詳細資訊之資產的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取包含您要擷取詳細資訊之資產的檔案夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>選取資產或對應您要擷取詳細資訊之資產的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出Assets]

此搜尋模組會擷取指定專案資料夾中的所有資產。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選擇或映射擁有包含要從中檢索資產的資料夾的專案的團隊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID]</td> 
   <td> <p> 選取包含您要擷取資產的資料夾的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取您要列出資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的資產最大數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新資產]

此動作模組可讓您更新現有資產的名稱、說明或自訂欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對應擁有您要更新資產的專案團隊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取專案或對應您要更新資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取資料夾或對應您要更新資產的資料夾之ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>輸入或對應您要更新之資產的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
   <td> <p>輸入更新檔案的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL說明] </td> 
   <td> <p>輸入已更新資產的簡短說明。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看資產已刪除]

刪除屬於指定團隊的資產時，此觸發模組就會開始案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱]</td> 
   <td> <p> 輸入webhook的名稱，例如「已刪除資產」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看資產標籤已更新]

此觸發模組會在指定團隊所擁有資產的標籤設定、變更或移除時開始案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱]</td> 
   <td> <p> 輸入webhook的名稱，例如「資產狀態已更新」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看新資產]

在為指定團隊建立新資產時，此觸發模組會啟動案例。

由於這是即時觸發器，因此必須選擇或創建 Webhook 以供模組使用。

如果添加 Webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱]</td> 
   <td> <p> 輸入 Webhook 的名稱，例如「已創建資產」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連接] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 評論

* [[!UICONTROL 建立註解]](#create-a-comment)
* [[!UICONTROL 刪除註解]](#delete-a-comment)
* [[!UICONTROL 取得註解]](#get-a-comment)
* [[!UICONTROL 清單註解]](#list-comments)
* [[!UICONTROL 更新註解]](#update-a-comment)
* [[!UICONTROL 觀看評論已更新]](#watch-comment-updated)
* [[!UICONTROL 觀看新註解]](#watch-new-comment)

#### [!UICONTROL 建立註解]

此動作模組會新增註解或回覆至資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL型別] </td> 
   <td> <p>選取您要建立註解還是回覆註解。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，專案中包含您想要新增註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取專案或對應專案ID，專案包含您要新增註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取資料夾或對應包含您要新增註解之資產的資料夾的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>選取或對應您要新增註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL註解ID] </td> 
   <td> <p>選取或對應您要新增回覆的註解。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Text]</td> 
   <td> <p> 輸入評論或回覆的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL時間戳記] </td> 
   <td> <p>在影片中輸入評論應連結的影格編號。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除註解]

此動作模組會刪除現有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID]</td> 
   <td> <p> 選取或對映擁有專案的團隊，專案中包含您要從中刪除註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID]</td> 
   <td> <p> 選取專案或對應包含您要從中刪除註解之資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID]</td> 
   <td> <p> 選取包含您要從中刪除註解的資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>輸入或對應包含您要刪除之註解的資產ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL註解ID] </td> 
   <td> <p>輸入或對應您要刪除之註解的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得註解]

此動作模組會擷取指定註解的詳細資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，該專案包含您要從中擷取資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取包含您要擷取資產的資料夾的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取您要列出資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>選擇包含要檢索的註釋的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解 ID] </td> 
   <td> <p>選擇要檢索詳細信息的評論。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清單備註]

此搜尋模組會擷取指定資產的所有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，該專案包含您要從中擷取註解的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取包含您要從中擷取註解的資料夾的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取包含您要列出註解之資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>選擇要為其清單評論的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大註解數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新註解]

此動作模組會編輯現有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取或對應擁有專案的團隊，專案中包含您要更新註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取包含您要更新註解的資產的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾ID] </td> 
   <td> <p>選取包含您要更新評論之資產的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>選取您要更新註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL註解ID] </td> 
   <td> <p>選取要更新的註解。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Text]</td> 
   <td> <p> 輸入註解的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL時間戳記] </td> 
   <td> <p>在評論連結的視訊中輸入影格編號。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看評論已更新]

此觸發模組會在編輯評論時啟動案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱] </td> 
   <td> <p>輸入webhook的名稱，例如「編輯的註解」。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看新註解]

此觸發器模組會在建立新評論或回覆時啟動案例。

因為這是立即觸發程式，您必須選取或建立webhook以供模組使用。

如果新增webhook，請輸入以下資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱] </td> 
   <td> <p>輸入webhook的名稱，例如新增註解。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL團隊ID] </td> 
   <td> <p>選取建立此webhook的團隊。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 專案

#### [!UICONTROL 列出專案]

此搜尋模組會擷取指定團隊的所有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>有關創建與的連接[!DNL Frame.io]的說明，請參閱<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">本文中的連接到[!DNL Frame.io][!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 團隊 ID] </td> 
   <td> <p>選取或對應要擷取專案的團隊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 限制] </td> 
   <td> <p>輸入或映射您希望模組在每個方案執行週期中返回的最大項目數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### [!UICONTROL 進行API呼叫]

此模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於<code>https://api.frame.io</code>的路徑。 範例： <code> /v2/teams</code></p> <p>注意：如需可用端點的清單，請參閱[!DNL Frame.io] API參考。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL方法]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標題]</td> 
   <td> <p>以標準 JSON 物件的格式添加請求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL查詢字串] </td> 
   <td> <p>輸入請求查詢字串。 針對您要包含在查詢字串中的每個引數，按一下<b>[！UICONTROL新增專案]</b>，然後輸入欄位名稱及所要的值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Body]</td> 
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

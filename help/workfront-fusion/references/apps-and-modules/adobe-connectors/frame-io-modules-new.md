---
title: Frame.io (Beta)模組
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] 帳戶。'
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '3553'
ht-degree: 1%

---

# [!DNL Frame.io] V4模組

>[!IMPORTANT]
>
>本文說明Frame.io聯結器的新版本。 此聯結器用於連線至Frame.io版本4。
>
>如需舊版Frame.io聯結器的說明，請參閱[Frame.io舊版聯結器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)。

Adobe Workfront Fusion [!DNL Frame.io]模組可讓您監視、建立、更新、擷取或刪除您[!DNL Frame.io]帳戶中的資產和註解。

Workfront提供兩個Frame.io聯結器，根據您連線的Frame.io版本而定。

| 聯結器 | Frame.io版本 |
|---|---|
| Frame.io | V4 |
| Frame.io （舊版） | V3 |

如需舊版Frame.io聯結器的說明，請參閱[Frame.io舊版聯結器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)。


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

## 先決條件

若要使用[!DNL Frame.io]模組，您必須有[!DNL Frame.io]帳戶

## Frame.io API資訊

Frame.io聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://api.frame.io/v4</td> 
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

您可以使用使用者認證自動連線、手動建立使用者認證連線，或建立伺服器對伺服器連線。

* [使用使用者認證自動連線](#connect-automatically-with-user-credentials#)
* [手動建立使用者認證連線](#create-a-user-credentials-connection-manually)
* [建立伺服器對伺服器連線](#create-a-server-to-server-connection)

### 使用使用者認證自動連線

如果您已登入Frame.io，此方法會自動建立連線，或將您連線至Frame.io登入頁面以便您登入。

1. 在任何Frame.io Beta模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。
1. 輸入連線的名稱。
1. 按一下&#x200B;**繼續**。
1. 如果系統提示您登入Frame.io帳戶，請登入。
1. 如果您屬於多個Frame.io組織，請選取要用於此連線的組織。

已建立連線。

### 手動建立使用者認證連線

您可以登入Frame.io或提供使用者端ID或使用者端密碼來建立使用者認證連線。

若要建立伺服器對伺服器連線，您必須先在Adobe Developer Console中設定應用程式。

* [在Adobe Developer Console中建立使用者認證](#create-user-credentials-in-the-adobe-developer-console)
* [設定使用者驗證連線](#configure-a-user-authentication-connection)

#### 在Adobe Developer Console中建立使用者認證

如果您在Adobe Developer Console專案中還沒有伺服器對伺服器認證，您可以建立這些認證。

1. 開啟[Adobe Developer Console](https://developer.adobe.com/)。
1. 在Adobe Developer Console中選取要用於此連線的現有專案

   或

   在Adobe Developer Console中建立新專案。 如需指示，請參閱[建立空白專案](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)。

1. 在專案概觀頁面或開始使用新專案頁面上，按一下&#x200B;**新增API**。
1. 在開啟的頁面上，找到並按一下&#x200B;**Frame.io API**。
1. 在[選取驗證型別]頁面上，選取[**使用者驗證**]，然後按一下[下一步] **。**
1. 在[新增使用者驗證認證]頁面上，選取&#x200B;**OAuth Web App**，然後按一下[下一步]****。
1. 在設定OAuth Web App認證頁面上，輸入下列內容：   <table style="table-layout:auto">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[！UICONTROL預設重新導向URI]</td>
          <td>
            <p><code>https://oauth.app.workfrontfusion.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL重新導向URI模式]</td>
          <td>
            <p><code>https://oauth\.app\.workfrontfusion\.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
       </tbody>
    </table>
1. 按一下&#x200B;**下一步**。
1. 按一下&#x200B;**儲存設定的API**。
1. 在產品頁面上，按一下您剛建立之憑證的卡片。

   您可以在這裡找到您的使用者端ID和使用者端密碼。

>[!NOTE]
>
> 建議您在Adobe Workfront Fusion中開始設定連線時，保持此視窗開啟。 您可以複製使用者端ID，並從此頁面擷取及複製使用者端密碼，以貼入連線欄位。


#### 設定使用者驗證連線

1. 在任何Frame.io Beta模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。
1. 在[建立連線]方塊中，按一下[顯示進階設定]。****

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[！UICONTROL連線型別]</td>
          <td>
            <p>選取<b>IMS使用者驗證</b>。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL連線名稱]</td>
          <td>
            <p>輸入此連線的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL使用者端ID]</td>
          <td>輸入您的[!DNL Adobe] [！UICONTROL使用者端識別碼]。 這可以在[!DNL Adobe Developer Console]的[！UICONTROL認證詳細資料]區段中找到。<p>如需建立認證的指示，請參閱本文中的<a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">在Adobe Developer Console中建立使用者認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL使用者端密碼]</td>
          <td>輸入您的[!DNL Adobe] [！UICONTROL使用者端密碼]。 這可以在[!DNL Adobe Developer Console]的[！UICONTROL認證詳細資料]區段中找到。<p>如需建立認證的指示，請參閱本文中的<a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">在Adobe Developer Console中建立使用者認證</a>。</p>
        </tr>
       </tbody>
    </table>
1. 如果系統提示您登入Frame.io帳戶，請登入。
1. 如果您屬於多個Frame.io組織，請選取要用於此連線的組織。

已建立連線。


### 建立伺服器對伺服器連線

若要建立伺服器對伺服器連線，您必須先在Adobe Developer Console中設定應用程式。

* [在Adobe Developer Console中建立伺服器對伺服器認證](#create-server-to-server-credentials-in-the-adobe-developer-console)
* [設定伺服器對伺服器連線](#configure-a-server-to-server-connection)

#### 在Adobe Developer Console中建立伺服器對伺服器認證

如果您在Adobe Developer Console專案中還沒有伺服器對伺服器認證，您可以建立這些認證。

1. 開啟[Adobe Developer Console](https://developer.adobe.com/)。
1. 在Adobe Developer Console中選取要用於此連線的現有專案

   或

   在Adobe Developer Console中建立新專案。 如需指示，請參閱[建立空白專案](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)。

1. 在專案概觀頁面或開始使用新專案頁面上，按一下&#x200B;**新增API**。
1. 在開啟的頁面上，找到並按一下&#x200B;**Frame.io API**。
1. 在[選取驗證型別]頁面上，選取&#x200B;**伺服器對伺服器驗證**，然後按一下[下一步]****。
1. 輸入認證的名稱。 這可讓您稍後在Adobe Admin Console的「API認證」區域中識別認證。
1. 按一下&#x200B;**下一步**。
1. 在「選取產品設定檔」頁面上，選取包含您要連線之Frame.io帳戶的產品設定檔。
1. 按一下&#x200B;**儲存設定的API**。
1. 在產品頁面上，按一下您剛建立之憑證的卡片。

   您可以在這裡找到您的使用者端ID和使用者端密碼。

>[!NOTE]
>
> 建議您在Adobe Workfront Fusion中開始設定連線時，保持此視窗開啟。 您可以複製使用者端ID，並從此頁面擷取及複製使用者端密碼，以貼入連線欄位。


#### 設定伺服器對伺服器連線

1. 在任何Frame.io Beta模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[！UICONTROL連線型別]</td>
          <td>
            <p>選取<b>IMS伺服器至伺服器</b>。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL連線名稱]</td>
          <td>
            <p>輸入此連線的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL使用者端ID]</td>
          <td>輸入您的[!DNL Adobe] [！UICONTROL使用者端識別碼]。 這可以在[!DNL Adobe Developer Console]的[！UICONTROL認證詳細資料]區段中找到。<p>如需建立認證的指示，請參閱本文中的<a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">在Adobe Developer Console中建立伺服器對伺服器認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL使用者端密碼]</td>
          <td>輸入您的[!DNL Adobe] [！UICONTROL使用者端密碼]。 這可以在[!DNL Adobe Developer Console]的[！UICONTROL認證詳細資料]區段中找到。<p>如需建立認證的指示，請參閱本文中的<a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">在Adobe Developer Console中建立伺服器對伺服器認證</a>。</p>
        </tr>
       </tbody>
    </table>
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。




## [!DNL Frame.io]模組及其欄位

當您設定[!DNL Frame.io]模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Frame.io]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [資產](#assets)
* [註解](#comments)
* [資料夾](#folders)
* [專案](#projects)
* [共用](#shares)
* [工作區](#workspaces)
* [其他](#other)

### 資產

* [[!UICONTROL 建立資產]](#create-an-asset)
* [[!UICONTROL 刪除資產]](#delete-an-asset)
* [[!UICONTROL 取得資產]](#get-an-asset)
* [[!UICONTROL 列出資產]](#list-assets)
* [觀看資產已刪除](#watch-asset-deleted)
* [觀看新資產](#watch-new-asset)

#### [!UICONTROL 建立資產] <!--different for v4-->

此動作模組會建立新資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要建立資產的專案之帳戶的ID。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取工作區或對應包含您要建立資產的專案之工作區的ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取專案或對應您要建立資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL路徑] </td> 
   <td> <p>選取您要建立資產的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL檔案名稱] </td> 
   <td> <p>輸入您要用於此資產的檔案名稱。</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">檔案大小 </td> 
    <td> <p>輸入或對應檔案大小（位元組）。</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[！UICONTROL Source URL] </td> 
   <td> <p>如果建立檔案，請輸入您要上傳之檔案的URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL媒體型別] </td> 
   <td> <p>選取此資產的媒體型別。</p> </td> 
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
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要刪除之資產的帳戶ID。</p> </td> 
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
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要擷取之資產的帳戶ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>選取或對應您要擷取的資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出資產]

此搜尋模組會擷取指定專案資料夾中的所有資產。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要列出之資產的帳戶ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回資產的最大數量] </td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的資產最大數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看資產已刪除

此觸發模組會在資產刪除時啟動案例。

選取您要用於此模組的webhook，或按一下Webhook欄位旁的新增，然後輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱] </td> 
   <td> <p>輸入新webhook的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應您要監視已刪除資產的帳戶ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看新資產

此觸發模組會在建立新資產時啟動案例。

選取您要用於此模組的webhook，或按一下Webhook欄位旁的新增，然後輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱] </td> 
   <td> <p>輸入新webhook的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應您要監視新資產的帳戶ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 註解

* [[!UICONTROL 建立註解]](#create-a-comment)
* [[!UICONTROL 刪除註解]](#delete-a-comment)
* [[!UICONTROL 取得註解]](#get-a-comment)
* [[!UICONTROL 清單註解]](#list-comments)
* [[!UICONTROL 更新註解]](#update-a-comment)
* [觀看評論已更新](#watch-comment-updated)
* [觀看新評論](#watch-new-comment)

#### [!UICONTROL 建立註解]

此動作模組會新增註解或回覆至資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要新增註解之資產的帳戶ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取帳戶或對應包含您要新增註解之資產的工作區ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取專案或對應專案ID，專案包含您要新增註解的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL路徑] </td> 
   <td> <p>選取您要新增註解的資產路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Text]</td> 
   <td> <p> 輸入評論或回覆的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL時間戳記] </td> 
   <td> <p>在影片中輸入評論應連結的影格編號。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頁面] </td> 
   <td> <p>如果資產是PDF，請輸入或對應應附加註解的頁面。</p> </td> 
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
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要刪除之註解的帳戶ID。</p> </td> 
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
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要擷取詳細資訊之註解的帳戶ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL註解ID] </td> 
   <td> <p>選取您要擷取有關詳細資訊的註解。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出註解]

此搜尋模組會擷取指定資產的所有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要擷取註解之資產的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應包含您要擷取註解之資產的工作區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取包含您要擷取註解之資產的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL路徑] </td> 
   <td> <p>選取通往您要列出註解之資產的路徑。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[！UICONTROL傳回評論的最大數量] </td> 
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
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要在其中更新評論之資產的專案的帳戶。</p> </td> 
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
  <tr> 
   <td role="rowheader">[！UICONTROL頁面] </td> 
   <td> <p>如果資產是PDF，請輸入或對應附有註解的頁面。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看評論已更新

此觸發模組會在評論更新時啟動案例。

選取您要用於此模組的webhook，或按一下Webhook欄位旁的新增，然後輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱] </td> 
   <td> <p>輸入新webhook的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應您要監視其是否有更新評論的帳戶ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看新評論

此觸發模組會在建立評論時啟動案例。

選取您要用於此模組的webhook，或按一下Webhook欄位旁的新增，然後輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱] </td> 
   <td> <p>輸入新webhook的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應您要監視新評論的帳戶ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 資料夾

#### 建立資料夾

此動作模組會在Frame.io中建立新資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應您要建立資料夾的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應您要建立資料夾的工作區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取您要建立資料夾的位置。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL路徑] </td> 
   <td> <p>選取您要建立資料夾的路徑。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">姓名 </td> 
   <td> <p>輸入或對應新資料夾的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 專案

* [建立專案](#create-a-project)
* [邀請使用者加入Frame.io專案](#invite-users-to-frameio-project)
* [列出專案](#list-projects)

#### 建立專案

此動作模組會在Frame.io中建立新專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應您要建立專案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應您要建立專案的工作區。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">姓名 </td> 
   <td> <p>輸入或對應新專案的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 邀請使用者加入Frame.io專案

此動作模組邀請使用者加入指定的Frame.io專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要邀請使用者加入之專案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應包含您要邀請使用者加入之專案的工作區。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">專案 ID </td> 
   <td> <p>選取或對應您要邀請使用者加入的專案。</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">使用者 ID </td> 
   <td> <p>選取或對應您要邀請加入專案的使用者。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出專案]

此搜尋模組會擷取指定團隊的所有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要擷取專案之資產的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應包含您要擷取專案之資產的工作區。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[！UICONTROL傳回專案的最大數量] </td> 
   <td> <p>輸入或對應最大專案數量
   您希望模組在每個案例執行週期中傳回。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 共用

* [將資產新增至共用連結](#add-an-asset-to-a-share-link)
* [建立共用連結](#create-a-share-link)

#### 將資產新增至共用連結

此動作模組會將資產新增至Frame.io中的共用連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要新增資產的共用連結的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL共用連結ID] </td> 
   <td> <p>選取或對應您要新增資產的共用連結。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[！UICONTROL資產ID] </td> 
   <td> <p>輸入或對應您要新增至共用連結之資產的ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 建立共用連結

此動作模組會在Frame.io中建立新的共用連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應您要建立共用連結的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應您要建立共用連結的工作區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL專案ID] </td> 
   <td> <p>選取或對應您要建立共用連結的專案。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">存取 </td> 
   <td> <p>選取此連結是否具有公開或限制的存取權。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">資產 </td> 
   <td> <p>針對您想要新增至共用連結的每個資產，按一下<b>新增專案</b>並輸入資產識別碼。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">說明 </td> 
   <td> <p>輸入或對應共用連結的說明。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">姓名 </td> 
   <td> <p>輸入或對應共用連結的到期日。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">姓名 </td> 
   <td> <p>輸入或對應新共用連結的名稱。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">姓名 </td> 
   <td> <p>輸入或對應共用連結的密碼。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 工作區

#### 建立工作區

此動作模組會在Frame.io中建立新的工作區

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應您要建立工作區的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL名稱] </td> 
   <td> <p>輸入或對應工作區的新名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 列出工作區

此模組會列出帳戶中的所有工作區。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要擷取工作區之資產的帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[！UICONTROL傳回工作區的最大數目] </td> 
   <td> <p>輸入或對應工作區的最大數目
   您希望模組在每個案例執行週期中傳回。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [進行自訂API呼叫](#make-a-custom-api-call)
* [觀看中繼資料值已更新](#watch-metadata-value-updated)


#### [!UICONTROL 進行自訂API呼叫]

此模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於<code>https://api.frame.io</code>的路徑。 範例： <code> /v4/me</code></p> <p>注意：如需可用端點的清單，請參閱[!DNL Frame.io] API參考。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL方法]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會自動新增授權標頭。</p> </td> 
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

#### 觀看中繼資料值已更新

此觸發模組會在評論更新時啟動案例。

選取您要用於此模組的webhook，或按一下Webhook欄位旁的新增，然後輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook名稱] </td> 
   <td> <p>輸入新webhook的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的指示，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應您要監視更新後中繼資料值的帳戶ID。</p> </td> 
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

---
title: Frame.io 模組
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] 帳戶。'
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: 3cb613c11500dfc94774783ee0b38e6f1768de20
workflow-type: tm+mt
source-wordcount: '4539'
ht-degree: 85%

---

# [!DNL Frame.io] V4 模組

>[!IMPORTANT]
>
>這篇文章說明新版本的 Frame.io 連接器。此連接器用於連接至 Frame.io 版本 4。
>
>關於舊版 Frame.io 連接器的說明，請參閱 [Frame.io 舊版連接器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)。

Adobe Workfront Fusion [!DNL Frame.io] 模組讓您可以監視、建立、更新、檢索或刪除您 [!DNL Frame.io] 帳戶中的資產和註解。

Workfront 提供兩個 Frame.io 連接器，根據您所連接的 Frame.io 版本而定。

| 連接器 | Frame.io 版本 |
|---|---|
| Frame.io | V4 |
| Frame.io (舊版) | V3 |

關於舊版 Frame.io 連接器的說明，請參閱 [Frame.io 舊版連接器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)。


關於 Frame.io 連接器的影片簡介，請參閱：

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

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
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>連接器型 (舊版)：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用 [!DNL Frame.io] 模組，您必須擁有 [!DNL Frame.io] 帳戶

## Frame.io API 資訊

Frame.io 連接器會使用以下項目：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://api.frame.io/v4</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 版本</td> 
   <td> v2 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.0.76</td> 
  </tr>
 </tbody> 
 </table>

## 將 [!DNL Frame.io] 連接至 [!UICONTROL Adobe Workfront Fusion]

您可以利用使用者認證進行自動連線、手動建立使用者認證連線，或建立伺服器對伺服器連線。

* [利用使用者認證進行自動連線](#connect-automatically-with-user-credentials#)
* [手動建立使用者認證連線](#create-a-user-credentials-connection-manually)
* [建立伺服器對伺服器連線](#create-a-server-to-server-connection)

### 利用使用者認證進行自動連線

若您登入 Frame.io，此方法會自動建立連線，或將您連線至 Frame.io 登入頁面以便您登入。

1. 在任何 Frame.io 模組中，按一下「連線」方框旁的「**[!UICONTROL 新增]**」。
1. 輸入此連線的名稱。
1. 按一下「**繼續**」。
1. 如果系統提示您登入 Frame.io 帳戶，請登入。
1. 若您屬於多個 Frame.io 組織，請選取您要用於此連線的組織。

已建立連線。

### 手動建立使用者認證連線

您可以透過登入 Frame.io、提供用戶端 ID 或用戶端密碼來建立使用者認證連線。

若要建立伺服器對伺服器連線，您必須先在 Adobe Developer Console 中設定應用程式。

* [在 Adobe Developer Console 中建立使用者認證](#create-user-credentials-in-the-adobe-developer-console)
* [設定使用者驗證連線](#configure-a-user-authentication-connection)

#### 在 Adobe Developer Console 中建立使用者認證

若在 Adobe Developer Console 專案中尚未擁有伺服器對伺服器認證，您可以建立這些認證。

1. 開啟 [Adobe Developer Console](https://developer.adobe.com/)。
1. 在 Adobe Developer Console 中選取此連線要使用的現有專案

   或

   在 Adobe Developer Console 中建立新專案。相關說明請參閱[建立空白專案](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)。

1. 在專案概觀頁面或開始使用新專案頁面上，按一下「**新增 API**」。
1. 在開啟的頁面上，找到「**Frame.io API**」並按一下。
1. 在選取驗證類型頁面上，選取「**使用者驗證**」，然後按一下「**下一步**」。
1. 在新增使用者驗證認證頁面上，選取「**OAuth 網頁應用程式**」，然後按一下「**下一步**」。
1. 在設定 OAuth 網頁應用程式認證頁面上，輸入下列內容：   <table style="table-layout:auto">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL 預設重新導向 URI]</td>
          <td>
            <p><code>https://oauth.app.workfrontfusion.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 重新導向 URI 模式]</td>
          <td>
            <p><code>https://oauth\.app\.workfrontfusion\.com/oauth/cb/frame-io2</code></p>
          </td>
        </tr>
       </tbody>
    </table>
1. 按一下「**下一步**」。
1. 按一下「**儲存已設定的 API**」。
1. 在產品頁面上，按一下您剛建立的認證卡片。

   您可以在此處找到您的用戶端 ID 和用戶端密碼。

>[!NOTE]
>
> 我們建議您在 Adobe Workfront Fusion 中開始設定連線時，保持此視窗開啟。您可以複製用戶端 ID，並從這個頁面檢索及複製用戶端密碼，將其貼上到連線欄位。


#### 設定使用者驗證連線

1. 在任何 Frame.io 模組中，按一下「連線」方框旁的「**[!UICONTROL 新增]**」。
1. 在「建立連線」方框中，按一下「**顯示進階設定**」。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL 連線類型]</td>
          <td>
            <p>選取「<b>IMS 使用者驗證</b>」。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 連線名稱]</td>
          <td>
            <p>輸入此連線的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端 ID]。此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。<p>關於建立認證的說明，請參閱這篇文章中的<a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立使用者認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端密碼]。此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。<p>關於建立認證的說明，請參閱這篇文章中的<a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立使用者認證</a>。</p>
        </tr>
       </tbody>
    </table>
1. 如果系統提示您登入 Frame.io 帳戶，請登入。
1. 若您屬於多個 Frame.io 組織，請選取您要用於此連線的組織。

已建立連線。


### 建立伺服器對伺服器連線

若要建立伺服器對伺服器連線，您必須先在 Adobe Developer Console 中設定應用程式。

* [在 Adobe Developer Console 中建立伺服器對伺服器認證](#create-server-to-server-credentials-in-the-adobe-developer-console)
* [設定伺服器對伺服器連線](#configure-a-server-to-server-connection)

#### 在 Adobe Developer Console 中建立伺服器對伺服器認證

若在 Adobe Developer Console 專案中尚未擁有伺服器對伺服器認證，您可以建立這些認證。

1. 開啟 [Adobe Developer Console](https://developer.adobe.com/)。
1. 在 Adobe Developer Console 中選取此連線要使用的現有專案

   或

   在 Adobe Developer Console 中建立新專案。相關說明請參閱[建立空白專案](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)。

1. 在專案概觀頁面或開始使用新專案頁面上，按一下「**新增 API**」。
1. 在開啟的頁面上，找到「**Frame.io API**」並按一下。
1. 在選取驗證類型頁面上，選取「**伺服器對伺服器驗證**」，然後按一下「**下一步**」。
1. 輸入此認證的名稱。這樣一來，您稍後在 Adobe Admin Console 的「API 認證」區域中即可找到認證。
1. 按一下「**下一步**」。
1. 在選取產品設定檔頁面上，選取包括您要連接之 Frame.io 帳戶的產品設定檔。
1. 按一下「**儲存已設定的 API**」。
1. 在產品頁面上，按一下您剛建立的認證卡片。

   您可以在此處找到您的用戶端 ID 和用戶端密碼。

>[!NOTE]
>
> 我們建議您在 Adobe Workfront Fusion 中開始設定連線時，保持此視窗開啟。您可以複製用戶端 ID，並從這個頁面檢索及複製用戶端密碼，將其貼上到連線欄位。


#### 設定伺服器對伺服器連線

1. 在任何 Frame.io 模組中，按一下「連線」方框旁的「**[!UICONTROL 新增]**」。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL 連線類型]</td>
          <td>
            <p>選取「<b>IMS 伺服器對伺服器</b>」。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 連線名稱]</td>
          <td>
            <p>輸入此連線的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端 ID]。此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。<p>關於建立認證的說明，請參閱這篇文章中的<a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立伺服器對伺服器認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端密碼]。此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。<p>關於建立認證的說明，請參閱這篇文章中的<a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立伺服器對伺服器認證</a>。</p>
        </tr>
       </tbody>
    </table>
1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。




## [!DNL Frame.io] 模組及其欄位

當您設定 [!DNL Frame.io] 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 [!DNL Frame.io] 欄位。在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [資產](#assets)
* [註解](#comments)
* [資料夾](#folders)
* [專案](#projects)
* [共用](#shares)
* [工作區](#workspaces)
* [中繼資料](#metadata)
* [其他](#other)

### 資產

* [[!UICONTROL 建立資產]](#create-an-asset)
* [[!UICONTROL 刪除資產]](#delete-an-asset)
* [[!UICONTROL 取得資產]](#get-an-asset)
* [[!UICONTROL 列出資產清單]](#list-assets)
* [監視資產被刪除](#watch-asset-deleted)
* [監視新資產](#watch-new-asset)

#### [!UICONTROL 建立資產] <!--different for v4-->

此動作模組會建立新資產。 您可以上傳本機檔案，或提供遠端檔案的URL，以便從中建立資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要建立資產之專案的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取包含您要建立資產之專案的工作區，或對應該工作區的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取您要建立資產的專案，或對應該專案的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取您要建立資產的路徑。</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">[!UICONTROL File Name] </td> 
   <td> <p>Enter the name of the file that you want to use for this asset.</p> </td> 
  </tr> -->
    <tr> 
    <td role="rowheader">上傳型別 </td> 
    <td> <p>選取您是從本機檔案還是從遠端生命週期建立資產。</p> </td> 
   </tr>
    <tr> 
    <td role="rowheader">檔案大小 </td> 
    <td> <p>如果您要上傳本機檔案，請輸入或對應檔案大小（位元組）。</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL 來源 URL] </td> 
   <td> <p>如果從遠端檔案建立資產，請輸入您要上傳之檔案的URL。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 來源檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱。</p> </td> 
  </tr> 
<!--  <tr> 
   <td role="rowheader">[!UICONTROL Media type] </td> 
   <td> <p>Select the media type for this asset.</p> </td> 
  </tr> -->
  </tbody> 
</table>

#### [!UICONTROL 建立資產（舊版）] <!--different for v4-->

此動作模組會建立新資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要建立資產之專案的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取包含您要建立資產之專案的工作區，或對應該工作區的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取您要建立資產的專案，或對應該專案的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取您要建立資產的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案名稱] </td> 
   <td> <p>輸入您要用於此資產的檔案之名稱。</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">檔案大小 </td> 
    <td> <p>輸入或對應檔案大小，以位元組為單位。</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL 來源 URL] </td> 
   <td> <p>若要建立檔案，請輸入要上傳之檔案的 URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 媒體類型] </td> 
   <td> <p>選取此資產的媒體類型。</p> </td> 
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
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要刪除的資產的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
   <td> <p>選取或對應您要刪除的資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得資產]

此動作模組會檢索資產詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要檢索的資產的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
   <td> <p>選取或對應您要檢索的資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出資產清單]

此搜尋模組會檢索指定的專案資料夾中的所有資產。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要列出清單之資產的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回資產的最大數量] </td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 監視資產被刪除

此觸發程序模組會在刪除資產時啟動一個情境。

選取您要用於此模組的 Webhook，或按一下「Webhook」欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取您要監視是否有資產被刪除的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 監視新資產

此觸發程序模組會在建立新資產時啟動一個情境。

選取您要用於此模組的 Webhook，或按一下「Webhook」欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取您要監視是否有新資產的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 註解

* [[!UICONTROL 建立註解]](#create-a-comment)
* [[!UICONTROL 刪除註解]](#delete-a-comment)
* [[!UICONTROL 取得註解]](#get-a-comment)
* [[!UICONTROL 列出註解清單]](#list-comments)
* [[!UICONTROL 更新註解]](#update-a-comment)
* [監視註解更新](#watch-comment-updated)
* [監視新註解](#watch-new-comment)

#### [!UICONTROL 建立註解]

此動作模組會新增新註解或回覆資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要新增註解的資產的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取包含您要新增註解之資產的工作區，或對應該工作區的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取包含您要新增註解的資產的專案，或對應該專案的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取您要新增註解的資產的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 文字]</td> 
   <td> <p> 輸入註解或回覆的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 時間戳記] </td> 
   <td> <p>輸入註解應連結的影片影格編號。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 頁面] </td> 
   <td> <p>若此資產為 PDF，請輸入或對應要附加註解的頁面。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除註解]

此動作模組會刪除現有的註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要刪除的註解的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解 ID] </td> 
   <td> <p>輸入或對應您要刪除的註解的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得註解]

此動作模組會檢索指定註解的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取包含您要從中檢索詳細資訊的註解之帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解 ID] </td> 
   <td> <p>選取您要檢索相關詳細資訊的註解。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出註解清單]

此搜尋模組會檢索指定資產的所有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要從中檢索註解的資產的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取或對應包含您要從中檢索註解的資產的工作區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取包含您要從中檢索註解的資產的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取前往您要列出註解清單的資產的路徑。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回註解的最大數量] </td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大註解數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新註解]

此動作模組會編輯現有的註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要更新註解的資產之專案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解 ID] </td> 
   <td> <p>選取您要更新的註解。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 文字]</td> 
   <td> <p> 輸入註解的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 時間戳記] </td> 
   <td> <p>輸入註解連結的影片影格編號。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 頁面] </td> 
   <td> <p>若此資產為 PDF，請輸入或對應要附加註解的頁面。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 監視註解更新

此觸發程序模組會在註解更新時啟動一個情境。

選取您要用於此模組的 Webhook，或按一下「Webhook」欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取您要監視是否有更新註解的帳戶，或對應其帳戶的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 監視新註解

此觸發程序模組會在建立註解時啟動一個情境。

選取您要用於此模組的 Webhook，或按一下「Webhook」欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取您要監視是否有新註解的帳戶，或對應該帳戶的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 資料夾

#### 建立資料夾

此動作模組會在 Frame.io 中建立新資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立資料夾的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取或對應您要建立資料夾的工作區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取您要建立資料夾的位置。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取要建立資料夾的路徑。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應新資料夾的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 專案

* [建立專案](#create-a-project)
* [邀請使用者加入 Frame.io 專案](#invite-users-to-frameio-project)
* [列出專案清單](#list-projects)

#### 建立專案

此動作模組會在 Frame.io 中建立新專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立專案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取或對應您要建立專案的工作區。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應新專案的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 邀請使用者加入 Frame.io 專案

此動作模組會邀請使用者加入指定的 Frame.io 專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要邀請使用者加入的專案之帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取或對應包含您要邀請使用者加入的專案之工作區。</p> </td> 
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

#### [!UICONTROL 列出專案清單]

此搜尋模組會檢索指定團隊的所有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要從中檢索專案的資產之帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取或對應包含您要從中檢索專案的資產之工作區。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回專案的最大數量] </td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大專案數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 共用

* [將資產新增至共用連結](#add-an-asset-to-a-share-link)
* [建立共用連結](#create-a-share-link)

#### 將資產新增至共用連結

此動作模組會將資產新增至 Frame.io 中的共用連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要加入資產的共用連結之帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 共用連結 ID] </td> 
   <td> <p>選取或對應您要加入資產的共用連結。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
   <td> <p>輸入或對應您要新增至共用連結的資產之 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 建立共用連結

此動作模組會在 Frame.io 中建立新的共用連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立共用連結的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取或對應您要建立共用連結的工作區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取或對應您要建立共用連結的專案。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">存取權 </td> 
   <td> <p>選取此連結的存取權為公開或受限制。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">資產 </td> 
   <td> <p>針對您要新增至共用連結的每個資產，按一下「<b>新增項目</b>」並輸入資產 ID。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">說明 </td> 
   <td> <p>輸入或對應共用連結的說明。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應共用連結的過期日期。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應新共用連結的名稱。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應共用連結的密碼短語。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 工作區

#### 建立工作區

此動作模組會在 Frame.io 中建立新工作區。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立工作區的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 名稱] </td> 
   <td> <p>輸入或對應工作區的新名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 列出工作區清單

此模組會列出帳戶中所有工作區的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要從中檢索工作區的資產之帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回工作區的最大數量] </td> 
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大工作區數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 中繼資料

* [建立帳戶層級欄位](#create-an-account-level-field)
* [刪除帳戶層級欄位](#delete-an-account-level-field)
* [取得中繼資料](#get-metadata)
* [列出帳戶層級欄位](#list-account-level-fields)
* [更新科目層次欄位定義](#update-an-account-level-field-definition)
* [在多個檔案中更新中繼資料](#update-metadata-across-multiple-files)

#### 建立帳戶層級欄位

此動作模組會建立及設定新的帳戶層級中繼資料欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立中繼資料的帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">欄位類型 </td> 
   <td> <p>選取您要建立的中繼資料欄位型別，然後設定該欄位的選項。</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應新欄位的名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 刪除帳戶層級欄位

此動作模組會刪除單一帳戶層級中繼資料欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要刪除之中繼資料欄位的帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">欄位定義ID </td> 
   <td> <p>輸入或對應您要刪除之欄位的ID。 您可以使用清單帳戶層級欄位模組來尋找欄位ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 取得中繼資料

此動作模組會擷取Frame.io中檔案的中繼資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要擷取中繼資料之檔案的帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">檔案ID </td> 
   <td> <p>輸入或對應您要擷取中繼資料的檔案ID。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">顯示null </td> 
   <td> <p>啟用此選項以在輸出中包含值為null的欄位。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 列出帳戶層級欄位

此模組會擷取指定帳戶的帳戶層級中繼資料欄位清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要列出其欄位的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回協定的最大數目]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大欄位數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 更新科目層次欄位定義

此模組會更新單一現有中繼資料欄位的定義。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立中繼資料的帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">欄位定義ID </td> 
   <td> <p>輸入或對應您要更新的欄位ID。 您可以使用清單帳戶層級欄位模組來尋找欄位ID。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">欄位類型 </td> 
   <td> <p>如果您想要變更欄位的欄位型別，請選取您要建立的中繼資料欄位型別，然後設定該欄位的選項。</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應欄位的新名稱。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 在多個檔案中更新中繼資料

此模組會以您指定的值更新一或多個檔案的中繼資料欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要更新中繼資料之檔案的帳戶。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL 工作區 ID] </td> 
   <td> <p>選取包含您要建立資產之專案的工作區，或對應該工作區的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取您要建立資產的專案，或對應該專案的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案ID] </td> 
   <td> <p>針對您要更新中繼資料的每個檔案，按一下<b>新增專案</b>，然後輸入或對應檔案的識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 值] </td> 
   <td> <p>針對您想要更新中繼資料的每個欄位，按一下<b>新增專案</b>，然後輸入或對應欄位定義的識別碼，以及您想要放在該欄位中的值。 「檔案ID」欄位中指定的所有檔案都會使用此欄位值更新。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [進行自訂的 API 呼叫](#make-a-custom-api-call)
* [觀看活動](#watch-events)
* [監視後設資料值更新](#watch-metadata-value-updated)


#### [!UICONTROL 進行自訂的 API 呼叫]

您可以透過此模組進行自訂的 API 呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於 <code>https://api.frame.io</code> 的路徑。範例： <code> /v4/me</code></p> <p>注：如需可用端點的清單，請參閱 [!DNL Frame.io] API 參考資料。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion 會自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串] </td> 
   <td> <p>輸入請求查詢字串。對於您要包括在查詢字串中的每個參數，按一下<b>[!UICONTROL 新增項目]</b>，並輸入此欄位的名稱和所需的值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看活動

此即時觸發模組會在選取的事件發生在Frame.io中時啟動案例。

您可以使用現有的webhook，也可以建立新的。

若要建立新的 Webhook：

1. 按一下 Webhook 欄位旁的「**新增**」。
1. 填寫下列資訊：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
     <td role="rowheader">Webhook名稱 </td> 
      <td> <p>輸入新 Webhook 的名稱。</p> </td> 
     </tr> 
     <tr> 
       <td role="rowheader">[!UICONTROL 連線] </td> 
       <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
     </tr> 
     <tr> 
     <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
      <td> <p>選取或對應包含您要觀看活動之工作區的帳戶。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 工作區 ID]</td> 
      <td> <p>輸入您要觀看活動之工作區的ID。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 事件]</td> 
      <td> <p>選取您要觸發此模組的事件</p> </td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**儲存**&#x200B;以儲存webhook並返回模組。
1. 按一下「觀看事件」模組中的&#x200B;**確定**&#x200B;以儲存設定。


#### 監視後設資料值更新

此觸發程序模組會在註解更新時啟動一個情境。

選取您要用於此模組的 Webhook，或按一下「Webhook」欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 的名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>關於建立與 [!DNL Frame.io] 的連線的說明，請參閱這篇文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">將 [!DNL Frame.io] 連接至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取您要監視後設資料值是否有更新的帳戶，或對應該帳戶的 ID。</p> </td> 
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

---
title: Frame.io 模組
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] 帳戶。'
author: Becky
feature: Workfront Fusion
exl-id: 16d32ebd-1807-495e-8aaf-27346056ec71
source-git-commit: 52dbf75ebb65a1de1a7a86619af4c7633e0cbe03
workflow-type: tm+mt
source-wordcount: '4399'
ht-degree: 87%

---

# [!DNL Frame.io] V4 模組

>[!IMPORTANT]
>
>此文章說明新版本的 Frame.io 連接器。此連接器是用來連線至 Frame.io 版本 4。
>
>如需有關舊版 Frame.io 連接器說明，請參閱 [Frame.io 舊版連接器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)。

Adobe Workfront Fusion [!DNL Frame.io] 模組可讓您監視、建立、更新、檢索或刪除您 [!DNL Frame.io] 帳戶中的資產和註解。

Workfront 提供兩個 Frame.io 連接器，會根據您所連線的 Frame.io 版本而定。

| 連接器 | Frame.io 版本 |
|---|---|
| Frame.io | V4 |
| Frame.io (舊版) | V3 |

如需有關舊版 Frame.io 連接器說明，請參閱 [Frame.io 舊版連接器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)。


如需有關 Frame.io 連接器的影片簡介，請參閱：

* [Frame.io](https://video.tv.adobe.com/v/3427032/){target=_blank}

## 存取需求

+++ 展開以查看此文章中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront 套件</td> 
   <td> <p>任何 Adobe Workfront Workflow 套件及任何 Adobe Workfront 自動化和整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime 和 Select 套件，以及額外購買的 Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront 授權</td> 
   <td> <p>標準</p><p>工作或更高層級</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權需求</p>
   <p>連接器型 (舊版)：適用於工作自動化和整合的 Workfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 套件，但不包括 Workfront 自動化和整合，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需有關此表格資訊的詳細資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取需求[。

如需有關 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用 [!DNL Frame.io] 模組，您必須擁有 [!DNL Frame.io] 帳戶

## Frame.io API 資訊

Frame.io 連接器使用下列專案：

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

## 將 [!DNL Frame.io] 連線至 [!UICONTROL Adobe Workfront Fusion]

您可以利用使用者認證進行自動連線、手動建立使用者認證連線，或建立伺服器對伺服器連線。

* [利用使用者認證進行自動連線](#connect-automatically-with-user-credentials#)
* [手動建立使用者認證連線](#create-a-user-credentials-connection-manually)
* [建立伺服器對伺服器連線](#create-a-server-to-server-connection)

### 利用使用者認證進行自動連線

若您登入 Frame.io，此方法會自動建立連線，或將您連線至 Frame.io 登入頁面以便您登入。

1. 在任何 Frame.io 模組中，按一下「連線」方框旁的「**[!UICONTROL 新增]**」。
1. 輸入此連線的名稱。
1. 按一下「**繼續**」。
1. 如果系統提示您登入 Frame.io 帳戶，請進行此步驟。
1. 若您屬於多個 Frame.io 組織，請選取要用於此連線的組織。

已建立此連線。

### 手動建立使用者認證連線

您可以透過登入 Frame.io、提供用戶端 ID 或用戶端密碼來建立使用者認證連線。

若要建立伺服器對伺服器連線，您必須先在 Adobe Developer Console 中設定應用程式。

* [在 Adobe Developer Console 中建立使用者認證](#create-user-credentials-in-the-adobe-developer-console)
* [設定使用者驗證連線](#configure-a-user-authentication-connection)

#### 在 Adobe Developer Console 中建立使用者認證

若您在 Adobe Developer Console 專案中尚未擁有伺服器對伺服器認證，則可以建立這些認證。

1. 開啟 [Adobe Developer Console](https://developer.adobe.com/)
1. 在 Adobe Developer Console 中選取要用於此連線的現有專案

   或

   在 Adobe Developer Console 中建立新專案。如需相關說明，請參閱[建立空白專案](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)。

1. 在專案概觀頁面或開始使用新專案頁面上，按一下「**新增 API**」。
1. 在開啟的頁面上，找到 **Frame.io API** 並點選。
1. 在「選取驗證類別」頁面上，選取「**使用者驗證**」，並按一下「**下一步**」。
1. 在「新增使用者驗證認證」頁面上，選取「**OAuth 網頁應用程式**」，並按一下「**下一步**」。
1. 在「設定 OAuth 網頁應用程式認證」頁面上，請輸入下列內容：   <table style="table-layout:auto">
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
> 我們建議您在 Adobe Workfront Fusion 中開始設定連線時，保持此視窗開啟。您可以複製此用戶端 ID，並從此頁面檢索及複製用戶端密碼，將其貼上到此連線欄位。


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
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端 ID]。此欄位可在 [!DNL Adobe Developer Console]的 [!UICONTROL 認證詳細資訊] 區段中找到。<p>如需建立認證相關說明，請參閱此文章中的<a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立使用者認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端密碼]。此欄位可在 [!DNL Adobe Developer Console]的 [!UICONTROL 認證詳細資訊] 區段中找到。<p>如需建立認證相關說明，請參閱此文章中<a href="#create-user-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立使用者認證</a>。</p>
        </tr>
       </tbody>
    </table>
1. 如果系統提示您登入 Frame.io 帳戶，請進行此步驟。
1. 若您屬於多個 Frame.io 組織，請選取要用於此連線的組織。

已建立此連線。


### 建立伺服器對伺服器連線

若要建立伺服器對伺服器連線，您必須先在 Adobe Developer Console 中設定應用程式。

* [在 Adobe Developer Console 中建立伺服器對伺服器認證](#create-server-to-server-credentials-in-the-adobe-developer-console)
* [設定伺服器對伺服器連線](#configure-a-server-to-server-connection)

#### 在 Adobe Developer Console 中建立伺服器對伺服器認證

若您在 Adobe Developer Console 專案中尚未擁有伺服器對伺服器認證，則可以建立這些認證。

1. 開啟 [Adobe Developer Console](https://developer.adobe.com/)
1. 在 Adobe Developer Console 中選取要用於此連線的現有專案

   或

   在 Adobe Developer Console 中建立新專案。如需相關說明，請參閱[建立空白專案](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty)。

1. 在專案概觀頁面或開始使用新專案頁面上，按一下「**新增 API**」。
1. 在開啟的頁面上，找到 **Frame.io API** 並點選。
1. 在「選取驗證類別」頁面上，選取「**伺服器對伺服器驗證**」，並按一下「**下一步**」。
1. 輸入此認證名稱。此步驟可讓您稍後在 Adobe Admin Console 的 API 認證區域中識別此認證。
1. 按一下「**下一步**」。
1. 在「選取產品設定檔」頁面上，選取包括您要連線的 Frame.io 帳戶的產品設定檔。
1. 按一下「**儲存已設定的 API**」。
1. 在產品頁面上，按一下您剛建立的認證卡片。

   您可以在此處找到您的用戶端 ID 和用戶端密碼。

>[!NOTE]
>
> 我們建議您在 Adobe Workfront Fusion 中開始設定連線時，保持此視窗開啟。您可以複製此用戶端 ID，並從此頁面檢索及複製用戶端密碼，將其貼上到此連線欄位。


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
            <p>選取「<b>IMS 伺服器至伺服器</b>」。</p>
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
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端 ID]。此欄位可在 [!DNL Adobe Developer Console]的 [!UICONTROL 認證詳細資訊] 區段中找到。<p>如需建立認證相關說明，請參閱此文章中的<a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立伺服器對伺服器認證</a>。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
          <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端密碼]。此欄位可在 [!DNL Adobe Developer Console]的 [!UICONTROL 認證詳細資訊] 區段中找到。<p>如需建立認證相關說明，請參閱此文章中的<a href="#create-server-to-server-credentials-in-the-adobe-developer-console" class="MCXref xref">在 Adobe Developer Console 中建立伺服器對伺服器認證</a>。</p>
        </tr>
       </tbody>
    </table>
1. 按一下「**[!UICONTROL 繼續]**」來儲存連線並返回此模組。




## [!DNL Frame.io] 模組及其欄位

當您設定 [!DNL Frame.io] 模組時，Workfront Fusion 會顯示下列欄位。除了這些欄位以外，可能還會顯示其他 [!DNL Frame.io] 欄位，取決於您在此應用程式或服務中的存取層級等因素。模組中的粗體標題表示必填欄位。

若在欄位或函數上方看到對應按鈕，您可以使用此按鈕來設定欄位的變數和函式。如需詳細資訊，請參閱[將資訊從一個模組對應至另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

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
* [[!UICONTROL 獲得資產]](#get-an-asset)
* [[!UICONTROL 列出資產]](#list-assets)
* [觀看已刪除的資產](#watch-asset-deleted)
* [觀看新資產](#watch-new-asset)

#### [!UICONTROL 建立資產] <!--different for v4-->

此動作模組會建立新資產。 您可以上傳本機檔案，或提供遠端檔案的URL，以便從中建立資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取此帳戶或對應包含您要建立資產專案的帳戶 ID。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取此工作區或對應包含您要建立資產專案的工作區 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取此專案或對應您要建立資產的專案 ID。</p> </td> 
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
   <td>[！UICONTROL Source檔案]</td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取此帳戶或對應包含您要建立資產專案的帳戶 ID。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取此工作區或對應包含您要建立資產專案的工作區 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取此專案或對應您要建立資產的專案 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取您要建立資產的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案名稱] </td> 
   <td> <p>輸入您要用於此資產的檔案名稱。</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">檔案大小 </td> 
    <td> <p>輸入或對應此檔案大小 (以位元組為單位)。</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[!UICONTROL 來源 URL] </td> 
   <td> <p>若要建立檔案，請輸入您要上傳檔案的 URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 媒體類別] </td> 
   <td> <p>選取此資產的媒體類別。</p> </td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應包含您要刪除資產的帳戶 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
   <td> <p>選取或對應您要刪除的資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 獲得資產]

此動作模組會檢索資產詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應包含您要檢索資產的帳戶 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
   <td> <p>選取或對應您要檢索的資產。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出資產]

此搜尋模組會檢所指定專案資料夾中的所有資產。

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應包含您要列出資產的帳戶 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 傳回資產的最大數量] </td> 
   <td> <p>輸入或對應您希望此模組在每個情境執行週期中傳回的最大資產數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看已刪除的資產

此觸發模組會在資產已刪除時開始情境。

選取您要用於此模組的 Webhook，或按一下 Webhook 欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應您要觀看已刪除資產的帳戶 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看新資產

此觸發模組會在建立新資產時開始情境。

選取您要用於此模組的 Webhook，或按一下 Webhook 欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應您要觀看新資產的帳戶 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 註解

* [[!UICONTROL 建立註解]](#create-a-comment)
* [[!UICONTROL 刪除註解]](#delete-a-comment)
* [[!UICONTROL 獲得註解]](#get-a-comment)
* [[!UICONTROL 列出註解]](#list-comments)
* [[!UICONTROL 更新註解]](#update-a-comment)
* [觀看已更新的註解](#watch-comment-updated)
* [觀看新註解](#watch-new-comment)

#### [!UICONTROL 建立註解]

此動作模組會新增新註解或回覆資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應包含您要新增註解的資產帳戶 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取帳戶或對應包含您要新增註解的資產 Workspace ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取專案或對應包含您要新增註解的資產專案 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取您要新增註解的資產路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 文字]</td> 
   <td> <p> 輸入註解或回覆的文字內容。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 時間戳記] </td> 
   <td> <p>輸入影片中應連結註解的時間格編號。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 頁面] </td> 
   <td> <p>若此資產為 PDF，請輸入或對應應附加註解的頁面。</p> </td> 
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
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應包含您要刪除註解的帳戶 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解 ID] </td> 
   <td> <p>輸入或對應您要刪除註解的 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 獲得註解]

此動作模組會檢索指定註解的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應包含您要檢索相關詳細資訊的註解帳戶 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解 ID] </td> 
   <td> <p>選取您要檢索相關詳細資訊的註解。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出註解]

此搜尋模組會檢索指定資產的所有註解。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要檢索註解的資產帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應包含您要檢索註解的資產 Workspace。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取包含您要檢索註解的資產專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取引導至您要列出註解的資產路徑。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回註解的最大數量] </td> 
   <td> <p>輸入或對應您希望此模組在每個情境執行週期中傳回的最大註解數量。</p> </td> 
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
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要更新註解的資產專案帳戶。</p> </td> 
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
   <td> <p>輸入影片中要連結註解的時間格編號。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 頁面] </td> 
   <td> <p>若此資產為 PDF，請輸入或對應要附加註解的頁面。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看已更新的註解

此觸發模組會在註解更新時開始情境。

選取您要用於此模組的 Webhook，或按一下 Webhook 欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應您要觀看已更新註解的帳戶 ID。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看新註解

此觸發模組會在註解建立時開始情境。

選取您要用於此模組的 Webhook，或按一下 Webhook 欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應您要觀看新註解的帳戶 ID。</p> </td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立資料夾的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應您要建立資料夾的 Workspace。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取您要建立資料夾的位置。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選取您要建立資料夾的路徑。</p> </td> 
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
* [列出專案](#list-projects)

#### 建立專案

此動作模組會在 Frame.io 中建立新專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立專案的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應您要建立專案的 Workspace。</p> </td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要邀請使用者加入的專案帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應包含您要邀請使用者加入的專案工作區。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">專案 ID </td> 
   <td> <p>選取或對應您要邀請使用者加入的專案。</p> </td> 
  </tr> 
  </tr> 
   <tr> 
   <td role="rowheader">使用者 ID </td> 
   <td> <p>選取或對應您要邀請使用者加入的專案。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 列出專案]

此搜尋模組會檢索指定團隊的所有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要檢索專案的資產帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應包含您要檢索專案的資產 Workspace。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回專案的最大數量] </td> 
   <td> <p>輸入或對應您希望此模組在每個情境執行週期中傳回的最大專案數量。</p> </td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要新增資產至共用連結的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 共用連結 ID] </td> 
   <td> <p>選取或對應您要新增資產的共用連結。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
   <td> <p>輸入或對應您要新增至共用連結的資產 ID。</p> </td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立共用連結的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取或對應您要建立共用連結的工作區。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取或對應您要建立共用連結的專案。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">存取 </td> 
   <td> <p>選取此連結的存取權是否公開或限制。</p> </td> 
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
   <td> <p>輸入或對應共用連結的到期日。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">名稱 </td> 
   <td> <p>輸入或對應此新共用連結的名稱。</p> </td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要建立工作區的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 名稱] </td> 
   <td> <p>輸入或對應此工作區的新名稱。</p> </td> 
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
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要檢索工作區的資產帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回工作區的最大數量] </td> 
   <td> <p>輸入或對應您希望此模組在每個情境執行週期中傳回的最大工作區數量。</p> </td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應您要列出其欄位的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL傳回協定的最大數目]</td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
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
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取或對應包含您要更新中繼資料之檔案的帳戶。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL Workspace ID] </td> 
   <td> <p>選取此工作區或對應包含您要建立資產專案的工作區 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取此專案或對應您要建立資產的專案 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL檔案ID] </td> 
   <td> <p>針對您要更新中繼資料的每個檔案，按一下<b>新增專案</b>，然後輸入或對應檔案的識別碼。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL值] </td> 
   <td> <p>針對您想要更新中繼資料的每個欄位，按一下<b>新增專案</b>，然後輸入或對應欄位定義的識別碼，以及您想要放在該欄位中的值。 「檔案ID」欄位中指定的所有檔案都會使用此欄位值更新。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [進行自訂 API 呼叫](#make-a-custom-api-call)
* [觀看已更新的後設資料值](#watch-metadata-value-updated)


#### [!UICONTROL 進行自訂 API 呼叫]

此模組可讓您執行自訂 API 呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於 <code>https://api.frame.io</code> 的路徑。範例： <code> /v4/me</code></p> <p>注意：如需可用端點的清單，請參閱 [!DNL Frame.io] API 參考。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL 方法]</p> </td> 
   <td> <p>選取所需的 HTTP 要求方法，來設定 API 呼叫。如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增請求的標頭。</p> <p>例如： <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion 會自動新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串] </td> 
   <td> <p>輸入此請求查詢字串。針對您要包括在查詢字串中的每個參數，按一下 <b>[!UICONTROL 新增項目]</b>，並輸入此欄位名稱和必要值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 內文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的內文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外側。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看已更新的後設資料值

此觸發模組會在註解更新時開始情境。

選取您要用於此模組的 Webhook，或按一下 Webhook 欄位旁的「新增」，並輸入下列資訊：

<table style="table-layout:auto"> 
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱] </td> 
   <td> <p>輸入新 Webhook 名稱。</p> </td> 
  </tr> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連線] </td> 
   <td>如需建立 [!DNL Frame.io] 連線的相關說明，請參閱此文章中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線 [!DNL Frame.io] 至 Adobe Workfront Fusion</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選取帳戶或對應您要觀看已更新後設資料的帳戶 ID。</p> </td> 
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

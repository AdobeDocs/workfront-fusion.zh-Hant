---
title: Frame.io模組
description: ' [!DNL Adobe Workfront Fusion Frame].io modules enable you to monitor, create, update, retrieve, or delete assets and comments in your [!DNL Frame.io] 帳戶。'
author: Becky
feature: Workfront Fusion
source-git-commit: c0b08b206f69d6af3b629c5d31cc0b840edea766
workflow-type: tm+mt
source-wordcount: '2167'
ht-degree: 1%

---

# [!DNL Frame.io] Beta (V4)模組

>[!IMPORTANT]
>
>本文說明Frame.io聯結器的新（測試版）版本。 此聯結器用於連線至Frame.io版本4。
>
>有關舊版 Frame.io 連接器的說明，請參閱 [Frame.io 舊版連接器](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/frame-io-modules.md)。

這些[!DNL Adobe Workfront Fusion][!DNL Frame.io]模組使您能够監視、创建、更新、檢索或刪除帳戶中的[!DNL Frame.io]資產和評論。

Workfront 根據要連接到的 Frame.io 版本提供兩個 Frame.io 連接器。

| 連接器 | Frame.io 版本 |
|---|---|
| Frame.io (Beta) | V4 |
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
   <td role="rowheader">Adobe Systems Workfront 許可證</td> 
   <td> <p>新：標準</p><p>或</p><p>目前：工作或以上</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權**</td> 
   <td>
   <p>當前： 無工作前沿融合許可證要求</p>
   <p>或</p>
   <p>舊版：工作自動化與集成的工作流融合 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增功能：</p> <ul><li>Select 或 Prime Workfront 套裝： 您的組織必須購買 Adobe Systems Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前： 您的組織必須購買 Adobe Systems Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

有關此表中資訊的更多詳細資訊，請參閱 [文檔中](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)的訪問要求。

有關許可證的資訊 [!DNL Adobe Workfront Fusion] ，請參閱 [[!DNL Adobe Workfront Fusion] 許可證](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

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

根據您是使用舊版Frame.io聯結器或Beta Frame.io聯結器，連線程式會有所不同。

1. 在任何 Frame.io Beta模組中，按兩下 **[!UICONTROL 「連接」框旁邊的“添加]** ”。

1. 填寫以下欄位..

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL 連線類型]</td>
          <td>
            <p>選取您要建立IMD使用者驗證連線或IMS伺服器到伺服器連線。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL連線名稱]</td>
          <td>
            <p>輸入此連接的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
          <td>輸入您的 [!DNL Adobe] [！UICONTROL 用戶端 ID]。 這可以在 [！UICONTROL 憑證詳細數據]區段。[!DNL Adobe Developer Console]<p>有關查找憑據的說明，請參閱 <a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >Adobe Systems 開發人員文檔中的憑據</a> 。</p></td>
        </tr>
        <tr>
          <td role="rowheader">[！UICONTROL使用者端密碼]</td>
          <td>輸入您的[!DNL Adobe] [！UICONTROL使用者端密碼]。 這可以在[!DNL Adobe Developer Console]的[！UICONTROL認證詳細資料]區段中找到。<p>如需尋找認證的說明，請參閱Adobe開發人員檔案中的<a href="https://developer.adobe.com/developer-console/docs/guides/services/services-add-api-oauth/#credentials" class="MCXref xref" >認證</a>。</p>
        </tr>
       </tbody>
    </table>
1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

## [!DNL Frame.io] 模組及其欄位

設定 [!DNL Frame.io] 模組時， [!DNL Workfront Fusion] 顯示下面列出的欄位。 除此之外，還可能會顯示其他 [!DNL Frame.io] 欄位，具體取決於您在應用或服務中的訪問級別等因素。 模組中的粗體標題表示必填欄位。

如果在欄位或函數上方看到地圖按鈕，則可以使用它來設置該欄位的變數和函數。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [資產](#assets)
* [評論](#comments)
* [資料夾](#folders)
* [專案](#projects)
* [共用](#shares)
* [工作區](#workspaces)
* [其他](#other)

### 資產

* [[!UICONTROL 建立資產]](#create-an-asset)
* [[!UICONTROL 刪除資產]](#delete-an-asset)
* [[!UICONTROL 取得資產]](#get-an-asset)
* [[!UICONTROL 列表資產]](#list-assets)
* [[!UICONTROL 更新資產]](#update-an-asset)

#### [!UICONTROL 建立資產] <!--different for v4-->

此動作模組會建立新資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>有關創建與的連接[!DNL Frame.io]的說明，請參閱<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">本文中的連接到[!DNL Frame.io][!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選擇帳戶或映射包含要為其创建資產的專案的帳戶的 ID。</p> </td> 
  </tr> 
 <tr> 
   <td role="rowheader">[!UICONTROL 工作環境 ID] </td> 
   <td> <p>選擇工作環境或映射包含要為其創建資產的專案的工作環境的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選取專案或對應您要建立資產的專案ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選擇要在其中建立資產的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 檔案名稱] </td> 
   <td> <p>輸入要用于此資產的文件名。</p> </td> 
  </tr>
    <tr> 
    <td role="rowheader">檔案大小 </td> 
    <td> <p>輸入或對應檔案大小（位元組）。</p> </td> 
   </tr>
  <tr> 
   <td role="rowheader">[！UICONTROL Source URL] </td> 
   <td> <p>如果要創建文件，請輸入要上傳的文件的URL。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 媒體類型] </td> 
   <td> <p>选取此資產的媒體類型。</p> </td> 
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
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選擇帳戶或映射包含要刪除資產的帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
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
   <td>有關創建與的連接[!DNL Frame.io]的說明，請參閱<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">本文中的連接到[!DNL Frame.io][!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選擇帳戶或映射包含要檢索的資產的帳戶的 ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 資產 ID] </td> 
   <td> <p>选取或映射您要撷取的資產。</p> </td> 
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
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要列出之資產的帳戶ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 返回資產的最大數量] </td> 
   <td> <p>輸入或映射您希望模組在每個方案執行周期中返回的最大資產數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 評論

* [[!UICONTROL 建立註解]](#create-a-comment)
* [[!UICONTROL 刪除註解]](#delete-a-comment)
* [[!UICONTROL 取得註解]](#get-a-comment)
* [[!UICONTROL 清單註解]](#list-comments)
* [[!UICONTROL 更新註解]](#update-a-comment)

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
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取帳戶或對應包含您要新增註解之資產的帳戶ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選取帳戶或對應包含您要新增註解之資產的工作區ID。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選擇專案或映射包含要向其添加註釋資產的專案 ID。</p> </td> 
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
   <td role="rowheader">[!UICONTROL 時間戳] </td> 
   <td> <p>在影片中輸入評論應連結的影格編號。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL頁面] </td> 
   <td> <p>如果資產是PDF，請輸入或對應應附加註解的頁面。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除評論]

此作模組刪除現有註釋。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
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
   <td>有關創建與的連接[!DNL Frame.io]的說明，請參閱<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">本文中的連接到[!DNL Frame.io][!DNL Adobe Workfront Fusion]</a>。</td> 
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
    <td role="rowheader">[!UICONTROL 連接] </td> 
   <td>有關創建與的連接[!DNL Frame.io]的說明，請參閱<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">本文中的連接到[!DNL Frame.io][!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選擇或映射包含要從中檢索評論資產的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Workspace ID] </td> 
   <td> <p>選擇或映射包含要從中檢索評論資產的工作環境。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 專案 ID] </td> 
   <td> <p>選擇包含要從中檢索評論資產的專案。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 路徑] </td> 
   <td> <p>選擇通往您要清單評論資產的路徑。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 返回評論的最大數量] </td> 
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
   <td role="rowheader">[!UICONTROL 帳戶 ID] </td> 
   <td> <p>選擇或映射包含專案的帳戶，該專案包含要更新註釋的資產。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 註解 ID] </td> 
   <td> <p>選擇要更新的評論。</p> </td> 
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

### 資料夾

#### 建立資料夾

此動作模組會在Frame.io中建立新資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
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
* [列出專案](#list-projects)

#### 建立專案

此動作模組會在Frame.io中建立新專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
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
   <td> <p>輸入或映射新項目的名稱。</p> </td> 
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
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要擷取專案之資產的帳戶。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 工作環境 ID] </td> 
   <td> <p>選擇或映射包含要從中檢索專案的資產的工作環境。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回專案的最大數量] </td> 
   <td> <p>輸入或映射最大項目數
   您希望在每個方案執行週期內返回模組。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 共用

* [將資產新增至共用連結](#add-an-asset-to-a-share-link)
* [建立共享連結](#create-a-share-link)

#### 將資產添加到共享連結

此作模組將資產添加到 Frame.io 中的共享連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[!UICONTROL 連接] </td> 
   <td>有關創建與的連接[!DNL Frame.io]的說明，請參閱<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">本文中的連接到[!DNL Frame.io][!DNL Adobe Workfront Fusion]</a>。</td> 
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

#### 建立共享連結

此作模組在 Frame.io 中創建新的共享連結。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">[！UICONTROL Connection] </td> 
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
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
    <td role="rowheader">[!UICONTROL 連接] </td> 
   <td>有關創建與的連接[!DNL Frame.io]的說明，請參閱<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">本文中的連接到[!DNL Frame.io][!DNL Adobe Workfront Fusion]</a>。</td> 
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
   <td>如需建立[!DNL Frame.io]連線的說明，請參閱本文中的<a href="#connect-frameio-to-adobe-workfront-fusion" class="MCXref xref">連線[!DNL Frame.io]至[!DNL Adobe Workfront Fusion]</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL帳戶ID] </td> 
   <td> <p>選取或對應包含您要擷取工作區之資產的帳戶。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">[!UICONTROL 傳回工作環境的最大數量] </td> 
   <td> <p>輸入或對應工作區的最大數目
   您希望模組在每個案例執行週期中傳回。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### [!UICONTROL 進行自訂API呼叫]

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
   <td> <p>輸入相對於的 <code>https://api.frame.io</code>路徑。 例： <code> /v4/me</code></p> <p>注意：有關可用終端節點清單，請參閱 [!DNL Frame.io] API 參考。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL方法]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 有關詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref">HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標題]</td> 
   <td> <p>以標準 JSON 物件的格式添加請求標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>[!DNL Workfront Fusion] 自動添加授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串] </td> 
   <td> <p>輸入請求查詢字串。 對於要包含在查詢字串中的每個參數，請按兩下 <b>[！UICONTROL 添加專案]</b> ，然後輸入字段名稱和所需值。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UI控制主體]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的内文內容。</p> <p>注意：  <p>使用條件語句（例如 <code>if</code> 在 JSON 中）時，請將引號放在條件語句之外。</p> 
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

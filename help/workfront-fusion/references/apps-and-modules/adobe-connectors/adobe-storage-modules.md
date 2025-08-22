---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe儲存模組
description: 在Adobe Workfront Fusion情境中，您可以在Adobe Admin Console中建立和管理專案。
author: Becky
feature: Workfront Fusion
exl-id: 78ee905f-4713-44a4-bffb-c64cdb3665c2
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1400'
ht-degree: 3%

---

# Adobe儲存模組

在Adobe Workfront Fusion情境中，您可以在Adobe Admin Console中建立和管理專案。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

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

## 建立與Adobe儲存體的連線

建立與Adobe儲存體的連線需要在Adobe Developer Console以及Fusion中進行一些設定。

### 在Adobe Developer Console中設定專案

您必須在Adobe Developer Console中將API新增至專案。

1. 在Adobe Developer Console中開啟您的專案。
1. 按一下&#x200B;**新增至專案**，然後選取&#x200B;**API**。
1. 從可用API清單中，選取&#x200B;**Adobe Cloud Platform和Collaboration API**。
1. 在[選取驗證型別]畫面上，選取&#x200B;**OAuth伺服器對伺服器**，然後按一下[下一步]****。
1. 新增憑證的名稱。
1. 按一下[下一步]****，然後按一下[儲存設定的API]****。
1. 記下提供的憑證，這些憑證將在Workfront Fusion中設定連線時使用。
1. 繼續[將您的技術帳戶設為Adobe Admin Console的管理員](#make-your-technical-account-an-admin-in-the-adobe-admin-console)。

### 將您的技術帳戶設為Adobe Admin Console的管理員

從Adobe Admin Console頁面，選取頂端導覽列中的「產品」索引標籤，然後選取Workfront Fusion

1. 尋找並複製貴組織中技術帳戶使用者的電子郵件地址。
1. 如果顯示清單，請選取頂端的連結。
1. 這是您的使用者所在的生產執行個體。
1. 在顯示的清單中，選取產品設定檔索引標籤後，按一下Workfront產品設定檔連結的名稱。

   此清單包含已指派給您的Workfront生產執行個體的所有使用者。

1. 選取使用者清單上方的&#x200B;**管理員**&#x200B;索引標籤。
1. 選取&#x200B;**新增管理員**。
1. 在[新增產品設定檔管理員]方塊中，輸入技術帳戶的電子郵件地址，然後選取[儲存]。****

   技術帳戶會成為管理員。

1. 繼續[在Workfront Fusion](#create-the-connection-in-workfront-fusion)中建立連線。

### 在Workfront Fusion中建立連線

若要為您的[!DNL Adobe Storage]模組建立連線：

1. 在任何模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[！UICONTROL連線型別]</td>
        <td>選擇「<code>Server to server</code>」。</td>
        </tr>
        <tr>
        <td role="rowheader">[！UICONTROL連線名稱]</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
        </tr>
        <td role="rowheader">[！UICONTROL使用者端ID]</td>
        <td>輸入您的[！UICONTROL Adobe] [！UICONTROL使用者端ID]。 您可以在[!DNL Adobe Developer Console]中專案的[！UICONTROL認證詳細資料]區段中找到此專案。</td>
        </tr>
        <tr>
        <td role="rowheader">[！UICONTROL使用者端密碼]</td>
        <td>輸入您的[!DNL Adobe] [！UICONTROL使用者端密碼]。 您可以在[!DNL Adobe Developer Console]中專案的[！UICONTROL認證詳細資料]區段中找到此專案。</td>
        </tr>
        <tr>
        <td role="rowheader">[！UICONTROL IMS組織識別碼]</td>
        <td>輸入或對應您的Adobe IMS組織ID。 這是格式為<code> 123abc@AdobeOrg</code>的字串，其中@之前的區段是十六進位數字。 您可以在Adobe Admin Console中，或在Adobe.IO主控台中，將此值視為您組織的URL路徑的一部分，以進行使用者管理整合。</td>
        </tr>
      </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

## Adobe儲存模組及其欄位

當您設定Adobe使用者管理模組時，Workfront Fusion會顯示下列欄位。 除此之外，也會根據您應用程式或服務中的存取層級等因素，顯示其他Adobe「使用者管理」欄位。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [ESM存放區](#esm-stores)
* [邀請](#invitations)
* [其他](#other)

### ESM存放區

* [建立ESM存放區](#create-an-esm-store)
* [刪除ESM存放區](#delete-an-esm-store)
* [捨棄ESM存放區](#discard-an-esm-store)
* [還原ESM存放區](#restore-an-esm-store)

#### 建立ESM存放區

此動作模組會設定新的企業儲存空間管理(ESM)存放區，以組織和管理關鍵業務資產。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe儲存體連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >建立與Adobe儲存體的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">專案名稱</td> 
   <td>輸入或對應新專案的名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 刪除ESM存放區

此動作模組會永久移除現有的ESM存放區及其所有相關資料。 此動作無法還原。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe儲存體連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >建立與Adobe儲存體的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">存放區ID</td> 
   <td>輸入或對應您要刪除之存放區的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### 捨棄ESM存放區

此動作模組會將EMS存放區標示為要刪除，以便在永久移除前留出寬限期。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe儲存體連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >建立與Adobe儲存體的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">存放區ID</td> 
   <td>輸入或對應您要捨棄之存放區的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### 還原ESM存放區

此動作模組會復原先前刪除的ESM存放區，並還原其資料和設定的存取權。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe儲存體連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >建立與Adobe儲存體的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">存放區ID</td> 
   <td>輸入或對應您要還原之存放區的ID。</td> 
  </tr> 
 </tbody> 
</table>

### 邀請

#### 邀請使用者

此動作模組會傳送邀請，授予新使用者存取特定ESM存放區的許可權，以啟用共同作業和檔案管理。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe儲存體連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >建立與Adobe儲存體的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">電子郵件地址</td> 
   <td>輸入或對應您要邀請加入商店之使用者的電子郵件地址。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產 ID</td> 
   <td>輸入或對應您要邀請使用者加入的資產ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">角色</td> 
   <td>選取您希望新邀請的使用者對資產擁有的角色。<ul><li>所有者</li><li>編輯者</li><li>檢視者</li></ul></td> 
  </tr> 
  <tr> 
   <td role="rowheader">可以評論</td> 
   <td>啟用此選項可允許使用者評論資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">可以分享</td> 
   <td>啟用此選項可允許使用者與其他使用者共用資產。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">需要接受</td> 
   <td>啟用此選項以確保使用者必須先接受邀請，然後才能在資產上共同作業。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用掛載</td> 
   <td>如果必須為被邀請者建立資源的掛載點，請啟用此選項。 必須啟用「必須接受」選項才能啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">通知型別</td> 
   <td>輸入或對應您要用來通知使用者有關邀請的Adobe通知型別。 如果此項留空，則通知型別會根據資產的mimetype。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">範本名稱</td> 
   <td>輸入或對應您要用於邀請電子郵件之範本的Adobe郵政局ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">語系設定</td> 
   <td>以語言代碼和國家/地區代碼的形式，輸入使用者的地區設定。 <p>範例： <code>en-us</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">外部</td> 
   <td>如果您想使用Adobe邀請服務外部的系統傳送通知，請將此選項設為true。 僅當不需要接受時才支援外部通知。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">資產型別</td> 
   <td>輸入或對應資產型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">訊息</td> 
   <td>輸入或對應要包含在邀請電子郵件中的訊息。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">目標URL</td> 
   <td>輸入或對應受邀者可用來檢視資產的URL。</td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### 進行自訂API呼叫

此動作模組會向Adobe Storage API提出自訂HTTP請求。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連接</td>
   <td>如需建立與Adobe儲存體連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-storage" class="MCXref xref" >建立與Adobe儲存體的連線</a>。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://ccprojects.adobe.io/api/v3/.</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>方法</p>
      </td>
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">標頭</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會自動新增授權標題和x-api-key標題。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">查詢字串  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">內文</td>
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

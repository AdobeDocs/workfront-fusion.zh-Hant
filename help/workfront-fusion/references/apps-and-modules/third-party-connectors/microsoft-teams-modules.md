---
title: Microsoft Teams模組
description: 在Adobe Workfront Fusion案例中，您可以自動化使用Teams的工作流程，並將其連結到多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
source-git-commit: f5b49cca308fad01167aed27e4716a3d630cb026
workflow-type: tm+mt
source-wordcount: '3642'
ht-degree: 2%

---

# Microsoft Teams模組

<!-- ADD REDIRECTS -->

在Adobe Workfront Fusion案例中，您可以自動化使用Microsoft Teams的工作流程，並將其連結至多個協力廠商應用程式和服務。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

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
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
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

若要使用Microsoft Teams模組，您必須擁有Microsoft Teams帳戶才能在模組中執行動作。

## 將Microsoft Teams服務連線至Workfront Fusion

如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱[建立與Adobe Workfront Fusion的連線 — 基本說明](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

>[!NOTE]
>
>部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
>
>例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

## Microsoft Teams模組及其欄位

設定Microsoft Teams模組時，Workfront Fusion會顯示下列欄位。 除此之外，可能還會顯示其他Microsoft Teams欄位，視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [團隊](#team)
* [頻道](#channel)
* [訊息](#message)
* [成員](#member)
* [線上會議](#online-meeting)
* [其他](#other)

### 團隊

* [從群組建立團隊](#create-a-team-from-a-group)
* [建立Office 365群組](#create-an-office-365-group)
* [刪除團隊或群組](#delete-a-team-or-group)
* [取得團隊](#get-a-team)
* [列出所有團隊和群組](#list-all-teams-and-groups)
* [列出已加入的團隊](#list-joined-teams)
* [更新團隊](#update-a-team)
* [觀看團隊](#watch-teams)

#### 從群組建立團隊

此動作模組會從現有的Microsoft Office 365群組建立團隊，並設定新團隊的設定。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組 ID</td> 
   <td> <p>選取要建立專案團隊的群組。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">允許成員建立和更新管道</td> 
   <td>選取是否要允許成員建立和更新管道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許成員刪除管道</td> 
   <td>選取是否要允許成員刪除管道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許成員新增和移除應用程式</td> 
   <td>選取是否要允許成員新增和移除應用程式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許成員建立、更新和移除標籤</td> 
   <td>選取是否要允許成員建立、更新及移除標籤。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許成員建立和移除聯結器</td> 
   <td>選取是否要允許成員建立和移除聯結器。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許使用者編輯訊息</td> 
   <td>選取是否要允許使用者編輯其訊息。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許使用者刪除訊息</td> 
   <td>選取是否要允許使用者刪除其訊息。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許擁有者刪除訊息</td> 
   <td>選取是否要允許擁有者刪除任何郵件。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許@team提及</td> 
   <td>選取是否要允許@team提及。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許@channel提及</td> 
   <td>選取是否要允許@channel提及。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許Giphy</td> 
   <td>選取是否要允許此團隊使用Giphy。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許貼紙和Meme</td> 
   <td>選取您是否要允許使用者包含貼圖和meme。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許自訂Meme</td> 
   <td>選取您是否要允許使用者包含自訂模組。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許來賓建立和更新頻道</td> 
   <td>選取是否要允許來賓建立和更新頻道。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">允許來賓刪除頻道</td> 
   <td>選取是否要允許來賓(Guests)刪除頻道。</td> 
  </tr> 
 </tbody> 
</table>

#### 建立Office 365群組

此動作模組會在Microsoft Office 365中建立群組。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">顯示名稱</td> 
   <td> <p>輸入或對應此群組在其通訊錄中顯示的名稱。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">群組的別名</td> 
   <td>輸入或對應此群組的電子郵件別名。 您可以包含小寫字母、數字和底線。 對於Office 365群組型別，這將是群組的電子郵件別名([別名]@[您的網域].onmicrosoft.com)。 對於「安全性群組」型別，別名會充當暱稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組型別</td> 
   <td>選取您要建立Office 365群組還是安全性群組。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">說明</td> 
   <td>輸入或對應此群組的描述。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">已啟用安全性</td> 
   <td>如果您希望群組啟用安全性，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">擁有者</td> 
   <td>選取此群組的擁有者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">成員</td> 
   <td>選取此群組的成員。</td> 
  </tr> 
 </tbody> 
</table>

#### 刪除團隊或群組

此動作模組會刪除指定的團隊或群組。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組 ID</td> 
   <td> <p>輸入或對應您要刪除之群組的ID。</p> 
   </tr> 
 </tbody> 
</table>

#### 取得團隊

此模組會擷取指定Microsoft團隊或Office 365群組的屬性和關係。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組 ID</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之群組的ID。</p> 
   </tr> 
 </tbody> 
</table>

#### 列出所有團隊和群組

此模組會列出Microsoft Teams中與組織相關聯的所有團隊和Office 365群組。 您可以篩選以僅傳回符合您指定准則的結果。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">篩選器</td> 
   <td> <p>您可以設定篩選器，只傳回符合您選取條件的團隊和群組。</p> <p>針對每個篩選器，輸入您希望篩選器評估的欄位、運運算元，以及您希望篩選器允許的值。 您可以新增AND或OR規則，以使用一個以上的篩選器。</p> </td> 
   </tr> 
  <tr> 
   <td>傳回結果的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期中傳回的團隊或群組數量上限。</td> 
  </tr> 
 </tbody> 
</table>


#### 列出已加入的團隊

此動作模組會列出與用於此模組的連線相關聯的使用者所加入的團隊。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>傳回結果的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期中傳回的團隊或群組數量上限。</td> 
  </tr> 
 </tbody> 
</table>

#### 更新團隊

此動作模組會更新Microsoft Teams或Office 365群組中指定團隊的屬性。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">顯示名稱</td> 
   <td> <p>輸入或對應此群組在其通訊錄中顯示的名稱。</p> 
   </tr> 
  <tr> 
   <td role="rowheader">群組的別名</td> 
   <td>輸入或對應此群組的電子郵件別名。 您可以包含小寫字母、數字和底線。 對於Office 365群組型別，這將是群組的電子郵件別名([別名]@[您的網域].onmicrosoft.com)。 對於「安全性」群組型別，別名會充當暱稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">說明</td> 
   <td>輸入或對應此群組的描述。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">已啟用安全性</td> 
   <td>如果您希望群組啟用安全性，請啟用此選項。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">可見度</td> 
   <td>指定Office 365群組的可見度。</td> 
  </tr> 
 </tbody> 
</table>

#### 觀看團隊

此觸發模組會在建立團隊時啟動案例。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">篩選器</td> 
   <td> <p>您可以設定篩選器以僅監視符合您選取條件的團隊和群組。</p> <p>針對每個篩選器，輸入您希望篩選器評估的欄位、運運算元，以及您希望篩選器允許的值。 您可以新增AND或OR規則，以使用一個以上的篩選器。</p> </td> 
   </tr> 
  <tr> 
   <td>傳回結果的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期中傳回的團隊或群組數量上限。</td> 
  </tr> 
 </tbody> 
</table>

### 頻道

* [建立管道](#create-a-channel)
* [刪除頻道](#delete-a-channel)
* [取得頻道](#get-a-channel)
* [列出頻道](#list-channels)
* [更新頻道](#update-a-channel)

#### 建立管道

此動作模組會為指定的團隊建立新的管道。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>在Microsoft Teams中選取您要建立頻道的團隊。</p> </td> 
   </tr> 
  <tr> 
   <td>頻道名稱</td> 
   <td>輸入或對映新管道的名稱。</td> 
  </tr> 
  <tr> 
   <td>說明</td> 
   <td>輸入或對映新頻道的說明。</td> 
  </tr> 
 </tbody> 
</table>

#### 刪除頻道

此動作模組會從Microsoft團隊中刪除指定的頻道。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>在Microsoft Teams中輸入或對應您要刪除頻道的團隊ID。</p> </td> 
   </tr> 
  <tr> 
   <td>管道ID</td> 
   <td>輸入或對應您要刪除之管道的ID。</td> 
  </tr> 
  </tbody> 
</table>

#### 取得頻道

此模組會擷取管道的屬性和關係。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>在Microsoft Teams中輸入或對應擁有您要擷取詳細資料之管道的團隊ID。</p> </td> 
   </tr> 
  <tr> 
   <td>管道ID</td> 
   <td>輸入或對應您要擷取詳細資料的管道ID。</td> 
  </tr> 
  </tbody> 
</table>

#### 列出頻道

此模組會列出Microsoft Teams中指定團隊擁有的管道。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>在Microsoft Teams中選取您要列出頻道的團隊。</p> </td> 
   </tr> 
  <tr> 
   <td>傳回結果的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期內傳回的最大通道數。</td> 
  </tr> 
  </tbody> 
</table>

#### 更新頻道

此動作模組會更新指定頻道的說明。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>在Microsoft Teams中選取擁有您要更新頻道的團隊。</p> </td> 
   </tr> 
  <tr> 
   <td>頻道名稱</td> 
   <td>輸入或對應您要更新的管道名稱。</td> 
  </tr> 
  <tr> 
   <td>說明</td> 
   <td>輸入或對映頻道的新說明。</td> 
  </tr> 
 </tbody> 
</table>

### 訊息

* [回覆頻道訊息](#reply-to-a-channel-message)
* [傳送訊息](#send-a-message)
* [觀看訊息](#watch-messages)
* [觀看新回覆](#watch-new-replies)

#### 回覆頻道訊息

此動作模組會在指定頻道中建立訊息的回覆。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>在Microsoft Teams中選取擁有包含您要回覆之訊息之頻道的團隊。</p> </td> 
   </tr> 
  <tr> 
   <td>管道ID</td> 
   <td>選取包含您要回覆之訊息的頻道。</td> 
  </tr> 
  <tr> 
   <td>訊息ID</td> 
   <td>輸入或對應您要回覆的郵件ID。</td> 
  </tr> 
  <tr> 
   <td>內容型別</td> 
   <td>選取您要以純文字或HTML格式傳送訊息。</td> 
  </tr> 
  <tr> 
   <td>回複訊息</td> 
   <td>輸入或對應您要傳送的回複訊息內文。</td> 
  </tr> 
 </tbody> 
</table>

#### 傳送訊息

此動作模組會傳送訊息至團隊的頻道或聊天。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">訊息型別/td&gt; 
   <td> <p>選取您是傳送頻道訊息還是聊天訊息。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>如果您要傳送訊息至頻道，請在Microsoft Teams中輸入或對應擁有您要傳送訊息之頻道之團隊的ID。</p> </td> 
   </tr> 
  <tr> 
   <td>管道ID</td> 
   <td>如果您要傳送訊息至頻道，請輸入或對應您要傳送訊息的目標頻道ID。</td> 
  </tr> 
  <tr> 
   <td>建立新聊天</td> 
   <td>如果您要傳送聊天訊息，請選取是否要建立新聊天。
   <ul><li><b>是</b><p>選取您想要一對一聊天或群組聊天，然後選取要包含在聊天中的成員。 您必須選取與此模組使用之連線相關聯的使用者，一對一聊天必須僅包含該使用者和另一個使用者。</p><p>如果您正在建立群組聊天，可以在「主題」欄位中設定主題。</p>
   <li><b>否</b><p>輸入或對應擁有您要向其傳送訊息之頻道的團隊識別碼，然後輸入或對應頻道識別碼。</td> 
  </tr> 
  <tr> 
   <td>訊息</td> 
   <td>輸入或對應您要傳送的訊息本文。</td> 
  </tr> 
  <tr> 
   <td>內容型別</td> 
   <td>選取您要以純文字或HTML格式傳送訊息。</td> 
  </tr> 
 </tbody> 
</table>

#### 觀看訊息

此觸發模組會在訊息傳送至團隊的頻道或聊天時啟動案例。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">要觀看的訊息型別</td> 
   <td> <p>選取您要觀看頻道訊息或聊天訊息。</p> </td> 
   </tr> 
   <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>如果您正在觀看頻道訊息，請在Microsoft Teams中選取擁有您觀看訊息之頻道的團隊。</p> </td> 
   </tr> 
  <tr> 
   <td>管道ID</td> 
   <td>如果您正在觀看頻道訊息，請選取您要觀看訊息的頻道。</td> 
  </tr> 
  <tr> 
   <td>聊天ID</td> 
   <td>如果您正在觀看聊天訊息，請選取您要觀看訊息的聊天。</td> 
  </tr> 
  <tr> 
   <td>傳回訊息的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期內傳回的最大訊息數量。</td> 
  </tr> 
 </tbody> 
</table>

#### 觀看新回覆

此觸發模組會在指定訊息收到新回覆時啟動案例。

此模組不適用於個人帳戶。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> <p>在Microsoft Teams中選取擁有您觀看回覆之管道的團隊。</p> </td> 
   </tr> 
  <tr> 
   <td>管道ID</td> 
   <td>選取您要觀看回覆的頻道。</td> 
  </tr> 
  <tr> 
   <td>訊息ID</td> 
   <td>選取您要觀看回覆的聊天。</td> 
  </tr> 
  <tr> 
   <td>傳回回覆的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期內傳回的最大回複數。</td> 
  </tr> 
 </tbody> 
</table>

### 成員

* [新增成員](#add-a-member)
* [新增成員至群組](#add-a-member-to-a-group)

#### 新增成員

此動作模組會將成員新增至Microsoft Teams。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">成員名稱</td> 
   <td> <p>輸入或對應您要新增至Microsoft Teams的成員名稱。</p> </td> 
   </tr> 
  <tr> 
   <td>密碼</td> 
   <td>輸入或對應成員的密碼。</td> 
  </tr> 
 </tbody> 
</table>

#### 新增成員至群組

此動作模組會將成員新增至Office 365群組。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">群組 ID</td> 
   <td> <p>選取您要新增成員的群組。</p> </td> 
   </tr> 
  <tr> 
   <td>成員ID</td> 
   <td>選取要新增至群組的成員。</td> 
  </tr> 
 </tbody> 
</table>

### 線上會議

* [建立線上會議](#create-an-online-meeting)
* [刪除線上會議](#delete-an-online-meeting)
* [取得線上會議](#get-an-online-meeting)
* [更新線上會議](#update-an-online-meeting)

#### 建立線上會議

此動作模組會建立與使用者行事曆上的事件無關的獨立會議。 此會議不會顯示在使用者的行事曆上。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">主旨</td> 
   <td>輸入或對應此會議的主旨。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">開始日期和時間</td> 
   <td>輸入或對應您要會議開始的日期和時間。 如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">結束日期和時間</td> 
   <td>輸入或對應您要會議結束的日期和時間。 如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許的主持人</td> 
   <td>選取允許出現在此會議中的群組。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者</td> 
   <td>針對您想要新增至會議的每位出席者，按一下[新增專案] <b> </b>並選取出席者的名稱和角色。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許與會者啟用他們的相機</td> 
   <td>選取是否要允許與會者啟用自己的相機。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許與會者啟用其麥克風</td> 
   <td>選取是否要允許與會者啟用自己的麥克風。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許會議聊天</td> 
   <td>選取您是要啟用、停用會議聊天，還是以會議通話的持續時間為限</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許團隊回應</td> 
   <td>選取是否要為此會議啟用Teams回應。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">執行緒 ID</td> 
   <td>輸入或對應與此會議關聯的執行緒ID。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">訊息ID</td> 
   <td>輸入或對應與此會議相關之訊息的ID。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">回覆鏈結訊息ID</td> 
   <td>輸入或對應與此會議相關聯的回覆鏈結識別碼。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">宣佈進入和退出</td> 
   <td>選取您是否希望在與會者進入或退出時宣佈會議。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">範圍</td> 
   <td>選取可略過在大廳等待的出席者群組。 這些出席者將直接加入會議。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">啟用撥入使用者以略過大廳</td> 
   <td>選取是否允許撥入使用者略過大廳。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">自動錄製</td> 
   <td>選取是否要自動錄製會議。</td> 
   </tr> 
   </tbody> 
</table>

#### 刪除線上會議

此動作模組會刪除具有指定ID的線上會議。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">會議ID</td> 
   <td> <p>輸入或對應您要刪除之會議的ID。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### 取得線上會議

此動作模組會使用指定的ID擷取線上會議的詳細資訊。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">會議ID</td> 
   <td> <p>輸入或對應您要擷取其詳細資訊之會議的ID。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### 更新線上會議

此動作模組會以指定的ID更新線上會議。



<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">會議ID</td> 
   <td>輸入或對應您要更新的會議ID。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">主旨</td> 
   <td>輸入或對應此會議的主旨。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">開始日期和時間</td> 
   <td>輸入或對應您要會議開始的日期和時間。 如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">結束日期和時間</td> 
   <td>輸入或對應您要會議結束的日期和時間。 如需支援的日期格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制轉換</a>。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許的主持人</td> 
   <td>選取允許出現在此會議中的群組。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">出席者</td> 
   <td>針對您想要新增至會議的每位出席者，按一下[新增專案] <b> </b>並選取出席者的名稱和角色。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許與會者啟用他們的相機</td> 
   <td>選取是否要允許與會者啟用自己的相機。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許與會者啟用其麥克風</td> 
   <td>選取是否要允許與會者啟用自己的麥克風。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許會議聊天</td> 
   <td>選取您是要啟用、停用會議聊天，還是以會議通話的持續時間為限</td> 
   </tr> 
   <tr> 
   <td role="rowheader">允許團隊回應</td> 
   <td>選取是否要為此會議啟用Teams回應。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">執行緒 ID</td> 
   <td>輸入或對應與此會議關聯的執行緒ID。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">訊息ID</td> 
   <td>輸入或對應與此會議相關之訊息的ID。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">回覆鏈結訊息ID</td> 
   <td>輸入或對應與此會議相關聯的回覆鏈結識別碼。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">宣佈進入和退出</td> 
   <td>選取您是否希望在與會者進入或退出時宣佈會議。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">範圍</td> 
   <td>選取可略過在大廳等待的出席者群組。 這些出席者將直接加入會議。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">啟用撥入使用者以略過大廳</td> 
   <td>選取是否允許撥入使用者略過大廳。</td> 
   </tr> 
   <tr> 
   <td role="rowheader">自動錄製</td> 
   <td>選取是否要自動錄製會議。</td> 
   </tr> 
   </tbody> 
</table>

### 其他

* [檢查使用者是否存在](#check-presence-of-users)
* [進行自訂API呼叫](#make-a-custom-api-call)
* [搜尋使用者](#search-users)

#### 檢查使用者是否存在

此動作模組會檢查選取的使用者是否出現在Microsoft Teams上。

此模組不支援個人帳戶。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
   <tr> 
   <td role="rowheader">使用者ID</td> 
   <td> <p>選取您要檢查其是否存在的使用者。</p> </td> 
   </tr> 
 </tbody> 
</table>

#### 進行自訂API呼叫

此動作模組會向Microsoft Teams API提出自訂請求。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL URL]</td> 
   <td>輸入相對於<code>https://graph.microsoft.com</code>的路徑。 範例：<code> /v1.0/groups</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。</p> <p>例如， <code>{"Content-type":"application/json"}</code></p> <p>Workfront Fusion會為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> </td> 
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

#### 搜尋使用者

此模組會使用您指定的條件來搜尋使用者。

<table style="table-layout:auto"> 
 <col data-mc-conditions=""> 
 <col data-mc-conditions=""> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接 </td> 
   <td> <p>如需有關將Microsoft Teams帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">建立連線 — 基本說明</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">篩選器</td> 
   <td> <p>您可以設定篩選器，以僅傳回符合您選取條件的使用者。</p> <p>針對每個篩選器，輸入您希望篩選器評估的欄位、運運算元，以及您希望篩選器允許的值。 您可以新增AND或OR規則，以使用一個以上的篩選器。</p> </td> 
   </tr> 
  <tr> 
   <td>傳回結果的最大數量</td> 
   <td>設定Workfront Fusion在一個執行週期中傳回的團隊或群組數量上限。</td> 
  </tr> 
 </tbody> 
</table>




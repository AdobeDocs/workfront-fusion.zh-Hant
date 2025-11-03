---
content-type: reference
product-previous: workfront-fusion
product-area: workfront-integrations
navigation-topic: apps-and-their-modules
title: Adobe使用者管理模組
description: 在Adobe Workfront Fusion案例中，您可以自動化在Adobe帳戶中管理使用者的工作流程。
author: Becky
feature: Workfront Fusion
exl-id: e8fe8ec4-4b00-4c9a-81a5-acb2039b153b
source-git-commit: 1929bf897e9263ec551e93df776b96f419436715
workflow-type: tm+mt
source-wordcount: '2373'
ht-degree: 2%

---

# Adobe使用者管理模組

在Adobe Workfront Fusion案例中，您可以自動化在Adobe帳戶中管理使用者的工作流程。

如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件</td> 
   <td> <p>任何Adobe Workfront Workflow套件和任何Adobe Workfront自動化與整合套件</p><p>Workfront Ultimate</p><p>Workfront Prime和Select套件，以及額外購買的Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權</td> 
   <td> <p>標準</p><p>工作或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">Adobe Workfront Fusion授權</td> 
   <td>
   <p>作業型：無Workfront Fusion授權需求</p>
   <p>以聯結器為基礎（舊版）：用於工作自動化和整合的Workfront Fusion </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織有Select或Prime Workfront套件，但不包含Workfront Automation和Integration，則您的組織必須購買Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[中的](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 建立與Adobe使用者管理的連線

若要為您的[!DNL Adobe User Management]模組建立連線：

1. 在任何模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL 新增]**。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入此連線的名稱。</p>
        </td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>選取您要連線到生產或非生產環境。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 型別]</td>
        <td>選取您要連線到服務帳戶還是個人帳戶。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的[!UICONTROL Adobe] [!UICONTROL 使用者端ID]。 您可在的[!UICONTROL Credentials]詳細資訊區段中找到 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的[!DNL Adobe] [!UICONTROL 使用者端密碼]。 您可在的[!UICONTROL Credentials]詳細資訊區段中找到 [!DNL Adobe Developer Console]</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL IMS組織識別碼]</td>
        <td>輸入您的[!DNL Adobe] IMS認證。 適用於組織的唯一識別碼。 此字串格式為A495E53@AdobeOrg，其中@的前置詞為十六進位數字。 您可以在Admin Console或adobe.io主控台中，將此值視為組織URL路徑的一部分，以進行使用者管理整合。</td>
        </tr>
        <tr>
        <td role="rowheader">[!UICONTROL 其他範圍]</td>
        <td>針對您想要新增的每個其他範圍，按一下<b>新增專案</b>並輸入範圍。</td>
        </tr>
      </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。



## Adobe使用者管理模組及其欄位

當您設定Adobe使用者管理模組時，Workfront Fusion會顯示下列欄位。 除此之外，也會根據您應用程式或服務中的存取層級等因素，顯示其他Adobe「使用者管理」欄位。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [搜尋](#searches)
* [使用者動作](#user-actions)
* [使用者群組動作](#user-group-actions)
* [其他](#other)

### 搜尋

* [取得使用者群組和產品設定檔](#get-user-groups-and-product-profiles)
* [取得使用者資訊](#get-user-information)
* [取得使用者群組或產品設定檔中的使用者](#get-users-in-a-user-group-or-product-profile)
* [取得組織中的使用者](#get-users-in-an-organization)

#### 取得使用者群組和產品設定檔

此搜尋模組會擷取您組織中所有使用者群組和產品設定檔的清單，以及有關群組和設定檔的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>

#### 取得使用者資訊

此搜尋模組會擷取組織中單一使用者的詳細資訊（由其電子郵件地址識別）。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">電子郵件地址</td> 
   <td>輸入或對應您要傳回詳細資料之使用者的電子郵件地址。 對於AdobeID、Enterprise和電子郵件同盟使用者，這應該是完整的電子郵件地址，包括網域。 在所有情況下，引數均不區分大小寫。</td> 
  </tr> 
 </tbody> 
</table>

#### 取得使用者群組或產品設定檔中的使用者

此搜尋模組會擷取指定使用者群組或產品設定檔中所有使用者的清單，以及有關使用者的詳細資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組名稱</td> 
   <td>使用者群組、產品設定檔名稱或管理群組。 對於管理員群組，名稱可以是固定群組<code>_org_admin</code>、<code>_deployment_admin</code>或<code>_support_admin</code>之一；或群組特定的管理員群組。 群組名稱的前置詞可識別這些專案，例如<code>_admin_groupName</code>、<code>_product_admin_productName</code>或<code>_developer_groupName</code>。 如果群組存在，但管理員群組不存在，則會傳回空白清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">僅限直接</td> 
   <td>指定傳回的使用者結構中的群組欄位是否僅包含該使用者為其直接成員的產品設定檔。 若為false，會傳回包含該使用者的所有群組（使用者群組、產品設定檔和管理員群組），無論特定產品設定檔的權益是直接（透過使用者指派）或間接（透過包含被指派至產品設定檔的使用者群組）獲得。 如果為true，則傳回包含該使用者的所有使用者群組和管理員群組，但僅限該使用者已被明確指派權利的產品設定檔。 使用者可以是產品設定檔的直接和間接成員。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">排除群組</td> 
   <td>指定回應是否排除針對每位使用者傳回的群組陣列。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">狀態</td> 
   <td>此選項僅適用於產品設定檔。 選取「有效」可列出已針對產品布建的使用者，並具有有效的授權。 選取「非使用中」以列出已新增至產品設定檔但沒有使用中授權的使用者。 如果保留為空白，模組會傳回所有成員使用者，無論其權益狀態為何。
</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>

#### 取得組織中的使用者

此搜尋模組會傳回與連線相關聯之組織的所有使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</td> 
  </tr> 
 </tbody> 
</table>

### 使用者動作

* [將使用者新增為群組的成員](#add-a-user-as-a-member-of-a-group)
* [建立使用者](#create-a-user)
* [從群組移除使用者](#remove-a-user-from-groups)
* [更新使用者](#update-a-user)

#### 將使用者新增為群組的成員

此動作模組會將使用者新增為指定群組的成員。 此模組最多可將使用者新增至四個群組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用者</td> 
   <td>輸入或對應您要新增至群組的使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">網域</td> 
   <td>對於不是電子郵件地址的Federated ID，請輸入使用者所屬的網域。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組</td> 
   <td>針對您想要新增使用者的每個群組，按一下<b>新增專案</b>，然後輸入或對應群組。 您最多可以輸入四個群組，而且至少必須輸入一個。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用Adobe ID</td> 
   <td>選取true可確保使用者ID會解譯成參考現有的Adobe ID，即使Enterprise或Federated ID存在時具有相同名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 建立使用者

此動作模組會在組織中建立新使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID型別</td> 
   <td>選取您要使用Adobe ID、Enterprise ID或Federated ID建立使用者。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">登入</td> 
   <td>如果您使用Federated ID建立使用者，請選取登入型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">電子郵件</td> 
   <td>輸入或對應新使用者的電子郵件地址。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">網域</td> 
   <td>如果您使用Federated ID建立具有網域型登入的使用者，請輸入或對應網域。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用者</td> 
   <td>如果您使用Federated ID建立具有網域式登入的使用者，請輸入或對應新使用者將代表的使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名字</td> 
   <td>輸入或對映使用者的名字。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">姓氏</td> 
   <td>輸入或對映使用者的姓氏。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">國家/地區</td> 
   <td>輸入或對應兩個字元的ISO國家/地區代碼。 建立使用者後即無法變更。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">選項</td> 
   <td>選取當使用者已存在於組織中時要採取的動作。 如果未選取任何選項，且使用者已存在，則模組會傳回錯誤。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用Adobe ID</td> 
   <td>為true時，使用者ID會解譯為參考現有的Adobe ID，即使Enterprise或Federated ID存在時具有相同名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 從群組移除使用者

此動作模組會從指定的群組中移除使用者的成員資格。 您一次最多可以從四個群組中移除一個使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用者</td> 
   <td>輸入或對應您要從群組移除的使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">網域</td> 
   <td>對於不是電子郵件地址的Federated ID，請輸入使用者所屬的網域。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組</td> 
   <td>針對您要移除使用者的每個群組，按一下[新增專案] <b> </b>，然後輸入或對應群組。 您最多可以輸入四個群組，而且至少必須輸入一個。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用Adobe ID</td> 
   <td>選取true可確保使用者ID會解譯成參考現有的Adobe ID，即使Enterprise或Federated ID存在時具有相同名稱。</td> 
  </tr> 
 </tbody> 
</table>



#### 更新使用者

此動作模組會更新現有使用者。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用者</td> 
   <td>輸入或對應您要更新的使用者ID。 這是使用者的電子郵件地址，例如 <code>user@example.com</code></td> 
  </tr> 
  <tr> 
   <td role="rowheader">網域</td> 
   <td>如果您更新的Federated ID使用者不是電子郵件地址，請輸入或對應使用者所屬的網域，以便識別使用者。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">電子郵件</td> 
   <td>輸入或對映使用者的新電子郵件地址。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">名字</td> 
   <td>輸入或對映使用者的名字。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">姓氏</td> 
   <td>輸入或對映使用者的姓氏。</td> 
  </tr> 
 </tbody> 
</table>

### 使用者群組動作

* [新增使用者群組的成員資格](#add-memberships-for-a-user-group)
* [建立使用者群組](#create-a-user-group)
* [刪除使用者群組](#delete-a-user-group)
* [移除使用者群組的成員資格](#remove-memberships-for-a-user-group)
* [更新使用者群組](#update-a-user-group)

#### 新增使用者群組的成員資格

此動作模組會將使用者和產品設定檔新增到使用者群組。 新增到使用者群組的使用者，將取得使用者群組中所有產品設定檔的權益。 新增產品設定檔時，使用者群組中的使用者將有權存取該設定檔。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組名稱</td> 
   <td>輸入或對應您要從中移除使用者或設定檔的群組名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用者</td> 
   <td>針對您想要新增的每個使用者，按一下<b>新增使用者</b>並輸入使用者的電子郵件地址。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">設定檔</td> 
   <td>針對您想要新增至群組的每個設定檔，按一下<b>新增使用者</b>並輸入設定檔名稱</td> 
  </tr> 
 </tbody> 
</table>

#### 建立使用者群組

此動作模組會建立新的使用者群組。 如果已有指定名稱的群組存在，模組可以更新現有的群組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組名稱</td> 
   <td>輸入或對應新使用者群組的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">說明</td> 
   <td>輸入或對應新使用者群組的描述。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">選項</td> 
   <td>選取當使用者群組已存在於組織中時要採取的動作。 如果未選取任何選項，且使用者群組已存在，則模組會傳回錯誤。</td> 
  </tr> 
 </tbody> 
</table>

#### 刪除使用者群組

此動作模組會刪除現有的使用者群組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組名稱</td> 
   <td>輸入或對應您要刪除之群組的名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 移除使用者群組的成員資格

此動作模組會從使用者群組中移除使用者或設定檔。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">群組名稱</td> 
   <td>輸入或對應您要從中移除使用者或設定檔的群組名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用者</td> 
   <td>針對您要移除的每個使用者，按一下[新增使用者] <b> </b>並輸入使用者的電子郵件地址。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">設定檔</td> 
   <td>針對您要從群組移除的每個設定檔，按一下[新增使用者] <b> </b>並輸入設定檔名稱</td> 
  </tr> 
  <tr> 
   <td role="rowheader">使用Adobe ID</td> 
   <td>為true時，使用者ID會解譯為參考現有的Adobe ID，即使Enterprise或Federated ID存在具有相同名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 更新使用者群組

此動作模組會更新現有的使用者群組。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">原始群組名稱</td> 
   <td>輸入或對應您要更新的群組目前名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">新群組名稱</td> 
   <td>輸入或對應您希望群組擁有的新名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">原始群組名稱</td> 
   <td>輸入或對應更新後的群組說明。</td> 
  </tr> 
 </tbody> 
 </table>

### 其他


#### 進行自訂API呼叫

此動作模組會對Adobe使用者管理API進行自訂呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連接</td>
      <td>如需建立與Adobe User Management的連線的指示，請參閱本文中的<a href="#create-a-connection-to-adobe-user-management" class="MCXref xref" >建立與Adobe User Management的連線</a>。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>URL</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://usermanagement.adobe.io/v2/usermanagement/</code></p>
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

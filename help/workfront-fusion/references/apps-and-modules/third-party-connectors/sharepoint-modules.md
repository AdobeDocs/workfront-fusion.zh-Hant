---
title: SharePoint模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Microsoft SharePoint Online的工作流程，並將其連結至多個協力廠商應用程式和服務。
author: Becky
feature: Workfront Fusion
exl-id: 1a09aa86-5e0e-4347-b4cf-2b0a95e5b049
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '3124'
ht-degree: 0%

---

# Microsoft SharePoint Online模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用Microsoft SharePoint Online的工作流程，並將其連結至多個協力廠商應用程式和服務。

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

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用Microsoft SharePoint Online模組，您必須擁有Microsoft SharePoint Online帳戶。

## SharePoint API資訊

SharePoint聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://graph.microsoft.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.14.2</td> 
  </tr>
 </tbody> 
 </table>

## 將Microsoft SharePoint Online連線至[!DNL Workfront Fusion] {#connect-microsoft-sharepoint-online-to-workfront-fusion}

* [使用 [!DNL Microsoft] 帳戶將Microsoft SharePoint Online連線至 [!DNL Workfront Fusion] ](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-a-microsoft-account)
* [使用進階設定將Microsoft SharePoint Online連線至 [!DNL Workfront Fusion] ](#connect-microsoft-sharepoint-online-to-workfront-fusion-using-advanced-settings)

### 使用[!DNL Microsoft]帳戶將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]

您可以使用您的[!DNL Microsoft]帳戶建立與Microsoft SharePoint Online的連線。 如需有關將您的[!DNL Sharepoint]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱[建立連線到 [!DNL Adobe Workfront Fusion]  — 基本指示](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md)

### 使用進階設定將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]

若要在沒有[!DNL Microsoft]帳戶的情況下將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]，您需要使用者端識別碼、使用者端密碼和租使用者識別碼。

1. 按一下&#x200B;**Microsoft SharePoint Online**&#x200B;方塊頂端附近的&#x200B;**[!UICONTROL 新增]**&#x200B;以開啟&#x200B;**[!UICONTROL 建立連線]**&#x200B;方塊。

1. （選擇性）變更預設的&#x200B;**[!UICONTROL 連線名稱]**。
1. 按一下&#x200B;**[!UICONTROL 顯示進階設定]**。
1. 輸入Microsoft SharePoint Online **[!UICONTROL 使用者端識別碼]**&#x200B;和&#x200B;**[!UICONTROL 使用者端密碼]**。

1. 按一下&#x200B;**[!UICONTROL 繼續]**。
1. 在顯示的登入視窗中，輸入您的認證以登入應用程式（如果尚未這麼做）。
1. （視條件而定）如果顯示&#x200B;**[!UICONTROL 允許]**&#x200B;按鈕，請按一下按鈕以將應用程式連線到[!DNL Workfront Fusion]。

## Microsoft SharePoint Online模組及其欄位

當您設定Microsoft SharePoint Online模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除此之外，可能還會顯示其他Microsoft SharePoint Online欄位，視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [磁碟機專案](#drive-item)
* [項目](#item)
* [清單](#list)
* [頁面(Beta)](#page-beta)
* [網站](#site)
* [其他](#other)

### 磁碟機專案

* [建立檔案](#create-a-file)
* [建立資料夾](#create-a-folder)
* [取得檔案](#get-a-file)
* [監視資料夾專案](#watch-folder-items)

#### 建立檔案

此模組會傳回SharePoint中所做的變更。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別要擷取變更的資料夾位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立檔案之位置的<strong>[！UICONTROL站台識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要建立檔案的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source檔案]</td> 
      <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p>
  </tr>  </tbody> 
</table>

#### 建立資料夾

此動作模組會在SharePoint中建立新資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取要如何識別要建立的資料夾位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立資料夾位置的<strong>[！UICONTROL站台識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要建立資料夾的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾名稱]</td> 
   <td>輸入或對應新資料夾的名稱。</td> 
  </tr>
  </tbody> 
</table>

#### 取得檔案

此動作模組會擷取指定的SharePoint檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別要取得之檔案的位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要擷取的檔案，輸入或對應<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL檔案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取檔案的位置。 </p> </li> 
    </ul> </td> 
  </tr> 
</tbody> 
</table>

#### 監視資料夾專案

當您選取的資料夾中有專案更新時，此觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別要取得之檔案的位置。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在出現的欄位中輸入或對映<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取要監視的資料夾位置。 </p> </li> 
    </ul> </td> 
  </tr> 
   <td role="rowheader">[！UICONTROL限制]</td> 
   <td>輸入在一個案例執行週期內應該傳回的專案數上限[!DNL Workfront Fusion]。</td> 
  <tr>
  </tr>
</tbody> 
</table>

### 項目

* [[!UICONTROL 複製專案]](#copy-an-item)
* [[!UICONTROL 建立專案]](#create-an-item)
* [[!UICONTROL 刪除專案]](#delete-an-item)
* [[!UICONTROL 取得專案]](#get-an-item)
* [[!UICONTROL 清單專案]](#list-items)
* [[!UICONTROL 移動專案]](#move-an-item)
* [[!UICONTROL 更新專案]](#update-an-item)
* [[!UICONTROL 觀看專案] （已排程）](#watch-items-scheduled)


#### [!UICONTROL 複製專案]

此動作模組會複製SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸入站台、磁碟機和資料夾ID</td> 
   <td> <p>選取您要如何識別包含您要複製之專案的場地和磁碟機。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要複製之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>在「專案型別」欄位中，選取您要移動欄位或資料夾。  選取包含您要複製之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL目的地ID]</td> 
   <td> 輸入或對應您要複製專案的資料夾識別碼。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新名稱]</td> 
   <td>輸入或對應專案新復本的名稱。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 建立專案]

此動作模組會在SharePoint清單中建立新專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL建立專案]</td> 
   <td> <p>選取您要如何識別網站及要建立專案的磁碟機。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立專案的<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL清單識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要建立專案之清單的網站，然後選取清單。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL欄位]</td> 
   <td>針對您想要為新專案設定的每個欄位，按一下<b>新增專案</b>，然後輸入欄位索引鍵（可識別欄位）以及您想要新專案在該欄位中的值。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除專案]

此動作模組會刪除SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL更新專案]</td> 
   <td> <p>選取您要如何識別網站以及包含您要刪除之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要刪除之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要刪除之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得專案]

此動作模組會傳回指定專案的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得專案]</td> 
   <td> <p>選取您要如何識別網站以及包含您要取得之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要傳回資料之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取專案之清單的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清單專案]

此動作模組會擷取指定清單中所有專案的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL清單專案]</td> 
   <td> <p>選取您要如何識別要從中擷取專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要列出專案的清單，輸入或對映<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL清單識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要從中擷取專案的清單的網站，然後選取清單。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大專案數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 移動專案]

此動作模組會複製SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">輸入站台、磁碟機和資料夾ID</td> 
   <td> <p>選取您要如何識別網站以及包含您要移動之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>針對您要移動的專案，輸入或對映<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>在「專案型別」欄位中，選取您要移動欄位或資料夾。 選取包含您要複製之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL目的地ID]</td> 
   <td> 輸入或對應您要移動專案的資料夾識別碼。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新名稱]</td> 
   <td>輸入或對應已移動專案的名稱。 </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新專案]

此動作模組會更新SharePoint清單中的現有專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL更新專案]</td> 
   <td> <p>選取您要如何識別包含您要更新之專案的場地與清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要更新之專案的<strong>[！UICONTROL網站識別碼]</strong>、<strong>[！UICONTROL清單識別碼]</strong>和<strong>[！UICONTROL專案識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要更新之專案的網站，然後選取清單，再選取專案。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL欄位]</td> 
   <td>針對您想要更新新專案的每個欄位，按一下<b>新增專案</b>，然後輸入欄位索引鍵（可識別欄位）以及您想要專案在該欄位擁有的新值。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看專案] （已排程）

此觸發模組會在建立或修改專案時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL監看清單]</td> 
   <td>選取您要依建立時間（新專案）還是依修改時間（更新專案）來監視清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站和清單ID]</td> 
   <td> <p>選取您要如何識別要觀看的網站和清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要觀看的<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL清單識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要觀看的網站，然後選取清單。 這些下拉式清單只會擷取追蹤的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大專案數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 清單

* [[!UICONTROL 建立清單]](#create-a-list)
* [[!UICONTROL 取得清單]](#get-a-list)
* [[!UICONTROL 清單清單]](#list-lists)
* [[!UICONTROL 觀看清單]](#watch-lists)

#### [!UICONTROL 建立清單]

此動作模組會在SharePoint中建立新清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站ID]</td> 
   <td> <p>選取您要如何識別要建立清單的網站。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要建立清單的<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取您要建立清單的網站。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL顯示名稱]</td> 
   <td>輸入或對應新清單的名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL說明]</td> 
   <td>輸入或對應新清單的說明。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL新增欄]</td> 
   <td>針對您想要為新清單設定的每個資料行，按一下<b>新增專案</b>，輸入欄位的<strong>[！UICONTROL名稱]</strong>，然後選取您想要新資料行具有的值<strong>[！UICONTROL型別]</strong>。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得清單]

此動作模組會傳回指定清單的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得清單]</td> 
   <td> <p>選取您要如何識別網站以及包含您要取得之專案的清單。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您要傳回的<strong>[！UICONTROL網站識別碼]</strong>與<strong>清單識別碼</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取之清單的網站，然後選取清單。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 清單清單]

此動作模組會擷取指定網站中所有專案的清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL清單清單]</td> 
   <td> <p>選取您要如何識別要從中擷取清單的網站。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應包含您要傳回清單的<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取之清單的網站。 下拉式清單只會擷取您關注的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大清單數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看清單]

此觸發模組會在建立或修改清單時啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL監看清單]</td> 
   <td>選取您要依建立時間（新專案）還是依修改時間（更新專案）來監視清單。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站ID]</td> 
   <td> <p>選取您要如何識別要監視清單的網站。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應您想要監視清單的<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從您關注的清單中選取]</strong> </p> <p>選取您要觀看的網站。 下拉式清單只會擷取您追蹤的網站。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大清單數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 頁面(Beta)

>[!NOTE]
>
>[!DNL Microsoft Graph]中`beta`版本的API可能會變更。 不支援在生產應用程式中使用這些API。

#### [!UICONTROL 取得頁面]

此動作模組會傳回指定頁面的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得頁面]</td> 
   <td> <p>選取您要如何識別要擷取的頁面。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應<strong>[！UICONTROL網站識別碼]</strong>和<strong>[！UICONTROL頁面識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含您要擷取之頁面的網站，然後選取頁面。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 網站

* [[!UICONTROL 取得網站]](#get-a-site)
* [[!UICONTROL 搜尋網站]](#search-sites)

#### [!UICONTROL 取得網站]

此動作模組會傳回指定網站的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL取得網站]</td> 
   <td> <p>選取您要如何識別要擷取的頁面。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>輸入或對應<strong>[！UICONTROL網站識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取您要擷取的網站。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 搜尋網站]

此動作模組會依您指定的引數搜尋網站。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">顯示名稱的[！UICONTROL關鍵字]</td> 
   <td> <p>輸入或對應您要搜尋網站的搜尋字詞。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL限制]</td> 
   <td> <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大網站數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他

* [取得變更](#get-changes)
* [進行API呼叫](#make-an-api-call)
* [觀看活動](#watch-events)

#### 取得變更

此模組會擷取SharePoint資料夾中的新增、更新和刪除專案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL輸入網站、磁碟機和資料夾ID]</td> 
   <td> <p>選取您要如何識別包含您要更新之專案的場地與磁碟機。</p> 
    <ul> 
     <li> <p><strong>[！UICONTROL手動輸入]</strong> </p> <p>在出現的欄位中輸入或對映<strong>[！UICONTROL站台識別碼]</strong>、<strong>[！UICONTROL磁碟機識別碼]</strong>和<strong>[！UICONTROL資料夾識別碼]</strong>。</p> </li> 
     <li> <p><strong>[！UICONTROL從清單中選取]</strong> </p> <p>選取包含要更新專案的網站，然後選取磁碟機，再選取資料夾。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Token]</td> 
   <td> 代號會識別模組應該從何時開始擷取變更。  </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 進行API呼叫]

此模組可讓您執行自訂API呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的Microsoft SharePoint Online帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">將Microsoft SharePoint Online連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL URL]</p> </td> 
   <td> <p>輸入相對於<code>https://graph.microsoft.com</code>的路徑。 範例：<code> /beta/sites</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL方法]</p> </td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 例如，<code>{"Content-type":"application/json"}</code>。 [!DNL Workfront Fusion]為您新增授權標頭。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL查詢字串]</td> 
   <td> <p> 以標準JSON物件的形式新增API呼叫的查詢。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL型別]</td> 
   <td>選取您要在API呼叫中傳送的資料型別。</td> 
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

#### 觀看活動

在SharePoint中新增、更新或刪除專案時，此即時觸發模組就會啟動案例。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
  <!--
   <td role="rowheader">[!UICONTROL Connection]</td> 
   <td> <p>For instructions about connecting your Microsoft SharePoint Online account to [!DNL Workfront Fusion], see <a href="#connect-microsoft-sharepoint-online-to-workfront-fusion" class="MCXref xref" data-mc-variable-override="">Connect Microsoft SharePoint Online to [!DNL Workfront Fusion]</a> in this article.</p> </td> 
  </tr> 
  -->
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook]</td> 
   <td> <p>選取現有的webhook，或按一下「新增」並輸入連線以建立新的webhook。</p> 
   </td> 
  </tr> 
 </tbody> 
</table>

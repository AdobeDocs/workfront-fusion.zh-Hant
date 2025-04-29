---
title: 方塊模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用Box的工作流程，並將其連線到多個協力廠商應用程式和服務。 監視指定的資料夾以檢查檔案變更、修改和刪除現有檔案，或將新檔案上傳到資料夾。
author: Becky
feature: Workfront Fusion
exl-id: 9e741dce-05a6-4e13-8d58-fbe3b4900d7e
source-git-commit: f02c4df01c7fad6bb9cdf4911512eef97e71c82b
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 1%

---

# 方塊模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Box]的工作流程，並將其連線至多個協力廠商應用程式和服務。 監視指定的資料夾以檢查檔案變更、修改和刪除現有檔案，或將新檔案上傳到資料夾。

如需建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。 如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

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

若要使用[!DNL Box]模組，您必須有[!DNL Box]帳戶。

## Box API資訊

Box聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎URL</td> 
   <td> https://api.box.com/2.0
    </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v2.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v3.0.3</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Box]模組及其欄位

當您設定[!DNL Box]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Box]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)

### 觸發程序

* [[!UICONTROL 新事件]](#new-event)
* [[!UICONTROL 觀看檔案]](#watch-files)

#### [!UICONTROL 新事件]

此即時觸發模組會在檔案新增、移動、複製、刪除、鎖定或解除鎖定時啟動案例。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Webhook]</td> 
   <td> <p>選取您要用來觀看外寄郵件的webhook。 若要新增webhook，請按一下<strong>[！UICONTROL新增]</strong>並輸入webhook的名稱和連線。</p> <p> 如需有關將您的[！UICONTROL Box]帳戶連線到[！UICONTROL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref">連線到服務 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[！UICONTROL傳回事件數上限]</p> </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大事件數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 觀看檔案]

此觸發模組會在新增新檔案或更新正在觀看的資料夾中的現有檔案時啟動案例。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">連接</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  <tr> 
   <td role="rowheader">資料夾</td> 
   <td> <p>選取要監視的資料夾。 一個案例可以觀看單一資料夾。</p> 
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">觀看</td> 
   <td> <p>選取您要觀看的檔案型別。</p> 
    <ul> 
     <li> <p><strong>僅新檔案</strong> </p> <p>在新增檔案時，此案例就會開始。</p> </li> 
     <li> <p><strong>新檔案與所有變更</strong> </p> <p>新增檔案、修改檔案內容或檔案屬性（例如其名稱）時，就會開始此案例。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>已下載檔案的最大數量</p> </td> 
   <td> <p>輸入您希望模組在每個案例執行週期中傳回的最大檔案數。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 刪除檔案]](#delete-a-file)
* [[!UICONTROL 取得檔案]](#get-a-file)
* [[!UICONTROL 更新檔案]](#update-a-file)
* [[!UICONTROL 上傳]檔案](#upload-a-file)

#### [!UICONTROL 刪除檔案]

此動作模組會刪除檔案。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  <tr> 
   <td role="rowheader">[！UICONTROL檔案ID]</td> 
   <td>輸入或對應您要模組刪除之檔案的唯一ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 取得檔案]

此動作模組會下載檔案。

您指定檔案的ID。

>[!NOTE]
>
>此模組對於提供檔案給後續模組相當實用。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  <tr> 
   <td role="rowheader">[！UICONTROL檔案ID]</td> 
   <td>輸入或對應您要模組擷取之檔案的唯一ID。</td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 更新檔案]

此動作模組會更新檔案。

您指定檔案的ID。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  <tr> 
   <td role="rowheader">[！UICONTROL檔案ID]</td> 
   <td>輸入或對應您要模組更新的檔案唯一ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 上傳檔案]

此動作模組會上傳檔案。

您指定檔案。 您也可以為檔案提供新的檔案名稱。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[！UICONTROL Connection]</td> 
   <td> <p>如需有關將您的[!DNL Box]帳戶連線到[!DNL Workfront Fusion]的指示，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與[!DNL Adobe Workfront Fusion]的連線 — 基本指示</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL資料夾]</td> 
   <td> <p>選取您要上傳檔案的資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Source檔案]</td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如果此模組不成功，請考慮下列事項：
>
>* 檔案大小可能超過您[!DNL Box]計畫的檔案大小上限，或者您已使用所有[!DNL Box]帳戶的儲存配額。 若要取得更多儲存空間，請從[!DNL Box]刪除現有檔案，或升級您的[!DNL Box]帳戶。
>* [!DNL Box]不會將多個同名檔案上傳至單一資料夾。 如果目的地資料夾包含與正在上傳的檔案同名的檔案，則案例執行會以錯誤終止。 若要避免此情況，請重新命名檔案。 若要更新檔案，請使用&#x200B;**[!UICONTROL 更新檔案]**&#x200B;模組。

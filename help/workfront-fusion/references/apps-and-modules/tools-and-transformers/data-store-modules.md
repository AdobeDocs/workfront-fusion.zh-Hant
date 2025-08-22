---
title: 資料存放區模組
description: Adobe Workfront Fusion資料存放區（類似於資料庫或簡單表格）可以儲存情境中的資料，以便在個別情境或情境執行之間傳輸資料。 您可以在同步期間使用資料存放區來儲存來自不同系統的新資料。
author: Becky
feature: Workfront Fusion
exl-id: 0338b822-b345-429e-850d-3978b692231d
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '1154'
ht-degree: 0%

---

# [!UICONTROL 資料存放區]模組

Adobe Workfront Fusion資料存放區（類似於資料庫或簡單表格）可以儲存情境中的資料，以便在個別情境或情境執行之間傳輸資料。 您可以在同步期間使用資料存放區來儲存來自不同系統的新資料。

資料存放區模組可讓您新增、取代、更新、擷取、刪除、搜尋或計算Adobe Workfront Fusion資料存放區中的記錄。

<!--For information on creating, editing, and troubleshooting data stores, see [Data Stores in Adobe Workfront Fusion](/help/workfront-fusion/references/mapping-panel/data-types/)-->

如需有關Workfront Fusion中資料存放區的影片簡介，請參閱：

* [資料存放區](https://video.tv.adobe.com/v/3427029/){target=_blank}

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
   <p>無Workfront Fusion授權需求</p>
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

若要使用[!UICONTROL 資料存放區]模組，您必須先建立資料存放區。

如需建立資料存放區的資訊，請參閱[建立及管理資料存放區](/help/workfront-fusion/create-scenarios/map-data/data-stores.md)。

## [!UICONTROL 資料存放區]模組及其欄位

當您設定資料存放區模組時，Workfront Fusion會顯示下列欄位。 除此之外，其他資料存放區欄位可能會顯示，端視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

您不需要建立連線即可使用資料存放區。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)


* [新增/取代記錄](#addreplace-a-record)
* [檢查記錄是否存在](#check-the-existence-of-a-record)
* [計算記錄](#count-records)
* [刪除記錄](#delete-a-record)
* [刪除所有記錄](#delete-all-records)
* [取得記錄](#get-a-record)
* [搜尋記錄](#search-records)
* [更新記錄](#update-a-record)

### [!UICONTROL 新增/取代記錄]

此動作模組新增或取代記錄。

您可以指定資料存放區和記錄的索引鍵。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

>[!NOTE]
>
>當您嘗試以相同名稱新增資料存放區中的記錄時，模組擲回錯誤，且[!UICONTROL 覆寫現有記錄]選項已停用。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區]</td> 
   <td> <p> 選取或新增要建立記錄的資料存放區。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>輸入您要模組新增或取代之記錄的唯一索引鍵。 此金鑰稍後可用於擷取記錄。 如果您將此欄位留空，則會自動產生索引鍵。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 覆寫現有記錄] </td> 
   <td> <p>啟用此選項以覆寫記錄。 您必須在上方的[索引鍵]欄位中指定您要覆寫的記錄。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄] </td> 
   <td> <p>在記錄的欄位中輸入所需的值。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 檢查記錄是否存在]

此動作模組會指定特定記錄是否存在。

您可以指定資料存放區和記錄的索引鍵。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區] </td> 
   <td> <p>選取您要檢查記錄是否存在的資料存放區。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>輸入您要模組檢查其是否存在之記錄的唯一索引鍵。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 記錄數]

此動作模組對資料存放區中的記錄進行編號。

您可以指定資料存放區。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區] </td> 
   <td> <p>選取包含您要計算之記錄的資料存放區。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 刪除記錄]

此動作模組會刪除記錄。

您可以指定資料存放區和記錄的索引鍵。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區] </td> 
   <td> <p>選取您要檢查記錄是否存在的資料存放區。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>輸入您要模組刪除之記錄的唯一關鍵值。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 刪除所有記錄]

此動作模組會從特定資料存放區中刪除所有記錄。

您可以指定資料存放區。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區] </td> 
   <td> <p>選取要刪除所有記錄的資料存放區。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 取得記錄]

此動作模組會擷取記錄。

您可以指定資料存放區和記錄的索引鍵。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區]</td> 
   <td> <p> 選取您要從中擷取記錄的資料存放區</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>輸入您要模組擷取之記錄的唯一索引鍵。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 搜尋記錄]

此搜尋模組會在資料存放區中尋找符合您指定之搜尋查詢的物件記錄。

您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區]</td> 
   <td> <p> 選取您要搜尋的資料存放區。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL 篩選器]</p> </td> 
   <td> <p>設定搜尋的篩選器。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL 排序]</p> </td> 
   <td> <p style="font-weight: normal;">針對您要排序的每個欄位，填寫以下欄位：</p> <p style="font-weight: bold;">[!UICONTROL Key]</p> <p>選取要作為結果排序依據的欄名稱。</p> <p style="font-weight: bold;">[!UICONTROL 順序]</p> <p>選取您要以遞增或遞減順序排序結果。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 限制]</td> 
   <td> <p> 設定Workfront Fusion在一個執行週期內傳回的搜尋結果數上限。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 即使模組未傳回任何結果，仍繼續執行路由]</td> 
   <td> <p> 如果啟用，即使此模組未傳回任何結果，此模組所屬的路由仍會繼續處理。</p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL 更新記錄]

此動作模組會更新記錄。

您可以指定資料存放區和記錄的索引鍵。

模組會傳回記錄ID及任何關聯欄位，連同連線存取的任何自訂欄位和值。 您可以在情境中的後續模組中對應此資訊。

當您設定此模組時，會顯示下列欄位。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL 資料存放區]</td> 
   <td> <p> 選取或新增要建立記錄的資料存放區。 </p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Key] </td> 
   <td> <p>輸入您要模組更新的記錄唯一索引鍵。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 插入遺漏的記錄] </td> 
   <td> <p>啟用此選項以在指定索引鍵的記錄不存在時建立新記錄。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL 記錄]</td> 
   <td> <p> 在您要更新的記錄欄位中輸入所需的值。</p> </td> 
  </tr> 
 </tbody> 
</table>

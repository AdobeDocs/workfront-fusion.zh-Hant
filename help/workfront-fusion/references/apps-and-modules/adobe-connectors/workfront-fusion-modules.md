---
title: Workfront Fusion模組
description: 使用Workfront Fusion聯結器，您可以從情境中管理自己的Fusion組織，包括記錄、鉤點、情境和連線。
author: Becky
feature: Workfront Fusion
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 1665553df806ba49ee9b52199fdcc587a5bb6337
workflow-type: tm+mt
source-wordcount: 1374
ht-degree: 21%

---

# Workfront Fusion模組

使用Workfront Fusion聯結器，您可以從情境中管理自己的Fusion組織。 有別於將Fusion連線至協力廠商應用程式或服務的其他聯結器，此聯結器可讓案例呼叫Fusion自己的API，其方式類似於Adobe Workfront聯結器讓案例管理Workfront的方式。

關於建立情境的說明，請參閱[建立情境：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)之下的文章。

關於模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)之下的文章。

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
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 將Workfront Fusion連線至Workfront Fusion

1. 在任何Workfront Fusion模組中，按一下「連線」欄位旁的&#x200B;**[!UICONTROL 新增]**。
1. 填寫下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL 連線類型]</td> 
      <td>選取您要建立的連線型別。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 連線名稱]</td> 
      <td>輸入此連線的名稱。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 用戶端 ID]</td> 
      <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端 ID]。 這可以在[!DNL Adobe Developer Console]的[！UICONTROL Credentials]詳細資訊區段中找到。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL 用戶端密碼]</td> 
      <td>輸入您的 [!DNL Adobe] [!UICONTROL 用戶端密碼]。 這可以在[!DNL Adobe Developer Console]的[！UICONTROL Credentials]詳細資訊區段中找到。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL組織ID]</td> 
      <td>輸入您的[!DNL Adobe] IMS組織ID。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL區域]</td> 
      <td>選取此連線的Fusion區域。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

## Workfront Fusion模組及其欄位

當您設定Workfront Fusion模組時，Workfront Fusion會顯示下列欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [匯出](#export)
* [雜項](#misc)

### 動作

* [複製記錄](#clone-a-record)
* [建立記錄](#create-a-record)
* [刪除記錄](#delete-a-record)
* [清單記錄](#list-records)
* [讀取記錄](#read-a-record)
* [更新記錄](#update-a-record)

#### 複製記錄

此模組會製作指定記錄的復本。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> 選取您要複製的記錄型別。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">案例ID</td> 
   <td> 輸入或對應您要複製之案例的ID。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">名稱</td> 
   <td> 輸入或對應新情境的名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 建立記錄

此模組會使用指定的資料建立記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> 選取您要建立的記錄類型。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">團隊 ID</td> 
   <td> 輸入或對應將擁有此記錄的團隊ID。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">名稱</td> 
   <td> 輸入或對應新記錄的名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 刪除記錄

此模組會刪除指定的記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> 選取您要刪除的記錄型別。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td>輸入任何其他欄位的值。 可用欄位取決於所選的記錄型別。 </td> 
  </tr> 
 </tbody> 
</table>

#### 清單記錄

此模組會使用游標式分頁與屬性篩選器，傳回分頁記錄清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td>選取您要傳回清單的記錄型別。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">屬性</td> 
   <td>針對您要傳回結果的每個屬性篩選器，按一下<b>新增專案</b>，然後輸入您要篩選的欄位、運運算元和值。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">開始</td> 
   <td>輸入您要開始傳回結果的位置。 這是用於分頁。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個執行週期傳回的最大記錄數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">排序依據</td> 
   <td>選取您要依據排序結果的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方向</td> 
   <td>選取您要以遞增或遞減方式排序結果。</td> 
  </tr> 
 </tbody> 
</table>

#### 讀取記錄

此模組會擷取指定的記錄

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> 選取您要刪除的記錄型別。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">其他欄位</td> 
   <td>輸入任何其他欄位的值。 可用欄位取決於所選的記錄型別。 </td> 
  </tr> 
 </tbody> 
</table>

#### 更新記錄

更新指定的記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> 選取您要更新的記錄型別。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">名稱</td> 
   <td> 輸入或對映記錄的新名稱。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">ID</td> 
   <td> 輸入或對應您要更新的記錄ID。 </td> 
  </tr> 
 </tbody> 
</table>

### 匯出

#### 匯出活動記錄

此模組會匯出活動記錄。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">檔案類型</td> 
   <td>選取您要匯出記錄檔的檔案格式。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">屬性</td> 
   <td>針對您要傳回結果的每個屬性篩選器，按一下<b>新增專案</b>，然後輸入您要篩選的欄位、運運算元和值。 您也可以依欄位是否存在來篩選。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">開始</td> 
   <td>輸入您要開始傳回結果的位置。 這是用於分頁。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個執行週期傳回的最大記錄數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">排序依據</td> 
   <td>選取您要依據排序結果的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方向</td> 
   <td>選取您要以遞增或遞減方式排序結果。</td> 
  </tr> 
 </tbody> 
</table>

### 雜項

* [取得掛接的佇列統計資料](#get-queue-statistics-for-a-hook)
* [取得記錄相依性](#get-record-dependencies)
* [列出連線的案例](#list-scenarios-for-a-connection)
* [列出Fusion區域和組織](#list-the-fusion-regions-and-organizations)

#### 取得掛接的佇列統計資料

此模組會傳回指定掛接的佇列統計資料：目前佇列的事件數、佇列限制，以及掛接是否已啟用。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  <tr> 
   <td role="rowheader">勾點ID</td> 
   <td> 輸入或對應您要傳回詳細資訊之連結的ID。</td> 
  </tr> 
 </tbody> 
</table>

#### 取得記錄相依性

此模組取得記錄的相依性。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  <tr> 
   <td role="rowheader">記錄類型</td> 
   <td> 選取您要擷取相依性的記錄型別。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">案例ID</td> 
   <td> 輸入或對應您要擷取相依性的記錄ID。 </td> 
  </tr> 
  </tr> 
 </tbody> 
</table>

#### 列出連線的案例

此模組會傳回參考指定連線的案例分頁清單。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">連線ID</td> 
   <td>輸入或對應您要傳回案例的連線ID。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">屬性</td> 
   <td>針對您要傳回結果的每個屬性篩選器，按一下<b>新增專案</b>，然後輸入您要篩選的欄位、運運算元和值。 您也可以依欄位是否存在來篩選。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">開始</td> 
   <td>輸入您要開始傳回結果的位置。 這是用於分頁。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">傳回結果的最大數量</td> 
   <td>輸入或對應您希望模組在每個執行週期傳回的最大記錄數。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">排序依據</td> 
   <td>選取您要依據排序結果的欄位。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">方向</td> 
   <td>選取您要以遞增或遞減方式排序結果。</td> 
  </tr> 
 </tbody> 
</table>

#### 列出Fusion區域和組織

此模組會根據連線中所使用認證的IMS使用者設定檔中的認證和存取權，傳回連線可存取之每個Fusion組織的地區和組織ID。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需有關將Workfront Fusion連線到Workfront Fusion的說明，請參閱本文中的<a href="#connect-workfront-fusion-to-workfront-fusion" class="MCXref xref">將Workfront Fusion連線到Workfront Fusion</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>


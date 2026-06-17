---
title: Adobe Workfront內容與核准模組
description: 使用Adobe Workfront內容和核准模組，您可以取得核准詳細資訊、對資產做出決定、新增或刪除核准參與者、新增或更新核准階段、鎖定或解鎖階段，以及進行自訂API呼叫。
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: e9ea91840c9be594e98b97202cb46dfa009349a9
workflow-type: tm+mt
source-wordcount: 3743
ht-degree: 15%

---

# Adobe Workfront整合式檢閱和核准模組

使用Adobe Workfront整合式檢閱和核准模組，您可以取得核准詳細資訊、對資產做出決定、新增或刪除核准參與者、新增或更新核准階段、鎖定或解鎖階段，以及進行自訂API呼叫。

如需Workfront統一檢閱和核准的相關資訊，請參閱Workfront檔案中的[統一檢閱和核准總覽](https://experienceleague.adobe.com/zh-hant/docs/workfront/using/review-and-approve-work/document-approvals-overview)。

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

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 先決條件

您必須具備下列專案才能存取Workfront內容和核准：

* 您必須使用支援Adobe雲端儲存空間的Workfront版本。 如果貴組織尚未使用支援的版本，請聯絡您的Adobe客戶代表。

## 連線至Adobe Workfront統一檢閱和核准


1. 在任何Adobe Workfront整合式檢閱與核准模組中，按一下[連線]欄位旁的&#x200B;**新增**。
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
          <p>選取「<b>Adobe Workfront 伺服器對伺服器連線</b>」。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 執行個體名稱]</td>
        <td>
          <p>輸入執行個體的名稱，也是您的網域。</p><p>範例：若您的 URL 為 <code>https://example.my.workfront.com</code>，請輸入 <code>example</code>。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 執行個體路徑]</td>
        <td>
          <p>輸入此連線將連接的環境類型。</p><p>範例：若您的 URL 為 <code>https://example.my.workfront.com</code>，請輸入 <code>my</code>。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的 Workfront 用戶端 ID。 您可在 Workfront「設定」區域的「OAuth2 應用程式」區域內找到此項資訊。 開啟您要連接的特定應用程式以便查看用戶端 ID。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的 Workfront 用戶端密碼。 您可在 Workfront「設定」區域的「OAuth2 應用程式」區域內找到此項資訊。 如果您在 Workfront 的 OAuth2 應用程式沒有用戶端密碼，您可以產生另一個密碼。 相關說明請參閱 Workfront 文件。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 範圍]</td>
        <td>輸入此連線的適用範圍。</td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 主機前置詞]</td>
        <td>在大多數情況下，此值應為 <code>origin</code>。
      </tr>
    </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

   如果您未登入Workfront統一檢閱與核准，系統會將您導向登入畫面。 登入後，您可以允許連線。

## Adobe Workfront整合式檢閱和核准模組

當您設定 Workfront 模組時，Workfront Fusion 會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 Workfront 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。


![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)
* [搜尋](#searches)
* [其他](#other)

### 動作

* [新增或更新參與者](#add-or-update-participants)
* [大量刪除範本](#bulk-delete-templates)
* [建立範本](#create-a-template)
* [建立核准](#create-an-approval)
* [建立階段](#create-stages)
* [刪除階段上的決定](#delete-a-decision-on-a-stage)
* [刪除階段](#delete-a-stage)
* [刪除範本](#delete-a-template)
* [刪除核准](#delete-an-approval)
* [刪除決定](#delete-decisions)
* [刪除參與者](#delete-participants)
* [鎖定階段](#lock-a-stage)
* [做出決定](#make-a-decision)
* [在階段上做出決定](#make-a-decision-on-a-stage)
* [提醒舞台上的參與者](#remind-a-participant-on-a-stage)
* [提醒參與者](#remind-participant)
* [提醒尚未決定的參與者](#remind-undecided-participants)
* [提醒舞台上的未決定參與者](#remind-undecided-participants-on-a-stage)
* [解鎖階段](#unlock-a-stage)
* [更新階段](#update-a-stage)
* [更新範本](#update-a-template)
* [更新所有階段](#update-all-stages)


#### 新增或更新參與者

此動作模組在核準時新增或更新預設階段的參與者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>文件 ID</p>
      </td>
      <td>輸入或對應您要新增或更新參與者之資產的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>將參與者新增至階段</p>
      </td>
      <td>針對您想要新增參與者的每個階段，按一下<b>新增專案</b>並進入階段。<p> 接著，針對您想要新增至階段的每個參與者，按一下[新增專案] <b> </b>並輸入參與者詳細資料。</p>
      <ul>
      <li><b>參與者ID</b><p>輸入或對應參與者的ID。</p></li>
      <li><b>參與者型別</b><p>選取參與者是使用者還是茶葉。</p></li>
      <li><b>參與者角色</b><p>選取參與者是核准者還是稽核者。</p></li>
      </ul> 
      </td> 
      </tr>
  </tbody>
</table>

#### 大量刪除範本

此模組會刪除指定的核准範本。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>範本ID</p></td>
      <td>針對您要刪除的每個範本，按一下<b>新增專案</b>並輸入範本識別碼。</td> 
      </tr>
  </tbody>
</table>

#### 建立範本

此動作模組會建立核准範本

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>名稱</p></td>
      <td>輸入或對映範本的名稱。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>公司 ID</p></td>
      <td>如果您想要將公司範圍新增至範本，請輸入或對應公司ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段</p>
      </td>
      <td>針對您要新增的每個階段，按一下<b>新增專案</b>並輸入階段資料。<p>如需詳細資訊，請參閱本文中的<a href="#stages-fields" class="MCXref xref" >階段欄位</a>。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>共用對象</p></td>
      <td>對於您想要與其共用範本的每個使用者，按一下<b>新增專案</b>和使用者ID和所需的存取層級。</td> 
      </tr>
  </tbody>
</table>

#### 建立核准

此動作模組會為Adobe雲端儲存空間上的檔案建立核准，包括階段資料或範本。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要建立核准之資產的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段</p>
      </td>
      <td>針對您要新增的每個階段，按一下<b>新增專案</b>並輸入階段資料。<p>如需詳細資訊，請參閱本文中的<a href="#stages-fields" class="MCXref xref" >階段欄位</a>。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>範本 ID</p></td>
      <td>輸入或對應您要用於此核准的範本ID。</td> 
      </tr>
  </tbody>
</table>

#### 建立階段

此動作模組會使用指定的階段資料建立核准。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對映您要建立或更新階段的資產ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段</p>
      </td>
      <td>針對您要新增的每個階段，按一下<b>新增專案</b>並輸入階段資料。<p>如需詳細資訊，請參閱本文中的<a href="#stages-fields" class="MCXref xref" >階段欄位</a>。 </p> </td> 
      </tr>
    </tr>
     <tr>
      <td role="rowheader"><p>範本 ID</p></td>
      <td>輸入或對應您要建立階段的資產ID。</td> 
      </tr>
  </tbody>
</table>

#### 刪除階段上的決定

此模組會從指定的階段移除目前使用者的決定。 目前的使用者是在此模組使用的連線中使用其認證的使用者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要刪除其決定之檔案的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>階段ID</p></td>
      <td>輸入或對應您要刪除的階段ID。</td> 
      </tr>
   </tbody>
</table>


#### 刪除階段

此動作模組會從核准中刪除指定的階段。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要從中刪除階段的檔案ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>階段ID</p></td>
      <td>輸入或對應您要刪除的階段ID。</td> 
      </tr>
  </tbody>
</table>

#### 刪除範本

此模組會刪除指定的核准範本。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>範本 ID</p></td>
      <td>輸入或對應您要刪除之範本的ID。</td> 
      </tr>
  </tbody>
</table>

#### 刪除核准

此動作模組會刪除指定檔案的核准。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要刪除核准的檔案ID。</td> 
      </tr>
  </tbody>
</table>

#### 刪除決定

此模組會從指定的階段移除目前使用者的決定。 目前的使用者是在此模組使用的連線中使用其認證的使用者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要刪除其決定之檔案的ID。</td> 
      </tr>
  </tbody>
</table>

#### 刪除參與者

此動作模組會從核准中刪除參與者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要從中刪除參與者的資產ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>參與者型別</p>
      </td>
      <td>選取參與者是使用者還是團隊。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>參與者ID</p>
      </td>
      <td>輸入或對應參與者的ID。</td> 
      </tr>
  </tbody>
</table>

#### 鎖定階段

此動作模組會鎖定指定的核准階段，並將階段設定為非作用中。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要鎖定的資產ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段ID</p>
      </td>
      <td>輸入或對應您要鎖定的階段ID。</td> 
      </tr>
  </tbody>
</table>

#### 做出決定

此動作模組會將決定套用至核准或核准階段。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要鎖定的資產ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>決策</p></td>
      <td>選取要套用至核准或階段的決定。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段ID</p>
      </td>
      <td>針對您想要套用決定的每個階段，按一下<b>新增專案</b>並輸入階段ID。</td> 
      </tr>
  </tbody>
</table>

#### 在階段上做出決定

此模組會將決定套用至指定的階段。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要對其做出決定的檔案ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>階段ID</p></td>
      <td>輸入或對應您要做決定的階段ID。</td> 
      </tr>
    <tr>
      <td role="rowheader"><p>決策</p></td>
      <td>選取您要套用至此階段的決定。</td> 
      </tr>
  </tbody>
</table>

#### 提醒舞台上的參與者

此模組會傳送提醒給特定階段上的特定參與者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要傳送提醒之資產的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段ID</p>
      </td>
      <td>輸入或對應您要傳送提醒的階段ID。</td> 
      </tr>
    </tr>
     <tr>
      <td role="rowheader"><p>參與者ID</p></td>
      <td>輸入或對應您要傳送提醒的參與者識別碼。</td> 
      </tr>
  </tbody>
</table>

#### 提醒參與者

此模組會傳送提醒通知給指定的參與者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要傳送提醒之資產的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>參與者ID</p>
      </td>
      <td>輸入或對應您要提醒的參與者ID。</td> 
      </tr>
      <tr>
      <td role="rowheader">
        <p>參與者型別</p>
      </td>
      <td>輸入或對應您要提醒的參與者型別。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>參與者角色</p>
      </td>
      <td>輸入或對應您要提醒之參與者的角色。</td> 
      </tr>
  </tbody>
</table>

#### 提醒尚未決定的參與者

此模組會傳送提醒通知給指定核准的所有未決定參與者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要傳送提醒之資產的ID。</td> 
      </tr>
  </tbody>
</table>

#### 提醒舞台上的未決定參與者

此模組會傳送提醒通知給階段中所有未決定的參與者。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要傳送提醒之資產的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段ID</p>
      </td>
      <td>輸入或對應您要傳送提醒的階段ID。</td> 
      </tr>
  </tbody>
</table>

#### 解鎖階段

此動作模組會解除鎖定指定的核准階段，並將階段設定為作用中。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要解除鎖定之資產的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段ID</p>
      </td>
      <td>輸入或對應您要鎖定的階段ID。</td> 
      </tr>
  </tbody>
</table>


#### 更新階段

此動作模組會更新指定階段上的欄位。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要對其做出決定的檔案ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>階段ID</p></td>
      <td>輸入或對應您要做決定的階段ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>階段名稱</p></td>
      <td>輸入或對映範本的名稱。</td> 
      </tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>在階段欄位中輸入資料。<p>如需詳細資訊，請參閱本文中的<a href="#stages-fields" class="MCXref xref" >階段欄位</a>。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>共用對象</p></td>
      <td>對於您想要與其共用範本的每個使用者，按一下<b>新增專案</b>和使用者ID和所需的存取層級。</td> 
      </tr>
  </tbody>
</table>

#### 更新範本

此模組會更新指定核准範本上的欄位。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>範本 ID</p></td>
      <td>輸入或對映範本的名稱。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>名稱</p></td>
      <td>輸入或對應您要更新的範本ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>公司 ID</p></td>
      <td>如果您想要將公司範圍新增至範本，請輸入或對應公司ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段</p>
      </td>
      <td>針對您要新增的每個階段，按一下<b>新增專案</b>並輸入階段資料。<p>如需詳細資訊，請參閱本文中的<a href="#stages-fields" class="MCXref xref" >階段欄位</a>。 </p> </td> 
      </tr>
    <tr>
      <td role="rowheader"><p>共用對象</p></td>
      <td>對於您想要與其共用範本的每個使用者，按一下<b>新增專案</b>和使用者ID和所需的存取層級。</td> 
      </tr>
  </tbody>
</table>

#### 更新所有階段

此模組會以指定的階段資料取代現有核准中的所有階段。 檔案必須處於可編輯狀態。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要更新階段的資產ID。</td> 
      </tr>
     <tr>
      <td role="rowheader">
        <p>階段</p>
      </td>
      <td>針對您要更新的每個階段，按一下<b>新增專案</b>並輸入階段資料。<p>如需詳細資訊，請參閱本文中的<a href="#stages-fields" class="MCXref xref" >階段欄位</a>。 </p> </td> 
      </tr>
  </tbody>
</table>

### 搜尋

* [取得範本](#get-a-template)
* [取得核准詳細資料](#get-approval-details)
* [取得多個核准](#get-multiple-approvals)
* [取得建議的核准](#get-suggested-approvals)
* [取得建議的參與者](#get-suggested-participants)
* [清單機器人](#list-bots)
* [清單範本](#list-templates)
* [搜尋AI品牌檢閱者](#search-ai-brand-reviews)


#### 取得範本

此模組會傳回指定的核准範本。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>範本 ID</p></td>
      <td>輸入或對應您要取得建議核准參與者的檔案ID。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           傳回範本的最大數量
         </td>
         <td>
              輸入或對應您希望模組在每個案例執行週期中傳回的最大範本數量。 
         </td>
       </tr>
  </tbody>
</table>

#### 取得核准詳細資料

此搜尋模組會擷取資產的核准詳細資料。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>文件</p>
      </td>
      <td>輸入或對應您要擷取核准詳細資料之資產的ID。</td> 
      </tr>
  </tbody>
</table>

#### 取得多個核准

此模組會擷取特定型別檔案清單的核准詳細資料。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>檔案ID</p></td>
      <td>針對您想要擷取核准詳細資訊的每個檔案，按一下<b>新增專案</b>並輸入檔案識別碼。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           傳回結果的最大數量
         </td>
         <td>
              輸入或對應您希望模組在每個案例執行週期中傳回的最大結果數量。 
         </td>
       </tr>
  </tbody>
</table>

#### 取得建議的核准

此模組會傳回先前檔案版本的建議核准裝載。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要取得建議核准的檔案ID。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           傳回核准的最大數量
         </td>
         <td>
              輸入或對應您希望模組在每個案例執行週期中傳回的最大核准數。 
         </td>
       </tr>
  </tbody>
</table>

#### 取得建議的參與者

此模組會傳回先前檔案核准核准的參與者建議。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>文件 ID</p></td>
      <td>輸入或對應您要取得建議核准參與者的檔案ID。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           傳回參與者的最大數目
         </td>
         <td>
              輸入或對應您希望模組在每個案例執行週期中傳回的最大參與者數目。 
         </td>
       </tr>
  </tbody>
</table>

#### 清單機器人

此模組會傳回機器人帳戶的分頁清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>頁面</p></td>
      <td>輸入或對映您要傳回的結果頁面。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           傳回結果的最大數量
         </td>
         <td>
              輸入或對應您希望模組在每個案例執行週期中傳回的最大結果數量。 
         </td>
       </tr>
  </tbody>
</table>

#### 清單範本

此模組會傳回目前使用者可用的所有核准範本清單。 目前的使用者是在此模組使用的連線中使用其認證的使用者。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
   </tbody>
</table>

#### 搜尋AI品牌評論

此模組會傳回核準時為檔案版本產生的AI品牌評論結果。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>機器人使用者ID</p></td>
      <td>輸入或對應您要搜尋評論之機器人的使用者ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>父級檔案ID</p></td>
      <td>輸入或對應您要搜尋稽核的上層檔案ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>檔案版本ID</p></td>
      <td>輸入或對應您要傳送提醒之資產的ID。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>階段ID</p></td>
      <td>輸入或對映階段ID以將結果限制在核准的特定階段。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>頁面</p></td>
      <td>輸入或對映頁碼以將結果限制在該頁面。</td> 
      </tr>
       <tr>
         <td role="rowheader">
           已傳回稽核的最大數量
         </td>
         <td>
              輸入或對應您希望模組在每個案例執行週期中傳回的稽核最大數量。 
         </td>
       </tr>
  </tbody>
</table>

### 其他

* [進行自訂的 API 呼叫](#make-a-custom-api-call)
* [階段欄位](#stages-fields)


#### 進行自訂的 API 呼叫

此模組會對Adobe Workfront統一檢閱和核准API發出自訂API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">連線</td>
      <td>如需有關建立與Adobe Workfront整合式檢閱和核准的連線的指示，請參閱本文中的<a href="#connect-to-adobe-workfront-unified-review-and-approvals" class="MCXref xref" >連線到Adobe Workfront整合式檢閱和核准</a>。</td>
    </tr>
     <tr>
      <td role="rowheader">
        <p>相對路徑</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://workfront.adobe.io</code> 的路徑。 例如， <code>/unified-approvals/public/api/v1/approvals/&lt;ASSET_TYPE&gt;/&lt;ASSET_ID&gt;</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>方法</p>
      </td>
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">標頭</td>
      <td>
        <p>以標準 JSON 物件的形式新增要求標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion 會自動新增授權標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 查詢字串]  </td>
      <td>
        <p>針對您想要新增至查詢字串的每個索引鍵/值組，按一下<b>新增專案</b>並輸入索引鍵和值。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 正文]</td>
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>



#### 階段欄位

設定階段時，可使用下列欄位。 並非所有欄位都可用於所有模組。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">階段名稱</td>
      <td>輸入或對映舞台的名稱。</td>
    </tr>
     <tr>
      <td role="rowheader"><p>截止日期</p></td>
      <td>如果截止日期是特定日期，請輸入或對應日期。</td> 
      </tr>
  </tbody>
     <tr>
      <td role="rowheader"><p>截止日期營業日</p></td>
      <td>如果截止日期在特定業務天數之後，請輸入或對映天數。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>截止日期</p></td>
      <td>如果截止日期是特定時間，請輸入或對應時間。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>參與者</p></td>
      <td>針對您想要新增至階段的每個參與者，按一下<b>新增專案</b>並輸入參與者詳細資料。      
      <ul>
      <li><b>參與者ID</b><p>輸入或對應參與者的ID。</p></li>
      <li><b>參與者型別</b><p>選取參與者是使用者還是團隊。</p></li>
      <li><b>參與者角色</b><p>選取參與者是核准者還是稽核者。</p></li>
      </ul> 
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>自動鎖定已啟用</p></td>
      <td>指定是否要自動鎖定階段。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>決定規則</p></td>
      <td>選取您是否只想要為階段要求一個決定。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>上層ID /上層階段ID</p></td>
      <td>針對您想要新增至階段的每個父階段，按一下<b>新增專案</b>並輸入父識別碼。</td> 
      </tr>
     <tr>
      <td role="rowheader"><p>觸發程序</p></td>
      <td>若要設定此核准階段的觸發程式，請按一下[新增專案] <b>並輸入觸發程式詳細資料。      </b><ul>
      <li><b>類型</b><p>選取<b>啟用</b></p></li>
      <li><b>當</b><p>選取在建立核准或完成其他階段時是否要觸發階段。</p></li>
      <li><b>階段</b><p>針對您想要新增至觸發程式的每個階段，按一下<b>新增專案</b>，然後輸入或對應階段ID。</p></li>
      <li><b>決策</b><p>針對您想要新增至觸發器的每個決定，按一下<b>新增專案</b>，然後輸入或對應決定。</p></li>
      </ul> 
      </td> 
      </tr>
     <tr>
      <td role="rowheader"><p>自訂訊息</p></td>
      <td>輸入或對應階段的自訂訊息。</td> 
      </tr>
</table>


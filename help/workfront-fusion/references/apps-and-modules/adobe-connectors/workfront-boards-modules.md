---
title: Adobe Workfront主機板模組
description: 您可以使用Adobe Workfront面板聯結器在Workfront面板中自動化您的流程，並將其連線到第三方應用程式和服務。
author: Becky
feature: Workfront Fusion, Workfront Integrations and Apps
exl-id: dcc5044d-8fdf-4a74-b664-e965e714ce92
source-git-commit: 1ea2bf76b0fe6e0b0c7c3c894fbdede224d2cae2
workflow-type: tm+mt
source-wordcount: '2439'
ht-degree: 1%

---

# [!DNL Adobe Workfront]個主機板模組

>[!NOTE]
>
>主機板Fusion聯結器處於測試版狀態。 因此，此聯結器的支援有限，而且可能會因主機板的未來開發而變更。 此外，GraphQL API可能會有所變更，恕不另行通知，這可能會影響您的Fusion聯結器程式。

Adobe Workfront展示板是彈性的工具，可讓團隊透過提供對包含欄和卡片的共用展示板的存取權進行共同作業。

您可以使用Adobe Workfront面板模組來讀取或更新記錄、對Workfront面板API進行API呼叫，或當面板上發生動作時觸發情境。

<!--For general information on Workfront Boards, see [Boards overview](/help/quicksilver/agile/boards-overview.md).-->

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 封裝</td>
  <td> <p>任何</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權</td>
   <td> <p>新增：標準</p><p>或</p><p>目前： [!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]用於Work Automation and Integration]，[!UICONTROL [!DNL Workfront Fusion]用於Work Automation]</p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。


## 先決條件

您必須先在Adobe Workfront中設定主機板，才能連線至該主機板。

## Adobe Workfront面板API資訊

Adobe Workfront面板聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.23.6</td> 
  </tr>
 </tbody> 
 </table>

## 建立與Workfront展示板的連線

>[!NOTE]
>
>您可以使用Workfront連線來連線至Workfront面板，或是建立個別的Workfront面板連線。

若要建立Workfront面板連線：

1. 在任何[!DNL Adobe Workfront Boards]模組中，按一下[連線]方塊旁的&#x200B;**[!UICONTROL Add]**。

1. 填寫下列欄位：

   <table style="table-layout:auto"> 
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1">
      </col>
      <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2">
      </col>
      <tbody>
        <tr>
          <td role="rowheader">[!UICONTROL Connection name]</td>
          <td>
            <p>輸入此連線的名稱。</p>
          </td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Environment]</td>
          <td>選取您要連線到生產或非生產環境。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Type]</td>
          <td>選取您是要連線到服務帳戶還是個人帳戶。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client ID]<p>（可選）</p></td>
          <td>輸入您的[!DNL Adobe] [!UICONTROL Client ID]。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。</td>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Client Secret]<p>（可選）</p></td>
          <td>輸入您的[!DNL Adobe] [!UICONTROL Client Secret]。 您可以在[!DNL Adobe Developer Console]的[!UICONTROL Credentials details]區段中找到此專案。
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Authentication URL]<p>（可選）</p></td>
          <td>輸入您的Workfront執行個體將用來驗證此連線的URL。 <p>預設值為<code>https://oauth.my.workfront.com/integrations/oauth2</code>。</p>
        </tr>
        <tr>
          <td role="rowheader">[!UICONTROL Host prefix]</td>
          <td>輸入您的主機前置詞。<p>預設值為<code>origin-</code>。</p>
        </tr>
      </tbody>
    </table>
1. 按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以儲存連線並返回模組。

## Adobe Workfront面板模組及其欄位

當您設定Workfront面板模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除此之外，可能還會顯示其他Workfront面板欄位，視您應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [卡片](#cards)
* [展示板](#boards)
* [欄](#columns)
* [標記](#tags)
* [評論](#comments)
* [其他](#other)

<!--

### Watch

#### Watch events

This trigger module starts a scenario when an event occurs on a board.

1. Click **[!UICONTROL Add]** to the right of the **Webhook** box.

1. Configure the webhook in the **[!UICONTROL Add a hook]** box that displays.

   When you are configuring this module, the following fields display.

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[!UICONTROL Webhook name]</td> 
      <td>(Optional) Type a new name for the webhook</td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Connection]</td> 
      <td> <p>You can use an existing Workfront connection to connect to Workfront Boards, or you can use a specific Workfront Boards connection. </p><p>For instructions about connecting your [!DNL Workfront] app to [!DNL Workfront Fusion], see <a href="#create-a-connection-to-workfront-boards" class="MCXref xref">Create a connection to Workfront Boards</a> in this article.</p> </td> 
     </tr> 
     <tr> 
      <td>[!UICONTROL Object type]</td> 
      <td>Select the type of [!DNL Workfront] object that you want the module to watch.</td> 
     </tr> 
     <tr> 
      <td> <p>[!UICONTROL Objects to watch]</p> </td> 
      <td> Select whether you want to trigger a scenario when there is a new object, an updated object, a new or updated object, or a deleted object. </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td>Exclude events made by this connection</td> 
      <td>Enable this option to exclude events created or updated using the same connector that this trigger module uses. This can prevent situations where a scenario might trigger itself, causing it to repeat in an endless loop.</td> 
     </tr> 
    </tbody> 
   </table>

After the webhook is created, you can view the address of the endpoint that events are sent to.

-->

### 卡片

* [新增檢查清單項目](#add-checklist-item)
* [新增子任務](#add-subtask)
* [建立卡片](#create-a-card)
* [移動卡片](#move-a-card)
* [讀取卡片](#read-a-card)
* [更新卡片](#update-a-card)

#### 新增檢查清單項目

此動作模組會將檢查清單專案新增至指定的卡片。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對應您要新增檢查清單專案的卡片ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Checklist items]</td> 
   <td>針對您要新增的每個檢查清單專案，按一下「新增專案」，輸入檢查清單專案的名稱，然後選取該專案是否已完成。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 新增子任務

此動作模組會將子任務新增到展示板中的卡片。 此卡片必須是已連線的卡片。 子任務也會新增至卡片所代表的Workfront任務。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Parent card ID]</td> 
   <td>輸入或對應您要新增子任務的卡片ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應包含您要新增子任務之卡片之展示板的ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>輸入或對應新子工作的名稱。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 建立卡片

此動作模組會在Workfront展示板上建立新卡片。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應您要新增卡片之主機板的ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column ID]</td> 
   <td>輸入或對應您要新增子工作的資料行ID。<p>您可以從讀取展示板模組傳回的資訊中找到欄ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>輸入或對應新卡片的名稱。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 移動卡片

此動作模組會將卡片移至相同展示板上的不同欄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對應您要移動之卡片的ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應包含您要移動之卡片的主機板ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Destination column ID]</td> 
   <td>輸入或對應您要移動卡片的目標欄ID。<p>您可以從讀取展示板模組傳回的資訊中找到欄ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL To index]</td> 
   <td>輸入或對應您要卡片在新欄中的位置。<p>索引0中資料行的頂端位置。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 讀取卡片

此動作模組會擷取特定卡片的相關資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對應您要讀取的卡片ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 更新卡片

此動作模組會更新您指定之卡片的資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對應您要更新的卡片ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應包含要更新卡片之展示板的ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Name]</td> 
   <td>輸入或對映卡片的新名稱。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對映卡片的新說明。</p></td> 
  </tr> 
 </tbody> 
</table>

### 展示板

* [建立展示板](#create-a-board)
* [讀取展示板](#read-a-board)

#### 建立展示板

此動作模組會在Workfront中建立展示板。 您可以指定要建立的電路板型別。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board name]</td> 
   <td>輸入或對映新展示板的名稱。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Type]</td> 
   <td>選取您要建立的電路板型別。</td> 
  </tr> 
 </tbody> 
</table>

#### 讀取展示板

此動作模組會傳回單一展示板的資訊，例如展示板的卡片、欄、標籤和成員。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應您要擷取資訊之展示板的ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
 </tbody> 
</table>

### 欄

* [建立欄](#create-a-column)
* [搜尋欄](#search-for-a-column)
* [更新欄](#update-a-column)

#### 建立欄

此動作模組會在指定的展示板上建立新欄。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應您要新增欄的展示板ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column ID]</td> 
   <td>輸入或對應您要更新之欄的ID。<p>您可以從讀取展示板模組傳回的資訊中找到欄ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column name]</td> 
   <td>輸入或對映欄的新名稱。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL WIP Limit]</td> 
   <td>輸入或對應欄位的新在製品限制。</td> 
  </tr> 
 </tbody> 
</table>

#### 搜尋欄

此搜尋模組會傳回指定名稱之資料行的相關資訊。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應包含您要擷取之欄的展示板ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column Name]</td> 
   <td>輸入或對應您要擷取的資料行名稱。</td> 
  </tr> 
 </tbody> 
</table>

#### 更新欄

此動作模組會更新指定欄的名稱或WIP限制。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應包含您要擷取之欄的展示板ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Column Name]</td> 
   <td>輸入或對應您要擷取的資料行名稱。</td> 
  </tr> 
 </tbody> 
</table>

### 標記

* [新增標籤至卡片](#add-card-tag)
* [建立標籤](#create-a-tag)

#### 新增標籤至卡片

此動作模組會將標籤新增至卡片。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對應您要新增標籤的卡片ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應包含您要新增標籤之卡片的主機板ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag ID]</td> 
   <td>輸入或對應您要新增之標籤的ID。<p>您可以從讀取展示板模組傳回的資訊中找到標籤ID。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 建立標籤

此動作模組會建立新標籤並為其指派顏色。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Board ID]</td> 
   <td>輸入或對應您要建立標籤之展示板的ID。<p>在Workfront中檢視展示板時，您可以在URL中找到展示板ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag name]</td> 
   <td>輸入或對映新標籤的名稱。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Tag Color]</td> 
   <td>選取此標籤的顏色。</td> 
  </tr> 
 </tbody> 
</table>

### 評論

* [建立評論](#create-a-comment)
* [讀取卡片註解](#read-card-comments)

#### 建立評論

此動作模組已在指定卡片上建立註解。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對應您要新增註解的卡片ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Comment]</td> 
   <td>輸入或對應您要新增的註解文字。</p></td> 
  </tr> 
 </tbody> 
</table>

#### 讀取卡片註解

此動作模組會從指定的卡片擷取註解。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Card ID]</td> 
   <td>輸入或對應您要擷取註解的卡片ID。<p>在Workfront中檢視卡片時，您可以在URL中找到卡片ID。</p></td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Limit]</td> 
   <td>輸入您希望模組在一個執行週期內傳回的最大註解數。</p></td> 
  </tr> 
 </tbody> 
</table>

### 其他

#### 進行自訂API呼叫

此動作模組會對Workfront看板API進行自訂呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection]</td> 
      <td> <p>您可以使用現有的Workfront連線來連線至Workfront面板，或使用特定的Workfront面板連線。 </p><p>如需有關將您的[!DNL Workfront]應用程式連線到[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#create-a-connection-to-workfront-boards" class="MCXref xref">建立與Workfront展示板的連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>輸入相對於<code> https://&lt;WORKFRONT_DOMAIN&gt;/boards-service/graphql?</code>的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Method]</td> 
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p><p>對於大多數展示板呼叫，方法是POST的。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Headers]</td> 
   <td> <p>以標準JSON物件的形式新增請求的標頭。 這會決定請求的內容型別。</p> <p>例如，<code> { "Content-type":"application/json-stringify()"}</code></p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Query String]</td> 
   <td> <p>以標準JSON物件的形式新增API呼叫的查詢。</p> <p>若為Workfront面板，此區段通常會保留空白。</p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Body]</td> 
   <td> <p>以JSON內嵌Graphql的形式，新增API呼叫的內文內容 </p> <p>範例：</p><p>此範例會更新欄名稱。 您可以將<code>boardId</code>和<code>columnId</code>加入為GUID，以硬式編碼或對映自先前的模組。<p><pre>{<br> "query"： "mutation { updateColumn(boardId： \"\"， columnId： \"\"， updateColumnInput： { name： \"\" }) { id name }}"<br>}</pre><p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

---
title: Adobe Workfront 規劃模組
description: 透過 [!DNL Adobe Workfront Planning] 模組，您可以根據 [!DNL Adobe] Adobe Workfront Planning帳戶中的事件來啟動Workfront Fusion案例、建立、讀取或更新合約與其他記錄、使用您設定的條件搜尋記錄，以及上傳檔案。
author: Becky
feature: Workfront Fusion
exl-id: d1bc9e39-da49-4090-a106-14b52855bc8f
TQID: https://experienceleague.adobe.com/QHOFWDOT-18-c0b3wLXsRV5cjGVxlcyLhvZdkev3GFg
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2:
  - id: f48b5020-b9cd-4d99-bc6e-42c35e90c1f8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: f0e185778e01b71a91837531a082e88485e97ca2
workflow-type: tm+mt
source-wordcount: 6075
ht-degree: 34%

---


# Adobe Workfront 規劃模組

透過[!DNL Adobe Workfront Planning]模組，您可以在Workfront Planning中發生事件時觸發案例。 您也可以建立、讀取、更新及刪除記錄，或執行自訂API呼叫至您的[!DNL Adobe Workfront Planning]帳戶。

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

您必須具備下列專案才能存取Workfront Planning：

* 新的Workfront套件和授權。 Workfront計畫不適用於舊版Workfront套件或授權。
* Workfront計畫套件。
* 貴組織的Workfront執行個體必須上線至Adobe統一體驗。

## Adobe Workfront規劃API資訊

Adobe Workfront Planning聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td><pre><code>https://&#123;&#123;connection.host&#125;&#125;/maestro/api/&#123;&#123;common.maestroApiVersion&#125;&#125;/</code></pre></td> 
  </tr>
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.13.7</td> 
  </tr>
 </tbody> 
 </table>

## 將Workfront Planning連線至Workfront Fusion

Workfront Planning聯結器使用OAuth 2.0連線至Workfront Planning。

您可以直接從Workfront Planning Fusion模組內建立與Workfront Planning帳戶的連線。

* [使用使用者端ID和使用者端密碼連線至Workfront Planning](#connect-to-workfront-planning-using-client-id-and-client-secret)
* [使用伺服器對伺服器連線來連線至Workfront Planning](#connect-to-workfront--planning-using-a-server-to-server-connection)

### 使用使用者端ID和使用者端密碼連線至Workfront Planning

1. 在任何Adobe Workfront Planning模組中，按一下「連線」欄位旁的&#x200B;**新增**。
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
          <p>選取<b>Adobe Workfront驗證</b>連線。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 連線名稱]</td>
        <td>
          <p>輸入新連線的名稱。</p>
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
        <td role="rowheader">[!UICONTROL 驗證 URL]</td>
        <td>此欄位可維持預設值，或者您可以輸入 Workfront 實例的 URL 且後面接著 <code>/integrations/oauth2</code>。 <p>範例： <code>https://mydomain.my.workfront.com/integrations/oauth2</code></p></td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 主機前置詞]</td>
        <td>在大多數情況下，此值應為 <code>origin</code>。
      </tr>
    </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

   如果您未登入Workfront Planning，系統會將您導向至登入畫面。 登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API 的 OAuth 2.0 連線不再依賴 API 金鑰。
>* 若要建立與 Workfront 沙箱環境的連線，您必須在該環境中建立 OAuth2 應用程式，然後在您的連線中使用該應用程式產生的用戶端 ID 和用戶端密碼。

### 使用伺服器對伺服器連線來連線至Workfront Planning

1. 在任何Adobe Workfront Planning模組中，按一下「連線」欄位旁的&#x200B;**新增**。
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

   如果您未登入Workfront Planning，系統會將您導向至登入畫面。 登入後，您可以允許連線。

>[!NOTE]
>
>* Workfront API 的 OAuth 2.0 連線不再依賴 API 金鑰。
>* 若要建立與 Workfront 沙箱環境的連線，您必須在該環境中建立 OAuth2 應用程式，然後在您的連線中使用該應用程式產生的用戶端 ID 和用戶端密碼。

## [!DNL Adobe Workfront Planning]版本2模組及其欄位

>[!IMPORTANT]
>
>本節中的模組屬於Workfront Planning V2聯結器。如需Workfront規劃V1聯結器中的模組，請參閱[[!DNL Adobe Workfront Planning] 第1版模組及其欄位](#adobe-workfront-planning-version-1-modules-and-their-fields)。

當您設定Workfront Planning模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 Workfront 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

* [工作區](#workspaces-v2)
* [記錄類型](#record-types-v2)
* [記錄](#records-v2)
* [欄位](#fields-v2)
* [檢視](#views-v2)
* [權限](#permissions-v2)
* [其他](#other-v2)

### 工作區(V2)

* [建立工作區](#create-a-workspace-v2)
* [刪除工作區](#delete-a-workspace-v2)
* [取得所有工作區](#get-all-workspaces-v2)
* [取得工作區](#get-a-workspace-v2)
* [更新工作區](#update-a-workspace-v2)

#### 建立工作區(V2)

此動作模組會在Planning中建立新的工作區。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace名稱]</p>
      </td>
      <td>輸入或對應新工作區的名稱。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>說明</p>
      </td>
      <td>輸入或對應新工作區的描述/td&gt; 
    </tr>
    <tr>
      <td role="rowheader">
        <p>顏色</p>
      </td>
      <td>選取您要用來代表新記錄型別的顏色</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>圖示</p>
      </td>
      <td>對應您要用於此記錄型別的圖示。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>所有者</p>
      </td>
      <td>輸入或對應您要擁有工作區之使用者的Adobe IMS使用者ID。</td> 
    </tr>
  </tbody>
</table>

#### 刪除工作區(V2)

此動作模組會刪除ID所指定的單一工作區。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 工作區 ID]</p>
      </td>
      <td>輸入或對應您要刪除之工作區的ID。</td> 
    </tr>
  </tbody>
</table>

#### 取得所有工作區(V2)

此模組會擷取所有工作區的清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 傳回工作區的最大數量]</p>
      </td>
      <td>輸入或對應模組在一個執行週期內傳回的最大工作區數量。</td> 
    </tr>
  </tbody>
</table>

#### 取得工作區(V2)

此模組會依其ID擷取工作區。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 工作區 ID]</p>
      </td>
      <td>輸入或對應您要擷取之工作區的ID。</td> 
    </tr>
  </tbody>
</table>

#### 更新工作區(V2)

此動作模組會更新Planning中的新工作區。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要更新的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace名稱]</p>
      </td>
      <td>輸入或對應新工作區的名稱。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>說明</p>
      </td>
      <td>輸入或對應新工作區的描述/td&gt; 
    </tr>
    <tr>
      <td role="rowheader">
        <p>顏色</p>
      </td>
      <td>選取您要用來代表新記錄型別的顏色</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>圖示</p>
      </td>
      <td>對應您要用於此記錄型別的圖示。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>所有者</p>
      </td>
      <td>輸入或對應您要擁有工作區之使用者的Adobe IMS使用者ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>記錄型別區段</p>
      </td>
      <td>針對您想要新增至此工作區的每個記錄型別區段，按一下<b>新增專案</b>，然後輸入區段名稱、記錄型別ID以及是否要覆寫現有的記錄型別ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>記錄型別區段&gt;覆寫</p>
      </td>
      <td>選取是否以模組中的區段取代現有區段。 如果沒有，則會將模組中的區段新增至現有的區段清單中。</td> 
    </tr>
  </tbody>
</table>


### 記錄型別(V2)

* [建立記錄型別](#create-a-record-type-v2)
* [刪除記錄型別](#delete-a-record-type-v2)
* [取得全域記錄型別](#get-global-record-types-v2)
* [取得記錄型別](#get-a-record-type-v2)
* [取得記錄型別](#get-record-types-v2)
* [更新記錄型別](#update-a-record-type-v2)

#### 建立記錄型別(V2)

此動作模組會在選取的工作區中建立新的記錄型別。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要建立記錄型別的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>顯示名稱</p>
      </td>
      <td>輸入或對應新記錄型別的名稱。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>說明</p>
      </td>
      <td>輸入或對應新記錄型別的描述。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>圖示</p>
      </td>
      <td>對應您要用於此記錄型別的圖示。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>顏色</p>
      </td>
      <td>選取您要用來代表新記錄型別的顏色</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>Source記錄型別</p>
      </td>
      <td>如果您要使用其他記錄型別作為起點，請選取該記錄型別。</td> 
    </tr>
  </tbody>
</table>

#### 刪除記錄型別(V2)

此動作模組會刪除由ID指定的單一記錄型別。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄型別的ID。</td> 
    </tr>
  </tbody>
</table>

#### 取得全域記錄型別(V2)

此模組會擷取Adobe Workfront Planning帳戶中的記錄型別清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取工作區。 此模組將傳回可新增至此工作區的全域記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 傳回記錄型別的最大數目]</p>
      </td>
      <td>輸入或對應模組在一個執行週期內傳回的最大記錄型別數目。</td> 
    </tr>
  </tbody>
</table>

#### 取得記錄型別(V2)

此模組會依其ID擷取記錄型別。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要擷取的記錄型別ID。</td> 
    </tr>
  </tbody>
</table>

#### 取得記錄型別(V2)

此模組會擷取指定工作區中可用的記錄型別清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要擷取記錄型別的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 傳回記錄型別的最大數目]</p>
      </td>
      <td>輸入或對應模組在一個執行週期內傳回的最大記錄型別數目。</td> 
    </tr>
  </tbody>
</table>

#### 更新記錄型別(V2)

此模組會更新記錄型別。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要更新記錄型別的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要更新記錄型別的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>顯示名稱</p>
      </td>
      <td>輸入或對應記錄型別的名稱。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>說明</p>
      </td>
      <td>輸入或對應記錄型別的描述。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>主要欄位ID</p>
      </td>
      <td>輸入或對應做為記錄型別標題之欄位的ID。</td> 
    </tr>
     <tr>
      <td role="rowheader">
        <p>圖示</p>
      </td>
      <td>對應您要用於此記錄型別的圖示。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>顏色</p>
      </td>
      <td>選取您要用來代表新記錄型別的顏色</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>可與Workspace ID連結</p>
      </td>
      <td>對於您想要此記錄型別能夠連結到的每個工作區，按一下<b>新增專案</b>並輸入工作區的ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>可與Workspace ID連結&gt;覆寫</p>
      </td>
      <td>選取是否要以模組中的工作區取代現有工作區。 如果否，則來自模組的工作區會新增至現有的工作區清單中。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>已授權建立動態記錄型別</p>
      </td>
      <td>對於獲授權從此記錄型別建立動態記錄型別的每個主體，按一下<b>新增專案</b>並輸入主體的型別和ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>已授權建立動態記錄型別&gt;覆寫</p>
      </td>
      <td>選取是否以模組中的主題取代現有主題。 如果沒有，則會將模組中的主題新增至現有主題清單。</td> 
    </tr>
  </tbody>
</table>



### 記錄(V2)

* [建立記錄](#create-a-record-v2)
* [刪除記錄](#delete-a-record-v2)
* [取得記錄](#get-a-record-v2)
* [依記錄型別取得記錄](#get-records-by-record-type-v2)
* [移動記錄](#move-records-v2)
* [搜尋記錄](#search-records-v2)
* [更新記錄](#update-a-record-v2)

#### 建立記錄(V2)

這個動作會在Workfront Planning中建立單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要建立記錄的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要建立的記錄類型。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>輸入您希望新記錄具有的值。 這些欄位是根據您選取的記錄型別，對您的Workfront Planning組織而言是唯一的。</td> 
    </tr>
  </tbody>
</table>

#### 刪除記錄(V2)

此動作模組會刪除ID所指定的單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄的ID。</td> 
    </tr>
  </tbody>
</table>

#### 取得記錄(V2)

此動作模組會擷取由其ID指定的記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 工作區 ID]</p>
      </td>
      <td>輸入或對應您要擷取之記錄的ID。</td> 
    </tr>
  </tbody>
</table>

#### 依記錄型別取得記錄(V2)

此模組會擷取指定記錄型別的所有記錄清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含您要擷取之記錄的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要傳回的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 傳回記錄的最大數量]</p>
      </td>
      <td>輸入或對應模組在一個執行週期內傳回的最大記錄數。</td> 
    </tr>
  </tbody>
</table>

#### 移動記錄(V2)

此模組會指定記錄型別的放置位置，以重新排序一或多個記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含您要移動之記錄的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要移動的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含您要移動之記錄的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含您要移動之記錄的工作區。</td> 
    </tr>
  </tbody>
</table>

#### 搜尋記錄(V2)

根據您指定的條件傳回記錄

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含您要擷取之記錄的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取包含您要擷取之記錄的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 其他欄位]</p>
      </td>
      <td>針對您想要作為篩選依據的每個欄位，輸入該欄位的運運算元和值。 這些欄位是根據您選取的記錄型別，對您的Workfront Planning組織而言是唯一的。</td> 
    </tr>
  </tbody>
</table>

#### 更新記錄(V2)

此模組會更新指定的記錄。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含您要更新之記錄的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>選取您要更新的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要更新的記錄ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 其他欄位]</p>
      </td>
      <td>輸入其他欄位的值。 可用欄位取決於選取的記錄。</td> 
    </tr>
  </tbody>
</table>


### 欄位(V2)

* [建立欄位](#create-a-field-v2)
* [刪除欄位](#delete-a-field-v2)
* [取得欄位](#get-a-field-v2)
* [依記錄型別取得欄位](#get-fields-by-record-type-v2)
* [更新欄位](#update-a-field-v2)

#### 建立欄位(V2)

此動作模組會在指定的記錄型別上建立新欄位。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要建立欄位的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要建立欄位的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>顯示名稱</p>
      </td>
      <td>輸入或對應新欄位的名稱。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>說明</p>
      </td>
      <td>輸入或對應新欄位的說明。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>欄位類型</p>
      </td>
      <td>選取欄位的資料型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>所選欄位型別特定的其他欄位可能可供使用。 填寫這些欄位的值。</td> 
    </tr>
  </tbody>
</table>

#### 刪除欄位(V2)

此動作模組會刪除ID所指定的單一欄位。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 欄位ID]</p>
      </td>
      <td>輸入或對應要刪除的欄位之 ID。</td> 
    </tr>
  </tbody>
</table>

#### 取得欄位(V2)

此模組會依其ID擷取欄位。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 欄位ID]</p>
      </td>
      <td>輸入或對應您要擷取的欄位ID。</td> 
    </tr>
  </tbody>
</table>

#### 依記錄型別取得欄位(V2)

此模組會擷取特定記錄型別的欄位清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含要傳回欄位的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要傳回欄位的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 傳回欄位數上限]</p>
      </td>
      <td>輸入或對應模組在一個執行週期內傳回的最大欄位數。</td> 
    </tr>
  </tbody>
</table>

#### 更新欄位(V2)

此模組會透過其ID部分更新欄位。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源型別]</p>
      </td>
      <td>選取包含要更新欄位的資源型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 欄位ID]</p>
      </td>
      <td>選取您要更新的欄位。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 顯示名稱]</p>
      </td>
      <td>輸入或對應欄位的名稱。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 說明]</p>
      </td>
      <td>輸入或對應欄位的說明。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 其他引數]</p>
      </td>
      <td>輸入其他欄位引數的值。 可用的引數視選取的欄位而定。</td> 
    </tr>
  </tbody>
</table>


### 檢視(V2)

* [建立檢視](#create-a-view-v2)
* [刪除檢視](#delete-a-view-v2)
* [取得檢視](#get-a-view-v2)
* [依記錄型別取得檢視](#get-views-by-record-type-v2)
* [更新檢視](#update-a-view-v2)

#### 建立檢視(V2)

此動作模組會針對選取的記錄型別建立新的檢視。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要建立檢視的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要建立檢視的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>檢視名稱</p>
      </td>
      <td>輸入或對應新檢視的名稱。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>檢視類型</p>
      </td>
      <td>選取新檢視是表格、時間表或行事曆檢視。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>開始日期欄位</p>
      </td>
      <td>如果檢視是時間軸或行事曆檢視，請選取檢視將用來將記錄置於時間軸上的欄位。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>結束日期欄位。</p>
      </td>
      <td>如果檢視是時間表或行事曆檢視，請選取檢視將用於決定時間表結束日期的欄位。</td> 
    </tr>
  </tbody>
</table>

#### 刪除檢視(V2)

此動作模組會刪除ID所指定的單一檢視。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 檢視ID]</p>
      </td>
      <td>輸入或對應您要刪除之檢視的ID。</td> 
    </tr>
  </tbody>
</table>

#### 取得檢視(V2)

此模組會依ID擷取檢視。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 檢視ID]</p>
      </td>
      <td>輸入或對應您要擷取的檢視ID。</td> 
    </tr>
  </tbody>
</table>

#### 依記錄型別取得檢視(V2)

此模組會擷取特定記錄型別的檢視清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取包含您要擷取之檢視的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取包含要擷取之檢視的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 傳回檢視的最大數目]</p>
      </td>
      <td>輸入或對應模組在一個執行週期內傳回的最大檢視次數。</td> 
    </tr>
  </tbody>
</table>

#### 更新檢視(V2)

此動作模組會更新指定的檢視。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>選取您要更新檢視的工作區。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要更新檢視表的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>檢視 ID</p>
      </td>
      <td>選取您要更新的檢視。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>檢視名稱</p>
      </td>
      <td>輸入或對應新檢視的名稱。</td> 
    </tr>
  </tbody>
</table>

### 許可權(V2)

* [關閉存取要求](#dismiss-access-requests-v2)
* [取得資源的所有成員及其角色](#get-all-members-and-their-roles-for-a-resource-v2)
* [取得目前使用者對資源的有效許可權](#get-the-current-users-effective-permissions-on-a-resource-v2)
* [列出資源的擱置中存取要求](#list-pending-access-requests-for-a-resource-v2)
* [要求存取資源](#request-access-to-a-resource-v2)

#### 關閉存取要求(V2)

此動作模組會解除一或多個由ID指定的存取要求。



<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源型別]</p>
      </td>
      <td>輸入或對應您要刪除之Workspace的ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源ID]</p>
      </td>
      <td>輸入或對應您要解除存取要求的資源ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 請求ID]</p>
      </td>
      <td>針對您想要解除的每個存取要求，按一下[新增專案] <b>並輸入要求識別碼。</b></td> 
    </tr>
  </tbody>
</table>

#### 取得資源(V2)的所有成員及其角色

此模組會列出資源上擁有明確共用關係的所有使用者、群組和專案團隊。 此模組連線中使用的認證必須具有資源的管理許可權。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源型別]</p>
      </td>
      <td>選取您要擷取資訊的資源型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源ID]</p>
      </td>
      <td>輸入或對應您要擷取資訊之資源的ID。</td> 
    </tr>
  </tbody>
</table>

#### 取得目前使用者對資源(V2)的有效許可權

此模組會傳回目前使用者對指定資源的檢視、編輯、刪除和新增許可權。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源型別]</p>
      </td>
      <td>選取您要擷取許可權的資源型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源ID]</p>
      </td>
      <td>輸入或對應您要擷取許可權之資源的ID。</td> 
    </tr>
  </tbody>
</table>

#### 列出資源的擱置存取要求(V2)

此模組會傳回指定資源的所有擱置存取要求。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源型別]</p>
      </td>
      <td>選取您要擷取資訊的資源型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源ID]</p>
      </td>
      <td>輸入或對應您要擷取資訊之資源的ID。</td> 
    </tr>
  </tbody>
</table>

#### 要求存取資源(V2)

此模組會針對指定資源上的目前使用者建立或更新存取要求。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源型別]</p>
      </td>
      <td>選取您要建立或更新存取要求的資源型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 資源ID]</p>
      </td>
      <td>輸入或對應您要建立或更新存取要求的資源ID。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 訊息]</p>
      </td>
      <td>輸入或對應您要包含在存取要求中的訊息文字。</td> 
    </tr>
  </tbody>
</table>



### 其他(V2)

* [從Workfront ID取得驗證ID](#get-auth-id-from-workfront-id-v2)
* [進行自訂的 API 呼叫](#make-a-custom-api-call-v2)
* [觀看事件](#watch-events-v2)

#### 從Workfront ID (V2)取得驗證識別碼

此模組採用Workfront使用者ID並傳回Planning使用的相符授權ID。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workfront使用者ID]</p>
      </td>
      <td>輸入或對應您要擷取授權ID之使用者的Workfront ID。</td> 
    </tr>
  </tbody>
</table>

#### 進行自訂API呼叫(V2)&lt;表格

此模組會對Workfront Planning API進行自訂呼叫。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>關於將 Workfront 應用程式連接至 Workfront Fusion 的說明，請參閱這篇文章中的<a href="#connect-workfront-to-workfront-fusion" class="MCXref xref">將 Workfront 連接至 Workfront Fusion</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">URL</td> 
   <td> <p>輸入相對於 <code> https://&lt;WORKFRONT_DOMAIN>/maestro/api/.</code> 的路徑。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL API 版本]</td> 
   <td>選取您要模組使用的 Workfront API 版本。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 方法]</td> 
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">Adobe Workfront Fusion 中的 HTTP 要求方法</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 標頭]</td> 
   <td> <p>以標準 JSON 物件的形式新增要求標頭。 此資訊會決定請求的內容類型。</p> <p>例如，<code> {"Content-type":"application/json"}</code></p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 查詢字串]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的查詢。</p> <p>例如： <code>{"name":"something-urgent"}</code></p> <p>提示：建議您透過 JSON 正文而非查詢參數傳送資訊。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 正文]</td> 
   <td> <p>以標準 JSON 物件的形式新增 API 呼叫的正文內容。</p> <p>注意：  <p>在 JSON 中使用條件陳述式 (例如 <code>if</code>) 時，請將引號放在條件陳述式的外面。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td> 
  </tr> 
 </tbody> 
</table>

#### 觀看活動(V2)

在Workfront Planning中建立、更新或刪除記錄、記錄型別或工作區時，此觸發模組會啟動案例。

>[!IMPORTANT]
>
>您稍後可以編輯此模組，此模組將編輯webhook。
>
>更新webhook時，請考量下列事項：
>
>* Workfront事件訂閱會將編輯後的webhook視為新訂閱。 系統不會保留先前webhook設定的事件訂閱歷史記錄，因為這會視為個別的事件訂閱。
>* 從舊事件訂閱切換到新事件訂閱可能不會完全同步。 因此，可能會收到事件兩次（如果新訂閱在舊訂閱停止之前開始執行），或錯過事件（如果舊訂閱在新訂閱開始執行之前停止）。
>
>如需有關編輯webhook的詳細資訊，請參閱[編輯webhook](/help/workfront-fusion/manage-scenarios/edit-webhooks.md)。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>選取您要使用的webhook，或按一下「新增」以建立新的webhook。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 物件類型]</td>
      <td>選取您要監視記錄、記錄型別或工作區。</td>
    </tr>
    <tr>
      <td role="rowheader">要觀看的[!UICONTROL 物件]</td>
      <td>選取您要監視新記錄、更新的記錄、新記錄和更新的記錄，還是刪除的記錄。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 組態型別]</td>
      <td>選取您要簡單設定還是進階設定。 <p>如需進階設定的詳細資訊，請參閱本文章中的<a href="#example-of-advanced-logic-in-the-watch-events-module" class="MCXref xref" >觀看事件模組</a>中的進階邏輯範例。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 狀態]</td>
      <td>選取您要監視舊狀態或新狀態。<ul><li><p><b>[!UICONTROL 新狀態]</b></p><p>當記錄變更<b>為</b>特定值時觸發一個情境。</p></li><li><p><b>[!UICONTROL 舊狀態]</b></p><p>當記錄<b>從</b>特定值變更為其他時會觸發一個情境。</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>如果觀看記錄，請選取您要觀看記錄的Workspace 。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄類型]</td>
      <td>如果觀看記錄，請選取您要觀看的記錄型別。</td>
    </tr>
    </tr>
    <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL 事件篩選器]</p> </td> 
      <td> <p>您可以設定篩選器為僅監視符合所選取條件的記錄。</p> <p>對於每個篩選器，輸入您要篩選器評估的欄位、運算子，以及要讓篩選器允許的值。 您可以新增 AND 規則，以便使用一個以上的篩選器。</p> <p>注意：您無法編輯現有Workfront Webhook中的篩選器。 若要為 Workfront 事件訂閱設定不同的篩選器，請移除目前的 Webhook 並建立新的。</p> <p>如需事件篩選的詳細資訊，請參閱Workfront模組文章中的Workfront &gt; [!UICONTROL 觀看活動]模組中的<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">事件訂閱篩選</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">要觀看的[!UICONTROL 物件]</td>
      <td>選取是否要監視新專案。 更新、新增和更新或刪除的記錄。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 排除此連線所做的更新]</p>
      </td>
      <td>啟用此選項可防止此模組使用的連線進行變更時觸發此案例。 如此可防止在此案例執行觸發動作時觸發另一個案例例項。</td> 
    </tr>
  </tbody>
</table>

如需在此模組上使用進階邏輯的範例，請參閱監視事件模組[&#128279;](#example-of-advanced-logic-in-the-watch-events-module)中的進階邏輯範例。






## [!DNL Adobe Workfront Planning]版本1模組及其欄位

>[!IMPORTANT]
>
>本節中的模組屬於Workfront規劃V1聯結器。如需Workfront規劃V2聯結器中的模組，請參閱[[!DNL Adobe Workfront Planning] 版本2模組及其欄位](#adobe-workfront-planning-version-2-modules-and-their-fields)。

當您設定Workfront Planning模組時，Workfront Fusion會顯示下列欄位。 除了這些欄位以外，也可能因為其他因素，例如您在應用程式或服務中的存取層級，而顯示其他 Workfront 欄位。 在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。


![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [觸發程序](#triggers)
* [動作](#actions)
* [搜尋](#searches)
* [未分類](#uncategorized)

### 觸發程序

#### 觀看事件

在Workfront Planning中建立、更新或刪除記錄、記錄型別或工作區時，此觸發模組會啟動案例。

>[!IMPORTANT]
>
>您稍後可以編輯此模組，此模組將編輯webhook。
>
>更新webhook時，請考量下列事項：
>
>* Workfront事件訂閱會將編輯後的webhook視為新訂閱。 系統不會保留先前webhook設定的事件訂閱歷史記錄，因為這會視為個別的事件訂閱。
>* 從舊事件訂閱切換到新事件訂閱可能不會完全同步。 因此，可能會收到事件兩次（如果新訂閱在舊訂閱停止之前開始執行），或錯過事件（如果舊訂閱在新訂閱開始執行之前停止）。
>
>如需有關編輯webhook的詳細資訊，請參閱[編輯webhook](/help/workfront-fusion/manage-scenarios/edit-webhooks.md)。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Webhook]</td>
      <td>選取您要使用的webhook，或按一下「新增」以建立新的webhook。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 物件類型]</td>
      <td>選取您要監視記錄、記錄型別或工作區。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 狀態]</td>
      <td>選取您要監視舊狀態或新狀態。<ul><li><p><b>[!UICONTROL 新狀態]</b></p><p>當記錄變更<b>為</b>特定值時觸發一個情境。</p></li><li><p><b>[!UICONTROL 舊狀態]</b></p><p>當記錄<b>從</b>特定值變更為其他時會觸發一個情境。</p></li></ul></td> 
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>如果觀看記錄，請選取您要觀看記錄的Workspace 。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄類型]</td>
      <td>如果觀看記錄，請選取您要觀看的記錄型別。</td>
    </tr>
    </tr>
    <tr data-mc-conditions=""> 
      <td> <p>[!UICONTROL 事件篩選器]</p> </td> 
      <td> <p>您可以設定篩選器為僅監視符合所選取條件的記錄。</p> <p>對於每個篩選器，輸入您要篩選器評估的欄位、運算子，以及要讓篩選器允許的值。 您可以新增 AND 規則，以便使用一個以上的篩選器。</p> <p>注意：您無法編輯現有Workfront Webhook中的篩選器。 若要為 Workfront 事件訂閱設定不同的篩選器，請移除目前的 Webhook 並建立新的。</p> <p>如需事件篩選的詳細資訊，請參閱Workfront模組文章中的Workfront &gt; [!UICONTROL 觀看活動]模組中的<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/workfront-modules.md#event-subscription-filters-in-the-workfront--watch-events-modules" class="MCXref xref">事件訂閱篩選</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">要觀看的[!UICONTROL 物件]</td>
      <td>選取是否要監視新專案。 更新、新增和更新或刪除的記錄。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 排除此連線所做的更新]</p>
      </td>
      <td>啟用此選項可防止此模組使用的連線進行變更時觸發此案例。 如此可防止在此案例執行觸發動作時觸發另一個案例例項。</td> 
    </tr>
  </tbody>
</table>

如需在此模組上使用進階邏輯的範例，請參閱監視事件模組[&#128279;](#example-of-advanced-logic-in-the-watch-events-module)中的進階邏輯範例。

### 動作

* [刪除記錄型別](#delete-a-record-type)
* [進行自訂AI呼叫](#make-a-custom-api-call)

#### 刪除記錄型別

此動作模組會依據其ID刪除Workfront Planning中的單一記錄型別。

>[!WARNING]
>
>刪除Workfront Planning中的記錄型別也會刪除記錄型別表格中的所有記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄型別的ID。</td> 
    </tr>
  </tbody>
</table>

#### 進行自訂的 API 呼叫

此模組會對[!DNL Adobe Workfront Planning] API發出自訂API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL URL]</p>
      </td>
      <td>
        <p>輸入相對於 <code>https://(YOUR_WORKFRONT_DOMAIN)/maestro/api/</code></p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
      </td>
   <td> <p>選取您設定 API 呼叫所需的 HTTP 要求方法。 如需詳細資訊，請參閱 <a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP 要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 標頭]</td>
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


### 搜尋

#### 搜尋記錄

此動作模組會根據您指定的條件擷取記錄清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Workspace]</p>
      </td>
      <td>輸入或對應包含您要搜尋之記錄的Workspace。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄類型]</p>
      </td>
      <td>選取您要搜尋的記錄型別。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄欄位]</p>
      </td>
      <td>針對搜尋中要使用的每個欄位，找到該欄位，選取運運算元，然後輸入或對應您要搜尋的值。 根據所選的記錄型別，可使用欄位。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 篩選條件]</p>
      </td>
      <td>選取篩選條件：<ul><li><b>且</b><p>模組傳回符合您選取之欄位值的<b>所有</b>的記錄。</p></li><li><b>或</b><p>模組傳回符合您選取之欄位值的<b>任一</b>的記錄。</p></li></ul></td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 限制]</p>
      </td>
   <td> <p>輸入或對應您要此模組在每個情境執行週期中傳回的最大記錄數量。</p> </td> 
    </tr>
  </tbody>
</table>


### 未分類


#### 建立記錄

這個動作會在Workfront Planning中建立單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄型別ID]</p>
      </td>
      <td>輸入或對應您要建立的記錄型別。 可用的記錄型別取決於您的Workfront Planning帳戶。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>輸入您希望新記錄具有的值。 這些欄位是根據您選取的記錄型別。</td> 
    </tr>
    <tr>
  </tbody>
</table>

### 刪除記錄

此動作模組會刪除Workfront Planning中的指定記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要刪除之記錄的ID。</td> 
    </tr>
  </tbody>
</table>

### 取得記錄

此動作模組會從其ID所指定的[!DNL Adobe Workfront Planning]擷取單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄ID]</td>
      <td>輸入或對應您要擷取之記錄的ID。</td>
    </tr>
  </tbody>
</table>

### 依記錄型別取得記錄

此動作模組會擷取指定型別的所有記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>選取或對映包含您要擷取之記錄的工作區。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄類型]</td>
      <td>選取您要擷取的記錄型別。</td>
    </tr>
    <!--
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL Maximum number of returned records]</p>
      </td>
      <td>Enter or map the maximum number of records you want the module to return during each scenario execution cycle.</td>
    </tr>
    -->
  </tbody>
</table>

### 取得記錄型別

此動作模組會擷取[!DNL Adobe Workfront Planning]帳戶中的記錄型別清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>選取或對應包含您要擷取之記錄型別的工作區。</td>
    </tr>
  </tbody>
</table>

### 更新記錄

此動作會更新Workfront Planning中的單一記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 連線]</td>
      <td>關於建立與 [!DNL Adobe Workfront Planning] 的連線的說明，請參閱這篇文章中的<a href="#create-a-connection-to-adobe-workfront-planning" class="MCXref xref" >建立與 [!DNL Adobe Workfront Planning]</a> 的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 記錄ID]</p>
      </td>
      <td>輸入或對應您要更新的記錄型別。 可用的記錄型別取決於您的Workfront Planning帳戶。</td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>其他欄位</p>
      </td>
      <td>輸入您要記錄的新值。 這些欄位是根據您選取的記錄型別。</td> 
    </tr>
    <tr>
  </tbody>
</table>


## 使用JSONata進行可讀取的`record-types`劃分

下列JSONata運算式會建立可讀取的Planning查詢輸出，提供您記錄型別劃分。 這使記錄型別名稱、欄位名稱和欄位選項名稱（如果適用）可由名稱讀取，並保持結構的其餘部分不變。

```
(
    $s0 := ({"data":$ ~> | fields | {"options":(options){name:$}} |});
    $s1 := ({"data":$s0.data ~> | **.fields | {"options_name":(options.*){displayName:$}} | });
    $s2 := $s1 ~> | data | {"fields":(fields){displayName:$}} |; 
    $s2.data{displayName:$}
)
```

如需有關使用JSONata模組的資訊，請參閱[JSONata模組](/help/workfront-fusion/references/apps-and-modules/tools-and-transformers/jsonata-module.md)。

## 監看事件模組中的進階邏輯範例

這是進階邏輯在使用「Workfront規劃>觀看事件」模組時所採用格式的範例。

```
[
  {
    "fieldName": "recordTypeId",
    "fieldValue": "Rt68c886502d4b5554ee80896b",
    "comparison": "eq",
    "state": "newState"
  },
  {
    "fieldName": "data",
    "fieldValue": {
      "F68c886502d4b5554ee808975": "planning"
    },
    "comparison": "eq",
    "state": "newState"
  },
  {
    "fieldName": "data",
    "fieldValue": {
      "F68c886502d4b5554ee808975": "active"
    },
    "comparison": "eq",
    "state": "newState"
  }
]
```

在「觀看事件」模組使用進階邏輯時，請考量下列事項：

* 第一個`"fieldvalue":`專案是從URL提取的計畫記錄型別ID。 在此範例中，Planning記錄型別識別碼為`Rt68c886502d4b5554ee80896b`。
* Planning資料傳回名為`data `的陣列中，此範例中顯示為`"fieldName": "data"`。
* 規劃fieldNames會傳回為以`F`開頭的ID。
* 因為此範例是針對`OR`篩選器聯結器進行評估，所以它有兩個相同欄位(`F68c886502d4b5554eec808975`)的專案。  模組篩選依據的兩個下拉式清單選項是`"planning"`和`"active"`。


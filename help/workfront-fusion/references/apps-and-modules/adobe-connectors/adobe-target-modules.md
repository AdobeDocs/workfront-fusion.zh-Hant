---
title: Adobe Target模組
description: 在 [!DNL Adobe Workfront Fusion] 案例中，您可以自動執行使用 [!DNL Adobe Target], as well as connect it to multiple third-party applications and services. [!DNL Adobe Target] 模組的工作流程，讓您建立、讀取、更新或刪除記錄、列出特定型別的所有記錄、根據您指定的條件搜尋記錄，或對 [!DNL Adobe Target] API執行自訂API呼叫。
author: Becky
feature: Workfront Fusion
exl-id: f3c1ed7b-b69b-478a-8240-1a2ab89e11e5
source-git-commit: 899fc717f5107433d6f1aea31c4d079243a85822
workflow-type: tm+mt
source-wordcount: '2259'
ht-degree: 0%

---

# [!DNL Adobe Target]模組

在[!DNL Adobe Workfront Fusion]案例中，您可以自動化使用[!DNL Adobe Target]的工作流程，並將其連線至多個協力廠商應用程式和服務。 [!DNL Adobe Target]模組可讓您建立、讀取、更新或刪除記錄、列出特定型別的所有記錄、根據您指定的條件搜尋記錄，或執行對[!DNL Adobe Target] API的自訂API呼叫。


如果您需要建立案例的指示，請參閱[建立案例：文章索引](/help/workfront-fusion/create-scenarios/create-scenarios-toc.md)下的文章。

如需有關模組的資訊，請參閱[模組：文章索引](/help/workfront-fusion/references/modules/modules-toc.md)下的文章。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
      <td>
        <p>[!UICONTROL Pro]或更高版本</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
      <td>
        <p>[!UICONTROL 計畫]，[!UICONTROL 工作]</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td>
      <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求：[!UICONTROL [!DNL Workfront Fusion] for Work Automation and Integration] </p>
   </td>
    </tr>
    <tr>
      <td role="rowheader">產品</td>
      <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td>
    </tr>
    </tr>
  </tbody>
</table>


若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## 先決條件

使用[!DNL Adobe Target]聯結器之前，您必須確定符合下列先決條件：

* 您必須擁有使用中的[!DNL Adobe Target]帳戶。

## Adobe Target API資訊

Adobe Target聯結器會使用以下專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.7.33</td> 
  </tr>
 </tbody> 
 </table>

## 建立與[!DNL Adobe Target]的連線

>[!IMPORTANT]
>
>2024年6月3日之後建立的連線需要Adobe Target伺服器對伺服器連線。
>
>* 現有的服務帳戶連線將持續運作到2025年1月。 您必須在2024年1月前，將服務帳戶連線取代為Adobe Target伺服器對伺服器連線。
>* 您必須是組織的開發人員才能建立Adobe Target伺服器對伺服器連線。 開發人員角色是在Adobe Admin Console中設定。

若要為您的[!DNL Adobe Target]模組建立連線：

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
        <td role="rowheader">[!UICONTROL 連線型別]</td>
        <td>選擇您要建立服務帳戶連線還是Adobe Target伺服器對伺服器連線。<p><b>重要</b>： 2024年6月3日之後建立的連線需要Adobe Target伺服器對伺服器連線。 現有的服務帳戶連線將持續運作到2025年1月。 您必須在2024年1月前，將服務帳戶連線取代為Adobe Target伺服器對伺服器連線。
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 環境]</td>
        <td>選取您要連線到生產或非生產環境。
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 型別]</td>
        <td>選取您要連線到服務帳戶還是個人帳戶。
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端ID]</td>
        <td>輸入您的[!DNL Adobe]使用者端識別碼。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 使用者端密碼]</td>
        <td>輸入您的[!DNL Adobe]使用者端密碼。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 技術帳戶ID]</td>
        <td>輸入您的[!DNL Adobe]技術帳戶ID。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 組織ID]</td>
        <td>輸入您的[!DNL Adobe]組織識別碼。 這可以在[!DNL Adobe Developer Console]的[!UICONTROL 認證詳細資料]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 租使用者]</td>
        <td>
          <p> 若要尋找您的租使用者，請登入[!DNL Adobe Experience Cloud]，開啟[!DNL Target]，然後按一下[!DNL Target]卡片。 使用URL子網域中所述的租使用者ID值。</p>
          <p>例如，如果您在登入[!DNL Adobe Target]時的URL是<code>&lt;https://mycompany.experiencecloud.adobe.com/...></code>，則您的租使用者ID是"mycompany"。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 中繼範圍]</td>
        <td>輸入<code>ent_marketing_sdk</code>       </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 私密金鑰]</td>
        <td>
          <p>輸入在[!DNL Adobe Developer Console]中建立認證時產生的私密金鑰。 </p>
          <p>若要擷取您的私密金鑰或憑證：</p>
          <ol>
            <li value="1">
              <p>按一下<b>[!UICONTROL Extract]</b>。</p>
            </li>
            <li value="2">
              <p>選取要解壓縮的檔案型別。</p>
            </li>
            <li value="3">
              <p>選取包含私密金鑰或憑證的檔案。</p>
            </li>
            <li value="4">
              <p>輸入檔案的密碼。</p>
            </li>
            <li value="5">
              <p>按一下<b>[!UICONTROL 儲存]</b>以擷取檔案並返回連線設定。</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody>
    </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

## [!DNL Adobe Target]模組及其欄位

當您設定[!DNL Adobe Target]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!DNL Adobe Target]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [動作](#actions)

* [搜尋](#searches)


### 動作

* [[!UICONTROL 建立記錄]](#create-a-record)

* [[!UICONTROL 進行自訂API呼叫]](#make-a-custom-api-call)

* [[!UICONTROL 刪除記錄]](#delete-a-record)

* [[!UICONTROL 讀取記錄]](#read-a-record)

* [[!UICONTROL 更新記錄]](#update-a-record)


#### [!UICONTROL 建立記錄]

此動作模組會建立AB或XT活動、選件或對象。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>如需建立[!DNL Adobe Target]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >建立與[!DNL Adobe Target]</a>的連線。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 記錄型別]</td>
    <td>
      <p>選取您要建立的記錄型別。</p>
      <ul>
        <li>
        <b>屬性</b><p>如需欄位的詳細資訊，請參閱Adobe Target API檔案中的<a href="https://developer.adobe.com/target/administer/admin-api/#tag/Properties/operation/createProperty">建立屬性</a>。</p>
        </li>
        <li>
        <b>優惠建議</b><p>如需欄位的詳細資訊，請參閱Adobe Target API檔案中的<a href="https://developer.adobe.com/target/administer/admin-api/#tag/Offers/operation/createOffer">建立新的RECS選件</a>。</p>
        </li>
        <li>
          <b>[!UICONTROL 選件JSON]</b>
          <p>繼續<a href="#offer-fields" class="MCXref xref" >選件欄位</a>。</p>
        </li>
        <li>
          <b>[!UICONTROL 選件內容]</b>
          <p>繼續<a href="#offer-fields" class="MCXref xref" >選件欄位</a>。</p>
        </li>
        <li>
        <b>環境</b><p>如需欄位的詳細資訊，請參閱Adobe Target API檔案中的<a href="https://developer.adobe.com/target/administer/admin-api/#tag/Environments/operation/createEnvironment">建立環境</a>。</p>
        </li>
        <li>
          <b>[!UICONTROL 對象]</b>
          <p>如需欄位的詳細資訊，請參閱Adobe Target API檔案中的<a href="https://developer.adobe.com/target/administer/admin-api/#tag/Audiences/operation/createAudience_1_1">建立對象</a>。</p>
        </li>
        <li>
          <b>[!UICONTROL AB活動]</b>
          <p>如需欄位的詳細資訊，請參閱Adobe Target API檔案中的<a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_4_1">建立AB活動</a>。</p>
        </li>
        <li>
          <b>[!UICONTROL XT活動]</b>
          <p>繼續<a href="#xt-activity-fields" class="MCXref xref" >XT活動欄位</a>。</p>
        </li>
        <li>
          <b>[!UICONTROL AP活動]</b>
          <p>如需欄位的詳細資訊，請參閱Adobe Target API檔案中的<a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_2">建立AP活動</a>。</p>
        </li>
        <li>
          <b>[!UICONTROL 回應Token]</b>
          <p>如需欄位的詳細資訊，請參閱Adobe Target API檔案中的<a href="https://developer.adobe.com/target/administer/admin-api/#tag/Response-tokens/operation/createResponseToken">建立回應Token</a>。</p>
        </li>
      </ul>
    </td>
  </tr>
</tbody>
</table>

<!--

##### AB Activity fields

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Enter or map a name for this activity. The name can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Options]</td>
      <td>
        <p>For each option that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Option local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the option across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the option. The name must be no more than 250 characters.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Offer ID]</b>
            </p>
          </li>
          <li>
            <p>Select or map the Offer associated with the option.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Mboxes]</td>
      <td>
        <p>For each Mbox that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>For each audience that you want to add to the Mbox, click <b>[!UICONTROL Add item]</b> and select the Audience ID.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the Location. The name must be no more than 250 characters.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Selectors]</td>
      <td>
        <p>For each selector that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and fill in the following fields:</p>
        <ul>
          <li>
            <p>[!UICONTROL Audience IDs]</p>
            <p>For each audience that you want to add to the Mbox, click <b>[!UICONTROL Add item]</b> and select the Audience ID.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Location local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Selector]</b>
            </p>
            <p>Enter or map a string to be used to track the location across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map a name for the Location. The name must be no more than 250 characters.</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Experiences]</td>
      <td>
        <p>A list of locations on the page where the content offer is served. A location contains the following:
</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Experience local ID]</b>
            </p>
            <p>Enter or map the ID of the experience</p>
          </li>
          <li>
            <p><b>[!UICONTROL Name]</b>
            </p>
            <p>Enter or map the name of the experience
</p>
          </li>
          <li>
            <p><b>[!DNL Audience IDs]</b>
            </p>
            <p>For each audience that you want to see the experience, click <b>[!UICONTROL Add item]</b> and enter the Audience ID.
</p>
          </li>
          <li>
            <p><b>[!UICONTROL Visitor Percentage]</b>
            </p>
            <p>Enter or map the percentage of visitors that is allocated to the experience</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Metrics]</td>
      <td><p>For details on metrics, see <a href="https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/createActivity_4_1">Create AB activity</a> in the Adobe Target API documentation.</p> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Third Party ID]</td>
      <td>Enter or map an ID to identify this activity. You can choose this ID. This ID must not be the same as another activity, and can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Starts at]</td>
      <td>Enter or map the date and time to start the activity in the format <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Ends at]</td>
      <td>Enter or map the date and time to end the activity in the format <code>YYYY-MM-DD hh:mm:ss.z</code>.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL State]</td>
      <td>
        <p>Enter or map the state of the activity.</p>
        <ul>
          <li>
            <p>[!UICONTROL Approved]</p>
          </li>
          <li>
            <p>[!UICONTROL Deactivated]</p>
          </li>
          <li>
            <p>[!UICONTROL Paused]</p>
          </li>
          <li>
            <p>[!UICONTROL Saved] </p>
          </li>
          <li>
            <p>[!UICONTROL Deleted]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Priority]</td>
      <td>Enter a number that defines the priority of the activity. Higher numbers have higher priority. This value must be between 0 and 999. The default value is 5.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Auto-allocate traffic]</td>
      <td>
        <p>Enable this option to auto-allocate traffic. Auto-allocating sends more traffic to the more successful experience.</p>
        <p>Select or map the evaluation criteria by which to judge which experience is more successful.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>Enter or map the workspace that the activity is associated with</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Property IDs] </td>
      <td>For each property that you want to add to the activity, click <b>[!UICONTROL Add item]</b> and select or map the property's ID.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Reporting audiences]</td>
      <td>
        <p>For each reporting audience that you want to add to the activity, click [!UICONTROL Add item] and enter the following information:</p>
        <ul>
          <li>
            <p><b>[!UICONTROL Reporting Audience local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the Reporting Audience across API requests.</p>
          </li>
          <li>
            <p><b>[!UICONTROL Audience ID]</b>
            </p>
            <p>Enter or map the Segment to be used in reporting</p>
          </li>
          <li>
            <p><b>[!UICONTROL Metric local ID]</b>
            </p>
            <p>Enter or map a string to be used to track the metric across API requests.</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

-->

##### XT活動欄位

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 名稱]</td>
      <td>輸入或對應此活動的名稱。 名稱不能超過250個字元。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Options]</td>
      <td>
        <p>針對您想要新增至活動的每個選項，按一下<b>[!UICONTROL 新增專案]</b>並填入下列欄位：</p>
        <ul>
          <li>
            <p><b>[!UICONTROL 選項本機識別碼]</b>
            </p>
            <p>輸入或對應要用於跨API請求追蹤選項的字串。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 名稱]</b>
            </p>
            <p>輸入或對映選項的名稱。 名稱不得超過250個字元。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 選件ID]</b>
            </p>
          </li>
          <li>
            <p>選取或對應與選項相關聯的優惠。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 位置]</td>
      <td>
        <p>針對您要新增至活動的每個Mbox，按一下<b>[!UICONTROL 新增專案]</b>並填寫下列欄位：</p>
        <ul>
          <li>
            <p>[!UICONTROL 對象ID]</p>
            <p>針對您想要新增至Mbox的每個對象，按一下<b>[!UICONTROL 新增專案]</b>並選取對象ID。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 位置本機識別碼]</b>
            </p>
            <p>輸入或對應要用來跨API請求追蹤位置的字串。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 名稱]</b>
            </p>
            <p>輸入或對應「位置」的名稱。 名稱不得超過250個字元。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 體驗]</td>
      <td>
        <p>頁面上提供內容選件的位置清單。 位置包含以下內容：
</p>
        <ul>
          <li>
            <p><b>[!UICONTROL 體驗本機識別碼]</b>
            </p>
            <p>輸入或對映體驗的ID</p>
          </li>
          <li>
            <p><b>[!UICONTROL 名稱]</b>
            </p>
            <p>輸入或對映體驗的名稱

</p>
          </li>
          <li>
            <p><b>[!DNL Audience IDs]</b>
            </p>
            <p>針對您想要檢視體驗的每個對象，按一下<b>[!UICONTROL 新增專案]</b>並輸入對象ID。

</p>
          </li>
          <li>
            <p><b>[!UICONTROL 訪客百分比]</b>
            </p>
            <p>輸入或對映分配至體驗的訪客百分比</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Metrics]</td>
      <td> </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 第三方ID]</td>
      <td>輸入或對應ID以識別此活動。 您可以選擇此ID。 此ID不得與其他活動相同，且不得超過250個字元。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 開始於]</td>
      <td>輸入或對應開始活動的日期和時間，格式為<code>YYYY-MM-DD hh:mm:ss.z</code>。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 結尾為]</td>
      <td>輸入或對應結束活動的日期和時間，格式為<code>YYYY-MM-DD hh:mm:ss.z</code>。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 狀態]</td>
      <td>
        <p>輸入或對映活動的狀態。</p>
        <ul>
          <li>
            <p>[!UICONTROL 已核准]</p>
          </li>
          <li>
            <p>[!UICONTROL 已停用]</p>
          </li>
          <li>
            <p>[!UICONTROL 已暫停]</p>
          </li>
          <li>
            <p>[!UICONTROL 已儲存] </p>
          </li>
          <li>
            <p>[!UICONTROL 已刪除]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 優先順序]</td>
      <td>輸入定義活動優先順序的數字。 數字越大，優先順序越高。 此值必須介於0到999之間。 預設值為5。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 自動分配流量]</td>
      <td>
        <p>啟用此選項以自動分配流量。 自動分配會將更多流量傳送到更成功的體驗。</p>
        <p>選取或對應評估標準，以判斷哪個體驗更成功。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>輸入或對應與活動相關聯的工作區</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 屬性ID] </td>
      <td>針對您想要新增至活動的每個屬性，按一下<b>[!UICONTROL 新增專案]</b>，然後選取或對應屬性的識別碼。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表受眾]</td>
      <td>
        <p>針對您想要新增至活動的每個報表對象，按一下[!UICONTROL 新增專案]並輸入下列資訊：</p>
        <ul>
          <li>
            <p><b>[!UICONTROL 報表對象本機識別碼]</b>
            </p>
            <p>輸入或對應字串，用於跨API請求追蹤報表對象。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 對象ID]</b>
            </p>
            <p>輸入或對應要在報告中使用的區段</p>
          </li>
          <li>
            <p><b>[!UICONTROL 量度本機識別碼]</b>
            </p>
            <p>輸入或對應字串，用於跨API請求追蹤量度。</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

##### 選件欄位

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 名稱]</td>
      <td>輸入或對應此活動的名稱。 名稱不能超過250個字元。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 內容]</td>
      <td>
        <p>輸入或對應要向使用者顯示的優惠方案內容。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>輸入或對應與選件相關聯之工作區的ID。 如果保留為空白，選件會與帳戶的預設工作區相關聯。 此功能僅適用於[!DNL Target]個Premium帳戶。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>輸入或對應此優惠方案的修改日期和時間。</p>
      </td>
    </tr>
  </tbody>
</table>

<!--

##### Audience fields

>[!NOTE]
>
>Audiences created through Workfront Fusion can only be edit in Fusion or through the API. They cannot be edited from within Target.

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Name]</td>
      <td>Enter or map a name for this audience. The name can be no more than 250 characters.</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Description]</td>
      <td>
        <p>Enter or map a description of this audience.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Origin]</td>
      <td>
        <p>Select whether this audience's origin is from Target or from the cloud.</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Target Rule]</td>
      <td>
        <p>Enable the toggle to make rules AND, that is, all rules must be applied.</p>
        <p>For each rule that you want to apply to the audience, click <b>[!UICONTROL Add item]</b> and enter the JSON of the rule you want to apply. </p>
        <div class="example"><span class="autonumber"><span><b>Example: </b></span></span>
          <p>Example 1:</p>
          <p ><code>&lbrace;</code></p>
                    <p ><code>                "page": "url",</code>
                    </p>
                    <p><code>                "equals":&lbrack;</code>
                    </p>
                    <p ><code>                    "http://www.myhomepage.com/"</code>
                    </p>
                    <p><code>                &rbrack;</code>
                    </p>
                    <p ><code>            &rbrace;,</code>
                    </p>
                    <p>Example 2</p>
                    <p ><code>            &lbrace;</code>
                    </p>
                    <p><code>                "geo": "region",</code>
                    </p>
                    <p><code>                "matches": &lbrack;</code>
                    </p>
                    <p ><code>                    "california"</code>
                    </p>
                    <p ><code>                &rbrack;</code>
                    </p>
                    <p ><code>            &rbrace;</code>
                    </p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Workspace]</td>
      <td>
        <p>Enter or map the ID of the workspace associated with the audience. If left blank, the offer is associated with the default workspace of the account. This functionality applies only to [!DNL Target Premium] accounts.</p>
      </td>
    </tr>
  </tbody>
</table>

-->

#### [!UICONTROL 進行自訂API呼叫]

此模組會對[!DNL Adobe Target] API發出自訂API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Target]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >建立與[!DNL Adobe Target]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL [!DNL Target]基底URL]</td>
      <td>輸入或對應您的[!DNL Target]基底URL。</td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 路徑]</p>
      </td>
      <td>
        <p>輸入相對於{baseURL}/</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
      </td>
   <td> <p>選取設定API呼叫所需的HTTP要求方法。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/http-request-methods.md" class="MCXref xref" data-mc-variable-override="">HTTP要求方法</a>。</p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>[!DNL Workfront Fusion] 自動新增授權標頭和x-api-key標頭。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 查詢字串]  </td>
      <td>
        <p>輸入請求查詢字串。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Body]</td>
   <td> <p>以標準JSON物件的形式新增API呼叫的內文內容。</p> <p>注意：  <p>在JSON中使用條件陳述式（例如<code>if</code>）時，請將引號放在條件陳述式之外。</p> 
     <div class="example" data-mc-autonum="<b>Example: </b>"> 
      <p> <img src="/help/workfront-fusion/references/apps-and-modules/assets/quotes-in-json-350x120.png" style="width: 350;height: 120;"> </p> 
     </div> </p> </td>     </tr>
  </tbody>
</table>

#### [!UICONTROL 刪除記錄]

此動作模組會刪除單一AB活動、XT活動、選件或對象。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>如需建立[!DNL Adobe Target]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >建立與[!DNL Adobe Target]</a>的連線。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 記錄型別]</td>
    <td>選取您要刪除的記錄型別。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 記錄ID]</td>
    <td>輸入或對應您要刪除之記錄的ID。</td>
  </tr>
</tbody>
</table>

#### [!UICONTROL 讀取記錄]

此動作模組會擷取單一活動、選件、對象、屬性或報表的資料。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>如需建立[!DNL Adobe Target]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >建立與[!DNL Adobe Target]</a>的連線。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 記錄型別]</td>
    <td>選取您要讀取的記錄型別。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 記錄ID]</td>
    <td>輸入或對應您要讀取之記錄的ID。</td>
  </tr>
</tbody>
</table>

#### [!UICONTROL 更新記錄]

此動作模組會更新Target中的記錄。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Target]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >建立與[!DNL Adobe Target]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄型別]</td>
      <td>
        <p>選取您要更新的記錄型別。</p>
       </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 欄位名稱]</td>
      <td>選取您要更新的欄位。 欄位顯示如下。
          <p>如需欄位的詳細資訊，請參閱<a href="https://developer.adobe.com/target/administer/admin-api/">Adobe Target API檔案</a>。</p>
      </td>
    </tr>
  </tbody>
</table>

### 搜尋

* [[!UICONTROL 取得記錄]](#get-records)

* [[!UICONTROL 搜尋]](#search)


#### [!UICONTROL 取得記錄]

此搜尋模組會擷取所選型別的記錄清單。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
      <td>如需建立[!DNL Adobe Target]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >建立與[!DNL Adobe Target]</a>的連線。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 記錄型別]</td>
      <td>選取您要更新的記錄型別。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 排序依據]</td>
      <td>針對您要排序的每個欄位，按一下<b>[!UICONTROL 新增專案]</b>，然後選取欄位以及傳回的結果應該遞增還是遞減。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 開始於]</td>
      <td>
        <p>輸入您要擷取記錄的最早日期。 </p>
        <p>如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 結尾為]</td>
      <td>
        <p>輸入您要擷取記錄的最晚日期。 </p>
        <p>如需支援的日期和時間格式清單，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/type-coercion.md" class="MCXref xref">型別強制執行</a>。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 搜尋]

此搜尋模組會根據您指定的條件搜尋活動、選件或對象。

<table style="table-layout:auto"> 
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
    <td>如需建立[!DNL Adobe Target]連線的說明，請參閱本文中的<a href="#create-a-connection-to-adobe-target" class="MCXref xref" >建立與[!DNL Adobe Target]</a>的連線。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 記錄型別]</td>
    <td>選取您要更新的記錄型別。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 排序依據]</td>
    <td>針對您要排序的每個欄位，按一下<b>[!UICONTROL 新增專案]</b>，然後選取欄位以及傳回的結果應該遞增還是遞減。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 搜尋條件]</td>
    <td>針對您要設定的每個規則，選取欄位、運運算元和值。 按一下<b>[!UICONTROL Add AND rule]</b>以建立其他規則。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 位移]</td>
    <td>
      <p>輸入您希望模組傳回的第一個回應編號。 第一個傳回回回的回應有<code>0</code>的位移。 將此欄位與[!UICONTROL Maximum number of returned results]欄位搭配使用，可將回應分頁。</p>
      <p>例如，若要檢視回應的第三個頁面，當每個頁面有10個回應時，請將[!UICONTROL Offset]設為20，並將[!UICONTROL Maximum number of returned]設為10。</p>
    </td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 限制]</td>
    <td>
      <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。 將此欄位與[!UICONTROL Offset]欄位搭配使用，可將回應分頁。</p>
      <p>例如，若要檢視回應的第三個頁面，當每個頁面有10個回應時，請將[!UICONTROL Offset]設為20，並將[!UICONTROL Maximum number of returned]設為10。</p>
    </td>
  </tr>
</tbody>
</table>

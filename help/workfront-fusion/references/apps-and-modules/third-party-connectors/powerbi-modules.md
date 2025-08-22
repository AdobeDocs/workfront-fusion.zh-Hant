---
title: Power BI模組
description: 除了Adobe Workfront授權，Adobe Workfront Fusion還需要Adobe Workfront Fusion授權。
author: Becky
feature: Workfront Fusion
exl-id: 73eb70e1-3f3d-419d-9cde-3ec3cda224f8
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '2600'
ht-degree: 0%

---

# [!DNL Power BI]模組

[!DNL Power BI]是應用程式，可讓您以視覺效果呈現資料給利害關係人。 它可接收來自各種來源的資料。

>[!NOTE]
>
>Workfront Fusion不是資料來源。 雖然Workfront Fusion可以建立和使用資料來源，但不會儲存您的資料。


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

## Microsoft Power BI API資訊

Microsoft Power BI聯結器使用下列專案：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">基礎 URL</td> 
   <td> https://api.powerbi.com/v1.0</td> 
  </tr> 
  <tr> 
   <td role="rowheader">API版本</td> 
   <td> v1.0 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API標籤</td> 
   <td>v1.0.2</td> 
  </tr>
 </tbody> 
 </table>

## [!DNL Power BI]模組及其欄位

當您設定[!DNL Power BI]時，Workfront Fusion會顯示下列欄位。 除了這些以外，其他欄位可能會顯示，端視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[在Adobe Workfront Fusion中將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

* [儀表板](#dashboards)
* [報告](#reports)
* [資料集](#dataset)
* [應用程式](#apps)
* [其他](#other)

### 儀表板

* [建立控制面板](#create-a-dashboard)
* [取得儀表板](#get-a-dashboard)
* [取得儀表板動態磚](#get-a-dashboard-tile)
* [清單控制面板圖磚](#list-dashboard-tiles)
* [清單儀表板](#list-dashboards)

#### [!UICONTROL 建立儀表板]

此動作模組會建立新的控制面板。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 名稱]</td>
      <td>輸入或對應控制面板的名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應將擁有新儀表板的群組ID。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 取得儀表板]

此動作模組會擷取指定控制面板的中繼資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入儀表板ID]</td>
      <td>
        <p>選取或對應選項，以選擇要擷取中繼資料的控制面板。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 儀表板ID]</td>
      <td>
        <p>輸入或對應您要擷取中繼資料之控制面板的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要擷取中繼資料之控制面板的群組ID。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 取得儀表板拼貼]

此動作模組會擷取指定控制面板圖磚的中繼資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入儀表板ID]</td>
      <td>
        <p>選取或對應選項，以選擇要擷取的控制面板詳細資訊。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 儀表板ID]</td>
      <td>
        <p>輸入或對應您要擷取其詳細資訊之控制面板的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 拼貼ID]</td>
      <td>輸入或對應您要擷取詳細資料的[!DNL Power BI]圖磚識別碼。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要擷取之圖磚之群組的ID。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出儀表板圖磚]

此搜尋模組會擷取控制面板圖磚清單。

<table>
<col/>
<col/>
<tbody>
  <tr>
    <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 輸入儀表板ID]</td>
    <td>
      <p>選取或對應選項，以選擇要列出圖磚的控制面板。</p>
    </td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 儀表板ID]</td>
    <td>
      <p>輸入或對應包含您要列出之圖磚之控制面板的ID。</p>
    </td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 群組ID]  </td>
    <td>選取或對應擁有控制面板的群組ID，控制面板包含您要列出的圖磚。</td>
  </tr>
  <tr>
    <td role="rowheader">[!UICONTROL 限制]  </td>
    <td>
      <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
    </td>
  </tr>
</tbody>
</table>

#### [!UICONTROL 清單儀表板]

此搜尋模組會擷取控制面板清單。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>
        <p>選取或對應擁有您要列出之控制面板的群組ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 限制]  </td>
      <td>
        <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
  </tbody>
</table>

### 報告

* [複製報告](#copy-a-report)
* [刪除報告](#delete-a-report)
* [取得報表](#get-a-report)
* [清單報告](#list-reports)

#### [!UICONTROL 複製報告]

此動作模組會複製現有報表。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入報表ID]</td>
      <td>
        <p>選取或對應選項，以選擇要複製的報表。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表ID]</td>
      <td>
        <p>輸入或對應您要複製之報表的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要複製之報表之群組的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 新複製的報表名稱]</td>
      <td>輸入或對應新報表的名稱。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 刪除報告]

此動作模組會刪除報表。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入報表ID]</td>
      <td>
        <p>選取或對應選項，以選擇要刪除的報表。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表ID]</td>
      <td>
        <p>輸入或對應您要刪除之報表的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要刪除之報表之群組的ID。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 取得報表]

此動作模組會擷取指定報表的中繼資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入報表ID]</td>
      <td>
        <p>選取或對應選項，以選擇要擷取中繼資料的報表。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表ID]</td>
      <td>
        <p>輸入或對應您要擷取中繼資料之報表的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要擷取中繼資料之報表的群組ID。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 清單報告]

此搜尋模組會擷取報表清單。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>
        <p>選取或對應擁有您要列出之報告的群組ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 限制]  </td>
      <td>
        <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
  </tbody>
</table>


### 資料集

* [在資料集表格中新增/刪除列](#add-or-delete-rows-in-a-dataset-table)
* [建立資料集](#create-a-dataset)
* [刪除資料集](#delete-a-dataset)
* [取得資料集](#get-a-dataset)
* [清單資料集](#list-datasets)
* [重新整理資料集](#refresh-a-dataset)

#### [!UICONTROL 新增或刪除資料集資料表中的資料列]

此動作模組會新增或刪除指定推送資料集表格的列。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入表格]</td>
      <td>選取或對應選項以選取包含您要調整之表格的資料集。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資料集ID]</td>
      <td>輸入或對應包含您要新增或刪除之列的資料集ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資料表名稱]  </td>
      <td>
        <p>輸入或對應包含您要新增或刪除之資料列的表格名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>輸入或對應擁有資料集之群組的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 選取動作]</td>
      <td>
        <p>選取或對應您要執行的動作。</p>
        <ul>
          <li>
            <p>[!UICONTROL 新增列]</p>
          </li>
          <li>
            <p>[!UICONTROL Delete All Rows]</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 列]</td>
      <td>
        <p>新增列欄位。</p>
        <ul>
          <li>
            <p><b>[!UICONTROL 索引鍵]</b>
            </p>
            <p>輸入或對應金鑰名稱。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 欄位型別]</b>
            </p>
            <p>選取或對應欄位型別：</p>
            <ul>
              <li>
                <p>布林值</p>
              </li>
              <li>
                <p>日期</p>
              </li>
              <li>
                <p>文字</p>
              </li>
              <li>
                <p>數字</p>
              </li>
            </ul>
          </li>
          <li>
            <p>[!UICONTROL 值]</p>
            <p>輸入或對應索引鍵值。</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 建立資料集]

此動作模組會建立新資料集。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 名稱]</td>
      <td>輸入或對應資料集的名稱。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應將擁有新資料集的群組ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 預設模式]</td>
      <td>
        <p>選取或對應資料集的預設模式：</p>
        <ul>
          <li>
            <p><b>[!UICONTROL As Azure]</b>：與有即時連線的資料集 [!DNL Azure Analysis Service]</p>
          </li>
          <li>
            <p><b>[!UICONTROL As on Prem]</b>：與[!DNL On-premise Analysis]服務有即時連線的資料集</p>
          </li>
          <li>
            <p><b>[!DNL Push]</b>：允許以程式設計方式存取資料，以推送資料至的資料集 [!DNL Power BI]</p>
          </li>
          <li>
            <p><b>[!DNL Push Streaming]</b>：支援資料串流的資料集，可程式化地存取以推送資料至 [!DNL Power BI]</p>
          </li>
          <li>
            <p><b>[!DNL Streaming]</b>：支援資料串流的資料集</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 表格]</td>
      <td>新增表格至資料集。 如需欄位，請參閱<a href="#Table" class="MCXref_0">表格欄位</a></td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Data sources]</td>
      <td>新增資料來源。 如需欄位，請參閱<a href="#Data" class="MCXref_0">資料來源欄位</a>。</td>
    </tr>
    <tr>
      <td role="rowheader">[!DNL Default Retention Policy]  </td>
      <td>
        <p>選取或對應資料集的刻意原則：</p>
        <ul>
          <li>
            <p>[!UICONTROL 無]</p>
          </li>
          <li>
            <p>[!UICONTROL 基本FIFO]</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

##### 表格欄位

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 名稱]</td>
      <td>
        <p>  輸入或對映表格的名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 欄]</td>
      <td>
        <p>新增欄：</p>
        <ul>
          <li>
            <p><b>[!UICONTROL 名稱]</b>
            </p>
            <p>輸入（對應）欄名稱。</p>
          </li>
          <li>
            <p><b>[!UICONTROL 資料型別]</b>
            </p>
            <p>選取或對應資料型別：</p>
            <ul>
              <li>
                <p>[!UICONTROL 字串]</p>
              </li>
              <li>
                <p>[!UICONTROL 整數]</p>
              </li>
              <li>
                <p>[!UICONTROL Boolean]</p>
              </li>
              <li>
                <p>[!UICONTROL 日期時間]</p>
              </li>
            </ul>
          </li>
          <li>
            <p><b>[!UICONTROL 格式字串]</b>
            </p>
            <p>輸入（對應）格式字串。</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 列]</td>
      <td>輸入或對應列詳細資料。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Measures]</td>
      <td>新增表格的測量。</td>
    </tr>
  </tbody>
</table>

##### 資料來源欄位

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL 資料庫]  </td>
      <td>
        <p>輸入或對應您要使用的資料庫。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Server]  </td>
      <td>
        <p>輸入或對應您要使用的伺服器名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL URL]  </td>
      <td>
        <p>輸入或對應您要使用的URL。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資料來源ID]</td>
      <td>
        <p>  輸入或對應資料來源的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資料來源型別]  </td>
      <td>
        <p>選取或對應資料來源型別。 範例： SQL。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 閘道ID]  </td>
      <td>輸入或對應您要使用的閘道識別碼。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 刪除資料集]

此動作模組會刪除資料集。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入報表ID]</td>
      <td>
        <p>選取或對應選項，以選擇要刪除的資料集。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表ID]</td>
      <td>
        <p>輸入或對應您要刪除之資料集的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要刪除之資料集的群組ID。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 取得資料集]

此動作模組會擷取指定資料集的中繼資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入報表ID]</td>
      <td>
        <p>選取或對應選項，以選擇要擷取中繼資料的報表。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表ID]</td>
      <td>
        <p>輸入或對應您要擷取中繼資料之資料集的ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要擷取中繼資料之資料集的群組ID。</td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出資料集]

此搜尋模組會擷取資料集清單。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>選取或對應擁有您要擷取中繼資料之報表的群組ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 限制]</td>
      <td>
        <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 重新整理資料集]

此動作模組會重新整理指定的資料集。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 輸入資料集]</td>
      <td>選取或對應選項，以選取您要重新整理的資料集。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資料集ID]</td>
      <td>輸入或對應您要重新整理之資料集的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 資料表名稱]  </td>
      <td>
        <p>輸入或對應包含您要新增或刪除之資料列的表格名稱。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 群組ID]  </td>
      <td>輸入或對應擁有資料集之群組的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 通知選項]  </td>
      <td>
        <p>選取或對應選項以通知：</p>
        <ul>
          <li>
            <p>[!UICONTROL Mail on Completion]</p>
          </li>
          <li>
            <p>[!UICONTROL 郵件失敗]</p>
          </li>
          <li>
            <p>[!UICONTROL 無通知]</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 應用程式

* [取得應用程式](#get-an-app)
* [取得應用程式的儀表板](#get-an-apps-dashboard)
* [取得應用程式的報表](#get-an-apps-report)
* [列出應用程式的儀表板](#list-apps-dashboards)
* [清單應用程式的報表](#list-apps-reports)
* [列出應用程式](#list-apps)
* [Watch應用程式](#watch-apps)

#### [!UICONTROL 取得應用程式]

此動作模組會擷取指定應用程式的中繼資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 應用程式ID]  </td>
      <td>
        <p>選取或對應您要擷取的應用程式ID。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 取得應用程式的儀表板]

此動作模組會擷取指定應用程式控制面板的中繼資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 應用程式ID]  </td>
      <td>
        <p>選取或對應包含您要擷取之控制面板的應用程式ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表ID]</td>
      <td>
        <p>  選取或對應您要擷取之控制面板的ID。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 取得應用程式的報表]

此動作模組會擷取指定應用程式報表的中繼資料。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 應用程式ID]  </td>
      <td>
        <p>選取或對應包含您要擷取之報表的應用程式ID。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 報表ID]</td>
      <td>
        <p>  選取或對應您要擷取之報表的ID。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出應用程式]

此搜尋模組會擷取已安裝的所有應用程式清單。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 限制]  </td>
      <td>
        <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出應用程式的儀表板]

此搜尋模組會從指定的應用程式擷取控制面板清單。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 應用程式ID]</td>
      <td>選取或對應您要列出控制面板之應用程式的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 限制]  </td>
      <td>
        <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 列出應用程式的報表]

此搜尋模組會從指定的應用程式擷取所有報表的清單。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 應用程式ID]</td>
      <td>選取或對應您要從中列出報表之應用程式的ID。</td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 限制]  </td>
      <td>
        <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
  </tbody>
</table>

#### [!UICONTROL 觀看應用程式]

此觸發模組會在應用程式更新時啟動案例。

<table>
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL 限制]  </td>
      <td>
        <p>輸入或對應您希望模組在每個案例執行週期中傳回的最大記錄數。</p>
      </td>
    </tr>
  </tbody>
</table>

### 其他

#### [!UICONTROL 進行API呼叫]

此動作模組會執行[!DNL Power BI] API的API呼叫。

<table style="table-layout:auto"> 
  <col/>
  <col/>
  <tbody>
    <tr>
      <td role="rowheader">[!UICONTROL Connection]</td>
   <td> <p>如需有關將您的[!DNL Power BI]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/create-scenarios/connect-to-apps/connect-to-fusion-general.md" class="MCXref xref" data-mc-variable-override="">建立與Adobe Workfront Fusion的連線 — 基本說明</a></p> </td> 
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 路徑]</p>
      </td>
      <td>
        <p>輸入相對於<code>https://api.powerbi.com</code>的路徑。 範例：<code>/v1.0/myorg/datasets</code>。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">
        <p>[!UICONTROL 方法]</p>
      </td>
      <td>
        <p>選取設定API呼叫所需的[!UICONTROL HTTP]要求方法。 如需詳細資訊，請參閱[!UICONTROL HTTP]要求方法。</p>
      </td>
    </tr>
    <tr>
      <td role="rowheader">[!UICONTROL Headers]</td>
      <td>
        <p>以標準JSON物件的形式新增請求的標頭。</p>
        <p>例如， <code>{"Content-type":"application/json"}</code></p>
        <p>Workfront Fusion會自動新增授權標題和x-api-key標題。</p>
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

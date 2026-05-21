---
title: Adobe Experience Manager Forms 模組
description: 使用Adobe Workfront Fusion的 [!DNL Adobe Experience Manager Forms] 聯結器，您可以根據 [!DNL Adobe Experience Manager Forms] 帳戶中的事件啟動案例、建立、上傳和更新資產，以及複製或行動資料夾和資產。
author: Becky
feature: Workfront Fusion, Digital Content and Documents
exl-id: e0d7a655-1353-4d24-83d4-7da73d859a63
TQID: https://experienceleague.adobe.com/LTNDa0pulA4RE5tG59Fui-5bPlKxqHoQHEsKOp485No
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 600
ht-degree: 50%

---

# [!DNL Adobe Experience Manager Forms] 模組

使用Adobe Workfront Fusion的[!DNL Adobe Experience Manager Forms]聯結器，您可以建立webhook，根據[!DNL Adobe Experience Manager Forms]帳戶中的事件啟動案例。

您可以在[!DNL Adobe Experience Manager Forms]內設定表單，以將表單提交內容傳送至此webhook。

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
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>連接器型 (舊版)：Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

* 您必須有[!DNL Adobe Experience Manager Forms]帳戶才能使用此模組。

## Adobe Experience Manager Assets API 資訊

Adobe Experience Manager Assets 連接器會使用以下項目：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">API 標記</td> 
   <td>v1.2.27</td> 
  </tr>
 </tbody> 
 </table>

## 建立與Adobe Experience Manager Forms的連線

若要為您的 [!DNL Adobe Experience Manager Forms] 模組建立連線：

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
        <td>
          <p>選取此連線是連線至生產或非生產環境。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 類型]</td>
        <td>
          <p>選取此帳戶是服務帳戶還是個人帳戶。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 執行個體URL，不含尾隨斜線]</td>
        <td>
          <p>輸入您用來存取帳戶的URL，不含最後一個斜線。</p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL IMS端點]</td>
        <td>
          <p><code>https://ims-na1.adobelogin.com</code></p>
        </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端 ID]</td>
        <td>輸入您的[!DNL Adobe]使用者端識別碼。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 用戶端密碼]</td>
        <td>輸入您的[!DNL Adobe]使用者端密碼。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 組織ID]</td>
        <td>輸入您的[!DNL Adobe]組織識別碼。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 技術帳戶ID]</td>
        <td>輸入您的[!DNL Adobe]技術帳戶ID。 此資訊可在 [!DNL Adobe Developer Console] 的[!UICONTROL 認證詳細資訊]區段中找到。
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL Meta範圍]</td>
        <td>輸入任何適當的中繼範圍       </td>
      </tr>
      <tr>
        <td role="rowheader">[!UICONTROL 私密金鑰]</td>
        <td>
          <p>輸入在[!DNL Adobe Developer Console]中建立認證時產生的私密金鑰。 </p>
          <p>若要擷取您的私密金鑰或憑證：</p>
          <ol>
            <li value="1">
              <p>按一下「<b>[!UICONTROL 擷取]</b>」。</p>
            </li>
            <li value="2">
              <p>選取要擷取的檔案類型。</p>
            </li>
            <li value="3">
              <p>選取包含私密金鑰或憑證的檔案。</p>
            </li>
            <li value="4">
              <p>輸入檔案的密碼。</p>
            </li>
            <li value="5">
              <p>按一下「<b>[!UICONTROL 儲存]</b>」，擷取檔案並返回連線設定。</p>
            </li>
          </ol>
        </td>
      </tr>
    </tbody>
    </table>

1. 按一下「**[!UICONTROL 繼續]**」，儲存連線並返回模組。

## Adobe Experience Manager Forms模組及其欄位

目前Adobe Experience Manager Forms聯結器中只有一個模組。

### 關注表單事件

此即時觸發器(webhook)可讓您在Adobe Experience Manager表單上發生提交動作時開始案例。

>[!IMPORTANT]
>
>此模組也需要Adobe Experience Manager中的設定。 設定此webhook後，您必須開啟Adobe Experience Manager並設定表單，以將提交內容傳送至webhook。
>
><!--For instructions on the required form configuration, see insert url here-->

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Webhook 名稱]</td> 
   <td> <p>輸入 Webhook 的名稱</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL 連線]</td> 
   <td> <p>如需將您的[!DNL Adobe Experience Manager]帳戶連線到Workfront Fusion的說明，請參閱<a href="/help/workfront-fusion/references/apps-and-modules/adobe-connectors/aem-forms-modules.md#create-a-connection-to-adobe-experience-manager-forms" class="MCXref xref">建立與[!DNL Adobe Experience Manager Forms]</a>的連線</p> </td> 
  </tr>

模組會建立webhook並提供webhook位址，您可以在[!DNL Adobe Experience Manager Forms]中輸入此位址至表單提交對話方塊。

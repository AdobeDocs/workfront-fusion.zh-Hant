---
title: 建立連線 — 基本指示
description: 許多 [!DNL Adobe Workfront Fusion] 聯結器在建立連線時不需要自訂組態。 本文會介紹預設的連線建立程式。
author: Becky
feature: Workfront Fusion
exl-id: e47ab4d9-6612-4d9a-a024-da508a8bbfb2
source-git-commit: 6aec65919e79a9e9d950a11de53bfbb1051ca20b
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 0%

---

# 建立連線 — 基本指示

許多[!DNL Adobe Workfront Fusion]聯結器在建立連線時不需要自訂設定。 本文會介紹預設的連線建立程式。

>[!NOTE]
>
>
>如果Adobe Workfront Fusion未針對您要在情境中使用的Web服務提供應用程式，您可以使用[!DNL Workfront Fusion] HTTP和Webhooks模組連線至Web服務，如下列文章所述：
>
>* [將Adobe Workfront Fusion連線至使用API權杖授權的Web服務](/help/workfront-fusion/create-scenarios/connect-to-apps/connect-wf-web-service-uses-api-token-auth.md)
>* [為沒有聯結器的Web服務設定webhook](/help/workfront-fusion/create-scenarios/add-modules/receive-a-webhook-from-a-web-service.md)

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront套件 
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
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront計畫：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront計畫：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 建立連線

若要建立與指定應用程式的連線，您必須位於該應用程式的模組中。 例如，若要建立與Workfront的連線，您必須在Workfront模組中。

若要在[!DNL Workfront Fusion]模組內建立連線：

1. 在指定應用程式的任何模組中，按一下[!UICONTROL 連線]方塊旁的&#x200B;**[!UICONTROL 新增]**&#x200B;以開啟&#x200B;**[!UICONTROL 建立連線]**&#x200B;面板。
1. （選擇性）變更預設的&#x200B;**[!UICONTROL 連線名稱]**。
1. 在「環境」欄位中，選取這是生產或非生產環境。
1. 在「型別」欄位中，選取這是服務或個人帳戶。
1. （條件式）如果應用程式需要進階連線設定（例如ID、金鑰或[!UICONTROL 密碼]），請輸入該資訊。

   您可能需要按一下「顯示進階設定」**&#x200B;**&#x200B;來顯示可輸入這類資訊的欄位。

1. 按一下&#x200B;**[!UICONTROL 繼續]**。
1. 在顯示的登入視窗中，輸入您的認證以登入應用程式（如果尚未這麼做）。
1. （條件式）如果顯示&#x200B;**[!UICONTROL 允許]**&#x200B;按鈕，請檢查聯結器能夠採取的動作，然後按一下按鈕以將應用程式連線到[!DNL Workfront Fusion]。

   >[!NOTE]
   >
   >* 「環境」和「型別」欄位僅供參考，不會變更連線的功能。 此資訊會顯示在Fusion的「連線」區域中，可讓您決定要在組織的指定使用案例中使用哪個連線。
   >* 部分Microsoft應用程式使用相同的連線，而此連線會繫結至個別使用者許可權。 因此，在建立連線時，許可權同意畫面會顯示先前授與此使用者連線的所有許可權，以及目前應用程式所需的任何新許可權。
   >
   >   例如，如果使用者擁有透過Excel聯結器授予的「讀取表格」許可權，然後在Outlook聯結器中建立連線以讀取電子郵件，則許可權同意畫面會顯示已授予的「讀取表格」許可權和新要求的「寫入電子郵件」許可權。

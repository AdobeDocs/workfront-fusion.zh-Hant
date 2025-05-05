---
content-type: reference
title: 設定及管理組織和團隊：文章索引
description: 本節包含有關在Adobe Workfront Fusion中設定和管理組織和團隊的文章。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: aa570f28-7387-47c5-9968-e3554921b0f5
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# 透過[!DNL Adobe Admin Console]刪除使用者

您只能從[!DNL Adobe Workfront Fusion]中移除使用者，保留存取任何其他[!DNL Adobe]產品設定檔，或者您可以從[!DNL Adobe Admin Console]中完全移除使用者。

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

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
   <td> <p>新增： [!UICONTROL Standard]</p><p>或</p><p>目前： [!UICONTROL Work]或更高</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版：任何 </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>[!UICONTROL Select] 或[!UICONTROL Prime] [!DNL Workfront]計畫：您的組織必須購買[!DNL Adobe Workfront Fusion]。</li><li>[!UICONTROL Ultimate] [!DNL Workfront] 計畫： [!DNL Workfront Fusion]已包括在內。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買[!DNL Adobe Workfront Fusion]。</p>
   </td> 
  </tr>
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定*</td> 
   <td> 
     <p>您必須是組織的[!DNL Adobe Admin Console]管理員。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 僅從[!DNL Adobe Workfront Fusion]移除使用者

您可以從Workfront Fusion移除使用者，同時將其他Adobe產品許可權維持不變。

如需指示，請參閱[管理Admin Console上的產品](https://helpx.adobe.com/tw/enterprise/using/manage-products.html)一文中的「從產品移除使用者和使用者群組」。

## 在[!DNL Adobe Admin Console]的所有產品中停用使用者

若要刪除使用者，您必須透過[!DNL Adobe Admin Console]停用該使用者。

當下列其中一項適用時，使用者將從[!DNL Adobe Admin Console]中停用：

* 使用者會從產品或產品設定檔中移出，且不會指派給任何其他產品或產品設定檔。
* 使用者會從連結至產品設定檔的群組移除，且不會包含在連結至產品設定檔的任何其他群組內。
* 使用者會從產品設定檔中移除，且不會指派給另一個產品設定檔。
* 在包含Workfront Fusion的組織中，使用者會被刪除或停用。

  如需指示，請參閱[個別管理使用者](https://helpx.adobe.com/tw/enterprise/using/manage-users-individually.html)中的「移除使用者」一節。

在[!DNL Workfront Fusion]中，停用會以下列其中一種方式影響使用者：

* 如果使用者只在一個組織中，則停用該使用者。
* 如果使用者位於多個組織，則會將該使用者從在[!DNL Adobe Admin Console]上修改該使用者的組織中移除。
* 刪除使用者時，請考量下列事項。

### 在Workfront Fusion中刪除使用者時的注意事項

刪除使用者時，請考量下列事項。

* 刪除使用者時，會移除使用者的連線、金鑰和Webhook。
* 屬於使用者的任何案例都會轉移給組織「擁有者」。 必須更新這些案例中的連線，因為屬於使用者的連線已無效。
* 如果刪除的使用者擁有任何應用程式或公用範本，則應用程式或公用範本會轉移至組織「擁有者」。 如果沒有組織「擁有者」，則應用程式或公用範本會轉讓給其他使用者。

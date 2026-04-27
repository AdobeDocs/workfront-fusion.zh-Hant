---
content-type: reference
title: 設定及管理組織和團隊：文章索引
description: 本節包含有關在Adobe Workfront Fusion中設定和管理組織和團隊的文章。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: aa570f28-7387-47c5-9968-e3554921b0f5
source-git-commit: 6762806f17a0fc55531b647a84901b8ca572a997
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 21%

---

# 透過[!DNL Adobe Admin Console]刪除使用者

您只能從Adobe Workfront Fusion移除使用者，保留存取任何其他[!DNL Adobe]產品設定檔，或者您可以從[!DNL Adobe Admin Console]完全移除使用者。

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
  <tr data-mc-conditions=""> 
   <td role="rowheader">存取層級設定</td> 
   <td> 
     <p>您必須是組織的Adobe Admin Console管理員。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 僅從Adobe Workfront Fusion移除使用者

您可以從Workfront Fusion移除使用者，同時將其他Adobe產品許可權維持不變。

如需指示，請參閱[在Admin Console上管理產品](https://helpx.adobe.com/tw/enterprise/using/manage-products.html)一文中的「從產品移除使用者和使用者群組」。

## 在[!DNL Adobe Admin Console]的所有產品中停用使用者

若要刪除使用者，您必須透過[!DNL Adobe Admin Console]停用該使用者。

當下列其中一項適用時，使用者將從[!DNL Adobe Admin Console]中停用：

* 使用者會從產品或產品設定檔中移出，且不會指派給任何其他產品或產品設定檔。
* 使用者會從連結至產品設定檔的群組移除，且不會包含在連結至產品設定檔的任何其他群組內。
* 使用者會從產品設定檔中移除，且不會指派給另一個產品設定檔。
* 在包含Workfront Fusion的組織中，使用者會被刪除或停用。

  如需指示，請參閱[個別管理使用者](https://helpx.adobe.com/tw/enterprise/using/manage-users-individually.html)中的「移除使用者」一節。

在Workfront Fusion中，停用會透過下列其中一個方式影響使用者：

* 如果使用者只在一個組織中，則停用該使用者。
* 如果使用者位於多個組織，則會將該使用者從在[!DNL Adobe Admin Console]上修改該使用者的組織中移除。

### 在Workfront Fusion中刪除使用者時的注意事項

刪除使用者時，請考量下列事項。

* 刪除使用者時，會移除使用者的連線、金鑰和Webhook。
* 屬於使用者的任何案例都會轉移給組織「擁有者」。 必須更新這些案例中的連線，因為屬於使用者的連線已無效。
* 如果刪除的使用者擁有任何應用程式或公用範本，則應用程式或公用範本會轉移至組織「擁有者」。 如果沒有組織「擁有者」，則應用程式或公用範本會轉讓給其他使用者。

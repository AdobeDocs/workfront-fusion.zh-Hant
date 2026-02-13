---
title: 使用自訂函式對應資料
description: 對應項目時，您可以使用函式來建立簡單或複雜的公式。
author: Becky
feature: Workfront Fusion
source-git-commit: 109ea8a6b3c37918110dc930a19ac85ef3e6d764
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 20%

---

# 使用自訂函式對應資料

您可以在Fusion的「函式」區域中建立自訂函式。 然後，以Adobe App Builder模組的形式，將這些函式新增到您的情境中。

由於自訂函式可透過Adobe App Builder運作，因此您的組織必須擁有Adobe App Builder授權才能使用它們。

自訂函式（如大多數案例元素）為團隊所擁有。

Workfront Fusion也包含內建函式，可讓您建立簡單或複雜的公式。 這些函式涵蓋各種使用案例，包括陣列、字串、數字及先前模組資料的函式。

如需內建函式的資訊與指示，請參閱[使用內建函式對應專案](/help/workfront-fusion/create-scenarios/map-data/map-using-functions.md)。

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
   <p><ul><li>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li><li>您必須擁有Adobe App Builder授權才能使用自訂函式。</ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 設定自訂函式

自訂函式是在Workfront Fusion的函式區域中設定。 設定函式後，您可以使用Adobe App Builder聯結器將其新增至案例。

### 初始化您的執行階段環境

您必須先初始化執行階段環境，才能建立自訂函式。 只有在您的團隊沒有任何自訂功能時，才需要完成這項工作。

>[!IMPORTANT]
>
>只有有權存取Adobe App Builder的使用者（開發人員或IMS組織內的系統管理員）才能執行初始化。
>
>初始化完成後，執行初始化的團隊中的所有使用者都可以建立和使用函式。

1. 按一下左側面板中的&#x200B;**函式** ![函式圖示](assets/functions-icon.png)標籤。

   如果您尚未設定執行階段，您會看到訊息「未設定執行階段環境」。
1. 按一下&#x200B;**初始化執行階段**。

   一段時間後，會出現函式清單，內含兩個範例函式。

### 建立自訂函式

設定執行階段環境後，您就可以開始建立自訂函式。

>[!IMPORTANT]
>
>* 您的自訂函式&#x200B;**必須**&#x200B;是JavaScript函式。
>* 您的自訂函式&#x200B;**必須**&#x200B;傳回物件。
>* 建立自訂函式後，您無法：
>
>   * 變更其名稱
>   * 檢視預設引數值

1. 按一下左側面板中的&#x200B;**函式** ![函式圖示](assets/functions-icon.png)標籤。
1. 按一下&#x200B;**新增函式**。
1. 輸入自訂函式的名稱。

   您稍後將無法變更此名稱。
1. 輸入函式的程式碼。
1. 針對您要新增的每個預設引數值，按一下&#x200B;**新增引數**&#x200B;並輸入引數名稱和預設值。

   將函式新增至案例時，您可以覆寫預設引數。
1. 按一下&#x200B;**儲存**

## 新增自訂函式至案例

若要將自訂函式新增至案例，請使用Adobe App Builder聯結器。

如需指示，請參閱[Adobe App Builder模組](/help/workfront-fusion/references/apps-and-modules/adobe-connectors/adobe-app-builder.md)。


---
title: 鏈結模組
description: 使用這些模組，您可以將案例連結在一起，進行另一個呼叫。
author: Becky
feature: Workfront Fusion
hide: true
hidefromtoc: true
exl-id: 21429f94-fe4c-4ccc-a8c0-d7573657fecc
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 1%

---

# 鏈結模組

使用「鏈」模組，可以將一個案例連線到另一個案例。

<!--This article will be about the specific module configuration-->

如需計畫連結案例的指示，請參閱[將多個案例連結在一起](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)。


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
   <p>無Workfront Fusion授權需求</p>
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

## 鏈結模組及其欄位

### 觸發程序

#### 從父項接收資料

此模組是子情境中的觸發模組，由父情境中的呼叫子情境模組觸發。 它會接收來自父案例的資料，這些資料可以在子案例中處理。

若要設定從父模組接收資料：

1. 若要使用現有的資料結構，請在「資料結構」欄位中，選取將用於案例輸入資料的資料結構。

   或

   若要建立新的資料結構以作為情境的輸入資料，請按一下[資料結構]欄位旁的&#x200B;**[新增]**&#x200B;並建立資料結構。

   如需建立資料結構的說明，請參閱[資料結構](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md)。

1. 按一下&#x200B;**確定**&#x200B;以儲存模組。

### 動作

#### 呼叫子情境

此模組位於父案例中。 欄位會反映在子情境中，從父模組接收資料中所設定的資料結構。

>[!NOTE]
>
>* 您可以選取現有的子情境，或透過此模組建立新的子情境。
>* 建立子情境時，您可以建立資料結構。

若要設定「呼叫子案例」模組

1. 將「呼叫子項」情境模組新增至情境。
1. 若要使用現有的子案例，請在「鏈結」欄位中，選取您要呼叫的子案例。

   或

   若要建立新的子情境，請按一下「鏈」欄位旁的新增。 子案例會顯示在另一個視窗中，且有來自父模組的接收資料及來自父模組的傳回回應。

   在子情境的觸發程式模組中設定的欄位會顯示在「呼叫子情境模組」中。

1. 輸入要傳遞給子案例的資訊或對應到「呼叫子案例」模組中。
1. （條件式）如果您希望父案例繼續執行而不等待子案例的回應，請啟用&#x200B;**引發並忘記**&#x200B;選項。
1. 按一下&#x200B;**確定**&#x200B;以儲存模組。

>[!NOTE]
>
>如果您為此模組建立新的子情境，子情境會在個別的瀏覽器視窗中開啟，可讓您同時檢視及設定父項與子項情境。

#### 將回應傳回至父系

這是在子情境中，並將所選結構中的資料傳送至父情境。 您可以在父情境的後續模組中對應此資料。

如果您的子情境有多個路由，我們建議將此模組新增到始終在其他路由之後執行和執行的路由。

若要設定「新增回應者」模組：

1. 若要使用現有的資料結構，請在「資料結構」欄位中，選取將用於子案例傳回至父案例的資料的資料結構。

   或

   若要為資料建立新的資料結構，請按一下[資料結構]欄位旁的&#x200B;**新增**，然後建立資料結構。

   如需建立資料結構的說明，請參閱[資料結構](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md)。

1. 按一下&#x200B;**確定**&#x200B;以儲存模組。

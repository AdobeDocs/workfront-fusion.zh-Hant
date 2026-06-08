---
title: 鏈結模組
description: 使用這些模組，您可以將案例連結在一起，進行另一個呼叫。
author: Becky
feature: Workfront Fusion
exl-id: 21429f94-fe4c-4ccc-a8c0-d7573657fecc
TQID: https://experienceleague.adobe.com/AlHUrliXikCc3OVHiBTjLNQFndCf5qLzOLuBvnDTUfA
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 81d1dfcdb5c15f6a93e2793f9a0e41821b65c7e3
workflow-type: tm+mt
source-wordcount: 883
ht-degree: 10%

---

# 鏈結模組

>[!IMPORTANT]
>
>此功能位於Beta中，不建議用於關鍵任務生產工作流程。 由於Beta功能，行為可能會變更，且邊緣案例可能無法完全處理。
>
>對於穩定整合，考慮使用HTTP請求模組透過webhook觸發第二個案例，此模式使用完全支援的原語並給予每個案例獨立的執行控制。
>
>如果您選擇使用鏈結的情境，請檢閱[將多個情境鏈結在一起](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)以取得設計手冊。

使用「鏈」模組，可以將一個案例連線到另一個案例。

<!--This article will be about the specific module configuration-->

如需計畫連結案例的指示，請參閱[將多個案例連結在一起](/help/workfront-fusion/create-scenarios/plan-a-scenario/chain-scenarios.md)。


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

>[!IMPORTANT]
>
> 在生產情境中設定此模組之前，請先檢閱下列內容：
>
> * 停用[引發並忘記]時，**請勿在此案例上啟用認可觸發程式(CTL)**。 CTL將在暫停等待子回應時重試此案例，建立無限制的重試回圈。
> * **將此模組放在疊代器內時請小心。** 為大型疊代器中的每個料號分派子案例會建立顯著的平台負載。 考慮內嵌子情境的邏輯，或在迭代器外預先計算共用查詢。
> * **引發並忘記**&#x200B;表示父系無法檢視子系是否執行或成功。 只有在獨立監視子項失敗時才使用。
>
> 如需完整的設計手冊，請參閱[將多個案例鏈結在一起](https://experienceleague.adobe.com/en/docs/workfront-fusion/using/create-scenarios/plan-a-scenario/chain-scenarios)。

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

>[!IMPORTANT]
>
> 如果您的子案例有多個路由，您&#x200B;**必須**&#x200B;確保可從每個執行路徑連線到父模組的傳回回應。 如果傳回回應模組位於已略過或未執行的路由上，則父案例會無限期等待從未到達的回應。
>
> 將Return回應加入至路由器之後的父模組，其路由一律執行，而不論路由器結果為何，或加入錯誤處理，以確保即使發生錯誤也一律會傳回回應。

若要設定「新增回應者」模組：

1. 若要使用現有的資料結構，請在「資料結構」欄位中，選取將用於子案例傳回至父案例的資料的資料結構。

   或

   若要為資料建立新的資料結構，請按一下[資料結構]欄位旁的&#x200B;**新增**，然後建立資料結構。

   如需建立資料結構的說明，請參閱[資料結構](/help/workfront-fusion/references/mapping-panel/data-types/data-structures.md)。

1. 按一下&#x200B;**確定**&#x200B;以儲存模組。

---
title: 在情境中加入模組
description: 本文說明將模組新增至案例的基本程式。
author: Becky
feature: Workfront Fusion
exl-id: f3757468-3e11-4862-a83e-ed447805545b
TQID: 'https://experienceleague.adobe.com/R2JCX7aaYzmYHgiLqj1WDlVFHI-s-qanltoOrycQ5JU'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '1508'
ht-degree: 8%
---
# 在情境中加入模組

情境由一系列模組所組成，這些模組會指出如何在應用程式內轉換資料，或在應用程式和網頁服務之間如何轉移資料。 您可以透過新增和設定模組來建置模組。

本文說明將模組新增至案例的基本程式。 如需新增情境的詳細指示，請參閱[新增模組：文章索引](/help/workfront-fusion/create-scenarios/add-modules/add-modules-toc.md)下的其他文章。

>[!NOTE]
>
>Workfront Fusion正在將案例編輯器轉換為新體驗。 在此轉換期間，傳統體驗和新體驗皆可使用，而且您可以隨時在它們之間切換。 我們建議您使用新體驗。 如需詳細資訊，請參閱文章「情境編輯器」中的[新體驗和傳統體驗](/help/workfront-fusion/get-started-with-fusion/navigate-fusion/scenario-editor.md#new-and-classic-experiences)。

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

## 將第一個模組新增至情境

情境的第一個模組通常是觸發模組。

如需有關觸發模組的詳細資訊，請參閱文章模組概觀上的[觸發模組](/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md#trigger-modules)。

* [新增新體驗中的第一個模組（建議）](#add-the-first-module-in-the-new-experience-recommended)
* [在傳統體驗中新增第一個模組](#add-the-first-module-in-the-classic-experience)

### 新增新體驗中的第一個模組（建議）

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 按一下畫面右上角的&#x200B;**建立新情境**，開始建立情境。

   情境編輯器隨即開啟，其中包含預留位置模組和可用聯結器的清單。

   ![預留位置模組](/help/workfront-fusion/build-practice-scenarios/assets/new-placeholder-module.png)

   ![應用程式和服務選擇器](/help/workfront-fusion/build-practice-scenarios/assets/new-connector-picker.png)

1. 選取將啟動此情境的聯結器或webhook：

   * 使用左側的面板依類別瀏覽（[!UICONTROL 我的最愛]、[!UICONTROL 所有應用程式]、[!UICONTROL Adobe Workfront]、[!UICONTROL Adobe Firefly Services]、[!UICONTROL Adobe Creative &amp; Content]、[!UICONTROL Adobe Cloud Services]、[!UICONTROL Generative AI]或[!UICONTROL 內建]），或
   * 在搜尋方塊中輸入字詞。 輸入時會更新結果，在符合模組名稱和說明之前，會先列出符合的聯結器。

1. 按一下您要新增至情境的模組。

1. 設定模組。

   模組的設定會在畫布右側的面板中開啟。

   如需有關設定特定模組的說明，請參閱所選應用程式的文章，列於[Fusion應用程式及其模組參考中：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>* 在聯結器清單中，徽章可識別私人、進階和測試版應用程式。
>* 會將大型應用程式的模組組織成群組。
>* 新增錯誤處理常式時，會先列出指令。
>* 如果聯結器有一個以上的版本，則選取聯結器後，您將能夠選取版本。

>[!NOTE]
>
>如果您已從案例中移除第一個模組並想要取代它，請按一下預留位置模組以開啟聯結器清單。

### 在傳統體驗中新增第一個模組

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 按一下畫面右上角的&#x200B;**建立新情境**，開始建立情境。

   情境編輯器隨即開啟，其中含有預留位置（問號）模組和可用聯結器的清單。

   ![預留位置模組](assets/placeholder-module.png)

1. 選取將啟動此案例的聯結器或webhook。 您可以在清單的搜尋列中鍵入聯結器的名稱，以篩選清單。
1. 設定模組。

   如需有關設定特定模組的說明，請參閱所選應用程式的文章，列於[Fusion應用程式及其模組參考中：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>如果您已從案例中移除第一個模組並想要取代它，請按一下預留位置（問號）模組以開啟聯結器清單。

## 將另一個模組新增至情境

* [在新體驗中新增另一個模組（建議）](#add-another-module-in-the-new-experience-recommended)
* [在傳統體驗中新增另一個模組](#add-another-module-in-the-classic-experience)

### 在新體驗中新增另一個模組（建議）

1. 如果您不在您要新增模組的情境的情境編輯器中，請按一下左側面板中的&#x200B;**[!UICONTROL 情境]**&#x200B;索引標籤。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 若要在其他模組之後新增模組，請將滑鼠移到模組的右邊緣，之後您想要新增模組，然後在其出現時按一下[新增其他模組]。**&#x200B;**

   聯結器清單隨即開啟，顯示情景中已經使用的任何聯結器。

1. （選擇性）若要選取其他聯結器，請按一下[清單中新增其他模組] **&#x200B;**，然後選取聯結器：

   * 使用左側的面板依類別瀏覽（[!UICONTROL 我的最愛]、[!UICONTROL 所有應用程式]、[!UICONTROL Adobe Workfront]、[!UICONTROL Adobe Firefly Services]、[!UICONTROL Adobe Creative &amp; Content]、[!UICONTROL Adobe Cloud Services]、[!UICONTROL Generative AI]或[!UICONTROL 內建]），或
   * 在搜尋方塊中輸入字詞。 輸入時會更新結果，在符合模組名稱和說明之前，會先列出符合的聯結器。

1. 按一下您要新增至情境的模組。

1. 設定模組。

   模組的設定會在畫布右側的面板中開啟。

   如需有關設定特定模組的說明，請參閱所選應用程式的文章，列於[Fusion應用程式及其模組參考中：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

### 在傳統體驗中新增另一個模組

1. 如果您不在您要新增模組的情境的情境編輯器中，請按一下左側面板中的&#x200B;**[!UICONTROL 情境]**&#x200B;索引標籤。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 若要將模組新增至另一個模組，請將滑鼠游標停留在模組的右側控制代碼上，之後您要新增模組，然後在其出現時按一下[新增另一個模組] **&#x200B;**。

   聯結器清單隨即開啟，顯示情景中已經使用的任何聯結器。

1. （選擇性）若要選取其他聯結器，請按一下[清單中新增其他模組] **&#x200B;**，然後選取聯結器。 您可以在清單的搜尋列中鍵入聯結器的名稱，以篩選清單。
1. 設定模組。

   如需有關設定特定模組的說明，請參閱所選應用程式的文章，列於[Fusion應用程式及其模組參考中：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

## 在情境中的現有模組之間插入模組

* [在新體驗中插入模組（建議）](#insert-a-module-in-the-new-experience-recommended)
* [在傳統體驗中插入模組](#insert-a-module-in-the-classic-experience)

### 在新體驗中插入模組（建議）

1. 如果您不在您要新增模組的情境的情境編輯器中，請按一下左側面板中的&#x200B;**[!UICONTROL 情境]**&#x200B;索引標籤。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 以滑鼠右鍵按一下您要插入模組的模組之間的路徑，然後選取&#x200B;**新增模組**。

   ![在現有模組之間新增模組](assets/add-a-module-between-modules.png)

   聯結器清單隨即開啟，顯示情景中已經使用的任何聯結器。

1. （選擇性）若要選取其他聯結器，請按一下[清單中新增其他模組] **&#x200B;**，然後選取聯結器：

   * 使用左側的面板依類別瀏覽（[!UICONTROL 我的最愛]、[!UICONTROL 所有應用程式]、[!UICONTROL Adobe Workfront]、[!UICONTROL Adobe Firefly Services]、[!UICONTROL Adobe Creative &amp; Content]、[!UICONTROL Adobe Cloud Services]、[!UICONTROL Generative AI]或[!UICONTROL 內建]），或
   * 在搜尋方塊中輸入字詞。 輸入時會更新結果，在符合模組名稱和說明之前，會先列出符合的聯結器。

1. 按一下您要新增至情境的模組。

1. 設定模組。

   模組的設定會在畫布右側的面板中開啟。

   如需有關設定特定模組的說明，請參閱所選應用程式的文章，列於[Fusion應用程式及其模組參考中：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>若要建立特定模組的連結，請在檢視下列頁面時將`?moduleId=<module-id>`新增至URL：
>
>* 案例編輯頁面（URL結尾為`/edit`）
>* 特定案例執行（URL結尾為`/logs/<log-id>`）
>
>`<module-id>`在檢視案例時參照模組標籤旁的數字。
>
>這在偵錯案例或複製模組設定時可能很有用。

### 在傳統體驗中插入模組

1. 如果您不在您要新增模組的情境的情境編輯器中，請按一下左側面板中的&#x200B;**[!UICONTROL 情境]**&#x200B;索引標籤。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 按一下您要插入模組的模組之間的虛線路徑。
1. 在出現的功能表中，選取&#x200B;**新增模組**。

聯結器清單隨即開啟，顯示情景中已經使用的任何聯結器。

1. （選擇性）若要選取其他聯結器，請按一下[清單中新增其他模組] **&#x200B;**，然後選取聯結器。 您可以在清單的搜尋列中鍵入聯結器的名稱，以篩選清單。
1. 設定模組。

   如需有關設定特定模組的說明，請參閱所選應用程式的文章，列於[Fusion應用程式及其模組參考中：文章索引](/help/workfront-fusion/references/apps-and-modules/apps-and-modules-toc.md)。

>[!NOTE]
>
>若要建立特定模組的連結，請在檢視下列頁面時將`?moduleId=<module-id>`新增至URL：
>
>* 案例編輯頁面（URL結尾為`/edit`）
>* 特定情境執行（URL結尾為`/logs/<log-id>`）
>
>`<module-id>`在檢視案例時參照模組標籤旁的數字。
>
>這在偵錯案例或複製模組設定時可能很有用。

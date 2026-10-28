---
title: 檢視特定情境執行
description: 您可以檢視特定案例執行的詳細資訊，包括篩選和搜尋案例事件。
author: Becky
feature: Workfront Fusion
exl-id: 34dd9836-9a1b-4ce2-b24e-ae769888a52a
TQID: 'https://experienceleague.adobe.com/Msh3ArxBUIu6YDZjL7eXpxlEBiYABHN-Q7xUlJ-qU0g'
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
    internal-label: Workfront
feature_v2:
  - id: c3a155b4-a54b-4a82-a3d2-c8f0f971673e
    internal-label: Workfront Fusion
source-git-commit: cc160f0e8c2465b4f102b6d1755088335b2a9fe5
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 15%
---
# 檢視特定情境執行

您可以檢視特定案例執行的詳細資訊，包括篩選和搜尋案例事件。

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

若要詳細了解此表格中的資訊，請參閱](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求[。

+++

## 檢視特定執行

您可以從情境的情境歷史記錄中檢視執行。


1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤，然後按一下案例。

   或

   如果您正在案例編輯器中處理案例，請按一下視窗左上角附近的向左箭頭![結束編輯箭頭](assets/exit-editing-arrow.png)。

1. 按一下情境名稱附近的&#x200B;**歷程記錄**。
   ![歷程記錄標籤](assets/history-tab.png)


1. 找到您要檢視的執行專案，然後按一下該執行專案最右邊的&#x200B;**詳細資料**。 [!UICONTROL 詳細資料]連結只有在執行有可用的詳細資料時才可見。

   情境圖表隨即開啟，右側會顯示執行詳細資訊面板。

   為此執行產生輸出的模組會標示綠色標題。

   未執行的模組會變暗。

1. 若要檢視模組的輸出，請按一下模組附近的輸出詳細資訊泡泡。 泡泡圖中的數字代表模組輸出的組合數量。

   ![模組附近的輸出泡泡](assets/new-output-bubble.png)

1. 若要檢視通過篩選的組合，請按一下篩選。 篩選器附近的數字代表透過篩選器的組合數量。
1. 若要在執行面板中搜尋特定模組或事件，請在&#x200B;**搜尋執行事件**&#x200B;方塊中輸入搜尋字詞。 當您鍵入時，結果會顯示出來。
1. 若要依「成功」或「警告」等狀態限制執行面板搜尋結果，請按一下&#x200B;**狀態篩選**&#x200B;下拉式清單，然後選取狀態。




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

## 在新的案例編輯器中檢閱執行

在新版Experience中，當您從執行記錄開啟執行時，畫布右側附近的控制項可協助您找出問題，而不需編輯情境：

![檢閱執行](assets/review-an-execution.png)

| 控制 | 詳細資料 |
| ---------- | ---------- |
| 移至下一個錯誤或警告 | 顯示目前週期中有多少模組發生問題。 每次點選都會移到下一個專案，先是錯誤，然後從左到右依次顯示警告。 它會置中模組，並開啟第一個失敗的操作。 當執行沒有錯誤或警告時，按鈕會隱藏。 |
| 搜尋模組 | 依名稱尋找模組，並將其置中在畫布上。 按Ctrl+K (Windows)或Command+K (Mac)。 |
| 附註 | 顯示或隱藏情境的附註。 此控制項僅在案例具有附註，且附註在此為唯讀時顯示。 |
| 說明流程 | 將案例模組執行的順序製成動畫。 再按一下，或按Esc停止。 |
| 放大、縮小、聚焦和迷你地圖 | 與編輯模式中的工作方式相同。 |

**壓縮檢視**&#x200B;切換開關也可在右上角使用。 當您檢閱執行時，它只會在您檢視該執行時變更版面。 它不會變更您的壓縮檢視設定以進行編輯，並且不會將任何內容儲存到情境。

在執行中選取要置中的事件，並反白標示比對模組。 有可用的作業詳細資訊時，請求和回應面板會開啟。 如果面板沒有資料，則不會為該執行保留請求和回應詳細資料。 若要收集它們以供未來執行，請參閱[暫時的偵錯記錄檔](/help/workfront-fusion/create-scenarios/config-scenarios-settings/configure-scenario-settings.md#temporary-debug-logs)。

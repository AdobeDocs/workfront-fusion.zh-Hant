---
title: 檢視特定案例執行
description: 您可以檢視特定案例執行的詳細資訊，包括篩選和搜尋案例事件。
author: Becky
feature: Workfront Fusion
exl-id: 34dd9836-9a1b-4ce2-b24e-ae769888a52a
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 1%

---

# 檢視特定案例執行

您可以檢視特定案例執行的詳細資訊，包括篩選和搜尋案例事件。

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

   ![模組附近的輸出泡泡](assets/output-bubble.png)

1. 若要檢視通過篩選的組合，請按一下篩選。 篩選器附近的數字代表透過篩選器的組合數量。
1. 若要在執行面板中搜尋特定模組或事件，請在&#x200B;**搜尋執行事件**&#x200B;方塊中輸入搜尋字詞。 當您鍵入時，結果會顯示出來。
1. 若要依「成功」或「警告」等狀態限制執行面板搜尋結果，請按一下&#x200B;**狀態篩選**&#x200B;下拉式清單，然後選取狀態。




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

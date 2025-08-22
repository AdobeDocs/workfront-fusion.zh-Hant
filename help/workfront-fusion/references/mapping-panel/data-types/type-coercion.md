---
title: 輸入強制
description: 本檔案說明Adobe Workfront Fusion在收到預期和意外資料格式的值時如何行動。
author: Becky
feature: Workfront Fusion
exl-id: a8bdd36d-c01f-4019-a3ea-fb185101500e
source-git-commit: e0d9d76ab2cbd8bd277514a4291974af4fceba73
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 5%

---

# 輸入強制

## 存取需求

+++ 展開以檢視本文中功能的存取需求。

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
    <td role="rowheader">Adobe Workfront計畫*</td> 
   <td> <p>[!DNL Pro] 或更高</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront授權*</td> 
   <td> <p>[！UICONTROL計畫]，[！UICONTROL工作]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[！UICONTROL Adobe Workfront Fusion]授權**</td> 
   <td>
   <p>目前授權需求：無Workfront Fusion授權需求。</p>
   <p>或</p>
   <p>舊版授權要求：[！UICONTROL Workfront Fusion for Work Automation and Integration] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[！UICONTROL Select]或[！UICONTROL Prime] Adobe Workfront計畫，貴組織必須購買Adobe Workfront Fusion以及Adobe Workfront，才能使用本文所述的功能。 Workfront Fusion包含在[！UICONTROL Ultimate] Workfront計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買Adobe Workfront Fusion和Adobe Workfront，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請聯絡您的Workfront管理員。

如需Adobe Workfront Fusion授權的相關資訊，請參閱[Adobe Workfront Fusion授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

### 輸入強制

本檔案說明Adobe Workfront Fusion在收到預期和意外資料格式的值時如何行動。

<table style="table-layout:auto">
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>預期</th> 
   <th>已收到</th> 
   <th> <p>說明</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td>陣列 </td> 
   <td>陣列 </td> 
   <td> <p>值會以不變的方式傳遞。</p> </td> 
  </tr> 
  <tr> 
   <td>陣列 </td> 
   <td>其他 </td> 
   <td> <p>如果收到的值不是陣列型別，Workfront Fusion會建立一個陣列，第一個（也是唯一的）元素將是收到的值。</p> </td> 
  </tr> 
  <tr> 
   <td>布林值 </td> 
   <td>布林值 </td> 
   <td> <p>值會以不變的方式傳遞。</p> </td> 
  </tr> 
  <tr> 
   <td>布林值 </td> 
   <td>數字 </td> 
   <td> <p>即使值為0，該值也會轉換為邏輯「是」。</p> </td> 
  </tr> 
  <tr> 
   <td>布林值 </td> 
   <td>文字 </td> 
   <td> <p>如果值等於false或為空白，則會轉換為邏輯「否」。 如果沒有，則會轉換為邏輯「是」。</p> </td> 
  </tr> 
  <tr> 
   <td>布林值 </td> 
   <td>其他 </td> 
   <td> <p>只要收到的值存在（不是空值），該值就會轉換為邏輯「是」。</p> </td> 
  </tr> 
  <tr> 
   <td>緩衝 </td> 
   <td>緩衝 </td> 
   <td> <p>只有在程式碼頁如預期般時，才會傳遞未變更的值。 如果字碼頁不同，Workfront Fusion會嘗試將收到的值轉換為要求的字碼頁。 如果不支援此轉換，Workfront Fusion將會傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>緩衝 </td> 
   <td>布林值 </td> 
   <td> <p>值會轉換為文字(true/false)，然後依照上述步驟轉換為二進位資料。</p> </td> 
  </tr> 
  <tr> 
   <td>緩衝 </td> 
   <td>日期 </td> 
   <td> <p>值會轉換為ISO 8601文字，然後依照上述轉換為文字的步驟轉換為二進位資料。</p> </td> 
  </tr> 
  <tr> 
   <td>緩衝 </td> 
   <td>數字 </td> 
   <td> <p>值會轉換為文字，然後依照上述步驟轉換為二進位資料，以轉換為文字。</p> </td> 
  </tr> 
  <tr> 
   <td>緩衝 </td> 
   <td>文字 </td> 
   <td> <p>值會轉換為二進位資料，並按預期編碼。 如果未指定預期的編碼，則會使用utf8編碼。</p> </td> 
  </tr> 
  <tr> 
   <td>緩衝 </td> 
   <td>其他 </td> 
   <td> <p>Workfront Fusion傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>集合 </td> 
   <td>集合 </td> 
   <td> <p>值會以不變的方式傳遞。</p> </td> 
  </tr> 
  <tr> 
   <td>集合 </td> 
   <td>其他 </td> 
   <td> <p>Workfront Fusion傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>日期 </td> 
   <td>日期 </td> 
   <td> <p>值會以不變的方式傳遞。</p> </td> 
  </tr> 
  <tr> 
   <td>日期 </td> 
   <td>文字 </td> 
   <td> <p>Workfront Fusion會嘗試將文字轉換為日期。 如果轉換失敗，則會傳回驗證錯誤。 日期必須包含日、月和年。 日期可能包含時間和時區。 預設時區是以您的設定為準。 範例：</p> <p><code>2016-06-20T17:26:44.356Z</code> </p> <p><code>2016-06-20 19:26:44 GMT+02:00</code> </p> <p><code>2016-06-20 19:26+0200</code> </p> <p><code>2016-06-20 17:26:44</code> </p> <p><code>2016-06-20</code> </p> <p><code>2016/06/20 17:26:44</code> </p> <p><code>2016/06/20 19:26:44+02:00</code> </p> <p><code>2016/06/20 17:26</code> </p> <p><code>2016/06/20 5:26 PM</code> </p> <p><code>2016/06/20</code> </p> <p><code>06/20/2016 17:26:44</code> </p> <p><code>06/20/2016 19:26:44+02:00</code> </p> <p><code>06/20/2016 17:26</code> </p> <p><code>06/20/2016 5:26 PM</code> </p> <p><code>06/20/2016</code> </p> <p><code>20.6.2016 17:26:44</code> </p> <p><code>20.6.2016 19:26:44+02:00</code> </p> <p><code>20.6.2016 17:26</code> </p> <p><code>20.6.2016</code> </p> </td> 
  </tr> 
  <tr> 
   <td>日期 </td> 
   <td>其他 </td> 
   <td> <p>Workfront Fusion傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>數字 </td> 
   <td>數字 </td> 
   <td> <p>值會以不變的方式傳遞。</p> </td> 
  </tr> 
  <tr> 
   <td>數字 </td> 
   <td>文字 </td> 
   <td> <p>Workfront Fusion會嘗試將文字轉換為數字。 如果轉換失敗，則會傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>數字 </td> 
   <td>其他 </td> 
   <td> <p>Workfront Fusion傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>文字 </td> 
   <td>文字 </td> 
   <td> <p>值會以不變的方式傳遞。</p> </td> 
  </tr> 
  <tr> 
   <td>文字 </td> 
   <td>陣列 </td> 
   <td> <p>如果指定的陣列支援轉換為文字，則會轉換值。 否則，Workfront Fusion會傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>文字 </td> 
   <td>布林值 </td> 
   <td> <p>值會轉換為文字(true/false)。</p> </td> 
  </tr> 
  <tr> 
   <td>文字 </td> 
   <td>緩衝 </td> 
   <td> <p>如果為二進位資料指定了文字編碼，該值將會轉換為文字。 否則，Workfront Fusion會傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>文字 </td> 
   <td>日期 </td> 
   <td> <p>值會轉換為ISO 8601文字。</p> </td> 
  </tr> 
  <tr> 
   <td>文字 </td> 
   <td>數字 </td> 
   <td> <p>值會轉換為文字。</p> </td> 
  </tr> 
  <tr> 
   <td>文字 </td> 
   <td>其他 </td> 
   <td> <p>Workfront Fusion傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>時間 </td> 
   <td>時間 </td> 
   <td> <p>值會以不變的方式傳遞。</p> </td> 
  </tr> 
  <tr> 
   <td>時間 </td> 
   <td>文字 </td> 
   <td> <p>Workfront Fusion將嘗試將時間轉換為<code>hours:minutes:seconds</code>格式。 如果轉換失敗，則會傳回驗證錯誤。</p> </td> 
  </tr> 
  <tr> 
   <td>時間 </td> 
   <td>其他 </td> 
   <td> <p>Workfront Fusion傳回驗證錯誤。</p> </td> 
  </tr> 
 </tbody> 
</table>

---
content-type: reference
title: 排程情境
description: 依預設，一個案例每15分鐘執行一次。 您可以定義已啟動案例執行的時間和頻率，以變更此專案。 融合情境可以排程為每5分鐘執行一次。
author: Becky
feature: Workfront Fusion
recommendations: noDisplay, noCatalog
exl-id: 9b74af0d-e7ff-4bf5-974e-0651d0d51f71
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# 排程情境

依預設，一個案例每15分鐘執行一次。 您可以定義已啟動案例執行的時間和頻率，以變更此專案。 融合情境可以排程為每5分鐘執行一次。

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
     <p>您必須是組織的[!DNL Workfront Fusion]管理員。</p>
     <p>您必須是團隊的[!DNL Workfront Fusion]管理員。</p>
   </td> 
  </tr> 
   </td> 
  </tr> 
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 排程情境

1. 按一下左側面板中的&#x200B;**案例**&#x200B;索引標籤。
1. 選取您要排程的情境。
1. 在「情境詳細資料」頁面的右上角，按一下&#x200B;**[!UICONTROL Options]** > **[!UICONTROL Scheduling]**

   或

   按一下情境觸發程式模組上的&#x200B;**[!UICONTROL Scheduling]**&#x200B;圖示（時鐘）。

1. 在下列欄位中輸入資訊：

   <table style="table-layout:auto">   
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Run scenario]</td> 
      <td> <p>選取您要執行情境的頻率，然後選取間隔。</p> 
       <ul> 
        <li> <p><strong>[!UICONTROL At regular intervals]</strong> </p> <p>輸入執行之間的分鐘數。 預設值為15分鐘。</p> </li> 
        <li> <p><strong>[!UICONTROL Once]</strong> </p> <p>輸入您希望案例執行的日期和時間。 使用格式<code>MM/DD/YYYY h:mm A</code>。 範例： <code>06/25/2019 11:00 PM</code>。</p> </li> 
        <li> <p><strong>[!UICONTROL Every day]</strong> </p> <p>輸入您希望案例執行的時間。 使用格式<code>h:mm A</code>。 範例： <code>11:00 PM</code>。</p> </li> 
        <li> <p><strong>[!UICONTROL Days of the week]</strong> </p> <p>天數：選取您希望案例在一週中執行的天數。 您可以選取一或多天。</p> <p>時間：輸入您希望案例在所選日期執行的時間。 使用格式<code>h:mm A</code>。 範例： <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Days of the month]</strong> </p> <p>天數：選取您希望案例執行的月份天數。 您可以選取一或多天。</p> <p>時間：輸入您希望案例在所選日期執行的時間。 使用格式<code>h:mm A</code>。 範例： <code>11:00 PM</code></p> </li> 
        <li> <p><strong>[!UICONTROL Specified dates]</strong> </p> <p>月份：選取您要執行案例的月份。 您可以選取一或多個月份。</p> <p>天數：選取您希望案例執行的月份天數。 您可以選取一或多天。</p> <p>時間：輸入您希望案例在所選日期執行的時間。 使用格式<code>h:mm A</code>。 範例： <code>11:00 PM</code></p> </li> 
       </ul> <p>備註：案例必須有日期才能在該日期執行。 例如，僅排定在該月第31天的情境將不會在2月、4月、6月、9月或11月執行，因為這些月份沒有第31天。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Advanced scheduling]</td> 
      <td>您可以定義執行情境的特定時間間隔。 您可以指定一天中的時間間隔、工作日或月。 對於每個間隔，按一下<strong>[!UICONTROL Add]</strong>並填入[!UICONTROL Run scenario]欄位中所述的欄位。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Start]</td> 
      <td>輸入您希望案例執行的日期和時間。 使用格式<code>MM/DD/YYYY h:mm A</code>。 範例： <code>06/25/2019 11:00 PM</code>。</td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL End]</td> 
      <td>輸入您希望案例執行的日期和時間。 使用格式<code>MM/DD/YYYY h:mm A</code>。 範例： <code>06/25/2019 11:00 PM</code>。</td> 
     </tr> 
    </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;儲存排程設定並返回案例。

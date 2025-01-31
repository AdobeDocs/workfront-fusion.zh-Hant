---
title: SOAP 模組
description: 您可以使用SOAP模組來連線到Adobe Workfront Fusion中的SOAP API。
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
source-git-commit: bf9af473f08463c00578a1a8b07c800239225f09
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 1%

---

# [!UICONTROL SOAP]模組

您可以使用[!UICONTROL SOAP]模組連線至[!UICONTROL Adobe Workfront Fusion]中的[!UICONTROL SOAP] API。

## 存取需求

您必須具有下列存取權才能使用本文中的功能：

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 計畫*</td>
  <td> <p>[!UICONTROL Pro] 或更高</p> </td>
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">[!DNL Adobe Workfront] 授權*</td>
   <td> <p>[!UICONTROL Plan]， [!UICONTROL Work]</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 授權**</td> 
   <td>
   <p>目前授權需求：無[!DNL Workfront Fusion]授權需求。</p>
   <p>或</p>
   <p>舊版授權需求： [!UICONTROL [!DNL Workfront Fusion]工作自動化與整合] </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>目前產品需求：如果您有[!UICONTROL Select]或[!UICONTROL Prime] [!DNL Adobe Workfront]計畫，您的組織必須購買[!DNL Adobe Workfront Fusion]和[!DNL Adobe Workfront]，才能使用本文所述的功能。 [!DNL Workfront Fusion]包含在[!UICONTROL Ultimate] [!DNL Workfront]計畫中。</p>
   <p>或</p>
   <p>舊版產品需求：您的組織必須購買[!DNL Adobe Workfront Fusion]及[!DNL Adobe Workfront]，才能使用本文所述的功能。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

若要瞭解您擁有的計畫、授權型別或存取權，請連絡您的[!DNL Workfront]管理員。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

## [!UICONTROL SOAP]模組的限制

>[!NOTE]
>
>在WDSL載入期間會停用重新導向。 這是安全性功能，但可能表示執行模組時會封鎖未驗證的重新導向。

[!UICONTROL SOAP]模組目前為測試版，不支援：

* 重新定義元素
* 小數位數限制
* 總數字限制
* 空白字元限制
* 輸入和輸出訊息中有多個部分。 僅支援單一零件訊息
* 在[[!UICONTROL SOAP]編碼](https://schemas.xmlsoap.org)結構描述和元素的說明下定義的自訂XML結構描述元素。

>[!INFO]
>
>**範例：**
>  
>[!UICONTROL Workfront Fusion]無法正確辨識下列專案：
>
>```
><complexType name="ArrayOfFloat">
>     <complexContent>
>           <restriction base="soapenc:Array">
>                 <attribute ref="soapenc:arrayType"
>                       wsdl:arrayType="xsd:integer[]"/>
>           </restriction>
>     </complexContent>
></complexType>
>```
>
>此範例包含[!UICONTROL Workfront Fusion]尚未支援的`soapenc:Array`、`soapenc:arrayType`和`wsdl:arrayType`參考。

## 因應措施

如果[!UICONTROL SOAP]模組拒絕處理WSDL檔案或在模組設定中擲回各種錯誤，您可以嘗試改用通用&#x200B;**[!UICONTROL HTTP]>[!UICONTROL Make a request]**&#x200B;模組：

1. 在[!DNL Workfront Fusion]中建立新情境。
1. 在情境中插入&#x200B;**[!UICONTROL HTTP]>[!UICONTROL Make a request]**&#x200B;模組。
1. 開啟模組的設定，並填寫下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL Method]</td> 
      <td> <p>[!UICONTROL POST]</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td role="rowheader">[!UICONTROL Body type]</td> 
      <td> <p>[!UICONTROL Raw]</p> </td>
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Content type]</td> 
      <td> <p>[!UICONTROL XML (application/xml)]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[!UICONTROL Parse response]</td> 
      <td>[!UICONTROL Enabled]</td> 
     </tr> 
    </tbody> 
   </table>

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. 開啟新的Web瀏覽器視窗或標籤。
1. 將WSDL URL貼入網頁瀏覽器的位址列，並擷取XML檔案。

   WSDL URL通常以`?wsdl`結尾，但不一定是，例如`http://voip.ms/api/v1/server.wsdl`。

1. 如果WSDL檔案沒有直接顯示在網頁瀏覽器中，請在文字編輯器中開啟下載的檔案。
1. 搜尋`<service>`或`<wsdl:service>`標籤：

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. 找到後，從`location`屬性複製URL。
1. 在[!DNL Workfront Fusion]中，將URL貼到HTTP模組的URL欄位中。
1. 在新的網頁瀏覽器視窗/標籤中開啟[線上[!UICONTROL SOAP]使用者端](https://wsdlbrowser.com/)。
1. 將WSDL URL貼到WSDL URL欄位中。
1. 按一下&#x200B;**[!UICONTROL Browse]**。
1. 從左側的函式清單中選取，例如`getLanguages`。
1. 複製[!UICONTROL Request XML]文字區域的內容。
1. 在[!UICONTROL Workfront Fusion]中，將複製的內容貼到模組的URL欄位。
1. 將問號取代為實際值，以提供所選引數的值：

   <!--![](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;關閉模組的設定。
1. 執行案例或模組。

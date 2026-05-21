---
title: SOAP 模組
description: 您可以使用SOAP模組來連線至Adobe Workfront Fusion中的SOAP API。
author: Becky
feature: Workfront Fusion
exl-id: dbcc04f8-8306-4a81-aed8-1ce0798e145f
TQID: https://experienceleague.adobe.com/MIMXln44-LWfrQf0w-lZXfZJ3020Flty2CgwSC3JI9c
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
feature_v2: id: b58ad82f-df6b-4b01-81a3-3a02ab9567a0
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 647
ht-degree: 26%

---

# [!UICONTROL SOAP]模組

您可以使用[!UICONTROL SOAP]模組來連線至[!UICONTROL Adobe Workfront Fusion]中的[!UICONTROL SOAP] API。

## SOAP模組及其欄位

SOAP聯結器僅包含一個模組：執行SOAP動作

### 執行SOAP動作

此動作模組會執行指定的SOAP動作。



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
   <td role="rowheader">Adobe Workfront Fusion 授權</td> 
   <td>
   <p>作業型：無 Workfront Fusion 授權要求</p>
   <p>連接器型 (舊版)：Workfront Fusion for Work Automation and Integration </p>
   </td> 
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

關於 Adobe Workfront Fusion 授權的資訊，請參閱 [Adobe Workfront Fusion 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## SOAP模組及其欄位

設定SOAP模組時，Workfront Fusion會顯示下列欄位。  在模組中，粗體標題表示那是必要欄位。

若在欄位或函式上方看到對應按鈕，可以使用按鈕設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![對應切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 執行SOAP動作

此動作模組會根據您指定的WSDL執行SOAP動作。

<table style="table-layout:auto">
 <col> 
 </col> 
 <col> 
 </col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL WSDL]</td> 
   <td> 選取您希望模組使用的WSDL。 若要建立WSDL，請按一下欄位旁的<b>新增</b>並填寫欄位。 </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL HTTP標頭]</td> 
   <td> 針對您想要新增的每個HTTP標頭，按一下<b>新增專案</b>並輸入標頭的名稱和值。</td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL SOAP headers]</td> 
   <td> 針對您要新增的每個SOAP標頭，按一下<b>新增專案</b>並輸入標頭的名稱、值、名稱空間及XMLNS。</td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td>[！UICONTROL Force SOAP headers]</td> 
   <td> 啟用此選項以設定SOAP 1.2的標頭。 </td> 
  </tr> 
  </tbody> 
</table>

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
* 在SOAP編碼結構描述和元素的協助下定義的自訂XML結構描述元素。

>[!BEGINSHADEBOX]

**範例：**

[!UICONTROL Workfront Fusion]無法正確辨識下列專案：

```
<complexType name="ArrayOfFloat">
   <complexContent>
      <restriction base="soapenc:Array">
         <attribute ref="soapenc:arrayType"
            wsdl:arrayType="xsd:integer[]"/>
      </restriction>
   </complexContent>
</complexType>
```

此範例包含[!UICONTROL Workfront Fusion]尚未支援的`soapenc:Array`、`soapenc:arrayType`和`wsdl:arrayType`參考。

>[!ENDSHADEBOX]

## 因應措施

如果[!UICONTROL SOAP]模組拒絕處理WSDL檔案或在模組設定中擲回各種錯誤，您可以嘗試改用通用&#x200B;**[!UICONTROL HTTP] > [!UICONTROL 發出要求]**&#x200B;模組：

1. 在Workfront Fusion中建立新情境。
1. 在情境中插入&#x200B;**[!UICONTROL HTTP] > [!UICONTROL 提出要求]**&#x200B;模組。
1. 開啟模組的設定，並填寫下列欄位：

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">[!UICONTROL 方法]</td> 
      <td> <p>[！UICONTROL POST]</p> </td> 
     </tr> 
     <tr data-mc-conditions=""> 
      <td role="rowheader">[！UICONTROL主體型別]</td> 
      <td> <p>[！UICONTROL Raw]</p> </td>
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL內容型別]</td> 
      <td> <p>[！UICONTROL XML (application/xml)]</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">[！UICONTROL剖析回應]</td> 
      <td>[！UICONTROL已啟用]</td> 
     </tr> 
    </tbody> 
   </table>

   <!--![Workaround](/help/workfront-fusion/references/apps-and-modules/assets/workaround-350x443.png)-->

1. 開啟新的Web瀏覽器視窗或標籤。
1. 將WSDL URL貼入網頁瀏覽器的位址列，並擷取XML檔案。

   WSDL URL通常以`?wsdl`結尾，但不一定是，例如`http://voip.ms/api/v1/server.wsdl`。

1. 如果WSDL檔案沒有直接顯示在網頁瀏覽器中，請在文字編輯器中開啟下載的檔案。
1. 搜尋`<service>`或`<wsdl:service>`標籤：

   <!--![Service](/help/workfront-fusion/references/apps-and-modules/assets/service-350x65.png)-->

1. 找到後，從`location`屬性複製URL。
1. 在Workfront Fusion中，將URL貼到HTTP模組的&#x200B;**要求內容**&#x200B;欄位中。
1. 將問號取代為實際值，以提供所選引數的值。

   >[!NOTE]
   >
   > 若要從WSDL檔案取得特定值，請使用線上WSDL檢視器。

   <!--![Request](/help/workfront-fusion/references/apps-and-modules/assets/request-xml-350x172.png)-->

1. 按一下&#x200B;**[!UICONTROL 確定]**，關閉模組的設定。
1. 執行案例或模組。

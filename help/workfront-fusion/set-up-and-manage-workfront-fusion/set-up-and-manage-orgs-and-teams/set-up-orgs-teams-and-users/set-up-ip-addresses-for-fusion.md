---
title: 在組織的允許清單中設定Fusion的IP位址
description: Fusion使用特定的IP位址和網域進行Web通訊。 必須先將這些專案新增到貴組織的允許清單中，您才能在組織中使用Workfront。
author: Becky
feature: Workfront Fusion
exl-id: 406dd45c-0863-4270-a80e-c1c115e0b367
source-git-commit: 59d739093c88238af7a7e97499fd0c7d7cf6053a
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# 在組織的允許清單中設定Fusion的IP位址

由於Adobe Workfront Fusion會與貴組織的網路通訊，因此貴組織的防火牆必須設定為允許該通訊。 防火牆是高度有效的安全措施，可將組織的網路與網際網路隔離開來。 它們可確保只有選取的資料和網路流量可以移入或移出組織的網路。 防火牆會根據傳送或接收資料的網站，允許或封鎖資料。 身為Fusion管理員，您必須確保傳送至或來自Fusion的資料可透過您組織的防火牆。

這是透過允許清單來完成，其實質為「允許」透過防火牆傳送或接收資料的網站「清單」。 您可以使用下列兩種方式之一來識別網站：

* **IP位址**：一系列數字，例如52.31.132.175
* **網域**： URL的一部分，例如`www.thisdomain.com`中的`thisdomain`

Fusion使用特定的IP位址和網域進行Web通訊。 必須先將這些專案新增到貴組織的允許清單中，您才能在組織中使用Workfront。

通常由網路管理員設定允許清單。 請與貴組織的網路管理員合作，確保您的防火牆允許這些IP位址。 如果您不知道您的網路管理員是誰，貴組織的IT部門可以引導您往正確的方向前進。

>[!IMPORTANT]
>
>作為Fusion管理員，您必須確保將這些IP位址和網域新增到您組織的允許清單中。 即使您自己不新增這些專案，也是如此。 Fusion無法設定您組織的允許清單。

您可以將所有Fusion IP位址和網域新增至允許清單，也可以找到Fusion叢集並僅新增該叢集的IP位址和網域。

## 新增所有Fusion IP位址和網域

將下列IP位址新增至允許清單：

* 52.30.133.50
* 54.220.93.204
* 34.254.76.122
* 54.244.142.219
* 52.39.217.230
* 44.241.82.96
* 100.20.126.137
* 34.223.32.4
* 52.39.176.220
* 20.36.133.48/28
* 20.81.156.240/28
* 172.172.84.48/28

此外，如果您的組織使用傳出網路篩選，請將以下網域新增到您的允許清單，讓您的系統能夠存取Workfront Fusion。

* hook.app.workfrontfusion.com
* hook.app-eu.workfrontfusion.com
* hook.app-az.workfrontfusion.com

## 僅為您的叢集新增Fusion IP位址和網域

### 識別您的資料中心

IP位址會依您儲存資料的位置而有所不同。

如果您透過URL存取Fusion，則可檢查URL以找出您的資料中心。

| URL | 資料中心 |
| --- | --- |
| `https://app.workfrontfusion.com` | 美國資料中心 |
| `https://app-eu.workfrontfusion.com` | 歐盟資料中心 |
| `https://app-az.workfrontfusion.com` | Azure叢集 |

如果您透過`experience.adobe.com`存取Fusion，可以檢查瀏覽器中的網路索引標籤，以識別資料中心。

| URL | 資料中心 |
| --- | --- |
| 呼叫`https://fusion.adobe.com` | 美國資料中心 |
| 呼叫`https://eu.fusion.adobe.com` | 歐盟資料中心 |
| 呼叫`https://az.fusion.adobe.com` | Azure叢集 |

### 為您的資料中心新增IP位址和網域

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 歐盟資料中心</td> 
   <td> 
    <ul> 
     <li>52.30.133.50</li> 
     <li>54.220.93.204</li> 
     <li>34.254.76.122</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront] 美國資料中心</p> </td> 
   <td> 
    <ul> 
     <li>54.244.142.219</li> 
     <li>52.39.217.230</li> 
     <li>44.241.82.96</li>
     <li>100.20.126.137</li>
     <li>34.223.32.4</li>
     <li>52.39.176.220</li>
    </ul> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront Fusion] 在Microsoft Azure叢集上</td> 
   <td> 
    <ul> 
     <li>20.36.133.48/28</li> 
     <li>20.81.156.240/28</li> 
     <li>172.172.84.48/28</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

此外，如果您的組織使用傳出網路篩選，請將以下網域新增到您的允許清單，讓您的系統能夠存取Workfront Fusion。 這些會用於Webhook

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!DNL Adobe Workfront] 歐盟資料中心</td> 
   <td> <p> hook.app-eu.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront] 美國資料中心</p> </td> 
   <td> <p>hook.app.workfrontfusion.com </p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!DNL Adobe Workfront Fusion] 在Microsoft Azure叢集上</p> </td> 
   <td> <p>hook.app-az.workfrontfusion.com </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>傳出網路篩選並不常見。 請洽詢您的網路管理員，以瞭解是否需要更新允許清單以符合您的要求。

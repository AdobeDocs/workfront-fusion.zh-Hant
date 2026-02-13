---
title: 處理大型檔案
description: Workfront和HTTP聯結器目前提供大型檔案支援。
author: Becky
feature: Workfront Fusion
exl-id: 6df81943-e70c-42b3-aa44-d82343598a51
source-git-commit: 2493ce7ccca599e30b44b62558573ce2a55b03e0
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 6%

---

# 處理大型檔案

>[!IMPORTANT]
>
>大型檔案功能僅適用於Workfront Ultimate套件上的組織。

Workfront Fusion現在提供增強的資料傳輸功能，讓場景可以處理顯著更大的檔案。

若要處理大型檔案，必須更新您的情境。

## 支援大型檔案的聯結器

目前，下列聯結器支援大型檔案。

>[!NOTE]
>
>* 如果使用支援大型檔案的模組下載檔案，然後傳遞至不支援大型檔案的模組，則該模組無法成功處理相關檔案。在整個工作流程中，大型檔案必須由支援的模組專門處理。
>* 不支援大型檔案的模組可處理大小最大為200 MB的檔案。

* Workfront
   * 上傳檔案
   * 下載文件
* Adobe Experience Manager Assets
   * 上傳文件
* Workfront Proof
   * 上傳檔案
   * 下載校訂
* Adobe Authenticator
   * 進行自訂API呼叫
* Adobe Photoshop
   * 套用PSD編輯
* SharePoint
   * 建立檔案
   * 建立檔案（舊版）
   * 取得檔案
* Salesforce
   * 上傳檔案
* AWS S3
   * 上傳檔案
   * 取得檔案
* HTTP

未來版本將支援其他聯結器。

## 更新您的情境以處理大型檔案

Workfront >上傳檔案模組已修改為處理大型檔案。 此模組的先前版本現在顯示附加至模組名稱的`(Legacy)`。 在大多數情況下，舊版模組仍可繼續運作。

如果您打算使用較大的檔案，建議將舊版模組取代為新的上傳檔案模組。 新的上傳檔案模組可防止逾時和其他錯誤。

![上傳檔案](assets/new-upload-document.png)

## 常見問題集

### 新的檔案大小限製為何？

使用者現在可以處理超過先前1 GB限制的檔案，進而提高效率和生產力。  雖然Workfront Fusion平台沒有已定義的檔案大小限制，但還有其他因素可能會影響大型檔案的使用：

* **Fusion所連線之服務的檔案大小限制**：如果服務限制檔案大小，Workfront Fusion不會克服該限制。 檔案大小限制最終取決於Fusion所連線的Web服務。

* **案例執行時間**： Fusion會處理任何大小的檔案，直到達到40分鐘的執行限制。 在您的Fusion案例中，大型檔案可能需要一些時間才能上傳、下載或處理。 如果大型檔案會導致執行超過40分鐘，則案例會失敗。 案例執行時間也可能會受到案例大小、模組複雜性和網路速度影響。 因此，我們建議您在使用大型檔案時，從這些方面考慮情境。

>[!NOTE]
>
>作為最佳實務，我們建議將檔案大小限製為15 GB。

### Fusion的新檔案傳輸如何運作？

Fusion處理檔案時，會將較大的檔案新增到永久儲存體(S3儲存貯體或Azure Blob儲存體)。 當Fusion模組執行檔案動作（例如上傳或下載）時，Fusion會使用持續性儲存體中的檔案作為來源，而非使用中記憶體。

### 我可以使用不完整執行的大型檔案嗎？

是，Fusion支援大型檔案的不完整執行。 請注意，未完成的執行在組織大小上有所限制，應主動管理。

### 我可以透過任何聯結器使用較大的檔案嗎？

必須更新每個Fusion聯結器以支援較大的檔案。 支援的聯結器包括Workfront、HTTP和AEM Assets。 Fusion聯結器仍受Web服務支援的檔案大小限制。 檔案大小限制通常包含在下載和上傳檔案的Web服務端點的API檔案中。

### 這是否會影響作業？

否，模組執行的作業數量相同。

### Fusion的UI何時會更新以顯示檔案傳輸資料？

此功能已完成並部署至生產環境。

### 有哪些方法可考慮協助我設計情境的新檔案處理限制？

將情境設計成在40分鐘執行限制內運作似乎很複雜。 我們建議在設計情境時記住下列事項：

* **瞭解您的業務執行時間需求**： Fusion的執行時間平台限製為40分鐘，但大部分的業務程式自動化執行速度預計會快很多。 例如，以結果為根據的持續作業方式，使用者啟動的自動化作業預計會在40分鐘限制內順利完成。
* **在設計時考慮執行時間**：在設計您的情境時，必須瞭解個別檔案動作（例如上傳和下載）的模組執行時間。 此知識可協助您規劃涉及多個檔案動作的情境。  為了確保設計的正確性，我們建議將模組的執行時間四捨五入以包含緩衝區。
例如，如果Fusion在144秒（2.4分鐘）內下載檔案，您可以預期單一執行可以多次執行類似的動作。 在此範例中，模組執行需要144秒來執行，您應規劃下載3分鐘的執行時間。 如果您的需求包含上傳和下載，則預期執行時間將約為6分鐘。 請注意，Fusion執行時間上限為40分鐘。

* **合併檔案動作**： Fusion案例中最常見的檔案動作範例是下載一次和上傳。 大多數只有這兩個動作的情境會在幾分鐘內執行。 如有可能，Fusion設計人員應該將其案例限製為一次下載和一次上傳。

* **使用對應面板計算大小**： Workfront和其他網站服務在下載模組的輸出中包含檔案大小。 您可以使用此資料來篩選出檔案太大，而無法上傳模組或檔案太大，無法執行案例。

* **使用多個檔案時，將檔案動作隔離在自己的情境中**： Fusion Designers應考慮將檔案動作隔離到不同的情境中。 例如，含有多個附加檔案的新Workfront請求所觸發的Fusion情境可能需要容納最多30個檔案。 由於上傳和下載每個檔案最多可能需要3分鐘的時間，因此在一次執行中處理所有檔案將超過Fusion的40分鐘執行限制。 解決方案是建立檔案動作情境，專用於處理個別檔案的上傳和下載。 要求觸發的案例會逐一檢視附加檔案，並使用HTTP模組叫用每個檔案的檔案動作案例。 此方法可確保在執行時間限制內處理每個檔案。

<!--
## Connectors that do not support large files

Some Fusion connectors do not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.

The following connectors do **not** support large files. 

* Archive
* Box
* Convert
* CSV
* Datastores
* Flow control
* FTP
* JSON
* JWT
* Markdown
* Math
* Microsoft Word templates
* MIME
* Microsoft SQL
* SFTP
* Adobe Acrobat Sign
* SOAP
* Tools
* XML

If a connector is not on this list, it does not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.-->






<!--## Connectors that support large files

The following connectors support large files.

Workfront
HTTP
Webhooks
Salesforce
Microsoft Email
Workfront Proof
AEM Assets
Email
Slack
Jira
Microsoft Excel
SharePoint
Frame.io
Adobe PDF Services
Marketo
Azure Devops 
Google Email
Jira Server
Google Sheets
Microsoft OneDrive
ServiceNow 
AWS S3
Bynder
OneDrive Business
Adobe Authenticator
Google Drive
Microsoft Dynamics
Google Docs
NetSuite
Airtable
Azure AD
QuickBase 
Adobe Target
Adobe Campaign Classic
Microsoft Calendar
Workfront Planning
HubSpot CRM  
DropBox
Cloud Convert
Egnyte
Adobe Firefly
OpenAI / Chat GPT
Allocadia
Cvent
GitLab 
Google Team Drive
Google Calendar
Workfront SDL Managed Translation
Widen
Workfront Boards
Google Slides
Qualtrics
Microsoft Power BI
Adobe Photoshop
Anaplan
DocuSign 
MariaDB
Adobe Creative Cloud Libraries
Figma
AEM Forms
Datadog
GitHub 
Google Forms
Adobe I/O Events
Trello
Workday
Adobe Journey Optimizer
Adobe Lightroom


If a file is not on this list, it does not support large files. For these connectors, Fusion's total processing capacity for files is **1 GB**. 

This limit is based on a total memory cost. Every operation contributes to that cost. If a single file of 400 MB is downloaded and uploaded then the total cost to the file capacity would be 800 MB.

-->

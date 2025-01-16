---
title: FTP模組
description: FTP模組可讓您監視所選資料夾中的檔案變更、將新檔案上傳到所需的資料夾，以及修改或刪除資料夾中已存在的現有檔案。
author: Becky
feature: Workfront Fusion
exl-id: 1e14f778-ab8c-421f-a4b4-c57be66c7cad
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1117'
ht-degree: 0%

---

# FTP模組

FTP模組可讓您監視所選資料夾中的檔案變更、將新檔案上傳到所需的資料夾，以及修改或刪除資料夾中已存在的現有檔案。

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

## 先決條件

若要搭配[!DNL Workfront Fusion]使用[Fusion應用程式]，您必須擁有FTP帳戶。

## 在FTP模組中建立連線 {#create-a-connection}

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection name]</td> 
   <td> <p> 輸入FTP連線的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Host] </td> 
   <td> <p>輸入FTP伺服器主機名稱。 E.g. <code>myftp123.server.com</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Port] </td> 
   <td> <p>輸入FTP伺服器連線埠號碼。 E.g. <code>21</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL User name] </td> 
   <td> <p>輸入您的FTP帳戶使用者名稱。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Password] </td> 
   <td> <p>輸入您的FTP帳戶密碼。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>使用安全連線(TLS)</p> </td> 
   <td> <p>選取是否要使用安全連線。</p> <p style="font-weight: bold;">[!UICONTROL No]</p> <p>連線不安全。</p> <p style="font-weight: bold;">[!UICONTROL Explicit encryption or Implicit encryption]</p> <p>使用SSL來保護連線。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Reject unauthorized certificates]</p> </td> 
   <td> <p>啟用此選項以驗證FTP伺服器憑證。 如果驗證失敗，將不會建立連線。 若要通過驗證，憑證必須符合下列其中一個條件：</p> 
    <ul> 
     <li>由根<a href="https://en.wikipedia.org/wiki/Certificate_authority">憑證授權單位</a>簽署</li> 
     <li>由中繼憑證授權單位簽署（如<a href="https://knowledge.digicert.com/solution/SO16297.html">憑證鏈結如何運作</a>以取得進一步說明）。 在此情況下，所有中繼憑證都應安裝在FTP伺服器上。</li> 
     <li>是[!UICONTROL Self-signed certificate]欄位中提供的自我簽署憑證（請參閱下文）</li> </ul>

如果停用此選項，則不會驗證FTP伺服器憑證。 我們強烈建議不要停用此選項，因為它會導致連線不安全，並帶來嚴重的安全風險。</td>
</tr> 
  <tr> 
   <td> <p>[!UICONTROL Self-signed certificate]</p> </td> 
   <td> <p>按一下<b>[!UICONTROL Extract]</b>按鈕，開啟上傳對話方塊。</p> <p>上傳憑證以將TLS與您的自我簽署憑證搭配使用。 [!DNL Workfront Fusion]不會保留或儲存您提供的任何資料，例如檔案和密碼。 檔案和密碼僅用於擷取憑證。</p> </td> 
  </tr> 
 </tbody> 
</table>

## FTP模組及其欄位

* [觸發器](#triggers)
* [動作](#actions)

### 觸發器

#### [!UICONTROL Watch files]

[!UICONTROL Watch files]是FTP的唯一觸發程式模組。 它會監視所選資料夾的檔案內容。 將新檔案插入指定的資料夾時，就會執行觸發程式。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需建立與FTP帳戶連線的指示，請參閱本文中FTP模組</a>的<a href="#create-a-connection" class="MCXref xref">[!UICONTROL Create a connection]。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Folder]</p> </td> 
   <td> <p>選取要監視的資料夾。</p> <p><b>注意：</b>每個情境只允許一個資料夾。 子資料夾會被忽略。</p> <p><b>秘訣：</b>若要追蹤多個資料夾，請為每個資料夾建立獨立的案例。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files] </td> 
   <td> <p>設定[!DNL Workfront Fusion]在一個週期內可處理的最大結果數量。 如果該值設定得太高，則在指定的第三方服務端可能會中斷連線（逾時）。 [!DNL Workfront Fusion]對此沒有影響。 我們建議您設定較低的值，並為最大週期數定義較高的值，或是更頻繁地執行情境。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL Change permissions]](#change-permissions)
* [[!UICONTROL Create a folder]](#create-a-folder)
* [[!UICONTROL Delete a file]](#delete-a-file)
* [[!UICONTROL Delete a folder]](#delete-a-folder)
* [[!UICONTROL Get a file]](#get-a-file)
* [[!UICONTROL List of files in a folder]](#list-of-files-in-a-folder)
* [[!UICONTROL Move a file or folder]](#move-a-file-or-folder)
* [[!UICONTROL Upload]檔案](#upload-a-file)

#### [!UICONTROL Change permissions]

此動作模組會變更檔案或資料夾的許可權設定。

<table style="width: 100%;" class="TableStyle-TableStyle-List-options-in-steps" cellspacing="0">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1" />
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2" />
   <tbody>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">如需建立與FTP帳戶連線的指示，請參閱本文中FTP模組</a>的<a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection]。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-MediumGray" role="rowheader">[!UICONTROL Change permission settings of]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-MediumGray">
               <p>選取是否要變更檔案或資料夾的設定。</p>
            </td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL File path]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">輸入檔案路徑，或將檔案路徑對應至資料夾或檔案。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-MediumGray" role="rowheader">[!UICONTROL Permissions]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-MediumGray">
               <p>設定所需的檔案或資料夾許可權。 使用chmod引數。 例如： <code>777 </code>或<code>-rwxrwxrwx</code>。</p>
               <p>許可權必須符合模式<code> /(.?([r-][w-][x-]){3})|[0-7]{3,4}/</code>。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Create a folder]

此動作模組會建立新資料夾。

<table style="width: 100%;" class="TableStyle-TableStyle-List-options-in-steps" cellspacing="0">
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column1" />
   <col class="TableStyle-TableStyle-List-options-in-steps-Column-Column2" />
   <tbody>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-LightGray" role="rowheader">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">如需建立與FTP帳戶連線的指示，請參閱本文中FTP模組</a>的<a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection]。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-MediumGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyE-Column1-MediumGray" role="rowheader">[!UICONTROL Folder path]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-MediumGray">輸入檔案路徑，或將檔案路徑對應到新資料夾。</td>
         </tr>
         <tr class="TableStyle-TableStyle-List-options-in-steps-Body-LightGray">
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyB-Column1-LightGray" role="rowheader">[!UICONTROL New folder name]</td>
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyA-Column2-LightGray">
               <p>輸入或對應新資料夾的名稱。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Delete a file]

從指定的資料夾中刪除檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
            <td class="TableStyle-TableStyle-List-options-in-steps-BodyD-Column2-LightGray">如需建立與FTP帳戶連線的指示，請參閱本文中FTP模組</a>的<a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection]。</td>
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>選取要刪除檔案的FTP資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File name]</td> 
   <td> <p> 輸入檔案名稱，包括副檔名。 範例： <code>[!DNL image].png</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a folder]

此動作模組會永久刪除指定的資料夾。

<table style="width: 100%;" class="TableStyle-TableStyle-HeaderRow" cellspacing="15">
   <col style="width: 301px;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <col style="width: 50%;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <tbody>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-LightGray" style="font-weight: bold;">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-LightGray">如需建立與FTP帳戶連線的指示，請參閱本文中FTP模組</a>的<a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection]。</td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-MediumGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyB-Column1-MediumGray" style="font-weight: bold;">[!UICONTROL Folder]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyA-Column1-MediumGray">
               <p>選取要刪除檔案的FTP資料夾。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL Get a file]

從FTP伺服器擷取可進一步處理的檔案，例如上傳至[!DNL Dropbox]。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需建立與FTP帳戶連線的說明，請參閱本文中的<a href="#creating-the-ftp-connection" class="MCXref xref">建立FTP連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File path]</td> 
   <td> <p> 輸入您要取得的檔案路徑。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL List of files in a folder]

擷取檔案和/或資料夾資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需建立與FTP帳戶連線的說明，請參閱本文中的<a href="#creating-the-ftp-connection" class="MCXref xref">建立FTP連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>選取您要搜尋的FTP資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>選取您要擷取有關檔案或資料夾的資訊，或兩者。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>輸入搜尋字詞。 如果未輸入搜尋字詞，則會擷取指定資料夾中的所有檔案和資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> 設定此模組擷取的檔案數上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a file or folder]

此動作模組會將檔案或資料夾移至其他位置。

<table style="width: 100%;" class="TableStyle-TableStyle-HeaderRow" cellspacing="15">
   <col style="width: 301px;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <col style="width: 50%;" class="TableStyle-TableStyle-HeaderRow-Column-Column1" />
   <tbody>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-LightGray" style="font-weight: bold;">[!UICONTROL Connection]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-LightGray">如需建立與FTP帳戶連線的指示，請參閱本文中FTP模組</a>的<a href="#Create" class="MCXref xref" >[!UICONTROL Create a connection]。</td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-MediumGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyE-Column1-MediumGray" style="font-weight: bold;">[!UICONTROL Old file path]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyD-Column1-MediumGray">
               <p>輸入您要移動檔案的路徑。 範例： <code>/folder1/document.txt</code>。</p>
            </td>
         </tr>
         <tr class="TableStyle-TableStyle-HeaderRow-Body-LightGray">
            <td class="TableStyle-TableStyle-HeaderRow-BodyB-Column1-LightGray" style="font-weight: bold;">[!UICONTROL New file path]</td>
            <td class="TableStyle-TableStyle-HeaderRow-BodyA-Column1-LightGray">
               <p>輸入您要移動檔案的路徑。 範例： <code>/folder2/document.txt</code>。</p>
            </td>
         </tr>
   </tbody>
</table>


#### [!UICONTROL Upload a file]

將檔案上傳至FTP伺服器。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td>如需建立與FTP帳戶連線的說明，請參閱本文中的<a href="#creating-the-ftp-connection" class="MCXref xref">建立FTP連線</a>。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>選取您要上傳檔案的FTP資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source file] </td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Append to an already existing file]</td> 
   <td> <p>如果已啟用此選項，且FTP伺服器上已存在檔案，則檔案的內容會附加至現有檔案。 如果未啟用此選項，則會覆寫檔案的內容。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Create folders if don't exist] </td> 
   <td> <p>如果啟用此選項，而FTP伺服器上不存在您輸入到「資料夾」欄位的資料夾，則模組會建立該資料夾</p> </td> 
  </tr> 
 </tbody> 
</table>

## 疑難排解 {#troubleshooting}

如果您在建立連線或模組作業期間遇到FTP應用程式問題，請嘗試使用其中一個常用的FTP使用者端，並嘗試執行相同的動作（例如，建立連線或列出資料夾中的檔案）。 FTP使用者端。 如果您也遇到與FTP使用者端相同的問題，原因可能是FTP伺服器的設定錯誤。

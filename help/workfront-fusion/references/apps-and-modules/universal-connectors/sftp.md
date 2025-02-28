---
title: sftp模組
description: ' [!DNL Adobe Workfront Fusion SFTP] 模組可讓您監視選取的資料夾/子資料夾中的檔案變更、將新檔案上傳到所需的資料夾、修改或刪除資料夾中現有的檔案，或變更檔案許可權。'
author: Becky
feature: Workfront Fusion
exl-id: bde3cbda-8a19-4d9f-b970-f56d73a1f8dd
source-git-commit: 77ec3c007ce7c49ff760145fafcd7f62b273a18f
workflow-type: tm+mt
source-wordcount: '1688'
ht-degree: 0%

---

# sftp模組

[!DNL Adobe Workfront Fusion] SFTP模組可讓您監視選取的資料夾/子資料夾中的檔案變更、將新檔案上傳到所需的資料夾、修改或刪除資料夾中現有的檔案，或變更檔案許可權。

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

若要搭配[!DNL Workfront Fusion]使用SFTP，您必須擁有SFTP帳戶（例如[!DNL GoDaddy]網站託管）。

## 將SFTP連線至[!DNL Workfront Fusion] {#connect-sftp-to-workfront-fusion}

若要將您的SFTP帳戶連線至[!DNL Workfront Fusion]，您必須輸入目標主機，以及模組[!UICONTROL Create a connection]對話方塊的SFTP認證（使用者名稱和密碼或使用者名稱和金鑰）。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">[!UICONTROL Connection name]</td> 
   <td> <p> 輸入SFTP連線的名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Host]</p> </td> 
   <td> <p>輸入您要連線之SFTP伺服器的主機名稱。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">[!UICONTROL Port] </td> 
   <td> <p>輸入SFTP伺服器連線埠。 例如， 22。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>[!UICONTROL Auth type]</p> </td> 
   <td> <p>選取您要用來連線至SFTP伺服器的授權方法。</p> 
    <ul> 
     <li><strong>[!UICONTROL User name and password]</strong>：輸入您的認證。</li> 
     <li> <p><strong>[!UICONTROL User name and key]</strong>：輸入您的使用者名稱和私密金鑰/憑證</p> <p>如果您想要使用自我簽署憑證的TLS，請上傳私密金鑰以使用使用者端授權，或上傳您的憑證（P12或PFX檔案）。 如果您使用使用者端憑證授權，可以在這裡輸入您的CA憑證。</p> <p>[!DNL Workfront Fusion] 不會保留或儲存您在這裡提供的任何資料（檔案、密碼）。 檔案和密碼僅用於擷取私密金鑰/憑證。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

輸入連線資訊後，按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立連線。

## [!UICONTROL SFTP]模組及其欄位

當您設定[!UICONTROL SFTP]模組時，[!DNL Workfront Fusion]會顯示下列欄位。 除了這些欄位以外，可能還會顯示其他[!UICONTROL SFTP]欄位，視您在應用程式或服務中的存取層級等因素而定。 模組中的粗體標題表示必填欄位。

如果您在欄位或函式上方看到對應按鈕，則可以使用它來設定該欄位的變數和函式。 如需詳細資訊，請參閱[將資訊從一個模組對應到另一個模組](/help/workfront-fusion/create-scenarios/map-data/map-data-from-one-to-another.md)。

![地圖切換](/help/workfront-fusion/references/apps-and-modules/assets/map-toggle-350x74.png)

### 觸發器

#### [!UICONTROL Watch Files in a Folder]

在指定的資料夾中建立或變更檔案時，傳回包含詳細資訊的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>輸入或對應您要觀看的資料夾。 您可以指定絕對路徑，例如<code>/home/user/</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>緩衝區大小[B]</td> 
   <td> <p> 輸入緩衝區大小（位元組）。 值會定義從伺服器傳輸之區塊的大小。 值太高時，有些伺服器可能會造成問題或檔案損毀。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> 設定[!DNL Workfront Fusion]在一個週期內可處理的最大檔案數</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Watch Subfolders in a Folder]

在指定的資料夾中建立或變更資料夾時，傳回包含詳細資訊的資料夾。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td> 
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>輸入或對應您要觀看的資料夾。 您可以指定絕對路徑，例如<code>/home/user/</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned files]</td> 
   <td> <p> 設定[!DNL Workfront Fusion]在一個週期內傳回的資料夾數目上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

#### [!UICONTROL List a folder's content]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Show] </td> 
   <td> <p>選取您要擷取檔案、資料夾或兩者。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>輸入或對應包含您要列出之檔案或資料夾的資料夾。 您可以指定絕對路徑，例如<code>/home/user/</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>輸入或對映搜尋字詞。 例如，如果您要搜尋副檔名為.txt的檔案，請輸入<code>.txt</code>。您也可以輸入或對應您要搜尋的檔案名稱。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> 選取是否要依檔案名稱、大小、上次存取日期或上次修改日期來排序結果。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order] </td> 
   <td> <p>選取結果應依遞增或遞減順序傳回。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>啟用此選項以確保此模組不會在未傳回任何結果時停止案例。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p> 設定[!DNL Workfront Fusion]在一個週期內傳回的結果數目上限。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get Files]

此模組會列出指定資料夾中的檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> 輸入緩衝區大小（位元組）。 值會定義從伺服器傳輸之區塊的大小。 值太高時，有些伺服器可能會造成問題或檔案損毀。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>輸入或對應包含您要列出之檔案或資料夾的資料夾。 您可以指定絕對路徑，例如<code>/home/user/</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Search] </td> 
   <td> <p>輸入或對映搜尋字詞。 例如，如果您要搜尋副檔名為.txt的檔案，請輸入<code>.txt</code>。您也可以輸入或對應您要搜尋的檔案名稱。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort By]</td> 
   <td> <p> 選取是否要依檔案名稱、大小、上次存取日期或上次修改日期來排序結果。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Sort Order]</td> 
   <td> <p> 選取結果應依遞增或遞減順序傳回。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Continue the execution of the route even if the module returns no results]</p> </td> 
   <td>啟用此選項以確保此模組不會在未傳回任何結果時停止案例。</td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Maximum number of returned results]</td> 
   <td> <p> 設定[!DNL Workfront Fusion]在一個週期內傳回的最大檔案數。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Get a File]

此模組會擷取檔案詳細資料，包括檔案的資料。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Buffer Size [B]]</td> 
   <td> <p> 輸入緩衝區大小（位元組）。 值會定義從伺服器傳輸之區塊的大小。 值太高時，有些伺服器可能會造成問題或檔案損毀。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path] </td> 
   <td> <p>輸入檔案的路徑。 您可以指定絕對路徑，例如<code>/home/user/file.txt</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如<code>./file.txt</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Upload a File]

此模組可讓您將檔案上傳至SFTP伺服器。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>指定現有的資料夾作為檔案的儲存位置。 您可以指定絕對路徑，例如<code>/home/user/</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如 <code>./.</code></p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Source File]</td> 
   <td> <p> 從先前的模組（例如[!UICONTROL Dropbox] &gt; [!UICONTROL Get File]）對應來源檔案。 您也可以輸入或對應檔案名稱和檔案資料。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>為檔案或資料夾設定所需的許可權。 使用chmod引數。 例如： <code>777 </code>或<code>-rwxrwxrwx</code>。</p> <p>如需有關chmod的詳細資訊，請參閱<a href="https://ss64.com/bash/chmod.html">chmod檔案</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Rename a File]

重新命名檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 輸入要重新命名的檔案路徑。 您可以指定絕對路徑，例如<code>/home/user/file.txt</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如<code>./file.txt</code>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New file name]</td> 
   <td> <p> 輸入檔案的新名稱，包括副檔名。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Move a File]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 輸入要移動的檔案路徑。 您可以指定絕對路徑，例如<code>/home/user/file.txt</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如<code>./file.txt</code>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL New Folder]</td> 
   <td> <p> 輸入檔案新位置的路徑。 您可以指定絕對路徑，例如<code>/home/user/</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如 <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a File]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 輸入您要刪除的檔案路徑。 您可以指定絕對路徑，例如<code>/home/user/file.txt</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如<code>./file.txt</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Update file permissions]

可讓您變更檔案的許可權。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL File Path]</td> 
   <td> <p> 輸入要移動的檔案路徑。 您可以指定絕對路徑，例如<code>/home/user/file.txt</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如<code>./file.txt</code>。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>設定所需的檔案許可權。 使用chmod引數。 例如，<code>777 </code>或<code>-rwxrwxrwx</code>。</p> <p>必須符合模式 <code> /(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>如需有關chmod的詳細資訊，請參閱<a href="https://ss64.com/bash/chmod.html">chmod檔案</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Create Folder]

在指定位置中建立新資料夾。

>[!NOTE]
>
>如果資料夾已經存在，模組將會擲回錯誤。 若要繼續流而不中斷，請將錯誤處理常式路由附加到模組以擷取錯誤，並使用[!UICONTROL Resume]指示詞來繼續流。 如需有關附加錯誤處理常式路由的資訊，請參閱 [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/create-scenarios/config-error-handling/error-handling.md)中的[錯誤處理。 如需有關錯誤處理常式路由的資訊，請參閱 [!DNL Adobe Workfront Fusion]](/help/workfront-fusion/references/errors/directives-for-error-handling.md)中錯誤處理的[指示。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder] </td> 
   <td> <p>指定現有資料夾作為新資料夾的儲存位置。 您可以指定絕對路徑，例如<code>/home/user/file.txt</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如<code>./</code>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!UICONTROL Folder Name]</td> 
   <td> <p> 輸入資料夾名稱。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[!UICONTROL Permissions]</p> </td> 
   <td> <p>設定所需的檔案夾許可權。 使用chmod引數。 例如，<code>777 </code>或<code>-rwxrwxrwx</code>。</p> <p>必須符合模式 <code>/(.?([r-][w-][x-]){3})|[0-7]{3}/.</code></p> <p>如需chmod的詳細資訊，請參閱<a href="https://ss64.com/bash/chmod.html">chmod線上手冊</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL Delete a Folder]

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[!UICONTROL Connection] </td>
   <td> <p>如需有關將SFTP帳戶連線至[!DNL Workfront Fusion]的說明，請參閱本文中的<a href="#connect-sftp-to-workfront-fusion" class="MCXref xref">將SFTP連線至[!DNL Workfront Fusion]</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[!DNL Folder Path]</td> 
   <td> <p> 指定您要刪除的資料夾路徑。 您可以指定絕對路徑，例如<code>/home/user/</code>。 或者，您可以指定指向登入使用者之特定資料夾的相對路徑，例如 <code>./.</code></p> </td> 
  </tr> 
 </tbody> 
</table>

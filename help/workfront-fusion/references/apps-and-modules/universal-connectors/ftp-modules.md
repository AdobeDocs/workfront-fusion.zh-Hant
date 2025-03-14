---
title: FTP模組
description: FTP模組可讓您監視所選資料夾中的檔案變更、將新檔案上傳到所需的資料夾，以及修改或刪除資料夾中已存在的現有檔案。
author: Becky
feature: Workfront Fusion
exl-id: 1e14f778-ab8c-421f-a4b4-c57be66c7cad
source-git-commit: ec2388ab509e89aec71278210bc4ab6f55ed38fd
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 0%

---

# FTP模組

FTP模組可讓您監視所選資料夾中的檔案變更、將新檔案上傳到所需的資料夾，以及修改或刪除資料夾中已存在的現有檔案。

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
   <p>目前：無Workfront Fusion授權需求</p>
   <p>或</p>
   <p>舊版：Workfront Fusion for Work Automation and Integration </p>
   </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>新增：</p> <ul><li>選取或Prime Workfront套件：您的組織必須購買Adobe Workfront Fusion。</li><li>Ultimate Workfront套件：包含Workfront Fusion。</li></ul>
   <p>或</p>
   <p>目前：您的組織必須購買Adobe Workfront Fusion。</p>
   </td> 
  </tr>
 </tbody> 
</table>

如需此表格中資訊的詳細資訊，請參閱檔案](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)中的[存取需求。

如需[!DNL Adobe Workfront Fusion]授權的相關資訊，請參閱[[!DNL Adobe Workfront Fusion] 授權](/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/license-automation-vs-integration.md)。

+++

## 先決條件

若要使用FTP模組，您必須擁有具有FTP服務的帳戶。

## 在FTP模組中建立連線 {#create-a-connection}

1. 在任何FTP模組中，按一下連線方塊旁的&#x200B;**新增**。
1. 填寫下列欄位。

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td>[！UICONTROL連線名稱]</td> 
      <td> <p> 輸入FTP連線的名稱。</p> </td> 
     </tr> 
     <tr> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL環境]</p> </td> 
      <td> <p>選取您使用生產或非生產環境。</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader"> <p>[！UICONTROL型別]</p> </td> 
      <td> <p>選取您是使用服務帳戶還是個人帳戶。</p> </td> 
     </tr> 
     <tr> 
      <td>[！UICONTROL主機] </td> 
      <td> <p>輸入FTP伺服器主機名稱。 範例： <code>myftp123.server.com</code></p> </td> 
     </tr> 
     <tr> 
      <td>[！UICONTROL連線埠] </td> 
      <td> <p>輸入FTP伺服器連線埠號碼。 範例： <code>21</code></p> </td> 
     </tr> 
     <tr> 
      <td>[！UICONTROL使用者名稱] </td> 
      <td> <p>輸入您的FTP帳戶使用者名稱。</p> </td> 
     </tr> 
     <tr> 
      <td>[！UICONTROL密碼] </td> 
      <td> <p>輸入您的FTP帳戶密碼。</p> </td> 
     </tr> 
     <tr> 
      <td> <p>使用安全連線(TLS)</p> </td> 
      <td> <p>選取是否要使用安全連線。</p> <ul><li><p><b>[！UICONTROL否]</b></p> <p>連線不安全。</p></li><li> <p><b>明確加密</b>或<b>隱含加密</b></p> <p>使用SSL來保護連線。</p> </td> 
     </tr> 
    <tr> 
   <td> <p>[！UICONTROL拒絕未授權的憑證]</p> </td> 
   <td> <p>啟用此選項以驗證FTP伺服器憑證。 如果驗證失敗，將不會建立連線。 若要通過驗證，憑證必須符合下列其中一個條件：</p> 
    <ul> 
     <li>由根憑證授權單位簽署</a></li> 
     <li>由中繼憑證授權單位簽署。 在此情況下，所有中繼憑證都應安裝在FTP伺服器上。</li> 
     <li>是[！UICONTROL Self-signed certificate]欄位中提供的自我簽署憑證（請參閱下文）</li> </ul>
     <p>如果停用此選項，則不會驗證FTP伺服器憑證。 我們強烈建議不要停用此選項，因為它會導致連線不安全，並帶來嚴重的安全風險。</p></td>
    </tr> 
    <tr> 
     <td> <p>[！UICONTROL自我簽署憑證]</p> </td> 
     <td> <p>按一下<b>[！UICONTROL Extract]</b>按鈕，開啟上傳對話方塊。</p> <p>上傳憑證以將TLS與您的自我簽署憑證搭配使用。 [!DNL Workfront Fusion]不會保留或儲存您提供的任何資料，例如檔案和密碼。 檔案和密碼僅用於擷取憑證。</p> </td> 
    </tr> 
   </tbody> 
   </table>

1. 按一下&#x200B;**[!UICONTROL 繼續]**&#x200B;以儲存連線並返回模組。

## FTP模組及其欄位

* [觸發程序](#triggers)
* [動作](#actions)

### 觸發程序

#### [!UICONTROL 觀看檔案]

[!UICONTROL 觀看檔案]是FTP的唯一觸發模組。 它會監視所選資料夾的檔案內容。 將新檔案新增至指定的資料夾時，就會執行觸發器。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL Connection] </td> 
   <td> <p>如需建立與FTP帳戶連線的指示，請參閱本文的FTP模組</a>中的<a href="#create-a-connection" class="MCXref xref">[！UICONTROL建立連線]。</p> </td> 
  </tr> 
  <tr> 
   <td> <p>[！UICONTROL資料夾]</p> </td> 
   <td> <p>選取要監視的資料夾。</p> <p><b>注意：</b>每個情境只允許一個資料夾。 子資料夾會被忽略。</p> <p><b>提示：</b>若要觀看多個資料夾，請為每個資料夾建立個別的情境。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL傳回檔案的最大數量] </td> 
   <td> <p>設定在一個週期內要模組使用的最大結果數量。 如果值設定得太高，FTP伺服器端的連線可能會中斷。 [!DNL Workfront Fusion]對此沒有影響。 我們建議您設定較低的值，並為最大週期數定義較高的值，或是更頻繁地執行情境。</p> </td> 
  </tr> 
 </tbody> 
</table>

### 動作

* [[!UICONTROL 變更許可權]](#change-permissions)
* [[!UICONTROL 建立資料夾]](#create-a-folder)
* [[!UICONTROL 刪除檔案]](#delete-a-file)
* [[!UICONTROL 刪除資料夾]](#delete-a-folder)
* [[!UICONTROL 取得檔案]](#get-a-file)
* [[!UICONTROL 資料夾中的檔案清單]](#list-of-files-in-a-folder)
* [[!UICONTROL 移動檔案或資料夾]](#move-a-file-or-folder)
* [[!UICONTROL 上傳]檔案](#upload-a-file)

#### [!UICONTROL 變更許可權]

此動作模組會變更檔案或資料夾的許可權設定。

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[！UICONTROL Connection]</td>
            <td>如需建立與FTP帳戶連線的指示，請參閱本文的FTP模組</a>中的<a href="#Create" class="MCXref xref" >[！UICONTROL建立連線]。</td>
         </tr>
         <tr>
            <td>[！UICONTROL變更許可權設定]</td>
            <td>
               <p>選取是否要變更檔案或資料夾的設定。</p>
            </td>
         </tr>
         <tr>
            <td>[！UICONTROL檔案路徑]</td>
            <td>輸入檔案路徑，或將檔案路徑對應至資料夾或檔案。</td>
         </tr>
         <tr>
            <td>[！UICONTROL Permissions]</td>
            <td>
               <p>設定所需的檔案或資料夾許可權。 使用chmod引數。 例如： <code>777 </code>或<code>-rwxrwxrwx</code>。</p>
               <p>許可權必須符合模式<code> /(.?([r-][w-][x-]){3})|[0-7]{3,4}/</code>。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL 建立資料夾]

此動作模組會建立新資料夾。

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[！UICONTROL Connection]</td>
            <td>如需建立與FTP帳戶連線的指示，請參閱本文的FTP模組</a>中的<a href="#Create" class="MCXref xref" >[！UICONTROL建立連線]。</td>
         </tr>
         <tr>
            <td>[！UICONTROL資料夾路徑]</td>
            <td>輸入檔案路徑，或將檔案路徑對應到新資料夾。</td>
         </tr>
         <tr>
            <td>[！UICONTROL新資料夾名稱]</td>
            <td>
               <p>輸入或對應新資料夾的名稱。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL 刪除檔案]

此動作模組會從指定的資料夾中刪除檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL Connection] </td> 
            <td>如需建立與FTP帳戶連線的指示，請參閱本文的FTP模組</a>中的<a href="#Create" class="MCXref xref" >[！UICONTROL建立連線]。</td>
  </tr> 
  <tr> 
   <td>[！UICONTROL資料夾] </td> 
   <td> <p>選取要刪除檔案的FTP資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL檔案名稱]</td> 
   <td> <p> 輸入檔案名稱，包括副檔名。 範例： <code>[!DNL image].png</code></p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 刪除資料夾]

此動作模組會永久刪除指定的資料夾。

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[！UICONTROL Connection]</td>
            <td>如需建立與FTP帳戶連線的指示，請參閱本文的FTP模組</a>中的<a href="#Create" class="MCXref xref" >[！UICONTROL建立連線]。</td>
         </tr>
         <tr>
            <td>[！UICONTROL資料夾]</td>
            <td>
               <p>選取要刪除檔案的FTP資料夾。</p>
            </td>
         </tr>
   </tbody>
</table>

#### [!UICONTROL 取得檔案]

此動作模組會從FTP伺服器擷取檔案。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL Connection] </td> 
   <td> <p>如需建立與FTP帳戶連線的說明，請參閱本文中的<a href="#creating-the-ftp-connection" class="MCXref xref">建立FTP連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL檔案路徑]</td> 
   <td> <p> 輸入您要取得的檔案路徑。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 資料夾中的檔案清單]

此動作模組會擷取檔案和/或資料夾資訊。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL Connection] </td> 
   <td> <p>如需建立與FTP帳戶連線的說明，請參閱本文中的<a href="#creating-the-ftp-connection" class="MCXref xref">建立FTP連線</a>。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL資料夾] </td> 
   <td> <p>選取您要搜尋的FTP資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Show] </td> 
   <td> <p>選取您要擷取有關檔案或資料夾的資訊，或兩者。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL搜尋] </td> 
   <td> <p>輸入搜尋字詞。 如果未輸入搜尋字詞，則會擷取指定資料夾中的所有檔案或資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL傳回檔案的最大數量]</td> 
   <td> <p>輸入或對應您希望模組在一個週期內使用的最大結果數量。</p> </td> 
  </tr> 
 </tbody> 
</table>

#### [!UICONTROL 移動檔案或資料夾]

此動作模組會將檔案或資料夾移至其他位置。

<table>
   <col>
   <col>
   <tbody>
         <tr>
            <td>[！UICONTROL Connection]</td>
            <td>如需建立與FTP帳戶連線的指示，請參閱本文的FTP模組</a>中的<a href="#Create" class="MCXref xref" >[！UICONTROL建立連線]。</td>
         </tr>
         <tr>
            <td>[！UICONTROL舊檔案路徑]</td>
            <td>
               <p>輸入您要移動檔案的路徑。 範例： <code>/folder1/document.txt</code>。</p>
            </td>
         </tr>
         <tr>
            <td>[！UICONTROL新檔案路徑]</td>
            <td>
               <p>輸入您要移動檔案的路徑。 範例： <code>/folder2/document.txt</code>。</p>
            </td>
         </tr>
   </tbody>
</table>


#### [!UICONTROL 上傳檔案]

將檔案上傳至FTP伺服器。

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td>[！UICONTROL Connection] </td> 
   <td>如需建立與FTP帳戶連線的說明，請參閱本文中的<a href="#creating-the-ftp-connection" class="MCXref xref">建立FTP連線</a>。</td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL資料夾] </td> 
   <td> <p>選取您要上傳檔案的FTP資料夾。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL Source檔案] </td> 
   <td> <p>從先前的模組中選取來源檔案，或對應來源檔案的名稱和資料。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL附加至現有的檔案]</td> 
   <td> <p>如果已啟用此選項，且FTP伺服器上已存在檔案，則檔案的內容會附加至現有檔案。 如果未啟用此選項，則會覆寫檔案的內容。</p> </td> 
  </tr> 
  <tr> 
   <td>[！UICONTROL建立資料夾（如果不存在的話）] </td> 
   <td> <p>如果啟用此選項，而FTP伺服器上不存在您輸入到「資料夾」欄位的資料夾，則模組會建立該資料夾</p> </td> 
  </tr> 
 </tbody> 
</table>

## 疑難排解 {#troubleshooting}

如果您在建立連線或模組作業期間遇到FTP應用程式問題，請嘗試使用其中一個常用的FTP使用者端，並嘗試執行相同的動作（例如，建立連線或列出資料夾中的檔案）。 FTP使用者端。 如果您也遇到與FTP使用者端相同的問題，原因可能是FTP伺服器的設定錯誤。

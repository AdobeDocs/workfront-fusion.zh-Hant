---
title: 加密程式
description: Adobe Workfront Fusion Encryptor模組可讓您加密任何文字資料。 目前支援透過AES256和PGP (OpenPGP)進行訊息加密。
author: Becky
feature: Workfront Fusion
exl-id: 4b119efe-6762-445e-bbc7-c59437fd5060
source-git-commit: 0689cfee7cf546a6c1f5f72c79a1e7be9df85a8c
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 0%

---

# 加密程式

[!DNL Adobe Workfront Fusion] [!UICONTROL 加密程式]模組可讓您加密任何文字資料。 它們目前支援透過AES256和PGP ([!UICONTROL OpenPGP])進行訊息加密。

這些模組需要熟悉加密流程。

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
   <p>不需要Workfront Fusion授權。</p>
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

## 使用PGP的訊息加密與解密

透過PGP加密和解密時，必須使用金鑰鏈並建立私密或公開金鑰（或兩者）。

如需公開和私密金鑰的詳細資訊，請參閱[Adobe Workfront Fusion字彙表](/help/workfront-fusion/get-started-with-fusion/understand-fusion/fusion-glossary.md)。

如需金鑰的詳細資訊，請參閱[金鑰](/help/workfront-fusion/references/modules/keys.md)。

## [!UICONTROL 加密程式]模組及其欄位

當您設定[!UICONTROL 加密程式]模組時，會顯示下列欄位。 模組中的粗體標題表示必填欄位。

### AES解密（進階）

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL Key]</td>
        <td>選取您希望模組使用的金鑰。 若要建立金鑰，請按一下<b>新增</b>，然後輸入金鑰的名稱、金鑰和編碼型別。</td>
    </tr>
    <tr>
        <td>位元</td>
        <td>選取您希望模組使用128位元或256位元加密。</td>
    </tr>
    <tr>
        <td>輸入編碼</td>
        <td>選取您要使用的輸入編碼型別：
        <ul>
        <li>二進位</li>
        <li>以64為底</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>資料</td>
        <td>輸入或對應您要解密的資料。</td>
    </tr>
    <tr>
        <td>輸出編碼</td>
        <td>選取您要使用的輸出編碼型別：
        <ul>
        <li>ASCII</li>
        <li>二進位</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>加密演演算法</td>
        <td>選取要使用的加密演演算法：
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>初始化向量編碼</td>
        <td>選取您要使用的初始化向量編碼：
        <ul>
        <li>UTF-8</li>
        <li>二進位</li>
        <li>以64為底</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>驗證標籤編碼</td>
        <td>選取您要使用的驗證標籤編碼：
        <ul>
        <li>UTF-8</li>
        <li>二進位</li>
        <li>以64為底</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
</table>

### AES解密（簡單）

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL Key]</td>
        <td>選取您希望模組使用的金鑰。 若要建立金鑰，請按一下<b>新增</b>，然後輸入金鑰的名稱、金鑰和編碼型別。</td>
    </tr>
   <tr>
        <td>輸入編碼</td>
        <td>選取您要使用的輸入編碼型別：
        <ul>
        <li>二進位</li>
        <li>以64為底</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>資料</td>
        <td>輸入或對應您要解密的資料。</td>
    </tr>
    <tr>
        <td>輸出編碼</td>
        <td>選取您要使用的輸出編碼型別：
        <ul>
        <li>ASCII</li>
        <li>二進位</li>
        <li>UTF-8</li>
        </ul>
        </td>
     </tr>
    <tr>
        <td>秘密金鑰</td>
        <td>輸入或對應您要使用的秘密金鑰。</td>
    </tr>
</table>

### AES加密（進階）

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL Key]</td>
        <td>選取您希望模組使用的金鑰。 若要建立金鑰，請按一下<b>新增</b>，然後輸入金鑰的名稱、金鑰和編碼型別。</td>
    </tr>
    <tr>
        <td>位元</td>
        <td>選取您希望模組使用128位元或256位元加密。</td>
    </tr>
    <tr>
        <td>輸入編碼</td>
        <td>選取您要使用的輸入編碼型別：
        <ul>
        <li>二進位</li>
        <li>ASCII</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>資料</td>
        <td>輸入或對應您要加密的資料。</td>
    </tr>
    <tr>
        <td>輸出編碼</td>
        <td>選取您要使用的輸出編碼型別：
        <ul>
        <li>ASCII</li>
        <li>二進位</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>加密演演算法</td>
        <td>選取要使用的加密演演算法：
        <ul>
        <li>CBC</li>
        <li>GCM</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>初始化向量編碼</td>
        <td>選取您要使用的驗證標籤編碼：
        <ul>
        <li>UTF-8</li>
        <li>二進位</li>
        <li>以64為底</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
</table>

### AES加密（簡單）

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL Key]</td>
        <td>選取您希望模組使用的金鑰。 若要建立金鑰，請按一下<b>新增</b>，然後輸入金鑰的名稱、金鑰和編碼型別。</td>
    </tr>
   <tr>
        <td>輸入編碼</td>
        <td>選取您要使用的輸入編碼型別：
        <ul>
        <li>二進位</li>
        <li>ASCII</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>資料</td>
        <td>輸入或對應您要加密的資料。</td>
    </tr>
    <tr>
        <td>輸出編碼</td>
        <td>選取您要使用的輸出編碼型別：
        <ul>
        <li>以64為底</li>
        <li>二進位</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>秘密金鑰</td>
        <td>輸入或對應您要使用的秘密金鑰。</td>
    </tr>
</table>


### 建立數位簽名

此模組可讓您使用公開和私密金鑰解密訊息。

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL私密金鑰]</td>
        <td>選取要用於此簽章的私密金鑰。 若要新增私密金鑰，請按一下[新增] <b></b>，然後輸入金鑰的名稱、金鑰文字和複雜密碼。</td>
    </tr>
    <tr>
        <td>演演算法 </td>
        <td>選取您要使用RSA-SHA1或RSA-SHA256。 </td>
    </tr>
   <tr>
        <td>輸入編碼</td>
        <td>選取您要使用的輸入編碼型別：
        <ul>
        <li>ASCII</li>
        <li>二進位</li>
        <li>UTF-8</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>輸出編碼</td>
        <td>選取您要使用的輸出編碼型別：
        <ul>
        <li>以64為底</li>
        <li>十六進位</li>
        </ul>
        </td>
    </tr>
    <tr>
        <td>資料</td>
        <td>輸入或對應您要建立簽章的資料。</td>
    </tr>
</table>

### 解密PGP訊息

此模組可讓您使用公開和私密金鑰解密訊息。

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL私密金鑰]</td>
        <td>選取要用於此郵件的收件者私密金鑰。 若要新增私密金鑰，請按一下[新增] <b></b>，然後輸入金鑰的名稱、金鑰文字和複雜密碼。</td>
    </tr>
    <tr>
        <td>[！UICONTROL公開金鑰]</td>
        <td>輸入寄件者的公開金鑰。 這可以驗證寄件者的身分。</td>
    </tr>
    <tr>
        <td>[！UICONTROL訊息]</td>
        <td>對應您要解密的訊息。</td>
    </tr>
</table>

### 加密PGP訊息

此模組可讓您使用公開和私密金鑰來加密訊息。

<table style="table-layout:auto">
    <tr>
        <td>[！UICONTROL私密金鑰]</td>
        <td>輸入寄件者的私密金鑰。 這可以驗證寄件者的身分。</td>
    </tr>
    <tr>
        <td>[！UICONTROL公開金鑰]</td>
        <td>輸入收件者的公開金鑰。</td>
    </tr>
    <tr>
        <td>[！UICONTROL訊息]</td>
        <td>輸入您要加密的訊息。</td>
    </tr>
    </table>

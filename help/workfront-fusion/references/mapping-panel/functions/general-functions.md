---
title: 一般函式
description: Adobe Workfront Fusion對應面板中有以下一般函式。
author: Becky
feature: Workfront Fusion
exl-id: 6d4b8801-aa7e-47d4-80b3-aceac10c073f
source-git-commit: 295004ab7536b85124bc366d6832c08365338d08
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# 一般函式

## 變數

有兩個一般變數可用來識別執行的詳細資訊：

* `executionID`：此案例執行的識別碼
* `triggerTimestamp`：觸發此執行的時間

## [!UICONTROL get （物件或陣列；路徑）]

傳回物件或陣列的值路徑。 若要存取巢狀物件，請使用點標籤法。 陣列中的第一個專案是索引1。

>[!BEGINSHADEBOX]

**範例：**

* `get( array ; 1 + 1 )`
* `get( array ; 5.raw_name )`
* `get( object ; raw_name )`
* `get( object ; raw_name.sub_raw_name )`

>[!ENDSHADEBOX]

## [!UICONTROL if （運算式；值1；值2）]

如果運算式評估為true，則傳回`value1`；否則會傳回`value2`。

若要建立if陳述式（只有在兩個或多個運算式被評估為true時才傳回值），請使用`and`關鍵字。

若要合併`if`陳述式，請使用`and`和`or`運運算元。

![和運運算元](assets/and-in-if-statement.png)

>[!BEGINSHADEBOX]

**範例：**

* `if( 1 = 1 ; A ; B )`

  傳回

* `if( 1 = 2 ; A ; B )`

  傳回B

* `if( 1 = 2 and 1 = 2 ; A ; B )`

  傳回B

>[!ENDSHADEBOX]

## [!UICONTROL imfempty (value1； value2)]

如果此值不是空的，則傳回`value1`；否則會傳回`value2`。

>[!BEGINSHADEBOX]

**範例：**

* `ifempty(` `A` `;` `B`

  傳回

* `ifempty(` `unknown` `;` `B`

  傳回B

* `ifempty(` `""` `;` `B`

  傳回B

>[!ENDSHADEBOX]

## [!UICONTROL switch （運算式； value1； result1； [value2； result2； ...]； [else]）]

根據值清單評估一個值（稱為運算式）；傳回對應至第一個相符值的結果。 若要包含`else`值，請將其新增到最終運算式或值之後。

>[!BEGINSHADEBOX]

**範例：**

* `switch( B ; A ; 1 ; B ; 2 ; C ; 3 )`

  傳回2

* `switch( C ; A ; 1 ; B ; 2 ; C ; 3 )`

  傳回3

* `switch( X ; A ; 1 ; B ; 2 ; C ; 3 ; 4 )`

  傳回4

  在此函式中，4是在未套用運算式時傳回的值（`else`值）。

>[!ENDSHADEBOX]

## [!UICONTROL 省略（物件；key1； [key2； ...]）]

省略物件的指定索引鍵並傳回其餘索引鍵。

>[!BEGINSHADEBOX]

**範例：**

`omit(`使用者`;`密碼`)`

傳回使用者資訊（不包括密碼）的集合。

>[!ENDSHADEBOX]

## [!UICONTROL pick（物件；key1； [key2； ...]）]

僅從物件中挑選指定的索引鍵。

>[!BEGINSHADEBOX]

**範例：**

`pick(`使用者`;`密碼`;`電子郵件`)`

只傳回使用者密碼和電子郵件地址的集合。

>[!ENDSHADEBOX]

## mergeCollections(collection1； collection2)

結合兩個集合的機碼值組以將其合併。 如果兩個集合包含相同的索引鍵，則第二個集合的值會覆寫第一個集合的值。

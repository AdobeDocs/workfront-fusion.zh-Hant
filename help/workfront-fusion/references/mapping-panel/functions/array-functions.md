---
title: 陣列函式
description: 下列陣列函式可在Adobe Workfront Fusion對應面板中使用。
author: Becky
feature: Workfront Fusion
exl-id: 16c3915c-add1-4aab-a0e1-75fc590c42a6
source-git-commit: 2c732659f3f3e81e13b7b12a5df5bde19c0e0928
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# 陣列函式

## [!UICONTROL join (array; separator)]

在每個專案之間使用指定的分隔符號，將陣列中的所有專案串連到字串中。

## [!UICONTROL length (array)]

傳回陣列中的專案數。

## [!UICONTROL keys (object)]

傳回給定物件或陣列屬性的陣列。

## [!UICONTROL slice (array; start; [end])]

傳回僅包含所選專案的新陣列。

## [!UICONTROL merge (array1; array2; ...)]

將一個或多個陣列合併到一個陣列中。

## [!UICONTROL contains (array; value)]

驗證陣列是否包含值。

## [!UICONTROL remove (array; value1; value2; ...)]

移除陣列引數中指定的值。 此函式僅對文字或數字的原始陣列有效。

## [!UICONTROL add (array; value1; value2; ...)]

將引數中指定的值加入陣列並傳回該陣列。

## [!UICONTROL map (complex array; key;[key for filtering];[possible values for filtering])]

傳回包含複雜陣列值的原始陣列。 此函式允許篩選值。 將原始變數名稱用於金鑰。

>[!BEGINSHADEBOX]

**範例：**

* `map(Emails[];email)`

  傳回包含電子郵件的基本陣列

* `map(Emails[];email;label;work;home)`

  傳回原始陣列，其中包含標籤等於工作或住家位置的電子郵件

>[!ENDSHADEBOX]

如需詳細資訊，請參閱[對應陣列或陣列元素](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md)。

## 隨機播放

## [!UICONTROL sort (array; [order]; [key])]

排序陣列的值。 `order`引數的有效值為：

* `asc`

  （預設） — 遞增順序： 1、2、3、...代表型別「數字」。 A， B， C， a， b， c， ...適用於文字

* `desc`

  遞減順序： ...， 3， 2， 1代表型別Number。...， c， b， a， C， B， A代表文字。

* `asc ci`

  不區分大小寫的遞增順序：A、a、B、b、C、c...代表文字型別。

* `desc ci`

  不區分大小寫的遞減順序： ...， C， c， B， b， A，代表文字型別。

使用`key`引數來存取複雜物件內的屬性。

將原始變數名稱用於金鑰。

若要存取巢狀屬性，請使用點標籤法。

陣列中的第一個專案是索引1。

>[!BEGINSHADEBOX]

**範例：**

* `sort(Contacts[];name)`

  以預設遞增順序依「name」屬性來排列連絡人陣列

* `sort(Contacts[];desc;name)`

  依「name」屬性以遞減順序來排列連絡人陣列

* `sort(Contacts[];asc ci;name)`

  以不區分大小寫的遞增順序依「name」屬性來排列連絡人陣列

* `sort(Emails[];sender.name)`

  依「sender.name」屬性排序電子郵件陣列

>[!ENDSHADEBOX]

## [!UICONTROL reverse (array)]

陣列中的第一個元素會成為最後一個元素，第二個元素會成為倒數第二個元素，依此類推。

## [!UICONTROL flatten (array)]

建立一個新陣列，將所有子陣列元素以遞回方式串連到其中，直到指定的深度。

## [!UICONTROL distinct (array; [key])]

移除陣列內的重複專案。 使用&quot;[!UICONTROL key]&quot;引數來存取複雜物件內的屬性。 若要存取巢狀屬性，請使用點標籤法。 陣列中的第一個專案是索引1。

>[!BEGINSHADEBOX]

**範例：** `distinct(Contacts[];name)`

透過比較「name」屬性來移除連絡人陣列內的重複專案

>[!ENDSHADEBOX]

## toCollection

## toArray

此函式將集合轉換為機碼值組的陣列。

>[!BEGINSHADEBOX]

**範例：**

已提供集合

`{ key1: "value1", key2: "value2:}`

函式

`toArray({ key1: "value1", key2: "value2:})`

傳回機碼值組的陣列

`[{ key1: "value1"}, { key2: "value2"}]`

>[!ENDSHADEBOX]

## [!UICONTROL arrayDifference [array1, array2, mode]]

傳回兩個陣列之間的差異。

為`mode`引數輸入下列其中一個值。

* `classic`：傳回新陣列，其中包含`array2`中不存在的`array1`的所有元素。

* `symmetric`：傳回兩個陣列不共用的元素陣列。

  換言之，此函式傳回的陣列包含`array2`中不存在的`array1`的所有元素，以及`array1`中不存在的`array2`的所有元素。

>[!BEGINSHADEBOX]

**範例：**

假設使用下列陣列：

```
myArray = [1,2,3,4,5]
```

```
yourArray = [3,4,5,6,7]
```

* `arrayDifference [myArray, yourArray, classic]`

  傳回`[1,2]`

* `arrayDifference [yourArray, myArray, classic]`

  傳回`[6,7]`

* `arrayDifference [myArray, yourArray, symmetric]`

  傳回`[1,2,6,7]`

>[!ENDSHADEBOX]

## 去重複化

## 關鍵字

## emptyarray

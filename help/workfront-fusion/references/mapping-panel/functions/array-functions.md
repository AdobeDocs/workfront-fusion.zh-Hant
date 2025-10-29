---
title: 陣列函式
description: 下列陣列函式可在Adobe Workfront Fusion對應面板中使用。
author: Becky
feature: Workfront Fusion
exl-id: 16c3915c-add1-4aab-a0e1-75fc590c42a6
source-git-commit: 9b61a3b18df1f755cc7ccc28889564e4bcb6cda0
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 0%

---

# 陣列函式

## [!UICONTROL 聯結（陣列；分隔符號）]

在每個專案之間使用指定的分隔符號，將陣列中的所有專案串連到字串中。

## [!UICONTROL 長度（陣列）]

傳回陣列中的專案數。

## [!UICONTROL 鍵（物件）]

傳回給定物件或陣列屬性的陣列。

## [!UICONTROL 磁碟片段（陣列；開始；[結束]）]

傳回僅包含所選專案的新陣列。

## [!UICONTROL 合併(array1； array2； ...)]

將一個或多個陣列合併到一個陣列中。

## [!UICONTROL 包含（陣列；值）]

驗證陣列是否包含值。

## [!UICONTROL 移除（陣列；值1；值2； ...）]

移除陣列引數中指定的值。 此函式僅對文字或數字的原始陣列有效。

## [!UICONTROL 新增（陣列；值1；值2； ...）]

將引數中指定的值加入陣列並傳回該陣列。

## [!UICONTROL 對應（複雜陣列；機碼；[用於篩選的機碼]；[用於篩選的可能值]）]

傳回包含複雜陣列值的原始陣列。 此函式允許篩選值。 將原始變數名稱用於金鑰。

>[!BEGINSHADEBOX]

**範例：**

* `map(Emails[];email)`

  傳回包含電子郵件的基本陣列

* `map(Emails[];email;label;work)`

  傳回帶有標籤等於運作之電子郵件的基本陣列

>[!ENDSHADEBOX]

如需詳細資訊，請參閱[對應陣列或陣列元素](/help/workfront-fusion/create-scenarios/map-data/map-an-array.md)。

## 隨機播放

## [!UICONTROL 排序（陣列；[順序]；[索引鍵]）]

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

## [!UICONTROL 反向（陣列）]

陣列中的第一個元素會成為最後一個元素，第二個元素會成為倒數第二個元素，依此類推。

## [!UICONTROL 平面化（陣列）]

建立一個新陣列，將所有子陣列元素以遞回方式串連到其中，直到指定的深度。

## [!UICONTROL distinct （陣列；[索引鍵]）]

移除陣列內的重複專案。 使用&quot;[!UICONTROL key]&quot;引數來存取複雜物件內的屬性。 若要存取巢狀屬性，請使用點標籤法。 陣列中的第一個專案是索引1。

>[!BEGINSHADEBOX]

**範例：** `distinct(Contacts[];name)`

透過比較「name」屬性來移除連絡人陣列內的重複專案

>[!ENDSHADEBOX]

## toCollection

* 此函式接受包含機碼值組的陣列，並將其轉換為集合。 函式有3個引數：

* （陣列）包含鍵值組
* （字串）要當作索引鍵使用的欄位名稱
* （字串）要當作值使用的欄位名稱

>[!BEGINSHADEBOX]

範例：

給定陣列：

```
[{"name":"Bob", "age":22}, {"name":"Tim", "age":23}]
```

和引數

```
{{toCollection(6.array; "name"; "age")}}
```

函式傳回

```
{
    "Bob": 22,
    "Tim": 23
}
```

>[!ENDSHADEBOX]

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

## [!UICONTROL arrayDifference [array1，array2，模式]]

傳回兩個陣列之間的差異。

為`mode`引數輸入下列其中一個值。

* `classic`：傳回新陣列，其中包含`array1`中不存在的`array2`的所有元素。

* `symmetric`：傳回兩個陣列不共用的元素陣列。

  換言之，此函式傳回的陣列包含`array1`中不存在的`array2`的所有元素，以及`array2`中不存在的`array1`的所有元素。

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

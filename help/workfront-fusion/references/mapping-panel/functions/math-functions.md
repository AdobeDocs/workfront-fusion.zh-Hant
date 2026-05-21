---
title: 數學函式
description: Adobe Workfront Fusion對應面板中有以下數學函式。
author: Becky
feature: Workfront Fusion
exl-id: 3d08b09d-b395-4226-b7e3-d5650c428a59
TQID: https://experienceleague.adobe.com/a0WYFvPFBnXOvKS9ndQ-TD5xSvJz2bCbUbDY5VnXW0w
product_v2:
  - id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 6%

---

# 數學函式

## [!UICONTROL 平均值（[陣列值]） average(value1； [value2]， ...)]

傳回特定陣列中數值的平均值，或個別輸入之數值的平均值。

## [!UICONTROL ceil （數字）]

傳回大於或等於指定數字的最小整數。

>[!BEGINSHADEBOX]

**範例：**

* `ceil(` `1.2` `)`

  傳回2

* `ceil(` `4` `)`

  傳回4

>[!ENDSHADEBOX]

## [!UICONTROL 樓層（數字）]

傳回小於或等於指定數字的最大整數。

>[!BEGINSHADEBOX]

**範例：**

* `floor(` `1.2` `)`

  傳回1

* `floor(` `1.9` `)`

  傳回1

* `floor(` `4` `)`

  傳回4

>[!ENDSHADEBOX]

## [!UICONTROL 最大值（[個值陣列]），最大值(value1；value2； ...)]

傳回指定陣列中的最大數字或個別輸入數字中的最大數字。

## [!UICONTROL 分鐘（[個值陣列]），分鐘(value1； value2； ...)]

傳回指定陣列中的最小數字，或個別輸入數字中的最小數字。

## [!UICONTROL 回合（數字）]

將數值四捨五入至最接近的整數。

>[!BEGINSHADEBOX]

**範例：**

* `round(` `1.2` `)`

  傳回1

* `round(` `1.5` `)`

  傳回2

* `round(` `1.7` `)`

  傳回2

* `round(` `2` `)`

  傳回2

>[!ENDSHADEBOX]

## [!UICONTROL sum （[個值陣列]）， sum(value1； value2； ...)]

傳回指定陣列中值的總和，或個別輸入的數字總和。

## [!UICONTROL parseNumber （數字；小數分隔符號）]

剖析包含數字的字串並傳回數字。 例如， parseNumber(1 756,456；，)

## [!UICONTROL formatNumber (number； decimalPOINTS； [decimalSeparator]； [thousandsSeparator])]

傳回要求格式的數字。 依預設，小數點為逗號(，)，千分位分隔符號為句點(.)。

>[!BEGINSHADEBOX]

**範例：**

`formatNumber( 123456789 ; 3 ; , ; . )`

傳回123.456.789,000

>[!ENDSHADEBOX]

### [!UICONTROL abs（號碼）]

[!BADGE 新增！]{type=Informative}

傳回數字的絕對值。

>[!BEGINSHADEBOX]

**範例：**

* `abs(-3.14)`

  傳回3.14
* `abs(3.14)`

  傳回3.14


### [!UICONTROL div(number1； number2； ...)]

[!BADGE 新增！]{type=Informative}

按照提供的順序除以所有數字。

>[!BEGINSHADEBOX]

**範例：**

* `div(10; 2)`

  傳回5
* `div(100; 5; 4)`

  傳回5


### [!UICONTROL ln（數字）]

[!BADGE 新增！]{type=Informative}

傳回數字的自然對數。


>[!BEGINSHADEBOX]

**範例：**

* `ln(1)`

  傳回0
* `ln(2.718281828)`

  傳回1


### [!UICONTROL log(number1； number2)]

[!BADGE 新增！]{type=Informative}

傳回基底`number1`的`number2`對數。

>[!BEGINSHADEBOX]

**範例：**

* `log(10; 100)`

  傳回2
* `log(2; 8)`

  傳回3


### [!UICONTROL number(string)]

[!BADGE 新增！]{type=Informative}

將字串轉換為數字。

>[!BEGINSHADEBOX]

**範例：**

* `number("3.14")`

  傳回3.14
* `number("42")`

  傳回42


### [!UICONTROL power(number； power)]

[!BADGE 新增！]{type=Informative}

傳回提升為指定次方的數字。

>[!BEGINSHADEBOX]

**範例：**

* `power(2; 3)`

  傳回8
* `power(4; 0.5)`

  傳回2


### [!UICONTROL prod(number1； number2； ...)]

[!BADGE 新增！]{type=Informative}

將所有提供的數字相乘。

>[!BEGINSHADEBOX]

**範例：**

* `prod(2; 3; 4)`

  傳回24
* `prod(5; 5)`

  傳回25


### [!UICONTROL sortAscNum(number1； number2； ...)]

[!BADGE 新增！]{type=Informative}

傳回提供的以遞增順序排序的數字。

>[!BEGINSHADEBOX]

**範例：**

* `sortAscNum(3; 1; 2)`

  傳回\[1， 2， 3]
* `sortAscNum(5; 3; 4)`

  傳回\[3， 4， 5]


### [!UICONTROL sortDescNum(number1； number2； ...)]

[!BADGE 新增！]{type=Informative}

傳回提供的以遞減順序排序的數字。

>[!BEGINSHADEBOX]

**範例：**

* `sortDescNum(3; 1; 2)`

  傳回\[3， 2， 1]
* `sortDescNum(5; 3; 4)`

  傳回\[5， 4， 3]


### [!UICONTROL sqrt(number)]

[!BADGE 新增！]{type=Informative}

傳回數字的平方根。

>[!BEGINSHADEBOX]

**範例：**

* `sqrt(9)`

  傳回3
* `sqrt(4)`

  傳回2


### [!UICONTROL sub(number1； number2； ...)]

[!BADGE 新增！]{type=Informative}

依照提供的順序減去所有數字。

>[!BEGINSHADEBOX]

**範例：**

* `sub(10; 3; 2)`

  傳回5
* `sub(20; 5)`

  傳回15

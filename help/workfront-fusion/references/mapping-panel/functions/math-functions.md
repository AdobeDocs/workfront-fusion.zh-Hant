---
title: 數學函式
description: Adobe Workfront Fusion對應面板中有以下數學函式。
author: Becky
feature: Workfront Fusion
exl-id: 3d08b09d-b395-4226-b7e3-d5650c428a59
source-git-commit: 24a6c1558fd6349c022df8a1847a7f39fafddd67
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# 數學函式

## [!UICONTROL average ([array of values]) average(value1; [value2], ...)]

傳回特定陣列中數值的平均值，或個別輸入之數值的平均值。

## [!UICONTROL ceil (number)]

傳回大於或等於指定數字的最小整數。

>[!BEGINSHADEBOX]

**範例：**

* `ceil(` `1.2` `)`

  傳回2

* `ceil(` `4` `)`

  傳回4

>[!ENDSHADEBOX]

## [!UICONTROL floor (number)]

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

## [!UICONTROL max ([array of values]), max(value1;value2; ...)]

傳回指定陣列中的最大數字或個別輸入數字中的最大數字。

## [!UICONTROL min ([array of values]), min(value1; value2; ...)]

傳回指定陣列中的最小數字，或個別輸入數字中的最小數字。

## [!UICONTROL round (number)]

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

## [!UICONTROL sum ([array of values]), sum(value1; value2; ...)]

傳回指定陣列中值的總和，或個別輸入的數字總和。

## [!UICONTROL parseNumber (number; decimal separator)]

剖析包含數字的字串並傳回數字。 例如， parseNumber(1 756,456；，)

## [!UICONTROL formatNumber (number; decimalPOINTS; [decimalSeparator]; [thousandsSeparator])]

傳回要求格式的數字。 依預設，小數點為逗號(，)，千分位分隔符號為句點(.)。

>[!BEGINSHADEBOX]

**範例：**

`formatNumber( 123456789 ; 3 ; , ; . )`

傳回123.456.789,000

>[!ENDSHADEBOX]

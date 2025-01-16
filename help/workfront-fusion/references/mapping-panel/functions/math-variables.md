---
title: 數學變數
description: 下列數學變數可在 [!DNL Adobe Workfront Fusion mapping] 面板中使用。
author: Becky
feature: Workfront Fusion
exl-id: b309f035-4d46-473b-b915-6938587b0bcf
source-git-commit: 24a6c1558fd6349c022df8a1847a7f39fafddd67
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 0%

---

# 數學變數

## pi

代表數學符號$\pi$。

## [!UICONTROL random]

傳回範圍[`0`，`1`]中的浮點偽隨機數（包含`0`，但不包含`1`）。

使用以下公式來產生範圍[`min`，`max`]中的整數偽隨機數（包含`min`和`max`）：

![](assets/math-variable-random-350x61.png)

```
floor(random * (1.max - 1.min + 1)) + 1.min
```

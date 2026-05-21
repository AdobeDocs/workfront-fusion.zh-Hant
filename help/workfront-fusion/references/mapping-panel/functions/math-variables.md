---
title: 數學變數
description: 下列數學變數可在 [!DNL Adobe Workfront Fusion mapping] 面板中使用。
author: Becky
feature: Workfront Fusion
exl-id: b309f035-4d46-473b-b915-6938587b0bcf
TQID: https://experienceleague.adobe.com/7vPwofVyFGdTGAXXuqbP5mmpPgSEK0JqimFqWu-UlJU
product_v2: id: c4a86a5d-6562-4fc6-aa00-bfa25833aed9
source-git-commit: 219b9dbf3a7e4be1676b21bc3d3752d70d743b13
workflow-type: tm+mt
source-wordcount: 52
ht-degree: 11%

---

# 數學變數

## pi

代表數學符號$\pi$。

## [!UICONTROL random]

傳回範圍[`0`，`1`]中的浮點偽隨機數（包含`0`，但不包含`1`）。

使用以下公式來產生範圍[`min`，`max`]中的整數偽隨機數（包含`min`和`max`）：

![Random](assets/math-variable-random-350x61.png)

```
floor(random * (1.max - 1.min + 1)) + 1.min
```

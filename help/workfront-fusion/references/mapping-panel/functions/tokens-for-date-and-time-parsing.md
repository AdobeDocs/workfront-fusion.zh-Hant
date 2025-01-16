---
title: 日期和時間剖析的權杖
description: ' [!DNL Adobe Workfront Fusion mapping] 面板中有下列日期和時間剖析的權杖。'
author: Becky
feature: Workfront Fusion
exl-id: d3242af3-89e8-45ae-81a1-3b4dadf824fd
source-git-commit: 24a6c1558fd6349c022df8a1847a7f39fafddd67
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 10%

---

# 日期和時間剖析的權杖

## 年、月和日權杖

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>輸入 </th> 
   <th>範例 </th> 
   <th> <p>說明</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>YYYY </code> </td> 
   <td><code>2014 </code> </td> 
   <td> <p>4或2位數年</p> </td> 
  </tr> 
  <tr> 
   <td><code>YY</code></td> 
   <td><code>14</code></td> 
   <td> <p>2位數年份</p> </td> 
  </tr> 
  <tr> 
   <td><code>Y</code> </td> 
   <td><code>-25</code> </td> 
   <td> <p>[!UICONTROL Year with any number of digits and sign]</p> </td> 
  </tr> 
  <tr> 
   <td><code>Q</code> </td> 
   <td><code>1..4</code> </td> 
   <td> <p> 季別。 將月份設為季度的第一個月。</p> </td> 
  </tr> 
  <tr> 
   <td><code>M MM</code> </td> 
   <td><code>1..12</code> </td> 
   <td> <p> 月數</p> </td> 
  </tr> 
  <tr> 
   <td><code>MMM MMMM</code> </td> 
   <td><code>Jan..December</code> </td> 
   <td> <p> 月份名稱</p> </td> 
  </tr> 
  <tr> 
   <td><code>D DD</code> </td> 
   <td><code>1..31</code> </td> 
   <td> <p> 月中的日</p> </td> 
  </tr> 
  <tr> 
   <td><code>Do </code> </td> 
   <td><code>1st..31st</code> </td> 
   <td> <p> 含序數的月中日</p> </td> 
  </tr> 
  <tr> 
   <td><code>DDD DDDD</code> </td> 
   <td><code>1..365</code></td> 
   <td> <p> 一年中的日數</p> </td> 
  </tr> 
  <tr> 
   <td><code>X</code> </td> 
   <td><code>1410715640.579</code> </td> 
   <td> <p> Unix時間戳記</p> </td> 
  </tr> 
  <tr> 
   <td><code>x</code> </td> 
   <td><code>1410715640579</code> </td> 
   <td> <p> Unix毫秒時間戳記</p> </td> 
  </tr> 
 </tbody> 
</table>

## 週年、周和工作日權杖

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>輸入 </th> 
   <th>範例 </th> 
   <th> <p>說明</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>ddd dddd</code> </td> 
   <td><code>Mon...Sunday</code> </td> 
   <td> <p> 日期名稱</p> </td> 
  </tr> 
  <tr> 
   <td><code>GGGG</code> </td> 
   <td><code>2014</code> </td> 
   <td> <p> ISO 4位數週年</p> </td> 
  </tr> 
  <tr> 
   <td><code>GG </code> </td> 
   <td><code>14</code> </td> 
   <td> <p> ISO 2位數週年</p> </td> 
  </tr> 
  <tr> 
   <td><code>W WW</code> </td> 
   <td><code>1..53</code></td> 
   <td> <p> ISO年度周數</p> </td> 
  </tr> 
  <tr> 
   <td><code>E</code> </td> 
   <td><code>1..7</code> </td> 
   <td> <p> ISO星期</p> </td> 
  </tr> 
 </tbody> 
</table>

## 小時、分鐘、秒、毫秒和位移權杖

<table style="table-layout:auto"> 
 <col> 
 <col> 
 <col> 
 <thead> 
  <tr> 
   <th>輸入 </th> 
   <th>範例 </th> 
   <th> <p>說明</p> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td><code>H HH</code> </td> 
   <td><code>0..23</code></td> 
   <td> <p> 小時（24小時時間）</p> </td> 
  </tr> 
  <tr> 
   <td><code>h hh</code> </td> 
   <td><code>1..12</code> </td> 
   <td> <p> 小時（搭配A.使用的12小時時間）</p> </td> 
  </tr> 
  <tr> 
   <td><code>k kk</code> </td> 
   <td><code>1..24</code> </td> 
   <td> <p> 小時（從1到24的24小時時間）</p> </td> 
  </tr> 
  <tr> 
   <td><code>a A</code> </td> 
   <td><code>am pm</code> </td> 
   <td> <p> 後置或前置經線（請注意，a p這個字元也被視為有效）</p> </td> 
  </tr> 
  <tr> 
   <td><code>m mm</code> </td> 
   <td><code>0..59</code> </td> 
   <td> <p> 分鐘</p> </td> 
  </tr> 
  <tr> 
   <td><code>s ss</code> </td> 
   <td><code>0..59</code> </td> 
   <td> <p> 秒</p> </td> 
  </tr> 
  <tr> 
   <td><code>S SS SSS</code> </td> 
   <td><code>0..999</code> </td> 
   <td> <p> 分數秒</p> </td> 
  </tr> 
  <tr> 
   <td><code>Z ZZ</code> </td> 
   <td><code>+12:00</code> </td> 
   <td> <p> 從UTC位移為+-HH：mm、+-HHmm或Z</p> </td> 
  </tr> 
 </tbody> 
</table>

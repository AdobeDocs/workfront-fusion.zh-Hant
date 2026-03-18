---
title: 新增錯誤處理
description: 當在執行案例期間發生錯誤時，通常是因為服務因失敗而無法使用、服務以非預期的資料回應，或輸入資料的驗證失敗。
author: Becky
feature: Workfront Fusion
exl-id: 82ddaf73-ecf9-4fd6-8f8e-909351023c77
source-git-commit: d7072a2dca50bf47f20d1f25dba4d3fb819d3ddc
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 9%

---

# 新增錯誤處理

執行情境期間可能會發生錯誤。

例如，發生錯誤的可能原因如下：

* 服務因失敗而無法使用
* 服務以非預期的資料回應
* 驗證輸入資料失敗
* 其他原因

如果模組在案例執行期間遇到錯誤，並且沒有附加到模組的錯誤處理路由或其路由，則會執行預設錯誤處理邏輯。

您可以將錯誤處理常式新增至模組或路由，以您自己的邏輯取代預設的錯誤處理邏輯。 Adobe Workfront Fusion提供五種不同的指令，可在錯誤處理常式路由的結尾插入。

如需預設錯誤處理的詳細資訊，請參閱[錯誤型別](/help/workfront-fusion/references/errors/error-processing.md)。

如需錯誤處理指示的詳細資訊，請參閱錯誤處理[的](/help/workfront-fusion/references/errors/directives-for-error-handling.md)指示。

>[!NOTE]
>
>Workfront Fusion支援路由層級的錯誤處理，可讓您為每個路由定義一次錯誤處理邏輯，而不是將錯誤處理常式附加至每個個別模組。
>由於路由層級的錯誤處理是管理錯誤的更可擴充、一致和架構上更乾淨的方法，尤其是在進階、多分支自動化中，因此我們建議使用路由層級錯誤處理作為最佳實務。

## 存取權要求

+++ 展開以檢視這篇文章中所述功能的存取權要求。

<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader">Adobe Workfront 封裝</td> 
   <td> <p>任何 Adobe Workfront Workflow 封裝及任何 Adobe Workfront Automation and Integration 封裝</p><p>Workfront Ultimate</p><p>Workfront Prime 和 Select 封裝，以及額外購買的 Workfront Fusion。</p> </td> 
  </tr> 
  <tr data-mc-conditions=""> 
   <td role="rowheader">Adobe Workfront 授權</td> 
   <td> <p>標準</p><p>工作或更高層級</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">產品</td> 
   <td>
   <p>如果您的組織擁有 Select 或 Prime Workfront 封裝，但不包括 Workfront Automation and Integration，則您的組織必須購買 Adobe Workfront Fusion。</li></ul>
   </td> 
  </tr>
 </tbody> 
</table>

若要詳細了解此表格中的資訊，請參閱[&#128279;](/help/workfront-fusion/references/licenses-and-roles/access-level-requirements-in-documentation.md)文件中的存取權要求。

+++

## 錯誤處理常式位置和階層

您可以將錯誤處理常式新增至個別模組或路由器。

附加到模組的錯誤處理常式，只會針對處理該特定模組時遇到的錯誤而觸發。

路由器路由上任何模組遇到錯誤時，路由器觸發的錯誤處理常式會附加至該路由器。 這包括在任何在其自己的路由器上沒有錯誤處理常式的子路由上遇到的錯誤。

錯誤由下列階層處理：

1. 模組
2. 路由器
3. 父路由器
4. 預設錯誤處理

>[!BEGINSHADEBOX]

### 範例

考量下列範例情境：

![顯示路由和錯誤處理常式的範例案例](assets/error-handling-route-example-with-numbers.png)

1. 此模組有錯誤處理常式。 此模組上的任何錯誤都由Commit指示詞處理。
1. 此模組沒有錯誤處理常式。 如果此模組發生錯誤，建立模組路由的路由器上的處理常式會處理此錯誤。 此模組上的任何錯誤都由Rollback指示詞處理。
1. 此模組沒有錯誤處理常式，建立模組路由的路由器也沒有錯誤處理常式，但下一個路由器上有錯誤處理常式。 此模組上的任何錯誤都由Break指示詞處理。

>[!NOTE]
>
>* 如果模組、其路由器或任何父路由器上沒有錯誤處理常式，該模組上的任何錯誤都會由預設的錯誤處理來處理。
>* 若要建立全域錯誤處理常式，請在方案開頭附近建立路由器，並將錯誤處理附加至該路由器。


>[!ENDSHADEBOX]

## 新增錯誤處理常式

您可以將錯誤處理常式新增至模組或路由器。

* [將錯誤處理常式新增至模組](#add-an-error-handler-to-a-module)
* [將錯誤處理常式新增至路由器](#add-an-error-handler-to-a-router)

### 將錯誤處理常式新增至模組

若要將錯誤處理常式新增至模組：

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要新增錯誤處理路由的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 用滑鼠右鍵按一下要在其後新增錯誤處理常式路由的模組，然後選取&#x200B;**[!UICONTROL 新增錯誤處理常式]**：

   ![錯誤處理常式路由](assets/error-handler-route.png)

   錯誤處理常式路由已新增至模組。 如果模組是路由中的最後一個模組，則錯誤處理常式會直接依照該模組操作。 如果模組之後有更多模組，則會新增個別的錯誤處理常式路由。

   錯誤處理模組會顯示指令清單，以及在您的情境中使用的應用程式。

   ![錯誤路由](assets/error-route.png)

1. 選取其中一個指令。

   或

   新增一或多個模組至錯誤處理常式路由。

   如果您將更多模組加入路由，則預設會套用「忽略」指令。 如果出現錯誤，則會處理該路由上的後續模組。

   如需指令的詳細資訊，請參閱本文中的[處理指令時發生錯誤](#error-handling-directives)。

1. （可選）將篩選器新增至錯誤處理路由。 如需指示，請參閱[新增篩選和巢狀至錯誤處理路由](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)。

>[!NOTE]
>
>請注意，錯誤處理常式路由是由透明圓組成，而一般路由是由實心圓組成。

### 將錯誤處理常式新增至路由器

1. 按一下左側面板中的&#x200B;**[!UICONTROL 案例]**&#x200B;索引標籤。
1. 選取您要新增錯誤處理路由的案例。
1. 按一下情境上的任何位置，以輸入情境編輯器。
1. 用滑鼠右鍵按一下您要新增錯誤處理常式路由的路由器，然後選取&#x200B;**[!UICONTROL 新增錯誤處理常式]**：

   ![錯誤處理常式路由](assets/error-handler-on-router.png)

   已將錯誤處理常式路由新增至路由器。

   錯誤處理模組會顯示指令清單，以及在您的情境中使用的應用程式。

   ![錯誤路由](assets/error-handler-route-from-router.png)

1. 選取其中一個指令。

   或

   新增一或多個模組至錯誤處理常式路由。

   如果您將更多模組加入路由，則預設會套用「忽略」指令。 如果出現錯誤，則會處理該路由上的後續模組。

   如需指令的詳細資訊，請參閱本文中的[處理指令時發生錯誤](#error-handling-directives)。

1. （可選）將篩選器新增至錯誤處理路由。 如需指示，請參閱[新增篩選和巢狀至錯誤處理路由](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)。

## 處理指示時發生錯誤

這些指示詞會簡要說明如下。 如需詳細資訊，請參閱錯誤處理[的](/help/workfront-fusion/references/errors/directives-for-error-handling.md)指示。

有五個指令，可根據錯誤後案例執行是否繼續分組為下列類別。

下列指令可確保案例執行繼續進行：

* **[!UICONTROL 繼續]**：可讓您指定發生錯誤的模組替代輸出。 案例執行狀態會標籤為成功。
* **[!UICONTROL 忽略]**：忽略錯誤。 案例執行狀態會標籤為成功。
* **[!UICONTROL 中斷]**：將輸入儲存到未完成執行的佇列。 案例執行狀態會標示為警告。

  如需詳細資訊，請參閱[檢視並解決不完整的執行](/help/workfront-fusion/manage-scenarios/view-and-resolve-incomplete-executions.md)。

如果發生錯誤時，案例執行應該停止，請使用以下指令之一：

* **[!UICONTROL 回覆]**：立即停止案例執行並標示其狀態為錯誤。
* **[!UICONTROL 認可]**：立即停止案例執行並將其狀態標籤為成功。

## 資源

如需錯誤處理的詳細資訊，請參閱：

* [Adobe Workfront Fusion中錯誤處理的指示](/help/workfront-fusion/references/errors/directives-for-error-handling.md)
* [為錯誤處理路由新增篩選和嵌套功能](/help/workfront-fusion/create-scenarios/config-error-handling/advanced-error-handling.md)

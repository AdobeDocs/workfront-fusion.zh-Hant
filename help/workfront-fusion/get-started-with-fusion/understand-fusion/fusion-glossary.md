---
title: Adobe Workfront Fusion字彙表
description: 下列字彙表說明Adobe Workfront Fusion中的一些常用辭彙。
author: Becky
feature: Workfront Fusion
exl-id: 7f098ec2-8594-4e5d-9ce7-d1738a05f9a6
source-git-commit: 190bfe5992fb21b789a7246c4ae732a5dc7672fa
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 1%

---

# Adobe Workfront Fusion字彙表

下列字彙表說明Adobe Workfront Fusion中的一些常用辭彙。


<table style="table-layout:auto">
 <col> 
 <col> 
 <tbody> 
  <tr> 
   <td role="rowheader"> <p>動作</p> </td> 
   <td>可讓您執行動作的模組，例如從選取的應用程式或服務讀取或寫入資料。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>匯總</p> </td> 
   <td> <p>一種模組型別，可將多個套件（多個資料集合）合併為單一套件。 </p><p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/aggregator-module.md" class="MCXref xref">彙總器模組</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API</td> 
   <td>應用程式設計介面(API)是應用程式和服務彼此通訊的一種方式。 Fusion會使用API與您連線的應用程式通訊。 每個應用程式都有個別的API。 </td> 
  </tr> 
  <tr> 
   <td role="rowheader">API 密鑰</td> 
   <td>唯一代碼，可識別呼叫軟體API （用於驗證）的使用者、開發人員或程式。 由於Fusion模組是透過連線API來運作，因此API金鑰有時是必要的。 API金鑰由需要它們的應用程式所散發。 例如，如果您需要API金鑰才能將Fusion連線至Adobe Lightroom，則可透過您的Adobe Lightroom帳戶請求該金鑰。</td> 
  </tr> 
  <tr> 
   <td role="rowheader">應用程式或服務</td> 
   <td> <p>軟體應用程式。 Fusion可以連線到大部分的應用程式，即使它沒有該應用程式的專用聯結器。</p> <p>應用程式也可以是處理資料的特殊函式，例如疊代器或彙總。 </p> <p>服務是資料來源，其中可能包含網頁API、網頁、不同型別的伺服器(FTP、SMTP、IMAP)等。 </p>  </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>組合</p> </td> 
   <td> <p>組合是模組傳回或接收的基本資料單位。 例如，傳回三個記錄的搜尋模組會輸出三組資料，每個記錄一個。 組合是由專案所組成。</p> </td> 
  </tr> 
  <tr>
   <td role="rowheader"> <p>連接</p> </td> 
   <td> <p>連線代表連線至指定服務的一組認證。 您可以在任何模組內設定連線，然後可以在任何其他模組內使用該連線。 每個模組都必須選取連線，這樣Fusion才能使用這些認證來存取模組所需的資訊。 </p><p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/connection-overview.md" class="MCXref xref">連線總覽</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader">聯結器</td> 
   <td>聯結器是指定應用程式的一組模組。 Workfront Fusion為許多常見的工作應用程式提供聯結器，例如Workfront、Salesforce和Jira。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>週期</p> </td> 
   <td> <p>週期包含案例執行的兩個階段：作業與確認。 此情境可能包含一或多個週期。 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/scenarios/scenario-execution-cycles-phases.md" class="MCXref xref">案例執行、週期和階段</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>資料存放區</p> </td> 
   <td> <p>資料存放區會儲存情境中的資料，或讓您在個別情境或情境執行之間傳輸資料。 </p><p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/map-data/data-stores.md" class="MCXref xref">資料存放區</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>篩選器</p> </td> 
   <td> <p> 篩選可在兩個模組之間套用，並可讓您僅使用符合特定條件的組合。 您可以套用許多不同的篩選器。 </p><p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/add-modules/add-a-filter-to-a-scenario.md" class="MCXref xref">將篩選器新增至案例</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>ID </p> </td> 
   <td> <p>用來唯一識別組合包的名稱。 ID通常用於區分要從指定服務更新或刪除的套件。 ID可從先前模組的輸出對應。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>項目</p> </td> 
   <td> <p>組合的一部分。 套件組合可包含多個專案。 有數種不同型別的專案：文字、數字、布林值（是/否）、日期、時間、緩衝（二進位資料）、集合、選取功能表、陣列和驗證。</p><p> 如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/mapping-panel/data-types/item-data-types.md" class="MCXref xref">專案資料型別</a>。</p> </td> 
  </tr>
  <tr> 
   <td role="rowheader"> <p>迭代器</p> </td> 
   <td> <p>一種模組型別，可讓您取得一束資料（資料集合），然後分割成個別的束。 接著，這些套件組合便可由後續模組個別處理。 </p><p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/iterator-module.md" class="MCXref xref">[!UICONTROL Iterator]模組</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>模組</p> </td> 
   <td> <p>在相關應用程式或服務內執行功能（例如建立記錄）的案例中的單一步驟。</p> <p>每個應用程式或服務都有各種模組，可定義其回應請求的方式。</p>  <p> <img src="assets/module.png"> </p> <p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md" class="MCXref xref">模組總覽</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>營運</p> </td> 
   <td> <p>模組執行的任務，例如擷取記錄或上傳檔案。</p><p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/set-up-and-manage-workfront-fusion/licensing-operations-overview/operations-in-workfront-fusion.md" class="MCXref xref">作業</a>。</p>
  </tr> 
  <tr> 
   <td role="rowheader">公開/私密金鑰</td> 
   <td>公開和私密金鑰可用來加密和解密資料。 公開金鑰可以散發，任何擁有公開金鑰的人都可以加密資料，但只有私密金鑰可以解密資料。 同樣地，擁有私密金鑰的使用者可以加密任何擁有公開金鑰的使用者都可以解密的資料。 私密金鑰加密可確保資料來自私密金鑰的擁有者，並作為資料來源的驗證。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>路由器</p> </td> 
   <td>路由器可讓您複製資料或新增路由至情境，以便重新路由資料並個別處理不同的資料群組。</p><p> 如需詳細資訊，請參閱<a href="/help/workfront-fusion/create-scenarios/add-modules/router-module.md" class="MCXref xref">[!UICONTROL Router]模組</a>。</td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>情境</p> </td> 
   <td> <p>使用者建立的一系列自動化步驟，每個步驟都由模組表示和執行。 案例的目的是移動及操控資料。</p> <p> <img src="assets/entire-scenario-blank.png" style="width: 350;height: 178;"> </p> <p> 如需詳細資訊，請參閱<a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/scenario-overview.md" class="MCXref xref">案例概觀</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>案例區段</p> </td> 
   <td> <p> 案例區段是案例的一部分，包含一系列全部連線到相同應用程式的模組。 案例區段通常代表應用程式中的簡短工作流程。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>觸發</p> </td> 
   <td> <p>觸發器是一種模組，可監視新的和更新的資料，並在模組中所設定的某些條件套用時啟動情境。 觸發器可設定為依排程（輪詢）開始案例，或每當資料變更時（即時觸發器或webhook）。</p> <p>如需詳細資訊，請參閱模組概觀文章中的<a href="/help/workfront-fusion/get-started-with-fusion/understand-fusion/module-overview.md" class="MCXref xref">觸發器</a>。</p> </td> 
  </tr> 
  <tr> 
   <td role="rowheader"> <p>Webhook</p> </td> 
   <td> <p>一種特殊型別的觸發器，可讓您在新套裝可用後立即執行案例。 </p><p>如需詳細資訊，請參閱<a href="/help/workfront-fusion/references/modules/webhooks-reference.md" class="MCXref xref">即時觸發程式(webhook)</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

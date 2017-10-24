---
title: "Termelési rendelések készként jelentése"
description: "Termelési szakasz készként jelenítése Ebben a szakaszban megtörténik a késztermék jelentése, és a gyártási rendelés átkerül a készletbe."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f8adcbcc2157058151c26179eb2eb925b0092d2d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="report-production-orders-as-finished"></a><span data-ttu-id="ac932-104">Termelési rendelések készként jelentése</span><span class="sxs-lookup"><span data-stu-id="ac932-104">Report production orders as finished</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ac932-105">Termelési szakasz készként jelenítése</span><span class="sxs-lookup"><span data-stu-id="ac932-105">Report as finished is a production stage.</span></span> <span data-ttu-id="ac932-106">Ebben a szakaszban megtörténik a késztermék jelentése, és a gyártási rendelés átkerül a készletbe.</span><span class="sxs-lookup"><span data-stu-id="ac932-106">At this stage, a finished product is reported and moved from the production order to the inventory.</span></span>

<span data-ttu-id="ac932-107">Amikor a késztermékek mennyiségét egy termelési rendelésen készként jelentik, akkor a mennyiség frissül a rendelkezésre álló készletben is.</span><span class="sxs-lookup"><span data-stu-id="ac932-107">When a quantity of the finished goods is reported as finished on a production order it is updated as on-hand in the inventory.</span></span> <span data-ttu-id="ac932-108">Az eredetileg tervezett rendelési mennyiségből részleges mennyiség is jelenthető készként.</span><span class="sxs-lookup"><span data-stu-id="ac932-108">Partial quantities of the originally planned order quantity can be reported as finished.</span></span> <span data-ttu-id="ac932-109">Emellett a hibás mennyiségeket is készre lehet jelenteni, kapcsolódó hibaok megadásával.</span><span class="sxs-lookup"><span data-stu-id="ac932-109">It is also possible to report error quantities with an associated error reason when reporting quantities as finished.</span></span> <span data-ttu-id="ac932-110">Amikor a termelési rendelés eléri a Készként jelentve fokozatot, az azt jelenti, hogy nem lesz további mennyiség jelentve a termelési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="ac932-110">When the production order reach the stage Reported as finished it indicates that no more quantity is going to be reported at the production  order.</span></span>
<span data-ttu-id="ac932-111">A következő jellemzők társulnak a **Készként jelentve** folyamathoz:</span><span class="sxs-lookup"><span data-stu-id="ac932-111">The following characteristics are also associated with the **Report as finished** process:</span></span>
-   <span data-ttu-id="ac932-112">A nyersanyag és az idő felhasználása úgy is beállítható, hogy arányos legyen a jelentett mennyiséggel (visszavezetés)</span><span class="sxs-lookup"><span data-stu-id="ac932-112">It is possible to set up consumption of raw material and time that are proportional to the reported quantity (back-flushing)</span></span>
-   <span data-ttu-id="ac932-113">Betárolási munka generálható olyan cikkekre, amelyeknél engedélyezve vannak a raktárkezelési folyamatok.</span><span class="sxs-lookup"><span data-stu-id="ac932-113">Put-away work can be generated for items that are enabled for warehouse processes.</span></span>
-   <span data-ttu-id="ac932-114">A késztermékek tervezett vagy standard költségére beállítható a főkönyvi számlákra való jelentés.</span><span class="sxs-lookup"><span data-stu-id="ac932-114">The planned or standard cost value of the finished goods can be set up to be reported to ledger accounts.</span></span>
-   <span data-ttu-id="ac932-115">Minőségi rendelés hozható létre a jelentett mennyiséghez, minőségi társítás beállítása alapján.</span><span class="sxs-lookup"><span data-stu-id="ac932-115">A quality order can be created for the reported quantity based on the setup of a quality association.</span></span>

<span data-ttu-id="ac932-116">A mennyiség a kimeneti helyre lesz jelentve.</span><span class="sxs-lookup"><span data-stu-id="ac932-116">The quantity is reported to the output location.</span></span> <span data-ttu-id="ac932-117">Ekkor raktári munka jön létre, amely áttárolja a mennyiséget a kimeneti helyről arra a végcélra, amelyet a betárolási munka helyutasítása határoz meg.</span><span class="sxs-lookup"><span data-stu-id="ac932-117">Warehouse work is then generated to move the quantity from the output location to its final destination defined by the location directive for the put-away work.</span></span>

-   <span data-ttu-id="ac932-118">Minőségi rendelés akkor hozható létre, amikor wgy termelési rendelést készre jelentenek, amennyiben be lett állítva minőségi társítás.</span><span class="sxs-lookup"><span data-stu-id="ac932-118">A quality order can be created when a production order is reported as finished if a quality association has been set up.</span></span>

## <a name="set-a-production-order-to-reporting-as-finished"></a><span data-ttu-id="ac932-119">Termelési rendelés Készre jelentett állapotra állítása</span><span class="sxs-lookup"><span data-stu-id="ac932-119">Set a production order to Reporting as finished</span></span>
<span data-ttu-id="ac932-120">A termelési rendelés a szokásos termelési rendelés frissítése funkcióval, az útvonal- és feladatkártyanaplókkal, vagy a **Jelentés készként** naplóval lehet **Készként jelenteni**.</span><span class="sxs-lookup"><span data-stu-id="ac932-120">You can set a production order to **Report as finished** through the standard production order update function, or through the route and job card journals, or through the journal **Report as finished**.</span></span> <span data-ttu-id="ac932-121">Emellett a feladatkártya-terminál és a feladatkártya-eszköz oldalakon keresztül is frissítheti az állapotot **Jelentés készként** értékre, amikor a termelési rendelés utolsó feladatát lejelenti.</span><span class="sxs-lookup"><span data-stu-id="ac932-121">You can also update the stage to **Report as finished** through the job card terminal and job card device pages, when you report on the last job of the production order.</span></span> <span data-ttu-id="ac932-122">Végül a **Jelentés készként** állapotot a hordozható raktári eszközök megoldásának folyamatán keresztül is aktiválhatja.</span><span class="sxs-lookup"><span data-stu-id="ac932-122">Finally, you can enable the **Report as finished** option as a process for the handheld warehouse device solution.</span></span>  





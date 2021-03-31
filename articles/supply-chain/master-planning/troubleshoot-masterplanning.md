---
title: Alaptervezés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani az alaptervezés használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: db336946873fa1b5cc3f669823541af8cab4115b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216105"
---
# <a name="troubleshoot-master-planning"></a><span data-ttu-id="0c920-103">Alaptervezés – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="0c920-103">Troubleshoot master planning</span></span>

<span data-ttu-id="0c920-104">Ez a témakör azt mutatja be, hogyan lehet javítani az alaptervezés használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="0c920-104">This topic describes how to fix issues that you might encounter while you work with master planning.</span></span>

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a><span data-ttu-id="0c920-105">Az anyagjegyzék alábontása eltérően viselkedik a megerősített termelési rendeléseknél és a manuálisan létrehozott munka becsült termelési rendeléseinél.</span><span class="sxs-lookup"><span data-stu-id="0c920-105">Bill of materials explosion behaves differently for firmed production orders and for estimated production orders for manually created work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0c920-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="0c920-106">Issue description</span></span>

<span data-ttu-id="0c920-107">Ha egy gyártási rendelés meg van erősítve, a cikkek nem lesznek alábontva, amikor alábontja az anyagjegyzéket (BOM).</span><span class="sxs-lookup"><span data-stu-id="0c920-107">When a production order is firmed, the items aren't exploded when you explode the bill of materials (BOM).</span></span> <span data-ttu-id="0c920-108">Azonban ha manuálisan hoz létre egy munkarendelést, majd megbecsüli a termelési rendelést, a cikkek alábontásra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="0c920-108">However, when you manually create a work order and then estimate the production order, the items are exploded.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0c920-109">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="0c920-109">Issue resolution</span></span>

<span data-ttu-id="0c920-110">A rendszer a várt módon működik.</span><span class="sxs-lookup"><span data-stu-id="0c920-110">The system is working as expected.</span></span> <span data-ttu-id="0c920-111">A termelési rendelés megerősítésekor bekövetkező alábontás a tervezett rendelésre mutat, de nem tűnik jelenik meg, hogy a tervezett rendelés ebben az esetben meg lennel erősítve.</span><span class="sxs-lookup"><span data-stu-id="0c920-111">The explosion that occurs when the production order is firmed will point to the planned order, but it doesn't appear that the planned order is currently firmed in this case.</span></span> <span data-ttu-id="0c920-112">Ha azonban a termelési rendelés meg lett becsülve, az alábontás az engedélyezett termelési rendelésből aktiválódik, ahol nincs tervezett rendelés.</span><span class="sxs-lookup"><span data-stu-id="0c920-112">However, if the production order has been estimated, the explosion is triggered from the released production order where no planned order exists.</span></span>

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a><span data-ttu-id="0c920-113">A Késleltetés érték nem frissül, amikor átütemezek egy tervezett rendelést.</span><span class="sxs-lookup"><span data-stu-id="0c920-113">The Delay value isn't updated when I reschedule a planned order.</span></span>

<span data-ttu-id="0c920-114">A tervezett rendelések késésének frissítéséhez nyissa meg a tervezett rendelés **Átütemezés** párbeszédpaneljét.</span><span class="sxs-lookup"><span data-stu-id="0c920-114">To update the delay for planned orders, open the **Rescheduling** dialog box for the planned order.</span></span> <span data-ttu-id="0c920-115">Győződjön meg arról , hogy az **Alábontás** gyorslapon az **Alábontás elvégzése átütemezés után** beállítás értéke *Igen* legyen.</span><span class="sxs-lookup"><span data-stu-id="0c920-115">On the **Explosion** FastTab, make sure that the **Perform explosion after rescheduling** option is set to *Yes*.</span></span>

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a><span data-ttu-id="0c920-116">A termelésütemezés nem veszi figyelembe a rögzített készlet cikkfedezetén beállított biztonsági időtartalékokat.</span><span class="sxs-lookup"><span data-stu-id="0c920-116">Production scheduling doesn't consider the safety margins that are set on the item coverage for pegged supply.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0c920-117">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="0c920-117">Issue description</span></span>

<span data-ttu-id="0c920-118">Az alaptervezés figyelembe veszi a biztonsági időtartalékokat.</span><span class="sxs-lookup"><span data-stu-id="0c920-118">Master planning considers the safety margins.</span></span> <span data-ttu-id="0c920-119">A rendszer azonban figyelmen kívül hagyja a biztonsági időtartalékokat a tervezett termelési rendelések ütemezésekor.</span><span class="sxs-lookup"><span data-stu-id="0c920-119">However, the safety margins are ignored when planned production orders are scheduled.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0c920-120">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="0c920-120">Issue resolution</span></span>

<span data-ttu-id="0c920-121">Az időtartalékok csak az alaptervezés során lesznek figyelembe véve, a manuális ütemezés során nem.</span><span class="sxs-lookup"><span data-stu-id="0c920-121">Margins are considered only during master planning, not during manual scheduling.</span></span> <span data-ttu-id="0c920-122">Az időtartalékok úgy vannak kialakítva, hogy a tervezési fázisban pufferként működjenek, hogy a tényleges folyamathoz bizonyos „időtartalékot” biztosítsanak.</span><span class="sxs-lookup"><span data-stu-id="0c920-122">Margins are designed to act as a buffer during the planning phase, to give some "margin" for the actual process.</span></span>

<span data-ttu-id="0c920-123">A kívánt eredmény eléréséhez eltávolíthatja az időtartalékot.</span><span class="sxs-lookup"><span data-stu-id="0c920-123">To get the desired result, you can remove the margin.</span></span> <span data-ttu-id="0c920-124">Az útvonalat ezután frissíteni kell, hogy tartalmazza a kívánt időt (például várakozási sorként).</span><span class="sxs-lookup"><span data-stu-id="0c920-124">The route must then be updated so that it includes the desired time (for example, as queue time).</span></span> <span data-ttu-id="0c920-125">Az alaptervezésnek és a manuális ütemezésnek is ugyanazt az eredményt kell elérniük.</span><span class="sxs-lookup"><span data-stu-id="0c920-125">Both master planning and manual scheduling should then produce the same result.</span></span>

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a><span data-ttu-id="0c920-126">A tervezett rendelések akkor jönnek létre, ha a készleten lévő cikkek és termelési rendelések már léteznek.</span><span class="sxs-lookup"><span data-stu-id="0c920-126">Planned orders are generated even though we have items in stock and production orders already exist for them.</span></span>

<span data-ttu-id="0c920-127">Ezt a problémát úgy oldhatja meg, hogy növeli a **Fedezeti csoport** oldalon lévő **Pozitív napok** értékét.</span><span class="sxs-lookup"><span data-stu-id="0c920-127">You might be able to fix this issue by increasing the **Positive days** value for the relevant groups on the **Coverage group** page.</span></span> <span data-ttu-id="0c920-128">Ezen módosítás hatására a rendszer megállapítja, hogy az aktuális készlet használható-e a keresletre.</span><span class="sxs-lookup"><span data-stu-id="0c920-128">This change will cause the system to determine whether on-hand inventory can be used for the demand.</span></span> <span data-ttu-id="0c920-129">Ezután nem jön létre új tervezett rendelés a készleten lévő cikkekhez.</span><span class="sxs-lookup"><span data-stu-id="0c920-129">Then a new planned order won't be generated for the items that are in stock.</span></span>

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a><span data-ttu-id="0c920-130">Úgy tűnik, hogy az alaptervezés nem veszi figyelembe a kapacitáskorlátozásokat, és a rendelkezésre álló kapacitásnál többet ütemez.</span><span class="sxs-lookup"><span data-stu-id="0c920-130">Master planning doesn't seem to respect capacity limitations and is scheduling more than the available capacity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0c920-131">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="0c920-131">Issue description</span></span>

<span data-ttu-id="0c920-132">Ha olyan műveletütemezést használ, ahol véges kapacitás van, és ahol az útvonal egy erőforráscsoport és az egyes erőforrások követelményeinek kombinációját meghatározza, akkor kis esély van a túlfoglalásra, mivel az algoritmus a kapacitásütközéseket figyelembe véve érvényesít.</span><span class="sxs-lookup"><span data-stu-id="0c920-132">When you use operation scheduling where there is finite capacity, and where the route specifies a mix of requirements for both a resource group and individual resources, there is a small chance of overbooking because of the way that the algorithm validates for capacity conflicts.</span></span> <span data-ttu-id="0c920-133">Ez a túlfoglalás akkor fordulhat elő, ha segédalkalmazásokkal futtatja az alaptervezést.</span><span class="sxs-lookup"><span data-stu-id="0c920-133">This overbooking can occur when you use helpers to run master planning.</span></span> <span data-ttu-id="0c920-134">Ez leginkább akkor fordul elő, ha sok olyan feladat van, amelyeknek viszonylag rövid a futásidejű.</span><span class="sxs-lookup"><span data-stu-id="0c920-134">It's most likely to occur if there are many jobs that have a relatively short runtime.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0c920-135">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="0c920-135">Issue resolution</span></span>

<span data-ttu-id="0c920-136">Ha elengedhetetlen, hogy a műveletütemezéshez ne legyen túlfoglalás, az alaptervezés ütemezését egyszálassá teheti, ha bekapcsolja a **Műveletütemezéshez való pontos, véges kapacitás** beállítást az **Alaptervezési paraméterek** lapon.</span><span class="sxs-lookup"><span data-stu-id="0c920-136">If it's essential that no overbooking occur for operation scheduling, you can make the scheduling part of master planning single-threaded by turning on the **Accurate finite capacity for Operation Scheduling** option on the **Master planning parameters** page.</span></span> <span data-ttu-id="0c920-137">Ez a beállítás nem érhető el alapértelmezetten.</span><span class="sxs-lookup"><span data-stu-id="0c920-137">This option isn't available by default.</span></span> <span data-ttu-id="0c920-138">A személyre szabási funkciók használatával manuálisan kell hozzáadnia az oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="0c920-138">You must manually add it to the page by using personalization features.</span></span> <span data-ttu-id="0c920-139">Ha ezt a beállítást használja, az ütemezés lassabban fog futni a párhuzamos feldolgozás hiánya miatt.</span><span class="sxs-lookup"><span data-stu-id="0c920-139">When you use this option, scheduling will run more slowly because of the lack of parallel processing.</span></span>

## <a name="planned-orders-take-a-long-time-to-update"></a><span data-ttu-id="0c920-140">A tervezett rendelések frissítése hosszú időt vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="0c920-140">Planned orders take a long time to update.</span></span>

### <a name="issue-description"></a><span data-ttu-id="0c920-141">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="0c920-141">Issue description</span></span>

<span data-ttu-id="0c920-142">A szükséglet mennyiségének és/vagy szállítási dátumának tervezett rendelésen történő frissítésekor általában rendelésenként legalább 30 másodpercet vesz igénybe a frissítés mentése.</span><span class="sxs-lookup"><span data-stu-id="0c920-142">When updating the requirement quantity and/or delivery date on a planned order, it typically takes at least 30 seconds per order to save the update.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="0c920-143">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="0c920-143">Issue resolution</span></span>

<span data-ttu-id="0c920-144">Ez egy ismert probléma a beépített fő tervezőmotorral.</span><span class="sxs-lookup"><span data-stu-id="0c920-144">This is a known issue with the built-in master planning engine.</span></span> <span data-ttu-id="0c920-145">Ezt az okozza, hogy az anyagjegyzékstruktúrán keresztül a szerkesztések során automatikusan alá van bontva.</span><span class="sxs-lookup"><span data-stu-id="0c920-145">It is caused by the underlying auto explosion through the BOM structure during edits.</span></span> <span data-ttu-id="0c920-146">Ezzel a problémával részletesebben a Tervezés optimalizálása című részben olvashat, ahol a tervező frissítheti és jóváhagyhatja a megfelelő rendeléseket, és szükség esetén tervezési futtatást indíthat el a mögöttes anyagjegyzékstruktúra tervezett rendeléseinek frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="0c920-146">This issue is addressed in Planning Optimization, where a planner can update and approve the relevant orders and, when desired, trigger a planning run to update planned orders for the underlying BOM structure.</span></span>

<span data-ttu-id="0c920-147">A beépített fő tervezőmotorral a teljesítmény javításának egyik módja a következő:</span><span class="sxs-lookup"><span data-stu-id="0c920-147">One way to improve performance with the built-in master planning engine is to do the following:</span></span>

1. <span data-ttu-id="0c920-148">Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c920-148">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="0c920-149">Válasszon egy tervet.</span><span class="sxs-lookup"><span data-stu-id="0c920-149">Select a plan.</span></span>
1. <span data-ttu-id="0c920-150">Bontsa ki az **Időkorlátot napokban** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="0c920-150">Expand the **Time fence in days** FastTab.</span></span>
1. <span data-ttu-id="0c920-151">Állítsa az **Alábontás** beállítást *Igen* értékre, és állítsa a beállítás alatti mezőt 0-ra (nulla).</span><span class="sxs-lookup"><span data-stu-id="0c920-151">Set **Explosion** to *Yes*, and set the field below this setting to 0 (zero).</span></span>

> [!NOTE]
> <span data-ttu-id="0c920-152">Ez egyetlen napra korlátozza az alaptervben végrehajtott alábontások időszakát.</span><span class="sxs-lookup"><span data-stu-id="0c920-152">This will limit the period for explosions performed for this master plan to a single day.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
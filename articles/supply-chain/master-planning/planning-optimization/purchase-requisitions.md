---
title: Beszerzési igénylések
description: Ez a témakör azt ismerteti, hogyan támogatottak a beszerzési igénylések a tervezési optimalizálásban.
author: ChristianRytt
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8075f8d7c3868c6d6012edbce17dbbb4749209ab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992344"
---
# <a name="purchase-requisitions"></a><span data-ttu-id="e0b5c-103">Beszerzési igénylések</span><span class="sxs-lookup"><span data-stu-id="e0b5c-103">Purchase requisitions</span></span>

<span data-ttu-id="e0b5c-104">Az alaptervezés feltöltheti a jóváhagyott beszerzési igényléseket.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-104">Master planning can replenish approved purchase requisitions.</span></span> <span data-ttu-id="e0b5c-105">A beszerzési igénylések fedezésére tehát a felhasználóknak nem kell munkafolyamatot használni a beszerzési igénylések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-105">Therefore, to cover purchase requisitions, users don't have to use a workflow to create purchase orders.</span></span> <span data-ttu-id="e0b5c-106">Ehelyett az alaptervezés fedezheti a beszerzési igényléseket.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-106">Instead, purchase requisitions can be covered by master planning.</span></span> <span data-ttu-id="e0b5c-107">A funkciók miatt a beszerzési igénylések a kapcsolódó termék beállított **Tervezett rendelési típusától** függően beszerzési igénylést, átmozgatási rendelést vagy termelési rendelést is előállíthat.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-107">Because of this functionality, a purchase requisition can produce a purchase order, a transfer order, or a production order, depending on the **Planned order type** value that is set for the related product.</span></span>

## <a name="enable-master-plans-to-include-requisitions"></a><span data-ttu-id="e0b5c-108">Alaptervek engedélyezése az igénylések belefoglalásához</span><span class="sxs-lookup"><span data-stu-id="e0b5c-108">Enable master plans to include requisitions</span></span>

<span data-ttu-id="e0b5c-109">Ha az igényléseket is figyelembe kell venni az alapterv fedezetszámítása során, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-109">To include requisitions during the coverage calculation for a master plan, follow these steps.</span></span>

1. <span data-ttu-id="e0b5c-110">Ugorjon az **Alaptervezés** \> **Beállítás** \> **Tervek** \> **Alaptervezések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-110">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="e0b5c-111">Hozzon létre vagy válasszon egy alaptervet.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-111">Create or select a master plan.</span></span>
1. <span data-ttu-id="e0b5c-112">Az **Általános** gyorslapon állítsa az **Igénylések befoglalása** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-112">On the **General** FastTab, set the **Include requisitions** option to *Yes*.</span></span>
1. <span data-ttu-id="e0b5c-113">Ismételje meg a 2. és 3. lépést minden további olyan alaptervre, amelyben szerepeltetni szeretné az igényléseket.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-113">Repeat steps 2 and 3 for each additional master plan where you want to include requisitions.</span></span>

## <a name="approved-requisitions-time-fence"></a><span data-ttu-id="e0b5c-114">Jóváhagyott igénylések időkorlátja</span><span class="sxs-lookup"><span data-stu-id="e0b5c-114">Approved requisitions time fence</span></span>

<span data-ttu-id="e0b5c-115">A *jóváhagyott igénylések időkorlátja* meghatározza, hogy az alapterv mennyire visszamenőleg (napokban) fogja tartalmazni a jóváhagyott feltöltési igénylések iránti igényt.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-115">The *approved requisitions time fence* establishes how far back (in days) a master plan will include demand from approved replenishment requisitions.</span></span> <span data-ttu-id="e0b5c-116">A jóváhagyott igénylések időkorlátját mind a fedezeti csoport szintjén, mind az alapterv szintjén be lehet állítani.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-116">You can set an approved requisitions time fence at both the coverage group level and the master plan level.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a><span data-ttu-id="e0b5c-117">A jóváhagyott igénylési időkorlát beállítása fedezeti csoporthoz</span><span class="sxs-lookup"><span data-stu-id="e0b5c-117">Set the approved requisitions time fence for a coverage group</span></span>

1. <span data-ttu-id="e0b5c-118">Ugorjon az **Alaptervezés** \> **Beállítás** \> **Fedezet** \> **Fedezeti csoportok** menübe.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-118">Go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage group**.</span></span>
1. <span data-ttu-id="e0b5c-119">Hozzon létre vagy válasszon ki egy fedezeti csoportot.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-119">Create or select a coverage group.</span></span>
1. <span data-ttu-id="e0b5c-120">Állítsa a **Jóváhagyott igénylések időkorlátja (napok)** mezőt az **Egyéb** gyorslapon az időkorlátba belefoglalandó napok számára.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-120">On the **Other** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="e0b5c-121">Ismételje meg a 2. és 3. lépést minden olyan további fedezetcsoportra, ahol be szeretné állítani a jóváhagyott igénylések időkorlátját.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-121">Repeat steps 2 and 3 for each additional coverage group where you want to set an approved requisitions time fence.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a><span data-ttu-id="e0b5c-122">A jóváhagyott igénylések időkorlátjának beállítása egyedi alaptervekhez</span><span class="sxs-lookup"><span data-stu-id="e0b5c-122">Set the approved requisitions time fence for individual master plans</span></span>

<span data-ttu-id="e0b5c-123">Ha egy adott alaptervhez beállít egy jóváhagyott igénylési időkorlátot, akkor a beállítás felülbírálja az esetleges fedezeti csoportok időkorlát-beállítását.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-123">When you set an approved requisitions time fence for an individual master plan, the setting overrides the time fence setting for any applicable coverage group.</span></span>

1. <span data-ttu-id="e0b5c-124">Ugorjon az **Alaptervezés** \> **Beállítás** \> **Tervek** \> **Alaptervezések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-124">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="e0b5c-125">Hozzon létre vagy válasszon egy alaptervet.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-125">Create or select a master plan.</span></span>
1. <span data-ttu-id="e0b5c-126">Állítsa a **Jóváhagyott igénylések időkorlátja (napok)** mezőt az **Időkorlát napokban** gyorslapon az időkorlátba belefoglalandó napok számára.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-126">On the **TIme fences in days** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="e0b5c-127">Ismételje meg a 2. és 3. lépést minden olyan további alaptervre, ahol be szeretné állítani a jóváhagyott igénylések időkorlátját.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-127">Repeat steps 2 and 3 for each additional master plan where you want to set an approved requisitions time fence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0b5c-128">**Hamarosan:** A jóváhagyott igénylések időkorlátja még nem támogatott a tervezési optimalizálásban.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-128">**Coming soon:** Approved requisitions time fences aren't yet supported for Planning Optimization.</span></span> <span data-ttu-id="e0b5c-129">Amíg nem válnak támogatottá, a rendszer figyelmen kívül hagyja a **Jóváhagyott igénylések időkorlátja (napok)** mezőbe beírt összes értéket.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-129">Until they are supported, all values that you enter in the **Approved requisitions time fence (days)** field will be ignored.</span></span>

## <a name="independent-supply-regardless-of-coverage-code"></a><span data-ttu-id="e0b5c-130">Önálló készlet a fedezeti kódtól függetlenül</span><span class="sxs-lookup"><span data-stu-id="e0b5c-130">Independent supply, regardless of coverage code</span></span>

<span data-ttu-id="e0b5c-131">A beszerzési igényléseket mindig önálló tervezett rendelések fedezik, függetlenül a fedezeti kódtól.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-131">Purchase requisitions are always covered by independent planned orders, regardless of the coverage code.</span></span> <span data-ttu-id="e0b5c-132">Ez a viselkedés gondoskodik a beszerzési igénylések és a feltöltési rendelések közötti egyértelmű nyomon követhetőségről és munkafolyamatokról.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-132">This behavior ensures clear traceability and workflows between purchase requisitions and replenishment orders.</span></span>

### <a name="example-1"></a><span data-ttu-id="e0b5c-133">1. példa</span><span class="sxs-lookup"><span data-stu-id="e0b5c-133">Example 1</span></span>

<span data-ttu-id="e0b5c-134">Egy termék úgy van beállítva, hogy a **Fedezeti kód** értéke *Min/max*. A következő készlet- és igénylési állapotokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="e0b5c-134">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="e0b5c-135">Aktuális készletmennyiség = 10.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-135">Inventory on-hand quantity = 10.</span></span>
- <span data-ttu-id="e0b5c-136">Minimális készletmennyiség = 15.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-136">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="e0b5c-137">Maximális készletmennyiség = 20.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-137">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="e0b5c-138">Akár egy darabhoz is megadható beszerzési igénylés.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-138">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="e0b5c-139">A kért dátuma a mai.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-139">It has a requested date of today.</span></span>

<span data-ttu-id="e0b5c-140">Az alaptervezés futtatásakor két tervezett rendelés jön létre: egy a készlet maximális mennyiségre való feltöltéséhez szükséges 10 darabhoz és egy darab a beszerzési igénylés feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-140">When master planning runs, two planned orders are created: one for 10 pieces to replenish inventory to the maximum quantity, and one for one piece to replenish the purchase requisition.</span></span>

### <a name="example-2"></a><span data-ttu-id="e0b5c-141">2. példa</span><span class="sxs-lookup"><span data-stu-id="e0b5c-141">Example 2</span></span>

<span data-ttu-id="e0b5c-142">Egy termék úgy van beállítva, hogy a **Fedezeti kód** értéke *Min/max*. A következő készlet- és igénylési állapotokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="e0b5c-142">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="e0b5c-143">Aktuális készletmennyiség = 17.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-143">Inventory on-hand quantity = 17.</span></span>
- <span data-ttu-id="e0b5c-144">Minimális készletmennyiség = 15.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-144">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="e0b5c-145">Maximális készletmennyiség = 20.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-145">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="e0b5c-146">Akár egy darabhoz is megadható beszerzési igénylés.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-146">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="e0b5c-147">A kért dátuma a mai.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-147">It has a requested date of today.</span></span>

<span data-ttu-id="e0b5c-148">Az alaptervezés futtatásakor egy darabra vonatkozó tervezett rendelés jön létre a beszerzési igénylés feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-148">When master planning runs, one planned order for one piece is created to replenish the purchase requisition.</span></span>

### <a name="example-3"></a><span data-ttu-id="e0b5c-149">3. példa</span><span class="sxs-lookup"><span data-stu-id="e0b5c-149">Example 3</span></span>

<span data-ttu-id="e0b5c-150">Egy termék úgy van beállítva, hogy **Időszak** értékű *Fedezetti kóddal* rendelkezik, és az időszak hossza hét nap.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-150">A product is set up so that it has a **Coverage code** value of *Period* and a period length of seven days.</span></span> <span data-ttu-id="e0b5c-151">A következő készlet-, értékesítési és igénylési állapotokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="e0b5c-151">It has the following inventory, sales order, and requisition statuses:</span></span>

- <span data-ttu-id="e0b5c-152">Aktuális készletmennyiség = 0.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-152">Inventory on-hand quantity = 0.</span></span>
- <span data-ttu-id="e0b5c-153">Akár öt darabhoz is megadható értékesítési rendelés.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-153">A sales order for five pieces exists.</span></span> <span data-ttu-id="e0b5c-154">A várható szállítási dátuma a maihoz képest plusz egy nap.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-154">It has an expected ship date of today plus one day.</span></span>
- <span data-ttu-id="e0b5c-155">Akár három darabhoz is megadható beszerzési igénylés.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-155">A purchase requisition for three pieces exists.</span></span> <span data-ttu-id="e0b5c-156">A kért dátuma a maihoz képest plusz három nap.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-156">It has a requested date of today plus three days.</span></span>

<span data-ttu-id="e0b5c-157">Az alaptervezés futtatásakor két tervezett rendelés jön létre: egy a beszerzési igénylés feltöltéséhez szükséges három darabhoz és egy az értékesítési igénylés öt darabjának feltöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-157">When master planning runs, two planned orders are created: one for three pieces to replenish the purchase requisition and one for five pieces to replenish sales order demand.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b5c-158">Miután a beszerzési igényléshez rögzített tervezett rendelést megerősítik, a tervezőmotor megtartja az igénykövetést a beszerzési igényléshez.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-158">After a planned order that is pegged to a purchase requisition is firmed, the planning engine keeps the pegging to the purchase requisition.</span></span> <span data-ttu-id="e0b5c-159">Ha a megerősített rendelésben később hiányzó mennyiséget találnak a beszerzési igénylés teljesítéséhez, a rendszer új tervezett rendelést hoz létre a különbözethez.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-159">If the firmed order is later found to be missing some quantity that is required to fulfill the purchase requisition, the system will create a new planned order for the difference.</span></span>

<span data-ttu-id="e0b5c-160">A beszerzési igénylésekkel kapcsolatos tudnivalókért lásd: [Beszerzési igénylés áttekintése](../../procurement/purchase-requisitions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0b5c-160">For more information about purchase requisitions, see [Purchase requisition overview](../../procurement/purchase-requisitions-overview.md).</span></span>

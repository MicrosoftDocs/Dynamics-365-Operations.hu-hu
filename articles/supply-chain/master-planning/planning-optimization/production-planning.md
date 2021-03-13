---
title: Termeléstervezés
description: Ez a témakör a termelés tervezését írja le, és bemutatja, hogyan lehet módosítani a tervezett termelési rendeléseket a Tervezési optimalizálás segítségével.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
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
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: eda22aa6f1e8d665d8ef390f24b247a76d4c2956
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992395"
---
# <a name="production-planning"></a><span data-ttu-id="04cee-103">Termeléstervezés</span><span class="sxs-lookup"><span data-stu-id="04cee-103">Production planning</span></span>

<span data-ttu-id="04cee-104">A tervezési optimalizálások több termelési helyzetet is támogatnak.</span><span class="sxs-lookup"><span data-stu-id="04cee-104">Planning Optimizations supports several production scenarios.</span></span> <span data-ttu-id="04cee-105">Ha egy meglévő, beépített alaptervezési motorról tér át, fontos, hogy tisztában legyen a némiképp megváltozott viselkedéssel.</span><span class="sxs-lookup"><span data-stu-id="04cee-105">If you're migrating from the existing, built-in master planning engine, it's important that you be aware of some changed behavior.</span></span>

<!-- The following video gives a short introduction to some of the current capabilities. 
KFM: Link to video for production functionality, coming soon... -->

## <a name="planned-production-orders"></a><span data-ttu-id="04cee-106">Terv. term. rendelések</span><span class="sxs-lookup"><span data-stu-id="04cee-106">Planned production orders</span></span>

<span data-ttu-id="04cee-107">Amikor az alaptervezés tervezett rendeléseket hoz létre a követelmények kielégítése érdekében, a rendelés típusát a **Tervezett rendeléstípus** mező értéke határozza meg.</span><span class="sxs-lookup"><span data-stu-id="04cee-107">When master planning creates planned orders to fulfill requirements, the order type is determined by the value of the **Planned order type** field.</span></span> <span data-ttu-id="04cee-108">Ha a **Tervezett rendelés típusa** mező beállítása *Termelés*, akkor létrejönnek a tervezett termelési rendelések.</span><span class="sxs-lookup"><span data-stu-id="04cee-108">If the **Planned order type** field is set to *Production*, planned production orders are created.</span></span> <span data-ttu-id="04cee-109">Ezek a tervezett termelési rendelések az aktív anyagjegyzékről (BOM) és a kapcsolódó termelési beállításból származó útvonal-azonosítóról tartalmaznak információkat.</span><span class="sxs-lookup"><span data-stu-id="04cee-109">These planned production orders include information about the active bill of materials (BOM) and the route ID from the related production setup.</span></span>

## <a name="requirements-from-boms"></a><span data-ttu-id="04cee-110">Követelmények az anyagjegyzékekből</span><span class="sxs-lookup"><span data-stu-id="04cee-110">Requirements from BOMs</span></span>

<span data-ttu-id="04cee-111">Az anyagjegyzék-adatokat figyelembe veszik az alaptervezés során.</span><span class="sxs-lookup"><span data-stu-id="04cee-111">BOM information is honored during master planning.</span></span> <span data-ttu-id="04cee-112">A terv kimenete tartalmazza az anyagellátást, amely fedezi a kapcsolódó termelési anyagigényt.</span><span class="sxs-lookup"><span data-stu-id="04cee-112">The plan output includes material supply to cover related material demand for production.</span></span>

<span data-ttu-id="04cee-113">Az alaptervezés során az aktuális, aktív anyagjegyzék használatos a termeléshez szükséges anyagok meghatározására.</span><span class="sxs-lookup"><span data-stu-id="04cee-113">During master planning, the current, active BOM is used to determine the materials that are required for production.</span></span> <span data-ttu-id="04cee-114">Ez a lépés az anyagjegyzék-szerkezetnek a szükséges termelési rendeléshez kapcsolódó összes szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="04cee-114">This step is done through all levels of the BOM structure that is related to the required production order.</span></span> <span data-ttu-id="04cee-115">Az anyagszükséglet kielégítése az elérhető aktuális készletből, a meglévő rendelési készletekből és a jóváhagyott tervezett rendelésekből történik.</span><span class="sxs-lookup"><span data-stu-id="04cee-115">Material requirement is fulfilled by using available on-hand inventory, existing on-order supply, and approved planned orders.</span></span> <span data-ttu-id="04cee-116">Ha bárhol további anyag szükséges, egy tervezett rendelés jön létre az igény fedezése érdekében.</span><span class="sxs-lookup"><span data-stu-id="04cee-116">If additional material is required anywhere, a planned order is created to cover the demand.</span></span>

## <a name="scheduling-during-firming"></a><span data-ttu-id="04cee-117">Ütemezés megerősítés során</span><span class="sxs-lookup"><span data-stu-id="04cee-117">Scheduling during firming</span></span>

<span data-ttu-id="04cee-118">A tervezett termelési rendelések tartalmazzák a termelés ütemezéséhez szükséges útvonal-azonosítót.</span><span class="sxs-lookup"><span data-stu-id="04cee-118">Planned production orders include the route ID that is required for production scheduling.</span></span> <span data-ttu-id="04cee-119">A tervezett rendelések tervezett futtatása során azonban függőben van az ütemezés támogatása.</span><span class="sxs-lookup"><span data-stu-id="04cee-119">However, scheduling support during the planning run for planned orders is pending.</span></span> <span data-ttu-id="04cee-120">Az útvonal-azonosító a tervezett termelési rendelések ütemezésére használható a megerősítés során.</span><span class="sxs-lookup"><span data-stu-id="04cee-120">The route ID is used to schedule planned production orders during firming.</span></span> <span data-ttu-id="04cee-121">Ennek megfelelően a tervezett termelési rendelések átfutási ideje eltérhet a kapcsolódó ütemezett, megerősített termelési rendelések átfutási idejétől, a következők szerint:</span><span class="sxs-lookup"><span data-stu-id="04cee-121">Therefore, the lead time on planned production orders can differ from the lead time on related scheduled, firmed production orders that are generated from them, as described here:</span></span>

- <span data-ttu-id="04cee-122">**Tervezett termelési rendelés** – Az átfutási idő a kiadott termékből származó statikus átfutási időn alapul.</span><span class="sxs-lookup"><span data-stu-id="04cee-122">**Planned production order** – The lead time is based on the static lead time from the released product.</span></span>
- <span data-ttu-id="04cee-123">**Visszaszorítású termelési rendelés** – Az átfutási idő az útvonal-információkat és a kapcsolódó erőforrásmegszorításokat használó ütemezésen alapul.</span><span class="sxs-lookup"><span data-stu-id="04cee-123">**Firmed production order** – The lead time is based on scheduling that uses route information and related resource constraints.</span></span>

<span data-ttu-id="04cee-124">A szolgáltatások várható elérhetőségével kapcsolatos további tudnivalókat lásd a [Tervezési optimalizálás igazítási elemzés](planning-optimization-fit-analysis.md)oldalon.</span><span class="sxs-lookup"><span data-stu-id="04cee-124">For more information about expected feature availability, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

<span data-ttu-id="04cee-125">Ha olyan termelési funkcióktól függ, amelyek még nem állnak rendelkezésre tervezési optimalizáláshoz, akkor továbbra is használhatja a beépített alaptervezési motort.</span><span class="sxs-lookup"><span data-stu-id="04cee-125">If you depend on production functionality that isn't yet available for Planning Optimization, you can continue to use the built-in master planning engine.</span></span> <span data-ttu-id="04cee-126">Nincs szükség kivételre.</span><span class="sxs-lookup"><span data-stu-id="04cee-126">No exception is required.</span></span>

## <a name="delays"></a><span data-ttu-id="04cee-127">Késések</span><span class="sxs-lookup"><span data-stu-id="04cee-127">Delays</span></span>

<span data-ttu-id="04cee-128">Ha a szükséges anyag átfutási ideje hosszabb a mai dátum és az anyagszükséglet dátuma közötti időszaknál, akkor a szükséges anyag és a kapcsolódó termelési rendelés tervezett rendelése késik.</span><span class="sxs-lookup"><span data-stu-id="04cee-128">If the lead time for required material is longer than the period between today's date and the material requirement date, the planned order for the required material and the related production order will be delayed.</span></span> <span data-ttu-id="04cee-129">Tervezett rendelések esetén a késleltetés (napokban) számítása a kiadott termék átfutási ideje alapján történik.</span><span class="sxs-lookup"><span data-stu-id="04cee-129">For planned orders, the delay (in days) is calculated based on the lead time from the released product.</span></span> <span data-ttu-id="04cee-130">A késleltetési adatok ezután az anyagjegyzék-szerkezet összes szintjén keresztül továbbterjednek.</span><span class="sxs-lookup"><span data-stu-id="04cee-130">The delay information is then propagated through all levels of the BOM structure.</span></span> <span data-ttu-id="04cee-131">Így végigkövetheti a késleltetett nyersanyag kihatását a vevői értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="04cee-131">Therefore, you can follow the impact of delayed raw material all the way to the customer sales order.</span></span>

## <a name="modifying-planned-orders"></a><span data-ttu-id="04cee-132">Tervezett rendelések módosítása</span><span class="sxs-lookup"><span data-stu-id="04cee-132">Modifying planned orders</span></span>

<span data-ttu-id="04cee-133">Ha módosítja egy tervezett rendelés adatait, a következő üzenet jelenik meg: „Ne feledje, hogy a következő alaptervezés futtatásáig a terv többi részében nem fog tükröződni a manuális módosítások hatása a tervezett rendelésekre.”</span><span class="sxs-lookup"><span data-stu-id="04cee-133">When you change information on a planned order, you receive the following message: "Note that the impact of manual changes on planned orders won't be reflected in the rest of the plan until the next master planning run."</span></span>

<span data-ttu-id="04cee-134">Ha módosítani szeretné a tervezett rendelés adatait, és látni szeretné a kapcsolódó anyagkövetelmények hatását, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="04cee-134">If you want to change information on a planned order and see the impact on the related material requirements, follow these steps.</span></span>

1. <span data-ttu-id="04cee-135">Frissítse a tervezett rendelést.</span><span class="sxs-lookup"><span data-stu-id="04cee-135">Update the planned order.</span></span>
2. <span data-ttu-id="04cee-136">Hagyja jóvá a tervezett rendelést.</span><span class="sxs-lookup"><span data-stu-id="04cee-136">Approve the planned order.</span></span>
3. <span data-ttu-id="04cee-137">Futtassa az alaptervezést.</span><span class="sxs-lookup"><span data-stu-id="04cee-137">Run master planning.</span></span>

<span data-ttu-id="04cee-138">Az alaptervezés futtatásakor nem szabad szűrőket használni, ha szerepel benne tervezett termelési rendelés.</span><span class="sxs-lookup"><span data-stu-id="04cee-138">When you run master planning, you should not use filters if planned production orders are included.</span></span> <span data-ttu-id="04cee-139">További tudnivalókat a [Szűrők](#filters) részben olvashat, a témakör későbbi részében.</span><span class="sxs-lookup"><span data-stu-id="04cee-139">For more information, see the [Filters](#filters) section later in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="04cee-140">Ha a tervezett rendelés szállítási dátumát későbbi dátumra módosították, akkor előfordulhat, hogy az igény egy új tervezett rendeléshez lesz hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="04cee-140">If the delivery date of the planned order is changed to a later date, the demand might be pegged against a new planned order.</span></span> <span data-ttu-id="04cee-141">Ez a viselkedés akkor fordul elő, amikor az új ellátási dátum késést okoz a követett igényhez, de az átfutási idő beállításai szerint a késleltetés elkerülhető.</span><span class="sxs-lookup"><span data-stu-id="04cee-141">This behavior occurs when the new supply date causes a delay for the pegged demand but, according to the lead time settings, the delay can be avoided.</span></span>

## <a name="explosion-page"></a><span data-ttu-id="04cee-142">Alábontás lap</span><span class="sxs-lookup"><span data-stu-id="04cee-142">Explosion page</span></span>

<span data-ttu-id="04cee-143">Az **Alábontás** lap használatával elemezni lehet egy adott termelési rendelés vagy tervezett termelési rendelés igényét, a kapcsolódó fedezetet és az igénykövetési adatokat.</span><span class="sxs-lookup"><span data-stu-id="04cee-143">You can use the **Explosion** page to analyze the demand that is required for a specific production order or planned production order, the related coverage, and pegging information.</span></span> <span data-ttu-id="04cee-144">Az **Alábontás** lapon az alaptervezés során frissülnek az adatok.</span><span class="sxs-lookup"><span data-stu-id="04cee-144">Information on the **Explosion** page is updated during master planning.</span></span> <span data-ttu-id="04cee-145">Az információk nem frissíthetőek közvetlenül az **Alábontás** lapon.</span><span class="sxs-lookup"><span data-stu-id="04cee-145">You can't update the information directly from the **Explosion** page.</span></span>

## <a name="filters"></a><a name="filters"></a><span data-ttu-id="04cee-146">Szűrők</span><span class="sxs-lookup"><span data-stu-id="04cee-146">Filters</span></span>

<span data-ttu-id="04cee-147">A termelést is magukban foglaló tervezési eseteknél javasoljuk, hogy kerülje el a szűrt alaptervezési futtatásokat.</span><span class="sxs-lookup"><span data-stu-id="04cee-147">For planning scenarios that include production, we recommend that you avoid filtered master planning runs.</span></span> <span data-ttu-id="04cee-148">Annak érdekében, hogy a tervezési optimalizálás a helyes eredmény kiszámításához szükséges információkat tartalmazza, minden olyan terméket bele kell foglalnia a tervezett rendelés teljes anyagjegyzék-struktúrájába, amely bármilyen kapcsolatban áll a termékekkel.</span><span class="sxs-lookup"><span data-stu-id="04cee-148">To ensure that Planning Optimization has the information that is required to calculate the correct result, you must include all products that have any relation to products in the whole BOM structure of the planned order.</span></span>

<span data-ttu-id="04cee-149">Bár a rendszer automatikusan észleli a függő gyermekeket, és bekerül az alaptervezésbe a beépített alaptervezési motor használata esetén, a tervezési optimalizálás nem végzi el ezt a műveletet.</span><span class="sxs-lookup"><span data-stu-id="04cee-149">Although dependent child items are automatically detected and included in master planning runs when the built-in master planning engine is used, Planning Optimization doesn't perform this action.</span></span>

<span data-ttu-id="04cee-150">Ha például az A termék anyagjegyzék-szerkezetében egy csavar a B termék előállítására is használatos, akkor a szűrőben szerepelnie kell az A és a B termék anyagjegyzék-szerkezetében található összes terméknek.</span><span class="sxs-lookup"><span data-stu-id="04cee-150">For example, if a single bolt from the BOM structure of product A is also used to produce product B, all products in the BOM structure of products A and B must be included in the filter.</span></span> <span data-ttu-id="04cee-151">Mivel nagyon bonyolult lehet annak biztosítása, hogy minden termék a szűrő része legyen, javasoljuk, hogy ne használjon szűrőt alaptervezési futtatásoknál termelési rendelések esetén.</span><span class="sxs-lookup"><span data-stu-id="04cee-151">Because it can be very complex to ensure that all products are part of the filter, we recommend that you avoid filtered master planning runs when production orders are involved.</span></span>
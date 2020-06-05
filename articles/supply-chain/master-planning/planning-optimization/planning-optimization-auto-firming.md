---
title: Automatikus megerősítés a tervezési optimalizációval
description: Ez a témakör azt mutatja be, hogyan kell használni az automatikus megerősítést a tervezési optimalizációval.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: e412ccbc7c44d41e0a70ef8b5436901e01c671e6
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383688"
---
# <a name="auto-firming-with-planning-optimization"></a><span data-ttu-id="03034-103">Automatikus megerősítés a tervezési optimalizációval</span><span class="sxs-lookup"><span data-stu-id="03034-103">Auto-firming with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="03034-104">Az automatikus megerősítéssel az Alaptervezési folyamat részeként megerősítheti (azaz kiadhatja) a tervezett rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="03034-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="03034-105">A tervezett rendelések a megerősítéskor tényleges beszerzési rendelésekké, átmozgatási rendelésekké vagy termelési rendelésekké alakulnak át.</span><span class="sxs-lookup"><span data-stu-id="03034-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="03034-106">A tervezés optimalizálása használata során a program a tervezett rendeléseket az Alaptervezés futtatása során megerősíti, amikor a rendelés dátuma (azaz a kezdő dátum) a megerősítés időkorlátján belül van.</span><span class="sxs-lookup"><span data-stu-id="03034-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="03034-107">A tervezett beszerzési rendelés automatikus megerősítése csak akkor lehetséges, ha a cikk társítva van szállítóval.</span><span class="sxs-lookup"><span data-stu-id="03034-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>

## <a name="turn-on-auto-firming"></a><span data-ttu-id="03034-108">Automatikus megerősítés bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="03034-108">Turn on auto-firming</span></span>

<span data-ttu-id="03034-109">Ha be szeretné kapcsolni az automatikus megerősítést, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="03034-109">To turn on auto-firming, follow these steps.</span></span>

1. <span data-ttu-id="03034-110">A **funkciókezelés** munkaterületen az **új** lapon válassza ki a listában az **Automatikus megerősítés a tervezési optimalizációhoz** elemet.</span><span class="sxs-lookup"><span data-stu-id="03034-110">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="03034-111">Ha a funkció nem jelenik meg az **új** lapon, akkor keresse a **nem engedélyezett és** az **Összes** lapon.</span><span class="sxs-lookup"><span data-stu-id="03034-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="03034-112">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="03034-112">Select **Enable now**.</span></span> <span data-ttu-id="03034-113">Azt is megteheti, hogy az **ütemezés** elemet választja, majd azt az időpontot, amikor be kívánja kapcsolni a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="03034-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="03034-114">Állítsa be a megerősítési időkorlátot</span><span class="sxs-lookup"><span data-stu-id="03034-114">Set up the firming time fence</span></span>

<span data-ttu-id="03034-115">A megerősítési időkorlátot a program az alaptervezés-futtatás dátumától kezdődően számítja ki.</span><span class="sxs-lookup"><span data-stu-id="03034-115">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="03034-116">A megadott napok száma alapján kerül meghatározásra.</span><span class="sxs-lookup"><span data-stu-id="03034-116">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="03034-117">A megerősítési időkorlátot a következő módokon lehet szabályozni:</span><span class="sxs-lookup"><span data-stu-id="03034-117">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="03034-118">A fedezeti csoport alapértelmezett megerősítési időkorlátjának megadásához nyissa meg az **Alaptervezés** \> **Beállítás** \> **Fedezet** \> **Fedezeti csoportok**, és válasszon ki egy fedezeti csoportot.</span><span class="sxs-lookup"><span data-stu-id="03034-118">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="03034-119">Ezután a **Egyéb** gyorslap **automatikus megerősítési időkorlátja (nap)** mezőjébe írja be a napok számát.</span><span class="sxs-lookup"><span data-stu-id="03034-119">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="03034-120">Ha felül szeretné írni egy adott cikk fedezeti csoportjához definiált megerősítési időkorlátot, akkor a **Termékadatok kezelése** \> **Kiadott termékek** pontra lépjen, majd a Művelet panelen válassza ki a **Terv** elemet , majd válassza a **Cikk fedezete** elemet.</span><span class="sxs-lookup"><span data-stu-id="03034-120">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the Action Pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="03034-121">Ezután az **Általános** lapon jelölje be az **Időkorlát felülbírálása** elemet, és az **automatikus megerősítés időkorlátja (nap)** mezőben adja meg a napok számát.</span><span class="sxs-lookup"><span data-stu-id="03034-121">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="03034-122">Ha felül szeretné írni a fedezeti csoporthoz tartozó megerősítési időkorlátot és az adott alaptervezéshez tartozó cikkfedezetet, lépjen az **Alaptervezés** \> **Beállítás** \> **Alaptervek** pontra, és válasszon alaptervet.</span><span class="sxs-lookup"><span data-stu-id="03034-122">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="03034-123">Ezután az **Időkorlát napokban** gyorslapon állítsa a **Befagyasztás** értékét **Igen** értékre, majd adja meg a napok számát.</span><span class="sxs-lookup"><span data-stu-id="03034-123">Then, on the **Time fence in days** FastTab, set **Freeze** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="03034-124">Ha az automatikus megerősítés be van kapcsolva egy olyan alaptervezéshez, amely tervezési optimalizációt alkalmaz, az automatikus megerősítési folyamat az automatikus megerősítési beállításnak megfelelően történik.</span><span class="sxs-lookup"><span data-stu-id="03034-124">If auto-firming is turned on for a master planning run that uses Planning Optimization, the auto-firming process is done according to the auto-firming setup.</span></span> <span data-ttu-id="03034-125">Ha nincs bekapcsolva az automatikus megerősítés, vagy ha a tervezés a **nettó szükségletek** oldalon kezdődik, akkor a rendszer kihagyja az automatikus megerősítési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="03034-125">If auto-firming isn't turned on, or if planning is started from the **Net requirements** page, the auto-firming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="03034-126">Tervezés optimalizálása és a beépített Supply Chain Management tervezési motorja</span><span class="sxs-lookup"><span data-stu-id="03034-126">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="03034-127">Mind a tervezés optimalizálása, mind a Microsoft Dynamics 365 Supply Chain Management szolgáltatásba beépített tervezési motor használható a tervezett rendelések automatikus megerősítésére.</span><span class="sxs-lookup"><span data-stu-id="03034-127">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to auto-firm planned orders.</span></span> <span data-ttu-id="03034-128">Vannak azonban fontos eltérések.</span><span class="sxs-lookup"><span data-stu-id="03034-128">However, there are some important differences.</span></span> <span data-ttu-id="03034-129">Mivel például a tervezés optimalizálása a rendelési dátumot (azaz a kezdő dátumot) használja a megerősítendő tervezett rendelések meghatározásához, a beépített Supply Chain Management tervezési motor a követelmény dátumát (azaz a záró dátumot) használja.</span><span class="sxs-lookup"><span data-stu-id="03034-129">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="03034-130">Itt van egy összefoglaló a különbségekről.</span><span class="sxs-lookup"><span data-stu-id="03034-130">Here is a summary of the differences.</span></span>

<span data-ttu-id="03034-131">**Tervezési optimalizálás**</span><span class="sxs-lookup"><span data-stu-id="03034-131">**Planning Optimization**</span></span>

- <span data-ttu-id="03034-132">Az automatikus megerősítés a rendelés dátuma (kezdő dátum) alapján történik.</span><span class="sxs-lookup"><span data-stu-id="03034-132">Auto-firming is based on the order date (start date).</span></span>
- <span data-ttu-id="03034-133">Mivel a rendelés dátuma (kezdő dátum) indítja a megerősítést, nem kell figyelembe vennie az átfutási időt a megerősítési időkorlát részeként.</span><span class="sxs-lookup"><span data-stu-id="03034-133">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="03034-134">Ha az összes olyan rendelést meg szeretné erősíteni, amely az aktuális hét során kezdődik, a megerősítési időkorlátnak egy hétnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="03034-134">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="03034-135">**Beépített Supply Chain Management tervezési motor**</span><span class="sxs-lookup"><span data-stu-id="03034-135">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="03034-136">Az automatikus megerősítés a követelmény dátuma (záró dátum) alapján történik.</span><span class="sxs-lookup"><span data-stu-id="03034-136">Auto-firming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="03034-137">Ha biztosítani szeretné, hogy a rendelések megfelelő időben legyenek megerősítve, a megerősítés időtartamának hosszabbnak kell lennie, mint az átfutási idő.</span><span class="sxs-lookup"><span data-stu-id="03034-137">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="03034-138">Ha az összes olyan rendelést meg szeretné erősíteni, amely az aktuális hét során kezdődik, a megerősítési időkorlátnak az átfutási idő plusz egy hétnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="03034-138">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>

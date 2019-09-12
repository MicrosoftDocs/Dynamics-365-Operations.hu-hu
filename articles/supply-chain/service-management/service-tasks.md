---
title: Szervizfeladatok áttekintése
description: A szervizfeladatok segítségével lehet leírni azt a feladatot, amelyet a szervizrendelés keretében el kell végezni. Ezt az információt a technikusok és a vevők látják.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd7e5293ef506c6d785b420824f2c2a2c96112f7
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865895"
---
# <a name="service-tasks-overview"></a><span data-ttu-id="9f4dd-104">Szervizfeladatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="9f4dd-104">Service tasks overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f4dd-105">A szervizfeladatok segítségével lehet leírni azt a feladatot, amelyet a szervizrendelés keretében el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="9f4dd-106">Ezt az információt a technikusok és a vevők látják.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="9f4dd-107">A szervizfeladatok létrehozására a **Szervizfeladatok** lap használható. A szervizfeladat-kapcsolatok létrehozásával a szervizfeladatokat meghatározott szolgáltatási megállapodáshoz vagy szervizrendeléshez lehet társítani.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="9f4dd-108">Minden alkalommal, amikor létrehozza a szervizfeladatok egy viszonyát, létrehozhatja a következőket is:</span><span class="sxs-lookup"><span data-stu-id="9f4dd-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="9f4dd-109">Belső megjegyzéseket a feladattal kapcsolatban, mint amilyenek az egy technikus számára lényeges, részletezett műszaki elvárások.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="9f4dd-110">Külső megjegyzések, amelyek láthatók a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-110">External notes that the customer can see.</span></span> <span data-ttu-id="9f4dd-111">Ezek a vevő és a szolgáltató vállalat megállapodása szerint elvégzendő feladatokról adnak egy kevésbé műszaki jellegű magyarázatot.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="9f4dd-112">Ha beállította a szolgáltatásifeladat‑kapcsolatokat a szervizfeladatok és a szervizrendelés vagy szolgáltatás szerződés között, megadhatja ezt a szolgáltatási feladatot, amikor az aktuális szervizrendelés vagy szolgáltatási szerződés számára szervizrendelési sort vagy szolgáltatási szerződéssort hoz létre.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="9f4dd-113">Amikor szervizrendelési sorokat generál egy szolgáltatási szerződésből, a szolgáltatási szerződés egyes soraihoz rendelt szervizfeladatokat felhasználva csoportosíthatja a szervizrendelési sorokat szervizrendelésekbe.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="9f4dd-114">Szervizfeladat létrehozása</span><span class="sxs-lookup"><span data-stu-id="9f4dd-114">Create a service task</span></span>

1. <span data-ttu-id="9f4dd-115">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szervizfeladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="9f4dd-116">Hozzon létre egy új sort.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-116">Create a new line.</span></span>
3. <span data-ttu-id="9f4dd-117">Adja meg a szolgáltatás azonosítóját és leírását.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="9f4dd-118">Példa</span><span class="sxs-lookup"><span data-stu-id="9f4dd-118">Example</span></span>

<span data-ttu-id="9f4dd-119">Egy technikusnak két feladatot kell elvégeznie egy sebességváltón (GB-1234-as szolgáltatási tárgy) az egyik vevő telephelyén.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="9f4dd-120">Egy, a vevőhöz tartozó szolgáltatási szerződés jön létre, és több tranzakció lesz a munkákhoz társítva.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="9f4dd-121">A két munkához tartozó szolgáltatási szerződés és a szerződési sorok a következőkben láthatók:</span><span class="sxs-lookup"><span data-stu-id="9f4dd-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="9f4dd-122">Szolgáltatási szerződés</span><span class="sxs-lookup"><span data-stu-id="9f4dd-122">Service agreement</span></span>

| <span data-ttu-id="9f4dd-123">Project</span><span class="sxs-lookup"><span data-stu-id="9f4dd-123">Project</span></span> | <span data-ttu-id="9f4dd-124">Szolgáltatási szerződés</span><span class="sxs-lookup"><span data-stu-id="9f4dd-124">Service agreement</span></span> | <span data-ttu-id="9f4dd-125">Leírás</span><span class="sxs-lookup"><span data-stu-id="9f4dd-125">Description</span></span>                                  | <span data-ttu-id="9f4dd-126">Csoport</span><span class="sxs-lookup"><span data-stu-id="9f4dd-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="9f4dd-127">9012</span><span class="sxs-lookup"><span data-stu-id="9f4dd-127">9012</span></span>    | <span data-ttu-id="9f4dd-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="9f4dd-128">000008\_001</span></span>       | <span data-ttu-id="9f4dd-129">Átvizsgálás és rendszeres cserék – GB-1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="9f4dd-130">Prémium</span><span class="sxs-lookup"><span data-stu-id="9f4dd-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="9f4dd-131">Szolgáltatási szerződés sorai</span><span class="sxs-lookup"><span data-stu-id="9f4dd-131">Service agreement lines</span></span>

| <span data-ttu-id="9f4dd-132">Leírás</span><span class="sxs-lookup"><span data-stu-id="9f4dd-132">Description</span></span>             | <span data-ttu-id="9f4dd-133">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="9f4dd-133">Transaction type</span></span> | <span data-ttu-id="9f4dd-134">A szolgáltatás tárgya</span><span class="sxs-lookup"><span data-stu-id="9f4dd-134">Service object</span></span> | <span data-ttu-id="9f4dd-135">Szervizfeladat</span><span class="sxs-lookup"><span data-stu-id="9f4dd-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="9f4dd-136">Átvizsgálás és tisztítás</span><span class="sxs-lookup"><span data-stu-id="9f4dd-136">Inspection and cleaning</span></span> | <span data-ttu-id="9f4dd-137">Óra</span><span class="sxs-lookup"><span data-stu-id="9f4dd-137">Hour</span></span>             | <span data-ttu-id="9f4dd-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-138">GB-1234</span></span>        | <span data-ttu-id="9f4dd-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-139">I/C - GB1234</span></span> |
| <span data-ttu-id="9f4dd-140">Utazás</span><span class="sxs-lookup"><span data-stu-id="9f4dd-140">Travel</span></span>                  | <span data-ttu-id="9f4dd-141">Expense</span><span class="sxs-lookup"><span data-stu-id="9f4dd-141">Expense</span></span>          | <span data-ttu-id="9f4dd-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-142">GB-1234</span></span>        | <span data-ttu-id="9f4dd-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-143">I/C - GB1234</span></span> |
| <span data-ttu-id="9f4dd-144">Anyagok</span><span class="sxs-lookup"><span data-stu-id="9f4dd-144">Materials</span></span>               | <span data-ttu-id="9f4dd-145">Tétel</span><span class="sxs-lookup"><span data-stu-id="9f4dd-145">Item</span></span>             | <span data-ttu-id="9f4dd-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-146">GB-1234</span></span>        | <span data-ttu-id="9f4dd-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-147">I/C - GB1234</span></span> |
| <span data-ttu-id="9f4dd-148">Rendszeres cserék</span><span class="sxs-lookup"><span data-stu-id="9f4dd-148">Routine replacement</span></span>     | <span data-ttu-id="9f4dd-149">Óra</span><span class="sxs-lookup"><span data-stu-id="9f4dd-149">Hour</span></span>             | <span data-ttu-id="9f4dd-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-150">GB-1234</span></span>        | <span data-ttu-id="9f4dd-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-151">RR - GB1234</span></span>  |
| <span data-ttu-id="9f4dd-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="9f4dd-152">GR-1</span></span>                    | <span data-ttu-id="9f4dd-153">Tétel</span><span class="sxs-lookup"><span data-stu-id="9f4dd-153">Item</span></span>             | <span data-ttu-id="9f4dd-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-154">GB-1234</span></span>        | <span data-ttu-id="9f4dd-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-155">RR - GB1234</span></span>  |
| <span data-ttu-id="9f4dd-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="9f4dd-156">GR-5</span></span>                    | <span data-ttu-id="9f4dd-157">Tétel</span><span class="sxs-lookup"><span data-stu-id="9f4dd-157">Item</span></span>             | <span data-ttu-id="9f4dd-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-158">GB-1234</span></span>        | <span data-ttu-id="9f4dd-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-159">RR - GB1234</span></span>  |

<span data-ttu-id="9f4dd-160">A két munka szolgáltatási szerződéssoraihoz két szervizfeladat van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="9f4dd-161">A szervizfeladat határozza meg az egyes munkákhoz tartozó tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="9f4dd-162">Az első esetben a I/C - GB1234 szervizfeladat azonosítja a GB-1234 tárgy átvizsgálásában és tisztításában résztvevő összes szolgáltatási szerződéssort.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="9f4dd-163">A második esetben az RR - GB1234 szervizfeladat azonosít minden szolgáltatási szerződéssort egy rendszeres cserefeladat elvégzésére vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="9f4dd-164">A szervizfeladat-kapcsolatok, amelyek a szervizfeladatokat a konkrét szolgáltatási szerződéshez kötik, a következők:</span><span class="sxs-lookup"><span data-stu-id="9f4dd-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="9f4dd-165">Szervizfeladatok</span><span class="sxs-lookup"><span data-stu-id="9f4dd-165">Service tasks</span></span>

| <span data-ttu-id="9f4dd-166">Szervizfeladat</span><span class="sxs-lookup"><span data-stu-id="9f4dd-166">Service task</span></span> | <span data-ttu-id="9f4dd-167">Leírás</span><span class="sxs-lookup"><span data-stu-id="9f4dd-167">Description</span></span>                             | <span data-ttu-id="9f4dd-168">Belső megjegyzés</span><span class="sxs-lookup"><span data-stu-id="9f4dd-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="9f4dd-169">Külső megjegyzés</span><span class="sxs-lookup"><span data-stu-id="9f4dd-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="9f4dd-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-170">I/C - GB1234</span></span> | <span data-ttu-id="9f4dd-171">GB-1234 – sebességváltó átvizsgálása</span><span class="sxs-lookup"><span data-stu-id="9f4dd-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="9f4dd-172">A GB-1234 sebességváltó átnézése, mechanikai vizsgálata és tisztítása.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="9f4dd-173">Sebességváltó rendszeres felülvizsgálata</span><span class="sxs-lookup"><span data-stu-id="9f4dd-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="9f4dd-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="9f4dd-174">RR - GB1234</span></span>  | <span data-ttu-id="9f4dd-175">GB-1234 – alkatrészek rendszeres cseréje</span><span class="sxs-lookup"><span data-stu-id="9f4dd-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="9f4dd-176">A GR-1 és GR-5 elem rendszeres szervizcseréje (a 2002 előtt gyártott sebességváltóknál a GR-2 elemet is cserélje)</span><span class="sxs-lookup"><span data-stu-id="9f4dd-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="9f4dd-177">Rendszeres alkatrészcsere</span><span class="sxs-lookup"><span data-stu-id="9f4dd-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="9f4dd-178">Szervizrendelések csoportosítása</span><span class="sxs-lookup"><span data-stu-id="9f4dd-178">Group service orders</span></span>

<span data-ttu-id="9f4dd-179">Amikor automatikusan állít elő szervizrendeléseket, a szervizfeladatokat fel lehet használni csoportosítási feltételekként.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="9f4dd-180">A szervizrendelések szervizfeladatok alapján történő csoportosításához jelezze a szolgáltatási szerződésben, hogy a szolgáltatási szerződésen alapuló szervizrendeléseket szervizfeladat-azonosítók (ID) szerint kell csoportosítani elsődleges csoportosítási szempontként.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="9f4dd-181">**Csoportosítás szervizfeladat alapján**</span><span class="sxs-lookup"><span data-stu-id="9f4dd-181">**Group by service task**</span></span>

1. <span data-ttu-id="9f4dd-182">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="9f4dd-183">Válassza ki a **Beállítás** lapon a **Szervizfeladat szerint** lehetőséget a **Szervizrendelések kombinálása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="9f4dd-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>



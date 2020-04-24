---
title: Terhelési kihasználtság ütemezése
description: Ez a témakör ismerteti egy adott raktár esetén a rakomány beállítását és ütemezését.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87455077c69834c9ace6409f4cc611ae6e14beb4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204631"
---
# <a name="schedule-load-utilization"></a><span data-ttu-id="211e8-103">Terhelési kihasználtság ütemezése</span><span class="sxs-lookup"><span data-stu-id="211e8-103">Schedule load utilization</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="211e8-104">Ütemezheti a terhelési kihasználtságot a kijelölt helytípusokhoz, valamint megtervezheti a jelenlegi és a jövőbeli terhelési kihasználtságot.</span><span class="sxs-lookup"><span data-stu-id="211e8-104">You can schedule load utilization for selected location types, and you can also project the current and future load utilization.</span></span> <span data-ttu-id="211e8-105">Megtervezheti egy vagy több hely terhelését terhelési egységenként (raktár vagy zóna), vagy zóna és raktár kombinációjára.</span><span class="sxs-lookup"><span data-stu-id="211e8-105">You can project the load for one or more sites, for the load units (zone or warehouse), or for a combination of a zone and a warehouse.</span></span>

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a><span data-ttu-id="211e8-106">Raktár vagy hely terhelésének ütemezése és megtekintése</span><span class="sxs-lookup"><span data-stu-id="211e8-106">Schedule and view the load for a warehouse or site</span></span>

<span data-ttu-id="211e8-107">Helyek, raktárak vagy zónák terhelésének ütemezéséhez létre kell hoznia egy helykihasználási beállítást, és társítania kell egy alaptervvel.</span><span class="sxs-lookup"><span data-stu-id="211e8-107">To schedule the load for sites, warehouses, or zones, you create a space utilization setup and associate it with a master plan.</span></span>

<span data-ttu-id="211e8-108">A helykihasználási beállításban helytípusokat használ, mint például **Ömlesztett tárolóhely** és **Kitárolási hely** annak a megadásához, hogy hogyan legyen a helykihasználás tervezve.</span><span class="sxs-lookup"><span data-stu-id="211e8-108">In the space utilization setup, you use location types, such as **Bulk location** and **Picking location**, to specify how space utilization should be projected.</span></span> <span data-ttu-id="211e8-109">A tárolás terhelési módját is megadhatja, például **Zóna**.</span><span class="sxs-lookup"><span data-stu-id="211e8-109">You also specify a storage load mode, such as **Zone**.</span></span>

<span data-ttu-id="211e8-110">A helykihasználás jövőbeli megtervezése a társított alapterv adatain végzett számításokon alapul.</span><span class="sxs-lookup"><span data-stu-id="211e8-110">The projection of future space utilization is based on information that is calculated on the associated master plan.</span></span> <span data-ttu-id="211e8-111">Az alaptervek előrejelzik a gyártáshoz és a műveletekhez szükséges bejövő és kimenő rendelések erőforrás-tervezését.</span><span class="sxs-lookup"><span data-stu-id="211e8-111">Master plans forecast the resource planning for incoming and outgoing orders for production and operations.</span></span> <span data-ttu-id="211e8-112">A szabad terület előrejelzése a helykihasználás beállítása és a kiválasztott alapterv közötti kapcsolat alapján történik.</span><span class="sxs-lookup"><span data-stu-id="211e8-112">The projection of available space is based on the relation between the space utilization setup and the selected master plan.</span></span>

<span data-ttu-id="211e8-113">A helykihasználás beállításánál kiválasztott tárolásterhelési mód segítségével adhatja meg, hogy a terhelést minden egyes raktárra vagy zónára meg kell-e tervezni, vagy a tervezésnek tartalmaznia kell mind a raktár, mind a zóna adatait.</span><span class="sxs-lookup"><span data-stu-id="211e8-113">By using the storage load mode that you selected in the space utilization setup, you can specify whether the load should be projected for each warehouse or zone, or whether the projections should include information about both warehouses and zones.</span></span> <span data-ttu-id="211e8-114">Azt is megadhatja, hogy ki kell-e zárni a blokkolt helyeket a terhelési kihasználtság számításánál.</span><span class="sxs-lookup"><span data-stu-id="211e8-114">You also specify whether blocked locations should be excluded from the calculation of load utilization.</span></span>

<span data-ttu-id="211e8-115">A helykihasználás tervezéséhez létrehozhatja a **Raktár terhelési kihasználtsága** jelentést.</span><span class="sxs-lookup"><span data-stu-id="211e8-115">You can project the space utilization by generating the **Warehouse load utilization** report.</span></span> <span data-ttu-id="211e8-116">A jelentés létrehozásakor megadhatja, hogy a terhelési kihasználtságot minden egyes helyre külön, több helyre együtt vagy a kiválasztott terhelési egységre, például zónára vagy raktárra kell-e tervezni.</span><span class="sxs-lookup"><span data-stu-id="211e8-116">When you generate this report, you can specify whether the load utilization should be projected for each site, across sites, or for the selected load unit, such as zone or warehouse.</span></span>

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a><span data-ttu-id="211e8-117">Raktár helykihasználási beállításának létrehozása</span><span class="sxs-lookup"><span data-stu-id="211e8-117">Create a space utilization setup for a warehouse</span></span>

1. <span data-ttu-id="211e8-118">Válassza ki **Készletkezelés** \> **Beállítás** \> **Raktárfigyelés** \> **Helykihasználás**.</span><span class="sxs-lookup"><span data-stu-id="211e8-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Space utilization**.</span></span>
2. <span data-ttu-id="211e8-119">Válassza az **Új** elemet egy új helykihasználási beállítás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="211e8-119">Select **New** to create a space utilization setup.</span></span> <span data-ttu-id="211e8-120">Adja meg az új beállítás azonosítóját és nevét.</span><span class="sxs-lookup"><span data-stu-id="211e8-120">Specify an ID and a name for the new setup.</span></span>
3. <span data-ttu-id="211e8-121">A **Tárolás terhelési módja** mezőben válassza ki, hogy a helykihasználás áttekintése raktár, zóna, vagy raktár és zóna szerint legyen-e.</span><span class="sxs-lookup"><span data-stu-id="211e8-121">In the **Storage load mode** field, select whether the overview of space utilization should show information by warehouse, zone, or warehouse and zone.</span></span>
4. <span data-ttu-id="211e8-122">Állítsa a **Blokkolt helyek kihagyása** lehetőséget **Igen** beállításra a zárolt készletezési helyek kihagyásához a rendelkezésre álló hely számításából.</span><span class="sxs-lookup"><span data-stu-id="211e8-122">Set the **Exclude blocked locations** option to **Yes** to exclude blocked inventory locations from the calculation of available space.</span></span> <span data-ttu-id="211e8-123">Egy készlethely bejövő vagy kimenő forgalmának blokkolásához meg kell adnia a helyhez egy blokkolási okot az **Bemenet zárolva** vagy **Kimenet zárolva** mezőben az **Egyéb** gyorslapon a **Készlethelyek** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="211e8-123">You can block an inventory location for input and output by specifying a blocking cause for the location in the **Input blocked** or **Output blocked** field on the **Other** FastTab on the **Inventory locations** page.</span></span>
5. <span data-ttu-id="211e8-124">A **Helytípus** gyorslapon jelölje ki a helykihasználtság kiszámításánál figyelembe veendő helytípusokat.</span><span class="sxs-lookup"><span data-stu-id="211e8-124">On the **Location type** FastTab, select the location types to include in the space utilization calculation.</span></span> <span data-ttu-id="211e8-125">Legalább egy helytípust ki kell választania a tervezéshez.</span><span class="sxs-lookup"><span data-stu-id="211e8-125">You must select at least one location type for the projection.</span></span>

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a><span data-ttu-id="211e8-126">Helykihasználtsági beállítás társítása egy alaptervhez</span><span class="sxs-lookup"><span data-stu-id="211e8-126">Associate a space utilization setup with a master plan</span></span>

1. <span data-ttu-id="211e8-127">Válassza ki ezt: **Készletkezelés** \> **Időszakos feladatok** \> **Terhelési kihasználtság ütemezése**.</span><span class="sxs-lookup"><span data-stu-id="211e8-127">Select **Inventory management** \> **Periodic tasks** \> **Schedule load utilization**.</span></span>
2. <span data-ttu-id="211e8-128">Válasszon ki egy alaptervet az **Alapterv** mezőben.</span><span class="sxs-lookup"><span data-stu-id="211e8-128">In the **Master plan** field, select a master plan.</span></span>
3. <span data-ttu-id="211e8-129">A **Napok száma** mezőben adja meg a jelenlegi és jövőbeli terhelések tervezéséhez tartozó napok számát.</span><span class="sxs-lookup"><span data-stu-id="211e8-129">In the **Number of days** field, specify the number of days to include in the projection of current and future workloads.</span></span>
4. <span data-ttu-id="211e8-130">A **Helykihasználás** mezőben válassza ki azt a helykihasználási beállítást, melyet a jelenlegi és jövőbeli terhelések tervezéséhez kíván használni.</span><span class="sxs-lookup"><span data-stu-id="211e8-130">In the **Space utilization** field, select the space utilization setup to use for the projection of current and future workloads.</span></span>

### <a name="specify-the-load-utilization-projection-and-view-information"></a><span data-ttu-id="211e8-131">A terheléskihasználás tervezési és megtekintési adatainak megadása</span><span class="sxs-lookup"><span data-stu-id="211e8-131">Specify the load utilization projection and view information</span></span>

1. <span data-ttu-id="211e8-132">Válassza ezt: **Készletkezelés** \> **Lekérdezések és jelentések** \> **Fizikai leltárjelentés** \> **Raktár terhelési kihasználtsága**.</span><span class="sxs-lookup"><span data-stu-id="211e8-132">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Warehouse load utilization**.</span></span>
2. <span data-ttu-id="211e8-133">A **Megjelenítés alapja** mezőben válassza ki a helykihasználás tervezési szintjét:</span><span class="sxs-lookup"><span data-stu-id="211e8-133">In the **Show by** field, select the level of the space utilization projection:</span></span>

    - <span data-ttu-id="211e8-134">**Hely** – Ha minden helyre meg szeretné tervezni a helykihasználást.</span><span class="sxs-lookup"><span data-stu-id="211e8-134">**Site** – Project the space utilization for each site.</span></span> <span data-ttu-id="211e8-135">Ez az előrejelzés akkor hasznos, ha például meg szeretné tekinteni a hely összes raktárát, így egyensúlyban tarthatja a raktárak közötti helykihasználást.</span><span class="sxs-lookup"><span data-stu-id="211e8-135">This projection is useful if, for example, you want to view all the warehouses for a site so that you can balance the space utilization between the warehouses.</span></span>
    - <span data-ttu-id="211e8-136">**Terhelési egység** – Ha zónákra vagy raktárakra szeretné megtervezni a helykihasználást.</span><span class="sxs-lookup"><span data-stu-id="211e8-136">**Load unit** – Project the space utilization for zones or warehouses.</span></span> <span data-ttu-id="211e8-137">A rendelkezésre álló hely ezután a kiválasztott értéknek megfelelő előre jelzett a **Tárolás terhelési módja** mezőben a **Helykihasználtsági** oldalon a helykihasználási beállítás létrehozása után.</span><span class="sxs-lookup"><span data-stu-id="211e8-137">The available space is then projected according to the value that you selected in the **Storage load mode** field on the **Space utilization** page when you created the space utilization setup.</span></span>

3. <span data-ttu-id="211e8-138">Hajtsa végre az előző lépésben kiválasztott értéktől függően az alábbi lépések közül:</span><span class="sxs-lookup"><span data-stu-id="211e8-138">Follow one of these steps, depending on the value that you selected in the previous step:</span></span>

    - <span data-ttu-id="211e8-139">Ha a **Hely** lehetőséget választotta a **Megjelenítés alapja** mezőben, a **Hely** mező rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="211e8-139">If you selected **Site** in the **Show by** field, the **Site** field is available.</span></span> <span data-ttu-id="211e8-140">Válasszon ki a egy vagy több helyet az előrejelzéshez.</span><span class="sxs-lookup"><span data-stu-id="211e8-140">Select one or more sites to include in the projection.</span></span>
    - <span data-ttu-id="211e8-141">Ha a **Terhelési egység** lehetőséget választotta a **Megjelenítés alapja** mezőben, a **Hely** mező rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="211e8-141">If you selected **Load unit** in the **Show by** field, the **Load unit** field is available.</span></span> <span data-ttu-id="211e8-142">A terhelési egység megadása.</span><span class="sxs-lookup"><span data-stu-id="211e8-142">Select the load unit.</span></span>

4. <span data-ttu-id="211e8-143">A **Terhelési típus** mezőben válassza ki a **Térfogat** vagy **Tömeg** elemet a raktár üzemi egységét, amelyhez a helyet meg kívánja tervezni.</span><span class="sxs-lookup"><span data-stu-id="211e8-143">In the **Load type** field, select **Volume** or **Weight** to specify the warehouse operating unit to project space for.</span></span>
5. <span data-ttu-id="211e8-144">A **Helykihasználás beállítása** mezőben jelölje be azt a helykihasználási beállítást, amelyet alapul fog venni az előrejelzés.</span><span class="sxs-lookup"><span data-stu-id="211e8-144">In the **Space utilization setup** field, select the space utilization setup that the projection should be based on.</span></span>

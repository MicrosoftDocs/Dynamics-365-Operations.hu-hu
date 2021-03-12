---
title: Ütemezés terhelési kapacitása
description: Ez a témakör bemutatja, hogyan lehet beállítani és ütemezni a raktárban dolgozók vagy egy teljes raktár terhelési kapacitását.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8db243949b2aeee0a8263276234d439652905449
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965577"
---
# <a name="schedule-workload-capacity"></a><span data-ttu-id="3ad4a-103">Ütemezés terhelési kapacitása</span><span class="sxs-lookup"><span data-stu-id="3ad4a-103">Schedule workload capacity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3ad4a-104">A raktárak esetében lehetősége van terhelési kapacitás ütemezésére, és a jelenlegi és jövőbeli terhelés meghatározására az egyes raktárakat illetően.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-104">You can schedule workload capacity for warehouses, and you can also project the current and future workloads for the workers in individual warehouses.</span></span> <span data-ttu-id="3ad4a-105">Akár az egész raktár terhelését, vagy a bejövő és kimenő terhelést külön-külön is meghatározhatja.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-105">You can project the workload for the whole warehouse, or you can project the workload separately for incoming and outgoing workloads.</span></span>

<span data-ttu-id="3ad4a-106">A kiválasztott raktárak terhelésének meghatározása érdekében elérhetővé kell tenni a raktárak alapütemezésre vonatkozó adatait.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-106">To project workload output for selected warehouses, master scheduling data must be available for those warehouses.</span></span> <span data-ttu-id="3ad4a-107">További informáciért lásd: [Alaptervek áttekintése](../master-planning/master-plans.md).</span><span class="sxs-lookup"><span data-stu-id="3ad4a-107">For more information, see [Master plans overview](../master-planning/master-plans.md).</span></span>

## <a name="schedule-and-view-workloads-for-a-warehouse"></a><span data-ttu-id="3ad4a-108">Egy adott raktár terhelésének ütemezése és megtekintése</span><span class="sxs-lookup"><span data-stu-id="3ad4a-108">Schedule and view workloads for a warehouse</span></span>

<span data-ttu-id="3ad4a-109">A raktár terhelési kapacitásának ütemezése érdekében hozzon létre terhelési beállítást egy vagy több raktárhoz, majd társítsa a terhelési beállítást egy alaptervvel.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-109">To schedule workload capacity for a warehouse, you create a workload setup for one or more warehouses, and then associate the workload setup with a master plan.</span></span> <span data-ttu-id="3ad4a-110">A terhelési kapacitás beállítása során meghatározható a súly vagy a mennyiség határértéke a bejövő és kimenő tranzakciókra nézve.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-110">In the workload capacity setup, you can define limits for the weight or volume for incoming and outgoing transactions.</span></span> <span data-ttu-id="3ad4a-111">Az egyes raktárak esetében több beállítás is létrehozható, ezt követően pedig a beállítás egyéni alaptervekkel társítható.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-111">You can also create more than one setup for each warehouse and then associate the setup with individual master plans.</span></span> <span data-ttu-id="3ad4a-112">Előfordulhat például, hogy ezzel a megközelítéssel a munkaerő szezonális változásaihoz igazodik.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-112">For example, you might use this approach to accommodate seasonal changes in the workforce.</span></span>

<span data-ttu-id="3ad4a-113">Ha az alkalmazottak egy adott raktárban a bejövő és kimenő tranzakciókkal is foglalkoznak, a raktározási kapacitás beállítása úgy is konfigurálható, hogy a terhelés kombinált nézetben legyen meghatározva.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-113">If the workers for a warehouse work with transactions for both incoming and outgoing workloads, you can configure the warehouse capacity setup so that the workload is projected in a combined view.</span></span>

<span data-ttu-id="3ad4a-114">A raktárak terhelésének ütemezése és megtekintése érdekében hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="3ad4a-114">To schedule and view workloads for warehouses, you must complete the following tasks:</span></span>

1. <span data-ttu-id="3ad4a-115">Hozzon létre terhelésikapacitás-beállítást, és határozza meg a terhelési kapacitás határértékeit egy vagy több raktár esetében.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-115">Create a workload capacity setup and define workload capacity limits for one or more warehouses.</span></span>
2. <span data-ttu-id="3ad4a-116">Terhelési előrejelzések meghatározása, valamint az előrejelzések hosszának megbecslése érdekében társítsa a terhelésikapacitás-beállítást alaptervvel.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-116">Associate the workload capacity setup with a master plan to create workload projections and specify how long those projections will apply.</span></span>

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a><span data-ttu-id="3ad4a-117">Terhelésikapacitás-beállítás létrehozása raktár esetében</span><span class="sxs-lookup"><span data-stu-id="3ad4a-117">Create a workload capacity setup for a warehouse</span></span>

1. <span data-ttu-id="3ad4a-118">Válassza ki **Készletkezelés** \> **Beállítás** \> **Raktárfigyelés** \> **Terhelési kapacitás**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="3ad4a-119">Jelölje be a műveleti ablakban az **Új** lehetőséget a terhelési kapacitás beállításának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-119">On the Action Pane, select **New** to create a workload capacity setup.</span></span>
3. <span data-ttu-id="3ad4a-120">Kattintson a képernyő **Raktárak** gyorslapján található **Új** elemre, majd adja meg az értékeket a raktár terhelésikapacitás-beállításhoz történő társítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-120">On the **Warehouses** FastTab, select **New**, and then enter values on the line to associate a warehouse with the workload capacity setup.</span></span>
4. <span data-ttu-id="3ad4a-121">Jelölje be a **Kombinált bejövő és kimenő terhelést** jelölőnégyzetet, ha a **Terhelési kapacitás** jelentés jelenítse meg a bejövő és kimenő tranzakciók teljes terhelését egy nézetben.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-121">Select the **Combined inbound and outbound workload** check box if the **Workload capacity** report should show the total workload for incoming and outgoing transactions in one view.</span></span>
5. <span data-ttu-id="3ad4a-122">A **Tranzakciótípusok** gyorslapon jelölje be azokat a bejövő és kimenő tranzakciótípusokat, amelyekre a terhelési határértékek vonatkozni fognak.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-122">On the **Transaction types** FastTab, select the types of incoming and outgoing transactions that the workload limits will apply to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3ad4a-123">Legalább egy tranzakciótípust ki kell jelölnie mind a bejövő, mind a kimenő terhelésekre nézve.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-123">You must select at least one transaction type for both the incoming workload and the outgoing workload.</span></span>

#### <a name="define-limits-for-volume-or-weight"></a><span data-ttu-id="3ad4a-124">Térfogat vagy tömeg korlátjának meghatározása</span><span class="sxs-lookup"><span data-stu-id="3ad4a-124">Define limits for volume or weight</span></span>

<span data-ttu-id="3ad4a-125">Raklapok, mennyiség vagy súly esetében is megadhat határértékeket attól függően, hogy milyen korlátozások vonatkoznak a raktárban dolgozó munkaerőre.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-125">You can set up limits for volume or weight, depending on the limitation that is relevant for the warehouse workforce.</span></span> <span data-ttu-id="3ad4a-126">A megadott határértékek szerepelnek a terhelési kapacitás előrejelzésében, amelyek a **Terhelési kapacitás** jelentésben tekinthetők meg.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-126">The limits that you specify are included in the workload capacity projection that you can view on the **Workload capacity** report.</span></span>

<span data-ttu-id="3ad4a-127">A cikkekhez szükséges mennyiséggel és súllyal kapcsolatos adatok előrejelzéséhez minden termék esetében meg kell adni a raklapok szabványos típusát, a készletcikk mennyiségét, valamint egy készletcikk súlyát.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-127">To project information about volume and weight for items, the standard volume of one inventory item and the weight of one inventory item must be specified for all products.</span></span> <span data-ttu-id="3ad4a-128">A szükséges mezők a következő mezőcsoportokban érhetők el a **Készlet kezelése** gyorslapján a **Kiadott termék részletei** lapnak:</span><span class="sxs-lookup"><span data-stu-id="3ad4a-128">The fields that are required are available in the following field groups on the **Manage inventory** FastTab of the **Released product details** page:</span></span>

- <span data-ttu-id="3ad4a-129">Kezelés</span><span class="sxs-lookup"><span data-stu-id="3ad4a-129">Handling</span></span>
- <span data-ttu-id="3ad4a-130">Tényleges dimenziók</span><span class="sxs-lookup"><span data-stu-id="3ad4a-130">Physical dimensions</span></span>
- <span data-ttu-id="3ad4a-131">Tömeg mérése</span><span class="sxs-lookup"><span data-stu-id="3ad4a-131">Weight measurements</span></span>

<span data-ttu-id="3ad4a-132">Ha ez az információ nincs megfelelően megadva, a rendszer üzenetet küld a **Terhelési kapacitás** jelentés létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-132">If this information isn't specified correctly, you receive a message when you generate the **Workload capacity** report.</span></span> <span data-ttu-id="3ad4a-133">A jelentésből lekérdezhetők azok az adatok, amelyek hiányoznak és szükségesek a jövőbeli terhelés előrejelzéséhez.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-133">From the report, you can then drill down to identify the missing information that is required in order to project the future workload.</span></span>

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a><span data-ttu-id="3ad4a-134">Terhelésikapacitás-beállítás társítása alaptervvel</span><span class="sxs-lookup"><span data-stu-id="3ad4a-134">Associate a workload capacity setup with a master plan</span></span>

1. <span data-ttu-id="3ad4a-135">Válassza ki ezt: **Készletkezelés** \> **Időszakos** \> **Terhelés ütemezése**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-135">Select **Inventory management** \> **Periodic** \> **Schedule workload**.</span></span>
2. <span data-ttu-id="3ad4a-136">Az **Alapterv** mezőben jelölje ki a terhelés előrejelzéseihez használni kívánt alaptervet.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-136">In the **Master plan** field, select the master plan to use for workload projections.</span></span>
3. <span data-ttu-id="3ad4a-137">Adja meg a **Napok száma** mezőben a terhelés-előrejelzés által érintett napok számát.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-137">In the **Number of days** field, specify the number of days that the workload projection covers.</span></span>
4. <span data-ttu-id="3ad4a-138">Válassza ki a **Munkaterhelés** mezőben az alaptervvel társítandó terhelésbeállítást.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-138">In the **Workload** field, select the workload setup to associate with the master plan.</span></span>

### <a name="view-workload-capacity"></a><span data-ttu-id="3ad4a-139">Terhelési kapacitás megtekintése</span><span class="sxs-lookup"><span data-stu-id="3ad4a-139">View workload capacity</span></span>

1. <span data-ttu-id="3ad4a-140">Válassza ezt: **Készletkezelés** \> **Lekérdezések és jelentések** \> **Fizikai leltárjelentés** \> **Terhelési kapacitás**.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-140">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="3ad4a-141">Adja meg az **Oszlopok száma** mezőben a jelentésben megjelenítendő oszlopok számát.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-141">In the **Number of columns** field, specify the number of columns to show on the report.</span></span>
3. <span data-ttu-id="3ad4a-142">A **Rendelés típusa** mezőben válassza ki a **Tervezett és visszaigazolt**, **Tervezett** vagy **Visszaigazolt** annak a meghatározásához, hogy milyen típusú rendelések legyenek feltüntetve a jelentésben.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-142">In the **Order type** field, select **Planned and confirmed**, **Planned**, or **Confirmed** to indicate the type of orders to project on the report.</span></span>
4. <span data-ttu-id="3ad4a-143">Válassza ki a **Terhelés típusa** mezőben a terhelés típusát annak meghatározása érdekében, hogy a terhelési kapacitást mennyiség vagy súly esetében kell-e előre jelezni.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-143">In the **Load type** field, select a load type to specify whether the workload capacity should be projected for volume or weight.</span></span>
5. <span data-ttu-id="3ad4a-144">Válassza ki a **Terhelési kapacitás** mezőben a terhelésikapacitás-beállítást.</span><span class="sxs-lookup"><span data-stu-id="3ad4a-144">In the **Workload capacity** field, select a workload capacity setup.</span></span>

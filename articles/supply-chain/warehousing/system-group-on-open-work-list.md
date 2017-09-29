---
title: "Nyitott munkalista rendszercsoportosítása"
description: "Ez a témakör leírja, hogyan történik a nyitott munkalista szűrése egy mobileszközön."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0c68d544fec985f325e6472203533f23948cc9b4
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="system-grouping-on-an-open-work-list"></a><span data-ttu-id="24a84-103">Nyitott munkalista rendszercsoportosítása</span><span class="sxs-lookup"><span data-stu-id="24a84-103">System grouping on an open work list</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="24a84-104">Csoportosító rendszermező segítségével a mobileszköz menüpontjának szerkesztése nélkül szűrheti a nyitott munkalistát.</span><span class="sxs-lookup"><span data-stu-id="24a84-104">By using a system grouping field, you can filter an open work list without having to edit the mobile device menu item.</span></span>
<span data-ttu-id="24a84-105">A rendszercsoportosítás alkalmazási köre egyetlen munkafejlécmező munkalistájának szűrése.</span><span class="sxs-lookup"><span data-stu-id="24a84-105">Where it applies, system grouping works for filtering a work list on a single work header field.</span></span> <span data-ttu-id="24a84-106">A rendszercsoportosítás nem használható online szinten lévő mezők szűrésére.</span><span class="sxs-lookup"><span data-stu-id="24a84-106">You cannot use system grouping to filter on line level fields.</span></span>

## <a name="set-up-system-grouping-on-an-open-work-list"></a><span data-ttu-id="24a84-107">Rendszercsoportosítás beállítása nyitott munkalistához</span><span class="sxs-lookup"><span data-stu-id="24a84-107">Set up system grouping on an open work list</span></span>
<span data-ttu-id="24a84-108">A következő lépésekkel beállíthatja a rendszercsoportosítást egy nyitott munkalistához.</span><span class="sxs-lookup"><span data-stu-id="24a84-108">Use these steps to set up system grouping on an open work list.</span></span>

-   <span data-ttu-id="24a84-109">Egy mobileszköz menüpontjában válassza a **Mód: közvetett** és a **Tevékenység kódja: nyitott munkalista megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24a84-109">From a mobile device menu item, select **Mode: Indirect** and **Activity Code: Display open work list**.</span></span> <span data-ttu-id="24a84-110">Az alábbi lehetőségek válnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="24a84-110">The following options become available.</span></span> <span data-ttu-id="24a84-111">Ezek a beállítások szükségesek a rendszercsoportosítás nyitott munkalistán történő működéséhez.</span><span class="sxs-lookup"><span data-stu-id="24a84-111">These options are required for system grouping on an open work list.</span></span> 

| <span data-ttu-id="24a84-112">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="24a84-112">Option</span></span>        | <span data-ttu-id="24a84-113">Leírás</span><span class="sxs-lookup"><span data-stu-id="24a84-113">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="24a84-114">Rendszercsoportosítás engedélyezése</span><span class="sxs-lookup"><span data-stu-id="24a84-114">Allow system grouping</span></span>   | <span data-ttu-id="24a84-115">Lehetővé teszi a rendszercsoportosítást a kijelölt munkalista menüelemére vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="24a84-115">Enables system groping for a selected work list menu item.</span></span>| 
| <span data-ttu-id="24a84-116">Csoportosító rendszermező</span><span class="sxs-lookup"><span data-stu-id="24a84-116">System grouping field</span></span>   | <span data-ttu-id="24a84-117">Csak akkor érhető el, ha a **Rendszer működésének ellenőrzése** értéke **Igen**.</span><span class="sxs-lookup"><span data-stu-id="24a84-117">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="24a84-118">Válassza ki azt a mezőt, amely meghatározza, hogyan fogja a rendszer kitárolási munkát csoportosítani a dolgozók számára.</span><span class="sxs-lookup"><span data-stu-id="24a84-118">Select the field that determines how picking work will be grouped for workers.</span></span> <span data-ttu-id="24a84-119">Ha például bejelöli a **ShipmentId** mezőt, a dolgozó ellenőrzi a szállítmányazonosítót a kitárolási munka csoportosításához.</span><span class="sxs-lookup"><span data-stu-id="24a84-119">For example, if you select the **ShipmentId** field, the worker will scan the shipment ID to group the picking work.</span></span> <span data-ttu-id="24a84-120">A rendszer hozzárendeli a dolgozóhoz a szállítmány minden munkáját.</span><span class="sxs-lookup"><span data-stu-id="24a84-120">All work for the shipment is then assigned to the worker.</span></span> <span data-ttu-id="24a84-121">Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához.</span><span class="sxs-lookup"><span data-stu-id="24a84-121">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="24a84-122">Használja a **Rendszercsoportosítási címke** mezőt, amely jelzi a dolgozónak, hogy mit olvasson be.</span><span class="sxs-lookup"><span data-stu-id="24a84-122">Use the **System grouping label** field to inform the worker what to scan.</span></span> |
| <span data-ttu-id="24a84-123">Csoportosító rendszercímke</span><span class="sxs-lookup"><span data-stu-id="24a84-123">System grouping label</span></span>   | <span data-ttu-id="24a84-124">Csak akkor érhető el, ha a **Rendszer működésének ellenőrzése** értéke **Igen**.</span><span class="sxs-lookup"><span data-stu-id="24a84-124">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="24a84-125">Írja be a szöveget, amely a dolgozót tájékoztatja arról, mit olvasson be, ha a kitárolási munka csoportosítva van a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="24a84-125">Enter information for the worker about what to scan when picking work is grouped.</span></span> <span data-ttu-id="24a84-126">Például ha a **Szállítmányazonosító** mezőt használja egy szállítmány kitárolási munkájának csoportosítására, megadhatja a Szállítási azonosító értékét a mezőben.</span><span class="sxs-lookup"><span data-stu-id="24a84-126">For example, if you use the **ShipmentId** field to group picking work by shipment, you might enter Shipment ID in the field.</span></span> <span data-ttu-id="24a84-127">Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához.</span><span class="sxs-lookup"><span data-stu-id="24a84-127">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="24a84-128">A **Rendszercsoportosítás** mezőben ki kell választania a mezőt is, amely szerint a csoportosítás történik.</span><span class="sxs-lookup"><span data-stu-id="24a84-128">You must also select the field to group by in the **System grouping** field.</span></span>|


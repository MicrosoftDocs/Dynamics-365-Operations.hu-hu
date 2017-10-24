---
title: "Helyek részleges ciklikus leltározása"
description: "A ciklikus leltározási tervek vezérlik a tényleges leltározási tevékenységeket. Kérhető az, hogy csak bizonyos termékek és termékváltozatok leltározása történjen meg a hely összes aktuális készlete helyett."
author: perlynne
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 626b2f9f35b94124168adb7bb09c75a086d38a97
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="partial-location-cycle-counting"></a><span data-ttu-id="285f5-104">Helyek részleges ciklikus leltározása</span><span class="sxs-lookup"><span data-stu-id="285f5-104">Partial location cycle counting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="285f5-105">A ciklikus leltározási tervek vezérlik a tényleges leltározási tevékenységeket.</span><span class="sxs-lookup"><span data-stu-id="285f5-105">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="285f5-106">Kérhető az, hogy csak bizonyos termékek és termékváltozatok leltározása történjen meg a hely összes aktuális készlete helyett.</span><span class="sxs-lookup"><span data-stu-id="285f5-106">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="285f5-107">Ha ciklikus leltározási terveket használ a leltározási munka létrehozásához, irányíthatja a tényleges leltározási műveleteket.</span><span class="sxs-lookup"><span data-stu-id="285f5-107">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="285f5-108">Kérhető az, hogy csak bizonyos termékek és termékváltozatok leltározása történjen meg a hely összes aktuális készlete helyett.</span><span class="sxs-lookup"><span data-stu-id="285f5-108">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="285f5-109">Adott termékekre való szűréssel a raktárvezető csökkentheti az ellenőrzéssel járó költségeket, elkerülheti a konszolidációs hibákat és időt takaríthat meg.</span><span class="sxs-lookup"><span data-stu-id="285f5-109">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="285f5-110">Hogyan kell konfigurálni a részleges helyre vonatkozó ciklikus leltározást</span><span class="sxs-lookup"><span data-stu-id="285f5-110">How to configure partial location cycle counting</span></span>
<span data-ttu-id="285f5-111">Ha a raktár munkafolyamatot használja a leltározási művelethez, minden egyes helyhez munkafejléc jön létre.</span><span class="sxs-lookup"><span data-stu-id="285f5-111">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="285f5-112">A ciklikus leltározási terv meghatározásakor fel lehet használni a **Helyek kiválasztása** lekérdezést a létrehozott ciklikus leltározási munka korlátozásához.</span><span class="sxs-lookup"><span data-stu-id="285f5-112">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="285f5-113">A ciklikus leltározási tervhez a termékek kiválasztásakor termék- és termékváltozat-lekérdezések is kiválaszthatók a leltározás hatókörének pontosításához.</span><span class="sxs-lookup"><span data-stu-id="285f5-113">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="285f5-114">A ciklikus leltározási tervvel társítani lehet egy **munkasablont** annak a meghatározásához, hogy hogyan történjen a ciklikus leltározási munka létrehozása.</span><span class="sxs-lookup"><span data-stu-id="285f5-114">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="285f5-115">A leltározási műveletek munkasablonjára közvetlenül hivatkozik a ciklikus leltározási terv.</span><span class="sxs-lookup"><span data-stu-id="285f5-115">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="285f5-116">A munkasablon részleteinek definiálásakor használhatja a **Munkasorszünetek** beállítást annak a megadásához, hogy a leltári munkasorokat cikkszám vagy a termékváltozatszám szerint kell-e csoportosítani.</span><span class="sxs-lookup"><span data-stu-id="285f5-116">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="285f5-117">Ez a beállítás akkor szükséges, ha csak bizonyos termékekre szeretne leltározást végrehajtani egy helyen.</span><span class="sxs-lookup"><span data-stu-id="285f5-117">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="285f5-118">A létrehozott ciklikus leltározási munkasorok az itt megadott információszinttel jönnek létre, és az irányított leltározási művelet kezelése ennek a szintnek az alapján történik.</span><span class="sxs-lookup"><span data-stu-id="285f5-118">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="285f5-119">Ha a ciklikus leltározási terveket társítja a munkasablonokkal a **Munkasorszünetek** lehetőség használatával, a **Részleges ciklikus leltár** mező be van jelölve a létrehozott leltározási munkához, és több ciklikus leltározási munkasorok jön létre a munkasablon definíciója alapján.</span><span class="sxs-lookup"><span data-stu-id="285f5-119">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="285f5-120">A részleges ciklikus leltározási munka feldolgozása előtt minimális követelményként ki kell választani a **Cikkszám megjelenítése** elemet a mobileszköz menüeleméhez a ciklikus leltározás telepítésének részeként.</span><span class="sxs-lookup"><span data-stu-id="285f5-120">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="285f5-121">A raktárkezelőt a rendszer arra kéri, hogy csak a leltársorokhoz kapcsolódó leltározási adatokat (cikkszámok és termékdimenziók) rögzítése.</span><span class="sxs-lookup"><span data-stu-id="285f5-121">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="285f5-122">A leltározási folyamat figyelmen kívül hagyja az összes többi aktuális készletet.</span><span class="sxs-lookup"><span data-stu-id="285f5-122">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="285f5-123">A részleges ciklikus leltározási folyamatban az **Utolsó ciklikus leltár** dátuma és időpontja nem frissül a helyre nézve.</span><span class="sxs-lookup"><span data-stu-id="285f5-123">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="285f5-124">Példa</span><span class="sxs-lookup"><span data-stu-id="285f5-124">Example</span></span>
<span data-ttu-id="285f5-125">Ebben a példában csak az A0001 cikkszámot kell leltározni a 61-es raktárban.</span><span class="sxs-lookup"><span data-stu-id="285f5-125">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="285f5-126">A ciklikus leltározáshoz új munkasablon jön létre.</span><span class="sxs-lookup"><span data-stu-id="285f5-126">A new work template for cycle counting is created.</span></span> <span data-ttu-id="285f5-127">A **Munkasorszünetek** beállítás szolgál a leltári munkasorok csoportosítására cikkszám szerint.</span><span class="sxs-lookup"><span data-stu-id="285f5-127">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="285f5-128">Emiatt a létrehozott ciklikus leltározási munka sorokkal fog rendelkezni cikkszámonként.</span><span class="sxs-lookup"><span data-stu-id="285f5-128">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="285f5-129">A sorokat termékváltozatszám szerint is lehet csoportosítani.</span><span class="sxs-lookup"><span data-stu-id="285f5-129">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="285f5-130">Létrejön egy új ciklikus leltári terv, amely az újonnan létrehozott munkasablonra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="285f5-130">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="285f5-131">A ciklikus leltározási terv minden helyet tartalmaz a 61-es raktárban (**Helyek kiválasztása** lekérdezés), ahol készleten van az A0001-es cikkszám.</span><span class="sxs-lookup"><span data-stu-id="285f5-131">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="285f5-132">A konkrét termékek körét a **Ciklikus leltározási terv termékkiválasztások** szakasz határozza meg.</span><span class="sxs-lookup"><span data-stu-id="285f5-132">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="285f5-133">A ciklikus leltározási tervekhez úgy lehet termékeket kiválasztani, hogy az **Üres helyek** mezőt **Üresek nélkül** beállításra állítjuk. A ciklikus leltározási terv feldolgozásakor az A0001 cikkszámhoz részleges ciklikus leltározási munka jön létre.</span><span class="sxs-lookup"><span data-stu-id="285f5-133">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="285f5-134">A tényleges leltározási folyamat az irányított ciklikus leltározás mobileszköz-menüelemének használatával hajtható végre.</span><span class="sxs-lookup"><span data-stu-id="285f5-134">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="see-also"></a><span data-ttu-id="285f5-135">Lásd még</span><span class="sxs-lookup"><span data-stu-id="285f5-135">See also</span></span>
--------

[<span data-ttu-id="285f5-136">Ciklikus leltározás</span><span class="sxs-lookup"><span data-stu-id="285f5-136">Cycle counting</span></span>](cycle-counting.md)


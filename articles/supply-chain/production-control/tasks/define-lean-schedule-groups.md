--- 
title: "Lean ütemezési csoportok meghatározása"
description: "A lean ütemezési csoportok definiálásával csoportosíthatók és különböztethetők meg a termékek a kanbanütemezésben."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a5bc20c0a9e2396365caebeb3751d2090e4575a4
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="d99ea-103">Lean ütemezési csoportok meghatározása</span><span class="sxs-lookup"><span data-stu-id="d99ea-103">Define lean schedule groups</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d99ea-104">A lean ütemezési csoportok definiálásával csoportosíthatók és különböztethetők meg a termékek a kanbanütemezésben.</span><span class="sxs-lookup"><span data-stu-id="d99ea-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="d99ea-105">A csoportosítás vállalatonként általános társításként hozható létre vagy munkacella-specifikusként.</span><span class="sxs-lookup"><span data-stu-id="d99ea-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="d99ea-106">Mindegyik csoport rendelkezik egy színkóddal, amely a vizuális jelöléshez kell a kanbanütemezési listaoldalon.</span><span class="sxs-lookup"><span data-stu-id="d99ea-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="d99ea-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d99ea-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="d99ea-108">Lean ütemezési csoport meghatározása</span><span class="sxs-lookup"><span data-stu-id="d99ea-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="d99ea-109">Ugorjon a Termékinformációk kezelése > Lean manufacturing > Lean ütemezéscsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d99ea-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="d99ea-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d99ea-110">Click New.</span></span>
3. <span data-ttu-id="d99ea-111">Írjon be egy értéket az Ütemezés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d99ea-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="d99ea-112">Egy ütemezéscsoportot meg lehet határozni globális csoportként vagy úgy, hogy egy konkrét munkacellára vonatkozzon.</span><span class="sxs-lookup"><span data-stu-id="d99ea-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="d99ea-113">Ebben az egyszerű példában egy globális csoportot definiálunk, és a munkacella üres marad.</span><span class="sxs-lookup"><span data-stu-id="d99ea-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="d99ea-114">Ezen csoport beállításai vonatkoznak minden munkacellára, amelyek nem rendelkeznek külön ütemezésicsoportokkal.</span><span class="sxs-lookup"><span data-stu-id="d99ea-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="d99ea-115">Válasszon egy színt a színválasztékból.</span><span class="sxs-lookup"><span data-stu-id="d99ea-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="d99ea-116">A színek jelölik a feladatokat a kanbanütemezés listaoldalán vagy a kanban-folyamattáblán.</span><span class="sxs-lookup"><span data-stu-id="d99ea-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="d99ea-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d99ea-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="d99ea-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d99ea-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="d99ea-119">Termékek társítása</span><span class="sxs-lookup"><span data-stu-id="d99ea-119">Associate product</span></span>
1. <span data-ttu-id="d99ea-120">Egy konkrét termék társítása</span><span class="sxs-lookup"><span data-stu-id="d99ea-120">Associate a specific product</span></span>
    * <span data-ttu-id="d99ea-121">Két módon lehet lean ütemezési csoportokhoz társítani termékeket; vagy konkrét termékként (cikk-kapcsolat típusa = Cikk) vagy egy cikkfelosztási kulcs részeként (cikk-kapcsolat típusa = csoport).</span><span class="sxs-lookup"><span data-stu-id="d99ea-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="d99ea-122">A Cikk-kapcsolat típusa mezőben válassza ki a „Cikk” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d99ea-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="d99ea-123">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d99ea-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="d99ea-124">Adjon meg egy számot a Teljesítmény aránya mezőben.</span><span class="sxs-lookup"><span data-stu-id="d99ea-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="d99ea-125">Az alapértelmezett teljesítményarány 1, amely azt jelenti, hogy a kapcsolódó termékek pontosan a termelési folyamatok folyamattevékenységeiben megadott kapacitást használják fel.</span><span class="sxs-lookup"><span data-stu-id="d99ea-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="d99ea-126">A > 1 teljesítményarány egy magasabb erőforrás-felhasználást határoz meg, a < 1 teljesítményarány egy alacsonyabb erőforrás-felhasználást határoz meg.</span><span class="sxs-lookup"><span data-stu-id="d99ea-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="d99ea-127">Az arány a költségszámításhoz és a kanbanfeladat felhasználásának kiszámítására használatos.</span><span class="sxs-lookup"><span data-stu-id="d99ea-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="d99ea-128">Cikkfoglalási kulcs társítása</span><span class="sxs-lookup"><span data-stu-id="d99ea-128">Associate item allocation key</span></span>
1. <span data-ttu-id="d99ea-129">Cikkfoglalási kulcs társítása</span><span class="sxs-lookup"><span data-stu-id="d99ea-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="d99ea-130">Adjon hozzá egy társítást egy cikkfelosztási kulcshoz a Cikk-kapcsolat típusa csoport segítségével.</span><span class="sxs-lookup"><span data-stu-id="d99ea-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="d99ea-131">Ne feledje, hogy ehhez a folyamathoz, meg kell határozni az adatokban egy előrejelzett cikkfelosztási kulcsot.</span><span class="sxs-lookup"><span data-stu-id="d99ea-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="d99ea-132">A Cikk-kapcsolat típusa mezőben válassza ki a „Csoport” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d99ea-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="d99ea-133">A Cikkfoglalási kulcs mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d99ea-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d99ea-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d99ea-134">In the list, click the link in the selected row.</span></span>


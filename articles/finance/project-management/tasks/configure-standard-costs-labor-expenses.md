---
title: Munka és kiadások elszámolóárainak konfigurálása
description: Ez a témakör elmagyarázza, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185405"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="76604-103">Munka és kiadások elszámolóárainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="76604-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76604-104">Ez a témakör elmagyarázza, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára.</span><span class="sxs-lookup"><span data-stu-id="76604-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="76604-105">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="76604-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="76604-106">A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Önköltségi ár (óra)** részre.</span><span class="sxs-lookup"><span data-stu-id="76604-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="76604-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-107">Select **New**.</span></span>
3. <span data-ttu-id="76604-108">Adja meg a dátumot az **Érvényesség dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="76604-109">Adjon meg egy számot az **Önköltségi ár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="76604-110">A projektkategóriához megadható elszámolóár, de megadható az önköltségi ár dolgozószám, projektszám, kategória, dátum vagy ezek tetszőleges kombinációja alapján is.</span><span class="sxs-lookup"><span data-stu-id="76604-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="76604-111">A rendszer a legnagyobb részletességű szinten létező önköltségi árat alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="76604-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="76604-112">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-112">Select **Save**.</span></span>
6. <span data-ttu-id="76604-113">A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Eladási ár (óra)** részre.</span><span class="sxs-lookup"><span data-stu-id="76604-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="76604-114">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-114">Select **New**.</span></span>
8. <span data-ttu-id="76604-115">Adja meg a dátumot az **Érvényesség dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="76604-116">Az **Érvényes** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="76604-117">Adjon meg egy számot az **Árazás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="76604-118">Beállítható az óratranzakciók és projektkategóriák szokásos eladási ára.</span><span class="sxs-lookup"><span data-stu-id="76604-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="76604-119">Szintén be lehet állítani dolgozók száma, projekt száma, kategória, tranzakció dátuma vagy ezek bármely kombinációja szerinti eladási árakat.</span><span class="sxs-lookup"><span data-stu-id="76604-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="76604-120">Amikor a dolgozó az óranaplóban beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár.</span><span class="sxs-lookup"><span data-stu-id="76604-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="76604-121">Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.</span><span class="sxs-lookup"><span data-stu-id="76604-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="76604-122">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-122">Select **Save**.</span></span>
12. <span data-ttu-id="76604-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76604-123">Close the page.</span></span>
13. <span data-ttu-id="76604-124">A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Önköltségi ár (költség)** részre.</span><span class="sxs-lookup"><span data-stu-id="76604-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="76604-125">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-125">Select **New**.</span></span>
15. <span data-ttu-id="76604-126">Adja meg a dátumot az **Érvényesség dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="76604-127">Adjon meg egy számot az **Önköltségi ár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="76604-128">Több mező is kitölthető, de ez a minimálisan szükséges a rekord mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="76604-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="76604-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-129">Select **Save**.</span></span>
18. <span data-ttu-id="76604-130">A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Eladási ár (költség)** részre.</span><span class="sxs-lookup"><span data-stu-id="76604-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="76604-131">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-131">Select **New**.</span></span>
20. <span data-ttu-id="76604-132">Adja meg a dátumot az **Érvényesség dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="76604-133">Az **Érvényes** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="76604-134">Adjon meg egy számot az **Árazás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="76604-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="76604-135">Amikor a dolgozó a költségnaplóba beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár.</span><span class="sxs-lookup"><span data-stu-id="76604-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="76604-136">Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.</span><span class="sxs-lookup"><span data-stu-id="76604-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="76604-137">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76604-137">Select **Save**.</span></span>


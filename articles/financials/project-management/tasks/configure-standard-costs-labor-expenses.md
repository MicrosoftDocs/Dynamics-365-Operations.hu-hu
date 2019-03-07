---
title: Munka és kiadások elszámolóárainak konfigurálása
description: Ez az eljárás bemutatja, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "339395"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="c1d39-103">Munka és kiadások elszámolóárainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c1d39-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c1d39-104">Ez az eljárás bemutatja, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára.</span><span class="sxs-lookup"><span data-stu-id="c1d39-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="c1d39-105">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="c1d39-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="c1d39-106">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Költségár (óra) elemet.</span><span class="sxs-lookup"><span data-stu-id="c1d39-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="c1d39-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1d39-107">Click New.</span></span>
3. <span data-ttu-id="c1d39-108">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="c1d39-109">Adjon meg egy számot az Önköltségi ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="c1d39-110">A projektkategóriához megadható elszámolóár, de megadható az önköltségi ár dolgozószám, projektszám, kategória, dátum vagy ezek tetszőleges kombinációja alapján is.</span><span class="sxs-lookup"><span data-stu-id="c1d39-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="c1d39-111">A rendszer a legnagyobb részletességű szinten létező önköltségi árat alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="c1d39-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="c1d39-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c1d39-112">Click Save.</span></span>
6. <span data-ttu-id="c1d39-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1d39-113">Close the page.</span></span>
7. <span data-ttu-id="c1d39-114">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Eladási ár (óra) elemet.</span><span class="sxs-lookup"><span data-stu-id="c1d39-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="c1d39-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1d39-115">Click New.</span></span>
9. <span data-ttu-id="c1d39-116">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="c1d39-117">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1d39-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="c1d39-118">Adjon meg egy számot az Árazás mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="c1d39-119">Beállítható az óratranzakciók és projektkategóriák szokásos eladási ára.</span><span class="sxs-lookup"><span data-stu-id="c1d39-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="c1d39-120">Szintén be lehet állítani dolgozók száma, projekt száma, kategória, tranzakció dátuma vagy ezek bármely kombinációja szerinti eladási árakat.</span><span class="sxs-lookup"><span data-stu-id="c1d39-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="c1d39-121">Amikor a dolgozó az óranaplóban beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár.</span><span class="sxs-lookup"><span data-stu-id="c1d39-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="c1d39-122">Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.</span><span class="sxs-lookup"><span data-stu-id="c1d39-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="c1d39-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c1d39-123">Click Save.</span></span>
13. <span data-ttu-id="c1d39-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1d39-124">Close the page.</span></span>
14. <span data-ttu-id="c1d39-125">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Költségár (kiadás) elemet.</span><span class="sxs-lookup"><span data-stu-id="c1d39-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="c1d39-126">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1d39-126">Click New.</span></span>
16. <span data-ttu-id="c1d39-127">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="c1d39-128">Adjon meg egy számot az Önköltségi ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="c1d39-129">Több mező is kitölthető, de ez a minimálisan szükséges a rekord mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="c1d39-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="c1d39-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c1d39-130">Click Save.</span></span>
19. <span data-ttu-id="c1d39-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1d39-131">Close the page.</span></span>
20. <span data-ttu-id="c1d39-132">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Értékesítési ár (kiadás) elemet.</span><span class="sxs-lookup"><span data-stu-id="c1d39-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="c1d39-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1d39-133">Click New.</span></span>
22. <span data-ttu-id="c1d39-134">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="c1d39-135">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1d39-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="c1d39-136">Adjon meg egy számot az Árazás mezőben.</span><span class="sxs-lookup"><span data-stu-id="c1d39-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="c1d39-137">Amikor a dolgozó a költségnaplóba beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár.</span><span class="sxs-lookup"><span data-stu-id="c1d39-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="c1d39-138">Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.</span><span class="sxs-lookup"><span data-stu-id="c1d39-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="c1d39-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c1d39-139">Click Save.</span></span>


--- 
title: "Munka és kiadások elszámolóárainak konfigurálása"
description: "Ez az eljárás bemutatja, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 432b5b195b29fb03786cb0560e277735b531b7d7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="7a582-103">Munka és kiadások elszámolóárainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7a582-103">Configure standard costs for labor and expenses</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a582-104">Ez az eljárás bemutatja, hogyan állítható be egy projekt munkához és kiadásokhoz tartozó elszámolóára.</span><span class="sxs-lookup"><span data-stu-id="7a582-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="7a582-105">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="7a582-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="7a582-106">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Költségár (óra) elemet.</span><span class="sxs-lookup"><span data-stu-id="7a582-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="7a582-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7a582-107">Click New.</span></span>
3. <span data-ttu-id="7a582-108">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="7a582-109">Adjon meg egy számot az Önköltségi ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="7a582-110">A projektkategóriához megadható elszámolóár, de megadható az önköltségi ár dolgozószám, projektszám, kategória, dátum vagy ezek tetszőleges kombinációja alapján is.</span><span class="sxs-lookup"><span data-stu-id="7a582-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="7a582-111">A rendszer a legnagyobb részletességű szinten létező önköltségi árat alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="7a582-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="7a582-112">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7a582-112">Click Save.</span></span>
6. <span data-ttu-id="7a582-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7a582-113">Close the page.</span></span>
7. <span data-ttu-id="7a582-114">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Eladási ár (óra) elemet.</span><span class="sxs-lookup"><span data-stu-id="7a582-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="7a582-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7a582-115">Click New.</span></span>
9. <span data-ttu-id="7a582-116">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="7a582-117">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7a582-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="7a582-118">Adjon meg egy számot az Árazás mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="7a582-119">Beállítható az óratranzakciók és projektkategóriák szokásos eladási ára.</span><span class="sxs-lookup"><span data-stu-id="7a582-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="7a582-120">Szintén be lehet állítani dolgozók száma, projekt száma, kategória, tranzakció dátuma vagy ezek bármely kombinációja szerinti eladási árakat.</span><span class="sxs-lookup"><span data-stu-id="7a582-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="7a582-121">Amikor a dolgozó az óranaplóban beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár.</span><span class="sxs-lookup"><span data-stu-id="7a582-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="7a582-122">Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.</span><span class="sxs-lookup"><span data-stu-id="7a582-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="7a582-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7a582-123">Click Save.</span></span>
13. <span data-ttu-id="7a582-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7a582-124">Close the page.</span></span>
14. <span data-ttu-id="7a582-125">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Költségár (kiadás) elemet.</span><span class="sxs-lookup"><span data-stu-id="7a582-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="7a582-126">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7a582-126">Click New.</span></span>
16. <span data-ttu-id="7a582-127">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="7a582-128">Adjon meg egy számot az Önköltségi ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="7a582-129">Több mező is kitölthető, de ez a minimálisan szükséges a rekord mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="7a582-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="7a582-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7a582-130">Click Save.</span></span>
19. <span data-ttu-id="7a582-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7a582-131">Close the page.</span></span>
20. <span data-ttu-id="7a582-132">Nyissa meg a Projektvezetés és könyvelés > Beállítás > Árak > Értékesítési ár (kiadás) elemet.</span><span class="sxs-lookup"><span data-stu-id="7a582-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="7a582-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7a582-133">Click New.</span></span>
22. <span data-ttu-id="7a582-134">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="7a582-135">Az Érvényes mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7a582-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="7a582-136">Adjon meg egy számot az Árazás mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a582-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="7a582-137">Amikor a dolgozó a költségnaplóba beviszi a tranzakciót, a legrészletesebb szintű eladási ár lesz az aktuális eladási ár.</span><span class="sxs-lookup"><span data-stu-id="7a582-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="7a582-138">Ha például egy általános és egy dolgozóra vonatkozó eladási ár is be van állítva, akkor a rendszer a dolgozóra vonatkozó eladási árat választja.</span><span class="sxs-lookup"><span data-stu-id="7a582-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="7a582-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7a582-139">Click Save.</span></span>



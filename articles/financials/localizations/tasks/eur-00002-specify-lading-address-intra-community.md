--- 
title: "Közösségen belüli tranzakcióhoz berakodási cím megadása"
description: "Ez az eljárás bemutatja, hogyan adhatja meg egy közösségen belüli kereskedelmi tranzakció berakodási címét."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0feeba19510d3c2790b1a77bca3c8ec6e7078726
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="specify-a-lading-address-for-an-intra-community-transaction"></a><span data-ttu-id="1479c-103">Közösségen belüli tranzakcióhoz berakodási cím megadása</span><span class="sxs-lookup"><span data-stu-id="1479c-103">Specify a lading address for an intra-community transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1479c-104">Ez az eljárás bemutatja, hogyan adhatja meg egy közösségen belüli kereskedelmi tranzakció berakodási címét.</span><span class="sxs-lookup"><span data-stu-id="1479c-104">This procedure shows how to specify a lading address for an intra-community trade transaction.</span></span> <span data-ttu-id="1479c-105">Például egy német cég egy német üzleti címmel rendelkező szállítótól rendel cikkeket.</span><span class="sxs-lookup"><span data-stu-id="1479c-105">For example, a Germany company orders items from a vendor with a German business address.</span></span> <span data-ttu-id="1479c-106">A szállítónak van egy raktára Olaszországban, és innen szállítja a cikkeket.</span><span class="sxs-lookup"><span data-stu-id="1479c-106">This vendor has a warehouse in Italy and ships the items from there.</span></span> <span data-ttu-id="1479c-107">Ezt a szállítást jelenteni kell az Intrastatban.</span><span class="sxs-lookup"><span data-stu-id="1479c-107">This delivery must be reported in the Intrastat.</span></span> <span data-ttu-id="1479c-108">Ugyanez érvényes az ügyfél visszáruszállításaira is.</span><span class="sxs-lookup"><span data-stu-id="1479c-108">The same behavior is valid for customer returns.</span></span>
<span data-ttu-id="1479c-109">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="1479c-109">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="1479c-110">Ezt a feladatot a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="1479c-110">The task was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="1479c-111">Az eljárás végrehajtása előtt be kell állítania az Intrastat jelentéskészítést.</span><span class="sxs-lookup"><span data-stu-id="1479c-111">Before you can complete this procedure, you must configure Intrastat reporting.</span></span> <span data-ttu-id="1479c-112">Ez az eljárás könyvelőknek szól.</span><span class="sxs-lookup"><span data-stu-id="1479c-112">This procedure is intended for accountants.</span></span> <span data-ttu-id="1479c-113">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="1479c-113">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="1479c-114">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="1479c-114">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="1479c-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1479c-115">Click New.</span></span>
3. <span data-ttu-id="1479c-116">Érték megadása vagy kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1479c-116">Enter or select a value</span></span>
    * <span data-ttu-id="1479c-117">Válassza ki például a DE-001-et.</span><span class="sxs-lookup"><span data-stu-id="1479c-117">For example, select DE-001.</span></span> <span data-ttu-id="1479c-118">A szállító német üzleti címmel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="1479c-118">This vendor has a German business address.</span></span>  
4. <span data-ttu-id="1479c-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1479c-119">Click OK.</span></span>
5. <span data-ttu-id="1479c-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1479c-120">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="1479c-121">Az Elemszám mezőben adjon meg, illetve válasszon ki egy értéket: D0001.</span><span class="sxs-lookup"><span data-stu-id="1479c-121">In the Item number field, enter or select a value D0001.</span></span>
7. <span data-ttu-id="1479c-122">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1479c-122">Click Save.</span></span>
8. <span data-ttu-id="1479c-123">A Művelet panelen kattintson a Fogadás elemre.</span><span class="sxs-lookup"><span data-stu-id="1479c-123">On the Action Pane, click Receive.</span></span>
9. <span data-ttu-id="1479c-124">Kattintson a Szállítás részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1479c-124">Click Transportation details.</span></span>
10. <span data-ttu-id="1479c-125">A Berakodás dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="1479c-125">In the Loading date and time field, enter a date and time.</span></span>
11. <span data-ttu-id="1479c-126">Kattintson az Új cím felvétele lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1479c-126">Click Add address.</span></span>
12. <span data-ttu-id="1479c-127">Kattintson az Új gombra, és hozzon létre egy új címet, amelynek a célja a berakodás.</span><span class="sxs-lookup"><span data-stu-id="1479c-127">Click New and create new address with purpose Lading.</span></span>
13. <span data-ttu-id="1479c-128">A Név vagy leírás mezőbe írja be az „olasz” értéket.</span><span class="sxs-lookup"><span data-stu-id="1479c-128">In the Name or description field, type 'Italian'.</span></span>
14. <span data-ttu-id="1479c-129">Értékként válassza ki a berakodást.</span><span class="sxs-lookup"><span data-stu-id="1479c-129">Select Lading as the value.</span></span>
    * <span data-ttu-id="1479c-130">Fontos megjegyezni, hogy a cím céljának berakodásnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1479c-130">Note that that address purpose must be Lading.</span></span>  
15. <span data-ttu-id="1479c-131">Az Ország/régió mezőben adja meg vagy válassza az ITA értéket.</span><span class="sxs-lookup"><span data-stu-id="1479c-131">In the Country/region field, enter or select a value ITA.</span></span>
16. <span data-ttu-id="1479c-132">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1479c-132">Click Save.</span></span>
17. <span data-ttu-id="1479c-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1479c-133">Close the page.</span></span>
18. <span data-ttu-id="1479c-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1479c-134">Click Save.</span></span>
    * <span data-ttu-id="1479c-135">Ellenőrizze a berakodási cím helyességét.</span><span class="sxs-lookup"><span data-stu-id="1479c-135">Verify that the lading address is correct.</span></span>  
19. <span data-ttu-id="1479c-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1479c-136">Close the page.</span></span>
20. <span data-ttu-id="1479c-137">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="1479c-137">On the Action Pane, click Purchase.</span></span>
21. <span data-ttu-id="1479c-138">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="1479c-138">Click Confirm.</span></span>
22. <span data-ttu-id="1479c-139">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1479c-139">On the Action Pane, click Invoice.</span></span>
23. <span data-ttu-id="1479c-140">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1479c-140">Click Invoice.</span></span>
24. <span data-ttu-id="1479c-141">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1479c-141">In the Number field, type a value.</span></span>
25. <span data-ttu-id="1479c-142">A Számla dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="1479c-142">In the Invoice date field, enter a date.</span></span>
26. <span data-ttu-id="1479c-143">Kattintson az Alapértelmezett forrás: Termék érkező mennyisége lehetőségre a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1479c-143">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="1479c-144">A Sorok alapértelmezett mennyisége mezőben válassza ki a „Megrendelt mennyiség” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1479c-144">In the Default quantity for lines field, select 'Ordered quantity'.</span></span>
28. <span data-ttu-id="1479c-145">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1479c-145">Click OK.</span></span>
29. <span data-ttu-id="1479c-146">Kattintson a Szállítás részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1479c-146">Click Transportation details.</span></span>
    * <span data-ttu-id="1479c-147">Győződjön meg arról, hogy az árukat Olaszországból szállítják.</span><span class="sxs-lookup"><span data-stu-id="1479c-147">Verify that goods were shipped from Italy.</span></span> <span data-ttu-id="1479c-148">Szükség esetén módosíthatja a berakodás részleteit.</span><span class="sxs-lookup"><span data-stu-id="1479c-148">If necessary, you can edit the lading details.</span></span>  
30. <span data-ttu-id="1479c-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1479c-149">Close the page.</span></span>
31. <span data-ttu-id="1479c-150">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1479c-150">Click Post.</span></span>
32. <span data-ttu-id="1479c-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1479c-151">Close the page.</span></span>
33. <span data-ttu-id="1479c-152">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.</span><span class="sxs-lookup"><span data-stu-id="1479c-152">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
34. <span data-ttu-id="1479c-153">Kattintson az Áthelyezés elemre.</span><span class="sxs-lookup"><span data-stu-id="1479c-153">Click Transfer.</span></span>
35. <span data-ttu-id="1479c-154">Válassza ki az Igen lehetőséget a Szállítói számla mezőben.</span><span class="sxs-lookup"><span data-stu-id="1479c-154">Select Yes in the Vendor invoice field.</span></span>
36. <span data-ttu-id="1479c-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1479c-155">Click OK.</span></span>
37. <span data-ttu-id="1479c-156">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="1479c-156">Click the General tab.</span></span>
    * <span data-ttu-id="1479c-157">Keressen meg egy újonnan létrehozott sort, és győződjön meg arról, hogy a feladó az árukat Olaszországból szállította.</span><span class="sxs-lookup"><span data-stu-id="1479c-157">Find a newly created line and verify that the sender shipped the goods from Italy.</span></span>  



--- 
title: "Szállítási ütemezés létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhatja létre az értékesítési rendelések kiszállítási ütemezését."
author: omulvad
manager: AnnBe
ms.date: 02/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 407337d31e0aa68217a27a5709da16ddc7d6e4a1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-delivery-schedule"></a><span data-ttu-id="12d9a-103">Szállítási ütemezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="12d9a-103">Create a delivery schedule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12d9a-104">Ez az eljárás bemutatja, hogyan hozhatja létre az értékesítési rendelések kiszállítási ütemezését.</span><span class="sxs-lookup"><span data-stu-id="12d9a-104">This procedure demonstrates how to create a delivery schedule for a sales order.</span></span> <span data-ttu-id="12d9a-105">A szállítási ütemezés akkor használatos, ha egy rendeléshez tartozó mennyiséget több részletben kell szállítani, vagy ilyen árajánlat szükséges.</span><span class="sxs-lookup"><span data-stu-id="12d9a-105">A delivery schedule is used when a quantity on an order or a quotation is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="12d9a-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="12d9a-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-delivery-schedule"></a><span data-ttu-id="12d9a-107">Szállítási ütemezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="12d9a-107">Create delivery schedule</span></span>
1. <span data-ttu-id="12d9a-108">Ugrás az összes értékesítési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="12d9a-108">Go to All sales orders.</span></span>
2. <span data-ttu-id="12d9a-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12d9a-109">Click New.</span></span>
3. <span data-ttu-id="12d9a-110">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12d9a-110">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="12d9a-111">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12d9a-111">Click OK.</span></span>
5. <span data-ttu-id="12d9a-112">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12d9a-112">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="12d9a-113">A Mennyiség mezőben adjon meg egy 1-nél nagyobb számot.</span><span class="sxs-lookup"><span data-stu-id="12d9a-113">In the Quantity field, enter a number that is bigger than 1.</span></span>
7. <span data-ttu-id="12d9a-114">Kattintson az Értékesítésirendelés-sor lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12d9a-114">Click Sales order line.</span></span>
8. <span data-ttu-id="12d9a-115">Kattintson a Szállítási ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="12d9a-115">Click Delivery schedule.</span></span>
    * <span data-ttu-id="12d9a-116">A Szállítási ütemezés lap az a hely, ahol megadhatja a szállítmányok számát, amely mennyiséggel a rendelési sor szállításra kerül a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="12d9a-116">The Delivery schedule page is the place where you can specify the number of shipments in which the total quantity of the order line will be delivered to the customer.</span></span>    
    * <span data-ttu-id="12d9a-117">Alapértelmezés szerint a rendszer bemásolja a teljes mennyiséget és az egyéb részleteket az eredeti eladási sorból az első szállítási ütemezés sorába.</span><span class="sxs-lookup"><span data-stu-id="12d9a-117">By default, the system copies the total quantity and other delivery details of the original sales line into the first delivery schedule line.</span></span> <span data-ttu-id="12d9a-118">Ebben a példában két szállítmányhoz ütemezést hozunk létre, a második szállítmány dátumát egy héttel eltolva az első szállítmányétól.</span><span class="sxs-lookup"><span data-stu-id="12d9a-118">In this example, we’ll create a schedule for two shipments, with the second shipment's date offset by a week from the first one.</span></span>  
9. <span data-ttu-id="12d9a-119">A Mennyiség mezőben adjon meg egy számot, amely a teljes mennyiség része.</span><span class="sxs-lookup"><span data-stu-id="12d9a-119">In the Quantity field, enter a number that is part of the total quantity.</span></span>
10. <span data-ttu-id="12d9a-120">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="12d9a-120">Click New.</span></span>
11. <span data-ttu-id="12d9a-121">Ezután a Mennyiség mezőben adja meg a visszamaradó mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="12d9a-121">In the Quantity field, enter the remaining quantity.</span></span>
12. <span data-ttu-id="12d9a-122">A kért szállítási dátum mezőben adjon meg egy olyan dátumot, amelyik egy héttel korábbi az első szállítási dátumnál.</span><span class="sxs-lookup"><span data-stu-id="12d9a-122">In the Requested ship date field, enter a date a date that is one week ahead from the date of the first delivery line.</span></span>
    * <span data-ttu-id="12d9a-123">A két lehetőség a Költségek átalakítás gyorslapon meghatározza, hogy hogyan oszoljanak el a költségek a szállítási ütemezés sorok között, miután hozzárendelte őket az eredeti rendelési sorhoz.</span><span class="sxs-lookup"><span data-stu-id="12d9a-123">The two options on the Charges conversion FastTab control how you want the charges to be distributed across the delivery schedule lines, once they’ve been assigned to the original order line.</span></span> <span data-ttu-id="12d9a-124">Ha a Bruttó összeg másolását választja ugyanaz a költségösszeg kerül másolásra minden sorba.</span><span class="sxs-lookup"><span data-stu-id="12d9a-124">If you select Copy gross amounts, the same charge amount is copied to each line.</span></span> <span data-ttu-id="12d9a-125">A Felosztás szállítmánysorokra lehetőség egyenlően osztja el a költségeket a szállítmánysorok között.</span><span class="sxs-lookup"><span data-stu-id="12d9a-125">The Allocate to delivery lines option divides the charge equally across the delivery lines.</span></span>  
    * <span data-ttu-id="12d9a-126">Csak rögzített költségek oszthatók, míg a változó költségek változatlanul a sorokba kerülnek.</span><span class="sxs-lookup"><span data-stu-id="12d9a-126">Only fixed charges can be divided, whereas variable charges will still be copied to the lines.</span></span>  
13. <span data-ttu-id="12d9a-127">Vigye el a kurzort a második szállítási sortól az oldal frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="12d9a-127">Move the cursor away from the second delivery line to update the page.</span></span>
    * <span data-ttu-id="12d9a-128">Nyomon követheti a teljes mennyiséget, ami a szállítási ütemezés soraihoz van rendelve ha megtekinti az Összes és Maradvány mezőket.</span><span class="sxs-lookup"><span data-stu-id="12d9a-128">You can keep track of the total quantity that’s allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="12d9a-129">Ha a maradvány mennyisége nulla, akkor a teljes mennyiség az eredeti sorból az ütemezéshez lett rendelve.</span><span class="sxs-lookup"><span data-stu-id="12d9a-129">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>   
14. <span data-ttu-id="12d9a-130">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12d9a-130">Click OK.</span></span>
    * <span data-ttu-id="12d9a-131">A szállítási ütemezés most a rendeléssorokba lett másolva.</span><span class="sxs-lookup"><span data-stu-id="12d9a-131">The delivery schedule has now been copied to the order lines.</span></span>   
    * <span data-ttu-id="12d9a-132">Az eredeti rendelési sorra hivatkozó Kereskedelmi sor egy több szállítással rendelkező Rendeléssorhoz lett konvertálva.</span><span class="sxs-lookup"><span data-stu-id="12d9a-132">The original order line, referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="12d9a-133">Egy külön ikon jelzi, ami fejlécként szolgál a szállítási sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="12d9a-133">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
    * <span data-ttu-id="12d9a-134">A szállítási sorokként hivatkozott két új sor egy szállítási ütemezést képez.</span><span class="sxs-lookup"><span data-stu-id="12d9a-134">The two new lines, referred to as delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="12d9a-135">A rendelés szembeni ezen sorok és nem az eredeti sor szerint kerül feldolgozásra.</span><span class="sxs-lookup"><span data-stu-id="12d9a-135">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="12d9a-136">Ha a dokumentumokat, például visszaigazolási leveleket, szállítóleveleket, kitárolási leveleket vagy számlákat nyomtat csak a szállítási sorok láthatóak.</span><span class="sxs-lookup"><span data-stu-id="12d9a-136">If documents such as confirmation slips, picking lists, packing slips, or invoices are printed, only the delivery lines are shown.</span></span>   
    * <span data-ttu-id="12d9a-137">A szállítási sorok különböző szállítási dátumokkal, mennyiségekkel, szállítási módokkal és tárolási dimenziókkal rendelkezhetnek, például webhely és raktár.</span><span class="sxs-lookup"><span data-stu-id="12d9a-137">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span> <span data-ttu-id="12d9a-138">Ugyanakkor a termékdimenzióknak mindig egyezniük kell a kereskedelmi sorral, amit nem lehet változtatni.</span><span class="sxs-lookup"><span data-stu-id="12d9a-138">However, the product dimensions must always match the ones on the commercial line and can't be changed.</span></span>  
15. <span data-ttu-id="12d9a-139">A Mennyiség mezőben adjon meg a jelenleginél nagyobb számot.</span><span class="sxs-lookup"><span data-stu-id="12d9a-139">In the Quantity field, enter a number that's bigger than the current one.</span></span>
16. <span data-ttu-id="12d9a-140">Válassza ki a kereskedelmi sort a mennyiség-újraszámítás hatásának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="12d9a-140">Select the commercial line to see the effect of the quantity recalculation.</span></span>
17. <span data-ttu-id="12d9a-141">A Művelet panelen kattintson a Kitárolás és csomagolás elemre.</span><span class="sxs-lookup"><span data-stu-id="12d9a-141">On the Action Pane, click Pick and pack.</span></span>
18. <span data-ttu-id="12d9a-142">Kattintson A szállítólevél feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12d9a-142">Click Post packing slip.</span></span>
19. <span data-ttu-id="12d9a-143">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="12d9a-143">Expand the Parameters section.</span></span>
20. <span data-ttu-id="12d9a-144">A Mennyiség mezőben válassza a „Mind” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12d9a-144">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="12d9a-145">Vegye figyelembe, hogy a szállítólevél a két szállítási ütemezési sorba és a nem az eredeti rendelési sorba fog létrejönni.</span><span class="sxs-lookup"><span data-stu-id="12d9a-145">Note that the packing slip will be created for the two delivery schedule lines and not the original order line.</span></span>  
21. <span data-ttu-id="12d9a-146">Válassza az Igen lehetőséget az Szállítólevél nyomtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="12d9a-146">Select Yes in the Print packing slip field.</span></span>
22. <span data-ttu-id="12d9a-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12d9a-147">Click OK.</span></span>
23. <span data-ttu-id="12d9a-148">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="12d9a-148">Click Yes.</span></span>
24. <span data-ttu-id="12d9a-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12d9a-149">Close the page.</span></span>



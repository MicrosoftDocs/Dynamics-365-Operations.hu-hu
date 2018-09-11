--- 
title: "Értékesítési rendelések szállítása raktározás nélkül"
description: "Ez az útmutató bemutatja, hogyan lehet egy értékesítési rendelést frissíteni, ha a termékeket kiszállították a vevőhöz."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 1d4d43ca62901ecd2280f21dfbeee9cb70ec600e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="12622-103">Értékesítési rendelések szállítása raktározás nélkül</span><span class="sxs-lookup"><span data-stu-id="12622-103">Ship sales orders without warehousing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12622-104">Ez az útmutató bemutatja, hogyan lehet egy értékesítési rendelést frissíteni, ha a termékeket kiszállították a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="12622-104">This guide demonstrates how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="12622-105">Ez az útmutató olyan teljesítési folyamatra használható, amely nincs beállítva raktárkezelésre (sem alap, sem speciális raktározásra), és ezért szükséges regisztrálni termék kitárolást szállítás előtt.</span><span class="sxs-lookup"><span data-stu-id="12622-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="12622-106">Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="12622-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="12622-107">Mindkét esetben, mielőtt elkezdi a feladatot, hozzon létre egy értékesítési rendelést egy raktározott termékre, amelynek mennyisége több, mint 1.</span><span class="sxs-lookup"><span data-stu-id="12622-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="12622-108">A feladás hibájának elkerülése érdekében ellenőrizze, hogy a termék készleten lévő mennyisége a webhelyen és a megrendeléshez kiválasztott raktárban elegendő a megrendelés teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="12622-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you’ve selected on the order covers the order quantity.</span></span>


## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="12622-109">Egy rendelés szállítólevelének feladása</span><span class="sxs-lookup"><span data-stu-id="12622-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="12622-110">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="12622-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="12622-111">A listában keresse meg és válassza ki a megrendelést, amelyet ehhez a feladathoz hozott létre.</span><span class="sxs-lookup"><span data-stu-id="12622-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="12622-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="12622-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="12622-113">A műveleti ablaktáblán kattintson a Választáás elemre, majd válassza ki a csomag elemet.</span><span class="sxs-lookup"><span data-stu-id="12622-113">On the Action Pane, click Pick and pack.</span></span>
5. <span data-ttu-id="12622-114">Kattintson A szállítólevél feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12622-114">Click Post packing slip.</span></span>
6. <span data-ttu-id="12622-115">Bontsa ki vagy csukja össze a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="12622-115">Expand or collapse the Parameters section.</span></span>
7. <span data-ttu-id="12622-116">A Mennyiség mezőben válassza a „Mind” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12622-116">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="12622-117">Egyéb lehetőségek a következők: Szállítás és Kitárolt.</span><span class="sxs-lookup"><span data-stu-id="12622-117">Other options include Deliver now and Picked.</span></span> <span data-ttu-id="12622-118">Ha a rendelési sort részlegesen kell szállítani és a rendelési sor Szállítás most mezőjében érték van megadva, válassza ki a Szállítás most lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12622-118">If the order line is to be shipped partially and the Deliver now field on the order line contains a quantity, you would select Deliver now.</span></span> <span data-ttu-id="12622-119">Ha a szervezete teljesítési folyamatában a kitárolás külön folyamatként szerepel, amelyet egy kitárolási lista kezel és regisztrál, válassza a Kitárolt lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12622-119">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select Picked.</span></span>  
    * <span data-ttu-id="12622-120">Ellenőrizze, hogy a Feladás értéke Igen.</span><span class="sxs-lookup"><span data-stu-id="12622-120">Check that the Posting option is set to Yes.</span></span>  
8. <span data-ttu-id="12622-121">Állítsa a Szállítólevél nyomtatása pontot Igenre.</span><span class="sxs-lookup"><span data-stu-id="12622-121">Set the Print packing slip option to Yes.</span></span>
    * <span data-ttu-id="12622-122">Az Áttekintés lapon található az ehhez a feladáshoz létrehozandó szállítólevelek listája.</span><span class="sxs-lookup"><span data-stu-id="12622-122">The Overview tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="12622-123">Ha egy egyedülálló rendelést szállít, általában egy szállítólevél van.</span><span class="sxs-lookup"><span data-stu-id="12622-123">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="12622-124">Azonban ha a megrendelés sorai több oldalról kerülnek szállításra, a feladást automatikusan a megfelelő számú dokumentumra bontja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="12622-124">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="12622-125">Ez egy kötelező feltétel, nem lehet megváltoztatni.</span><span class="sxs-lookup"><span data-stu-id="12622-125">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="12622-126">Ehhez hasonlóan a feladási is több dokumentumra oszlik, ha a rendelési sorok eltérő szállítási címekkel rendelkeznek, és a szállítási irányelv előírja a felosztást.</span><span class="sxs-lookup"><span data-stu-id="12622-126">Similarly, the posting will also be split into multiple documents if the order’s lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
9. <span data-ttu-id="12622-127">A Sorok lapon válassza ki a szállítandó rendelési sort.</span><span class="sxs-lookup"><span data-stu-id="12622-127">On the Lines tab, select the row for the order line to be shipped.</span></span>
10. <span data-ttu-id="12622-128">A Frissítés mezőben írjon be egy számot, amely kisebb, mint az eredeti mennyiség.</span><span class="sxs-lookup"><span data-stu-id="12622-128">In the Update field, enter a number lower than the original quantity.</span></span>
11. <span data-ttu-id="12622-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12622-129">Click OK.</span></span>
12. <span data-ttu-id="12622-130">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="12622-130">Click Yes.</span></span>
13. <span data-ttu-id="12622-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12622-131">Close the page.</span></span>
14. <span data-ttu-id="12622-132">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="12622-132">On the Action Pane, click Options.</span></span>
15. <span data-ttu-id="12622-133">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="12622-133">Click Change view.</span></span>
16. <span data-ttu-id="12622-134">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="12622-134">Click Header view.</span></span>
    * <span data-ttu-id="12622-135">Ha a rendelés összes sora teljesen kiszállított, a megrendelés állapota Nyitottról Szállítottra változik.</span><span class="sxs-lookup"><span data-stu-id="12622-135">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    * <span data-ttu-id="12622-136">Ebben a példában a rendelési sort részben kiszállították.</span><span class="sxs-lookup"><span data-stu-id="12622-136">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="12622-137">Ezért a megrendelés állapota Nyitott marad.</span><span class="sxs-lookup"><span data-stu-id="12622-137">This is why the the order status remains Open.</span></span>     
    * <span data-ttu-id="12622-138">A Dokumentum állapota mezőbe Szállítólevél van beállítva, mert legalább egy rendelési sor szállított.</span><span class="sxs-lookup"><span data-stu-id="12622-138">The Document status field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
17. <span data-ttu-id="12622-139">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="12622-139">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="12622-140">Kattintson a Sormennyiség lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12622-140">Click Line quantity.</span></span>
19. <span data-ttu-id="12622-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12622-141">Close the page.</span></span>
20. <span data-ttu-id="12622-142">A Művelet panelen kattintson a Kitárolás és csomagolás elemre.</span><span class="sxs-lookup"><span data-stu-id="12622-142">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="12622-143">Kattintson a Szállítólevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12622-143">Click Packing slip.</span></span>
    * <span data-ttu-id="12622-144">A Szállítólevél napló oldal tartalmazza az összes szállítólevél dokumentumot, amely az adott megrendeléshez lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="12622-144">The Packing slip journal page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="12622-145">Ellenőrizheti a dokumentumok részleteit és kinyomtathatja őket.</span><span class="sxs-lookup"><span data-stu-id="12622-145">You can review details of each document and print them, if you wish.</span></span>  



---
title: "A készlet elérhetőségének ellenőrzése"
description: "Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: b1c5331379ec1b16ef13ea64ee7f0324828e50a2
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="071e6-103">A készlet elérhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="071e6-103">Check the availability of stock</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="071e6-104">Ez az eljárás bemutatja, hogy hogyan ellenőrizheti egy adott cikkszám aktuális, illetve ténylegesen rendelkezésre álló készletét.</span><span class="sxs-lookup"><span data-stu-id="071e6-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="071e6-105">Az eljárás azt is bemutatja, hogy hogyan jelenítheti meg az adott cikkel kapcsolatos szállítói adatokat.</span><span class="sxs-lookup"><span data-stu-id="071e6-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="071e6-106">A tényleges aktuális készlet a ténylegesen rendelkezésre álló, azaz a beszerzett, átvett és nyilvántartásba vett készletet mutatja meg.</span><span class="sxs-lookup"><span data-stu-id="071e6-106">Physical on-hand inventory is the on-hand inventory that’s available – that is, it’s purchased, received and registered.</span></span> <span data-ttu-id="071e6-107">Az aktuális készlet nem csak a ténylegesen rendelkezésre álló, azaz a tényleges aktuális készletet, hanem a már megrendelt, viszont még nem át- vagy nyilvántartásba vett készletet is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="071e6-107">On-hand inventory includes the available on-hand inventory, but also the inventory that’s been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="071e6-108">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="071e6-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="071e6-109">A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket.</span><span class="sxs-lookup"><span data-stu-id="071e6-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="071e6-110">Ezeket a feladatokat jellemzően egy raktári dolgozó végzi el.</span><span class="sxs-lookup"><span data-stu-id="071e6-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="071e6-111">Ellenőrizze az adott cikk aktuális készletét</span><span class="sxs-lookup"><span data-stu-id="071e6-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="071e6-112">Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Aktuális készlet.</span><span class="sxs-lookup"><span data-stu-id="071e6-112">Go to Inventory management > Inquiries and reports > On-hand inventory.</span></span>
2. <span data-ttu-id="071e6-113">Válassza ki a Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="071e6-113">Select the Item number row.</span></span>
    * <span data-ttu-id="071e6-114">Az aktuális készlet cikkszám szerinti lekérdezéséhez válassza ki azt a sort, ahol a Táblázat beállítása Aktuális készlet, a Mező beállítása pedig cikkszám.</span><span class="sxs-lookup"><span data-stu-id="071e6-114">To query the on-hand inventory by item number, select the row where the Table is set to On-hand inventory and Field is set to Item number.</span></span>  
3. <span data-ttu-id="071e6-115">A Feltételek mezőben válassza ki a lekérdezni kívánt cikket.</span><span class="sxs-lookup"><span data-stu-id="071e6-115">In the Criteria field, select the item you want to query.</span></span>
    * <span data-ttu-id="071e6-116">Ha a USMF vállalat bemutató adatait alkalmazza, úgy használhatja az „M9201” értéket.</span><span class="sxs-lookup"><span data-stu-id="071e6-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="071e6-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="071e6-117">Click OK.</span></span>
5. <span data-ttu-id="071e6-118">Kattintson a Dimenziókra.</span><span class="sxs-lookup"><span data-stu-id="071e6-118">Click Dimensions.</span></span>
    * <span data-ttu-id="071e6-119">A Dimenziók lapon tudja beállítani az aktuális készletre vonatkozó információk részletességét.</span><span class="sxs-lookup"><span data-stu-id="071e6-119">The Dimensions tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="071e6-120">A foglalással kapcsolatos adatok megtekintéséhez a speciális raktározási (WHS) folyamatokat használó cikkek kapcsán meg kell jelenítenie az összes készletdimenziót.</span><span class="sxs-lookup"><span data-stu-id="071e6-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>  
6. <span data-ttu-id="071e6-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="071e6-121">Click OK.</span></span>
7. <span data-ttu-id="071e6-122">A Műveleti ablakban kattintson a Kapcsolódó információ elemre.</span><span class="sxs-lookup"><span data-stu-id="071e6-122">On the Action Pane, click Related information.</span></span>
    * <span data-ttu-id="071e6-123">Ha nem ez jelenik meg, úgy elképzelhetően rá kell kattintania az Ellipszis gomb (...) parancsra a további műveleti ablak opciók megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="071e6-123">If you don’t see this, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>  
8. <span data-ttu-id="071e6-124">Kattintson a Szállítmány-összesítés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="071e6-124">Click Supply overview.</span></span>
    * <span data-ttu-id="071e6-125">A Szállítmány-áttekintés lap olyan konkrét cikkről szolgáltat információt, mint az aktuális mennyiség, az átfutási idő vagy a szállítói adatok.</span><span class="sxs-lookup"><span data-stu-id="071e6-125">The Supply overview tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="071e6-126">Bontsa ki a Aktuális részt.</span><span class="sxs-lookup"><span data-stu-id="071e6-126">Expand the On-hand section.</span></span>
10. <span data-ttu-id="071e6-127">Bontsa ki a Szállító szakaszt.</span><span class="sxs-lookup"><span data-stu-id="071e6-127">Expand the Vendors section.</span></span>
11. <span data-ttu-id="071e6-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="071e6-128">Close the page.</span></span>
12. <span data-ttu-id="071e6-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="071e6-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="071e6-130">Ellenőrizze az adott cikk tényleges aktuális készletét</span><span class="sxs-lookup"><span data-stu-id="071e6-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="071e6-131">Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Tényleges aktuális készlet.</span><span class="sxs-lookup"><span data-stu-id="071e6-131">Go to Warehouse management > Inquiries and reports > Physical on-hand inventory.</span></span>
2. <span data-ttu-id="071e6-132">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="071e6-132">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="071e6-133">A cikklistát a Telephely és Raktár mezők segítségével tudja szűrni.</span><span class="sxs-lookup"><span data-stu-id="071e6-133">You can use the Site and Warehouse fields to filter the list of items.</span></span>  
3. <span data-ttu-id="071e6-134">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="071e6-134">Refresh the page.</span></span>
4. <span data-ttu-id="071e6-135">Kattintson a Dimenziók megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="071e6-135">Click Display Dimensions.</span></span>
    * <span data-ttu-id="071e6-136">A Dimenziókat megjelenítő lapon tudja beállítani az aktuális készletre vonatkozó információk részletességét.</span><span class="sxs-lookup"><span data-stu-id="071e6-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>  
5. <span data-ttu-id="071e6-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="071e6-137">Click OK.</span></span>
6. <span data-ttu-id="071e6-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="071e6-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="071e6-139">Ellenőrizze az aktuális készletet hely szerint.</span><span class="sxs-lookup"><span data-stu-id="071e6-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="071e6-140">Nyissa meg a következőt: Készletkezelés > Lekérdezések és jelentések > Aktuális helyenként.</span><span class="sxs-lookup"><span data-stu-id="071e6-140">Go to Warehouse management > Inquiries and reports > On hand by location.</span></span>
2. <span data-ttu-id="071e6-141">Érték beírása a Raktár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="071e6-141">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="071e6-142">Ha a USMF vállalat bemutató adatait alkalmazza, úgy használhatja az „51” értéket.</span><span class="sxs-lookup"><span data-stu-id="071e6-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="071e6-143">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="071e6-143">Refresh the page.</span></span>
4. <span data-ttu-id="071e6-144">Kattintson a Dimenziók megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="071e6-144">Click Display Dimensions.</span></span>
5. <span data-ttu-id="071e6-145">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="071e6-145">Click OK.</span></span>
6. <span data-ttu-id="071e6-146">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="071e6-146">Close the page.</span></span>


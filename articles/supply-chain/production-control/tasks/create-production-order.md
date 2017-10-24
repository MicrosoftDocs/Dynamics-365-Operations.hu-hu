--- 
title: "Termelési rendelés létrehozása"
description: "Ez az eljárás bemutatja, hogyan lehet termelési rendelést létrehozni."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 730adcea0ac59f683ecae8cbb62025bd7db75c55
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-production-order"></a><span data-ttu-id="1bd52-103">Termelési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="1bd52-103">Create a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1bd52-104">Ez az eljárás bemutatja, hogyan lehet termelési rendelést létrehozni.</span><span class="sxs-lookup"><span data-stu-id="1bd52-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="1bd52-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="1bd52-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1bd52-106">Ez az első eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="1bd52-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="1bd52-107">Termelési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="1bd52-107">Create a production order</span></span>
1. <span data-ttu-id="1bd52-108">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="1bd52-109">Kattintson az Új termelési rendelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-109">Click New production order.</span></span>
3. <span data-ttu-id="1bd52-110">A Cikkszám mezőbe írja be az „D0001” értéket.</span><span class="sxs-lookup"><span data-stu-id="1bd52-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="1bd52-111">A Szállítás mezőben adja meg a szállítási dátumot.</span><span class="sxs-lookup"><span data-stu-id="1bd52-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="1bd52-112">A szállítási dátum azt jelzi, hogy a termelési rendelésnek mikor kell véget érnie, hogy időben lehessen szállítani.</span><span class="sxs-lookup"><span data-stu-id="1bd52-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="1bd52-113">Ez a dátum az ütemezési folyamatban használható.</span><span class="sxs-lookup"><span data-stu-id="1bd52-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="1bd52-114">Például a szállítási dátumtól visszafelé ütemezheti a rendelést.</span><span class="sxs-lookup"><span data-stu-id="1bd52-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="1bd52-115">Állítsa a mennyiséget 20 értékre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="1bd52-116">Megjegyzés: Az Anyagjegyzékszám mező automatikusan megjeleníti az aktív Anyagjegyzék számát az aktuális cikk esetében, de a termelési rendeléshez megváltoztathatja az Anyagjegyzéket az elfogadott Anyagjegyzék-verziók listájából egy aktív Anyagjegyzéket kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="1bd52-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="1bd52-117">Megjegyzés: Az Útvonalszám mező automatikusan megjeleníti az aktív Útvonal számát az aktuális cikk esetében, de a termelési rendeléshez megváltoztathatja az Útvonalat az elfogadott Útvonal-verziók listájából egy aktív Útvonalat kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="1bd52-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="1bd52-118">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="1bd52-119">Validálja a termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="1bd52-119">Validate the production order</span></span>
1. <span data-ttu-id="1bd52-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1bd52-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1bd52-121">A termelési rendelés számához, amelyet az imént létrehozott, kattintson a hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1bd52-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="1bd52-122">Ezzel megnyitja a Részletek lapot a rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="1bd52-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="1bd52-123">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-123">Click Edit.</span></span>
3. <span data-ttu-id="1bd52-124">A Szállítás mezőben adja meg a szállítási dátumot.</span><span class="sxs-lookup"><span data-stu-id="1bd52-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="1bd52-125">Például megváltoztathatja a termelési rendelés szállítási dátumát.</span><span class="sxs-lookup"><span data-stu-id="1bd52-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="1bd52-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1bd52-126">Click Save.</span></span>
5. <span data-ttu-id="1bd52-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1bd52-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="1bd52-128">AJ frissítése.</span><span class="sxs-lookup"><span data-stu-id="1bd52-128">Update the BOM</span></span>
1. <span data-ttu-id="1bd52-129">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="1bd52-130">Kattintson az Anyagjegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-130">Click BOM.</span></span>
    * <span data-ttu-id="1bd52-131">Nyissa meg az Anyagjegyzék lapot az Anyagjegyzék adatainak validálásához, amelyeket az alapértelmezett adatokból másolt át, mikor létrehozta a termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="1bd52-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="1bd52-132">Ebben az eljárásban szükség lesz az Anyagjegyzék-mennyiség frissítésére.</span><span class="sxs-lookup"><span data-stu-id="1bd52-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="1bd52-133">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-133">Click Edit.</span></span>
4. <span data-ttu-id="1bd52-134">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="1bd52-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1bd52-135">Az AJ-sor mennyiségének módosítása hatással van a termelési rendelés nyersanyag-felhasználásának költségbecslésére.</span><span class="sxs-lookup"><span data-stu-id="1bd52-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="1bd52-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1bd52-136">Click Save.</span></span>
6. <span data-ttu-id="1bd52-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1bd52-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="1bd52-138">Termelési útvonal módosítása.</span><span class="sxs-lookup"><span data-stu-id="1bd52-138">Update the production route</span></span>
1. <span data-ttu-id="1bd52-139">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="1bd52-140">Kattintson az Útvonalra.</span><span class="sxs-lookup"><span data-stu-id="1bd52-140">Click Route.</span></span>
    * <span data-ttu-id="1bd52-141">Nyissa meg az Útvonal lapot a termelési útvonal adatainak validálásához, amelyeket az alapértelmezett adatokból másolt át, mikor létrehozta a termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="1bd52-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="1bd52-142">Ebben az eljárásban frissítenie kell a mennyiséget a termelési útvonal egyik műveletéhez.</span><span class="sxs-lookup"><span data-stu-id="1bd52-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="1bd52-143">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="1bd52-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1bd52-144">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1bd52-144">Click Edit.</span></span>
5. <span data-ttu-id="1bd52-145">A Folyamat menny. mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="1bd52-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="1bd52-146">A feldolgozási idő módosítása hatással van a becsült útvonal-felhasználásra és a termelési rendelés költségére.</span><span class="sxs-lookup"><span data-stu-id="1bd52-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="1bd52-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1bd52-147">Click Save.</span></span>
7. <span data-ttu-id="1bd52-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1bd52-148">Close the page.</span></span>


---
title: Készletszintek inicializálása a raktárban
description: Ez az eljárás bemutatja, hogyan frissítheti kézileg az aktuális készletet a Készletmozgási napló segítségével.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f922620c7aeeafd8560316239875c1ec5486191
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145686"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a><span data-ttu-id="e2c2e-103">Készletszintek inicializálása a raktárban</span><span class="sxs-lookup"><span data-stu-id="e2c2e-103">Initialize stock levels in the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2c2e-104">Ez az eljárás bemutatja, hogyan frissítheti kézileg az aktuális készletet a Készletmozgási napló segítségével.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-104">This procedure shows you how to get the on-hand inventory updated manually using an Inventory movement journal.</span></span> <span data-ttu-id="e2c2e-105">(Az aktuális készlet frissítése az adatentitásokban található tranzakciók importálásával is történhet.) Ezt az útmutatót az USMF bemutatócégen is lefuttathatja, ahol minden előfeltétel elérhető, például a naplónevek, cikkbeállítások, feladási profilok és számlák.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-105">(It's also possible to update on-hand inventory by importing transactions in data entities.) You can run this guide in demo data company USMF where all the prerequisites like journal name, item setup, posting profiles, and accounts are available.</span></span> <span data-ttu-id="e2c2e-106">Az útmutató a használt cikkre és dimenziókra vonatkozóan adott értékeket javasol.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-106">The guide suggests specific values for the item and dimensions that are used.</span></span> <span data-ttu-id="e2c2e-107">Ha egy másik elemet választ, lehetséges, hogy más dimenziók értékeit kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-107">If you choose a different item, you may need to enter values for different dimensions.</span></span>

1. <span data-ttu-id="e2c2e-108">Ugrás a Készletgazdálkodás > Naplóbejegyzések > Cikkek > Mozgás menüpontba.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-108">Go to Inventory management > Journal entries > Items > Movement.</span></span>
2. <span data-ttu-id="e2c2e-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-109">Click New.</span></span>
3. <span data-ttu-id="e2c2e-110">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e2c2e-111">Válassza ki az IMov. lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-111">Select IMov.</span></span>
    * <span data-ttu-id="e2c2e-112">Tanácsos különböző naplósablonok nevét használni különböző üzleti célokra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-112">It's a good practice to use different journal name templates for the different business purposes.</span></span>  
5. <span data-ttu-id="e2c2e-113">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e2c2e-114">Az Ellenszámla mezőben adja meg a „140200” értékeket.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-114">In the Offset account field, specify the values '140200'.</span></span>
    * <span data-ttu-id="e2c2e-115">Ez az ellenszámla lesz a naplósorok alapértelmezett számlája.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-115">This is the offset account that will be the default account on the journal lines.</span></span> <span data-ttu-id="e2c2e-116">Lehetséges felülírni az alapértelmezettet, ha más ellenszámlát szeretne hozzárendelni egy sorhoz.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-116">It's possible to override the default to assign different offset accounts per line.</span></span>  
7. <span data-ttu-id="e2c2e-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-117">Click OK.</span></span>
8. <span data-ttu-id="e2c2e-118">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-118">Click New.</span></span>
9. <span data-ttu-id="e2c2e-119">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="e2c2e-120">Válassza az A0001 elemet.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-120">Select item A0001.</span></span>
11. <span data-ttu-id="e2c2e-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="e2c2e-122">Kattintson a Készlet dimenziók lapra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-122">Click the Inventory dimensions tab.</span></span>
13. <span data-ttu-id="e2c2e-123">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-123">In the Site field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="e2c2e-124">Válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-124">Select site 1.</span></span>
15. <span data-ttu-id="e2c2e-125">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-125">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="e2c2e-126">Válasszak ki a 13. raktárt.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-126">Select warehouse 13.</span></span>
17. <span data-ttu-id="e2c2e-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-127">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="e2c2e-128">A Hely mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-128">In the Location field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="e2c2e-129">Válassza ki a 13. helyet.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-129">Select location 13.</span></span>
20. <span data-ttu-id="e2c2e-130">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="e2c2e-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-131">Click Save.</span></span>
22. <span data-ttu-id="e2c2e-132">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-132">Click Post.</span></span>
23. <span data-ttu-id="e2c2e-133">Jelölje be a Minden feladási hiba átvitele egy új naplóba jelölőnégyzetet, vagy törölje a jelölést.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-133">Check or uncheck the Transfer all posting errors to a new journal check box.</span></span>
    * <span data-ttu-id="e2c2e-134">Ha engedélyezi ezt a beállítást, a rendszer bemásolja egy új naplóba az olyan sorokat, amelyek nem kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-134">If you enable this option, any lines that fail to post will be copied to a new journal.</span></span> <span data-ttu-id="e2c2e-135">A naplóban található információk segítségével korrigálhatja a problémákat, majd újra feladathatja a sorokat.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-135">You can use the information in the log to correct the issues and then re-post the lines.</span></span>  
24. <span data-ttu-id="e2c2e-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-136">Click OK.</span></span>
25. <span data-ttu-id="e2c2e-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-137">Close the page.</span></span>
26. <span data-ttu-id="e2c2e-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e2c2e-138">Close the page.</span></span>


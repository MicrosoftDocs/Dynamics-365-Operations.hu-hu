--- 
title: "A kézi csomagolás beállítása (csak 2016. február és május)"
description: "A csomagolási folyamat lehetővé teszi az érvényesítést és a termékek tárolókba történő csomagolását."
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 31b689b6c31563f24892525eed5911af3a35bd51
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-manual-packing-february--may-2016-only"></a><span data-ttu-id="1d284-103">A kézi csomagolás beállítása (csak 2016. február és május)</span><span class="sxs-lookup"><span data-stu-id="1d284-103">Set up manual packing (February & May 2016 only)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1d284-104">A csomagolási folyamat lehetővé teszi az érvényesítést és a termékek tárolókba történő csomagolását.</span><span class="sxs-lookup"><span data-stu-id="1d284-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="1d284-105">Ebben a folyamatban a raktárosok a tárolási helyekből helyezik át a termékeket és azon csomagolási állomásra helyezik át ezeket, ahol a cikk mennyiségét és minőségét ellenőrzik, illetve hozzárendelik ezeket a megfelelő tárolókhoz.</span><span class="sxs-lookup"><span data-stu-id="1d284-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="1d284-106">Amikor a tároló teljesen tele van, bezárhatja, illetve áthelyezheti a kiszállítási területekre, és a termékek készen állnak a szállításra.</span><span class="sxs-lookup"><span data-stu-id="1d284-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="1d284-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="1d284-107">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="1d284-108">Helyprofilok beállítása</span><span class="sxs-lookup"><span data-stu-id="1d284-108">Set up location profiles</span></span>
1. <span data-ttu-id="1d284-109">Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési > Helyprofilok pontra.</span><span class="sxs-lookup"><span data-stu-id="1d284-109">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="1d284-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d284-110">Click New.</span></span>
    * <span data-ttu-id="1d284-111">A helyprofilt a csomagoló helyekre vonatkozóan használja a rendszer, és a helyre vonatkozó információkat és szabályokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1d284-111">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="1d284-112">Írjon egy értéket a Helyprofil azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1d284-112">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="1d284-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1d284-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="1d284-114">A Helyformátum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-114">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="1d284-115">A Hely típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-115">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="1d284-116">Válassza ki az Igen lehetőséget a Vegyes cikkek engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-116">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="1d284-117">Válassza ki az Igen lehetőséget a Vegyes készletállapotok engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-117">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="1d284-118">Válassza ki az Igen lehetőséget a Kötegelési időszak szabályainak felülbírálása mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-118">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="1d284-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1d284-119">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="1d284-120">Raktárkezelési paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="1d284-120">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="1d284-121">Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési paraméterekre.</span><span class="sxs-lookup"><span data-stu-id="1d284-121">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="1d284-122">Kattintson Csomagolás fülre.</span><span class="sxs-lookup"><span data-stu-id="1d284-122">Click the Packing tab.</span></span>
3. <span data-ttu-id="1d284-123">Adjon meg vagy válasszon ki egy értéket a Csomagolási hely profilazonosítója mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-123">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="1d284-124">Válassza ki a csomagolásra használni kívánt helyprofilt.</span><span class="sxs-lookup"><span data-stu-id="1d284-124">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="1d284-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1d284-125">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="1d284-126">Tárolótípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="1d284-126">Set up container types</span></span>
1. <span data-ttu-id="1d284-127">Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolótípusok pontra.</span><span class="sxs-lookup"><span data-stu-id="1d284-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="1d284-128">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d284-128">Click New.</span></span>
    * <span data-ttu-id="1d284-129">Meghatározhatja a használni kívánt tároló típusait.</span><span class="sxs-lookup"><span data-stu-id="1d284-129">You can define the types of containers to use.</span></span> <span data-ttu-id="1d284-130">Megadhatja a tároló fizikai dimenzióit, többek között a csomagolási súlyát, az össztömegét, a maximális térfogatát, a hosszúságát, a szélességét és a súlyát.</span><span class="sxs-lookup"><span data-stu-id="1d284-130">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="1d284-131">Az attribútumok olyan testreszabott mezők, amelyek lehetővé teszik az extra dimenziók hozzáadását a tárolótípuson.</span><span class="sxs-lookup"><span data-stu-id="1d284-131">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="1d284-132">Írjon be egy értéket a Tároló típuskódja mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1d284-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="1d284-133">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1d284-134">Adjon meg egy számot a Tárasúly mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-134">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="1d284-135">Adjon meg egy számot a Maximális súly mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-135">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="1d284-136">A Térfogat mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="1d284-136">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="1d284-137">Adjon meg egy számot a Hosszúság mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-137">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="1d284-138">Adjon meg egy számot a Szélesség mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-138">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="1d284-139">Adjon meg egy számot a Magasság mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-139">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="1d284-140">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1d284-140">Click Save.</span></span>
12. <span data-ttu-id="1d284-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1d284-141">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="1d284-142">Csomagolási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="1d284-142">Set up packing profiles</span></span>
1. <span data-ttu-id="1d284-143">Ugorjon a Raktárkezelés > Beállítás > Csomagolás > Csomagolási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="1d284-143">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="1d284-144">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d284-144">Click New.</span></span>
3. <span data-ttu-id="1d284-145">Írjon egy értéket a Csomagolási profil azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1d284-145">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="1d284-146">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-146">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1d284-147">Adjon meg vagy válasszon ki egy értéket a Tárolólezárási profil azonosítója mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-147">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="1d284-148">A tárolólezárási profil azonosítója nem kötelező, és a csomagolási profilra vonatkozó alapértelmezett tárolólezárási profil.</span><span class="sxs-lookup"><span data-stu-id="1d284-148">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="1d284-149">Válasszon ki egy lehetőséget a Tárolóazonosító mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-149">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="1d284-150">Ez a beállítás határozza meg, hogy a rendszer létrehozza-e automatikusan a tárolóazonosítót a tároló létrehozásakor vagy manuálisan hozzák létre a tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="1d284-150">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="1d284-151">A tárolótípus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-151">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="1d284-152">Alapértelmezés szerint használják a tárolótípust, amikor létrejön egy új tároló.</span><span class="sxs-lookup"><span data-stu-id="1d284-152">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="1d284-153">Válassza ki a Tároló automatikus létrehozása a tároló lezárásakor jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1d284-153">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="1d284-154">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1d284-154">Click Save.</span></span>
10. <span data-ttu-id="1d284-155">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1d284-155">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="1d284-156">Tárolólezárási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="1d284-156">Set up container closing profiles</span></span>
1. <span data-ttu-id="1d284-157">Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolólezárási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="1d284-157">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="1d284-158">A tárolólezárási profilok határozza meg, hogy mi történjen, ha a tároló le van zárva.</span><span class="sxs-lookup"><span data-stu-id="1d284-158">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="1d284-159">Több tárolólezárási profilt állíthat be.</span><span class="sxs-lookup"><span data-stu-id="1d284-159">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="1d284-160">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d284-160">Click New.</span></span>
3. <span data-ttu-id="1d284-161">Írjon be egy értéket a Tárolólezárási profil azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1d284-161">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="1d284-162">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1d284-163">Válasszon ki egy lehetőséget a Jegyzékfájl ekkor: mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-163">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="1d284-164">Határozza meg, hogy a jegyzékbe foglalás a tárolók lezárásakor vagy a szállítmány megerősítésekor történjen.</span><span class="sxs-lookup"><span data-stu-id="1d284-164">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="1d284-165">Vegye figyelembe, hogy a jegyzékbe foglalás Szállításkezelést igényel.</span><span class="sxs-lookup"><span data-stu-id="1d284-165">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="1d284-166">A Jegyzékbe foglalást a Szállításkezelő kalkulátorokban kell végrehajtani a működéshez.</span><span class="sxs-lookup"><span data-stu-id="1d284-166">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="1d284-167">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-167">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="1d284-168">Adjon meg vagy válasszon ki egy értéket a Végső szállítmány alapértelmezett helye mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d284-168">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="1d284-169">Ez a hely, ahova a termékeket áthelyezik a tárolók bezárása után.</span><span class="sxs-lookup"><span data-stu-id="1d284-169">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="1d284-170">Ezen helynek rendelkeznie kell a Raktárház paramétereiben meghatározott helyprofillal.</span><span class="sxs-lookup"><span data-stu-id="1d284-170">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="1d284-171">A Súlyegység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d284-171">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="1d284-172">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1d284-172">Click Save.</span></span>



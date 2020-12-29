---
title: A kézi csomagolás beállítása (2016. február és 2016. május)
description: A csomagolási folyamat lehetővé teszi az érvényesítést és a termékek tárolókba történő csomagolását.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67e1e99b479752a027c60a878c57bd35d4219981
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429902"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="6bbe0-103">A kézi csomagolás beállítása (2016. február és 2016. május)</span><span class="sxs-lookup"><span data-stu-id="6bbe0-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6bbe0-104">A csomagolási folyamat lehetővé teszi az érvényesítést és a termékek tárolókba történő csomagolását.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="6bbe0-105">Ebben a folyamatban a raktárosok a tárolási helyekből helyezik át a termékeket és azon csomagolási állomásra helyezik át ezeket, ahol a cikk mennyiségét és minőségét ellenőrzik, illetve hozzárendelik ezeket a megfelelő tárolókhoz.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="6bbe0-106">Amikor a tároló teljesen tele van, bezárhatja, illetve áthelyezheti a kiszállítási területekre, és a termékek készen állnak a szállításra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="6bbe0-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="6bbe0-108">Ez az eljárás csak a Dynamics 365 for Operations 2016. februári és 2016. májusi verzióira vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="6bbe0-109">Helyprofilok beállítása</span><span class="sxs-lookup"><span data-stu-id="6bbe0-109">Set up location profiles</span></span>
1. <span data-ttu-id="6bbe0-110">Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési > Helyprofilok pontra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="6bbe0-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-111">Click New.</span></span>
    * <span data-ttu-id="6bbe0-112">A helyprofilt a csomagoló helyekre vonatkozóan használja a rendszer, és a helyre vonatkozó információkat és szabályokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="6bbe0-113">Írjon egy értéket a Helyprofil azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="6bbe0-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6bbe0-115">A Helyformátum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="6bbe0-116">A Hely típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="6bbe0-117">Válassza ki az Igen lehetőséget a Vegyes cikkek engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="6bbe0-118">Válassza ki az Igen lehetőséget a Vegyes készletállapotok engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="6bbe0-119">Válassza ki az Igen lehetőséget a Kötegelési időszak szabályainak felülbírálása mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="6bbe0-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="6bbe0-121">Raktárkezelési paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="6bbe0-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="6bbe0-122">Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési paraméterekre.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="6bbe0-123">Kattintson Csomagolás fülre.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="6bbe0-124">Adjon meg vagy válasszon ki egy értéket a Csomagolási hely profilazonosítója mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="6bbe0-125">Válassza ki a csomagolásra használni kívánt helyprofilt.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="6bbe0-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="6bbe0-127">Tárolótípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="6bbe0-127">Set up container types</span></span>
1. <span data-ttu-id="6bbe0-128">Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolótípusok pontra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="6bbe0-129">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-129">Click New.</span></span>
    * <span data-ttu-id="6bbe0-130">Meghatározhatja a használni kívánt tároló típusait.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-130">You can define the types of containers to use.</span></span> <span data-ttu-id="6bbe0-131">Megadhatja a tároló fizikai dimenzióit, többek között a csomagolási súlyát, az össztömegét, a maximális térfogatát, a hosszúságát, a szélességét és a súlyát.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="6bbe0-132">Az attribútumok olyan testreszabott mezők, amelyek lehetővé teszik az extra dimenziók hozzáadását a tárolótípuson.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="6bbe0-133">Írjon be egy értéket a Tároló típuskódja mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="6bbe0-134">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6bbe0-135">Adjon meg egy számot a Tárasúly mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="6bbe0-136">Adjon meg egy számot a Maximális súly mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="6bbe0-137">A Térfogat mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="6bbe0-138">Adjon meg egy számot a Hosszúság mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="6bbe0-139">Adjon meg egy számot a Szélesség mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="6bbe0-140">Adjon meg egy számot a Magasság mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="6bbe0-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-141">Click Save.</span></span>
12. <span data-ttu-id="6bbe0-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="6bbe0-143">Csomagolási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="6bbe0-143">Set up packing profiles</span></span>
1. <span data-ttu-id="6bbe0-144">Ugorjon a Raktárkezelés > Beállítás > Csomagolás > Csomagolási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="6bbe0-145">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-145">Click New.</span></span>
3. <span data-ttu-id="6bbe0-146">Írjon egy értéket a Csomagolási profil azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="6bbe0-147">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6bbe0-148">Adjon meg vagy válasszon ki egy értéket a Tárolólezárási profil azonosítója mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="6bbe0-149">A tárolólezárási profil azonosítója nem kötelező, és a csomagolási profilra vonatkozó alapértelmezett tárolólezárási profil.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="6bbe0-150">Válasszon ki egy lehetőséget a Tárolóazonosító mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="6bbe0-151">Ez a beállítás határozza meg, hogy a rendszer létrehozza-e automatikusan a tárolóazonosítót a tároló létrehozásakor vagy manuálisan hozzák létre a tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="6bbe0-152">A tárolótípus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="6bbe0-153">Alapértelmezés szerint használják a tárolótípust, amikor létrejön egy új tároló.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="6bbe0-154">Válassza ki a Tároló automatikus létrehozása a tároló lezárásakor jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="6bbe0-155">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-155">Click Save.</span></span>
10. <span data-ttu-id="6bbe0-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="6bbe0-157">Tárolólezárási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="6bbe0-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="6bbe0-158">Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolólezárási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="6bbe0-159">A tárolólezárási profilok határozza meg, hogy mi történjen, ha a tároló le van zárva.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="6bbe0-160">Több tárolólezárási profilt állíthat be.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="6bbe0-161">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-161">Click New.</span></span>
3. <span data-ttu-id="6bbe0-162">Írjon be egy értéket a Tárolólezárási profil azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="6bbe0-163">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6bbe0-164">Válasszon ki egy lehetőséget a Jegyzékfájl ekkor: mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="6bbe0-165">Határozza meg, hogy a jegyzékbe foglalás a tárolók lezárásakor vagy a szállítmány megerősítésekor történjen.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="6bbe0-166">Vegye figyelembe, hogy a jegyzékbe foglalás Szállításkezelést igényel.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="6bbe0-167">A Jegyzékbe foglalást a Szállításkezelő kalkulátorokban kell végrehajtani a működéshez.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="6bbe0-168">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="6bbe0-169">Adjon meg vagy válasszon ki egy értéket a Végső szállítmány alapértelmezett helye mezőben.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="6bbe0-170">Ez a hely, ahova a termékeket áthelyezik a tárolók bezárása után.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="6bbe0-171">Ezen helynek rendelkeznie kell a Raktárház paramétereiben meghatározott helyprofillal.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="6bbe0-172">A Súlyegység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="6bbe0-173">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6bbe0-173">Click Save.</span></span>


---
title: Szállítási konténerek
description: Ez a témakör azt ismerteti, hogyan lehet szállítókonténereket beállítani a Partraszállítási költség modulhoz.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ca712aa7f07792861d5ba36afd8d7b63cc9ce8fb
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500958"
---
# <a name="shipping-container-setup"></a><span data-ttu-id="5a3da-103">Szállítókonténerek beállítása</span><span class="sxs-lookup"><span data-stu-id="5a3da-103">Shipping container setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5a3da-104">Ez a témakör azt ismerteti, hogyan lehet szállítókonténereket beállítani a **Partraszállítási költség** modulhoz.</span><span class="sxs-lookup"><span data-stu-id="5a3da-104">This topic describes how to set up shipping containers for the **Landed cost** module.</span></span>

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a><span data-ttu-id="5a3da-105">Szállítókonténer-típusok beállítása</span><span class="sxs-lookup"><span data-stu-id="5a3da-105">Set up shipping container types</span></span>

<span data-ttu-id="5a3da-106">A Szállítókonténer-típusok lehetőség beállítása határozza meg a szállítás és hajóút során használható szállítókonténerek típusait.</span><span class="sxs-lookup"><span data-stu-id="5a3da-106">Shipping container types define the types of shipping containers that are available for use during shipping and voyages.</span></span>

<span data-ttu-id="5a3da-107">A szállítókonténer-típusokkal a **Partraszállítási költség \> Konténerek beállítása \> Szállítókonténer-típusok** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="5a3da-107">To work with the shipping container types, go to **Landed cost \> Containers setup \> Shipping container types**.</span></span> <span data-ttu-id="5a3da-108">Itt megtekintheti, hozzáadhatja és eltávolíthatja a konténertípusok rekordjait.</span><span class="sxs-lookup"><span data-stu-id="5a3da-108">There, you can view, add, and remove records for your container types.</span></span> <span data-ttu-id="5a3da-109">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="5a3da-109">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="5a3da-110">Mező</span><span class="sxs-lookup"><span data-stu-id="5a3da-110">Field</span></span> | <span data-ttu-id="5a3da-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a3da-111">Description</span></span> |
|---|---|
| <span data-ttu-id="5a3da-112">Szállítási konténer típusa</span><span class="sxs-lookup"><span data-stu-id="5a3da-112">Shipping container type</span></span> | <span data-ttu-id="5a3da-113">Adja meg a szállítókonténer-típus egyedi azonosító nevét/számát.</span><span class="sxs-lookup"><span data-stu-id="5a3da-113">Enter a unique identification name/number for the shipping container type.</span></span> |
| <span data-ttu-id="5a3da-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a3da-114">Description</span></span> | <span data-ttu-id="5a3da-115">Adja meg a szállítókonténer-típus leírását.</span><span class="sxs-lookup"><span data-stu-id="5a3da-115">Enter a description of the shipping container type.</span></span> |
| <span data-ttu-id="5a3da-116">Térfogat</span><span class="sxs-lookup"><span data-stu-id="5a3da-116">Volume</span></span> | <span data-ttu-id="5a3da-117">Adja meg az ilyen típusú szállítókonténer esetében engedélyezett maximális térfogatot.</span><span class="sxs-lookup"><span data-stu-id="5a3da-117">Enter the maximum volume that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="5a3da-118">Betűvastagság</span><span class="sxs-lookup"><span data-stu-id="5a3da-118">Weight</span></span> | <span data-ttu-id="5a3da-119">Adja meg az ilyen típusú szállítókonténer esetében engedélyezett maximális tömeget.</span><span class="sxs-lookup"><span data-stu-id="5a3da-119">Enter the maximum weight that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="5a3da-120">Visszaküldhető</span><span class="sxs-lookup"><span data-stu-id="5a3da-120">Returnable</span></span> | <span data-ttu-id="5a3da-121">Adja meg, hogy az ilyen típusú szállítókonténerek visszaküldhetők-e a szállítónak a hajóút után.</span><span class="sxs-lookup"><span data-stu-id="5a3da-121">Specify whether shipping containers of this type can be returned to the vendor after they are used during a voyage.</span></span> <span data-ttu-id="5a3da-122">Ha ez a beállítás *Igen*, az ilyen típusú szállítókonténerek származási kikötőbe való visszaszállítására további költségek vonatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="5a3da-122">If this option is set to *Yes*, additional costs might apply for the return of shipping containers of this type to the port of origin.</span></span> |

## <a name="set-up-shipping-containers"></a><span data-ttu-id="5a3da-123">A szállítókonténerek beállítása</span><span class="sxs-lookup"><span data-stu-id="5a3da-123">Set up shipping containers</span></span>

<span data-ttu-id="5a3da-124">A szállítókonténer-rekordok segítségével azonosíthatja a hajúutak során használt konténereket.</span><span class="sxs-lookup"><span data-stu-id="5a3da-124">You use shipping container records to identify each container that you use during voyages.</span></span> <span data-ttu-id="5a3da-125">Hajóút létrehozásakor az itt megadott összes szállítókonténer-rekord listájában kiválaszthat egy konkrét konténert.</span><span class="sxs-lookup"><span data-stu-id="5a3da-125">When you create a voyage, you can select a specific container for it in the list of all the shipping container records that you've defined here.</span></span> <span data-ttu-id="5a3da-126">Ez a funkció különösen akkor hasznos, ha a vállalatnak saját szállítókonténerei vannak.</span><span class="sxs-lookup"><span data-stu-id="5a3da-126">This feature is especially useful if your company owns its own shipping containers.</span></span>

<span data-ttu-id="5a3da-127">Nem kell megadnia a szállítókonténer számát az egyszer használatos szállítókonténerek esetében.</span><span class="sxs-lookup"><span data-stu-id="5a3da-127">You don't have to enter shipping container numbers for shipping containers that will be used only one time.</span></span> <span data-ttu-id="5a3da-128">Hajóút létrehozásakor ehelyett hozzáadhatja a szállítókonténer számát.</span><span class="sxs-lookup"><span data-stu-id="5a3da-128">Instead, you can add the shipping container number when you create a voyage.</span></span>

<span data-ttu-id="5a3da-129">A szállítókonténer rekordjai csak a Partraszállítási költség pontban használatosak.</span><span class="sxs-lookup"><span data-stu-id="5a3da-129">Shipping container records are used only in Landed cost.</span></span> <span data-ttu-id="5a3da-130">Ezek nem érhetők el a szabványos **Szállításkezelés** modulban (TMS).</span><span class="sxs-lookup"><span data-stu-id="5a3da-130">They aren't available in the standard **Transportation management** module (TMS).</span></span>

<span data-ttu-id="5a3da-131">A szállítókonténerekkel a **Partraszállítási költség \> Konténerek beállítása \> Szállítókonténerek** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="5a3da-131">To work with shipping containers, go to **Landed cost \> Containers setup \> Shipping containers**.</span></span> <span data-ttu-id="5a3da-132">Itt megtekintheti, hozzáadhatja és eltávolíthatja a szállítókonténerek rekordjait.</span><span class="sxs-lookup"><span data-stu-id="5a3da-132">There, you can view, add, and remove records your shipping containers.</span></span> <span data-ttu-id="5a3da-133">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="5a3da-133">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="5a3da-134">Mező</span><span class="sxs-lookup"><span data-stu-id="5a3da-134">Field</span></span> | <span data-ttu-id="5a3da-135">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a3da-135">Description</span></span> |
|---|---|
| <span data-ttu-id="5a3da-136">Szállítási konténer</span><span class="sxs-lookup"><span data-stu-id="5a3da-136">Shipping container</span></span> | <span data-ttu-id="5a3da-137">Adja meg a szállítókonténer egyedi azonosító nevét/számát.</span><span class="sxs-lookup"><span data-stu-id="5a3da-137">Enter a unique identification name/number for the shipping container.</span></span> |
| <span data-ttu-id="5a3da-138">Szállítási konténer típusa</span><span class="sxs-lookup"><span data-stu-id="5a3da-138">Shipping container type</span></span> | <span data-ttu-id="5a3da-139">Válassza ki a szállítókonténer típusát.</span><span class="sxs-lookup"><span data-stu-id="5a3da-139">Select the type of shipping container.</span></span> <span data-ttu-id="5a3da-140">További tudnivalókért lásd a [Szállítókonténer-típusok beállítása](#shipping-container-types) című részt a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="5a3da-140">For more information, see the [Set up shipping container types](#shipping-container-types) section earlier in this topic.</span></span> |

> [!NOTE]
> - <span data-ttu-id="5a3da-141">A szállítókonténer beállítása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="5a3da-141">The shipping container setup is optional.</span></span> <span data-ttu-id="5a3da-142">Általában csak akkor használja, ha a vállalat saját szállítókonténereket használ, vagy gyakran használja fel újra ugyanazokat a szállítókonténereket.</span><span class="sxs-lookup"><span data-stu-id="5a3da-142">Typically, you will use it only if your company owns its own shipping containers or often reuses the same shipping containers.</span></span>
> - <span data-ttu-id="5a3da-143">A szállítókonténerek számához a rendszer nem számol ellenőrző számjegyeket.</span><span class="sxs-lookup"><span data-stu-id="5a3da-143">No check digits are calculated for shipping container numbers.</span></span>

## <a name="set-up-unit-types"></a><a name="unit-types"></a><span data-ttu-id="5a3da-144">Egységtípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="5a3da-144">Set up unit types</span></span>

<span data-ttu-id="5a3da-145">Az egységtípusok további csoportosításokat és azonosítási módszereket hoznak létre a szállítókonténerekhez.</span><span class="sxs-lookup"><span data-stu-id="5a3da-145">Unit types establish additional groupings and identification methods for shipping containers.</span></span> <span data-ttu-id="5a3da-146">Az egységtípus rendszerint az áruk csomagolásának típusát határozza meg, ilyenek például a raklapok vagy hordók.</span><span class="sxs-lookup"><span data-stu-id="5a3da-146">The unit type is typically used to identify the type of container that goods are packaged in, such as pallets or drums.</span></span> <span data-ttu-id="5a3da-147">Az egységtípust akkor választhatja ki, amikor az **Összes szállítókonténer** oldalon beállít egy konténert.</span><span class="sxs-lookup"><span data-stu-id="5a3da-147">You can select a unit type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="5a3da-148">Az egységtípusok csak a Partraszállítási költség lehetőségben használatosak.</span><span class="sxs-lookup"><span data-stu-id="5a3da-148">Unit types are used only in Landed cost.</span></span> <span data-ttu-id="5a3da-149">Nem érhetők el a TMS-ben.</span><span class="sxs-lookup"><span data-stu-id="5a3da-149">They aren't available in TMS.</span></span>

<span data-ttu-id="5a3da-150">Az egységtípusokkal a **Partraszállítási költség \> Konténerek beállítása \> Egységtípusok** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="5a3da-150">To work with unit types, go to **Landed cost \> Containers setup \> Unit types**.</span></span> <span data-ttu-id="5a3da-151">Itt megtekintheti, hozzáadhatja és eltávolíthatja az egységtípusok rekordjait.</span><span class="sxs-lookup"><span data-stu-id="5a3da-151">There, you can view, add, and remove records for your unit types.</span></span> <span data-ttu-id="5a3da-152">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="5a3da-152">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="5a3da-153">Mező</span><span class="sxs-lookup"><span data-stu-id="5a3da-153">Field</span></span> | <span data-ttu-id="5a3da-154">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a3da-154">Description</span></span> |
|---|---|
| <span data-ttu-id="5a3da-155">Egységtípus</span><span class="sxs-lookup"><span data-stu-id="5a3da-155">Unit type</span></span> | <span data-ttu-id="5a3da-156">Adja meg az egységtípus egyedi azonosító nevét/számát.</span><span class="sxs-lookup"><span data-stu-id="5a3da-156">Enter a unique identification name/number for the unit type.</span></span> |
| <span data-ttu-id="5a3da-157">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a3da-157">Description</span></span> | <span data-ttu-id="5a3da-158">Az egységtípus leírása.</span><span class="sxs-lookup"><span data-stu-id="5a3da-158">Enter a description of the unit type.</span></span> |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a><span data-ttu-id="5a3da-159">Hűtéstípusok beállítása</span><span class="sxs-lookup"><span data-stu-id="5a3da-159">Set up refrigeration types</span></span>

<span data-ttu-id="5a3da-160">A hűtéstípusok a szállítókonténerek (általában hűtött konténerek) csoportosításának és azonosításának további eszközként használhatók.</span><span class="sxs-lookup"><span data-stu-id="5a3da-160">Refrigeration types establish additional groupings and identification methods for shipping containers (usually refrigerated containers).</span></span> <span data-ttu-id="5a3da-161">A hűtéstípust akkor választhatja ki, amikor az **Összes szállítókonténer** oldalon beállít egy konténert.</span><span class="sxs-lookup"><span data-stu-id="5a3da-161">You can select a refrigeration type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="5a3da-162">A hűtéstípusokkal a **Partraszállítási költség \> Konténerek beállítása \> Hűtéstípusok** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="5a3da-162">To work with refrigeration types, go to **Landed cost \> Containers setup \> Refrigeration types**.</span></span> <span data-ttu-id="5a3da-163">Itt megtekintheti, hozzáadhatja és eltávolíthatja a hűtéstípusok rekordjait.</span><span class="sxs-lookup"><span data-stu-id="5a3da-163">There, you can view, add, and remove records for your refrigeration types.</span></span> <span data-ttu-id="5a3da-164">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="5a3da-164">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="5a3da-165">Mező</span><span class="sxs-lookup"><span data-stu-id="5a3da-165">Field</span></span> | <span data-ttu-id="5a3da-166">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a3da-166">Description</span></span> |
|---|---|
| <span data-ttu-id="5a3da-167">Hűtés típusa</span><span class="sxs-lookup"><span data-stu-id="5a3da-167">Refrigeration type</span></span> | <span data-ttu-id="5a3da-168">Adja meg a hűtéstípus egyedi azonosító nevét/számát.</span><span class="sxs-lookup"><span data-stu-id="5a3da-168">Enter a unique identification name/number for the refrigeration type.</span></span> |
| <span data-ttu-id="5a3da-169">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a3da-169">Description</span></span> | <span data-ttu-id="5a3da-170">Adja meg a hűtéstípus rövid leírását.</span><span class="sxs-lookup"><span data-stu-id="5a3da-170">Enter a description of the refrigeration type.</span></span> |

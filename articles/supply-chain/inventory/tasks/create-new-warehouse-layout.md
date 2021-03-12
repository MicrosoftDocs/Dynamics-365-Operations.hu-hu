---
title: Új raktárelrendezés létrehozása
description: Ez a témakör leírja, hogyan állíthat be információkat a raktárban lévő hellyekkel kapcsolatban.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f07fee1787cc2719bafbe2bb6d54849edda14018
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000034"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="c5e6b-103">Új raktárelrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c5e6b-103">Create a new warehouse layout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c5e6b-104">Ez a témakör leírja, hogyan állíthat be információkat a raktárban lévő hellyekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="c5e6b-105">Ez csak a Készletkezelő modulban az „alapvető raktározás” használatával létrehozott raktárakra érvényes, a Raktárkezelési rendszerben létrehozottakra nem.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="c5e6b-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="c5e6b-107">Az alapértelmezett hely kapacitás-beállítása</span><span class="sxs-lookup"><span data-stu-id="c5e6b-107">Set the default location capacity</span></span>
1. <span data-ttu-id="c5e6b-108">A Navigációs ablaktáblában válassza a **Modulok > Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="c5e6b-109">Válassza ki a **Helyek** lapot.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="c5e6b-110">Adjon meg egy számot a **Szokásos szélesség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="c5e6b-111">Adjon meg egy számot a **Szokásos mélység** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="c5e6b-112">Adjon meg egy számot a **Szokásos magasság** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="c5e6b-113">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-113">Select **Save**.</span></span>
7. <span data-ttu-id="c5e6b-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="c5e6b-115">Adja meg a hely nevének formátumát.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-115">Define the location name format</span></span>
1. <span data-ttu-id="c5e6b-116">A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Készlet részletezése > Raktárak** részre.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="c5e6b-117">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-117">Select **New**.</span></span>
3. <span data-ttu-id="c5e6b-118">Érték beírása a **Raktár** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="c5e6b-119">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="c5e6b-120">A **Hely** mező keresőjében válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="c5e6b-121">A **Helynevek** szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="c5e6b-122">A fejezetben leírt lehetőségek helynevek alapértelmezett formátumát adják meg.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="c5e6b-123">Ebben a példában megadjuk a folyosószámot, az állvány számát, illetve a polcszámot.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="c5e6b-124">A **Folyosó figyelembevétele** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="c5e6b-125">Az **Állvány figyelembevétele** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="c5e6b-126">A **Formátum** mezőbe írjon be egy értéket az állványhoz.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="c5e6b-127">A **Polc figyelembevétele** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="c5e6b-128">A **Formátum** mezőbe írjon be egy értéket a polchoz.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="c5e6b-129">Raktár-helyek meghatározása</span><span class="sxs-lookup"><span data-stu-id="c5e6b-129">Define warehouse locations</span></span>
1. <span data-ttu-id="c5e6b-130">A Műveleti ablaktáblán válassza a **Raktár** elemet.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="c5e6b-131">Válassza a **Hely varázsló** elemet.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="c5e6b-132">Válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-132">Select **Next**.</span></span>
4. <span data-ttu-id="c5e6b-133">A **Kiszállítási területek** beállítás kijelölésének törlése</span><span class="sxs-lookup"><span data-stu-id="c5e6b-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="c5e6b-134">Az **Ömlesztett tárolóhelyek** beállítás kijelölésének törlése</span><span class="sxs-lookup"><span data-stu-id="c5e6b-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="c5e6b-135">Válassza a **Tovább** lehetőséget, amíg ki nem választhatja a **Befejezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="c5e6b-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5e6b-136">Close the page.</span></span>
8. <span data-ttu-id="c5e6b-137">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="c5e6b-137">Refresh the page.</span></span>


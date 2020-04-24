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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09666e95cc90913f1bf8555b9ff2c48aa55369ed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214021"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="99fdf-103">Új raktárelrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="99fdf-103">Create a new warehouse layout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="99fdf-104">Ez a témakör leírja, hogyan állíthat be információkat a raktárban lévő hellyekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="99fdf-104">This topic describes how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="99fdf-105">Ez csak a Készletkezelő modulban az „alapvető raktározás” használatával létrehozott raktárakra érvényes, a Raktárkezelési rendszerben létrehozottakra nem.</span><span class="sxs-lookup"><span data-stu-id="99fdf-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="99fdf-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="99fdf-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="99fdf-107">Az alapértelmezett hely kapacitás-beállítása</span><span class="sxs-lookup"><span data-stu-id="99fdf-107">Set the default location capacity</span></span>
1. <span data-ttu-id="99fdf-108">A Navigációs ablaktáblában válassza a **Modulok > Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99fdf-108">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory and warehouse management parameters**.</span></span>
2. <span data-ttu-id="99fdf-109">Válassza ki a **Helyek** lapot.</span><span class="sxs-lookup"><span data-stu-id="99fdf-109">Select the **Locations** tab.</span></span>
3. <span data-ttu-id="99fdf-110">Adjon meg egy számot a **Szokásos szélesség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="99fdf-110">In the **Standard width** field, enter a number.</span></span>
4. <span data-ttu-id="99fdf-111">Adjon meg egy számot a **Szokásos mélység** mezőben.</span><span class="sxs-lookup"><span data-stu-id="99fdf-111">In the **Standard depth** field, enter a number.</span></span>
5. <span data-ttu-id="99fdf-112">Adjon meg egy számot a **Szokásos magasság** mezőben.</span><span class="sxs-lookup"><span data-stu-id="99fdf-112">In the **Standard height** field, enter a number.</span></span>
6. <span data-ttu-id="99fdf-113">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99fdf-113">Select **Save**.</span></span>
7. <span data-ttu-id="99fdf-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="99fdf-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="99fdf-115">Adja meg a hely nevének formátumát.</span><span class="sxs-lookup"><span data-stu-id="99fdf-115">Define the location name format</span></span>
1. <span data-ttu-id="99fdf-116">A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Készlet részletezése > Raktárak** részre.</span><span class="sxs-lookup"><span data-stu-id="99fdf-116">In the navigation pane, go to **Modules > Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>
2. <span data-ttu-id="99fdf-117">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99fdf-117">Select **New**.</span></span>
3. <span data-ttu-id="99fdf-118">Érték beírása a **Raktár** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="99fdf-118">In the **Warehouse** field, type a value.</span></span>
4. <span data-ttu-id="99fdf-119">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="99fdf-119">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="99fdf-120">A **Hely** mező keresőjében válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="99fdf-120">In the **Site** field, select the desired record in the lookup.</span></span>
6. <span data-ttu-id="99fdf-121">A **Helynevek** szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="99fdf-121">Toggle the expansion of the **Location names** section.</span></span> <span data-ttu-id="99fdf-122">A fejezetben leírt lehetőségek helynevek alapértelmezett formátumát adják meg.</span><span class="sxs-lookup"><span data-stu-id="99fdf-122">The options in this section define the default format for location names.</span></span> <span data-ttu-id="99fdf-123">Ebben a példában megadjuk a folyosószámot, az állvány számát, illetve a polcszámot.</span><span class="sxs-lookup"><span data-stu-id="99fdf-123">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
7. <span data-ttu-id="99fdf-124">A **Folyosó figyelembevétele** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="99fdf-124">Set the **Include aisle** option to **Yes**.</span></span>
8. <span data-ttu-id="99fdf-125">Az **Állvány figyelembevétele** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="99fdf-125">Set the **Include rack** option to **Yes**.</span></span> 
9. <span data-ttu-id="99fdf-126">A **Formátum** mezőbe írjon be egy értéket az állványhoz.</span><span class="sxs-lookup"><span data-stu-id="99fdf-126">In the **Format** field, for the rack, type a value.</span></span>
10. <span data-ttu-id="99fdf-127">A **Polc figyelembevétele** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="99fdf-127">Set the **Include shelf** option to **Yes**.</span></span>
11. <span data-ttu-id="99fdf-128">A **Formátum** mezőbe írjon be egy értéket a polchoz.</span><span class="sxs-lookup"><span data-stu-id="99fdf-128">In the **Format** field, for the shelf, type a value.</span></span>

## <a name="define-warehouse-locations"></a><span data-ttu-id="99fdf-129">Raktár-helyek meghatározása</span><span class="sxs-lookup"><span data-stu-id="99fdf-129">Define warehouse locations</span></span>
1. <span data-ttu-id="99fdf-130">A Műveleti ablaktáblán válassza a **Raktár** elemet.</span><span class="sxs-lookup"><span data-stu-id="99fdf-130">On the Action Pane, select **Warehouse**.</span></span>
2. <span data-ttu-id="99fdf-131">Válassza a **Hely varázsló** elemet.</span><span class="sxs-lookup"><span data-stu-id="99fdf-131">Select **Location Wizard**.</span></span>
3. <span data-ttu-id="99fdf-132">Válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99fdf-132">Select **Next**.</span></span>
4. <span data-ttu-id="99fdf-133">A **Kiszállítási területek** beállítás kijelölésének törlése</span><span class="sxs-lookup"><span data-stu-id="99fdf-133">De-select the **Outbound docks** option</span></span>
5. <span data-ttu-id="99fdf-134">Az **Ömlesztett tárolóhelyek** beállítás kijelölésének törlése</span><span class="sxs-lookup"><span data-stu-id="99fdf-134">De-select the **Bulk locations** option</span></span>
6. <span data-ttu-id="99fdf-135">Válassza a **Tovább** lehetőséget, amíg ki nem választhatja a **Befejezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="99fdf-135">Select **Next** until you come to the option to select **Finish**.</span></span>
7. <span data-ttu-id="99fdf-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="99fdf-136">Close the page.</span></span>
8. <span data-ttu-id="99fdf-137">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="99fdf-137">Refresh the page.</span></span>


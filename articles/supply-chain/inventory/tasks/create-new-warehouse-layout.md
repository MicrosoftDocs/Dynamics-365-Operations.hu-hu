---
title: Új raktárelrendezés létrehozása
description: Ez az eljárás bemutatja, hogyan adjon meg adatokat a raktár helyeivel kapcsolatban.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26314f9015feded41f105814b85069fff0c62964
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572765"
---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="bba5f-103">Új raktárelrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="bba5f-103">Create a new warehouse layout</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bba5f-104">Ez az eljárás bemutatja, hogyan adjon meg adatokat a raktár helyeivel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="bba5f-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="bba5f-105">Ez csak a Készletkezelő modulban az „alapvető raktározás” használatával létrehozott raktárakra érvényes, a Raktárkezelési rendszerben létrehozottakra nem.</span><span class="sxs-lookup"><span data-stu-id="bba5f-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="bba5f-106">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="bba5f-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="bba5f-107">Az alapértelmezett hely kapacitás-beállítása</span><span class="sxs-lookup"><span data-stu-id="bba5f-107">Set the default location capacity</span></span>
1. <span data-ttu-id="bba5f-108">Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bba5f-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="bba5f-109">Kattintson a Helyek fülre.</span><span class="sxs-lookup"><span data-stu-id="bba5f-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="bba5f-110">Adjon meg egy számot a Szokásos szélesség mezőben.</span><span class="sxs-lookup"><span data-stu-id="bba5f-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="bba5f-111">Adjon meg egy számot a Szokásos mélység mezőben.</span><span class="sxs-lookup"><span data-stu-id="bba5f-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="bba5f-112">Adjon meg egy számot a Szokásos magasság mezőben.</span><span class="sxs-lookup"><span data-stu-id="bba5f-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="bba5f-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-113">Click Save.</span></span>
7. <span data-ttu-id="bba5f-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bba5f-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="bba5f-115">Adja meg a hely nevének formátumát.</span><span class="sxs-lookup"><span data-stu-id="bba5f-115">Define the location name format</span></span>
1. <span data-ttu-id="bba5f-116">Ugrás a következő lehetőségre: Készletgazdálkodás > Beállítás > Készlet részletezése > Raktárak.</span><span class="sxs-lookup"><span data-stu-id="bba5f-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="bba5f-117">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bba5f-117">Click New.</span></span>
3. <span data-ttu-id="bba5f-118">Érték beírása a Raktár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bba5f-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="bba5f-119">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="bba5f-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="bba5f-120">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="bba5f-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="bba5f-121">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="bba5f-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="bba5f-122">A Helynevek szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="bba5f-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="bba5f-123">A fejezetben leírt lehetőségek helynevek alapértelmezett formátumát adják meg.</span><span class="sxs-lookup"><span data-stu-id="bba5f-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="bba5f-124">Ebben a példában megadjuk a folyosószámot, az állvány számát, illetve a polcszámot.</span><span class="sxs-lookup"><span data-stu-id="bba5f-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="bba5f-125">A folyosó figyelembevételével beállítása: Igen.</span><span class="sxs-lookup"><span data-stu-id="bba5f-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="bba5f-126">Az állvány figyelembevételével beállítása: Igen.</span><span class="sxs-lookup"><span data-stu-id="bba5f-126">Set the Include rack option to Yes.</span></span> 
10. <span data-ttu-id="bba5f-127">A Formátum mezőbe írjon be egy értéket az állványhoz.</span><span class="sxs-lookup"><span data-stu-id="bba5f-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="bba5f-128">Példa: -##</span><span class="sxs-lookup"><span data-stu-id="bba5f-128">For example: -##</span></span>  
11. <span data-ttu-id="bba5f-129">A polc figyelembevételével beállítása: Igen.</span><span class="sxs-lookup"><span data-stu-id="bba5f-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="bba5f-130">A Formátum mezőbe írjon be egy értéket a polchoz.</span><span class="sxs-lookup"><span data-stu-id="bba5f-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="bba5f-131">Példa: -##</span><span class="sxs-lookup"><span data-stu-id="bba5f-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="bba5f-132">Raktár-helyek meghatározása</span><span class="sxs-lookup"><span data-stu-id="bba5f-132">Define warehouse locations</span></span>
1. <span data-ttu-id="bba5f-133">A Műveleti panelen kattintson a Raktár elemre.</span><span class="sxs-lookup"><span data-stu-id="bba5f-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="bba5f-134">Kattintás a Hely varázslóra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="bba5f-135">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-135">Click Next.</span></span>
4. <span data-ttu-id="bba5f-136">A Kiszállítási területek beállítás kijelölésének törlése</span><span class="sxs-lookup"><span data-stu-id="bba5f-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="bba5f-137">Az Ömlesztett tárolóhelyek beállítás kijelölésének törlése</span><span class="sxs-lookup"><span data-stu-id="bba5f-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="bba5f-138">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-138">Click Next.</span></span>
7. <span data-ttu-id="bba5f-139">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-139">Click Next.</span></span>
8. <span data-ttu-id="bba5f-140">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-140">Click Next.</span></span>
9. <span data-ttu-id="bba5f-141">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-141">Click Next.</span></span>
10. <span data-ttu-id="bba5f-142">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-142">Click Next.</span></span>
11. <span data-ttu-id="bba5f-143">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-143">Click Next.</span></span>
12. <span data-ttu-id="bba5f-144">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-144">Click Next.</span></span>
    * <span data-ttu-id="bba5f-145">Ne feledje, hogy a lapon látható fizikai dimenziók azok, melyeket Ön a folyamat kezdetekor állít be.</span><span class="sxs-lookup"><span data-stu-id="bba5f-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="bba5f-146">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-146">Click Next.</span></span>
14. <span data-ttu-id="bba5f-147">Kattintson a Finish gombra.</span><span class="sxs-lookup"><span data-stu-id="bba5f-147">Click Finish.</span></span>
15. <span data-ttu-id="bba5f-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bba5f-148">Close the page.</span></span>
16. <span data-ttu-id="bba5f-149">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="bba5f-149">Refresh the page.</span></span>


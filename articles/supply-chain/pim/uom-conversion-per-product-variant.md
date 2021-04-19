---
title: Mértékegység-átváltás termékváltozatonként
description: Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a termékváltozatokon. Egy példát is tartalmaz a beállításra.
author: johanhoffmann
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: eaa20f9a8f145fa8d44bfe77cc85f4dc565c2d27
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841503"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="1d09b-104">Mértékegység-átváltás termékváltozatonként</span><span class="sxs-lookup"><span data-stu-id="1d09b-104">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d09b-105">Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a különféle termékváltozatokon.</span><span class="sxs-lookup"><span data-stu-id="1d09b-105">This topic explains how to set up unit of measure conversions for various product variants.</span></span>

<span data-ttu-id="1d09b-106">A karbantartani kívánt több egyéni termék létrehozása helyett használhatja a termékváltozatokat egyetlen termék változatainak létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1d09b-106">Instead of creating multiple individual products that must be maintained, you can use product variants to create variations of a single product.</span></span> <span data-ttu-id="1d09b-107">Egy termékváltozat lehet például egy adott méretű és színű póló.</span><span class="sxs-lookup"><span data-stu-id="1d09b-107">For example, a product variant might be a T-shirt of a given size and color.</span></span>

<span data-ttu-id="1d09b-108">Korábban a mértékegységek átváltásait csak az alaptermékben lehetett beállítani.</span><span class="sxs-lookup"><span data-stu-id="1d09b-108">Previously, unit conversions could be set up only on the product master.</span></span> <span data-ttu-id="1d09b-109">Ezért minden termékváltozat ugyanazzal az egységátváltási szabályokkal rendelkezett.</span><span class="sxs-lookup"><span data-stu-id="1d09b-109">Therefore, all product variants had the same unit conversion rules.</span></span> <span data-ttu-id="1d09b-110">Ha azonban a *Mértékegység-átváltások termékváltozatok esetén* funkció be van kapcsolva, ha a pólókat dobozban értékesítik, és a csomagolható pólók száma a pólók méretétől függ, akkor most beállíthatja a különböző pólóméretek és a csomagoláshoz használt dobozok között mértékegység-átváltásokat.</span><span class="sxs-lookup"><span data-stu-id="1d09b-110">However, when the *Unit of measure conversions for product variants* feature is turned on, if your T-shirts are sold in boxes, and the number of T-shirts that can be packed in a box depends on the size of the T-shirts, you can now set up unit conversions between the different shirt sizes and the boxes that are used for packaging.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="1d09b-111">A funkció bekapcsolása a rendszerben</span><span class="sxs-lookup"><span data-stu-id="1d09b-111">Turn on the feature in your system</span></span>

<span data-ttu-id="1d09b-112">Ha nem látja ezt a funkciót a rendszerben, nyissa meg a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) részt, és kapcsolja be a *Mértékegység-átváltások termékváltozatok esetén* funkciót.</span><span class="sxs-lookup"><span data-stu-id="1d09b-112">If you don't already see this feature in your system, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Unit of measure conversions for product variants* feature.</span></span>

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="1d09b-113">A termék beállítása egységátváltáshoz változat szerint</span><span class="sxs-lookup"><span data-stu-id="1d09b-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="1d09b-114">Termékváltozatokat csak olyan termékekhez lehet létrehozni, amelyek alaptermékek.</span><span class="sxs-lookup"><span data-stu-id="1d09b-114">Product variants can be created only for products that are product masters.</span></span> <span data-ttu-id="1d09b-115">További információ: [Alaptermék létrehozása](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="1d09b-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span> <span data-ttu-id="1d09b-116">A *Mértékegység-átváltások termékváltozatok esetén* funkció nem érhető el a tényleges súlyú folyamatokhoz beállított termékek esetében.</span><span class="sxs-lookup"><span data-stu-id="1d09b-116">The *Unit of measure conversions for product variants* feature isn't available for products that are set up for catch-weight processes.</span></span>

<span data-ttu-id="1d09b-117">A következő lépésekkel konfigurálhat egy alapterméket, amely támogatja a változatonkénti mértékegység-átalakítást.</span><span class="sxs-lookup"><span data-stu-id="1d09b-117">To configure a product master to support unit conversion per variant, follow these steps.</span></span>

1. <span data-ttu-id="1d09b-118">Ugorjon a **Termékinformációk kezelése \> Termékek \> Alaptermékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1d09b-118">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="1d09b-119">Hozzon létre vagy nyisson meg egy alapterméket, hogy a **Termék részletei** oldalra jusson.</span><span class="sxs-lookup"><span data-stu-id="1d09b-119">Create or open a product master to go to its **Product details** page.</span></span>
1. <span data-ttu-id="1d09b-120">Állítsa a **Mértékegység-átváltások engedélyezése** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="1d09b-120">Set the **Enable unit of measure conversions** option to *Yes*.</span></span>
1. <span data-ttu-id="1d09b-121">A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Mértékegység-átváltások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d09b-121">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Unit conversions**.</span></span>
1. <span data-ttu-id="1d09b-122">Megnyílik a **Mértékegység-átváltások** oldal.</span><span class="sxs-lookup"><span data-stu-id="1d09b-122">The **Unit conversions** page opens.</span></span> <span data-ttu-id="1d09b-123">A következő lapok közül választhat:</span><span class="sxs-lookup"><span data-stu-id="1d09b-123">Select one of the following tabs:</span></span>

    - <span data-ttu-id="1d09b-124">**Osztályon belüli átváltások** – Akkor válassza ezt a lapot, ha az ugyanahhoz az osztályhoz tartozó mértékegységek között szeretné végrehajtani az átalakítást.</span><span class="sxs-lookup"><span data-stu-id="1d09b-124">**Intra-class conversions** – Select this tab to convert between units that belong to the same unit class.</span></span>
    - <span data-ttu-id="1d09b-125">**Osztályok közötti átváltások** – Akkor válassza ezt a lapot, ha a különböző osztályokhoz tartozó mértékegységek között szeretné végrehajtani az átalakítást.</span><span class="sxs-lookup"><span data-stu-id="1d09b-125">**Inter-class conversions** – Select this tab to convert between units that belong to different unit classes.</span></span>

1. <span data-ttu-id="1d09b-126">Új mértékegység-átváltás hozzáadásához kattintson az **Új** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1d09b-126">Select **New** to add a new unit conversion.</span></span>
1. <span data-ttu-id="1d09b-127">Állítsa a **Átváltás létrehozása a következőhöz:** mezőt a következő értékek egyikére:</span><span class="sxs-lookup"><span data-stu-id="1d09b-127">Set the **Create conversion for** field to one of the following values:</span></span>

    - <span data-ttu-id="1d09b-128">**Termék** – Ha ezt az értéket választja, akkor beállíthatja a mértékegység-átváltást az alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="1d09b-128">**Product** – If you select this value, you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="1d09b-129">Ez a mértékegység-átváltás tartalékként fog szerepelni az összes olyan termékváltozathoz, amelynél nincs beállítva mértékegység-átváltás.</span><span class="sxs-lookup"><span data-stu-id="1d09b-129">That unit conversion will be used as a fallback for all product variants that no unit conversion is defined for.</span></span>
    - <span data-ttu-id="1d09b-130">**Termékváltozat** – Ha ezt az értéket választja, akkor beállíthatja a mértékegység-átváltást egy adott termékváltozathoz.</span><span class="sxs-lookup"><span data-stu-id="1d09b-130">**Product variant** – If you select this value, you can set up a unit conversion for a specific product variant.</span></span> <span data-ttu-id="1d09b-131">Válassza ki a változatot a **Termékváltozat** mező segítségével.</span><span class="sxs-lookup"><span data-stu-id="1d09b-131">Use the **Product variant** field to select the variant.</span></span>

    <span data-ttu-id="1d09b-132">![Új mértékegység-átváltás hozzáadása](media/uom-new-conversion.png "Új mértékegység-átváltás hozzáadása")</span><span class="sxs-lookup"><span data-stu-id="1d09b-132">![Adding a new unit conversion](media/uom-new-conversion.png "Adding a new unit conversion")</span></span>

1. <span data-ttu-id="1d09b-133">A mértékegység-átváltás beállításához használja az egyéb megadott mezőket.</span><span class="sxs-lookup"><span data-stu-id="1d09b-133">Use the other fields that are provided to set up your unit conversion.</span></span>
1. <span data-ttu-id="1d09b-134">Az új mértékegység-átalakítás mentéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1d09b-134">Select **OK** to save the new unit conversion.</span></span>

> [!TIP]
> <span data-ttu-id="1d09b-135">A termék vagy a termékváltozat **Mértékegység-átalakítás** oldalát a következő oldalak bármelyikéről megnyithatja:</span><span class="sxs-lookup"><span data-stu-id="1d09b-135">You can open the **Unit conversions** page for a product or a product variant from any of the following pages:</span></span>
> 
> - <span data-ttu-id="1d09b-136">Termék részletei</span><span class="sxs-lookup"><span data-stu-id="1d09b-136">Product details</span></span>
> - <span data-ttu-id="1d09b-137">Megjelent termékek részletei</span><span class="sxs-lookup"><span data-stu-id="1d09b-137">Released products details</span></span>
> - <span data-ttu-id="1d09b-138">Kiadott termékváltozatok</span><span class="sxs-lookup"><span data-stu-id="1d09b-138">Released product variants</span></span>

## <a name="example-scenario"></a><span data-ttu-id="1d09b-139">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="1d09b-139">Example scenario</span></span>

<span data-ttu-id="1d09b-140">Ebben a forgatókönyvben egy vállalat pólókat értékesít kicsi, közepes, nagy és extra nagy méretben.</span><span class="sxs-lookup"><span data-stu-id="1d09b-140">In this scenario, a company sells T-shirts in sizes small, medium, large, and extra-large.</span></span> <span data-ttu-id="1d09b-141">A pólót termékként határozzuk meg, a különböző méreteket pedig a termék változataiként definiáljuk.</span><span class="sxs-lookup"><span data-stu-id="1d09b-141">The T-shirt is defined as a product, and the different sizes are defined as variants of that product.</span></span> <span data-ttu-id="1d09b-142">A pólók csomagolása dobozokban történik.</span><span class="sxs-lookup"><span data-stu-id="1d09b-142">The shirts are packed in boxes.</span></span> <span data-ttu-id="1d09b-143">A kis, közepes és nagy méreteknél a dobozban öt póló lehet.</span><span class="sxs-lookup"><span data-stu-id="1d09b-143">For sizes small, medium, and large, there can be five shirts in each box.</span></span> <span data-ttu-id="1d09b-144">Az extra nagy méretnél azonban csak négy póló számára van hely a dobozban.</span><span class="sxs-lookup"><span data-stu-id="1d09b-144">However, for size extra-large, there is space for only four shirts in each box.</span></span>

<span data-ttu-id="1d09b-145">A vállalat nyomon szeretné követni a pólók különböző változatait *Darab* mértékegyégben, de a pólókat *Doboz* mértékegységben forgalmazza.</span><span class="sxs-lookup"><span data-stu-id="1d09b-145">The company wants to track the different variants in the *Pieces* unit, but it's selling them in the *Boxes* unit.</span></span> <span data-ttu-id="1d09b-146">Kis, közepes és nagy méretek esetében a készletegység és az értékesítési egység közötti átváltási arány 1 doboz = 5 darab.</span><span class="sxs-lookup"><span data-stu-id="1d09b-146">For sizes small, medium, and large, the conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces.</span></span> <span data-ttu-id="1d09b-147">Az extra nagy méretnél az átváltási arány 1 doboz = 4 darab.</span><span class="sxs-lookup"><span data-stu-id="1d09b-147">For size extra-large, the conversion is 1 Box = 4 Pieces.</span></span>

1. <span data-ttu-id="1d09b-148">Először nyissa meg a **Mértékegység-átváltás** lapot a **Póló** termék **Termékkiadás részletei** lapjáról.</span><span class="sxs-lookup"><span data-stu-id="1d09b-148">From the **Released product details** page for the **T-Shirt** product, open the **Unit conversions** page.</span></span>
1. <span data-ttu-id="1d09b-149">A **Mértékegység-átváltás** lapon állítsa be a következő mértékegység-átváltást az **Extra nagy** kiadási termékváltozatnál.</span><span class="sxs-lookup"><span data-stu-id="1d09b-149">On the **Unit conversions** page, set up the following unit conversion for the **X-Large** released product variant.</span></span>

    | <span data-ttu-id="1d09b-150">Mező</span><span class="sxs-lookup"><span data-stu-id="1d09b-150">Field</span></span>                 | <span data-ttu-id="1d09b-151">Beállítás</span><span class="sxs-lookup"><span data-stu-id="1d09b-151">Setting</span></span>                 |
    |-----------------------|-------------------------|
    | <span data-ttu-id="1d09b-152">Átváltás létrehozása a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="1d09b-152">Create conversion for</span></span> | <span data-ttu-id="1d09b-153">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="1d09b-153">Product variant</span></span>         |
    | <span data-ttu-id="1d09b-154">Termékváltozat</span><span class="sxs-lookup"><span data-stu-id="1d09b-154">Product variant</span></span>       | <span data-ttu-id="1d09b-155">Póló : : Extra nagy : :</span><span class="sxs-lookup"><span data-stu-id="1d09b-155">T-Shirt : : X-Large : :</span></span> |
    | <span data-ttu-id="1d09b-156">Kezdő egység</span><span class="sxs-lookup"><span data-stu-id="1d09b-156">From unit</span></span>             | <span data-ttu-id="1d09b-157">Dobozok</span><span class="sxs-lookup"><span data-stu-id="1d09b-157">Boxes</span></span>                   |
    | <span data-ttu-id="1d09b-158">Szorzó</span><span class="sxs-lookup"><span data-stu-id="1d09b-158">Factor</span></span>                | <span data-ttu-id="1d09b-159">4</span><span class="sxs-lookup"><span data-stu-id="1d09b-159">4</span></span>                       |
    | <span data-ttu-id="1d09b-160">Záró egység</span><span class="sxs-lookup"><span data-stu-id="1d09b-160">To Unit</span></span>               | <span data-ttu-id="1d09b-161">darab</span><span class="sxs-lookup"><span data-stu-id="1d09b-161">Pieces</span></span>                  |

1. <span data-ttu-id="1d09b-162">Mivel a **Kicsi**, **Közepes** és **Nagy** termékváltozatok esetében azonos a mértékegység-átváltás a *Doboz* és a *Darab* egységek között, az alapterméken meg lehet adni a mértékegység-átváltást ezekhez a termékváltozatokhoz.</span><span class="sxs-lookup"><span data-stu-id="1d09b-162">Because the **Small**, **Medium**, and **Large** product variants all have the same unit conversion between the *Box* and *Pieces* units, you can define the following unit conversion for them on the product master.</span></span>

    | <span data-ttu-id="1d09b-163">Mező</span><span class="sxs-lookup"><span data-stu-id="1d09b-163">Field</span></span>                 | <span data-ttu-id="1d09b-164">Beállítás</span><span class="sxs-lookup"><span data-stu-id="1d09b-164">Setting</span></span> |
    |-----------------------|---------|
    | <span data-ttu-id="1d09b-165">Átváltás létrehozása a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="1d09b-165">Create conversion for</span></span> | <span data-ttu-id="1d09b-166">Termék</span><span class="sxs-lookup"><span data-stu-id="1d09b-166">Product</span></span> |
    | <span data-ttu-id="1d09b-167">Termék</span><span class="sxs-lookup"><span data-stu-id="1d09b-167">Product</span></span>               | <span data-ttu-id="1d09b-168">Póló</span><span class="sxs-lookup"><span data-stu-id="1d09b-168">T-Shirt</span></span> |
    | <span data-ttu-id="1d09b-169">Kezdő egység</span><span class="sxs-lookup"><span data-stu-id="1d09b-169">From unit</span></span>             | <span data-ttu-id="1d09b-170">Dobozok</span><span class="sxs-lookup"><span data-stu-id="1d09b-170">Boxes</span></span>   |
    | <span data-ttu-id="1d09b-171">Szorzó</span><span class="sxs-lookup"><span data-stu-id="1d09b-171">Factor</span></span>                | <span data-ttu-id="1d09b-172">5</span><span class="sxs-lookup"><span data-stu-id="1d09b-172">5</span></span>       |
    | <span data-ttu-id="1d09b-173">Záró egység</span><span class="sxs-lookup"><span data-stu-id="1d09b-173">To Unit</span></span>               | <span data-ttu-id="1d09b-174">darab</span><span class="sxs-lookup"><span data-stu-id="1d09b-174">Pieces</span></span>  |

## <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="1d09b-175">A mértékegység-átváltások frissítése az Excel programmal</span><span class="sxs-lookup"><span data-stu-id="1d09b-175">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="1d09b-176">Ha egy terméknek számos olyan változata van, amelyek eltérő mértékegység-átváltással rendelkeznek, akkor célszerű exportálni egy Microsoft Excel munkafüzetbe az egység konverzióit, frissíteni őket, majd újra közzéteheti őket a Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="1d09b-176">If a product has many product variants that have different unit conversions, it's a good idea to export the unit conversions to a Microsoft Excel workbook, update them, and then publish them back to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="1d09b-177">Az egységek átváltásának Excel programba történő exportálásához válassza a **Mértékegység-átváltások** oldal Művelet paneljén a **Megnyitás Microsoft Office alkalmazásban** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d09b-177">To export unit conversions to Excel, on the **Unit conversions** page, on the Action Pane, select **Open in Microsoft Office**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1d09b-178">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1d09b-178">Additional resources</span></span>

[<span data-ttu-id="1d09b-179">Mértékegység kezelése</span><span class="sxs-lookup"><span data-stu-id="1d09b-179">Manage unit of measure</span></span>](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
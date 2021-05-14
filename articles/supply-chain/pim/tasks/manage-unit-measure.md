---
title: Mértékegységek kezelése
description: Ez a témakör leírja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921341"
---
# <a name="manage-units-of-measure"></a><span data-ttu-id="308f1-103">Mértékegységek kezelése</span><span class="sxs-lookup"><span data-stu-id="308f1-103">Manage units of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="308f1-104">Ez a témakör leírja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez.</span><span class="sxs-lookup"><span data-stu-id="308f1-104">This topic describes how to define a unit of measure, provide translations for the unit and its description, and define conversion rules for related units.</span></span>

## <a name="open-the-units-page"></a><span data-ttu-id="308f1-105">Nyissa meg az Egységek lapot</span><span class="sxs-lookup"><span data-stu-id="308f1-105">Open the Units page</span></span>

<span data-ttu-id="308f1-106">A rendszerben elérhető mértékegységek létrehozásához és a velük való munkához kattintson a **Szervezet felügyelete \> Beállítás \> Mértékegységek\>** gombra.</span><span class="sxs-lookup"><span data-stu-id="308f1-106">To create and work with the units of measure that are available in your system, go to **Organization administration \> Setup \> Units \> Units**.</span></span>

<span data-ttu-id="308f1-107">A témakör további részei leírják, hogy miket tud megtenni a **Mértékegységek** lapon.</span><span class="sxs-lookup"><span data-stu-id="308f1-107">The remaining sections of this topic describe what you can do on the **Units** page.</span></span>

## <a name="create-standard-units-and-conversions"></a><span data-ttu-id="308f1-108">Szabványos mértékegységek és átváltások létrehozása</span><span class="sxs-lookup"><span data-stu-id="308f1-108">Create standard units and conversions</span></span>

<span data-ttu-id="308f1-109">Ha a rendszer még nem tartalmazza a leggyakrabban használt mértékegységeket a metrikus rendszerhez és/vagy az USA-mértékegységrendszerhez (USCS), akkor az egységbeállítási varázsló segítségével gyorsan megismerkedhet az alapvető egységdefiníciókat és átváltásokat.</span><span class="sxs-lookup"><span data-stu-id="308f1-109">If your system doesn't already include the most commonly used units of measure for the metric system and/or the US customary system (USCS), the unit setup wizard can help you quickly get started with basic unit definitions and conversions.</span></span> <span data-ttu-id="308f1-110">A varázsló befejezéséhez válassza az **Egységlétrehozási varázsló** lehetőséget a munkaablakban, majd kövesse a képernyőn látható utasításokat.</span><span class="sxs-lookup"><span data-stu-id="308f1-110">To complete the wizard, select **Unit creation wizard** on the Action Pane, and then follow the on-screen instructions.</span></span>

## <a name="create-or-edit-a-unit-of-measure"></a><span data-ttu-id="308f1-111">Mértékegység létrehozása vagy szerkesztése</span><span class="sxs-lookup"><span data-stu-id="308f1-111">Create or edit a unit of measure</span></span>

<span data-ttu-id="308f1-112">A mértékegységek létrehozásához vagy szerkesztéséhez kövesse a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="308f1-112">To create or edit a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="308f1-113">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="308f1-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="308f1-114">Meglévő egység szerkesztéséhez jelölje ki azt a listaablakban.</span><span class="sxs-lookup"><span data-stu-id="308f1-114">To edit an existing unit, select it in the list pane.</span></span>
    - <span data-ttu-id="308f1-115">Új egység létrehozásához válassza az **Új** lehetőséget a Művelet panelben.</span><span class="sxs-lookup"><span data-stu-id="308f1-115">To create a new unit, select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="308f1-116">A rekord fejlécen állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="308f1-116">On the header of the record, set the following fields:</span></span>

    - <span data-ttu-id="308f1-117">**Egység** – Adja meg a rendszer nyelvén az egységre való hivatkozási azonosítót vagy szimbólumot.</span><span class="sxs-lookup"><span data-stu-id="308f1-117">**Unit** – Enter the ID or symbol to use to refer to the unit in the system language.</span></span> <span data-ttu-id="308f1-118">Ez az azonosító vagy szimbólum általában az egység általános rövidítése, például az *ea* az egyes, a *cm* pedig a centiméter rövidítése.</span><span class="sxs-lookup"><span data-stu-id="308f1-118">This ID or symbol is usually a common abbreviation for the unit, such as *ea* for each or *cm* for centimeter.</span></span>
    - <span data-ttu-id="308f1-119">**Leírás** – Írjon be egy jellemző nevet az egységnek a rendszer nyelvén.</span><span class="sxs-lookup"><span data-stu-id="308f1-119">**Description** – Enter a descriptive name for the unit in the system language.</span></span> <span data-ttu-id="308f1-120">Ez a név általában az egység teljes neve, például *Egyes* vagy *Centiméter*.</span><span class="sxs-lookup"><span data-stu-id="308f1-120">This name is usually the full name of the unit, such as *Each* or *Centimeter*.</span></span>

1. <span data-ttu-id="308f1-121">Az **Általános** gyorslapon állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="308f1-121">On the **General** FastTab, set the following fields:</span></span><!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - <span data-ttu-id="308f1-122">**Egységosztály** – Válassza ki azt a tulajdonságot, amit az egység mér (például hossz, terület, tömeg vagy mennyiség).</span><span class="sxs-lookup"><span data-stu-id="308f1-122">**Unit class** – Select the property that the unit measures (such as length, area, mass, or quantity).</span></span>
    - <span data-ttu-id="308f1-123">**Mértékegységrendszer** – Válassza ki azt a mértékegységrendszert, amelyhez az egység tartozik (*Metrikus egységek* vagy *Egyesült államokbeli szokásos egységek*).</span><span class="sxs-lookup"><span data-stu-id="308f1-123">**System of units** – Select the measurement system that the unit belongs to (*Metric units* or *United States customary units*).</span></span>
    - <span data-ttu-id="308f1-124">**Alapegység** – Akkor állítsa *Igen* értékre ezt a lehetőséget, ha az aktuális egységet használja az egységosztály alapegységeként.</span><span class="sxs-lookup"><span data-stu-id="308f1-124">**Base unit** – Set this option to *Yes* to use the current unit as the base unit for its unit class.</span></span> <span data-ttu-id="308f1-125">Ebben az esetben csak az alapegység és az egységosztályban található egyes további egységek közötti átváltási tényezőt kell megadni.</span><span class="sxs-lookup"><span data-stu-id="308f1-125">In this case, you only have to specify the conversion factor between the base unit and each additional unit in the unit class.</span></span> <span data-ttu-id="308f1-126">A rendszer ezután átválthat az egységosztályban található összes egység között.</span><span class="sxs-lookup"><span data-stu-id="308f1-126">The system can then convert between all units in that unit class.</span></span> <span data-ttu-id="308f1-127">Ezért könnyebb az átváltások beállítása.</span><span class="sxs-lookup"><span data-stu-id="308f1-127">Therefore, it's easier to set up conversions.</span></span>

        <span data-ttu-id="308f1-128">Ha például a gallon a *Térfogat* egységosztály alapegysége, akkor csak literből gallonba és pintből gallonba kell átváltási tényezőket beállítani.</span><span class="sxs-lookup"><span data-stu-id="308f1-128">For example, if gallon is the base unit for the *Volume* unit class, you only have to set up conversion factors from quart to gallon and from pint to gallon.</span></span> <span data-ttu-id="308f1-129">A rendszer ezután literből pintbe is tud átváltani.</span><span class="sxs-lookup"><span data-stu-id="308f1-129">The system can then also convert from quart to pint.</span></span>

        <span data-ttu-id="308f1-130">Egységosztályonként csak egy alapegység lehet.</span><span class="sxs-lookup"><span data-stu-id="308f1-130">You can have only one base unit per unit class.</span></span>

    - <span data-ttu-id="308f1-131">**Rendszeregység** – Akkor állítsa *Igen* értékre ezt a lehetőséget, ha a becsült egységet használja az egységosztály összes meghatározatlan egységeként.</span><span class="sxs-lookup"><span data-stu-id="308f1-131">**System unit** – Set this option to *Yes* to use the current unit as the assumed unit for all unspecified measurements in its unit class.</span></span> <span data-ttu-id="308f1-132">Ha például egy mező, amibe eddig be lehetett írni mennyiséget nem teszi lehetővé az egység beállítását (ha a felhasználó nem választ ki egységet), akkor a rendszer azt az egységet használja, amely a *Mennyiség* egységosztály rendszeregységeként van beállítva.</span><span class="sxs-lookup"><span data-stu-id="308f1-132">For example, if a field that is used to enter a quantity doesn't allow a unit to be specified (of if the user doesn't select a unit), the system uses the unit that is set as the system unit for the *Quantity* unit class.</span></span> <span data-ttu-id="308f1-133">Egységosztályonként csak egy rendszeregység lehet.</span><span class="sxs-lookup"><span data-stu-id="308f1-133">You can have only one system unit per unit class.</span></span>
    - <span data-ttu-id="308f1-134">**Tizedes pontosság** – Adja meg, hogy hány tizedesjegyre kell kerekíteni az aktuális egység számára megadott vagy az arra átalakítandó értékeket.</span><span class="sxs-lookup"><span data-stu-id="308f1-134">**Decimal precision** – Specify the number of decimal places that values that are specified for the current unit or converted to it should be rounded to.</span></span>

1. <span data-ttu-id="308f1-135">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="308f1-135">On the Action Pane, select **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="308f1-136">Egység fordításainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="308f1-136">Define unit translations</span></span>

<span data-ttu-id="308f1-137">A következő lépések követésével definiálhatja az azonosító vagy szimbólum fordítását, valamint a mértékegység leírását.</span><span class="sxs-lookup"><span data-stu-id="308f1-137">To define translations for the ID or symbol and the description for a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="308f1-138">A fordítások létrehozásához használt egység létrehozása vagy kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="308f1-138">Create or select the unit to create translations for.</span></span>
1. <span data-ttu-id="308f1-139">Válassza a Művelet panelen az **Egységszövegek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="308f1-139">On the Action Pane, select **Unit texts**.</span></span>

    <span data-ttu-id="308f1-140">Megjelenik az **Egységszövegek** lap.</span><span class="sxs-lookup"><span data-stu-id="308f1-140">The **Unit texts** page appears.</span></span> <span data-ttu-id="308f1-141">Ezen a lapon meghatározhatja a kiválasztott egység azonosítójának vagy szimbólumának fordítását.</span><span class="sxs-lookup"><span data-stu-id="308f1-141">You use this page to define translations for the ID or symbol for the selected unit.</span></span> <span data-ttu-id="308f1-142">Ezek a fordítások felhasználhatók a külső dokumentumokon a vevő- vagy szállítóspecifikus nyelveken.</span><span class="sxs-lookup"><span data-stu-id="308f1-142">Those translations can then be used on external documents in customer-specific or vendor-specific languages.</span></span>

1. <span data-ttu-id="308f1-143">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="308f1-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="308f1-144">A **Nyelv** mezőben adja azt a nyelvet, amire le szeretné fordíttatni az egység azonosítóját vagy szimbólumát.</span><span class="sxs-lookup"><span data-stu-id="308f1-144">In the **Language** field, select the language to translate the unit ID or symbol to.</span></span>
1. <span data-ttu-id="308f1-145">A **Szöveg** mezőbe írja be az egységazonosító vagy szimbólum fordítását a kiválasztott nyelven.</span><span class="sxs-lookup"><span data-stu-id="308f1-145">In the **Text** field, enter the translation of the unit ID or symbol in the selected language.</span></span>
1. <span data-ttu-id="308f1-146">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="308f1-146">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="308f1-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="308f1-147">Close the page.</span></span>
1. <span data-ttu-id="308f1-148">A **Művelet panelen** válassza az **Lefordított egységleírások** elemet.</span><span class="sxs-lookup"><span data-stu-id="308f1-148">On the **Action Pane**, select **Translated unit descriptions**.</span></span>

    <span data-ttu-id="308f1-149">Megjelenik a **Lefordított egységleírások** lap.</span><span class="sxs-lookup"><span data-stu-id="308f1-149">The **Translated unit descriptions** page appears.</span></span> <span data-ttu-id="308f1-150">Ezen a lapon lehet a kiválasztott egység nyelvspecifikus leírását definiálni.</span><span class="sxs-lookup"><span data-stu-id="308f1-150">You use this page to define language-specific descriptions for the selected unit.</span></span>

1. <span data-ttu-id="308f1-151">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="308f1-151">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="308f1-152">A **Nyelv** mezőben adja azt a nyelvet, amire le szeretné fordíttatni az egység leírását.</span><span class="sxs-lookup"><span data-stu-id="308f1-152">In the **Language** field, select the language to translate the unit description to.</span></span>
1. <span data-ttu-id="308f1-153">A **Leírás** mezőbe írja be az egységleírás fordítását a kiválasztott nyelven.</span><span class="sxs-lookup"><span data-stu-id="308f1-153">In the **Description** field, enter the translation of the unit description in the selected language.</span></span>
1. <span data-ttu-id="308f1-154">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="308f1-154">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="308f1-155">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="308f1-155">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="308f1-156">Egység átváltási szabályok definiálása</span><span class="sxs-lookup"><span data-stu-id="308f1-156">Define unit conversion rules</span></span>

<span data-ttu-id="308f1-157">A mértékegységek közötti átváltási szabályok meghatározásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="308f1-157">To define rules for conversions between units of measure, follow these steps.</span></span>

1. <span data-ttu-id="308f1-158">Az átváltási szabályok mehatározásához használt egység létrehozása vagy kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="308f1-158">Create or select the unit to define conversion rules for.</span></span>
1. <span data-ttu-id="308f1-159">Válassza a Művelet panelen az **Egységátváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="308f1-159">On the Action Pane, select **Unit conversions**.</span></span>

    <span data-ttu-id="308f1-160">Megjelenik a **Mértékegység-átváltások** oldal.</span><span class="sxs-lookup"><span data-stu-id="308f1-160">The **Unit conversions** page appears.</span></span> <span data-ttu-id="308f1-161">Arra használhatja ezt az oldalt, hogy szabályokat adjon meg a kiválasztott egységek átváltásához más egységekről és egységekre az egységosztályban.</span><span class="sxs-lookup"><span data-stu-id="308f1-161">You use this page to define rules for converting the selected unit to and from other units in the unit class.</span></span>

1. <span data-ttu-id="308f1-162">A következő lapok közül választhat a beállítani kívánt átváltás típusától függően:</span><span class="sxs-lookup"><span data-stu-id="308f1-162">Select one of the following tabs, depending on the type of conversion that you want to set up:</span></span>

    - <span data-ttu-id="308f1-163">**Standard átváltások** – Az összes termékre vonatkozó normál átváltási szabályok beállítása.</span><span class="sxs-lookup"><span data-stu-id="308f1-163">**Standard conversions** – Set up standard conversion rules for all products.</span></span>
    - <span data-ttu-id="308f1-164">**Osztályon belüli átváltások** – Termékspecifikus átváltási szabályok beállítása az ugyanabban az egységosztályban található egységekre.</span><span class="sxs-lookup"><span data-stu-id="308f1-164">**Intra-class conversions** – Set up product-specific conversion rules for units in the same unit class.</span></span>
    - <span data-ttu-id="308f1-165">**Osztályok közötti átváltások** – Termékspecifikus átváltási szabályok beállítása az egységosztályok között.</span><span class="sxs-lookup"><span data-stu-id="308f1-165">**Inter-class conversions** – Set up product-specific conversion rules for units across unit classes.</span></span>

1. <span data-ttu-id="308f1-166">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="308f1-166">Follow one of these steps:</span></span>

    - <span data-ttu-id="308f1-167">Új átváltás létrehozásához válassza az **Új** lehetőséget az eszközsávban.</span><span class="sxs-lookup"><span data-stu-id="308f1-167">To create a new conversion, select **New** on the toolbar.</span></span>
    - <span data-ttu-id="308f1-168">Meglévő átváltás szerkesztéséhez jelölje ki az átváltást a rácson, majd válassza az eszköztár **Szerkesztés** lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="308f1-168">To edit an existing conversion, select the conversion in the grid, and then select **Edit** on the toolbar.</span></span>

1. <span data-ttu-id="308f1-169">A legördülő párbeszédpanelen a következő mezőket állítsa be:</span><span class="sxs-lookup"><span data-stu-id="308f1-169">In the drop-down dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="308f1-170">**Termék** – Válassza ki azt a terméket, amelyre az átváltás vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="308f1-170">**Product** – Select the specific product that the conversion applies to.</span></span> <span data-ttu-id="308f1-171">Ez a mező csak osztályon belüli és osztályközi átalakítások esetén érhető el.</span><span class="sxs-lookup"><span data-stu-id="308f1-171">This field is available only for intra-class and inter-class conversions.</span></span>
    - <span data-ttu-id="308f1-172">**Receptúraelrendezés** – Hagyja ezt a mezőt *Egyszerű* beállításban, és adjon meg egy egyszerű átváltási tényezőt.</span><span class="sxs-lookup"><span data-stu-id="308f1-172">**Formula layout** – Leave this field set to *Simple* to specify a simple conversion that has a single factor.</span></span> <span data-ttu-id="308f1-173">Állítsa *Speciális* értékre egy összetettebb egyenlet beállításhoz.</span><span class="sxs-lookup"><span data-stu-id="308f1-173">Set it to *Advanced* to set up a more complex equation.</span></span> <span data-ttu-id="308f1-174">A speciális egyenletek formátuma az egységosztálytól függően eltérő lehet.</span><span class="sxs-lookup"><span data-stu-id="308f1-174">The format for advanced equations varies, depending on the unit class.</span></span>
    - <span data-ttu-id="308f1-175">**Kezdő egység** – Ez a mező a kiválasztott egységet mutatja.</span><span class="sxs-lookup"><span data-stu-id="308f1-175">**From unit** – This field shows the selected unit.</span></span> <span data-ttu-id="308f1-176">Általában nem szabad módosítani az értéket.</span><span class="sxs-lookup"><span data-stu-id="308f1-176">Usually, you should not change the value.</span></span> <span data-ttu-id="308f1-177">(Ha módosítja az értéket, meg kell nyitnia az **Egységátváltási** lapot a kiválasztott egységhez, hogy megtekinthesse az új átváltást a mentés után.)</span><span class="sxs-lookup"><span data-stu-id="308f1-177">(If you do change the value, you must open the **Unit conversions** page for the selected unit to view your new conversion after you save it.)</span></span>
    - <span data-ttu-id="308f1-178">**Cél egység** – Válassza ki azt az egységet, amelybe át kell váltani.</span><span class="sxs-lookup"><span data-stu-id="308f1-178">**To unit** – Select the unit to convert to.</span></span>
    - <span data-ttu-id="308f1-179">**Kerekítés** – Válassza ki, hogyan legyenek kerekítve a törtek a kiválasztott egység **Tizedes pontosság** értéke alapján (*Legközelebbi*, *Fel* és *Le*).</span><span class="sxs-lookup"><span data-stu-id="308f1-179">**Rounding** – Select how fractions should be rounded, based on the **Decimal precision** value of the selected unit (*To nearest*, *Up*, or *Down*).</span></span>
    - <span data-ttu-id="308f1-180">**Átváltási képlet** – A legördülő párbeszédpanel tetején található további mezők használatával megadhatja a két egység közötti átváltási képletet.</span><span class="sxs-lookup"><span data-stu-id="308f1-180">**Conversion formula** – Use the remaining fields at the top of the drop-down dialog box to specify the formula for converting between the two units.</span></span> <span data-ttu-id="308f1-181">A választható mezők a kiválasztott egységosztálytól és receptúraelrendezéstől függően eltérőek.</span><span class="sxs-lookup"><span data-stu-id="308f1-181">The available fields vary, depending on the unit class and formula layout that you've selected.</span></span>

1. <span data-ttu-id="308f1-182">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="308f1-182">Select **OK**.</span></span>
1. <span data-ttu-id="308f1-183">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="308f1-183">Close the page.</span></span>

> [!TIP]
> <span data-ttu-id="308f1-184">Termékváltozatonkénti egységátváltásokat is be lehet állítani.</span><span class="sxs-lookup"><span data-stu-id="308f1-184">You can also set up unit conversions per product variant.</span></span> <span data-ttu-id="308f1-185">További információért lásd: [Mértékegység-átváltás termékváltozatonként](../uom-conversion-per-product-variant.md).</span><span class="sxs-lookup"><span data-stu-id="308f1-185">For more information, see [Unit of measure conversion per product variant](../uom-conversion-per-product-variant.md).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

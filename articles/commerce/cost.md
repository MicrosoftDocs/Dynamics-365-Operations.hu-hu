---
title: A felosztott rendeléskezelés (DOM) költségkonfigurációja
description: Ez a témakör a Dynamics 365 Commerce felosztott rendeléskezelés (DOM) funkciójára vonatkozó költségkonfigurációt részletezi.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: bfdfee76840380b7dc7ea5043d7e188e3deebf05
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213914"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a><span data-ttu-id="360c3-103">A felosztott rendeléskezelés (DOM) költségkonfigurációja</span><span class="sxs-lookup"><span data-stu-id="360c3-103">Cost configuration for distributed order management (DOM)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="360c3-104">A szervezeteknek számos költségösszetevőt kell figyelembe venniük annak meghatározására, hogy melyik a rendelés teljesítésének szempontjából optimális helyszín.</span><span class="sxs-lookup"><span data-stu-id="360c3-104">Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</span></span> <span data-ttu-id="360c3-105">Ezen költségösszetevők közé tartozik például a szállítási költség, a kezelési költség és a csomagolási költség.</span><span class="sxs-lookup"><span data-stu-id="360c3-105">Some of these cost components are shipping cost, handling cost, and packaging cost.</span></span> <span data-ttu-id="360c3-106">Ezeknek a költségeknek a kombinációját ki kell számítani a teljesítési helyszín meghatározása céljából.</span><span class="sxs-lookup"><span data-stu-id="360c3-106">A combination of these costs is calculated to determine the fulfillment location.</span></span>

<span data-ttu-id="360c3-107">A Dynamics 365 Commerce szolgáltatásban a felosztott rendeléskezelés (DOM) első ismétlésekor sor került a megrendelések teljesítési helyszínekhez való hozzárendelésének optimalizálására, a rendszer csak a távolságot vette figyelembe.</span><span class="sxs-lookup"><span data-stu-id="360c3-107">When the first iteration of distributed order management (DOM) in Dynamics 365 Commerce optimized the assignment of orders to fulfillment locations, it factored in distance only.</span></span> <span data-ttu-id="360c3-108">Ugyan a távolság korrelálható a költséggel, ez nem egyezik meg a költséggel.</span><span class="sxs-lookup"><span data-stu-id="360c3-108">Although distance can be correlated with cost, it isn't the same as cost.</span></span> <span data-ttu-id="360c3-109">Például egy 24 órán belüli szállítási módszer többe kerül, mint a háromnapos szállítás vagy a hétnapos szállítás ugyanakkora távolságra.</span><span class="sxs-lookup"><span data-stu-id="360c3-109">For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</span></span>

<span data-ttu-id="360c3-110">A költségkonfiguráció funkció segítségével a kiskereskedők meghatározhatják és konfigurálhatják a további költségösszetevőket, amelyeket az rendelési sorok teljesítése céljából optimális helyszín meghatározása céljából ki kell számítani és figyelembe kell venni.</span><span class="sxs-lookup"><span data-stu-id="360c3-110">The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</span></span>

<span data-ttu-id="360c3-111">Ha be van állítva a költségösszetevők konfigurálása, a DOM-feloldó csak ezeket a költségmeghatározásokat használja a rendelés teljesítése szempontjából optimális helyszín meghatározásakor.</span><span class="sxs-lookup"><span data-stu-id="360c3-111">When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</span></span> <span data-ttu-id="360c3-112">Nem veszi figyelembe a távolság-összetevőt költségként.</span><span class="sxs-lookup"><span data-stu-id="360c3-112">It doesn't consider the distance component as a cost.</span></span> <span data-ttu-id="360c3-113">Azonban ha nincs beállítva a költségösszetevők konfigurálása, a DOM-feloldó használja a távolság-összetevőt költségként a rendelés teljesítése szempontjából optimális helyszín meghatározásakor.</span><span class="sxs-lookup"><span data-stu-id="360c3-113">However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</span></span>

## <a name="set-up-cost-components"></a><span data-ttu-id="360c3-114">Költségösszetevők beállítása</span><span class="sxs-lookup"><span data-stu-id="360c3-114">Set up cost components</span></span>

<span data-ttu-id="360c3-115">A rendszerben két fő költségösszetevő-típus határozható meg: **Szállítási** és **Egyéb**.</span><span class="sxs-lookup"><span data-stu-id="360c3-115">Two major cost component types can be defined in the system: **Shipping** and **Other**.</span></span>

<span data-ttu-id="360c3-116">Mindkét típusú költségösszetevő több számítási alapot is támogat, ahogy az alábbi táblázatban látható.</span><span class="sxs-lookup"><span data-stu-id="360c3-116">Both cost component types support multiple calculation bases, as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="360c3-117">Költségösszetevő típusa</span><span class="sxs-lookup"><span data-stu-id="360c3-117">Cost component type</span></span></th>
<th><span data-ttu-id="360c3-118">Számítás alapja</span><span class="sxs-lookup"><span data-stu-id="360c3-118">Calculation basis</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="360c3-119">Szállítás</span><span class="sxs-lookup"><span data-stu-id="360c3-119">Shipping</span></span></td>
<td>
<ul>
<li><span data-ttu-id="360c3-120">Egyszerű</span><span class="sxs-lookup"><span data-stu-id="360c3-120">Simple</span></span></li>
<li><span data-ttu-id="360c3-121">Rétegzett</span><span class="sxs-lookup"><span data-stu-id="360c3-121">Tiered</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="360c3-122">Egyéb</span><span class="sxs-lookup"><span data-stu-id="360c3-122">Other</span></span></td>
<td>
<ul>
<li><span data-ttu-id="360c3-123">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="360c3-123">Sales order</span></span></li>
<li><span data-ttu-id="360c3-124">Értékesítési sor</span><span class="sxs-lookup"><span data-stu-id="360c3-124">Sales line</span></span></li>
<li><span data-ttu-id="360c3-125">Helyszín</span><span class="sxs-lookup"><span data-stu-id="360c3-125">Location</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a><span data-ttu-id="360c3-126">Szállítási költségösszetevő típusa</span><span class="sxs-lookup"><span data-stu-id="360c3-126">Shipping cost component type</span></span>

<span data-ttu-id="360c3-127">Ez a szakasz bemutatja, hogy hogyan lehet beállítani a **Szállítási** költségösszetevő-típus és a számítási alap egyes kombinációit a szállítási költségekhez.</span><span class="sxs-lookup"><span data-stu-id="360c3-127">This section explains how to set up each combination of the **Shipping** cost component type and a calculation basis for shipping costs.</span></span> <span data-ttu-id="360c3-128">Bemutatja azt is, hogy a DOM-feloldó miként alkalmazza az egyes kombinációkat.</span><span class="sxs-lookup"><span data-stu-id="360c3-128">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a><span data-ttu-id="360c3-129">Költségösszetevő típusa = Szállítási és Számítási alap = Egyszerű</span><span class="sxs-lookup"><span data-stu-id="360c3-129">Cost component type = Shipping and Calculation basis = Simple</span></span>

<span data-ttu-id="360c3-130">Ha a **Szállítási** költségösszetevő-típus és az **Egyszerű** számítási alap kombinációját alkalmazzák, akkor a szállítási módhoz tartozó szállítási költség egy állandó költségen vagy távolságon alapul.</span><span class="sxs-lookup"><span data-stu-id="360c3-130">If a combination of the **Shipping** cost component type and the **Simple** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span>

<span data-ttu-id="360c3-131">Ehhez a kombinációhoz a következő mezőket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="360c3-131">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="360c3-132">**Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="360c3-132">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="360c3-133">**Leírás** – Adja meg a költségtényező nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="360c3-133">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="360c3-134">**Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</span><span class="sxs-lookup"><span data-stu-id="360c3-134">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="360c3-135">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</span><span class="sxs-lookup"><span data-stu-id="360c3-135">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="360c3-136">**Aktív** – Azt jelzi, hogy a költségtényező aktív-e.</span><span class="sxs-lookup"><span data-stu-id="360c3-136">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="360c3-137">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="360c3-137">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="360c3-138">**Vállalat** – Adja meg azt a jogi személyt, amelyre vonatkozóan konfigurálja a költségtényezőt.</span><span class="sxs-lookup"><span data-stu-id="360c3-138">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="360c3-139">A számítási feltétel minden sorának ugyanarra a jogi személyre kell vonatkoznia.</span><span class="sxs-lookup"><span data-stu-id="360c3-139">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="360c3-140">**Szállítási módok** – Adja meg azokat a szállítási módokat, amelyhez kapcsolódóan konfigurálja a költséget.</span><span class="sxs-lookup"><span data-stu-id="360c3-140">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="360c3-141">**Számítási típus** – Adja meg a költség számításának módját egy megadott szállítási mód esetén.</span><span class="sxs-lookup"><span data-stu-id="360c3-141">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery.</span></span> <span data-ttu-id="360c3-142">A szolgáltatásban két számítási típus támogatott:</span><span class="sxs-lookup"><span data-stu-id="360c3-142">Two calculation types are supported:</span></span>

    - <span data-ttu-id="360c3-143">**Rögzített** – Állandó költség, amely az adott szállítási módhoz használatos.</span><span class="sxs-lookup"><span data-stu-id="360c3-143">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="360c3-144">Ha ezt a számítási típust választja, akkor a **Költség** mező adja meg az állandó költséget.</span><span class="sxs-lookup"><span data-stu-id="360c3-144">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="360c3-145">**Távolságegység szerint** – A szállítási mód költségét a rendszer úgy számítja ki, hogy a **Költség** mezőben megadott költségértéket megszorozza a szállítási cím és a helyszínek közti távolsággal.</span><span class="sxs-lookup"><span data-stu-id="360c3-145">**Per-distance unit** – The cost for the mode of delivery is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="360c3-146">**Költség** – Megadja a **Számítási típus** mezővel kapcsolatban használt költségértéket, amellyel kiszámítható a szállítási mód költsége.</span><span class="sxs-lookup"><span data-stu-id="360c3-146">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a><span data-ttu-id="360c3-147">Költségösszetevő típusa = Szállítási és Számítási alap = Rétegzett</span><span class="sxs-lookup"><span data-stu-id="360c3-147">Cost component type = Shipping and Calculation basis = Tiered</span></span>

<span data-ttu-id="360c3-148">Ha a **Szállítási** költségösszetevő-típus és a **Rétegzett** számítási alap kombinációját alkalmazzák, akkor a szállítási módhoz tartozó szállítási költség egy állandó költségen vagy távolságon alapul.</span><span class="sxs-lookup"><span data-stu-id="360c3-148">If a combination of the **Shipping** cost component type and the **Tiered** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span> <span data-ttu-id="360c3-149">Ebben a kombinációban a távolság több távolság rétegzett tartományán alapul.</span><span class="sxs-lookup"><span data-stu-id="360c3-149">However, in this combination, the distance is based on a tiered range of distances.</span></span>

<span data-ttu-id="360c3-150">Ehhez a kombinációhoz a következő mezőket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="360c3-150">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="360c3-151">**Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="360c3-151">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="360c3-152">**Leírás** – Adja meg a költségtényező nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="360c3-152">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="360c3-153">**Alapértelmezett költség** – Adja meg a szállítási módhoz használt költséget, ha a szállítási cím és a helyszín közti távolság nem esik a szállítási módhoz meghatározott rétegzett távolságok egyikébe sem.</span><span class="sxs-lookup"><span data-stu-id="360c3-153">**Default cost** – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</span></span>
- <span data-ttu-id="360c3-154">**Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</span><span class="sxs-lookup"><span data-stu-id="360c3-154">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="360c3-155">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</span><span class="sxs-lookup"><span data-stu-id="360c3-155">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="360c3-156">**Aktív** – Azt jelzi, hogy a költségtényező aktív-e.</span><span class="sxs-lookup"><span data-stu-id="360c3-156">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="360c3-157">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="360c3-157">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="360c3-158">**Vállalat** – Adja meg azt a jogi személyt, amelyre vonatkozóan konfigurálja a költségtényezőt.</span><span class="sxs-lookup"><span data-stu-id="360c3-158">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="360c3-159">A számítási feltétel minden sorának ugyanarra a jogi személyre kell vonatkoznia.</span><span class="sxs-lookup"><span data-stu-id="360c3-159">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="360c3-160">**Szállítási módok** – Adja meg azokat a szállítási módokat, amelyhez kapcsolódóan konfigurálja a költséget.</span><span class="sxs-lookup"><span data-stu-id="360c3-160">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="360c3-161">**Távolság típusa** – Adja meg, hogy a rétegzett távolság meghatározása légi vagy közúti távolságra utal-e.</span><span class="sxs-lookup"><span data-stu-id="360c3-161">**Distance type** – Specify whether the tiered distance definition is an aerial distance or a road distance.</span></span>
- <span data-ttu-id="360c3-162">**Távolságegységek** – Adja meg az egységet, amelyben a rétegzett távolság mérése történjen.</span><span class="sxs-lookup"><span data-stu-id="360c3-162">**Distance units** – Specify the unit that the tiered distance is measured in.</span></span>
- <span data-ttu-id="360c3-163">**Távolság – alsó határ** – Adja meg a rétegzett távolság tartományának alsó határát.</span><span class="sxs-lookup"><span data-stu-id="360c3-163">**Distance from** – Specify the start range for the tiered distance.</span></span>
- <span data-ttu-id="360c3-164">**Távolság – felső határ** – Adja meg a rétegzett távolság tartományának felső határát.</span><span class="sxs-lookup"><span data-stu-id="360c3-164">**Distance to** – Specify the end range for the tiered distance.</span></span>
- <span data-ttu-id="360c3-165">**Számítási típus** – Adja meg a költség számításának módját egy megadott szállítási mód és rétegzett távolság esetén.</span><span class="sxs-lookup"><span data-stu-id="360c3-165">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</span></span> <span data-ttu-id="360c3-166">A szolgáltatásban két számítási típus támogatott:</span><span class="sxs-lookup"><span data-stu-id="360c3-166">Two calculation types are supported:</span></span>

    - <span data-ttu-id="360c3-167">**Rögzített** – Állandó költség, amely az adott szállítási módhoz használatos.</span><span class="sxs-lookup"><span data-stu-id="360c3-167">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="360c3-168">Ha ezt a számítási típust választja, akkor a **Költség** mező adja meg az állandó költséget.</span><span class="sxs-lookup"><span data-stu-id="360c3-168">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="360c3-169">**Távolságegység szerint** – A szállítási mód és a rétegzett távolság költségét a rendszer úgy számítja ki, hogy a **Költség** mezőben megadott költségértéket megszorozza a szállítási cím és a helyszínek közti távolsággal.</span><span class="sxs-lookup"><span data-stu-id="360c3-169">**Per distance unit** – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="360c3-170">**Költség** – Megadja a **Számítási típus** mezővel kapcsolatban használt költségértéket, amellyel kiszámítható a szállítási mód költsége.</span><span class="sxs-lookup"><span data-stu-id="360c3-170">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

> [!NOTE]
> - <span data-ttu-id="360c3-171">A rétegzett távolságok meghatározása során a rendszer ellenőrzi, hogy nincsenek-e hiányzó vagy egymást átfedő távolságok.</span><span class="sxs-lookup"><span data-stu-id="360c3-171">When you define tiered distances, the system validates that there are no missing or overlapping distances.</span></span>
> - <span data-ttu-id="360c3-172">A szállítási módhoz használt távolságtípusnak az összes rétegzett távolság esetén meg kell egyeznie.</span><span class="sxs-lookup"><span data-stu-id="360c3-172">The distance type that is used for a mode of delivery must be the same across all the tiered distances.</span></span>

### <a name="other-cost-component-type"></a><span data-ttu-id="360c3-173">Egyéb költségösszetevő-típus</span><span class="sxs-lookup"><span data-stu-id="360c3-173">Other cost component type</span></span>

<span data-ttu-id="360c3-174">Ez a szakasz bemutatja, hogy hogyan lehet beállítani az **Egyéb** költségösszetevő-típus és az egyéb költségtípus egyes kombinációit a nem szállítási költségekhez.</span><span class="sxs-lookup"><span data-stu-id="360c3-174">This section explains how to set up each combination of the **Other** cost component type and an other cost type for non-shipping costs.</span></span> <span data-ttu-id="360c3-175">Bemutatja azt is, hogy a DOM-feloldó miként alkalmazza az egyes kombinációkat.</span><span class="sxs-lookup"><span data-stu-id="360c3-175">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a><span data-ttu-id="360c3-176">Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="360c3-176">Cost component type = Other and Other cost type = Sales order</span></span>

<span data-ttu-id="360c3-177">Az **Egyéb** költségösszetevő és az **Értékesítési rendelés** egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos az értékesítési rendelés szintjén.</span><span class="sxs-lookup"><span data-stu-id="360c3-177">A combination of the **Other** cost component type and the **Sales order** other cost type is used to define non-shipping costs at the sales order level.</span></span>

<span data-ttu-id="360c3-178">Ehhez a kombinációhoz a következő mezőket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="360c3-178">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="360c3-179">**Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="360c3-179">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="360c3-180">**Leírás** – Adja meg a költségtényező nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="360c3-180">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="360c3-181">**Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</span><span class="sxs-lookup"><span data-stu-id="360c3-181">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="360c3-182">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</span><span class="sxs-lookup"><span data-stu-id="360c3-182">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="360c3-183">**Aktív** – Azt jelzi, hogy a költségtényező aktív-e.</span><span class="sxs-lookup"><span data-stu-id="360c3-183">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="360c3-184">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="360c3-184">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="360c3-185">**Költség** – Adja meg a nem szállítási költségek értékesítési rendelés szintjén vett költségértékét.</span><span class="sxs-lookup"><span data-stu-id="360c3-185">**Cost** – Specify the cost value for a non-shipping cost at the sales order level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a><span data-ttu-id="360c3-186">Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Értékesítési sor</span><span class="sxs-lookup"><span data-stu-id="360c3-186">Cost component type = Other and Other cost type = Sales line</span></span>

<span data-ttu-id="360c3-187">Az **Egyéb** költségösszetevő és az **Értékesítési sor** egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos az értékesítési rendelési sor szintjén.</span><span class="sxs-lookup"><span data-stu-id="360c3-187">A combination of the **Other** cost component type and the **Sales line** other cost type is used to define non-shipping costs at the sales order line level.</span></span>

<span data-ttu-id="360c3-188">Ehhez a kombinációhoz a következő mezőket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="360c3-188">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="360c3-189">**Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="360c3-189">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="360c3-190">**Leírás** – Adja meg a költségtényező nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="360c3-190">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="360c3-191">**Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</span><span class="sxs-lookup"><span data-stu-id="360c3-191">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="360c3-192">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</span><span class="sxs-lookup"><span data-stu-id="360c3-192">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="360c3-193">**Aktív** – Azt jelzi, hogy a költségtényező aktív-e.</span><span class="sxs-lookup"><span data-stu-id="360c3-193">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="360c3-194">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="360c3-194">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="360c3-195">**Költség** – Adja meg a nem szállítási költségek értékesítési rendelési sor szintjén vett költségértékét.</span><span class="sxs-lookup"><span data-stu-id="360c3-195">**Cost** – Specify the cost value for a non-shipping cost at the sales order line level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--location"></a><span data-ttu-id="360c3-196">Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Helyszín</span><span class="sxs-lookup"><span data-stu-id="360c3-196">Cost component type = Other and Other cost type = Location</span></span>

<span data-ttu-id="360c3-197">Az **Egyéb** költségösszetevő és a **Helyszín** egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos helyszínek csoportjára vagy egy egyéni helyszínre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="360c3-197">A combination of the **Other** cost component type and the **Location** other cost type is used to define non-shipping costs for a group of locations or an individual location.</span></span>

<span data-ttu-id="360c3-198">Ehhez a kombinációhoz a következő mezőket kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="360c3-198">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="360c3-199">**Költségtényező** – Adja meg a költségtényező egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="360c3-199">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="360c3-200">**Leírás** – Adja meg a költségtényező nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="360c3-200">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="360c3-201">**Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</span><span class="sxs-lookup"><span data-stu-id="360c3-201">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="360c3-202">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</span><span class="sxs-lookup"><span data-stu-id="360c3-202">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="360c3-203">**Aktív** – Azt jelzi, hogy a költségtényező aktív-e.</span><span class="sxs-lookup"><span data-stu-id="360c3-203">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="360c3-204">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="360c3-204">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="360c3-205">**Teljesítési csoport** – Adja meg a helyszíncsoportot, amellyel kapcsolatban meghatározza a nem szállítási költséget.</span><span class="sxs-lookup"><span data-stu-id="360c3-205">**Fulfillment group** – Specify the group of locations that the non-shipping cost is defined for.</span></span>
- <span data-ttu-id="360c3-206">**Teljesítési helyszín** – Adja meg a helyszínt, amellyel kapcsolatban meghatározza a nem szállítási költséget.</span><span class="sxs-lookup"><span data-stu-id="360c3-206">**Fulfillment location** – Specify the location that the non-shipping cost is defined for.</span></span>

    > [!NOTE]
    > <span data-ttu-id="360c3-207">Nem adható meg teljesítési csoport és teljesítési helyszín ugyanabban a sorban helyszínalapú számítási feltétel esetén.</span><span class="sxs-lookup"><span data-stu-id="360c3-207">You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</span></span>

- <span data-ttu-id="360c3-208">**Költség** – Adja meg a nem szállítási költségek teljesítési csoport szintjén vagy teljesítési helyszín szintjén vett költségértékét.</span><span class="sxs-lookup"><span data-stu-id="360c3-208">**Cost** – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="360c3-209">Ha azt szeretné, hogy a DOM futtatáskor figyelembe vegye ezeket a költségeket, hozzá kell adnia a költségtényezőt a megfelelő teljesítési profilhoz.</span><span class="sxs-lookup"><span data-stu-id="360c3-209">For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
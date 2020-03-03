---
title: A Modern POS (MPOS) bemutató adatképernyő-elrendezései
description: Ez a témakör a Dynamics 365 Commerce pénztári bemutató adatkészleteinek részét képező képernyő-elrendezésekkel kapcsolatban tartalmaz tájékoztatást.
author: zlinster
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: zlinster
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 7956eece1a77951795a3f5f66067a2ecfacf3450
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022735"
---
# <a name="demo-data-screen-layouts-in-modern-pos-mpos-and-cloud-pos"></a><span data-ttu-id="7a67e-103">A Modern POS (MPOS) bemutató adatképernyő-elrendezései</span><span class="sxs-lookup"><span data-stu-id="7a67e-103">Demo data screen layouts in Modern POS (MPOS) and Cloud POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7a67e-104">Ez a témakör a Dynamics 365 Commerce pénztári bemutató adatkészleteinek részét képező képernyő-elrendezésekkel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="7a67e-104">This topic provides information about the screen layouts that are included with the demo data set for the point of sale (POS) experiences in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7a67e-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7a67e-105">Overview</span></span>

<span data-ttu-id="7a67e-106">Bemutató adatokhoz mellékelt Commerce minta képernyő-elrendezések különböző kiskereskedelmi szegmensekhez, áruházi dolgozói szerepkörökhöz és eszközökhöz optimalizált tartalmakat nyújtanak.</span><span class="sxs-lookup"><span data-stu-id="7a67e-106">The sample screen layouts that are included with Commerce demo data provide content that is optimized for various retail segments, store worker roles, and devices.</span></span> <span data-ttu-id="7a67e-107">Egyetlen elrendezés több elrendezésméretet és gombrácsok kombinációit tartalmazhatja, a fedezet biztosítása érdekében, miközben a dolgozók az eszközök és az állomások között mozognak.</span><span class="sxs-lookup"><span data-stu-id="7a67e-107">A single layout can contain several layout sizes and combinations of button grids, to help ensure coverage as store workers move between devices and stations.</span></span> <span data-ttu-id="7a67e-108">Ez a témakör ismerteti az elrendezések közötti különbségeket, a műveleteket, amelyeket elérhetővé tesznek, valamint a teljes felhasználói élményt, amelyet nyújtanak.</span><span class="sxs-lookup"><span data-stu-id="7a67e-108">This topic highlights the differences between these layouts, the operations that they provide, and the overall experiences that they deliver.</span></span>

![Párhuzamos eszközök bemutatóadat-elrendezések](../commerce/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a><span data-ttu-id="7a67e-110">Képernyő-elrendezés azonosítójának szerkezete</span><span class="sxs-lookup"><span data-stu-id="7a67e-110">Anatomy of a screen layout ID</span></span>

<span data-ttu-id="7a67e-111">A képernyő-elrendezések megkereséséhez kattintson a **Retail és Commerce** \> **Csatorna beállításai** \> **POS-beállítás** \> **POS** \> **Képernyő-elrendezések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7a67e-111">To find screen layouts, go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS** \> **Screen layouts**.</span></span>

![Képernyő-elrendezések lap](../commerce/media/demo-screen-layouts-fig-2-1.png)

<span data-ttu-id="7a67e-113">A képernyő-elrendezés azonosítója legfeljebb 10 karaktert tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="7a67e-113">Screen layout IDs can have a maximum of 10 characters.</span></span> <span data-ttu-id="7a67e-114">Az azonosító karakterlánc, amely három különböző adatot tartalmaz, a következő sorrendben:</span><span class="sxs-lookup"><span data-stu-id="7a67e-114">The ID is a string that consists of three pieces of information, in this order:</span></span>

1. <span data-ttu-id="7a67e-115">Cég</span><span class="sxs-lookup"><span data-stu-id="7a67e-115">Company</span></span>
2. <span data-ttu-id="7a67e-116">Elrendezésverzió</span><span class="sxs-lookup"><span data-stu-id="7a67e-116">Layout version</span></span>
3. <span data-ttu-id="7a67e-117">Személyiség</span><span class="sxs-lookup"><span data-stu-id="7a67e-117">Persona</span></span>

### <a name="company"></a><span data-ttu-id="7a67e-118">Cég</span><span class="sxs-lookup"><span data-stu-id="7a67e-118">Company</span></span>

| <span data-ttu-id="7a67e-119">Levél</span><span class="sxs-lookup"><span data-stu-id="7a67e-119">Letter</span></span> | <span data-ttu-id="7a67e-120">Cég</span><span class="sxs-lookup"><span data-stu-id="7a67e-120">Company</span></span>         |
|--------|-----------------|
| <span data-ttu-id="7a67e-121">A</span><span class="sxs-lookup"><span data-stu-id="7a67e-121">A</span></span>      | <span data-ttu-id="7a67e-122">Kalandorbolt</span><span class="sxs-lookup"><span data-stu-id="7a67e-122">Adventure Works</span></span> |
| <span data-ttu-id="7a67e-123">G</span><span class="sxs-lookup"><span data-stu-id="7a67e-123">F</span></span>      | <span data-ttu-id="7a67e-124">Gyár</span><span class="sxs-lookup"><span data-stu-id="7a67e-124">Fabrikam</span></span>        |
| <span data-ttu-id="7a67e-125">t</span><span class="sxs-lookup"><span data-stu-id="7a67e-125">C</span></span>      | <span data-ttu-id="7a67e-126">Contoso</span><span class="sxs-lookup"><span data-stu-id="7a67e-126">Contoso</span></span>         |

### <a name="layout-version"></a><span data-ttu-id="7a67e-127">Elrendezésverzió</span><span class="sxs-lookup"><span data-stu-id="7a67e-127">Layout version</span></span>

| <span data-ttu-id="7a67e-128">Verziószám</span><span class="sxs-lookup"><span data-stu-id="7a67e-128">Version number</span></span> | <span data-ttu-id="7a67e-129">Leírás</span><span class="sxs-lookup"><span data-stu-id="7a67e-129">Description</span></span>                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| <span data-ttu-id="7a67e-130">3</span><span class="sxs-lookup"><span data-stu-id="7a67e-130">3</span></span>              | <span data-ttu-id="7a67e-131">A többféle eszközhöz és oldalarányhoz több képernyőméretet támogató alapverzió</span><span class="sxs-lookup"><span data-stu-id="7a67e-131">The base version that supports multiple screen sizes for various devices and aspect ratios</span></span> |
| <span data-ttu-id="7a67e-132">3.1</span><span class="sxs-lookup"><span data-stu-id="7a67e-132">3.1</span></span>            | <span data-ttu-id="7a67e-133">Az alapverzió, amely további támogatást nyújt a **Javasolt termékek** panelhez</span><span class="sxs-lookup"><span data-stu-id="7a67e-133">The base version that has additional support for the **Recommended products** panel</span></span>        |

### <a name="persona"></a><span data-ttu-id="7a67e-134">Személyiség</span><span class="sxs-lookup"><span data-stu-id="7a67e-134">Persona</span></span>

| <span data-ttu-id="7a67e-135">Rövidítés</span><span class="sxs-lookup"><span data-stu-id="7a67e-135">Abbreviation</span></span> | <span data-ttu-id="7a67e-136">Személyiség</span><span class="sxs-lookup"><span data-stu-id="7a67e-136">Persona</span></span>       | <span data-ttu-id="7a67e-137">Tartalom</span><span class="sxs-lookup"><span data-stu-id="7a67e-137">Contents</span></span> |
|--------------|---------------|----------|
| <span data-ttu-id="7a67e-138">CSH</span><span class="sxs-lookup"><span data-stu-id="7a67e-138">CSH</span></span>          | <span data-ttu-id="7a67e-139">Pénztáros</span><span class="sxs-lookup"><span data-stu-id="7a67e-139">Cashier</span></span>       | <span data-ttu-id="7a67e-140">A pénztáros elrendezések minden tranzakciókkal kapcsolatos műveletet tartalmaznak, például a vevői rendeléseket, visszaküldéseket, engedmények, érvénytelenítéseket és ajándékutalványokat.</span><span class="sxs-lookup"><span data-stu-id="7a67e-140">Cashier layouts include all transaction-related operations, such as customer orders, returns, discounts, voids, and gift cards.</span></span> <span data-ttu-id="7a67e-141">Ezek az elrendezések a készletkezelés, például az árellenőrzés, a készletkeresések és leltározás napi feladatait is magukban foglalják.</span><span class="sxs-lookup"><span data-stu-id="7a67e-141">These layouts also include daily tasks for inventory management, such price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="7a67e-142">Alapvető műszakkezelés is rendelkezésre áll a következőkhöz: kezdő összegek, műszakok felfüggesztése és blokkolóóra.</span><span class="sxs-lookup"><span data-stu-id="7a67e-142">Basic shift management is also provided for start amounts, suspending shifts, and time clock.</span></span> |
| <span data-ttu-id="7a67e-143">MGR</span><span class="sxs-lookup"><span data-stu-id="7a67e-143">MGR</span></span>          | <span data-ttu-id="7a67e-144">Üzletvezető</span><span class="sxs-lookup"><span data-stu-id="7a67e-144">Store Manager</span></span> | <span data-ttu-id="7a67e-145">Az üzletvezető elrendezések minden tranzakciókkal kapcsolatos műveletet magukban foglalnak, amelyek a pénztáros elrendezésekben találhatók, és az adófelülírásokat is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="7a67e-145">Store Manager layouts include all transaction-related operations that are found in the Cashier layouts but also include tax overrides.</span></span> <span data-ttu-id="7a67e-146">Ezek az elrendezések a készletkezelés, például az árellenőrzés, a készletkeresések és leltározás napi feladatait is magukban foglalják.</span><span class="sxs-lookup"><span data-stu-id="7a67e-146">These layouts also include daily tasks for inventory management, such as price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="7a67e-147">Műszakkezelés is rendelkezésre áll a következőkhöz: indítás, felfüggesztés és a műszak lezárása.</span><span class="sxs-lookup"><span data-stu-id="7a67e-147">Shift management is provided for starting, suspending, and closing shifts.</span></span> <span data-ttu-id="7a67e-148">Ezenkívül az elrendezések a bejegyzések, eltávolítások, fizetőeszköz-elszámolások és széf és banki műveletek pénztárgépfiókkal kapcsolatos műveleteit is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="7a67e-148">Additionally, the layouts include drawer operations for entries, removals, tender declarations, and safe and bank drops.</span></span> <span data-ttu-id="7a67e-149">Végül ezek az elrendezések hozzáférést nyújtanak a teljesítményre vonatkozó jelentésekhez, és kinyomtathatóvá teszik az X és Z-jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="7a67e-149">Finally, these layouts include access to performance reports, and enable X and Z reports to be printed.</span></span> |
| <span data-ttu-id="7a67e-150">STK</span><span class="sxs-lookup"><span data-stu-id="7a67e-150">STK</span></span>          | <span data-ttu-id="7a67e-151">Készletadminisztrátor</span><span class="sxs-lookup"><span data-stu-id="7a67e-151">Stock Clerk</span></span>   | <span data-ttu-id="7a67e-152">A készletadminisztrátor elrendezések a készletkezelésre vannak optimalizálva.</span><span class="sxs-lookup"><span data-stu-id="7a67e-152">Stock Clerk layouts are optimized for inventory management.</span></span> <span data-ttu-id="7a67e-153">Tartalmazzák a napi feladatokhoz való hozzáférést az árellenőrzésekhez, a készletkeresésekhez, a kitároláshoz és a bevételezéshez, a leltározáshoz és csomagok szétszereléséhez.</span><span class="sxs-lookup"><span data-stu-id="7a67e-153">They include access to daily tasks for price checks, inventory lookups, picking and receiving, stock counts, and kit disassembly.</span></span> <span data-ttu-id="7a67e-154">Ezek az elrendezések alapvető műszakműveleteket is kínálnak a blokkolóórához és a műszakok felfüggesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="7a67e-154">These layouts also provide basic shift operations for time clock and suspending shifts.</span></span> <span data-ttu-id="7a67e-155">Annak ellenére, hogy ezeket az elrendezéseket elsősorban háttérirodai feladatokra szánják, a készletadminisztrátorok ugyanazokat a műveleteket hajthatják végre, mint a pénztárosok a tranzakció képernyők esetében.</span><span class="sxs-lookup"><span data-stu-id="7a67e-155">Although these layouts are intended mainly for back-office tasks, stock clerks have the same operations as cashiers for transaction screens.</span></span> |

### <a name="example-layout"></a><span data-ttu-id="7a67e-156">Példa elrendezés</span><span class="sxs-lookup"><span data-stu-id="7a67e-156">Example layout</span></span>

<span data-ttu-id="7a67e-157">Íme egy példa, a Gyár vállalat képernyőelrendezés-azonosítója, 3-as elrendezésverzió, az üzletvezető személyiséggel:</span><span class="sxs-lookup"><span data-stu-id="7a67e-157">Here is an example of a screen layout ID for the Fabrikam company, layout version 3, and the Store Manager persona:</span></span>

<span data-ttu-id="7a67e-158">F3MGR</span><span class="sxs-lookup"><span data-stu-id="7a67e-158">F3MGR</span></span>

<span data-ttu-id="7a67e-159">A következő ábrán a Gyár üzletvezetőjének üdvözlőképernyője látható.</span><span class="sxs-lookup"><span data-stu-id="7a67e-159">The following illustration shows an example of the Welcome screen for a Fabrikam store manager.</span></span>

![A Gyár üzletvezetőjének üdvözlőképernyője](../commerce/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a><span data-ttu-id="7a67e-161">Elrendezési méretek</span><span class="sxs-lookup"><span data-stu-id="7a67e-161">Layout sizes</span></span>

### <a name="full-vs-compact-layouts"></a><span data-ttu-id="7a67e-162">Teljes és kompakt elrendezések összehasonlítása</span><span class="sxs-lookup"><span data-stu-id="7a67e-162">Full vs. compact layouts</span></span>

<span data-ttu-id="7a67e-163">A képernyő-elrendezés konfigurációkat tartalmazhat a teljes és kompakt eszközök számára.</span><span class="sxs-lookup"><span data-stu-id="7a67e-163">A screen layout can have configurations for both full devices and compact devices.</span></span> <span data-ttu-id="7a67e-164">Ezért a felhasználó hozzárendelhető egyetlen képernyő-elrendezéshez, amely a különböző méretek és formátumok mindegyikén működik az üzletben.</span><span class="sxs-lookup"><span data-stu-id="7a67e-164">Therefore, a user can be assigned to a single screen layout that will work across various sizes and form factors in the store.</span></span>

- <span data-ttu-id="7a67e-165">**Modern POS - teljes** - A teljes elrendezések általában a nagyobb kijelzők esetén használhatók a legjobban, például az asztaliszámítógép-monitorokon vagy a táblagépeken.</span><span class="sxs-lookup"><span data-stu-id="7a67e-165">**Modern POS - Full** – Typically, full layouts are best used for larger displays, such as desktop computer monitors or tablets.</span></span> <span data-ttu-id="7a67e-166">A felhasználók kiválaszthatják a felhasználóifelület-elemeket, amelyeket az elrendezés tartalmaz, megadhatják az elemek méretét és elhelyezését, és konfigurálhatják a részletes tulajdonságaikat.</span><span class="sxs-lookup"><span data-stu-id="7a67e-166">Users can select the UI elements that the layout includes, specify the size and placement of those elements, and configure their detailed properties.</span></span> <span data-ttu-id="7a67e-167">A teljes elrendezések az álló és a fekvő konfigurációkat egyaránt támogatják.</span><span class="sxs-lookup"><span data-stu-id="7a67e-167">Full layouts support both portrait and landscape configurations.</span></span>
- <span data-ttu-id="7a67e-168">**Modern POS – kompakt** - A kompakt elrendezések általában a telefonokhoz és kis táblagépekhez használhatók a legjobban.</span><span class="sxs-lookup"><span data-stu-id="7a67e-168">**Modern POS - Compact** – Typically, compact layouts are best used for phones or small tablets.</span></span> <span data-ttu-id="7a67e-169">A tervezési lehetőségek korlátozottak a kompakt eszközök esetében.</span><span class="sxs-lookup"><span data-stu-id="7a67e-169">Design possibilities are limited for compact devices.</span></span> <span data-ttu-id="7a67e-170">A felhasználók beállíthatják az oszlopokat és a mezőket a bevételezés és az összegek panelekhez.</span><span class="sxs-lookup"><span data-stu-id="7a67e-170">Users can configure the columns and fields for the receipt pane and the totals pane.</span></span>

### <a name="screen-resolutions-that-are-provided"></a><span data-ttu-id="7a67e-171">A biztosított képernyőfelbontások</span><span class="sxs-lookup"><span data-stu-id="7a67e-171">Screen resolutions that are provided</span></span>

<span data-ttu-id="7a67e-172">Az alábbi táblázat bemutatja a jellemző képernyőfelbontásokhoz rendelkezésre bocsájtott elrendezésméreteket.</span><span class="sxs-lookup"><span data-stu-id="7a67e-172">The following table shows the layout sizes that are provided for typical screen resolutions.</span></span>

| <span data-ttu-id="7a67e-173">Elrendezés típusa</span><span class="sxs-lookup"><span data-stu-id="7a67e-173">Layout type</span></span> | <span data-ttu-id="7a67e-174">Feloldás</span><span class="sxs-lookup"><span data-stu-id="7a67e-174">Resolution</span></span> | <span data-ttu-id="7a67e-175">Képarány</span><span class="sxs-lookup"><span data-stu-id="7a67e-175">Aspect ratio</span></span> | <span data-ttu-id="7a67e-176">Cél kijelző</span><span class="sxs-lookup"><span data-stu-id="7a67e-176">Target display</span></span>          |
|-------------|------------|--------------|-------------------------|
| <span data-ttu-id="7a67e-177">Tömörítés\*</span><span class="sxs-lookup"><span data-stu-id="7a67e-177">Compact\*</span></span>   | <span data-ttu-id="7a67e-178">480 × 853</span><span class="sxs-lookup"><span data-stu-id="7a67e-178">480 × 853</span></span>  | <span data-ttu-id="7a67e-179">16:9</span><span class="sxs-lookup"><span data-stu-id="7a67e-179">16:9</span></span>         | <span data-ttu-id="7a67e-180">Telefonok</span><span class="sxs-lookup"><span data-stu-id="7a67e-180">Phones</span></span>                  |
| <span data-ttu-id="7a67e-181">Teljes</span><span class="sxs-lookup"><span data-stu-id="7a67e-181">Full</span></span>        | <span data-ttu-id="7a67e-182">1024 × 768</span><span class="sxs-lookup"><span data-stu-id="7a67e-182">1024 × 768</span></span> | <span data-ttu-id="7a67e-183">4:3</span><span class="sxs-lookup"><span data-stu-id="7a67e-183">4:3</span></span>          | <span data-ttu-id="7a67e-184">Táblagépek</span><span class="sxs-lookup"><span data-stu-id="7a67e-184">Tablets</span></span>                 |
| <span data-ttu-id="7a67e-185">Teljes\*</span><span class="sxs-lookup"><span data-stu-id="7a67e-185">Full\*</span></span>      | <span data-ttu-id="7a67e-186">1280 × 720</span><span class="sxs-lookup"><span data-stu-id="7a67e-186">1280 × 720</span></span> | <span data-ttu-id="7a67e-187">16:9</span><span class="sxs-lookup"><span data-stu-id="7a67e-187">16:9</span></span>         | <span data-ttu-id="7a67e-188">Táblagépek</span><span class="sxs-lookup"><span data-stu-id="7a67e-188">Tablets</span></span>                 |
| <span data-ttu-id="7a67e-189">Teljes</span><span class="sxs-lookup"><span data-stu-id="7a67e-189">Full</span></span>        | <span data-ttu-id="7a67e-190">1366 × 768</span><span class="sxs-lookup"><span data-stu-id="7a67e-190">1366 × 768</span></span> | <span data-ttu-id="7a67e-191">16:9</span><span class="sxs-lookup"><span data-stu-id="7a67e-191">16:9</span></span>         | <span data-ttu-id="7a67e-192">Táblagépek, nagyobb képernyők</span><span class="sxs-lookup"><span data-stu-id="7a67e-192">Tablets, larger screens</span></span> |
| <span data-ttu-id="7a67e-193">Teljes</span><span class="sxs-lookup"><span data-stu-id="7a67e-193">Full</span></span>        | <span data-ttu-id="7a67e-194">1440 × 960</span><span class="sxs-lookup"><span data-stu-id="7a67e-194">1440 × 960</span></span> | <span data-ttu-id="7a67e-195">3:2</span><span class="sxs-lookup"><span data-stu-id="7a67e-195">3:2</span></span>          | <span data-ttu-id="7a67e-196">Táblagépek, nagyobb képernyők</span><span class="sxs-lookup"><span data-stu-id="7a67e-196">Tablets, larger screens</span></span> |

<span data-ttu-id="7a67e-197">\*Ezek a további elrendezési méretek csak a Kalandorbolt és a Gyár elrendezésekben érhetők el.</span><span class="sxs-lookup"><span data-stu-id="7a67e-197">\* These additional layout sizes are available only in Adventure Works and Fabrikam layouts.</span></span>

> [!TIP]
> <span data-ttu-id="7a67e-198">A pénztár automatikusan kiválasztja az elrendezésméreteket, az aktuális alkalmazásablak képernyőfelbontásához elérhető legközelebbi méret alapján.</span><span class="sxs-lookup"><span data-stu-id="7a67e-198">POS automatically selects layout sizes, based on the closest size that is available for the screen resolution of the current app window.</span></span> <span data-ttu-id="7a67e-199">A jelenleg használt képernyőelrendezés-azonosító és elrendezésfelbontás megkereséséhez a Modern POS (MPOS) vagy Retail Cloud POS (CPOS) esetében nyissa meg a **Beállítások** oldalt, majd tekintse meg a **Munkamenet adatai** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7a67e-199">To find the screen layout ID and layout resolution that are currently used, in Modern POS (MPOS) or Retail Cloud POS (CPOS), open the **Settings** page, and look in the **Session information** section.</span></span> <span data-ttu-id="7a67e-200">A jelenlegi alkalmazás vagy böngészőkeret tényleges ablakfelbontása is megtekinthető.</span><span class="sxs-lookup"><span data-stu-id="7a67e-200">You can also see the actual window resolution for your current application or browser frame.</span></span> <span data-ttu-id="7a67e-201">Ezeket az adatokat begyűjtve az elrendezéstartalom forrásának megkereséséhez menjen a **Csatorna beállítása** \> **POS beállítása** \> **POS** \> **Képernyő-elrendezések** menübe.</span><span class="sxs-lookup"><span data-stu-id="7a67e-201">After you have this information, you can find the source of the layout content by going to **Channel setup** \> **POS setup** \> **POS** \> **Screen layouts**.</span></span>

![Képernyő-elrendezések és elrendezésfelbontások/méretek a Commerce és a POS esetében](../commerce/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a><span data-ttu-id="7a67e-203">Vállalatok és márkák</span><span class="sxs-lookup"><span data-stu-id="7a67e-203">Companies and brands</span></span>

<span data-ttu-id="7a67e-204">Minden fiktív vállalat eltérő kiskereskedelmi szegmenst céloz, és termékkatalógusokat tartalmaz, amelyet a vállalat piacához vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="7a67e-204">Each fictitious company is targeted to a different retail segment and includes product catalogs that are tuned for the company's market.</span></span> <span data-ttu-id="7a67e-205">Minden vállalat rendelkezik egy egyedi vizuális márkával, amely a termékeire jellemző.</span><span class="sxs-lookup"><span data-stu-id="7a67e-205">Each company has a unique visual brand that accompanies its products.</span></span> <span data-ttu-id="7a67e-206">A kiemelés színe, a sötét és a világos téma és a reális tapasztalatokat biztosító fényképek a márkaelemek közé tartoznak.</span><span class="sxs-lookup"><span data-stu-id="7a67e-206">Branding elements include the accent color, dark or light theme, and accompanying photographs that provide realistic experiences.</span></span>

### <a name="company-segment-and-visual-characteristics"></a><span data-ttu-id="7a67e-207">Vállalati szegmens és vizuális jellemzők</span><span class="sxs-lookup"><span data-stu-id="7a67e-207">Company segment and visual characteristics</span></span>

| <span data-ttu-id="7a67e-208">Cég</span><span class="sxs-lookup"><span data-stu-id="7a67e-208">Company</span></span>         | <span data-ttu-id="7a67e-209">Tárolóhely</span><span class="sxs-lookup"><span data-stu-id="7a67e-209">Location</span></span> | <span data-ttu-id="7a67e-210">Szegmens</span><span class="sxs-lookup"><span data-stu-id="7a67e-210">Segment</span></span>        | <span data-ttu-id="7a67e-211">Kiemelés</span><span class="sxs-lookup"><span data-stu-id="7a67e-211">Accent</span></span> | <span data-ttu-id="7a67e-212">Téma</span><span class="sxs-lookup"><span data-stu-id="7a67e-212">Theme</span></span> |
|-----------------|----------|----------------|--------|-------|
| <span data-ttu-id="7a67e-213">Kalandorbolt</span><span class="sxs-lookup"><span data-stu-id="7a67e-213">Adventure Works</span></span> | <span data-ttu-id="7a67e-214">Seattle</span><span class="sxs-lookup"><span data-stu-id="7a67e-214">Seattle</span></span>  | <span data-ttu-id="7a67e-215">Sportcikkek</span><span class="sxs-lookup"><span data-stu-id="7a67e-215">Sporting Goods</span></span> | <span data-ttu-id="7a67e-216">Kék</span><span class="sxs-lookup"><span data-stu-id="7a67e-216">Blue</span></span>   | <span data-ttu-id="7a67e-217">Sötét</span><span class="sxs-lookup"><span data-stu-id="7a67e-217">Dark</span></span>  |
| <span data-ttu-id="7a67e-218">Gyár</span><span class="sxs-lookup"><span data-stu-id="7a67e-218">Fabrikam</span></span>        | <span data-ttu-id="7a67e-219">Houston</span><span class="sxs-lookup"><span data-stu-id="7a67e-219">Houston</span></span>  | <span data-ttu-id="7a67e-220">Divatáru</span><span class="sxs-lookup"><span data-stu-id="7a67e-220">Fashion</span></span>        | <span data-ttu-id="7a67e-221">Zöld</span><span class="sxs-lookup"><span data-stu-id="7a67e-221">Green</span></span>  | <span data-ttu-id="7a67e-222">Világos</span><span class="sxs-lookup"><span data-stu-id="7a67e-222">Light</span></span> |
| <span data-ttu-id="7a67e-223">Contoso</span><span class="sxs-lookup"><span data-stu-id="7a67e-223">Contoso</span></span>         | <span data-ttu-id="7a67e-224">Boston</span><span class="sxs-lookup"><span data-stu-id="7a67e-224">Boston</span></span>   | <span data-ttu-id="7a67e-225">Elektronika</span><span class="sxs-lookup"><span data-stu-id="7a67e-225">Electronics</span></span>    | <span data-ttu-id="7a67e-226">Piros</span><span class="sxs-lookup"><span data-stu-id="7a67e-226">Red</span></span>    | <span data-ttu-id="7a67e-227">Sötét</span><span class="sxs-lookup"><span data-stu-id="7a67e-227">Dark</span></span>  |

> [!NOTE]
> <span data-ttu-id="7a67e-228">A két főmárka a Kalandorbolt és a Gyár.</span><span class="sxs-lookup"><span data-stu-id="7a67e-228">Adventure Works and Fabrikam are the two flagship brands.</span></span> <span data-ttu-id="7a67e-229">A Contoso elérhető, de nem minden elrendezés áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="7a67e-229">Contoso is available, but not all layouts have been provided.</span></span>

<span data-ttu-id="7a67e-230">Az alábbi ábrákon a három fiktív vállalat üdvözlőoldalára és tranzakciós lapjára láthatók példák.</span><span class="sxs-lookup"><span data-stu-id="7a67e-230">The following illustrations show examples of the welcome page and transaction page for the three fictitious companies.</span></span>

### <a name="adventure-works"></a><span data-ttu-id="7a67e-231">Kalandorbolt</span><span class="sxs-lookup"><span data-stu-id="7a67e-231">Adventure Works</span></span>

![Bemutató adatok – a Kalandorbolt üdvözlőoldala](../commerce/media/demo-screen-layouts-fig-4-1a.png)

![Bemutató adatok – a Kalandorbolt tranzakciós lapja](../commerce/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a><span data-ttu-id="7a67e-234">Gyár</span><span class="sxs-lookup"><span data-stu-id="7a67e-234">Fabrikam</span></span>

![Bemutató adatok – a Gyár üdvözlőoldala](../commerce/media/demo-screen-layouts-fig-4-2a.png)

![Bemutató adatok – a Gyár tranzakciós lapja](../commerce/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a><span data-ttu-id="7a67e-237">Contoso</span><span class="sxs-lookup"><span data-stu-id="7a67e-237">Contoso</span></span>

![Bemutató adatok – Contoso elrendezések](../commerce/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a><span data-ttu-id="7a67e-239">Felhasználói bejelentkezési mátrix</span><span class="sxs-lookup"><span data-stu-id="7a67e-239">User sign in matrix</span></span>

<span data-ttu-id="7a67e-240">A különböző képernyő-elrendezésekhez felhasználókat is rendelkezésre bocsájtunk.</span><span class="sxs-lookup"><span data-stu-id="7a67e-240">Users have been provided for the various screen layouts.</span></span> <span data-ttu-id="7a67e-241">Az alábbi táblázat használatával hozzáférhet a képernyők bármelyikéhez.</span><span class="sxs-lookup"><span data-stu-id="7a67e-241">By using the following table, you should be able to access any of the screens.</span></span> <span data-ttu-id="7a67e-242">Csak jelentkezzen be egy megfelelő operátorazonosítóval.</span><span class="sxs-lookup"><span data-stu-id="7a67e-242">Just sign in by using an appropriate operator ID.</span></span>

| <span data-ttu-id="7a67e-243">Cég</span><span class="sxs-lookup"><span data-stu-id="7a67e-243">Company</span></span>         | <span data-ttu-id="7a67e-244">Képernyő-elrendezés azonosítója</span><span class="sxs-lookup"><span data-stu-id="7a67e-244">Screen layout ID</span></span> | <span data-ttu-id="7a67e-245">Személyiség</span><span class="sxs-lookup"><span data-stu-id="7a67e-245">Persona</span></span>       | <span data-ttu-id="7a67e-246">Operátorazonosító</span><span class="sxs-lookup"><span data-stu-id="7a67e-246">Operator IDs</span></span>           |
|-----------------|------------------|---------------|------------------------|
| <span data-ttu-id="7a67e-247">Kalandorbolt</span><span class="sxs-lookup"><span data-stu-id="7a67e-247">Adventure Works</span></span> | <span data-ttu-id="7a67e-248">A3MGR</span><span class="sxs-lookup"><span data-stu-id="7a67e-248">A3MGR</span></span>            | <span data-ttu-id="7a67e-249">Üzletvezető</span><span class="sxs-lookup"><span data-stu-id="7a67e-249">Store Manager</span></span> | <span data-ttu-id="7a67e-250">000154, 000137, 000073</span><span class="sxs-lookup"><span data-stu-id="7a67e-250">000154, 000137, 000073</span></span> |
| <span data-ttu-id="7a67e-251">Kalandorbolt</span><span class="sxs-lookup"><span data-stu-id="7a67e-251">Adventure Works</span></span> | <span data-ttu-id="7a67e-252">A3CSH</span><span class="sxs-lookup"><span data-stu-id="7a67e-252">A3CSH</span></span>            | <span data-ttu-id="7a67e-253">Pénztáros</span><span class="sxs-lookup"><span data-stu-id="7a67e-253">Cashier</span></span>       | <span data-ttu-id="7a67e-254">000150, 000175, 000165</span><span class="sxs-lookup"><span data-stu-id="7a67e-254">000150, 000175, 000165</span></span> |
| <span data-ttu-id="7a67e-255">Kalandorbolt</span><span class="sxs-lookup"><span data-stu-id="7a67e-255">Adventure Works</span></span> | <span data-ttu-id="7a67e-256">A3STK</span><span class="sxs-lookup"><span data-stu-id="7a67e-256">A3STK</span></span>            | <span data-ttu-id="7a67e-257">Készletadminisztrátor</span><span class="sxs-lookup"><span data-stu-id="7a67e-257">Stock Clerk</span></span>   | <span data-ttu-id="7a67e-258">000155, 000181, 000152</span><span class="sxs-lookup"><span data-stu-id="7a67e-258">000155, 000181, 000152</span></span> |
| <span data-ttu-id="7a67e-259">Gyár</span><span class="sxs-lookup"><span data-stu-id="7a67e-259">Fabrikam</span></span>        | <span data-ttu-id="7a67e-260">F3MGR</span><span class="sxs-lookup"><span data-stu-id="7a67e-260">F3MGR</span></span>            | <span data-ttu-id="7a67e-261">Üzletvezető</span><span class="sxs-lookup"><span data-stu-id="7a67e-261">Store Manager</span></span> | <span data-ttu-id="7a67e-262">000160, 000168, 000163</span><span class="sxs-lookup"><span data-stu-id="7a67e-262">000160, 000168, 000163</span></span> |
| <span data-ttu-id="7a67e-263">Gyár</span><span class="sxs-lookup"><span data-stu-id="7a67e-263">Fabrikam</span></span>        | <span data-ttu-id="7a67e-264">F3CSH</span><span class="sxs-lookup"><span data-stu-id="7a67e-264">F3CSH</span></span>            | <span data-ttu-id="7a67e-265">Pénztáros</span><span class="sxs-lookup"><span data-stu-id="7a67e-265">Cashier</span></span>       | <span data-ttu-id="7a67e-266">000161, 000113, 000114</span><span class="sxs-lookup"><span data-stu-id="7a67e-266">000161, 000113, 000114</span></span> |
| <span data-ttu-id="7a67e-267">Gyár</span><span class="sxs-lookup"><span data-stu-id="7a67e-267">Fabrikam</span></span>        | <span data-ttu-id="7a67e-268">F3STK</span><span class="sxs-lookup"><span data-stu-id="7a67e-268">F3STK</span></span>            | <span data-ttu-id="7a67e-269">Készletadminisztrátor</span><span class="sxs-lookup"><span data-stu-id="7a67e-269">Stock Clerk</span></span>   | <span data-ttu-id="7a67e-270">000164, 000112, 000123</span><span class="sxs-lookup"><span data-stu-id="7a67e-270">000164, 000112, 000123</span></span> |
| <span data-ttu-id="7a67e-271">Contoso</span><span class="sxs-lookup"><span data-stu-id="7a67e-271">Contoso</span></span>         | <span data-ttu-id="7a67e-272">C3MGR</span><span class="sxs-lookup"><span data-stu-id="7a67e-272">C3MGR</span></span>            | <span data-ttu-id="7a67e-273">Üzletvezető</span><span class="sxs-lookup"><span data-stu-id="7a67e-273">Store Manager</span></span> | <span data-ttu-id="7a67e-274">000100, 000111</span><span class="sxs-lookup"><span data-stu-id="7a67e-274">000100, 000111</span></span>         |
| <span data-ttu-id="7a67e-275">Contoso</span><span class="sxs-lookup"><span data-stu-id="7a67e-275">Contoso</span></span>         | <span data-ttu-id="7a67e-276">C3CSH</span><span class="sxs-lookup"><span data-stu-id="7a67e-276">C3CSH</span></span>            | <span data-ttu-id="7a67e-277">Pénztáros</span><span class="sxs-lookup"><span data-stu-id="7a67e-277">Cashier</span></span>       | <span data-ttu-id="7a67e-278">000110, 000120</span><span class="sxs-lookup"><span data-stu-id="7a67e-278">000110, 000120</span></span>         |
| <span data-ttu-id="7a67e-279">Contoso</span><span class="sxs-lookup"><span data-stu-id="7a67e-279">Contoso</span></span>         | <span data-ttu-id="7a67e-280">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="7a67e-280">Not applicable</span></span>   | <span data-ttu-id="7a67e-281">Készletadminisztrátor</span><span class="sxs-lookup"><span data-stu-id="7a67e-281">Stock Clerk</span></span>   | <span data-ttu-id="7a67e-282">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="7a67e-282">Not applicable</span></span>         |

> [!TIP]
> <span data-ttu-id="7a67e-283">A legjobb eredmények érdekében aktiváljon a megfelelő üzletben egy pénztárgépet, és a vállalatot annak a személyiségnek a vállalatára állítsa, amellyel be kíván jelentkezni.</span><span class="sxs-lookup"><span data-stu-id="7a67e-283">For best results, activate a register in the corresponding store location, and set the company to the company of the persona that you plan to use when you sign in.</span></span> <span data-ttu-id="7a67e-284">Ezzel a módszerrel segíthet garantálni, hogy vizuális profil és a márkázás egységes legyen a tapasztalat egészében.</span><span class="sxs-lookup"><span data-stu-id="7a67e-284">In this way, you help guarantee that the visual profile and branding images are aligned across the experience.</span></span> <span data-ttu-id="7a67e-285">Például ha a pénztárosi elrendezést szeretné kipróbálni a Gyár esetében, aktiválnia kell egy pénztárgépet a houstoni üzletben.</span><span class="sxs-lookup"><span data-stu-id="7a67e-285">For example, if you're interested in seeing a Fabrikam layout for a cashier, you should activate a register in the Houston store.</span></span>

<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail and Commerce \> Channel setup \> POS setup \> POS \> Images**. -->

<!-- ![Images in Dynamics 365 Commerce](../commerce/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../commerce/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->
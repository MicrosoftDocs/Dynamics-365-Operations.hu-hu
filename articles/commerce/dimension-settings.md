---
title: Megjelenítési beállítások alkalmazása termékdimenziókra
description: Ez a témakör a termékdimenziókra vonatkozó megjelenítési beállításokat ismerteti, és áttekinti a Microsoft Dynamics 365 Commerce történő használatukat.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117227"
---
# <a name="apply-display-settings-for-product-dimensions"></a><span data-ttu-id="b33a3-103">Megjelenítési beállítások alkalmazása termékdimenziókra</span><span class="sxs-lookup"><span data-stu-id="b33a3-103">Apply display settings for product dimensions</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="b33a3-104">Ez a témakör a termékdimenziókra vonatkozó megjelenítési beállításokat ismerteti, és áttekinti a Microsoft Dynamics 365 Commerce történő használatukat.</span><span class="sxs-lookup"><span data-stu-id="b33a3-104">This topic covers the display settings for product dimensions and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b33a3-105">A Dynamics 365 Commerce támogatja a termékváltozatok megkülönböztetésére szolgáló méret-, stílus- és színdimenziókat.</span><span class="sxs-lookup"><span data-stu-id="b33a3-105">Dynamics 365 Commerce supports size, style, and color dimensions to distinguish product variants.</span></span> <span data-ttu-id="b33a3-106">A dimenziók jellemzően szöveges értékként jelennek meg (például méretek esetén „Kicsi”, „Közepes” vagy „Nagy”; vagy színek esetén „Fekete” vagy „Barna”).</span><span class="sxs-lookup"><span data-stu-id="b33a3-106">Dimensions are typically shown as text values, such as "Small," "Medium," and "Large" for sizes, and "Black" and "Brown" for colors.</span></span> <span data-ttu-id="b33a3-107">Ha viszont egy termék számos változatot támogat, akkor nehéz lehet tallózással megkeresni a termékváltozatokat, mivel az egyes változatok képének megtekintéséhez több beállításra van szükség.</span><span class="sxs-lookup"><span data-stu-id="b33a3-107">However, if a product supports many variations, it can be difficult to browse product variants, because multiple selections are required to view the image for each variant.</span></span> <span data-ttu-id="b33a3-108">A termékváltozatok közötti tallózás megkönnyítése érdekében a Commerce 10.0.20-as kiadása képek és hexadecimális (hex) kódok használatával, palettaként jeleníti meg a dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="b33a3-108">To make it easier to browse product variants, the version 10.0.20 release of Commerce can use images and hexadecimal (hex) codes to show dimensions as swatches.</span></span>

<span data-ttu-id="b33a3-109">A Commerce webhelykészítőjében a dimenzióbeállítások a **Webhelybeállítások \> Bővítmények \> Dimenzióbeállítások** részen adhatók meg.</span><span class="sxs-lookup"><span data-stu-id="b33a3-109">In Commerce site builder, dimension settings are defined at **Site Settings \> Extensions \> Dimension Settings**.</span></span> <span data-ttu-id="b33a3-110">Az alábbi ábra a webhelyszerkesztőn belüli dimenzióbeállításokra ad példát.</span><span class="sxs-lookup"><span data-stu-id="b33a3-110">The following illustration shows an example of dimension settings in site builder.</span></span>

![Példa a Commerce webhelyszerkesztőjének webhelybeállításaira](./dev-itpro/media/swatch_site_settings.PNG)

<span data-ttu-id="b33a3-112">Két dimenzióbeállítás használható:</span><span class="sxs-lookup"><span data-stu-id="b33a3-112">Two dimension settings are available:</span></span>

- <span data-ttu-id="b33a3-113">**Dimenziók megjelenítése képként** – adja meg, hogy melyik dimenziók jelenjenek meg palettaként az e-kereskedelmi webhelyek oldalain, például a termékek részleteit tartalmazó oldalakon (PDP) vagy a keresési eredmények listaoldalán.</span><span class="sxs-lookup"><span data-stu-id="b33a3-113">**Dimensions to display as image** – Specify which dimensions should appear as swatches on e-commerce site pages such as product details pages (PDPs) and search result list pages.</span></span> <span data-ttu-id="b33a3-114">A szín-, a méret- és a stílusdimenziók bármely kombinációja megjeleníthető palettaként.</span><span class="sxs-lookup"><span data-stu-id="b33a3-114">Any combination of color, size, and style dimensions can be shown as a swatch.</span></span> <span data-ttu-id="b33a3-115">Ha egy dimenziót kiválaszt palettaként való megjelenítésre, a Commerce-modul renderelése megkeresi a hecadecimális kódú paletta megfelelő konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="b33a3-115">If a dimension is selected for display as a swatch, Commerce module rendering will look for an available configuration of a hex code swatch.</span></span> <span data-ttu-id="b33a3-116">Ha nincs konfigurálva hexadecimális kód, a rendszerlogika egy kép-URL palettájának konfigurációját fogja keresni.</span><span class="sxs-lookup"><span data-stu-id="b33a3-116">If no hex code is configured, system logic will look for a configuration of an image URL swatch.</span></span> <span data-ttu-id="b33a3-117">Ha sem hexadecimális kód, sem kép-URL nincs konfigurálva, akkor szöveg jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b33a3-117">If neither a hex code nor an image URL is configured, text will be shown.</span></span>

    <span data-ttu-id="b33a3-118">Az alábbi képen olyan példa látható, ahol egy e-kereskedelmi webhelyen PDP szín- és méretpaletták vannak.</span><span class="sxs-lookup"><span data-stu-id="b33a3-118">The following illustration shows an example where a PDP on an e-commerce site includes color and size swatches.</span></span> <span data-ttu-id="b33a3-119">Ebben a példában a szín dimenzióhoz egy hexadecimális kód van beállítva.</span><span class="sxs-lookup"><span data-stu-id="b33a3-119">In this example, a hex code is configured for the color dimension.</span></span> <span data-ttu-id="b33a3-120">Ennek megfelelően a paletták színekként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="b33a3-120">Therefore, swatches are shown as colors.</span></span> <span data-ttu-id="b33a3-121">A méret dimenzióhoz viszont sem hexadecimális kód, sem kép-URL nincs beállítva.</span><span class="sxs-lookup"><span data-stu-id="b33a3-121">However, neither a hex code nor an image URL is configured for the size dimension.</span></span> <span data-ttu-id="b33a3-122">Ebből következően szöveg jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b33a3-122">Therefore, text is shown.</span></span>

    ![Példa, amelyben egy termék részleteit tartalmazó e-kereskedelmi oldalon palettaként jelenik meg a színdimenzió](./dev-itpro/media/swatch_pdp.png)

- <span data-ttu-id="b33a3-124">**Termékkártyán megjelenítendő dimenziók** – adja meg, hogy melyik dimenziók jelenjenek meg a listákban és a listaoldalakon megjelenő termékkártyákban.</span><span class="sxs-lookup"><span data-stu-id="b33a3-124">**Dimensions to display in product card** – Specify which dimensions should appear on product cards that are shown in lists and on list pages.</span></span> <span data-ttu-id="b33a3-125">Egy termékkártyán csak akkor jelenhet meg egy dimenzió, ha ezt a beállítást engedélyezi az adott dimenziónál.</span><span class="sxs-lookup"><span data-stu-id="b33a3-125">Before a dimension can appear on a product card, this setting must be enabled for that dimension.</span></span> <span data-ttu-id="b33a3-126">A **Dimenziók megjelenítése képként** beállítást is engedélyezni kell.</span><span class="sxs-lookup"><span data-stu-id="b33a3-126">The **Dimensions to display as image** setting should also be enabled.</span></span> <span data-ttu-id="b33a3-127">A paletta termékkártyákon való kiválasztására szolgáló viselkedés a színdimenzióra van optimalizálva.</span><span class="sxs-lookup"><span data-stu-id="b33a3-127">The swatch selection behavior on product cards is optimized for the color dimension.</span></span> <span data-ttu-id="b33a3-128">Más dimenziók esetén szükség lehet egy nézetbővítményre a palettakiválasztási viselkedés testreszabásához.</span><span class="sxs-lookup"><span data-stu-id="b33a3-128">For other dimensions, a view extension might be required to customize swatch selection behavior.</span></span>

    <span data-ttu-id="b33a3-129">A következő ábrán lévő példán egy e-kereskedelmi webhely listaoldalán színpalettákat tartalmazó termékkártyák vannak.</span><span class="sxs-lookup"><span data-stu-id="b33a3-129">The following illustration shows an example where a list page on an e-commerce site contains product cards that include color swatches.</span></span>

    ![Példa, amelyben egy e-kereskedelmi listaoldalon palettaként jelenik meg a színdimenzió](./dev-itpro/media/swatch_searchresults.PNG)

<span data-ttu-id="b33a3-131">További információ arról, hogyan állítható be, hogy a termékdimenziók palettaként jelenjenek meg a webhely oldalain: [Termékdimenzió értékeinek konfigurálása palettaként való megjelenítésre](./dev-itpro/dimensions-swatch.md).</span><span class="sxs-lookup"><span data-stu-id="b33a3-131">For information about how to configure product dimensions so that they are shown as swatches on site pages, see [Configure product dimension values to appear as swatches](./dev-itpro/dimensions-swatch.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b33a3-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b33a3-132">Additional resources</span></span>

[<span data-ttu-id="b33a3-133">Modultár áttekintése</span><span class="sxs-lookup"><span data-stu-id="b33a3-133">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b33a3-134">Keresési eredmények modul</span><span class="sxs-lookup"><span data-stu-id="b33a3-134">Search results module</span></span>](search-result-module.md)

[<span data-ttu-id="b33a3-135">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="b33a3-135">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b33a3-136">Termékdimenzió értékeinek konfigurálása palettaként való megjelenítésre</span><span class="sxs-lookup"><span data-stu-id="b33a3-136">Configure product dimension values to appear as swatches</span></span>](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

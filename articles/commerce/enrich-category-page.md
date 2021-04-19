---
title: Kategória céloldalának gazdagítása
description: Ez a témakör a kategória oldalainak bővítésével foglalkozik Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5e18439fc0e91619cade33b83b87be0d5c4d1040
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799011"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="28daa-103">Kategória céloldalának bővítése</span><span class="sxs-lookup"><span data-stu-id="28daa-103">Enrich a category landing page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="28daa-104">Ez a témakör a kategória oldalainak bővítésével foglalkozik Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="28daa-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="28daa-105">A Commerce egy alapértelmezett kategória-nyitólapot biztosít, amely a kategóriaadatok megjelenítésekor kerül felhasználásra.</span><span class="sxs-lookup"><span data-stu-id="28daa-105">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="28daa-106">Az alapértelmezett kategórialap tartalmazza a szükséges elemeket, például a finomítókat, a kategorizált termékelhelyezést, a rendezési beállításokat, a választási lehetőségek összesítését és a laptördelési vezérlőelemeket.</span><span class="sxs-lookup"><span data-stu-id="28daa-106">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="28daa-107">Az alapértelmezett kategórialap használata helyett előfordulhat, hogy olyan „bővített” kategória-nyitólapot szeretne használni, amely több tartalmat és konkrétabb elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="28daa-107">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="28daa-108">A jellemző bővítéshez szükség lehet a kategória-specifikus marketinganyagok kategóriaoldalhoz.</span><span class="sxs-lookup"><span data-stu-id="28daa-108">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="28daa-109">Ez a tartalom több keresztértékesítési célú keresztkategóriás termékelhelyezést, szerkesztői listákat, képeket, videókat és egyéb szöveget tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="28daa-109">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="28daa-110">Vagy módosíthatja az alapértelmezett kategórialap, vagy meghatározható egy másik kategórialap egy adott kategóriához.</span><span class="sxs-lookup"><span data-stu-id="28daa-110">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Bővített kategória-céloldal](./media/CategoryLandingPages.png)

<span data-ttu-id="28daa-112">A Commerce webhelykészítőben a **Termékrk** lap a webhelyhez társított csatorna kategóriáinak listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="28daa-112">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="28daa-113">Ha a **Bővített** állapot van kiválasztva egy kategórialap számára, akkor a kategórialap bővített.</span><span class="sxs-lookup"><span data-stu-id="28daa-113">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="28daa-114">Ellenkező esetben az alapértelmezett kategórialap és tartalom kerül felhasználásra a kategóriához.</span><span class="sxs-lookup"><span data-stu-id="28daa-114">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="28daa-115">A kategória nevére kattintva megtekintheti a kategória bővített és nem bővített kategórialapjait.</span><span class="sxs-lookup"><span data-stu-id="28daa-115">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="28daa-116">A kategórialap bővítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="28daa-116">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="28daa-117">A **Termékek** lapon válassza ki annak a kategóriának a nevét, amelyhez bővíteni szeretné a kategória lapját.</span><span class="sxs-lookup"><span data-stu-id="28daa-117">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="28daa-118">A kiválasztott kategória alapértelmezett kategórialapja a lapszerkesztőben nyílik meg.</span><span class="sxs-lookup"><span data-stu-id="28daa-118">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="28daa-119">Válassza a **Kategórialap bővítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="28daa-119">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="28daa-120">Válassza ki a bővített kategórialap sablonját.</span><span class="sxs-lookup"><span data-stu-id="28daa-120">Select a template for the enriched category page.</span></span> <span data-ttu-id="28daa-121">Ha csak kisebb változtatásokat hajt végre, akkor választhatja az alapértelmezett kategórialapot.</span><span class="sxs-lookup"><span data-stu-id="28daa-121">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="28daa-122">Azt is megteheti, hogy kijelöl egy adott kategórialap-sablont.</span><span class="sxs-lookup"><span data-stu-id="28daa-122">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="28daa-123">Amikor kiválasztja a sablont, megnyílik a lap szerkesztője, és a kiválasztott sablon kerül felhasználásra a kiválasztott kategória új kategórialapjának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="28daa-123">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="28daa-124">A lap ki van véve az Ön részére, és most elvégezheti a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="28daa-124">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="28daa-125">A kategória-meghatározási adatokat használó modulok a kiválasztott kategória adatait használják.</span><span class="sxs-lookup"><span data-stu-id="28daa-125">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="28daa-126">A kiválasztott sablon beállításai határozzák meg, hogy milyen változtatásokat lehet végezni.</span><span class="sxs-lookup"><span data-stu-id="28daa-126">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28daa-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="28daa-127">Additional resources</span></span>

[<span data-ttu-id="28daa-128">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="28daa-128">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="28daa-129">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="28daa-129">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="28daa-130">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="28daa-130">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="28daa-131">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="28daa-131">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="28daa-132">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="28daa-132">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="28daa-133">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="28daa-133">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="28daa-134">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="28daa-134">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="28daa-135">Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján</span><span class="sxs-lookup"><span data-stu-id="28daa-135">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

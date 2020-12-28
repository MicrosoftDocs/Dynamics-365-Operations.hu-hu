---
title: Kategória céloldalának gazdagítása
description: Ez a témakör a kategória oldalainak bővítésével foglalkozik Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ca31ec7d2eee7d2b0c863506338341a870ff07ee
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412862"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="04cf8-103">Kategória céloldalának gazdagítása</span><span class="sxs-lookup"><span data-stu-id="04cf8-103">Enrich a category landing page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="04cf8-104">Ez a témakör a kategória oldalainak bővítésével foglalkozik Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="04cf8-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="04cf8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="04cf8-105">Overview</span></span>

<span data-ttu-id="04cf8-106">A Commerce egy alapértelmezett kategória-nyitólapot biztosít, amely a kategóriaadatok megjelenítésekor kerül felhasználásra.</span><span class="sxs-lookup"><span data-stu-id="04cf8-106">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="04cf8-107">Az alapértelmezett kategórialap tartalmazza a szükséges elemeket, például a finomítókat, a kategorizált termékelhelyezést, a rendezési beállításokat, a választási lehetőségek összesítését és a laptördelési vezérlőelemeket.</span><span class="sxs-lookup"><span data-stu-id="04cf8-107">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="04cf8-108">Az alapértelmezett kategórialap használata helyett előfordulhat, hogy olyan „bővített” kategória-nyitólapot szeretne használni, amely több tartalmat és konkrétabb elemeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="04cf8-108">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="04cf8-109">A jellemző bővítéshez szükség lehet a kategória-specifikus marketinganyagok kategóriaoldalhoz.</span><span class="sxs-lookup"><span data-stu-id="04cf8-109">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="04cf8-110">Ez a tartalom több keresztértékesítési célú keresztkategóriás termékelhelyezést, szerkesztői listákat, képeket, videókat és egyéb szöveget tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="04cf8-110">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="04cf8-111">Vagy módosíthatja az alapértelmezett kategórialap, vagy meghatározható egy másik kategórialap egy adott kategóriához.</span><span class="sxs-lookup"><span data-stu-id="04cf8-111">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Bővített kategória-céloldal](./media/CategoryLandingPages.png)

<span data-ttu-id="04cf8-113">A Commerce webhelykészítőben a **Termékrk** lap a webhelyhez társított csatorna kategóriáinak listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="04cf8-113">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="04cf8-114">Ha a **Bővített** állapot van kiválasztva egy kategórialap számára, akkor a kategórialap bővített.</span><span class="sxs-lookup"><span data-stu-id="04cf8-114">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="04cf8-115">Ellenkező esetben az alapértelmezett kategórialap és tartalom kerül felhasználásra a kategóriához.</span><span class="sxs-lookup"><span data-stu-id="04cf8-115">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="04cf8-116">A kategória nevére kattintva megtekintheti a kategória bővített és nem bővített kategórialapjait.</span><span class="sxs-lookup"><span data-stu-id="04cf8-116">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="04cf8-117">A kategórialap bővítéséhez tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="04cf8-117">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="04cf8-118">A **Termékek** lapon válassza ki annak a kategóriának a nevét, amelyhez bővíteni szeretné a kategória lapját.</span><span class="sxs-lookup"><span data-stu-id="04cf8-118">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="04cf8-119">A kiválasztott kategória alapértelmezett kategórialapja a lapszerkesztőben nyílik meg.</span><span class="sxs-lookup"><span data-stu-id="04cf8-119">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="04cf8-120">Válassza a **Kategórialap bővítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04cf8-120">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="04cf8-121">Válassza ki a bővített kategórialap sablonját.</span><span class="sxs-lookup"><span data-stu-id="04cf8-121">Select a template for the enriched category page.</span></span> <span data-ttu-id="04cf8-122">Ha csak kisebb változtatásokat hajt végre, akkor választhatja az alapértelmezett kategórialapot.</span><span class="sxs-lookup"><span data-stu-id="04cf8-122">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="04cf8-123">Azt is megteheti, hogy kijelöl egy adott kategórialap-sablont.</span><span class="sxs-lookup"><span data-stu-id="04cf8-123">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="04cf8-124">Amikor kiválasztja a sablont, megnyílik a lap szerkesztője, és a kiválasztott sablon kerül felhasználásra a kiválasztott kategória új kategórialapjának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="04cf8-124">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="04cf8-125">A lap ki van véve az Ön részére, és most elvégezheti a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="04cf8-125">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="04cf8-126">A kategória-meghatározási adatokat használó modulok a kiválasztott kategória adatait használják.</span><span class="sxs-lookup"><span data-stu-id="04cf8-126">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="04cf8-127">A kiválasztott sablon beállításai határozzák meg, hogy milyen változtatásokat lehet végezni.</span><span class="sxs-lookup"><span data-stu-id="04cf8-127">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04cf8-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="04cf8-128">Additional resources</span></span>

[<span data-ttu-id="04cf8-129">Meglévő webhelyoldal módosítása</span><span class="sxs-lookup"><span data-stu-id="04cf8-129">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="04cf8-130">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="04cf8-130">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="04cf8-131">Oldalelrendezések kiválasztása</span><span class="sxs-lookup"><span data-stu-id="04cf8-131">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="04cf8-132">SEO-metaadatok kezelése</span><span class="sxs-lookup"><span data-stu-id="04cf8-132">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="04cf8-133">Oldal mentése, megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="04cf8-133">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="04cf8-134">A termékoldal bővítése</span><span class="sxs-lookup"><span data-stu-id="04cf8-134">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="04cf8-135">Oldaltartalom hozzáférhetőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="04cf8-135">Verify page content accessibility</span></span>](verify-accessibility.md)

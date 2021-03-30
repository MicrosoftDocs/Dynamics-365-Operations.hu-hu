---
title: Árusítási entitások rendezési sorrendjének módosítása
description: Ez a témakör azt mutatja be, hogyan lehet szabályozni a különböző árusítási-entitások megjelenítési sorrendjét a Dynamics 365 Commerce megoldásban.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 67807c53a6ffc6dd09cc6f0e48218e2ee2de559f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207775"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="30379-103">Árusítási entitások rendezési sorrendjének módosítása</span><span class="sxs-lookup"><span data-stu-id="30379-103">Change the sort order for merchandising entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="30379-104">A kiskereskedők a termékfelderítésre elsődleges eszközként tekintenek az ügyfélinterakciókhoz összes kereskedelmi csatornán.</span><span class="sxs-lookup"><span data-stu-id="30379-104">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span> <span data-ttu-id="30379-105">A különböző funkciók segítségével a vevők könnyedén felfedezhetik a termékeket.</span><span class="sxs-lookup"><span data-stu-id="30379-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="30379-106">Tallózhatók például a kategóriák között, a kereshetnek és a szűrhetnek.</span><span class="sxs-lookup"><span data-stu-id="30379-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="30379-107">Ez a témakör azt mutatja be, hogyan lehet szabályozni a különböző árusítási-entitások megjelenítési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="30379-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="30379-108">Bemutatja a rendezési sorrend módosításának módját is.</span><span class="sxs-lookup"><span data-stu-id="30379-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="30379-109">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="30379-109">Overview</span></span>

<span data-ttu-id="30379-110">A különböző árusításhoz entitások rendezése tovább lett fejlesztve.</span><span class="sxs-lookup"><span data-stu-id="30379-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="30379-111">Ez a támogatás most jobban igazodik a meglévő vevői esetekhez, amelyekhez korábban bővítmények voltak szükségesek az implementálási partnerektől.</span><span class="sxs-lookup"><span data-stu-id="30379-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="30379-112">A Retail 10.0.5 verziójánál korábbi verziókban a navigációs hierarchiában a kategóriák rendezési sorrendje ábécé sorrendben volt.</span><span class="sxs-lookup"><span data-stu-id="30379-112">In versions of Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="30379-113">Az új egyéni rendezési funkció lehetővé teszi a az árukezelők számára, hogy az összes végfelhasználói ügyfél számára konfigurálják a különböző árusítási entitások rendezési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="30379-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="30379-114">Ezek az ügyfelek többek között a központok (HQ) és a hívásközpontok.</span><span class="sxs-lookup"><span data-stu-id="30379-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a><span data-ttu-id="30379-115">A termékek hierarchiájában megjelenítési sorrend konfigurálása a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="30379-115">Configure the display order for categories in the product hierarchy</span></span>

<span data-ttu-id="30379-116">Ennek a műveletnek az elvégzése előtt a demóadatokat telepítenie kell a környezetébe.</span><span class="sxs-lookup"><span data-stu-id="30379-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="30379-117">Ugorjon a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Kereskedelmi termékhierarchia** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30379-117">Go to **Retail and Commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
2. <span data-ttu-id="30379-118">Kattintson a **Kategóriahierarchiák szerkesztése** pontra.</span><span class="sxs-lookup"><span data-stu-id="30379-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="30379-119">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30379-119">Click **Edit**.</span></span>
4. <span data-ttu-id="30379-120">A fában bontsa ki az **ÖSSZES \> Akciósportok** elemet.</span><span class="sxs-lookup"><span data-stu-id="30379-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="30379-121">A fában bontsa ki az **ÖSSZES \> Csapatsportok** elemet.</span><span class="sxs-lookup"><span data-stu-id="30379-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="30379-122">Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.</span><span class="sxs-lookup"><span data-stu-id="30379-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="30379-123">(A szám negatív is lehet.)</span><span class="sxs-lookup"><span data-stu-id="30379-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="30379-124">Ismételje meg a 4–6 lépéseket minden olyan további kategória esetében, amelynek módosítani szeretné a sorrendet.</span><span class="sxs-lookup"><span data-stu-id="30379-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="30379-125">A csatorna navigációs hierarchiájának megjelenítési sorrendje tükröződni fog a központ számára a kereskedelmi termékek hierarchiájában, és kategóriánként kiadott termékeknél.</span><span class="sxs-lookup"><span data-stu-id="30379-125">The display order for the channel navigation hierarchy will be reflected in HQ for the commerce product hierarchy and released products by category.</span></span>

![A termékek hierarchiájának egyéni sorrendje negatív értékekkel](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Közzétett termékek kategóriák szerint, a termékek hierarchiája alapján egyéni módon rendezve](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="30379-128">A csatornanavigáció hierarchiájában megjelenítési sorrend konfigurálása a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="30379-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="30379-129">Ennek a műveletnek az elvégzése előtt a demóadatokat telepítenie kell a környezetébe.</span><span class="sxs-lookup"><span data-stu-id="30379-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="30379-130">Menjen a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Csatorna navigációs kategóriák** helyre.</span><span class="sxs-lookup"><span data-stu-id="30379-130">Go to **Retail and Commerce \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="30379-131">A listából válassza ki a **Divatnavigáció** hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="30379-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="30379-132">Kattintson a **Kategóriahierarchiák szerkesztése** pontra.</span><span class="sxs-lookup"><span data-stu-id="30379-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="30379-133">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30379-133">Click **Edit**.</span></span>
5. <span data-ttu-id="30379-134">A fában válassza ki a **Divat \> Női ruházat \> Női cipők** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="30379-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="30379-135">Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.</span><span class="sxs-lookup"><span data-stu-id="30379-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="30379-136">A fában válassza ki a **Divat \> Női ruházat \> Felsők** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="30379-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="30379-137">Hasonlóképpen meghatározható az alkategóriák rendezési sorrendje is.</span><span class="sxs-lookup"><span data-stu-id="30379-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="30379-138">A fában válassza ki a **Divat \> Férfiruházat \> Casual ingek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="30379-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="30379-139">Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.</span><span class="sxs-lookup"><span data-stu-id="30379-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="30379-140">A fában válassza ki a **Divat \> Férfiruházat \> Kabátok és dzsekik** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="30379-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="30379-141">Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.</span><span class="sxs-lookup"><span data-stu-id="30379-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="30379-142">Ismételje meg ezt minden olyan további kategória esetében, amelynek módosítani szeretné a sorrendet.</span><span class="sxs-lookup"><span data-stu-id="30379-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="30379-143">A csatorna navigációs hierarchiájának megjelenítési sorrendje a központ, katalógus és csatornákban is tükröződik.</span><span class="sxs-lookup"><span data-stu-id="30379-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and channels.</span></span>

![Csatornanavigáció hierarchiája egyéni módon rendezve](./media/ChannelNavCustomSorted.png)

![Katalógus-navigációs hierarchia egyéni módon rendezve a csatorna navigációs hierarchiája alapján](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Pénztár egyéni módon rendezett kategóriákkal](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="30379-147">Alapértelmezés szerint az egyéni rendezési sorrend funkció ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="30379-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="30379-148">Ennek a funkciónak és egyéb funkcióknak a bekapcsolásával kapcsolatosan lásd: [Funkciókezelés](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="30379-148">To learn how to turn on this feature and other features, see [Feature management](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: "Beszerzési katalógusok"
description: "Ez a cikk magas szinten leírja, hogy a beszerzési szakemberek hogyan állíthatnak be és tarthatnak fenn beszerzési katalógusokat. A beszerzési katalógusok határozzák meg a cikkeket és szolgáltatásokat, amelyeket a vállalati alkalmazottak megrendelhetnek belső használat céljából."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8d23c193e9a136c7ae315a991a9df7fff1c42392
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="procurement-catalogs"></a><span data-ttu-id="73f86-104">Beszerzési katalógusok</span><span class="sxs-lookup"><span data-stu-id="73f86-104">Procurement catalogs</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="73f86-105">Ez a cikk magas szinten leírja, hogy a beszerzési szakemberek hogyan állíthatnak be és tarthatnak fenn beszerzési katalógusokat.</span><span class="sxs-lookup"><span data-stu-id="73f86-105">This article describes, at a high level, how purchasing professionals can set up and maintain procurement catalogs.</span></span> <span data-ttu-id="73f86-106">A beszerzési katalógusok határozzák meg a cikkeket és szolgáltatásokat, amelyeket a vállalati alkalmazottak megrendelhetnek belső használat céljából.</span><span class="sxs-lookup"><span data-stu-id="73f86-106">Procurement catalogs define the items and services that company employees can order for internal use.</span></span>

<span data-ttu-id="73f86-107">A beszerzési szakemberek a beszerezhető cikkekre és szolgáltatásokra vonatkozó, a vállalaton belüli használatra szóló katalógusokat hozhatnak létre és karbantarthatják azokat.</span><span class="sxs-lookup"><span data-stu-id="73f86-107">Purchasing professionals can create and maintain catalogs of the items and services that can be purchased for internal use in an organization.</span></span> <span data-ttu-id="73f86-108">Katalógusok beállítása után a vállalat alkalmazottai beszerzési igényléseket hozhatnak létre a katalógusokból való rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="73f86-108">After catalogs are set up, company employees can create purchase requisitions to order from them.</span></span> <span data-ttu-id="73f86-109">A katalógusok használatával lehet érvényesíteni a beszerzési irányelveket, úgy, hogy az alkalmazottak csak olyan cikkeket és szolgáltatásokat rendelhetnek, amelyek engedélyezve vannak a vásárló jogi személyük számára.</span><span class="sxs-lookup"><span data-stu-id="73f86-109">The catalogs can be used to enforce purchasing policies, so that employees can order only the items and services that are allowed for their buying legal entity.</span></span> <span data-ttu-id="73f86-110">Beszerzési katalógus létrehozása esetén a következő feladatok elvégzését kell átgondolnia:</span><span class="sxs-lookup"><span data-stu-id="73f86-110">When you create a procurement catalog, you should consider the following tasks:</span></span>

-   <span data-ttu-id="73f86-111">A katalógus létrehozása előtt állítsa be a beszerzési kategóriák hierarchiáját.</span><span class="sxs-lookup"><span data-stu-id="73f86-111">Configure your procurement category hierarchy before you create the catalog.</span></span>
-   <span data-ttu-id="73f86-112">Határozza meg, mely termékeket rendelhessék meg az alkalmazottak.</span><span class="sxs-lookup"><span data-stu-id="73f86-112">Determine which products you want your employees to be able to order.</span></span> <span data-ttu-id="73f86-113">Megjelenítheti vagy elrejtheti az adott termékeket a katalógus csomópontban, vagy megjelenítheti vagy elrejtheti a csomópontban az összes terméket.</span><span class="sxs-lookup"><span data-stu-id="73f86-113">You can show or hide specific products in a catalog node, or you can show or hide all the products in a node.</span></span>
-   <span data-ttu-id="73f86-114">Határozza meg, hány beszerzési katalógusra van szüksége.</span><span class="sxs-lookup"><span data-stu-id="73f86-114">Determine how many procurement catalogs you require.</span></span> <span data-ttu-id="73f86-115">A beszerzési katalógushoz való hozzáférést a katalógus szabálya határozza meg, amelyet konfigurál a jogi személyhez és az üzemi egységhez, amelyhez az alkalmazott hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="73f86-115">Access to a procurement catalog is determined by the catalog policy rule that you configure for the legal entity and operating unit that an employee is assigned to.</span></span>

<span data-ttu-id="73f86-116">Számos tényező határozza meg azokat a termékeket, amelyeket az alkalmazottak megrendelhetnek, illetve a lehetséges beszerzési kategóriákat, amelyeket használhatnak a beszerzési igénylések létrehozásakor:</span><span class="sxs-lookup"><span data-stu-id="73f86-116">Several factors determine the products that employees can order and the procurement categories that they can use when they create purchase requisitions:</span></span>

-   <span data-ttu-id="73f86-117">A kategóriához való hozzáférésre vonatkozó irányelvszabály határozza meg, hogy mely beszerzési kategóriák érhetők el a beszerzési igénylésben.</span><span class="sxs-lookup"><span data-stu-id="73f86-117">The category access policy rule in the purchasing policy determines which procurement categories are available in the purchase requisition.</span></span> <span data-ttu-id="73f86-118">Ha nincs meghatározva szabály, akkor az összes beszerzési kategória elérhető.</span><span class="sxs-lookup"><span data-stu-id="73f86-118">If no rule is defined, all procurement categories are available.</span></span>
-   <span data-ttu-id="73f86-119">Az alkalmazottak egy terméket csak akkor rendelhetnek meg, ha az aktív az Ön szervezetének katalógusában, és ha engedélyezett csomópontban van, és nincs elrejtve.</span><span class="sxs-lookup"><span data-stu-id="73f86-119">Employees can order a product only if it's in the active procurement catalog for your organization, and if it's in an enabled node and not hidden.</span></span> <span data-ttu-id="73f86-120">A terméknek ezen felül olyan kategóriában kell lennie, amelyhez az adott alkalmazottnak hozzáférése van a kategória hozzáférési irányelvszabálya szerint.</span><span class="sxs-lookup"><span data-stu-id="73f86-120">The product must also be in a category that a particular employee has access to according to the category access policy rule.</span></span>
-   <span data-ttu-id="73f86-121">A katalógus-irányelvszabály adja meg a használt katalógust.</span><span class="sxs-lookup"><span data-stu-id="73f86-121">The catalog policy rule specifies the catalog that is used.</span></span> <span data-ttu-id="73f86-122">Ha nincs a katalógus-irányelvszabály beállítva, akkor egyedül a kategória hozzáférési szabálya határozza meg, hogy egy alkalmazott az igénylésben mely termékeket rendelheti meg.</span><span class="sxs-lookup"><span data-stu-id="73f86-122">If no catalog policy rule is defined, the category access rule alone determines the products that an employee can order on the requisition.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73f86-123">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="73f86-123">Prerequisites</span></span>
<span data-ttu-id="73f86-124">A következő táblázat leírja a feladatokat, amelyeket el kell végezni mielőtt a beszerzési szakember beszerzési katalógust hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="73f86-124">The following table describes the tasks that must be completed before a purchasing professional can create a procurement catalog.</span></span>

| <span data-ttu-id="73f86-125">Feladat</span><span class="sxs-lookup"><span data-stu-id="73f86-125">Task</span></span>                                                | <span data-ttu-id="73f86-126">Szerepkör</span><span class="sxs-lookup"><span data-stu-id="73f86-126">Role</span></span>               | <span data-ttu-id="73f86-127">Leírás</span><span class="sxs-lookup"><span data-stu-id="73f86-127">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="73f86-128">Beszerzési kategóriahierarchia beállítása.</span><span class="sxs-lookup"><span data-stu-id="73f86-128">Set up a procurement category hierarchy.</span></span>            | <span data-ttu-id="73f86-129">Beszerzési vezető</span><span class="sxs-lookup"><span data-stu-id="73f86-129">Purchasing manager</span></span> | <span data-ttu-id="73f86-130">A beszerzési kategóriahierarchiák segítségével a cikkek vagy tranzakciók besorolhatók jelentéskészítés és elemzés céljából.</span><span class="sxs-lookup"><span data-stu-id="73f86-130">Procurement category hierarchies classify items or transactions for reporting and analysis.</span></span> <span data-ttu-id="73f86-131">Beszerzési kategóriahierarchia használatával a vállalatok stratégiailag kezelhetik a kategóriákat, termékeket, szállítókat és egyéb beszerzési tényezőket egy központi helyről.</span><span class="sxs-lookup"><span data-stu-id="73f86-131">By using a procurement category hierarchy, companies can strategically manage categories, products, vendors, and other procurement factors from a central location.</span></span> <span data-ttu-id="73f86-132">Egy teljes szervezet számára egy beszerzési kategóriahierarchia van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="73f86-132">One procurement category hierarchy is defined for a whole organization.</span></span> <span data-ttu-id="73f86-133">A katalógus a beszerzési kategóriák hierarchiáján alapszik: a hierarchia kategóriái a katalógusban csomópontok lesznek.</span><span class="sxs-lookup"><span data-stu-id="73f86-133">The catalog is based on the procurement category hierarchy: the categories in the hierarchy become nodes in the catalog.</span></span> <span data-ttu-id="73f86-134">A szállítók és a termékek benne vannak az Ön katalógusában.</span><span class="sxs-lookup"><span data-stu-id="73f86-134">The vendors and products are included in your catalog.</span></span> |
| <span data-ttu-id="73f86-135">Szállítók és termékek hozzáadása a beszerzési kategóriákhoz.</span><span class="sxs-lookup"><span data-stu-id="73f86-135">Add vendors and products to procurement categories.</span></span> | <span data-ttu-id="73f86-136">Beszerzési vezető</span><span class="sxs-lookup"><span data-stu-id="73f86-136">Purchasing manager</span></span> | <span data-ttu-id="73f86-137">A szervezet számára a beszerzési kategóriahierarchia létrehozása után minden egyes beszerzési kategória társítható a meghatározott szállítókkal, termékekkel és így tovább.</span><span class="sxs-lookup"><span data-stu-id="73f86-137">When the procurement category hierarchy is created for your organization, each procurement category can be associated with specific vendors, products, and so on.</span></span> <span data-ttu-id="73f86-138">Ezek a társítások automatikusan bele lesznek másolva a katalógusba.</span><span class="sxs-lookup"><span data-stu-id="73f86-138">These associations are copied automatically to the catalog.</span></span>                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a><span data-ttu-id="73f86-139">Katalógus beállítása</span><span class="sxs-lookup"><span data-stu-id="73f86-139">Setting up a catalog</span></span>
<span data-ttu-id="73f86-140">Miután teljesültek az előfeltételek, beállíthatja a katalógusokat.</span><span class="sxs-lookup"><span data-stu-id="73f86-140">After the prerequisites have been met, you can set up catalogs.</span></span> <span data-ttu-id="73f86-141">Létrehozhat egy katalógust, amelyet a teljes szervezet használ, vagy több katalógust a szervezeten belüli különböző osztályok számára.</span><span class="sxs-lookup"><span data-stu-id="73f86-141">You can create either one catalog that your whole organization uses or multiple catalogs that the various divisions in your organization use.</span></span> <span data-ttu-id="73f86-142">Ha létrehoz egy katalógust a teljes szervezet számára, a katalógushoz való hozzáférést a beszerzési irányelvek vezérlik.</span><span class="sxs-lookup"><span data-stu-id="73f86-142">If you create one catalog for the whole organization, access to the catalog is controlled by your purchasing policy rules.</span></span>  

<span data-ttu-id="73f86-143">A katalógus határozza meg, hogy mely termékek állnak rendelkezésre, amikor a beszerzési igénylések létrejönnek, de használhat kategória-hozzáférési irányelveket további megkötések alkalmazása céljából.</span><span class="sxs-lookup"><span data-stu-id="73f86-143">The catalog defines which products are available when purchase requisitions are created, but you can use category access policies rules to apply additional restrictions.</span></span> <span data-ttu-id="73f86-144">Mivel a katalógus csomópontjai beszerzési kategóriák, azok letilthatók egy kategória-hozzáférési irányelvvel.</span><span class="sxs-lookup"><span data-stu-id="73f86-144">Because the nodes in a catalog are procurement categories, they can be suppressed by a category access policy rule.</span></span> <span data-ttu-id="73f86-145">Ebben az esetben az adott kategóriába tartozó termékek nem állnak rendelkezésre az alkalmazottak számára az igénylésekhez való használathoz.</span><span class="sxs-lookup"><span data-stu-id="73f86-145">In this case, the products in that category are not available for employees to use on requisitions.</span></span> <span data-ttu-id="73f86-146">A kategória-hozzáférési irányelvszabályokat a **Beszerzési irányelvek** oldalon adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="73f86-146">You define category access policy rules on the **Purchasing policies** page.</span></span> <span data-ttu-id="73f86-147">A következő táblázat leírja a katalógus beállításához elvégzendő feladatokat.</span><span class="sxs-lookup"><span data-stu-id="73f86-147">The following table describes the tasks that must be completed to set up a catalog.</span></span>

| <span data-ttu-id="73f86-148">Feladat</span><span class="sxs-lookup"><span data-stu-id="73f86-148">Task</span></span>                                                   | <span data-ttu-id="73f86-149">Szerepkör</span><span class="sxs-lookup"><span data-stu-id="73f86-149">Role</span></span>             | <span data-ttu-id="73f86-150">Leírás</span><span class="sxs-lookup"><span data-stu-id="73f86-150">Description</span></span>                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="73f86-151">Új katalógus létrehozása.</span><span class="sxs-lookup"><span data-stu-id="73f86-151">Create a new catalog.</span></span>                                  | <span data-ttu-id="73f86-152">Beszerzési ügynök</span><span class="sxs-lookup"><span data-stu-id="73f86-152">Purchasing agent</span></span> | <span data-ttu-id="73f86-153">A katalógus létrehozásakor megadja a katalógus nevét és a katalógus leírását.</span><span class="sxs-lookup"><span data-stu-id="73f86-153">When you create a catalog, you specify a name and description for the catalog.</span></span> <span data-ttu-id="73f86-154">Megadhatja azt is, hogy manuálisan vagy automatikusan frissül a katalógus, és megadhatja a katalógus tulajdonosát.</span><span class="sxs-lookup"><span data-stu-id="73f86-154">You also define whether the catalog is updated manually or automatically, and specify the catalog owner.</span></span>                                                                                                                                      |
| <span data-ttu-id="73f86-155">Ellenőrizze, hogy elérhetők-e termékek a katalógusban.</span><span class="sxs-lookup"><span data-stu-id="73f86-155">Control whether products are available in the catalog.</span></span> | <span data-ttu-id="73f86-156">Beszerzési ügynök</span><span class="sxs-lookup"><span data-stu-id="73f86-156">Purchasing agent</span></span> | <span data-ttu-id="73f86-157">Mivel a termékek a beszerzési kategóriákból öröklődnek, az összes a megfelelő katalógus csomópontjában jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="73f86-157">Because the products are inherited from the procurement categories, they all appear in the appropriate catalog nodes.</span></span> <span data-ttu-id="73f86-158">Szabályozhatja, hogy a csomópontban lévő összes termék el legyen rejtve vagy látszódjon, amikor a katalógust használják egy beszerzési igénylésnél.</span><span class="sxs-lookup"><span data-stu-id="73f86-158">You can control whether all products in a node are hidden or shown when the catalog is used in a purchase requisition.</span></span> <span data-ttu-id="73f86-159">Beállíthatja azt is, hogy a csomópont egyes termékei rejtve legyenek vagy látszódjanak.</span><span class="sxs-lookup"><span data-stu-id="73f86-159">You can also control whether individual products in a node are hidden or shown.</span></span> |
| <span data-ttu-id="73f86-160">Katalógus közzététele.</span><span class="sxs-lookup"><span data-stu-id="73f86-160">Publish the catalog.</span></span>                                   | <span data-ttu-id="73f86-161">Beszerzési ügynök</span><span class="sxs-lookup"><span data-stu-id="73f86-161">Purchasing agent</span></span> | <span data-ttu-id="73f86-162">Mielőtt a katalógus érhető lesz az alkalmazottak számára egy igényléshez, meg kell határoznia a katalógus számára egy katalógus-irányelvszabályt, be kell állítania a katalógus állapotát az **Aktív** lehetőségre, és közzé kell tennie a katalógust.</span><span class="sxs-lookup"><span data-stu-id="73f86-162">Before a catalog is available for employees to use in a requisition, you must define a catalog policy rule for the catalog, set the catalog’s status to **Active**, and publish the catalog.</span></span> <span data-ttu-id="73f86-163">Inaktiválhatja a katalógusokat, amelyekről nem szeretné, hogy elérhetőek legyenek a felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="73f86-163">You can inactivate catalogs that you no longer want to be available to your users.</span></span>                                              |

<span data-ttu-id="73f86-164">A frissítéseket automatikusan vagy manuálisan teszik közzé, attól függően, hogy milyen beállítást választ az **Alapértelmezett frissítéstípus** mezőben a **Katalógusok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="73f86-164">Updates are published either automatically or manually, depending on the option that you select for the catalog in the **Default update type** field on the **Catalogs** page.</span></span> <span data-ttu-id="73f86-165">A következő alapértelmezett frissítéstípusok érhetők el a katalógusok számára:</span><span class="sxs-lookup"><span data-stu-id="73f86-165">The following default update types are available for catalogs:</span></span>

-   <span data-ttu-id="73f86-166">**Dinamikus** – A katalógus automatikusan frissül, ahányszor csak megváltozik.</span><span class="sxs-lookup"><span data-stu-id="73f86-166">**Dynamic** – The catalog is automatically updated whenever it's changed.</span></span>
-   <span data-ttu-id="73f86-167">**Statikus** – A katalógusokat kézzel kell frissíteni.</span><span class="sxs-lookup"><span data-stu-id="73f86-167">**Static** – The catalogs must be manually updated.</span></span>
-   <span data-ttu-id="73f86-168">**Mindkét** – Ha a katalógus tartalmaz, megadhat egy alapértelmezett típusának módosítása termékkategóriák **statikus**, akkor kézzel kell frissíteni ezekbe a kategóriákba frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="73f86-168">**Both** – If the catalog includes product categories that have a default update type of **Static**, it must be manually updated when these categories are updated.</span></span> <span data-ttu-id="73f86-169">Ha a katalógus olyan termékkategóriákat tartalmaz, amelyeknek az alapértelmezett frissítési típusa **Dinamikus**, automatikusan frissül, amennyiben megváltoznak.</span><span class="sxs-lookup"><span data-stu-id="73f86-169">If the catalog includes product categories that have a default update type of **Dynamic**, it is automatically updated whenever it's changed.</span></span>


<a name="see-also"></a><span data-ttu-id="73f86-170">Lásd még</span><span class="sxs-lookup"><span data-stu-id="73f86-170">See also</span></span>
--------

[<span data-ttu-id="73f86-171">Beszerzési kategóriahierarchia beállítása (feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="73f86-171">Set up a procurement category hierarchy (Task guide)</span></span>](/dynamics365/unified-operations/supply-chain/procurement/tasks/set-up-procurement-category-hierarchy)




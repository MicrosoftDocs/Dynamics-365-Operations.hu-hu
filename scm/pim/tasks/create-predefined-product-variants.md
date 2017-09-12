--- 
title: "Az előre meghatározott termékváltozatok létrehozása"
description: "Ez az eljárás bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását."
author: BibiSp
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fa23f1449e750b4ed1c0f631a98c42b18b7dbb40
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="53b04-103">Az előre meghatározott termékváltozatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="53b04-103">Create predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="53b04-104">Ez az eljárás bemutatja az alaptermék termékváltozatainak a termékdimenziók kombinációjának használatával történő létrehozását.</span><span class="sxs-lookup"><span data-stu-id="53b04-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="53b04-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="53b04-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="53b04-106">Alaptermék létrehozása</span><span class="sxs-lookup"><span data-stu-id="53b04-106">Create a product master</span></span>
1. <span data-ttu-id="53b04-107">Ugorjon a Termékinformációk kezelése > Termékek > Alaptermékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="53b04-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-108">Click New.</span></span>
3. <span data-ttu-id="53b04-109">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="53b04-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="53b04-110">A termékszám manuálisan történő megadása csak akkor kötelező, ha nincs beállítva számsorozat a termék száma mezőre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="53b04-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="53b04-111">Másképpen fogalmazva, hagyja ki a lépést, ha a számsorozatot létrehozta a rendszer a mezőre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="53b04-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="53b04-112">Írjon be egy értéket a Terméknév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="53b04-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="53b04-113">A Termékdimenzió csoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="53b04-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="53b04-114">Válassza ki a SizeCol termékdimenzió-csoportot (Méret és Szín).</span><span class="sxs-lookup"><span data-stu-id="53b04-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="53b04-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53b04-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="53b04-116">Termékdimenziók hozzáadása</span><span class="sxs-lookup"><span data-stu-id="53b04-116">Add product dimensions</span></span>
1. <span data-ttu-id="53b04-117">Kattintson a Termékdimenziók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="53b04-118">Ez a példa bemutatja, hogy hogyan lehet manuálisan megadni a termékdimenziókat.</span><span class="sxs-lookup"><span data-stu-id="53b04-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="53b04-119">Arra is lehetősége van, hogy kiválassza a méretet, a színt és a stíluscsoportot, amely a használni kívánt termékdimenzió értékeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="53b04-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="53b04-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-120">Click New.</span></span>
3. <span data-ttu-id="53b04-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="53b04-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="53b04-122">A Méret mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="53b04-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="53b04-123">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="53b04-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="53b04-124">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="53b04-124">Click New.</span></span>
7. <span data-ttu-id="53b04-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="53b04-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="53b04-126">A Méret mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="53b04-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="53b04-127">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="53b04-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="53b04-128">Kattintson a Színek fülre.</span><span class="sxs-lookup"><span data-stu-id="53b04-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="53b04-129">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-129">Click New.</span></span>
12. <span data-ttu-id="53b04-130">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="53b04-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="53b04-131">A Szín mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="53b04-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="53b04-132">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="53b04-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="53b04-133">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="53b04-133">Click New.</span></span>
16. <span data-ttu-id="53b04-134">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="53b04-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="53b04-135">A Szín mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="53b04-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="53b04-136">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="53b04-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="53b04-137">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="53b04-137">Click Save.</span></span>
20. <span data-ttu-id="53b04-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="53b04-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="53b04-139">Termékváltozatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="53b04-139">Generate product variants</span></span>
1. <span data-ttu-id="53b04-140">Kattintson a Termékváltozatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-140">Click Product variants.</span></span>
2. <span data-ttu-id="53b04-141">Kattintson a Változatjavaslatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="53b04-142">Kattintson a Minden kijelölése elemre.</span><span class="sxs-lookup"><span data-stu-id="53b04-142">Click Select all.</span></span>
    * <span data-ttu-id="53b04-143">Az alábbi példában az összes lehetséges változat ki van választva.</span><span class="sxs-lookup"><span data-stu-id="53b04-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="53b04-144">Ha csak a lehetséges termék cikkdimenzió-kombinációk egy részét használja fel a rendszer a változatok létrehozásához, kiválaszthatja az egyes bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="53b04-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="53b04-145">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b04-145">Click Create.</span></span>
    * <span data-ttu-id="53b04-146">A termékdimenzió-értékek kombinációin alapuló összes változatra vonatkozóan létrehozhat leírásokat.</span><span class="sxs-lookup"><span data-stu-id="53b04-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="53b04-147">A Leírások nem kötelező jellegűek.</span><span class="sxs-lookup"><span data-stu-id="53b04-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="53b04-148">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="53b04-148">Click Save.</span></span>



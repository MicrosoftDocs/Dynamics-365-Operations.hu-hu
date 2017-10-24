---
title: "Termékdimenziók"
description: "Négy termékdimenzió létezik: szín, konfiguráció, méret és stílus. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 105324f146f28bc61e87dff1089b367958ff9062
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="product-dimensions"></a><span data-ttu-id="2d986-105">Termékdimenziók</span><span class="sxs-lookup"><span data-stu-id="2d986-105">Product dimensions</span></span>

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]


<span data-ttu-id="2d986-106">Négy termékdimenzió létezik: szín, konfiguráció, méret és stílus.</span><span class="sxs-lookup"><span data-stu-id="2d986-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="2d986-107">A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez.</span><span class="sxs-lookup"><span data-stu-id="2d986-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="2d986-108">A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is.</span><span class="sxs-lookup"><span data-stu-id="2d986-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="2d986-109">Termékdimenziók olyan jellemzőket termékváltozat azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="2d986-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="2d986-110">Cikkdimenziók kombinációi használhatja termékváltozatok meghatározására.</span><span class="sxs-lookup"><span data-stu-id="2d986-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="2d986-111">Termékváltozat létrehozásához meg kell adnia legalább egy termékdimenzió alaptermék.</span><span class="sxs-lookup"><span data-stu-id="2d986-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>
<span data-ttu-id="2d986-112">Termékváltozatok</span><span class="sxs-lookup"><span data-stu-id="2d986-112">Product variants</span></span>
----------------

<span data-ttu-id="2d986-113">Termékváltozatok is nevezik cikkeket.</span><span class="sxs-lookup"><span data-stu-id="2d986-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="2d986-114">Cikk tárgyi eszközök termék, amely nem azonos a szolgáltatás fut.</span><span class="sxs-lookup"><span data-stu-id="2d986-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="2d986-115">Azonban lehetőség van alaptermék meghatározására is a szolgáltatástípussal.</span><span class="sxs-lookup"><span data-stu-id="2d986-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="2d986-116">A Szolgáltatástípus használatával megadhat szolgáltatásokat magukba foglaló termékváltozatokat.</span><span class="sxs-lookup"><span data-stu-id="2d986-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="2d986-117">Például megadhatja a tanácsadói munka és a termékbevételezés változatok vezető tanácsadók és beosztott tanácsadók által végrehajtott munka alaptermék.</span><span class="sxs-lookup"><span data-stu-id="2d986-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="2d986-118">Termékdimenziók</span><span class="sxs-lookup"><span data-stu-id="2d986-118">Product dimensions</span></span>
<span data-ttu-id="2d986-119">A következő termékdimenziók léteznek: szín, konfiguráció, méret és stílus.</span><span class="sxs-lookup"><span data-stu-id="2d986-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="2d986-120">Termékváltozat hozható létre a termékdimenzió-értékek alapján.</span><span class="sxs-lookup"><span data-stu-id="2d986-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="2d986-121">Termékdimenzió-értékek, mint például méret, szín és stílus a **Méret**, **Szín** és **Stílus** lapokon hozhatók létre, amelyek a következő helyekről érhetők el: **Termékinformációk kezelése** &gt; **Beállítás** &gt; **Dimenzió- és változatcsoportok** &gt; **Méretek/Színek/Stílusok**.</span><span class="sxs-lookup"><span data-stu-id="2d986-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="2d986-122">A Konfigurációdimenzió termékdimenzió-értékei általában a Termékkonfiguráló vagy a Dimenzión alapuló konfiguráló használatával hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="2d986-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="2d986-123">A termékdimenziók létrehozása és karbantartása a **Termékdimenziók** oldalon lehetséges, amely a következő helyekről érhető el:</span><span class="sxs-lookup"><span data-stu-id="2d986-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="2d986-124">Kattintson a **Termékinformációk kezelése** &gt; **Termékek** &gt; **Alaptermékek** lehetőségekre.</span><span class="sxs-lookup"><span data-stu-id="2d986-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="2d986-125">A **Műveleti panel** modulon kattintson a **Termékdimenziók** elemre.</span><span class="sxs-lookup"><span data-stu-id="2d986-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="2d986-126">Kattintson a  **Termékinformációk kezelése** &gt; **Termékek** &gt; **Minden termék és alaptermék** lehetőségekre.</span><span class="sxs-lookup"><span data-stu-id="2d986-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="2d986-127">Válasszon ki egy alapterméket.</span><span class="sxs-lookup"><span data-stu-id="2d986-127">Select a product master.</span></span> <span data-ttu-id="2d986-128">A **Műveleti panel** modulon kattintson a **Termékdimenziók** elemre.</span><span class="sxs-lookup"><span data-stu-id="2d986-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="2d986-129">Kattintson a **Termékinformációk kezelése** &gt; **Kiadott termékek** lehetőségekre.</span><span class="sxs-lookup"><span data-stu-id="2d986-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="2d986-130">Válasszon ki egy alapterméket.</span><span class="sxs-lookup"><span data-stu-id="2d986-130">Select a product master.</span></span> <span data-ttu-id="2d986-131">A **Műveleti panel** modulon kattintson a **Termék** elemre.</span><span class="sxs-lookup"><span data-stu-id="2d986-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="2d986-132">Az **Alaptermék** csoportban kattintson a **Termékdimenziók** gombra.</span><span class="sxs-lookup"><span data-stu-id="2d986-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="2d986-133">A változatok létrehozható egy cikkhez száma lehetséges termék cikkdimenzió-kombinációk száma korlátozza.</span><span class="sxs-lookup"><span data-stu-id="2d986-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>
| <span data-ttu-id="2d986-134">**Tipp**</span><span class="sxs-lookup"><span data-stu-id="2d986-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2d986-135">Használatakor a termék, például egy olyan rendeléssort, választhat a termékdimenziókat, amellyel dolgozni szeretne termékváltozat azonosításához.</span><span class="sxs-lookup"><span data-stu-id="2d986-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="2d986-136">Példa</span><span class="sxs-lookup"><span data-stu-id="2d986-136">Example</span></span>
<span data-ttu-id="2d986-137">Egy vállalat farmernadrágokat értékesít.</span><span class="sxs-lookup"><span data-stu-id="2d986-137">A company sells denim jeans.</span></span> <span data-ttu-id="2d986-138">A Farmernadrág cikknél a Szín és a Méret termékdimenziókat alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2d986-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="2d986-139">A farmernadrágok három különböző színben és hat különböző méretben kaphatók.</span><span class="sxs-lookup"><span data-stu-id="2d986-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="2d986-140">Színek: Kék, Fekete, Barna Méretek: XS, S, M, L, XL, XXL Nem minden méretben érhető el mindhárom szín.</span><span class="sxs-lookup"><span data-stu-id="2d986-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="2d986-141">Ha minden kombináció érvényes lenne, az 18 féle farmernadrágot jelentene.</span><span class="sxs-lookup"><span data-stu-id="2d986-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="2d986-142">Ebben a példában csak a következő kilenc termék változat kombináció legyártva.</span><span class="sxs-lookup"><span data-stu-id="2d986-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="2d986-143">Szín</span><span class="sxs-lookup"><span data-stu-id="2d986-143">Color</span></span> | <span data-ttu-id="2d986-144">Méret</span><span class="sxs-lookup"><span data-stu-id="2d986-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="2d986-145">Kék</span><span class="sxs-lookup"><span data-stu-id="2d986-145">Blue</span></span>  | <span data-ttu-id="2d986-146">XS</span><span class="sxs-lookup"><span data-stu-id="2d986-146">XS</span></span>   |
| <span data-ttu-id="2d986-147">Kék</span><span class="sxs-lookup"><span data-stu-id="2d986-147">Blue</span></span>  | <span data-ttu-id="2d986-148">V</span><span class="sxs-lookup"><span data-stu-id="2d986-148">S</span></span>    |
| <span data-ttu-id="2d986-149">Kék</span><span class="sxs-lookup"><span data-stu-id="2d986-149">Blue</span></span>  | <span data-ttu-id="2d986-150">H</span><span class="sxs-lookup"><span data-stu-id="2d986-150">M</span></span>    |
| <span data-ttu-id="2d986-151">Fekete</span><span class="sxs-lookup"><span data-stu-id="2d986-151">Black</span></span> | <span data-ttu-id="2d986-152">H</span><span class="sxs-lookup"><span data-stu-id="2d986-152">M</span></span>    |
| <span data-ttu-id="2d986-153">Fekete</span><span class="sxs-lookup"><span data-stu-id="2d986-153">Black</span></span> | <span data-ttu-id="2d986-154">EREDMÉNY</span><span class="sxs-lookup"><span data-stu-id="2d986-154">L</span></span>    |
| <span data-ttu-id="2d986-155">Fekete</span><span class="sxs-lookup"><span data-stu-id="2d986-155">Black</span></span> | <span data-ttu-id="2d986-156">XL</span><span class="sxs-lookup"><span data-stu-id="2d986-156">XL</span></span>   |
| <span data-ttu-id="2d986-157">Barna</span><span class="sxs-lookup"><span data-stu-id="2d986-157">Brown</span></span> | <span data-ttu-id="2d986-158">K</span><span class="sxs-lookup"><span data-stu-id="2d986-158">L</span></span>    |
| <span data-ttu-id="2d986-159">Barna</span><span class="sxs-lookup"><span data-stu-id="2d986-159">Brown</span></span> | <span data-ttu-id="2d986-160">XL</span><span class="sxs-lookup"><span data-stu-id="2d986-160">XL</span></span>   |
| <span data-ttu-id="2d986-161">Barna</span><span class="sxs-lookup"><span data-stu-id="2d986-161">Brown</span></span> | <span data-ttu-id="2d986-162">XXL</span><span class="sxs-lookup"><span data-stu-id="2d986-162">XXL</span></span>  |






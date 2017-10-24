---
title: "Termékváltozat-elnevezési rendszer számai és nevei"
description: "Ez a témakör leírja, hogyan állíthat be termékszám-elnevezési rendszert, amelyre lecserélheti a rögzített [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus] formátumot. Az új elnevezési rendszer célzott formátumú, amely magában foglalja az alaptermék számát, az aktív termékdimenziókat és az Ön által választott szöveghatárolókat. A terméknevekhez is létrehozhat elnevezési rendszert. Végül pedig megszorításon alapuló termékkonfiguráló által létrehozott konfigurációk azonosítására szolgáló elnevezési rendszert is létrehozhat. Ezek az elnevezési rendszerek tetszés szerinti attribútumokat tartalmazhatnak."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 4ebebc1d287908dbe8ac7557c34fc6693c88bfae
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="5acbc-107">Termékváltozat-elnevezési rendszer számai és nevei</span><span class="sxs-lookup"><span data-stu-id="5acbc-107">Nomenclature of product variant numbers and names</span></span>

<span data-ttu-id="5acbc-108">Ez a témakör leírja, hogyan állíthat be termékszám-elnevezési rendszert, amelyre lecserélheti a rögzített [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus] formátumot.</span><span class="sxs-lookup"><span data-stu-id="5acbc-108">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="5acbc-109">Az új elnevezési rendszer célzott formátumú, amely magában foglalja az alaptermék számát, az aktív termékdimenziókat és az Ön által választott szöveghatárolókat.</span><span class="sxs-lookup"><span data-stu-id="5acbc-109">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="5acbc-110">A terméknevekhez is létrehozhat elnevezési rendszert.</span><span class="sxs-lookup"><span data-stu-id="5acbc-110">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="5acbc-111">Végül pedig megszorításon alapuló termékkonfiguráló által létrehozott konfigurációk azonosítására szolgáló elnevezési rendszert is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="5acbc-111">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="5acbc-112">Ezek az elnevezési rendszerek tetszés szerinti attribútumokat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="5acbc-112">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="5acbc-113">A termékváltozatszámok és termékváltozatnevek új elnevezési rendszere révén szegmenseket adhat a termékváltozatok azonosítóihoz.</span><span class="sxs-lookup"><span data-stu-id="5acbc-113">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="5acbc-114">Ezek a szegmensek tartalmazhatják az alaptermék számát és nevét, a termékdimenzió-azonosítókat és -neveket, a számsorozatokat, szöveges konstansokat és az attribútumokat.</span><span class="sxs-lookup"><span data-stu-id="5acbc-114">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="5acbc-115">Ezzel egy értékesítési rendelés vagy beszerzési rendelés létrehozásakor gyorsan megtalálhatja a konkrét termékváltozatot.</span><span class="sxs-lookup"><span data-stu-id="5acbc-115">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="5acbc-116">A termékváltozatszámokhoz és termékváltozatnevehez egyaránt a **Termékek elnevezési rendszere** lapon hozhat létre elnevezési rendszert.</span><span class="sxs-lookup"><span data-stu-id="5acbc-116">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="5acbc-117">A lap megnyitásához kattintson a **Termékinformációk kezelése** &gt; **Beállítás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5acbc-117">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="5acbc-118">Előre definiált termékváltozatok termékszámozási rendszere</span><span class="sxs-lookup"><span data-stu-id="5acbc-118">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="5acbc-119">Az alaptermékhez a termékváltozatokat a három konfigurációs technológia közül egyiknek megfelelően generálják:</span><span class="sxs-lookup"><span data-stu-id="5acbc-119">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="5acbc-120">Előre definiált változat</span><span class="sxs-lookup"><span data-stu-id="5acbc-120">Predefined variants</span></span>
-   <span data-ttu-id="5acbc-121">Megszorításon alapuló</span><span class="sxs-lookup"><span data-stu-id="5acbc-121">Constraint-based</span></span>
-   <span data-ttu-id="5acbc-122">Dimenzióalapú</span><span class="sxs-lookup"><span data-stu-id="5acbc-122">Dimension-based</span></span>

<span data-ttu-id="5acbc-123">Minden termékváltozatnak saját száma és neve van, és a termékváltozat-azonosító elnevezési rendszerei segítségével kiválaszthatja az egyes termékváltozatszámokba vagy -nevekbe beemelendő szegmenseket.</span><span class="sxs-lookup"><span data-stu-id="5acbc-123">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="5acbc-124">A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:</span><span class="sxs-lookup"><span data-stu-id="5acbc-124">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="5acbc-125">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="5acbc-125">Product master number</span></span>
-   <span data-ttu-id="5acbc-126">Alaptermék neve</span><span class="sxs-lookup"><span data-stu-id="5acbc-126">Product master name</span></span>
-   <span data-ttu-id="5acbc-127">Számsorozat értéke</span><span class="sxs-lookup"><span data-stu-id="5acbc-127">Number sequence value</span></span>
-   <span data-ttu-id="5acbc-128">Szöveges állandó</span><span class="sxs-lookup"><span data-stu-id="5acbc-128">Text constant</span></span>
-   <span data-ttu-id="5acbc-129">Termékdimenziók</span><span class="sxs-lookup"><span data-stu-id="5acbc-129">Product dimensions</span></span>
    -   <span data-ttu-id="5acbc-130">A konfiguráció azonosítója vagy elnevezése</span><span class="sxs-lookup"><span data-stu-id="5acbc-130">Configuration ID or name</span></span>
    -   <span data-ttu-id="5acbc-131">Szín azonosítója vagy neve</span><span class="sxs-lookup"><span data-stu-id="5acbc-131">Color ID or name</span></span>
    -   <span data-ttu-id="5acbc-132">Méret azonosítója vagy neve</span><span class="sxs-lookup"><span data-stu-id="5acbc-132">Size ID or name</span></span>
    -   <span data-ttu-id="5acbc-133">Stílus azonosítója vagy neve</span><span class="sxs-lookup"><span data-stu-id="5acbc-133">Style ID or name</span></span>

<span data-ttu-id="5acbc-134">A termékváltozat-azonosító számozási rendszerének meghatározása után társíthatja azt egy termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="5acbc-134">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="5acbc-135">A termékdimenzió-csoportra hivatkozó összes alaptermék az elnevezési rendszer alapján termékváltozatszámokat kap.</span><span class="sxs-lookup"><span data-stu-id="5acbc-135">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="5acbc-136">A termékváltozatnevek elnevezési rendszere azonban nem társítható termékdimenzió-csoportokkal.</span><span class="sxs-lookup"><span data-stu-id="5acbc-136">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="5acbc-137">A termékváltozat-azonosító elnevezési rendszerét közvetlenül is hozzárendelheti egy alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="5acbc-137">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="5acbc-138">Ebben az esetben az alaptermékhez tartozó termékváltozatok az elnevezési rendszer alapján kapnak termékváltozatszámokat és -neveket.</span><span class="sxs-lookup"><span data-stu-id="5acbc-138">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="5acbc-139">Példa</span><span class="sxs-lookup"><span data-stu-id="5acbc-139">Example</span></span>

<span data-ttu-id="5acbc-140">Egy póló (TS1234) három méretben (S, M, L), négy színben (piros, zöld, kék, sárga), illetve két stílusban (póló, V-nyakú) érhető el.</span><span class="sxs-lookup"><span data-stu-id="5acbc-140">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="5acbc-141">Emiatt 24 termékváltozat lehetséges (= 3 x 4 x 2).</span><span class="sxs-lookup"><span data-stu-id="5acbc-141">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="5acbc-142">Ön létrehoz egy termékváltozatszám-elnevezési rendszert, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-142">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="5acbc-143">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="5acbc-143">Product master number</span></span>
2.  <span data-ttu-id="5acbc-144">Szöveges állandó: "-"</span><span class="sxs-lookup"><span data-stu-id="5acbc-144">Text constant: "-"</span></span>
3.  <span data-ttu-id="5acbc-145">Szín</span><span class="sxs-lookup"><span data-stu-id="5acbc-145">Color</span></span>
4.  <span data-ttu-id="5acbc-146">Szöveges állandó: "-"</span><span class="sxs-lookup"><span data-stu-id="5acbc-146">Text constant: "-"</span></span>
5.  <span data-ttu-id="5acbc-147">Méret</span><span class="sxs-lookup"><span data-stu-id="5acbc-147">Size</span></span>
6.  <span data-ttu-id="5acbc-148">Szöveges állandó: "-"</span><span class="sxs-lookup"><span data-stu-id="5acbc-148">Text constant: "-"</span></span>
7.  <span data-ttu-id="5acbc-149">Stílus</span><span class="sxs-lookup"><span data-stu-id="5acbc-149">Style</span></span>

<span data-ttu-id="5acbc-150">Ebben az esetben a termékváltozat száma a piros, kicsi póló esetében: TS1234-Piros-Kicsi-Polo.</span><span class="sxs-lookup"><span data-stu-id="5acbc-150">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraintbased-configurations"></a><span data-ttu-id="5acbc-151">Megszorításon alapuló konfigurációk elnevezési rendszere</span><span class="sxs-lookup"><span data-stu-id="5acbc-151">Nomenclature of constraintbased configurations</span></span>
<span data-ttu-id="5acbc-152">A megszorításon alapuló konfigurációk esetében dedikált elnevezési rendszer hozható létre a konfiguráció termékdimenzió számára.</span><span class="sxs-lookup"><span data-stu-id="5acbc-152">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="5acbc-153">A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:</span><span class="sxs-lookup"><span data-stu-id="5acbc-153">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="5acbc-154">Számsorozat értéke</span><span class="sxs-lookup"><span data-stu-id="5acbc-154">Number sequence value</span></span>
-   <span data-ttu-id="5acbc-155">Szöveges állandó</span><span class="sxs-lookup"><span data-stu-id="5acbc-155">Text constant</span></span>
-   <span data-ttu-id="5acbc-156">Attribútumérték</span><span class="sxs-lookup"><span data-stu-id="5acbc-156">Attribute value</span></span>

<span data-ttu-id="5acbc-157">A termékkonfigurációs modell minden egyes összetevőjének saját konfigurációs elnevezési rendszere lehet.</span><span class="sxs-lookup"><span data-stu-id="5acbc-157">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="5acbc-158">Csak az adott komponenshez tartozó attribútumok használhatók.</span><span class="sxs-lookup"><span data-stu-id="5acbc-158">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="5acbc-159">Részösszetevők vagy felhasználói igények attribútumai nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="5acbc-159">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="5acbc-160">Példa</span><span class="sxs-lookup"><span data-stu-id="5acbc-160">Example</span></span>

<span data-ttu-id="5acbc-161">A termékkonfigurációs modell két attribútummal rendelkező gyökérszintű összetevőből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-161">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="5acbc-162">Anyagok (Műanyag, Fa, Acél)</span><span class="sxs-lookup"><span data-stu-id="5acbc-162">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="5acbc-163">Hossz (10.. 100)</span><span class="sxs-lookup"><span data-stu-id="5acbc-163">Length (10...100)</span></span>

<span data-ttu-id="5acbc-164">Ön létrehoz egy konfigurációelnevezési rendszert, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-164">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="5acbc-165">Attribútumérték: Anyag</span><span class="sxs-lookup"><span data-stu-id="5acbc-165">Attribute value: Material</span></span>
2.  <span data-ttu-id="5acbc-166">Szöveges állandó: "AAA"</span><span class="sxs-lookup"><span data-stu-id="5acbc-166">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="5acbc-167">Attribútumérték: Hossz</span><span class="sxs-lookup"><span data-stu-id="5acbc-167">Attribute value: Length</span></span>

<span data-ttu-id="5acbc-168">Ebben az esetben a 78-as hosszúságú faanyag konfigurációs azonosítója a FaAAA78 lesz.</span><span class="sxs-lookup"><span data-stu-id="5acbc-168">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimensionbased-configurations"></a><span data-ttu-id="5acbc-169">Dimenzión alapuló konfigurációk elnevezési rendszere</span><span class="sxs-lookup"><span data-stu-id="5acbc-169">Nomenclature of dimensionbased configurations</span></span>
<span data-ttu-id="5acbc-170">A dimenzión alapuló konfigurációk esetében dedikált elnevezési rendszer hozható létre a konfiguráció termékdimenzió számára.</span><span class="sxs-lookup"><span data-stu-id="5acbc-170">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="5acbc-171">A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:</span><span class="sxs-lookup"><span data-stu-id="5acbc-171">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="5acbc-172">Számsorozat értéke</span><span class="sxs-lookup"><span data-stu-id="5acbc-172">Number sequence value</span></span>
-   <span data-ttu-id="5acbc-173">Szöveges állandó</span><span class="sxs-lookup"><span data-stu-id="5acbc-173">Text constant</span></span>
-   <span data-ttu-id="5acbc-174">Konfigurációs csoport eleme</span><span class="sxs-lookup"><span data-stu-id="5acbc-174">Configuration group item</span></span>

<span data-ttu-id="5acbc-175">Anyagjegyzékhez (BOM) meghatározhat egy konfigurációelnevezési rendszert.</span><span class="sxs-lookup"><span data-stu-id="5acbc-175">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="5acbc-176">Példa</span><span class="sxs-lookup"><span data-stu-id="5acbc-176">Example</span></span>

<span data-ttu-id="5acbc-177">Egy anyagjegyzék négy anyagjegyzéksorral rendelkezik, amelyek két konfigurációs sorra oszlanak:</span><span class="sxs-lookup"><span data-stu-id="5acbc-177">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="5acbc-178">Anyagjegyzéksor: M0007, Standard kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="5acbc-178">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="5acbc-179">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="5acbc-179">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="5acbc-180">AJ-sor: M0008, Nagy záró kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="5acbc-180">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="5acbc-181">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="5acbc-181">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="5acbc-182">AJ-sor: M0021, az első rács szövetből</span><span class="sxs-lookup"><span data-stu-id="5acbc-182">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="5acbc-183">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="5acbc-183">Configuration group: Front grill</span></span>
-   <span data-ttu-id="5acbc-184">AJ-sor: M0022, az első rács fémből</span><span class="sxs-lookup"><span data-stu-id="5acbc-184">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="5acbc-185">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="5acbc-185">Configuration group: Front grill</span></span>

<span data-ttu-id="5acbc-186">Ön létrehoz egy konfigurációelnevezési rendszert, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-186">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="5acbc-187">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="5acbc-187">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="5acbc-188">Szöveges állandó: "&"</span><span class="sxs-lookup"><span data-stu-id="5acbc-188">Text constant: "&"</span></span>
3.  <span data-ttu-id="5acbc-189">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="5acbc-189">Configuration group: Front grill</span></span>

<span data-ttu-id="5acbc-190">Az első rács szövetből standard kabinetfájl konfigurációs azonosítója ebben az esetben: M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="5acbc-190">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="5acbc-191">Termékváltozatok és konfigurációk kombinációjának elnevezési rendszere</span><span class="sxs-lookup"><span data-stu-id="5acbc-191">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="5acbc-192">Akár megszorításon alapuló, akár dimenzión alapuló konfigurációs technológiát használ a termékváltozatok alaptermékre történő konfigurációja esetén, a termékváltozatok olyan termékváltozatszámokat kaphatnak, amelyek tartalmazzák a konfigurációdimenzió elnevezési rendszerét.</span><span class="sxs-lookup"><span data-stu-id="5acbc-192">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="5acbc-193">A változatok konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5acbc-193">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="5acbc-194">A **Termékek elnevezési rendszere** lapon adja meg a termékváltozatszám elnevezési rendszerét, amely tartalmazza a konfigurációdimenziót.</span><span class="sxs-lookup"><span data-stu-id="5acbc-194">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="5acbc-195">Rendelje az elnevezési rendszert egy konfigurációdimenziót tartalmazó termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="5acbc-195">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="5acbc-196">Határozza meg a termékváltozat konfigurálásához használandó összetevők vagy anyagjegyzékek konfigurációs elnevezési rendszerét.</span><span class="sxs-lookup"><span data-stu-id="5acbc-196">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="5acbc-197">A termékváltozatnevekhez is létrehozhat elnevezési rendszereket.</span><span class="sxs-lookup"><span data-stu-id="5acbc-197">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="5acbc-198">A termékváltozatnevek konfigurálhatók úgy, hogy tartalmazzák a konfiguráció azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="5acbc-198">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="5acbc-199">Példák megszorításon alapuló termékkonfigurációkra</span><span class="sxs-lookup"><span data-stu-id="5acbc-199">Example for constraint-based configurations</span></span>

<span data-ttu-id="5acbc-200">Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-200">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="5acbc-201">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="5acbc-201">Product master number</span></span>
2.  <span data-ttu-id="5acbc-202">Szöveges állandó: "\_"</span><span class="sxs-lookup"><span data-stu-id="5acbc-202">Text constant "\_"</span></span>
3.  <span data-ttu-id="5acbc-203">Konfiguráció</span><span class="sxs-lookup"><span data-stu-id="5acbc-203">Configuration</span></span>

<span data-ttu-id="5acbc-204">A konfigurációs elnevezési rendszer a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-204">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="5acbc-205">Attribútumérték: Anyag</span><span class="sxs-lookup"><span data-stu-id="5acbc-205">Attribute value: Material</span></span>
2.  <span data-ttu-id="5acbc-206">Szöveges állandó: "AAA"</span><span class="sxs-lookup"><span data-stu-id="5acbc-206">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="5acbc-207">Attribútumérték: Hossz</span><span class="sxs-lookup"><span data-stu-id="5acbc-207">Attribute value: Length</span></span>

<span data-ttu-id="5acbc-208">A szegmensekhez a következő értékeket adja meg:</span><span class="sxs-lookup"><span data-stu-id="5acbc-208">You enter the following values for segments:</span></span>

-   <span data-ttu-id="5acbc-209">Alaptermék száma = **M0099**</span><span class="sxs-lookup"><span data-stu-id="5acbc-209">Product master number = **M0099**</span></span>
-   <span data-ttu-id="5acbc-210">Anyag = **Műanyag**</span><span class="sxs-lookup"><span data-stu-id="5acbc-210">Material = **Plastic**</span></span>
-   <span data-ttu-id="5acbc-211">Hossz = **12**</span><span class="sxs-lookup"><span data-stu-id="5acbc-211">Length = **12**</span></span>

<span data-ttu-id="5acbc-212">A termékváltozat száma ebben az esetben: M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="5acbc-212">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="5acbc-213">Példák dimenzión alapuló konfigurációkra</span><span class="sxs-lookup"><span data-stu-id="5acbc-213">Example for dimension-based configurations</span></span>

<span data-ttu-id="5acbc-214">Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-214">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="5acbc-215">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="5acbc-215">Product master number</span></span>
2.  <span data-ttu-id="5acbc-216">Szöveges állandó: "//"</span><span class="sxs-lookup"><span data-stu-id="5acbc-216">Text constant "//"</span></span>
3.  <span data-ttu-id="5acbc-217">Konfiguráció</span><span class="sxs-lookup"><span data-stu-id="5acbc-217">Configuration</span></span>

<span data-ttu-id="5acbc-218">A konfigurációs elnevezési rendszer a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="5acbc-218">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="5acbc-219">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="5acbc-219">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="5acbc-220">Szöveges állandó: "&"</span><span class="sxs-lookup"><span data-stu-id="5acbc-220">Text constant: "&"</span></span>
3.  <span data-ttu-id="5acbc-221">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="5acbc-221">Configuration group: Front grill</span></span>

<span data-ttu-id="5acbc-222">A szegmensekhez a következő értékeket adja meg:</span><span class="sxs-lookup"><span data-stu-id="5acbc-222">You enter the following values for segments:</span></span>

-   <span data-ttu-id="5acbc-223">Alaptermék száma = **D0123**</span><span class="sxs-lookup"><span data-stu-id="5acbc-223">Product master number = **D0123**</span></span>
-   <span data-ttu-id="5acbc-224">Kabinet = **M0008**</span><span class="sxs-lookup"><span data-stu-id="5acbc-224">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="5acbc-225">Elülső rács = **M0022**</span><span class="sxs-lookup"><span data-stu-id="5acbc-225">Front grill = **M0022**</span></span>

<span data-ttu-id="5acbc-226">A termékváltozat száma ebben az esetben: D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="5acbc-226">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="5acbc-227">Ütközések számozása</span><span class="sxs-lookup"><span data-stu-id="5acbc-227">Numbering conflicts</span></span>
<span data-ttu-id="5acbc-228">Bizonyos esetekben lehetőség van olyan termékváltozat-számozási rendszer beállítására, amely nem hoz létre egyedi termékváltozatszámokat.</span><span class="sxs-lookup"><span data-stu-id="5acbc-228">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="5acbc-229">Például a termékváltozatszámok nem lehetnek egyediek, ha egy aktív termékdimenzió nem szerepel az alaptermék előre definiált változatkonfigurálási technológiát használó elnevezési rendszerében.</span><span class="sxs-lookup"><span data-stu-id="5acbc-229">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="5acbc-230">Az ütközések kezelési módja eltérő a konfigurációs technológiától függően.</span><span class="sxs-lookup"><span data-stu-id="5acbc-230">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="5acbc-231">Előre definiált változatok</span><span class="sxs-lookup"><span data-stu-id="5acbc-231">Predefined variants</span></span>

<span data-ttu-id="5acbc-232">Hiba lép fel, ha kézzel vagy automatikusan próbál termékváltozatokat létrehozni olyankor, amikor egy vagy több termékváltozat ugyanazon termékváltozatszámmal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="5acbc-232">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="5acbc-233">Ennek elkerülése érdekében használja az összes aktív termékdimenziót a termékdimenzió-csoportból.</span><span class="sxs-lookup"><span data-stu-id="5acbc-233">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="5acbc-234">Másik lehetőségként megadhat egy számsorozatot annak érdekében, hogy a termékváltozatszámok egyediek legyenek.</span><span class="sxs-lookup"><span data-stu-id="5acbc-234">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="5acbc-235">Megszorításon alapuló konfigurációk</span><span class="sxs-lookup"><span data-stu-id="5acbc-235">Constraint-based configurations</span></span>

<span data-ttu-id="5acbc-236">Az elnevezési rendszertől függően a rendszer megkísérelhet nem egyedi számot hozzárendelni egy konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="5acbc-236">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="5acbc-237">Ilyenkor a rendszer a konfigurációdimenzió számsorozatát fogja használni a termékváltozatszám helyett. Ebben az esetben egy figyelmeztetést fog kapni.</span><span class="sxs-lookup"><span data-stu-id="5acbc-237">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="5acbc-238">Ennek elkerülése érdekében elég attribútumot kell szerepeltetni az elnevezési rendszerben, hogy egyedi termékváltozat-számok lehessenek.</span><span class="sxs-lookup"><span data-stu-id="5acbc-238">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="5acbc-239">Arról is gondoskodnia kell, hogy az **Újra** beállítás engedélyezve van az összetevőnél.</span><span class="sxs-lookup"><span data-stu-id="5acbc-239">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="5acbc-240">Dimenzión alapuló konfigurációk</span><span class="sxs-lookup"><span data-stu-id="5acbc-240">Dimension-based configurations</span></span>

<span data-ttu-id="5acbc-241">A konfigurálási folyamat egyik lépésében a rendszer az elnevezési rendszernek megfelelő konfigurációs értéket fog javasolni.</span><span class="sxs-lookup"><span data-stu-id="5acbc-241">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="5acbc-242">Ebben a lépésben manuálisan módosíthatja a konfigurációs értéket.</span><span class="sxs-lookup"><span data-stu-id="5acbc-242">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="5acbc-243">A konfiguráció mentésekor a rendszer ellenőrzi, hogy konfigurációs érték egyedi-e.</span><span class="sxs-lookup"><span data-stu-id="5acbc-243">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="5acbc-244">Ha a megadott érték nem egyedi, akkor megjelenik egy hibaüzenet.</span><span class="sxs-lookup"><span data-stu-id="5acbc-244">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="5acbc-245">A konfiguráció mentéséhez meg kell adnia egy egyedi konfigurációs értéket.</span><span class="sxs-lookup"><span data-stu-id="5acbc-245">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="5acbc-246">Lásd még</span><span class="sxs-lookup"><span data-stu-id="5acbc-246">See also</span></span>
--------

[<span data-ttu-id="5acbc-247">Termékszámozási rendszer létrehozása előre definiált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="5acbc-247">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="5acbc-248">Termékszámozás-elnevezési rendszer létrehozása konfigurált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="5acbc-248">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)



---
title: Termékváltozat-elnevezési rendszer számai és nevei
description: Ez a témakör leírja, hogyan állíthat be termékszám-elnevezési rendszert, amelyre lecserélheti a rögzített [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus] formátumot.
author: roxanadiaconu
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 90c01e4281246d890ef888c56ca137f83e83741c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429288"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="a84d0-103">Termékváltozat-elnevezési rendszer számai és nevei</span><span class="sxs-lookup"><span data-stu-id="a84d0-103">Nomenclature of product variant numbers and names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a84d0-104">Ez a témakör leírja, hogyan állíthat be termékszám-elnevezési rendszert, amelyre lecserélheti a rögzített [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus] formátumot.</span><span class="sxs-lookup"><span data-stu-id="a84d0-104">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="a84d0-105">Az új elnevezési rendszer célzott formátumú, amely magában foglalja az alaptermék számát, az aktív termékdimenziókat és az Ön által választott szöveghatárolókat.</span><span class="sxs-lookup"><span data-stu-id="a84d0-105">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="a84d0-106">A terméknevekhez is létrehozhat elnevezési rendszert.</span><span class="sxs-lookup"><span data-stu-id="a84d0-106">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="a84d0-107">Végül pedig megszorításon alapuló termékkonfiguráló által létrehozott konfigurációk azonosítására szolgáló elnevezési rendszert is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="a84d0-107">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="a84d0-108">Ezek az elnevezési rendszerek tetszés szerinti attribútumokat tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="a84d0-108">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="a84d0-109">A termékváltozatszámok és termékváltozatnevek új elnevezési rendszere révén szegmenseket adhat a termékváltozatok azonosítóihoz.</span><span class="sxs-lookup"><span data-stu-id="a84d0-109">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="a84d0-110">Ezek a szegmensek tartalmazhatják az alaptermék számát és nevét, a termékdimenzió-azonosítókat és -neveket, a számsorozatokat, szöveges konstansokat és az attribútumokat.</span><span class="sxs-lookup"><span data-stu-id="a84d0-110">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="a84d0-111">Ezzel egy értékesítési rendelés vagy beszerzési rendelés létrehozásakor gyorsan megtalálhatja a konkrét termékváltozatot.</span><span class="sxs-lookup"><span data-stu-id="a84d0-111">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="a84d0-112">A termékváltozatszámokhoz és termékváltozatnevehez egyaránt a **Termékek elnevezési rendszere** lapon hozhat létre elnevezési rendszert.</span><span class="sxs-lookup"><span data-stu-id="a84d0-112">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="a84d0-113">A lap megnyitásához kattintson a **Termékinformációk kezelése** &gt; **Beállítás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a84d0-113">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="a84d0-114">Előre definiált termékváltozatok termékszámozási rendszere</span><span class="sxs-lookup"><span data-stu-id="a84d0-114">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="a84d0-115">Az alaptermékhez a termékváltozatokat a három konfigurációs technológia közül egyiknek megfelelően generálják:</span><span class="sxs-lookup"><span data-stu-id="a84d0-115">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="a84d0-116">Előre definiált változat</span><span class="sxs-lookup"><span data-stu-id="a84d0-116">Predefined variants</span></span>
-   <span data-ttu-id="a84d0-117">Megszorításon alapuló</span><span class="sxs-lookup"><span data-stu-id="a84d0-117">Constraint-based</span></span>
-   <span data-ttu-id="a84d0-118">Dimenzióalapú</span><span class="sxs-lookup"><span data-stu-id="a84d0-118">Dimension-based</span></span>

<span data-ttu-id="a84d0-119">Minden termékváltozatnak saját száma és neve van, és a termékváltozat-azonosító elnevezési rendszerei segítségével kiválaszthatja az egyes termékváltozatszámokba vagy -nevekbe beemelendő szegmenseket.</span><span class="sxs-lookup"><span data-stu-id="a84d0-119">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="a84d0-120">A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:</span><span class="sxs-lookup"><span data-stu-id="a84d0-120">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="a84d0-121">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="a84d0-121">Product master number</span></span>
-   <span data-ttu-id="a84d0-122">Alaptermék neve</span><span class="sxs-lookup"><span data-stu-id="a84d0-122">Product master name</span></span>
-   <span data-ttu-id="a84d0-123">Számsorozat értéke</span><span class="sxs-lookup"><span data-stu-id="a84d0-123">Number sequence value</span></span>
-   <span data-ttu-id="a84d0-124">Szöveges állandó</span><span class="sxs-lookup"><span data-stu-id="a84d0-124">Text constant</span></span>
-   <span data-ttu-id="a84d0-125">Termékdimenziók</span><span class="sxs-lookup"><span data-stu-id="a84d0-125">Product dimensions</span></span>
    -   <span data-ttu-id="a84d0-126">A konfiguráció azonosítója vagy elnevezése</span><span class="sxs-lookup"><span data-stu-id="a84d0-126">Configuration ID or name</span></span>
    -   <span data-ttu-id="a84d0-127">Szín azonosítója vagy neve</span><span class="sxs-lookup"><span data-stu-id="a84d0-127">Color ID or name</span></span>
    -   <span data-ttu-id="a84d0-128">Méret azonosítója vagy neve</span><span class="sxs-lookup"><span data-stu-id="a84d0-128">Size ID or name</span></span>
    -   <span data-ttu-id="a84d0-129">Stílus azonosítója vagy neve</span><span class="sxs-lookup"><span data-stu-id="a84d0-129">Style ID or name</span></span>

<span data-ttu-id="a84d0-130">A termékváltozat-azonosító számozási rendszerének meghatározása után társíthatja azt egy termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="a84d0-130">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="a84d0-131">A termékdimenzió-csoportra hivatkozó összes alaptermék az elnevezési rendszer alapján termékváltozatszámokat kap.</span><span class="sxs-lookup"><span data-stu-id="a84d0-131">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="a84d0-132">A termékváltozatnevek elnevezési rendszere azonban nem társítható termékdimenzió-csoportokkal.</span><span class="sxs-lookup"><span data-stu-id="a84d0-132">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="a84d0-133">A termékváltozat-azonosító elnevezési rendszerét közvetlenül is hozzárendelheti egy alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="a84d0-133">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="a84d0-134">Ebben az esetben az alaptermékhez tartozó termékváltozatok az elnevezési rendszer alapján kapnak termékváltozatszámokat és -neveket.</span><span class="sxs-lookup"><span data-stu-id="a84d0-134">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="a84d0-135">Példa</span><span class="sxs-lookup"><span data-stu-id="a84d0-135">Example</span></span>

<span data-ttu-id="a84d0-136">Egy póló (TS1234) három méretben (S, M, L), négy színben (piros, zöld, kék, sárga), illetve két stílusban (póló, V-nyakú) érhető el.</span><span class="sxs-lookup"><span data-stu-id="a84d0-136">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="a84d0-137">Emiatt 24 termékváltozat lehetséges (= 3 x 4 x 2).</span><span class="sxs-lookup"><span data-stu-id="a84d0-137">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="a84d0-138">Ön létrehoz egy termékváltozatszám-elnevezési rendszert, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-138">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="a84d0-139">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="a84d0-139">Product master number</span></span>
2.  <span data-ttu-id="a84d0-140">Szöveges állandó: "-"</span><span class="sxs-lookup"><span data-stu-id="a84d0-140">Text constant: "-"</span></span>
3.  <span data-ttu-id="a84d0-141">Szín</span><span class="sxs-lookup"><span data-stu-id="a84d0-141">Color</span></span>
4.  <span data-ttu-id="a84d0-142">Szöveges állandó: "-"</span><span class="sxs-lookup"><span data-stu-id="a84d0-142">Text constant: "-"</span></span>
5.  <span data-ttu-id="a84d0-143">Méret</span><span class="sxs-lookup"><span data-stu-id="a84d0-143">Size</span></span>
6.  <span data-ttu-id="a84d0-144">Szöveges állandó: "-"</span><span class="sxs-lookup"><span data-stu-id="a84d0-144">Text constant: "-"</span></span>
7.  <span data-ttu-id="a84d0-145">Stílus</span><span class="sxs-lookup"><span data-stu-id="a84d0-145">Style</span></span>

<span data-ttu-id="a84d0-146">Ebben az esetben a termékváltozat száma a piros, kicsi póló esetében: TS1234-Piros-Kicsi-Polo.</span><span class="sxs-lookup"><span data-stu-id="a84d0-146">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraint-based-configurations"></a><span data-ttu-id="a84d0-147">Megszorításon alapuló konfigurációk elnevezési rendszere</span><span class="sxs-lookup"><span data-stu-id="a84d0-147">Nomenclature of constraint-based configurations</span></span>
<span data-ttu-id="a84d0-148">A megszorításon alapuló konfigurációk esetében dedikált elnevezési rendszer hozható létre a konfiguráció termékdimenzió számára.</span><span class="sxs-lookup"><span data-stu-id="a84d0-148">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="a84d0-149">A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:</span><span class="sxs-lookup"><span data-stu-id="a84d0-149">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="a84d0-150">Számsorozat értéke</span><span class="sxs-lookup"><span data-stu-id="a84d0-150">Number sequence value</span></span>
-   <span data-ttu-id="a84d0-151">Szöveges állandó</span><span class="sxs-lookup"><span data-stu-id="a84d0-151">Text constant</span></span>
-   <span data-ttu-id="a84d0-152">Attribútumérték</span><span class="sxs-lookup"><span data-stu-id="a84d0-152">Attribute value</span></span>

<span data-ttu-id="a84d0-153">A termékkonfigurációs modell minden egyes összetevőjének saját konfigurációs elnevezési rendszere lehet.</span><span class="sxs-lookup"><span data-stu-id="a84d0-153">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="a84d0-154">Csak az adott komponenshez tartozó attribútumok használhatók.</span><span class="sxs-lookup"><span data-stu-id="a84d0-154">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="a84d0-155">Részösszetevők vagy felhasználói igények attribútumai nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="a84d0-155">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="a84d0-156">Példa</span><span class="sxs-lookup"><span data-stu-id="a84d0-156">Example</span></span>

<span data-ttu-id="a84d0-157">A termékkonfigurációs modell két attribútummal rendelkező gyökérszintű összetevőből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-157">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="a84d0-158">Anyagok (Műanyag, Fa, Acél)</span><span class="sxs-lookup"><span data-stu-id="a84d0-158">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="a84d0-159">Hossz (10.. 100)</span><span class="sxs-lookup"><span data-stu-id="a84d0-159">Length (10...100)</span></span>

<span data-ttu-id="a84d0-160">Ön létrehoz egy konfigurációelnevezési rendszert, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-160">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="a84d0-161">Attribútumérték: Anyag</span><span class="sxs-lookup"><span data-stu-id="a84d0-161">Attribute value: Material</span></span>
2.  <span data-ttu-id="a84d0-162">Szöveges állandó: "AAA"</span><span class="sxs-lookup"><span data-stu-id="a84d0-162">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="a84d0-163">Attribútumérték: Hossz</span><span class="sxs-lookup"><span data-stu-id="a84d0-163">Attribute value: Length</span></span>

<span data-ttu-id="a84d0-164">Ebben az esetben a 78-as hosszúságú faanyag konfigurációs azonosítója a FaAAA78 lesz.</span><span class="sxs-lookup"><span data-stu-id="a84d0-164">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimension-based-configurations"></a><span data-ttu-id="a84d0-165">Dimenzión alapuló konfigurációk elnevezési rendszere</span><span class="sxs-lookup"><span data-stu-id="a84d0-165">Nomenclature of dimension-based configurations</span></span>
<span data-ttu-id="a84d0-166">A dimenzión alapuló konfigurációk esetében dedikált elnevezési rendszer hozható létre a konfiguráció termékdimenzió számára.</span><span class="sxs-lookup"><span data-stu-id="a84d0-166">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="a84d0-167">A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:</span><span class="sxs-lookup"><span data-stu-id="a84d0-167">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="a84d0-168">Számsorozat értéke</span><span class="sxs-lookup"><span data-stu-id="a84d0-168">Number sequence value</span></span>
-   <span data-ttu-id="a84d0-169">Szöveges állandó</span><span class="sxs-lookup"><span data-stu-id="a84d0-169">Text constant</span></span>
-   <span data-ttu-id="a84d0-170">Konfigurációs csoport eleme</span><span class="sxs-lookup"><span data-stu-id="a84d0-170">Configuration group item</span></span>

<span data-ttu-id="a84d0-171">Anyagjegyzékhez (BOM) meghatározhat egy konfigurációelnevezési rendszert.</span><span class="sxs-lookup"><span data-stu-id="a84d0-171">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="a84d0-172">Példa</span><span class="sxs-lookup"><span data-stu-id="a84d0-172">Example</span></span>

<span data-ttu-id="a84d0-173">Egy anyagjegyzék négy anyagjegyzéksorral rendelkezik, amelyek két konfigurációs sorra oszlanak:</span><span class="sxs-lookup"><span data-stu-id="a84d0-173">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="a84d0-174">Anyagjegyzéksor: M0007, Standard kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="a84d0-174">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="a84d0-175">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="a84d0-175">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="a84d0-176">AJ-sor: M0008, Nagy záró kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="a84d0-176">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="a84d0-177">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="a84d0-177">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="a84d0-178">AJ-sor: M0021, az első rács szövetből</span><span class="sxs-lookup"><span data-stu-id="a84d0-178">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="a84d0-179">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="a84d0-179">Configuration group: Front grill</span></span>
-   <span data-ttu-id="a84d0-180">AJ-sor: M0022, az első rács fémből</span><span class="sxs-lookup"><span data-stu-id="a84d0-180">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="a84d0-181">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="a84d0-181">Configuration group: Front grill</span></span>

<span data-ttu-id="a84d0-182">Ön létrehoz egy konfigurációelnevezési rendszert, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-182">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="a84d0-183">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="a84d0-183">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="a84d0-184">Szöveges állandó: "&"</span><span class="sxs-lookup"><span data-stu-id="a84d0-184">Text constant: "&"</span></span>
3.  <span data-ttu-id="a84d0-185">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="a84d0-185">Configuration group: Front grill</span></span>

<span data-ttu-id="a84d0-186">Az első rács szövetből standard kabinetfájl konfigurációs azonosítója ebben az esetben: M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="a84d0-186">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="a84d0-187">Termékváltozatok és konfigurációk kombinációjának elnevezési rendszere</span><span class="sxs-lookup"><span data-stu-id="a84d0-187">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="a84d0-188">Akár megszorításon alapuló, akár dimenzión alapuló konfigurációs technológiát használ a termékváltozatok alaptermékre történő konfigurációja esetén, a termékváltozatok olyan termékváltozatszámokat kaphatnak, amelyek tartalmazzák a konfigurációdimenzió elnevezési rendszerét.</span><span class="sxs-lookup"><span data-stu-id="a84d0-188">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="a84d0-189">A változatok konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a84d0-189">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="a84d0-190">A **Termékek elnevezési rendszere** lapon adja meg a termékváltozatszám elnevezési rendszerét, amely tartalmazza a konfigurációdimenziót.</span><span class="sxs-lookup"><span data-stu-id="a84d0-190">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="a84d0-191">Rendelje az elnevezési rendszert egy konfigurációdimenziót tartalmazó termékdimenzió-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="a84d0-191">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="a84d0-192">Határozza meg a termékváltozat konfigurálásához használandó összetevők vagy anyagjegyzékek konfigurációs elnevezési rendszerét.</span><span class="sxs-lookup"><span data-stu-id="a84d0-192">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="a84d0-193">A termékváltozatnevekhez is létrehozhat elnevezési rendszereket.</span><span class="sxs-lookup"><span data-stu-id="a84d0-193">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="a84d0-194">A termékváltozatnevek konfigurálhatók úgy, hogy tartalmazzák a konfiguráció azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="a84d0-194">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="a84d0-195">Példák megszorításon alapuló termékkonfigurációkra</span><span class="sxs-lookup"><span data-stu-id="a84d0-195">Example for constraint-based configurations</span></span>

<span data-ttu-id="a84d0-196">Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-196">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="a84d0-197">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="a84d0-197">Product master number</span></span>
2.  <span data-ttu-id="a84d0-198">Szöveges állandó: "\_"</span><span class="sxs-lookup"><span data-stu-id="a84d0-198">Text constant "\_"</span></span>
3.  <span data-ttu-id="a84d0-199">Konfiguráció</span><span class="sxs-lookup"><span data-stu-id="a84d0-199">Configuration</span></span>

<span data-ttu-id="a84d0-200">A konfigurációs elnevezési rendszer a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-200">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="a84d0-201">Attribútumérték: Anyag</span><span class="sxs-lookup"><span data-stu-id="a84d0-201">Attribute value: Material</span></span>
2.  <span data-ttu-id="a84d0-202">Szöveges állandó: "AAA"</span><span class="sxs-lookup"><span data-stu-id="a84d0-202">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="a84d0-203">Attribútumérték: Hossz</span><span class="sxs-lookup"><span data-stu-id="a84d0-203">Attribute value: Length</span></span>

<span data-ttu-id="a84d0-204">A szegmensekhez a következő értékeket adja meg:</span><span class="sxs-lookup"><span data-stu-id="a84d0-204">You enter the following values for segments:</span></span>

-   <span data-ttu-id="a84d0-205">Alaptermék száma = **M0099**</span><span class="sxs-lookup"><span data-stu-id="a84d0-205">Product master number = **M0099**</span></span>
-   <span data-ttu-id="a84d0-206">Anyag = **Műanyag**</span><span class="sxs-lookup"><span data-stu-id="a84d0-206">Material = **Plastic**</span></span>
-   <span data-ttu-id="a84d0-207">Hossz = **12**</span><span class="sxs-lookup"><span data-stu-id="a84d0-207">Length = **12**</span></span>

<span data-ttu-id="a84d0-208">A termékváltozat száma ebben az esetben: M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="a84d0-208">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="a84d0-209">Példák dimenzión alapuló konfigurációkra</span><span class="sxs-lookup"><span data-stu-id="a84d0-209">Example for dimension-based configurations</span></span>

<span data-ttu-id="a84d0-210">Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-210">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="a84d0-211">Alaptermék száma</span><span class="sxs-lookup"><span data-stu-id="a84d0-211">Product master number</span></span>
2.  <span data-ttu-id="a84d0-212">Szöveges állandó: "//"</span><span class="sxs-lookup"><span data-stu-id="a84d0-212">Text constant "//"</span></span>
3.  <span data-ttu-id="a84d0-213">Konfiguráció</span><span class="sxs-lookup"><span data-stu-id="a84d0-213">Configuration</span></span>

<span data-ttu-id="a84d0-214">A konfigurációs elnevezési rendszer a következő szegmensekből áll:</span><span class="sxs-lookup"><span data-stu-id="a84d0-214">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="a84d0-215">Konfigurációs csoport: Kabinetfájl</span><span class="sxs-lookup"><span data-stu-id="a84d0-215">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="a84d0-216">Szöveges állandó: "&"</span><span class="sxs-lookup"><span data-stu-id="a84d0-216">Text constant: "&"</span></span>
3.  <span data-ttu-id="a84d0-217">Konfigurációs csoport: Első rács</span><span class="sxs-lookup"><span data-stu-id="a84d0-217">Configuration group: Front grill</span></span>

<span data-ttu-id="a84d0-218">A szegmensekhez a következő értékeket adja meg:</span><span class="sxs-lookup"><span data-stu-id="a84d0-218">You enter the following values for segments:</span></span>

-   <span data-ttu-id="a84d0-219">Alaptermék száma = **D0123**</span><span class="sxs-lookup"><span data-stu-id="a84d0-219">Product master number = **D0123**</span></span>
-   <span data-ttu-id="a84d0-220">Kabinet = **M0008**</span><span class="sxs-lookup"><span data-stu-id="a84d0-220">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="a84d0-221">Elülső rács = **M0022**</span><span class="sxs-lookup"><span data-stu-id="a84d0-221">Front grill = **M0022**</span></span>

<span data-ttu-id="a84d0-222">A termékváltozat száma ebben az esetben: D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="a84d0-222">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="a84d0-223">Ütközések számozása</span><span class="sxs-lookup"><span data-stu-id="a84d0-223">Numbering conflicts</span></span>
<span data-ttu-id="a84d0-224">Bizonyos esetekben lehetőség van olyan termékváltozat-számozási rendszer beállítására, amely nem hoz létre egyedi termékváltozatszámokat.</span><span class="sxs-lookup"><span data-stu-id="a84d0-224">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="a84d0-225">Például a termékváltozatszámok nem lehetnek egyediek, ha egy aktív termékdimenzió nem szerepel az alaptermék előre definiált változatkonfigurálási technológiát használó elnevezési rendszerében.</span><span class="sxs-lookup"><span data-stu-id="a84d0-225">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="a84d0-226">Az ütközések kezelési módja eltérő a konfigurációs technológiától függően.</span><span class="sxs-lookup"><span data-stu-id="a84d0-226">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="a84d0-227">Előre definiált változatok</span><span class="sxs-lookup"><span data-stu-id="a84d0-227">Predefined variants</span></span>

<span data-ttu-id="a84d0-228">Hiba lép fel, ha kézzel vagy automatikusan próbál termékváltozatokat létrehozni olyankor, amikor egy vagy több termékváltozat ugyanazon termékváltozatszámmal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="a84d0-228">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="a84d0-229">Ennek elkerülése érdekében használja az összes aktív termékdimenziót a termékdimenzió-csoportból.</span><span class="sxs-lookup"><span data-stu-id="a84d0-229">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="a84d0-230">Másik lehetőségként megadhat egy számsorozatot annak érdekében, hogy a termékváltozatszámok egyediek legyenek.</span><span class="sxs-lookup"><span data-stu-id="a84d0-230">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="a84d0-231">Megszorításon alapuló konfigurációk</span><span class="sxs-lookup"><span data-stu-id="a84d0-231">Constraint-based configurations</span></span>

<span data-ttu-id="a84d0-232">Az elnevezési rendszertől függően a rendszer megkísérelhet nem egyedi számot hozzárendelni egy konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="a84d0-232">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="a84d0-233">Ilyenkor a rendszer a konfigurációdimenzió számsorozatát fogja használni a termékváltozatszám helyett. Ebben az esetben egy figyelmeztetést fog kapni.</span><span class="sxs-lookup"><span data-stu-id="a84d0-233">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="a84d0-234">Ennek elkerülése érdekében elég attribútumot kell szerepeltetni az elnevezési rendszerben, hogy egyedi termékváltozat-számok lehessenek.</span><span class="sxs-lookup"><span data-stu-id="a84d0-234">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="a84d0-235">Arról is gondoskodnia kell, hogy az **Újra** beállítás engedélyezve van az összetevőnél.</span><span class="sxs-lookup"><span data-stu-id="a84d0-235">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="a84d0-236">Dimenzión alapuló konfigurációk</span><span class="sxs-lookup"><span data-stu-id="a84d0-236">Dimension-based configurations</span></span>

<span data-ttu-id="a84d0-237">A konfigurálási folyamat egyik lépésében a rendszer az elnevezési rendszernek megfelelő konfigurációs értéket fog javasolni.</span><span class="sxs-lookup"><span data-stu-id="a84d0-237">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="a84d0-238">Ebben a lépésben manuálisan módosíthatja a konfigurációs értéket.</span><span class="sxs-lookup"><span data-stu-id="a84d0-238">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="a84d0-239">A konfiguráció mentésekor a rendszer ellenőrzi, hogy konfigurációs érték egyedi-e.</span><span class="sxs-lookup"><span data-stu-id="a84d0-239">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="a84d0-240">Ha a megadott érték nem egyedi, akkor megjelenik egy hibaüzenet.</span><span class="sxs-lookup"><span data-stu-id="a84d0-240">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="a84d0-241">A konfiguráció mentéséhez meg kell adnia egy egyedi konfigurációs értéket.</span><span class="sxs-lookup"><span data-stu-id="a84d0-241">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="additional-resources"></a><span data-ttu-id="a84d0-242">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a84d0-242">Additional resources</span></span>
--------

[<span data-ttu-id="a84d0-243">Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="a84d0-243">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="a84d0-244">Termékszámozás-elnevezési rendszer létrehozása konfigurált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="a84d0-244">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)


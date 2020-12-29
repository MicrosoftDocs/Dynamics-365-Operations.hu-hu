---
title: A termékkonfigurációs modellek kifejezésmegszorításai
description: Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások. Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be9d9ae48d21db077928ba7bd5615fea47ea5181
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429716"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="db0f8-105">A termékkonfigurációs modellek kifejezésmegszorításai</span><span class="sxs-lookup"><span data-stu-id="db0f8-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db0f8-106">Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások.</span><span class="sxs-lookup"><span data-stu-id="db0f8-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="db0f8-107">Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor.</span><span class="sxs-lookup"><span data-stu-id="db0f8-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="db0f8-108">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="db0f8-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="db0f8-109">Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor.</span><span class="sxs-lookup"><span data-stu-id="db0f8-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="db0f8-110">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="db0f8-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="db0f8-111">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="db0f8-111">What are expression constraints?</span></span>
<span data-ttu-id="db0f8-112">Kifejezés megszorítások jellemző aritmetikai és logikai operátort és függvényt használó kifejezést.</span><span class="sxs-lookup"><span data-stu-id="db0f8-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="db0f8-113">A termékkonfigurációs modell adott összetevő egy Kifejezésmegszorítás készült.</span><span class="sxs-lookup"><span data-stu-id="db0f8-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="db0f8-114">Nem használja fel újra, és egy másik összetevő megosztva.</span><span class="sxs-lookup"><span data-stu-id="db0f8-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="db0f8-115">Egy összetevőre vonatkozó kifejezés megszorításai az összetevők részösszetevőinek attribútumaira is hivatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="db0f8-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="db0f8-116">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="db0f8-116">What are table constraints?</span></span>
<span data-ttu-id="db0f8-117">Táblamegszorítások-kombinációkat termék konfigurálásakor attribútumok megengedett értékek listája.</span><span class="sxs-lookup"><span data-stu-id="db0f8-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="db0f8-118">Táblamegszorítási definíciók általában használható.</span><span class="sxs-lookup"><span data-stu-id="db0f8-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="db0f8-119">A termékkonfigurációs modell összetevőhöz táblamegszorítás létrehozásakor ki kell választania egy táblamegszorítás definíciója.</span><span class="sxs-lookup"><span data-stu-id="db0f8-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="db0f8-120">A megengedett kombinációk létrehozásához hozzáadja az összetevők különféle jellemzőit.</span><span class="sxs-lookup"><span data-stu-id="db0f8-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="db0f8-121">Minden egyes attribútumtípus egy adott értékű.</span><span class="sxs-lookup"><span data-stu-id="db0f8-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="db0f8-122">Táblamegszorítás típusa</span><span class="sxs-lookup"><span data-stu-id="db0f8-122">Example of a table constraint</span></span>

<span data-ttu-id="db0f8-123">Ez a példa azt mutatja, hogyan korlátozhatja egy adott kabinetfájl befejeződik és előlapot hangszóró konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="db0f8-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="db0f8-124">Az első táblázat mutatja a méreteket és a televízió, általában elérhető konfigurációs típusú.</span><span class="sxs-lookup"><span data-stu-id="db0f8-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="db0f8-125">Határozhatók meg az értékeket a **Kabinetfájl befejezés** és **Első rács** attribútum típusa.</span><span class="sxs-lookup"><span data-stu-id="db0f8-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="db0f8-126">Attribútumtípus</span><span class="sxs-lookup"><span data-stu-id="db0f8-126">Attribute type</span></span> | <span data-ttu-id="db0f8-127">Értékek</span><span class="sxs-lookup"><span data-stu-id="db0f8-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="db0f8-128">Hangszóró borítása</span><span class="sxs-lookup"><span data-stu-id="db0f8-128">Cabinet finish</span></span> | <span data-ttu-id="db0f8-129">Fekete, tölgyfa, rózsafa, fehér</span><span class="sxs-lookup"><span data-stu-id="db0f8-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="db0f8-130">Elülső rács</span><span class="sxs-lookup"><span data-stu-id="db0f8-130">Front grill</span></span>    | <span data-ttu-id="db0f8-131">Fekete, fém, fehér</span><span class="sxs-lookup"><span data-stu-id="db0f8-131">Black, Metal, White</span></span>         |

<span data-ttu-id="db0f8-132">A következő táblázat bemutatja a kombinációk határozzák meg, hogy a **Szín és kivitel** táblamegszorítás.</span><span class="sxs-lookup"><span data-stu-id="db0f8-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="db0f8-133">A táblamegszorítás használatával konfigurálhatja egy tölgy Befejezés és fekete ráccsal, egy rózsafa Befejezés és fehér rács előadó, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="db0f8-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="db0f8-134">Elvégzés</span><span class="sxs-lookup"><span data-stu-id="db0f8-134">Finish</span></span>         | <span data-ttu-id="db0f8-135">Rács</span><span class="sxs-lookup"><span data-stu-id="db0f8-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="db0f8-136">Tölgyfa</span><span class="sxs-lookup"><span data-stu-id="db0f8-136">Oak</span></span>            | <span data-ttu-id="db0f8-137">Fekete</span><span class="sxs-lookup"><span data-stu-id="db0f8-137">Black</span></span>                       |
| <span data-ttu-id="db0f8-138">Rózsafa</span><span class="sxs-lookup"><span data-stu-id="db0f8-138">Rosewood</span></span>       | <span data-ttu-id="db0f8-139">Fehér</span><span class="sxs-lookup"><span data-stu-id="db0f8-139">White</span></span>                       |
| <span data-ttu-id="db0f8-140">Fehér</span><span class="sxs-lookup"><span data-stu-id="db0f8-140">White</span></span>          | <span data-ttu-id="db0f8-141">Fekete</span><span class="sxs-lookup"><span data-stu-id="db0f8-141">Black</span></span>                       |
| <span data-ttu-id="db0f8-142">Fehér</span><span class="sxs-lookup"><span data-stu-id="db0f8-142">White</span></span>          | <span data-ttu-id="db0f8-143">Fehér</span><span class="sxs-lookup"><span data-stu-id="db0f8-143">White</span></span>                       |
| <span data-ttu-id="db0f8-144">Fekete</span><span class="sxs-lookup"><span data-stu-id="db0f8-144">Black</span></span>          | <span data-ttu-id="db0f8-145">Fekete</span><span class="sxs-lookup"><span data-stu-id="db0f8-145">Black</span></span>                       |
| <span data-ttu-id="db0f8-146">Fekete</span><span class="sxs-lookup"><span data-stu-id="db0f8-146">Black</span></span>          | <span data-ttu-id="db0f8-147">Fém</span><span class="sxs-lookup"><span data-stu-id="db0f8-147">Metal</span></span>                       | 

<span data-ttu-id="db0f8-148">A táblázatok megszorításai felhasználó által definiáltak vagy rendszer definiáltak is lehetnek.</span><span class="sxs-lookup"><span data-stu-id="db0f8-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="db0f8-149">További tudnivalókért lásd: [Rendszer által definiált és felhasználó által definiált táblamegszorítások](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="db0f8-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="db0f8-150">Milyen szintaxist kell használni korlátozások kiírására?</span><span class="sxs-lookup"><span data-stu-id="db0f8-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="db0f8-151">A feltételt az Optimization Modeling Language (OML) szintaxisa alapján kell megírnia.</span><span class="sxs-lookup"><span data-stu-id="db0f8-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="db0f8-152">A rendszer a Microsoft Solver Foundation megszorításfeloldóját használja a megszorítások megoldására.</span><span class="sxs-lookup"><span data-stu-id="db0f8-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="db0f8-153">Kifejezés megszorítások és táblamegszorítások</span><span class="sxs-lookup"><span data-stu-id="db0f8-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="db0f8-154">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="db0f8-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="db0f8-155">Hoz létre olyan táblamegszorításhoz be egy mátrixban, mivel egy Kifejezésmegszorítás az egyes utasítást.</span><span class="sxs-lookup"><span data-stu-id="db0f8-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="db0f8-156">A termék konfigurálásához teljesen mindegy, milyen megszorítás használatos.</span><span class="sxs-lookup"><span data-stu-id="db0f8-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="db0f8-157">Az alábbi példák mutatják a beállításainak alkalmazását.</span><span class="sxs-lookup"><span data-stu-id="db0f8-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="db0f8-158">A termék a következő megszorítás beállítások használatával konfigurálásakor ezt követően a kombinációkat használhatók:</span><span class="sxs-lookup"><span data-stu-id="db0f8-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="db0f8-159">A termék fekete színnel 30 vagy 50 mérete</span><span class="sxs-lookup"><span data-stu-id="db0f8-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="db0f8-160">A termék piros színnel és 20 mérettel</span><span class="sxs-lookup"><span data-stu-id="db0f8-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="db0f8-161">Táblamegszorítási csoport</span><span class="sxs-lookup"><span data-stu-id="db0f8-161">Table constraint setup</span></span>

| <span data-ttu-id="db0f8-162">Szín</span><span class="sxs-lookup"><span data-stu-id="db0f8-162">Color</span></span> | <span data-ttu-id="db0f8-163">Méret</span><span class="sxs-lookup"><span data-stu-id="db0f8-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="db0f8-164">Fekete</span><span class="sxs-lookup"><span data-stu-id="db0f8-164">Black</span></span> | <span data-ttu-id="db0f8-165">30</span><span class="sxs-lookup"><span data-stu-id="db0f8-165">30</span></span>   |
| <span data-ttu-id="db0f8-166">Fekete</span><span class="sxs-lookup"><span data-stu-id="db0f8-166">Black</span></span> | <span data-ttu-id="db0f8-167">50</span><span class="sxs-lookup"><span data-stu-id="db0f8-167">50</span></span>   |
| <span data-ttu-id="db0f8-168">Piros</span><span class="sxs-lookup"><span data-stu-id="db0f8-168">Red</span></span>   | <span data-ttu-id="db0f8-169">20</span><span class="sxs-lookup"><span data-stu-id="db0f8-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="db0f8-170">Kifejezésmegszorítás</span><span class="sxs-lookup"><span data-stu-id="db0f8-170">Expression constraint setup</span></span>

<span data-ttu-id="db0f8-171">(Szín == "Fekete" & (méret == "30" | méret == "50")) | (szín == "Piros" & mérete = "20")</span><span class="sxs-lookup"><span data-stu-id="db0f8-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="db0f8-172">I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?</span><span class="sxs-lookup"><span data-stu-id="db0f8-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="db0f8-173">Előtag rendelkezésre álló operátorok a használatával egy Kifejezésmegszorítás írhat vagy használatával infix jelölés.</span><span class="sxs-lookup"><span data-stu-id="db0f8-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="db0f8-174">A **Min**, **Max** és **Abs** operátoroknál nem használhat infix jelölést.</span><span class="sxs-lookup"><span data-stu-id="db0f8-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="db0f8-175">A legtöbb programnyelven alapértelmezésként ezen operátorok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="db0f8-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="db0f8-176">I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?</span><span class="sxs-lookup"><span data-stu-id="db0f8-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="db0f8-177">A következő táblázatokban a listában az operátorok és infix jelölések, amely lehet használni, amikor egy Kifejezésmegszorítás összetevőhöz ír egy termékkonfigurációs modell.</span><span class="sxs-lookup"><span data-stu-id="db0f8-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="db0f8-178">A példákban a első táblázatban megtekintheti a kifejezés írása infix jelöléssel, vagy az operátorok segítségével.</span><span class="sxs-lookup"><span data-stu-id="db0f8-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db0f8-179">Kezelő</span><span class="sxs-lookup"><span data-stu-id="db0f8-179">Operator</span></span></th>
<th><span data-ttu-id="db0f8-180">Leírás</span><span class="sxs-lookup"><span data-stu-id="db0f8-180">Description</span></span></th>
<th><span data-ttu-id="db0f8-181">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="db0f8-181">Syntax</span></span></th>
<th><span data-ttu-id="db0f8-182">Példák</span><span class="sxs-lookup"><span data-stu-id="db0f8-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="db0f8-183">Implikálja</span><span class="sxs-lookup"><span data-stu-id="db0f8-183">Implies</span></span></td>
<td><span data-ttu-id="db0f8-184">Ez akkor is igaz, ha az első feltétel nem teljesül, a második feltétel értéke igaz, vagy mindkettőt.</span><span class="sxs-lookup"><span data-stu-id="db0f8-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="db0f8-185">Implies[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="db0f8-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-186"><strong>Műveleti jel:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="db0f8-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="db0f8-187"><strong>Infix jelölés:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="db0f8-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db0f8-188">És</span><span class="sxs-lookup"><span data-stu-id="db0f8-188">And</span></span></td>
<td><span data-ttu-id="db0f8-189">Ez akkor is igaz, csak az összes feltételek teljesülése esetén.</span><span class="sxs-lookup"><span data-stu-id="db0f8-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="db0f8-190">Ha a feltétel értéke 0 (nulla), <strong>Igaz</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="db0f8-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="db0f8-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="db0f8-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-192"><strong>Műveleti jel:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="db0f8-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="db0f8-193"><strong>Infix jelölés:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="db0f8-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="db0f8-194">Vagy</span><span class="sxs-lookup"><span data-stu-id="db0f8-194">Or</span></span></td>
<td><span data-ttu-id="db0f8-195">Ez akkor is igaz, ha bármelyik feltétel teljesül.</span><span class="sxs-lookup"><span data-stu-id="db0f8-195">This is true if any condition is true.</span></span> <span data-ttu-id="db0f8-196">Ha a feltétel értéke 0 (nulla), <strong>Hamis</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="db0f8-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="db0f8-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="db0f8-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-198"><strong>Műveleti jel:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="db0f8-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="db0f8-199"><strong>Infix jelölés:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="db0f8-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db0f8-200">Plusz</span><span class="sxs-lookup"><span data-stu-id="db0f8-200">Plus</span></span></td>
<td><span data-ttu-id="db0f8-201">Ez az összegek feltételeit.</span><span class="sxs-lookup"><span data-stu-id="db0f8-201">This sums its conditions.</span></span> <span data-ttu-id="db0f8-202">Ha a feltétel értéke 0 (nulla), <strong>0</strong>-t hoz létre.</span><span class="sxs-lookup"><span data-stu-id="db0f8-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="db0f8-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="db0f8-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-204"><strong>Művelet:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="db0f8-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="db0f8-205"><strong>Infix jelölés:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="db0f8-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="db0f8-206">Mínusz</span><span class="sxs-lookup"><span data-stu-id="db0f8-206">Minus</span></span></td>
<td><span data-ttu-id="db0f8-207">Ez a argumentum ellentettjét adja.</span><span class="sxs-lookup"><span data-stu-id="db0f8-207">This negates its argument.</span></span> <span data-ttu-id="db0f8-208">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="db0f8-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="db0f8-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="db0f8-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-210"><strong>Műveleti jel:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="db0f8-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="db0f8-211"><strong>Infix jelölés:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="db0f8-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db0f8-212">Abs</span><span class="sxs-lookup"><span data-stu-id="db0f8-212">Abs</span></span></td>
<td><span data-ttu-id="db0f8-213">Ez a termelésnek állapotuk adat abszolút értéke.</span><span class="sxs-lookup"><span data-stu-id="db0f8-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="db0f8-214">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="db0f8-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="db0f8-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="db0f8-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="db0f8-216"><strong>Művelet:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="db0f8-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="db0f8-217">Idők</span><span class="sxs-lookup"><span data-stu-id="db0f8-217">Times</span></span></td>
<td><span data-ttu-id="db0f8-218">Ez a feltétel a termék vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="db0f8-218">This takes the product of its conditions.</span></span> <span data-ttu-id="db0f8-219">Ha a feltétel értéke 0 (nulla), <strong>1</strong>-t hoz létre.</span><span class="sxs-lookup"><span data-stu-id="db0f8-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="db0f8-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="db0f8-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-221"><strong>Művelet:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="db0f8-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="db0f8-222"><strong>Infix jelölés:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="db0f8-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db0f8-223">Teljesítmény</span><span class="sxs-lookup"><span data-stu-id="db0f8-223">Power</span></span></td>
<td><span data-ttu-id="db0f8-224">Ez a termelésnek a tudományos.</span><span class="sxs-lookup"><span data-stu-id="db0f8-224">This takes an exponential.</span></span> <span data-ttu-id="db0f8-225">Ez akkor érvényes hatványkitevő jobbról balra.</span><span class="sxs-lookup"><span data-stu-id="db0f8-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="db0f8-226">(Ez azt jelenti, hogy jobbra társuló.) Ezért <strong>Hatvány[a, b, c]</strong> egyenlő: <strong>Hatvány[a, hatvány[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="db0f8-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="db0f8-227">A <strong>Power</strong> csak használható pozitív állandó, mint a kitevő.</span><span class="sxs-lookup"><span data-stu-id="db0f8-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="db0f8-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="db0f8-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-229"><strong>Művelet:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="db0f8-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="db0f8-230"><strong>Infix jelölés:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="db0f8-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="db0f8-231">Max.</span><span class="sxs-lookup"><span data-stu-id="db0f8-231">Max</span></span></td>
<td><span data-ttu-id="db0f8-232">A legnagyobb feltétel jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="db0f8-232">This produces the largest condition.</span></span> <span data-ttu-id="db0f8-233">Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="db0f8-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="db0f8-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="db0f8-234">Max[args]</span></span></td>
<td><span data-ttu-id="db0f8-235"><strong>Művelet:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="db0f8-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="db0f8-236">perc</span><span class="sxs-lookup"><span data-stu-id="db0f8-236">Min</span></span></td>
<td><span data-ttu-id="db0f8-237">A legkisebb feltételt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="db0f8-237">This produces the smallest condition.</span></span> <span data-ttu-id="db0f8-238">Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="db0f8-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="db0f8-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="db0f8-239">Min[args]</span></span></td>
<td><span data-ttu-id="db0f8-240"><strong>Művelet:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="db0f8-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="db0f8-241">Nem</span><span class="sxs-lookup"><span data-stu-id="db0f8-241">Not</span></span></td>
<td><span data-ttu-id="db0f8-242">A feltétel logikai inverzét jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="db0f8-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="db0f8-243">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="db0f8-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="db0f8-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="db0f8-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="db0f8-245"><strong>Műveleti jel</strong>: Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="db0f8-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="db0f8-246"><strong>Infix jelölés:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="db0f8-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="db0f8-247">Az alábbi táblázatban szereplő példák bemutatják, hogyan lehet írni egy infix jelölés.</span><span class="sxs-lookup"><span data-stu-id="db0f8-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="db0f8-248">Jelölés Infix:</span><span class="sxs-lookup"><span data-stu-id="db0f8-248">Infix notation</span></span>   |                                          <span data-ttu-id="db0f8-249">Leírás</span><span class="sxs-lookup"><span data-stu-id="db0f8-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="db0f8-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="db0f8-250">x + y + z</span></span>     |                                           <span data-ttu-id="db0f8-251">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="db0f8-251">Addition</span></span>                                            |
|    <span data-ttu-id="db0f8-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="db0f8-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="db0f8-253">szorzás</span><span class="sxs-lookup"><span data-stu-id="db0f8-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="db0f8-254">x - y</span><span class="sxs-lookup"><span data-stu-id="db0f8-254">x - y</span></span>       | <span data-ttu-id="db0f8-255">Bináris kivonás egy fordító bináris összeadás második megkereséséhez, megegyezik.</span><span class="sxs-lookup"><span data-stu-id="db0f8-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="db0f8-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="db0f8-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="db0f8-257">A jobb oldali asszociativitást hatványkitevő</span><span class="sxs-lookup"><span data-stu-id="db0f8-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="db0f8-258">!x</span><span class="sxs-lookup"><span data-stu-id="db0f8-258">!x</span></span>         |                                          <span data-ttu-id="db0f8-259">Logikai</span><span class="sxs-lookup"><span data-stu-id="db0f8-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="db0f8-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="db0f8-260">x -: y</span></span>       |                                      <span data-ttu-id="db0f8-261">Logikai tényezők</span><span class="sxs-lookup"><span data-stu-id="db0f8-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="db0f8-262">x</span><span class="sxs-lookup"><span data-stu-id="db0f8-262">x</span></span>         |                                               <span data-ttu-id="db0f8-263">y</span><span class="sxs-lookup"><span data-stu-id="db0f8-263">y</span></span>                                               |
|     <span data-ttu-id="db0f8-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="db0f8-264">x & y & z</span></span>     |                                          <span data-ttu-id="db0f8-265">Logikai és</span><span class="sxs-lookup"><span data-stu-id="db0f8-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="db0f8-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="db0f8-266">x == y == z</span></span>    |                                           <span data-ttu-id="db0f8-267">egyenlőség</span><span class="sxs-lookup"><span data-stu-id="db0f8-267">Equality</span></span>                                            |
|    <span data-ttu-id="db0f8-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="db0f8-268">x != y != z</span></span>    |                                           <span data-ttu-id="db0f8-269">Különálló</span><span class="sxs-lookup"><span data-stu-id="db0f8-269">Distinct</span></span>                                            |
|  <span data-ttu-id="db0f8-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="db0f8-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="db0f8-271">Kisebb, mint</span><span class="sxs-lookup"><span data-stu-id="db0f8-271">Less than</span></span>                                           |
|  <span data-ttu-id="db0f8-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="db0f8-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="db0f8-273">Nagyobb, mint</span><span class="sxs-lookup"><span data-stu-id="db0f8-273">Greater than</span></span>                                          |
| <span data-ttu-id="db0f8-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="db0f8-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="db0f8-275">Kisebb vagy egyenlő</span><span class="sxs-lookup"><span data-stu-id="db0f8-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="db0f8-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="db0f8-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="db0f8-277">Nagyobb vagy egyenlő</span><span class="sxs-lookup"><span data-stu-id="db0f8-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="db0f8-278">(x)</span><span class="sxs-lookup"><span data-stu-id="db0f8-278">(x)</span></span>        |                           <span data-ttu-id="db0f8-279">Zárójelek alapértelmezett elsőbbségi sorrend felülbírálása.</span><span class="sxs-lookup"><span data-stu-id="db0f8-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="db0f8-280">Miért nem megfelelő a kifejezés megszorítások ellenőrzése?</span><span class="sxs-lookup"><span data-stu-id="db0f8-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="db0f8-281">Attribútumok, alkatrészek vagy az egy termékkonfigurációs modell alösszetevői attribútumfeloldó neve fenntartott kulcsszó nem használható.</span><span class="sxs-lookup"><span data-stu-id="db0f8-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span><span data-ttu-id="db0f8-282"> Az alábbi lista a foglalt kulcsszavakat mutatja, amelyek nem használhatók:</span><span class="sxs-lookup"><span data-stu-id="db0f8-282"> Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="db0f8-283">Felső határ</span><span class="sxs-lookup"><span data-stu-id="db0f8-283">Ceiling</span></span>
-   <span data-ttu-id="db0f8-284">Elem</span><span class="sxs-lookup"><span data-stu-id="db0f8-284">Element</span></span>
-   <span data-ttu-id="db0f8-285">Egyenlő</span><span class="sxs-lookup"><span data-stu-id="db0f8-285">Equal</span></span>
-   <span data-ttu-id="db0f8-286">Emelet</span><span class="sxs-lookup"><span data-stu-id="db0f8-286">Floor</span></span>
-   <span data-ttu-id="db0f8-287">Ha</span><span class="sxs-lookup"><span data-stu-id="db0f8-287">If</span></span>
-   <span data-ttu-id="db0f8-288">Kisebb</span><span class="sxs-lookup"><span data-stu-id="db0f8-288">Less</span></span>
-   <span data-ttu-id="db0f8-289">Nagyobb</span><span class="sxs-lookup"><span data-stu-id="db0f8-289">Greater</span></span>
-   <span data-ttu-id="db0f8-290">Implikálja</span><span class="sxs-lookup"><span data-stu-id="db0f8-290">Implies</span></span>
-   <span data-ttu-id="db0f8-291">Eseménynapló</span><span class="sxs-lookup"><span data-stu-id="db0f8-291">Log</span></span>
-   <span data-ttu-id="db0f8-292">Max.</span><span class="sxs-lookup"><span data-stu-id="db0f8-292">Max</span></span>
-   <span data-ttu-id="db0f8-293">perc</span><span class="sxs-lookup"><span data-stu-id="db0f8-293">Min</span></span>
-   <span data-ttu-id="db0f8-294">Mínusz</span><span class="sxs-lookup"><span data-stu-id="db0f8-294">Minus</span></span>
-   <span data-ttu-id="db0f8-295">Plusz</span><span class="sxs-lookup"><span data-stu-id="db0f8-295">Plus</span></span>
-   <span data-ttu-id="db0f8-296">Teljesítmény</span><span class="sxs-lookup"><span data-stu-id="db0f8-296">Power</span></span>
-   <span data-ttu-id="db0f8-297">Idők</span><span class="sxs-lookup"><span data-stu-id="db0f8-297">Times</span></span>
-   <span data-ttu-id="db0f8-298">Időköz</span><span class="sxs-lookup"><span data-stu-id="db0f8-298">Slot</span></span>
-   <span data-ttu-id="db0f8-299">Típus</span><span class="sxs-lookup"><span data-stu-id="db0f8-299">Model</span></span>
-   <span data-ttu-id="db0f8-300">Döntés</span><span class="sxs-lookup"><span data-stu-id="db0f8-300">Decision</span></span>
-   <span data-ttu-id="db0f8-301">Cél</span><span class="sxs-lookup"><span data-stu-id="db0f8-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="db0f8-302">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="db0f8-302">Additional resources</span></span>
--------

[<span data-ttu-id="db0f8-303">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="db0f8-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="db0f8-304">Kalkuláció hozzáadása termékkonfigurációs modellhez</span><span class="sxs-lookup"><span data-stu-id="db0f8-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)




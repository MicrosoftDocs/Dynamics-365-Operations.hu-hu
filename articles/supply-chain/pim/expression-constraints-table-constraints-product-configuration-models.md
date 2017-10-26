---
title: "A termékkonfigurációs modellek kifejezésmegszorításai"
description: "Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások. Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 7aeb0438182fe177ac83580f03cbb547c79fd08a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="35d03-105">A termékkonfigurációs modellek kifejezésmegszorításai</span><span class="sxs-lookup"><span data-stu-id="35d03-105">Expression constraints and table constraints in product configuration models</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="35d03-106">Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások.</span><span class="sxs-lookup"><span data-stu-id="35d03-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="35d03-107">Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor.</span><span class="sxs-lookup"><span data-stu-id="35d03-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="35d03-108">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="35d03-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="35d03-109">Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor.</span><span class="sxs-lookup"><span data-stu-id="35d03-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="35d03-110">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="35d03-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="35d03-111">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="35d03-111">What are expression constraints?</span></span>
<span data-ttu-id="35d03-112">Kifejezés megszorítások jellemző aritmetikai és logikai operátort és függvényt használó kifejezést.</span><span class="sxs-lookup"><span data-stu-id="35d03-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="35d03-113">A termékkonfigurációs modell adott összetevő egy Kifejezésmegszorítás készült.</span><span class="sxs-lookup"><span data-stu-id="35d03-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="35d03-114">Nem használja fel újra, és egy másik összetevő megosztva.</span><span class="sxs-lookup"><span data-stu-id="35d03-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="35d03-115">Egy összetevőre vonatkozó kifejezés megszorításai az összetevők részösszetevőinek attribútumaira is hivatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="35d03-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="35d03-116">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="35d03-116">What are table constraints?</span></span>
<span data-ttu-id="35d03-117">Táblamegszorítások-kombinációkat termék konfigurálásakor attribútumok megengedett értékek listája.</span><span class="sxs-lookup"><span data-stu-id="35d03-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="35d03-118">Táblamegszorítási definíciók általában használható.</span><span class="sxs-lookup"><span data-stu-id="35d03-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="35d03-119">A termékkonfigurációs modell összetevőhöz táblamegszorítás létrehozásakor ki kell választania egy táblamegszorítás definíciója.</span><span class="sxs-lookup"><span data-stu-id="35d03-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="35d03-120">A megengedett kombinációk létrehozásához hozzáadja az összetevők különféle jellemzőit.</span><span class="sxs-lookup"><span data-stu-id="35d03-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="35d03-121">Minden egyes attribútumtípus egy adott értékű.</span><span class="sxs-lookup"><span data-stu-id="35d03-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="35d03-122">Táblamegszorítás típusa</span><span class="sxs-lookup"><span data-stu-id="35d03-122">Example of a table constraint</span></span>

<span data-ttu-id="35d03-123">Ez a példa azt mutatja, hogyan korlátozhatja egy adott kabinetfájl befejeződik és előlapot hangszóró konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="35d03-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="35d03-124">Az első táblázat mutatja a méreteket és a televízió, általában elérhető konfigurációs típusú.</span><span class="sxs-lookup"><span data-stu-id="35d03-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="35d03-125">Határozhatók meg az értékeket a **Kabinetfájl befejezés** és **Első rács** attribútum típusa.</span><span class="sxs-lookup"><span data-stu-id="35d03-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="35d03-126">Attribútumtípus</span><span class="sxs-lookup"><span data-stu-id="35d03-126">Attribute type</span></span> | <span data-ttu-id="35d03-127">Értékek</span><span class="sxs-lookup"><span data-stu-id="35d03-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="35d03-128">Hangszóró borítása</span><span class="sxs-lookup"><span data-stu-id="35d03-128">Cabinet finish</span></span> | <span data-ttu-id="35d03-129">Fekete, tölgyfa, rózsafa, fehér</span><span class="sxs-lookup"><span data-stu-id="35d03-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="35d03-130">Elülső rács</span><span class="sxs-lookup"><span data-stu-id="35d03-130">Front grill</span></span>    | <span data-ttu-id="35d03-131">Fekete, fém, fehér</span><span class="sxs-lookup"><span data-stu-id="35d03-131">Black, Metal, White</span></span>         |

<span data-ttu-id="35d03-132">A következő táblázat bemutatja a kombinációk határozzák meg, hogy a **Szín és kivitel** táblamegszorítás.</span><span class="sxs-lookup"><span data-stu-id="35d03-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="35d03-133">A táblamegszorítás használatával konfigurálhatja egy tölgy Befejezés és fekete ráccsal, egy rózsafa Befejezés és fehér rács előadó, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="35d03-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="35d03-134">Elvégzés</span><span class="sxs-lookup"><span data-stu-id="35d03-134">Finish</span></span>         | <span data-ttu-id="35d03-135">Rács</span><span class="sxs-lookup"><span data-stu-id="35d03-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="35d03-136">Tölgyfa</span><span class="sxs-lookup"><span data-stu-id="35d03-136">Oak</span></span>            | <span data-ttu-id="35d03-137">Fekete</span><span class="sxs-lookup"><span data-stu-id="35d03-137">Black</span></span>                       |
| <span data-ttu-id="35d03-138">Rózsafa</span><span class="sxs-lookup"><span data-stu-id="35d03-138">Rosewood</span></span>       | <span data-ttu-id="35d03-139">Fehér</span><span class="sxs-lookup"><span data-stu-id="35d03-139">White</span></span>                       |
| <span data-ttu-id="35d03-140">Fehér</span><span class="sxs-lookup"><span data-stu-id="35d03-140">White</span></span>          | <span data-ttu-id="35d03-141">Fekete</span><span class="sxs-lookup"><span data-stu-id="35d03-141">Black</span></span>                       |
| <span data-ttu-id="35d03-142">Fehér</span><span class="sxs-lookup"><span data-stu-id="35d03-142">White</span></span>          | <span data-ttu-id="35d03-143">Fehér</span><span class="sxs-lookup"><span data-stu-id="35d03-143">White</span></span>                       |
| <span data-ttu-id="35d03-144">Fekete</span><span class="sxs-lookup"><span data-stu-id="35d03-144">Black</span></span>          | <span data-ttu-id="35d03-145">Fekete</span><span class="sxs-lookup"><span data-stu-id="35d03-145">Black</span></span>                       |
| <span data-ttu-id="35d03-146">Fekete</span><span class="sxs-lookup"><span data-stu-id="35d03-146">Black</span></span>          | <span data-ttu-id="35d03-147">Fém</span><span class="sxs-lookup"><span data-stu-id="35d03-147">Metal</span></span>                       | 

<span data-ttu-id="35d03-148">A táblázatok megszorításai felhasználó által definiáltak vagy rendszer definiáltak is lehetnek.</span><span class="sxs-lookup"><span data-stu-id="35d03-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="35d03-149">További tudnivalókért lásd: [Rendszer által definiált és felhasználó által definiált táblamegszorítások](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="35d03-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="35d03-150">Milyen szintaxist kell használni korlátozások kiírására?</span><span class="sxs-lookup"><span data-stu-id="35d03-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="35d03-151">A feltételt az Optimization Modeling Language (OML) szintaxisa alapján kell megírnia.</span><span class="sxs-lookup"><span data-stu-id="35d03-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="35d03-152">A rendszer a Microsoft Solver Foundation megszorításfeloldóját használja a megszorítások megoldására.</span><span class="sxs-lookup"><span data-stu-id="35d03-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="35d03-153">Kifejezés megszorítások és táblamegszorítások</span><span class="sxs-lookup"><span data-stu-id="35d03-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="35d03-154">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="35d03-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="35d03-155">Hoz létre olyan táblamegszorításhoz be egy mátrixban, mivel egy Kifejezésmegszorítás az egyes utasítást.</span><span class="sxs-lookup"><span data-stu-id="35d03-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="35d03-156">A termék konfigurálásához teljesen mindegy, milyen megszorítás használatos.</span><span class="sxs-lookup"><span data-stu-id="35d03-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="35d03-157">Az alábbi példák mutatják a beállításainak alkalmazását.</span><span class="sxs-lookup"><span data-stu-id="35d03-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="35d03-158">A termék a következő megszorítás beállítások használatával konfigurálásakor ezt követően a kombinációkat használhatók:</span><span class="sxs-lookup"><span data-stu-id="35d03-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="35d03-159">A termék fekete színnel 30 vagy 50 mérete</span><span class="sxs-lookup"><span data-stu-id="35d03-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="35d03-160">A termék piros színnel és 20 mérettel</span><span class="sxs-lookup"><span data-stu-id="35d03-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="35d03-161">Táblamegszorítási csoport</span><span class="sxs-lookup"><span data-stu-id="35d03-161">Table constraint setup</span></span>

| <span data-ttu-id="35d03-162">Szín</span><span class="sxs-lookup"><span data-stu-id="35d03-162">Color</span></span> | <span data-ttu-id="35d03-163">Méret</span><span class="sxs-lookup"><span data-stu-id="35d03-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="35d03-164">Fekete</span><span class="sxs-lookup"><span data-stu-id="35d03-164">Black</span></span> | <span data-ttu-id="35d03-165">30</span><span class="sxs-lookup"><span data-stu-id="35d03-165">30</span></span>   |
| <span data-ttu-id="35d03-166">Fekete</span><span class="sxs-lookup"><span data-stu-id="35d03-166">Black</span></span> | <span data-ttu-id="35d03-167">50</span><span class="sxs-lookup"><span data-stu-id="35d03-167">50</span></span>   |
| <span data-ttu-id="35d03-168">Piros</span><span class="sxs-lookup"><span data-stu-id="35d03-168">Red</span></span>   | <span data-ttu-id="35d03-169">20</span><span class="sxs-lookup"><span data-stu-id="35d03-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="35d03-170">Kifejezésmegszorítás</span><span class="sxs-lookup"><span data-stu-id="35d03-170">Expression constraint setup</span></span>

<span data-ttu-id="35d03-171">(Szín == "Fekete" & (méret == "30" |} méret == "50")) |} (szín == "Piros" & mérete = "20")</span><span class="sxs-lookup"><span data-stu-id="35d03-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="35d03-172">I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?</span><span class="sxs-lookup"><span data-stu-id="35d03-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="35d03-173">Előtag rendelkezésre álló operátorok a használatával egy Kifejezésmegszorítás írhat vagy használatával infix jelölés.</span><span class="sxs-lookup"><span data-stu-id="35d03-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="35d03-174">A **Min**, **Max** és **Abs** operátoroknál nem használhat infix jelölést.</span><span class="sxs-lookup"><span data-stu-id="35d03-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="35d03-175">A legtöbb programnyelven alapértelmezésként ezen operátorok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="35d03-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="35d03-176">I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?</span><span class="sxs-lookup"><span data-stu-id="35d03-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="35d03-177">A következő táblázatokban a listában az operátorok és infix jelölések, amely lehet használni, amikor egy Kifejezésmegszorítás összetevőhöz ír egy termékkonfigurációs modell.</span><span class="sxs-lookup"><span data-stu-id="35d03-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="35d03-178">A példákban a első táblázatban megtekintheti a kifejezés írása infix jelöléssel, vagy az operátorok segítségével.</span><span class="sxs-lookup"><span data-stu-id="35d03-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35d03-179">Kezelő</span><span class="sxs-lookup"><span data-stu-id="35d03-179">Operator</span></span></th>
<th><span data-ttu-id="35d03-180">Leírás</span><span class="sxs-lookup"><span data-stu-id="35d03-180">Description</span></span></th>
<th><span data-ttu-id="35d03-181">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="35d03-181">Syntax</span></span></th>
<th><span data-ttu-id="35d03-182">Példák</span><span class="sxs-lookup"><span data-stu-id="35d03-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="35d03-183">Implikálja</span><span class="sxs-lookup"><span data-stu-id="35d03-183">Implies</span></span></td>
<td><span data-ttu-id="35d03-184">Ez akkor is igaz, ha az első feltétel nem teljesül, a második feltétel értéke igaz, vagy mindkettőt.</span><span class="sxs-lookup"><span data-stu-id="35d03-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="35d03-185">Azt jelenti, [a, b] infix: a-: b</span><span class="sxs-lookup"><span data-stu-id="35d03-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-186"><strong>Műveleti jel:</strong> a következőt jelenti: [x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="35d03-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="35d03-187"><strong>Infix jelölés:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="35d03-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35d03-188">És</span><span class="sxs-lookup"><span data-stu-id="35d03-188">And</span></span></td>
<td><span data-ttu-id="35d03-189">Ez akkor is igaz, csak az összes feltételek teljesülése esetén.</span><span class="sxs-lookup"><span data-stu-id="35d03-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="35d03-190">Ha a feltétel értéke 0 (nulla), <strong>Igaz</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="35d03-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="35d03-191">And[argumentumok], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="35d03-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-192"><strong>Műveleti jel:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="35d03-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="35d03-193"><strong>Infix jelölés:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="35d03-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35d03-194">Vagy</span><span class="sxs-lookup"><span data-stu-id="35d03-194">Or</span></span></td>
<td><span data-ttu-id="35d03-195">Ez akkor is igaz, ha bármelyik feltétel teljesül.</span><span class="sxs-lookup"><span data-stu-id="35d03-195">This is true if any condition is true.</span></span> <span data-ttu-id="35d03-196">Ha a feltétel értéke 0 (nulla), <strong>Hamis</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="35d03-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="35d03-197">Or[argumentumok], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="35d03-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-198"><strong>Műveleti jel:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="35d03-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="35d03-199"><strong>Infix jelölés:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="35d03-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35d03-200">Plusz</span><span class="sxs-lookup"><span data-stu-id="35d03-200">Plus</span></span></td>
<td><span data-ttu-id="35d03-201">Ez az összegek feltételeit.</span><span class="sxs-lookup"><span data-stu-id="35d03-201">This sums its conditions.</span></span> <span data-ttu-id="35d03-202">Ha a feltétel értéke 0 (nulla), <strong>0</strong>-t hoz létre.</span><span class="sxs-lookup"><span data-stu-id="35d03-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="35d03-203">Plusz[argumentumok], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="35d03-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-204"><strong>Művelet:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="35d03-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="35d03-205"><strong>Infix jelölés:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="35d03-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35d03-206">Mínusz</span><span class="sxs-lookup"><span data-stu-id="35d03-206">Minus</span></span></td>
<td><span data-ttu-id="35d03-207">Ez a argumentum ellentettjét adja.</span><span class="sxs-lookup"><span data-stu-id="35d03-207">This negates its argument.</span></span> <span data-ttu-id="35d03-208">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="35d03-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="35d03-209">[Kifejezés], csökkentett infix: - kifejezés</span><span class="sxs-lookup"><span data-stu-id="35d03-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-210"><strong>Művelet:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="35d03-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="35d03-211"><strong>Infix jelölés:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="35d03-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35d03-212">(ABS)</span><span class="sxs-lookup"><span data-stu-id="35d03-212">Abs</span></span></td>
<td><span data-ttu-id="35d03-213">Ez a termelésnek állapotuk adat abszolút értéke.</span><span class="sxs-lookup"><span data-stu-id="35d03-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="35d03-214">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="35d03-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="35d03-215">[Kifejezés] ABS</span><span class="sxs-lookup"><span data-stu-id="35d03-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="35d03-216"><strong>Művelet:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="35d03-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35d03-217">Idők</span><span class="sxs-lookup"><span data-stu-id="35d03-217">Times</span></span></td>
<td><span data-ttu-id="35d03-218">Ez a feltétel a termék vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="35d03-218">This takes the product of its conditions.</span></span> <span data-ttu-id="35d03-219">Ha a feltétel értéke 0 (nulla), <strong>1</strong>-t hoz létre.</span><span class="sxs-lookup"><span data-stu-id="35d03-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="35d03-220">Szorzás[argumentumok], infix: a * b * ... * z</span><span class="sxs-lookup"><span data-stu-id="35d03-220">Times[args], infix: a * b * ... * z</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-221"><strong>Művelet:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="35d03-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="35d03-222"><strong>Infix jelölés:</strong> x * y * 2 == z</span><span class="sxs-lookup"><span data-stu-id="35d03-222"><strong>Infix notation:</strong> x * y * 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35d03-223">Teljesítmény</span><span class="sxs-lookup"><span data-stu-id="35d03-223">Power</span></span></td>
<td><span data-ttu-id="35d03-224">Ez a termelésnek a tudományos.</span><span class="sxs-lookup"><span data-stu-id="35d03-224">This takes an exponential.</span></span> <span data-ttu-id="35d03-225">Ez akkor érvényes hatványkitevő jobbról balra.</span><span class="sxs-lookup"><span data-stu-id="35d03-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="35d03-226">(Ez azt jelenti, hogy jobbra társuló.) Ezért <strong>Hatvány[a, b, c]</strong> egyenlő: <strong>Hatvány[a, hatvány[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="35d03-226">(In other words, it's right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="35d03-227">A <strong>Power</strong> csak használható pozitív állandó, mint a kitevő.</span><span class="sxs-lookup"><span data-stu-id="35d03-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="35d03-228">Hatvány[argumentumok], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="35d03-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-229"><strong>Művelet:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="35d03-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="35d03-230"><strong>Infix jelölés:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="35d03-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35d03-231">Max.</span><span class="sxs-lookup"><span data-stu-id="35d03-231">Max</span></span></td>
<td><span data-ttu-id="35d03-232">A legnagyobb feltétel jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="35d03-232">This produces the largest condition.</span></span> <span data-ttu-id="35d03-233">Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="35d03-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="35d03-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="35d03-234">Max[args]</span></span></td>
<td><span data-ttu-id="35d03-235"><strong>Művelet:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="35d03-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35d03-236">Min.</span><span class="sxs-lookup"><span data-stu-id="35d03-236">Min</span></span></td>
<td><span data-ttu-id="35d03-237">A legkisebb feltételt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="35d03-237">This produces the smallest condition.</span></span> <span data-ttu-id="35d03-238">Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="35d03-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="35d03-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="35d03-239">Min[args]</span></span></td>
<td><span data-ttu-id="35d03-240"><strong>Művelet:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="35d03-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35d03-241">Nem</span><span class="sxs-lookup"><span data-stu-id="35d03-241">Not</span></span></td>
<td><span data-ttu-id="35d03-242">A feltétel logikai inverzét jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="35d03-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="35d03-243">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="35d03-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="35d03-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="35d03-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="35d03-245"><strong>Műveleti jel:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="35d03-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="35d03-246"><strong>Infix jelölés:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="35d03-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="35d03-247">Az alábbi táblázatban szereplő példák bemutatják, hogyan lehet írni egy infix jelölés.</span><span class="sxs-lookup"><span data-stu-id="35d03-247">The examples in the next table show how to write infix notation.</span></span>

| <span data-ttu-id="35d03-248">Jelölés Infix:</span><span class="sxs-lookup"><span data-stu-id="35d03-248">Infix notation</span></span>    | <span data-ttu-id="35d03-249">Leírás</span><span class="sxs-lookup"><span data-stu-id="35d03-249">Description</span></span>                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| <span data-ttu-id="35d03-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="35d03-250">x + y + z</span></span>         | <span data-ttu-id="35d03-251">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="35d03-251">Addition</span></span>                                                                                      |
| <span data-ttu-id="35d03-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="35d03-252">x \* y \* z</span></span>       | <span data-ttu-id="35d03-253">szorzás</span><span class="sxs-lookup"><span data-stu-id="35d03-253">Multiplication</span></span>                                                                                |
| <span data-ttu-id="35d03-254">x - y</span><span class="sxs-lookup"><span data-stu-id="35d03-254">x - y</span></span>             | <span data-ttu-id="35d03-255">Bináris kivonás egy fordító bináris összeadás második megkereséséhez, megegyezik.</span><span class="sxs-lookup"><span data-stu-id="35d03-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
| <span data-ttu-id="35d03-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="35d03-256">x ^ y ^ z</span></span>         | <span data-ttu-id="35d03-257">A jobb oldali asszociativitást hatványkitevő</span><span class="sxs-lookup"><span data-stu-id="35d03-257">Exponentiation that has right associativity</span></span>                                                   |
| <span data-ttu-id="35d03-258">!x</span><span class="sxs-lookup"><span data-stu-id="35d03-258">!x</span></span>                | <span data-ttu-id="35d03-259">Logikai</span><span class="sxs-lookup"><span data-stu-id="35d03-259">Boolean not</span></span>                                                                                   |
| <span data-ttu-id="35d03-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="35d03-260">x -: y</span></span>            | <span data-ttu-id="35d03-261">Logikai tényezők</span><span class="sxs-lookup"><span data-stu-id="35d03-261">Boolean implication</span></span>                                                                           |
| <span data-ttu-id="35d03-262">x</span><span class="sxs-lookup"><span data-stu-id="35d03-262">x</span></span> | <span data-ttu-id="35d03-263">y</span><span class="sxs-lookup"><span data-stu-id="35d03-263">y</span></span> | <span data-ttu-id="35d03-264">z</span><span class="sxs-lookup"><span data-stu-id="35d03-264">z</span></span>         | <span data-ttu-id="35d03-265">Logikai vagy</span><span class="sxs-lookup"><span data-stu-id="35d03-265">Boolean or</span></span>                                                                                    |
| <span data-ttu-id="35d03-266">x & y & z</span><span class="sxs-lookup"><span data-stu-id="35d03-266">x & y & z</span></span>         | <span data-ttu-id="35d03-267">Logikai és</span><span class="sxs-lookup"><span data-stu-id="35d03-267">Boolean and</span></span>                                                                                   |
| <span data-ttu-id="35d03-268">x == y == z</span><span class="sxs-lookup"><span data-stu-id="35d03-268">x == y == z</span></span>       | <span data-ttu-id="35d03-269">egyenlőség</span><span class="sxs-lookup"><span data-stu-id="35d03-269">Equality</span></span>                                                                                      |
| <span data-ttu-id="35d03-270">x != y != z</span><span class="sxs-lookup"><span data-stu-id="35d03-270">x != y != z</span></span>       | <span data-ttu-id="35d03-271">Különálló</span><span class="sxs-lookup"><span data-stu-id="35d03-271">Distinct</span></span>                                                                                      |
| <span data-ttu-id="35d03-272">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="35d03-272">x &lt; y &lt; z</span></span>   | <span data-ttu-id="35d03-273">Kisebb, mint</span><span class="sxs-lookup"><span data-stu-id="35d03-273">Less than</span></span>                                                                                     |
| <span data-ttu-id="35d03-274">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="35d03-274">x &gt; y &gt; z</span></span>   | <span data-ttu-id="35d03-275">Nagyobb, mint</span><span class="sxs-lookup"><span data-stu-id="35d03-275">Greater than</span></span>                                                                                  |
| <span data-ttu-id="35d03-276">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="35d03-276">x &lt;= y &lt;= z</span></span> | <span data-ttu-id="35d03-277">Kisebb vagy egyenlő</span><span class="sxs-lookup"><span data-stu-id="35d03-277">Less than or equal to</span></span>                                                                         |
| <span data-ttu-id="35d03-278">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="35d03-278">x &gt;= y &gt;= z</span></span> | <span data-ttu-id="35d03-279">Nagyobb vagy egyenlő</span><span class="sxs-lookup"><span data-stu-id="35d03-279">Greater than or equal to</span></span>                                                                      |
| <span data-ttu-id="35d03-280">(x)</span><span class="sxs-lookup"><span data-stu-id="35d03-280">(x)</span></span>               | <span data-ttu-id="35d03-281">Zárójelek alapértelmezett elsőbbségi sorrend felülbírálása.</span><span class="sxs-lookup"><span data-stu-id="35d03-281">Parentheses override default precedence.</span></span>                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="35d03-282">Miért nem megfelelő a kifejezés megszorítások ellenőrzése?</span><span class="sxs-lookup"><span data-stu-id="35d03-282">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="35d03-283">Attribútumok, alkatrészek vagy az egy termékkonfigurációs modell alösszetevői attribútumfeloldó neve fenntartott kulcsszó nem használható.</span><span class="sxs-lookup"><span data-stu-id="35d03-283">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span> <span data-ttu-id="35d03-284">Az alábbi lista a foglalt kulcsszavakat mutatja, amelyek nem használhatók:</span><span class="sxs-lookup"><span data-stu-id="35d03-284">Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="35d03-285">Felső határ</span><span class="sxs-lookup"><span data-stu-id="35d03-285">Ceiling</span></span>
-   <span data-ttu-id="35d03-286">Elem</span><span class="sxs-lookup"><span data-stu-id="35d03-286">Element</span></span>
-   <span data-ttu-id="35d03-287">Egyenlő</span><span class="sxs-lookup"><span data-stu-id="35d03-287">Equal</span></span>
-   <span data-ttu-id="35d03-288">Emelet</span><span class="sxs-lookup"><span data-stu-id="35d03-288">Floor</span></span>
-   <span data-ttu-id="35d03-289">Ha</span><span class="sxs-lookup"><span data-stu-id="35d03-289">If</span></span>
-   <span data-ttu-id="35d03-290">Kisebb</span><span class="sxs-lookup"><span data-stu-id="35d03-290">Less</span></span>
-   <span data-ttu-id="35d03-291">Nagyobb</span><span class="sxs-lookup"><span data-stu-id="35d03-291">Greater</span></span>
-   <span data-ttu-id="35d03-292">Implikálja</span><span class="sxs-lookup"><span data-stu-id="35d03-292">Implies</span></span>
-   <span data-ttu-id="35d03-293">Eseménynapló</span><span class="sxs-lookup"><span data-stu-id="35d03-293">Log</span></span>
-   <span data-ttu-id="35d03-294">Max.</span><span class="sxs-lookup"><span data-stu-id="35d03-294">Max</span></span>
-   <span data-ttu-id="35d03-295">Min.</span><span class="sxs-lookup"><span data-stu-id="35d03-295">Min</span></span>
-   <span data-ttu-id="35d03-296">Mínusz</span><span class="sxs-lookup"><span data-stu-id="35d03-296">Minus</span></span>
-   <span data-ttu-id="35d03-297">Plusz</span><span class="sxs-lookup"><span data-stu-id="35d03-297">Plus</span></span>
-   <span data-ttu-id="35d03-298">Teljesítmény</span><span class="sxs-lookup"><span data-stu-id="35d03-298">Power</span></span>
-   <span data-ttu-id="35d03-299">Idők</span><span class="sxs-lookup"><span data-stu-id="35d03-299">Times</span></span>
-   <span data-ttu-id="35d03-300">Időköz</span><span class="sxs-lookup"><span data-stu-id="35d03-300">Slot</span></span>
-   <span data-ttu-id="35d03-301">Típus</span><span class="sxs-lookup"><span data-stu-id="35d03-301">Model</span></span>
-   <span data-ttu-id="35d03-302">Döntés</span><span class="sxs-lookup"><span data-stu-id="35d03-302">Decision</span></span>
-   <span data-ttu-id="35d03-303">Cél</span><span class="sxs-lookup"><span data-stu-id="35d03-303">Goal</span></span>


<a name="see-also"></a><span data-ttu-id="35d03-304">Lásd még</span><span class="sxs-lookup"><span data-stu-id="35d03-304">See also</span></span>
--------

<span data-ttu-id="35d03-305">Kifejezésmegszorítás létrehozása a termékkonfigurációs modellhez (feladat-útmutató)(tasks/add-expression-constraint-product-configuration-model.md)</span><span class="sxs-lookup"><span data-stu-id="35d03-305">[Create an expression constraint (Task guide)(tasks/add-expression-constraint-product-configuration-model.md)</span></span>

[<span data-ttu-id="35d03-306">Kalkuláció hozzáadása termékkonfigurációs modellhez (feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="35d03-306">Add a calculation to a product configuration model (Task guide)</span></span>](tasks/add-calculation-product-configuration-model.md)





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
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979828"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="6c0ca-105">A termékkonfigurációs modellek kifejezésmegszorításai</span><span class="sxs-lookup"><span data-stu-id="6c0ca-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c0ca-106">Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="6c0ca-107">Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="6c0ca-108">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="6c0ca-109">Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="6c0ca-110">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="6c0ca-111">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="6c0ca-111">What are expression constraints?</span></span>
<span data-ttu-id="6c0ca-112">Kifejezés megszorítások jellemző aritmetikai és logikai operátort és függvényt használó kifejezést.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="6c0ca-113">A termékkonfigurációs modell adott összetevő egy Kifejezésmegszorítás készült.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="6c0ca-114">Nem használja fel újra, és egy másik összetevő megosztva.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="6c0ca-115">Egy összetevőre vonatkozó kifejezés megszorításai az összetevők részösszetevőinek attribútumaira is hivatkozhatnak.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="6c0ca-116">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="6c0ca-116">What are table constraints?</span></span>
<span data-ttu-id="6c0ca-117">Táblamegszorítások-kombinációkat termék konfigurálásakor attribútumok megengedett értékek listája.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="6c0ca-118">Táblamegszorítási definíciók általában használható.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="6c0ca-119">A termékkonfigurációs modell összetevőhöz táblamegszorítás létrehozásakor ki kell választania egy táblamegszorítás definíciója.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="6c0ca-120">A megengedett kombinációk létrehozásához hozzáadja az összetevők különféle jellemzőit.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="6c0ca-121">Minden egyes attribútumtípus egy adott értékű.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="6c0ca-122">Táblamegszorítás típusa</span><span class="sxs-lookup"><span data-stu-id="6c0ca-122">Example of a table constraint</span></span>

<span data-ttu-id="6c0ca-123">Ez a példa azt mutatja, hogyan korlátozhatja egy adott kabinetfájl befejeződik és előlapot hangszóró konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="6c0ca-124">Az első táblázat mutatja a méreteket és a televízió, általában elérhető konfigurációs típusú.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="6c0ca-125">Határozhatók meg az értékeket a **Kabinetfájl befejezés** és **Első rács** attribútum típusa.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="6c0ca-126">Attribútumtípus</span><span class="sxs-lookup"><span data-stu-id="6c0ca-126">Attribute type</span></span> | <span data-ttu-id="6c0ca-127">Értékek</span><span class="sxs-lookup"><span data-stu-id="6c0ca-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="6c0ca-128">Hangszóró borítása</span><span class="sxs-lookup"><span data-stu-id="6c0ca-128">Cabinet finish</span></span> | <span data-ttu-id="6c0ca-129">Fekete, tölgyfa, rózsafa, fehér</span><span class="sxs-lookup"><span data-stu-id="6c0ca-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="6c0ca-130">Elülső rács</span><span class="sxs-lookup"><span data-stu-id="6c0ca-130">Front grill</span></span>    | <span data-ttu-id="6c0ca-131">Fekete, fém, fehér</span><span class="sxs-lookup"><span data-stu-id="6c0ca-131">Black, Metal, White</span></span>         |

<span data-ttu-id="6c0ca-132">A következő táblázat bemutatja a kombinációk határozzák meg, hogy a **Szín és kivitel** táblamegszorítás.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="6c0ca-133">A táblamegszorítás használatával konfigurálhatja egy tölgy Befejezés és fekete ráccsal, egy rózsafa Befejezés és fehér rács előadó, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="6c0ca-134">Elvégzés</span><span class="sxs-lookup"><span data-stu-id="6c0ca-134">Finish</span></span>         | <span data-ttu-id="6c0ca-135">Rács</span><span class="sxs-lookup"><span data-stu-id="6c0ca-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="6c0ca-136">Tölgyfa</span><span class="sxs-lookup"><span data-stu-id="6c0ca-136">Oak</span></span>            | <span data-ttu-id="6c0ca-137">Fekete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-137">Black</span></span>                       |
| <span data-ttu-id="6c0ca-138">Rózsafa</span><span class="sxs-lookup"><span data-stu-id="6c0ca-138">Rosewood</span></span>       | <span data-ttu-id="6c0ca-139">Fehér</span><span class="sxs-lookup"><span data-stu-id="6c0ca-139">White</span></span>                       |
| <span data-ttu-id="6c0ca-140">Fehér</span><span class="sxs-lookup"><span data-stu-id="6c0ca-140">White</span></span>          | <span data-ttu-id="6c0ca-141">Fekete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-141">Black</span></span>                       |
| <span data-ttu-id="6c0ca-142">Fehér</span><span class="sxs-lookup"><span data-stu-id="6c0ca-142">White</span></span>          | <span data-ttu-id="6c0ca-143">Fehér</span><span class="sxs-lookup"><span data-stu-id="6c0ca-143">White</span></span>                       |
| <span data-ttu-id="6c0ca-144">Fekete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-144">Black</span></span>          | <span data-ttu-id="6c0ca-145">Fekete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-145">Black</span></span>                       |
| <span data-ttu-id="6c0ca-146">Fekete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-146">Black</span></span>          | <span data-ttu-id="6c0ca-147">Fém</span><span class="sxs-lookup"><span data-stu-id="6c0ca-147">Metal</span></span>                       | 

<span data-ttu-id="6c0ca-148">A táblázatok megszorításai felhasználó által definiáltak vagy rendszer definiáltak is lehetnek.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="6c0ca-149">További tudnivalókért lásd: [Rendszer által definiált és felhasználó által definiált táblamegszorítások](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="6c0ca-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="6c0ca-150">Milyen szintaxist kell használni korlátozások kiírására?</span><span class="sxs-lookup"><span data-stu-id="6c0ca-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="6c0ca-151">A feltételt az Optimization Modeling Language (OML) szintaxisa alapján kell megírnia.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="6c0ca-152">A rendszer a Microsoft Solver Foundation megszorításfeloldóját használja a megszorítások megoldására.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="6c0ca-153">Kifejezés megszorítások és táblamegszorítások</span><span class="sxs-lookup"><span data-stu-id="6c0ca-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="6c0ca-154">Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="6c0ca-155">Hoz létre olyan táblamegszorításhoz be egy mátrixban, mivel egy Kifejezésmegszorítás az egyes utasítást.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="6c0ca-156">A termék konfigurálásához teljesen mindegy, milyen megszorítás használatos.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="6c0ca-157">Az alábbi példák mutatják a beállításainak alkalmazását.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="6c0ca-158">A termék a következő megszorítás beállítások használatával konfigurálásakor ezt követően a kombinációkat használhatók:</span><span class="sxs-lookup"><span data-stu-id="6c0ca-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="6c0ca-159">A termék fekete színnel 30 vagy 50 mérete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="6c0ca-160">A termék piros színnel és 20 mérettel</span><span class="sxs-lookup"><span data-stu-id="6c0ca-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="6c0ca-161">Táblamegszorítási csoport</span><span class="sxs-lookup"><span data-stu-id="6c0ca-161">Table constraint setup</span></span>

| <span data-ttu-id="6c0ca-162">Szín</span><span class="sxs-lookup"><span data-stu-id="6c0ca-162">Color</span></span> | <span data-ttu-id="6c0ca-163">Méret</span><span class="sxs-lookup"><span data-stu-id="6c0ca-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="6c0ca-164">Fekete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-164">Black</span></span> | <span data-ttu-id="6c0ca-165">30</span><span class="sxs-lookup"><span data-stu-id="6c0ca-165">30</span></span>   |
| <span data-ttu-id="6c0ca-166">Fekete</span><span class="sxs-lookup"><span data-stu-id="6c0ca-166">Black</span></span> | <span data-ttu-id="6c0ca-167">50</span><span class="sxs-lookup"><span data-stu-id="6c0ca-167">50</span></span>   |
| <span data-ttu-id="6c0ca-168">Piros</span><span class="sxs-lookup"><span data-stu-id="6c0ca-168">Red</span></span>   | <span data-ttu-id="6c0ca-169">20</span><span class="sxs-lookup"><span data-stu-id="6c0ca-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="6c0ca-170">Kifejezésmegszorítás</span><span class="sxs-lookup"><span data-stu-id="6c0ca-170">Expression constraint setup</span></span>

<span data-ttu-id="6c0ca-171">(Szín == "Fekete" & (méret == "30" | méret == "50")) | (szín == "Piros" & mérete = "20")</span><span class="sxs-lookup"><span data-stu-id="6c0ca-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="6c0ca-172">I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?</span><span class="sxs-lookup"><span data-stu-id="6c0ca-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="6c0ca-173">Előtag rendelkezésre álló operátorok a használatával egy Kifejezésmegszorítás írhat vagy használatával infix jelölés.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="6c0ca-174">A **Min** , **Max** és **Abs** operátoroknál nem használhat infix jelölést.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-174">For the **Min** , **Max** , and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="6c0ca-175">A legtöbb programnyelven alapértelmezésként ezen operátorok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="6c0ca-176">I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?</span><span class="sxs-lookup"><span data-stu-id="6c0ca-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="6c0ca-177">A következő táblázatokban a listában az operátorok és infix jelölések, amely lehet használni, amikor egy Kifejezésmegszorítás összetevőhöz ír egy termékkonfigurációs modell.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="6c0ca-178">A példákban a első táblázatban megtekintheti a kifejezés írása infix jelöléssel, vagy az operátorok segítségével.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c0ca-179">Kezelő</span><span class="sxs-lookup"><span data-stu-id="6c0ca-179">Operator</span></span></th>
<th><span data-ttu-id="6c0ca-180">Leírás</span><span class="sxs-lookup"><span data-stu-id="6c0ca-180">Description</span></span></th>
<th><span data-ttu-id="6c0ca-181">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="6c0ca-181">Syntax</span></span></th>
<th><span data-ttu-id="6c0ca-182">Példák</span><span class="sxs-lookup"><span data-stu-id="6c0ca-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6c0ca-183">Implikálja</span><span class="sxs-lookup"><span data-stu-id="6c0ca-183">Implies</span></span></td>
<td><span data-ttu-id="6c0ca-184">Ez akkor is igaz, ha az első feltétel nem teljesül, a második feltétel értéke igaz, vagy mindkettőt.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="6c0ca-185">Azt jelenti, [a, b] infix: a-: b</span><span class="sxs-lookup"><span data-stu-id="6c0ca-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-186"><strong>Műveleti jel:</strong> a következőt jelenti: [x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="6c0ca-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="6c0ca-187"><strong>Infix jelölés:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="6c0ca-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6c0ca-188">És</span><span class="sxs-lookup"><span data-stu-id="6c0ca-188">And</span></span></td>
<td><span data-ttu-id="6c0ca-189">Ez akkor is igaz, csak az összes feltételek teljesülése esetén.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="6c0ca-190">Ha a feltétel értéke 0 (nulla), <strong>Igaz</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="6c0ca-191">And[argumentumok], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-192"><strong>Műveleti jel:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="6c0ca-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="6c0ca-193"><strong>Infix jelölés:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="6c0ca-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6c0ca-194">Vagy</span><span class="sxs-lookup"><span data-stu-id="6c0ca-194">Or</span></span></td>
<td><span data-ttu-id="6c0ca-195">Ez akkor is igaz, ha bármelyik feltétel teljesül.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-195">This is true if any condition is true.</span></span> <span data-ttu-id="6c0ca-196">Ha a feltétel értéke 0 (nulla), <strong>Hamis</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="6c0ca-197">Or[argumentumok], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-198"><strong>Műveleti jel:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="6c0ca-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="6c0ca-199"><strong>Infix jelölés:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="6c0ca-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6c0ca-200">Plusz</span><span class="sxs-lookup"><span data-stu-id="6c0ca-200">Plus</span></span></td>
<td><span data-ttu-id="6c0ca-201">Ez az összegek feltételeit.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-201">This sums its conditions.</span></span> <span data-ttu-id="6c0ca-202">Ha a feltétel értéke 0 (nulla), <strong>0</strong>-t hoz létre.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="6c0ca-203">Plusz[argumentumok], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-204"><strong>Művelet:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="6c0ca-205"><strong>Infix jelölés:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6c0ca-206">Mínusz</span><span class="sxs-lookup"><span data-stu-id="6c0ca-206">Minus</span></span></td>
<td><span data-ttu-id="6c0ca-207">Ez a argumentum ellentettjét adja.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-207">This negates its argument.</span></span> <span data-ttu-id="6c0ca-208">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="6c0ca-209">[Kifejezés], csökkentett infix: - kifejezés</span><span class="sxs-lookup"><span data-stu-id="6c0ca-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-210"><strong>Művelet:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="6c0ca-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="6c0ca-211"><strong>Infix jelölés:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="6c0ca-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6c0ca-212">(ABS)</span><span class="sxs-lookup"><span data-stu-id="6c0ca-212">Abs</span></span></td>
<td><span data-ttu-id="6c0ca-213">Ez a termelésnek állapotuk adat abszolút értéke.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="6c0ca-214">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="6c0ca-215">[Kifejezés] ABS</span><span class="sxs-lookup"><span data-stu-id="6c0ca-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="6c0ca-216"><strong>Művelet:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="6c0ca-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6c0ca-217">Idők</span><span class="sxs-lookup"><span data-stu-id="6c0ca-217">Times</span></span></td>
<td><span data-ttu-id="6c0ca-218">Ez a feltétel a termék vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-218">This takes the product of its conditions.</span></span> <span data-ttu-id="6c0ca-219">Ha a feltétel értéke 0 (nulla), <strong>1</strong>-t hoz létre.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="6c0ca-220">Szorzás[argumentumok], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-221"><strong>Művelet:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="6c0ca-222"><strong>Infix jelölés:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6c0ca-223">Teljesítmény</span><span class="sxs-lookup"><span data-stu-id="6c0ca-223">Power</span></span></td>
<td><span data-ttu-id="6c0ca-224">Ez a termelésnek a tudományos.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-224">This takes an exponential.</span></span> <span data-ttu-id="6c0ca-225">Ez akkor érvényes hatványkitevő jobbról balra.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="6c0ca-226">(Ez azt jelenti, hogy jobbra társuló.) Ezért <strong>Hatvány[a, b, c]</strong> egyenlő: <strong>Hatvány[a, hatvány[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="6c0ca-227">A <strong>Power</strong> csak használható pozitív állandó, mint a kitevő.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="6c0ca-228">Hatvány[argumentumok], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-229"><strong>Művelet:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="6c0ca-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="6c0ca-230"><strong>Infix jelölés:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="6c0ca-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6c0ca-231">Max.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-231">Max</span></span></td>
<td><span data-ttu-id="6c0ca-232">A legnagyobb feltétel jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-232">This produces the largest condition.</span></span> <span data-ttu-id="6c0ca-233">Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="6c0ca-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="6c0ca-234">Max[args]</span></span></td>
<td><span data-ttu-id="6c0ca-235"><strong>Művelet:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6c0ca-236">Min.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-236">Min</span></span></td>
<td><span data-ttu-id="6c0ca-237">A legkisebb feltételt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-237">This produces the smallest condition.</span></span> <span data-ttu-id="6c0ca-238">Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="6c0ca-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="6c0ca-239">Min[args]</span></span></td>
<td><span data-ttu-id="6c0ca-240"><strong>Művelet:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6c0ca-241">Nem</span><span class="sxs-lookup"><span data-stu-id="6c0ca-241">Not</span></span></td>
<td><span data-ttu-id="6c0ca-242">A feltétel logikai inverzét jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="6c0ca-243">Ez kell pontosan egy feltételt.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="6c0ca-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="6c0ca-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="6c0ca-245"><strong>Műveleti jel:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="6c0ca-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="6c0ca-246"><strong>Infix jelölés:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="6c0ca-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6c0ca-247">Az alábbi táblázatban szereplő példák bemutatják, hogyan lehet írni egy infix jelölés.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="6c0ca-248">Jelölés Infix:</span><span class="sxs-lookup"><span data-stu-id="6c0ca-248">Infix notation</span></span>   |                                          <span data-ttu-id="6c0ca-249">Leírás</span><span class="sxs-lookup"><span data-stu-id="6c0ca-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="6c0ca-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-250">x + y + z</span></span>     |                                           <span data-ttu-id="6c0ca-251">Hozzáadás</span><span class="sxs-lookup"><span data-stu-id="6c0ca-251">Addition</span></span>                                            |
|    <span data-ttu-id="6c0ca-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="6c0ca-253">szorzás</span><span class="sxs-lookup"><span data-stu-id="6c0ca-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="6c0ca-254">x - y</span><span class="sxs-lookup"><span data-stu-id="6c0ca-254">x - y</span></span>       | <span data-ttu-id="6c0ca-255">Bináris kivonás egy fordító bináris összeadás második megkereséséhez, megegyezik.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="6c0ca-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="6c0ca-257">A jobb oldali asszociativitást hatványkitevő</span><span class="sxs-lookup"><span data-stu-id="6c0ca-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="6c0ca-258">!x</span><span class="sxs-lookup"><span data-stu-id="6c0ca-258">!x</span></span>         |                                          <span data-ttu-id="6c0ca-259">Logikai</span><span class="sxs-lookup"><span data-stu-id="6c0ca-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="6c0ca-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="6c0ca-260">x -: y</span></span>       |                                      <span data-ttu-id="6c0ca-261">Logikai tényezők</span><span class="sxs-lookup"><span data-stu-id="6c0ca-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="6c0ca-262">x</span><span class="sxs-lookup"><span data-stu-id="6c0ca-262">x</span></span>         |                                               <span data-ttu-id="6c0ca-263">y</span><span class="sxs-lookup"><span data-stu-id="6c0ca-263">y</span></span>                                               |
|     <span data-ttu-id="6c0ca-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-264">x & y & z</span></span>     |                                          <span data-ttu-id="6c0ca-265">Logikai és</span><span class="sxs-lookup"><span data-stu-id="6c0ca-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="6c0ca-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-266">x == y == z</span></span>    |                                           <span data-ttu-id="6c0ca-267">egyenlőség</span><span class="sxs-lookup"><span data-stu-id="6c0ca-267">Equality</span></span>                                            |
|    <span data-ttu-id="6c0ca-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-268">x != y != z</span></span>    |                                           <span data-ttu-id="6c0ca-269">Különálló</span><span class="sxs-lookup"><span data-stu-id="6c0ca-269">Distinct</span></span>                                            |
|  <span data-ttu-id="6c0ca-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="6c0ca-271">Kisebb, mint</span><span class="sxs-lookup"><span data-stu-id="6c0ca-271">Less than</span></span>                                           |
|  <span data-ttu-id="6c0ca-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="6c0ca-273">Nagyobb, mint</span><span class="sxs-lookup"><span data-stu-id="6c0ca-273">Greater than</span></span>                                          |
| <span data-ttu-id="6c0ca-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="6c0ca-275">Kisebb vagy egyenlő</span><span class="sxs-lookup"><span data-stu-id="6c0ca-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="6c0ca-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="6c0ca-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="6c0ca-277">Nagyobb vagy egyenlő</span><span class="sxs-lookup"><span data-stu-id="6c0ca-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="6c0ca-278">(x)</span><span class="sxs-lookup"><span data-stu-id="6c0ca-278">(x)</span></span>        |                           <span data-ttu-id="6c0ca-279">Zárójelek alapértelmezett elsőbbségi sorrend felülbírálása.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="6c0ca-280">Miért nem megfelelő a kifejezés megszorítások ellenőrzése?</span><span class="sxs-lookup"><span data-stu-id="6c0ca-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="6c0ca-281">Attribútumok, alkatrészek vagy az egy termékkonfigurációs modell alösszetevői attribútumfeloldó neve fenntartott kulcsszó nem használható.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span><span data-ttu-id="6c0ca-282"> Az alábbi lista a foglalt kulcsszavakat mutatja, amelyek nem használhatók:</span><span class="sxs-lookup"><span data-stu-id="6c0ca-282"> Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="6c0ca-283">Felső határ</span><span class="sxs-lookup"><span data-stu-id="6c0ca-283">Ceiling</span></span>
-   <span data-ttu-id="6c0ca-284">Elem</span><span class="sxs-lookup"><span data-stu-id="6c0ca-284">Element</span></span>
-   <span data-ttu-id="6c0ca-285">Egyenlő</span><span class="sxs-lookup"><span data-stu-id="6c0ca-285">Equal</span></span>
-   <span data-ttu-id="6c0ca-286">Emelet</span><span class="sxs-lookup"><span data-stu-id="6c0ca-286">Floor</span></span>
-   <span data-ttu-id="6c0ca-287">Ha</span><span class="sxs-lookup"><span data-stu-id="6c0ca-287">If</span></span>
-   <span data-ttu-id="6c0ca-288">Kisebb</span><span class="sxs-lookup"><span data-stu-id="6c0ca-288">Less</span></span>
-   <span data-ttu-id="6c0ca-289">Nagyobb</span><span class="sxs-lookup"><span data-stu-id="6c0ca-289">Greater</span></span>
-   <span data-ttu-id="6c0ca-290">Implikálja</span><span class="sxs-lookup"><span data-stu-id="6c0ca-290">Implies</span></span>
-   <span data-ttu-id="6c0ca-291">Eseménynapló</span><span class="sxs-lookup"><span data-stu-id="6c0ca-291">Log</span></span>
-   <span data-ttu-id="6c0ca-292">Max.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-292">Max</span></span>
-   <span data-ttu-id="6c0ca-293">perc</span><span class="sxs-lookup"><span data-stu-id="6c0ca-293">Min</span></span>
-   <span data-ttu-id="6c0ca-294">Mínusz</span><span class="sxs-lookup"><span data-stu-id="6c0ca-294">Minus</span></span>
-   <span data-ttu-id="6c0ca-295">Plusz</span><span class="sxs-lookup"><span data-stu-id="6c0ca-295">Plus</span></span>
-   <span data-ttu-id="6c0ca-296">Teljesítmény</span><span class="sxs-lookup"><span data-stu-id="6c0ca-296">Power</span></span>
-   <span data-ttu-id="6c0ca-297">Idők</span><span class="sxs-lookup"><span data-stu-id="6c0ca-297">Times</span></span>
-   <span data-ttu-id="6c0ca-298">Időköz</span><span class="sxs-lookup"><span data-stu-id="6c0ca-298">Slot</span></span>
-   <span data-ttu-id="6c0ca-299">Típus</span><span class="sxs-lookup"><span data-stu-id="6c0ca-299">Model</span></span>
-   <span data-ttu-id="6c0ca-300">Döntés</span><span class="sxs-lookup"><span data-stu-id="6c0ca-300">Decision</span></span>
-   <span data-ttu-id="6c0ca-301">Cél</span><span class="sxs-lookup"><span data-stu-id="6c0ca-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="6c0ca-302">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6c0ca-302">Additional resources</span></span>
--------

[<span data-ttu-id="6c0ca-303">Kifejezésmegszorítás szerkesztője</span><span class="sxs-lookup"><span data-stu-id="6c0ca-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="6c0ca-304">Kalkuláció hozzáadása termékkonfigurációs modellhez</span><span class="sxs-lookup"><span data-stu-id="6c0ca-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)




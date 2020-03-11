---
title: VALUEIN ER-függvény
description: A témakör tájékoztatást nyújt a VALUEIN Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0df97234df41d11897473dea4e85354e82d36ec
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041699"
---
# <span data-ttu-id="a7a0f-103"><a name="VALUEIN">VALUEIN ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="a7a0f-103"><a name="VALUEIN">VALUEIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7a0f-104">A `VALUEIN` függvény azt határozza meg, hogy a megadott bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="a7a0f-105">A függvény *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="a7a0f-106">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7a0f-107">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="a7a0f-107">Syntax</span></span>

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="a7a0f-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="a7a0f-108">Arguments</span></span>

<span data-ttu-id="a7a0f-109">`input`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="a7a0f-109">`input`: *Field*</span></span>

<span data-ttu-id="a7a0f-110">A *Rekordlista* típusának megfelelő adatforrásra vonatkozó elem érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="a7a0f-111">Az elem értékét a rendszer megfelelteti.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-111">The value of this item will be matched.</span></span>

<span data-ttu-id="a7a0f-112">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="a7a0f-112">`list`: *Record list*</span></span>

<span data-ttu-id="a7a0f-113">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a7a0f-114">`list item expression`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="a7a0f-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="a7a0f-115">Egy érvényes feltételes kifejezés, amely a megadott lista egyetlen mezőjére mutat vagy azt tartalmazza, amely a megfeleltetéshez használandó.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="a7a0f-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="a7a0f-116">Return values</span></span>

<span data-ttu-id="a7a0f-117">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="a7a0f-117">*Boolean*</span></span>

<span data-ttu-id="a7a0f-118">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a7a0f-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a7a0f-119">Usage notes</span></span>

<span data-ttu-id="a7a0f-120">Általában a `VALUEIN` függvény **VAGY** feltételek egy csoportjára fordul le.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span>

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="a7a0f-121">Bizonyos esetekben az `EXISTS JOIN` operátor használatával lefordítható egy adatbázis SQL-utasításra.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-121">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="a7a0f-122">1. példa</span><span class="sxs-lookup"><span data-stu-id="a7a0f-122">Example 1</span></span>

<span data-ttu-id="a7a0f-123">A modell-hozzárendelésében meghatározza a *Számított mező* típus **Lista** adatforrását.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-123">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="a7a0f-124">Az adatforrás tartalmazza a `SPLIT ("a,b,c", ",")` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-124">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="a7a0f-125">Adatforrás meghívásakor, ha `VALUEIN ("B", List, List.Value)` kifejezésként lett konfigurálva, akkor **IGAZ** értéket ad eredményül.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-125">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="a7a0f-126">Ebben az esetben a `VALUEIN` függvény a következő feltételek csoportjára fordul le: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, ahol `("B" = "b")` értéke **IGAZ**.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-126">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="a7a0f-127">Adatforrás meghívásakor, ha a `VALUEIN ("B", List, LEFT(List.Value, 0))` kifejezésként lett konfigurálva, akkor **HAMIS** értéket ad eredményül.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-127">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="a7a0f-128">Ebben az esetben a `VALUEIN` függvény a következő feltételre fordul le: `("B" = "")`, amely nem egyenlő az **IGAZ** értékkel.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-128">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="a7a0f-129">Az ilyen feltétel szövegében a karakterszám felső határa 32 768 karakter.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-129">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="a7a0f-130">Ezért ne hozzon létre olyan adatforrásokat, amelyek túlléphetik ezt a korlátot futásidőben.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-130">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="a7a0f-131">Ha túllépte a korlátot, az alkalmazás leáll, és kivételt küld.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-131">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="a7a0f-132">Például ez a helyzet akkor fordulhat elő, ha így van beállítva az adatforrás: `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, és a **Lista 1** és **Lista 2** listák nagy mennyiségű rekordot tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-132">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="a7a0f-133">Bizonyos esetekben a `VALUEIN` funkció egy adatbázis-utasításra fordul le az `EXISTS JOIN` operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-133">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="a7a0f-134">Ez a viselkedés akkor fordul elő, amikor a [FILTER](er-functions-list-filter.md) függvény használatos, és a következő feltételek teljesülnek:</span><span class="sxs-lookup"><span data-stu-id="a7a0f-134">This behavior occurs when the [FILTER](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="a7a0f-135">A **LEKÉRDEZÉS KÉRÉSE** beállítás ki van kapcsolva a `VALUEIN` függvény adatforrása esetében, amely rekordok listájára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-135">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="a7a0f-136">További feltételek nem vonatkoznak erre az adatforrásra futásidőben.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-136">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="a7a0f-137">Nincsenek konfigurálva beágyazott kifejezések az adatforrás `VALUEIN` függvényéhez, amely rekordok listájára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-137">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="a7a0f-138">A `VALUEIN` függvény listaeleme a megadott adatforrás mezőjére hivatkozik, nem az adatforrás kifejezésére vagy metódusára.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-138">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="a7a0f-139">Fontolja meg ennek használatát a [WHERE](er-functions-list-where.md) függvény helyett, ahogy ebben a példában korábban ismertettük.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-139">Consider using this option instead of the [WHERE](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="a7a0f-140">2. példa</span><span class="sxs-lookup"><span data-stu-id="a7a0f-140">Example 2</span></span>

<span data-ttu-id="a7a0f-141">A következő adatforrás megadása a modell-hozzárendelésben:</span><span class="sxs-lookup"><span data-stu-id="a7a0f-141">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="a7a0f-142">A *Táblázatbejegyzés* típus **Tartalmazza** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-142">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="a7a0f-143">Ez az adatforrás az Intrastat-táblára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-143">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="a7a0f-144">A *Táblázatbejegyzés* típus **Port** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-144">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="a7a0f-145">Ez az adatforrás az IntrastatPort-táblára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-145">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="a7a0f-146">Amikor adatforrás van meghívva, amely a `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` kifejezésben van beállítva, a következő SQL-utasítás generálódik, hogy az Intrastat-tábla szűrt rekordjait adja vissza:</span><span class="sxs-lookup"><span data-stu-id="a7a0f-146">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="a7a0f-147">A **dataAreaId** mezők esetében a végső SQL-utasítás az `IN` operátor használatával van előállítva.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-147">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="a7a0f-148">3. példa</span><span class="sxs-lookup"><span data-stu-id="a7a0f-148">Example 3</span></span>

<span data-ttu-id="a7a0f-149">A következő adatforrás megadása a modell-hozzárendelésben:</span><span class="sxs-lookup"><span data-stu-id="a7a0f-149">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="a7a0f-150">A *Számított mező* típus **Le** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-150">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="a7a0f-151">Az adatforrás tartalmazza a `SPLIT ("DEMF,GBSI,USMF", ",")` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-151">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="a7a0f-152">A *Táblázatbejegyzés* típus **Tartalmazza** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-152">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="a7a0f-153">Ez az adatforrás az Intrastat-táblára hivatkozik, és a **Vállalatközi** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-153">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="a7a0f-154">Amikor adatforrás van meghívva, amely a `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` kifejezésként van beállítva, a végső SQL-utasítás tartalmazza a következő feltételt.</span><span class="sxs-lookup"><span data-stu-id="a7a0f-154">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="a7a0f-155">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a7a0f-155">Additional resources</span></span>

[<span data-ttu-id="a7a0f-156">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="a7a0f-156">Logical functions</span></span>](er-functions-category-logical.md)

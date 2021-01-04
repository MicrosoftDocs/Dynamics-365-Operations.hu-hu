---
title: VALUEINLARGE ER függvény
description: A témakör tájékoztatást nyújt a VALUEINLARGE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 26a7148a4caa80a191688145bac625bdf0bf83b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686906"
---
# <a name="valueinlarge-er-function"></a><span data-ttu-id="d5df9-103">VALUEINLARGE ER függvény</span><span class="sxs-lookup"><span data-stu-id="d5df9-103">VALUEINLARGE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d5df9-104">A `VALUEINLARGE` függvény azt határozza meg, hogy a megadott *Int64* vagy *Egész szám* típusú bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével.</span><span class="sxs-lookup"><span data-stu-id="d5df9-104">The `VALUEINLARGE` function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="d5df9-105">A függvény egy *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével.</span><span class="sxs-lookup"><span data-stu-id="d5df9-105">The function returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="d5df9-106">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="d5df9-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> <span data-ttu-id="d5df9-107">Ha meg szeretné ismerni az eltérést a `VALUEIN` függvényhez képest, akkor témakör későbbi [Használati megjegyzés](#usage_note) szakasza tartalmaz további tudnivalókat.</span><span class="sxs-lookup"><span data-stu-id="d5df9-107">To understand the difference with the `VALUEIN` function, see the [Usage note](#usage_note) section later in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5df9-108">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="d5df9-108">Syntax</span></span>

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="d5df9-109">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="d5df9-109">Arguments</span></span>

<span data-ttu-id="d5df9-110">`input`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="d5df9-110">`input`: *Field*</span></span>

<span data-ttu-id="d5df9-111">A *Rekordlista* elemtípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="d5df9-111">The valid path of a data source item of the *Record list* type.</span></span> <span data-ttu-id="d5df9-112">Az elem értékét a rendszer megfelelteti.</span><span class="sxs-lookup"><span data-stu-id="d5df9-112">The value of this item will be matched.</span></span>

<span data-ttu-id="d5df9-113">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="d5df9-113">`list`: *Record list*</span></span>

<span data-ttu-id="d5df9-114">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="d5df9-114">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="d5df9-115">`list item expression`: *Kifejezés*</span><span class="sxs-lookup"><span data-stu-id="d5df9-115">`list item expression`: *Expression*</span></span>

<span data-ttu-id="d5df9-116">Egy érvényes feltételes kifejezés, amely a megadott lista egyetlen mezőjére mutat vagy azt tartalmazza, amely a megfeleltetéshez használandó.</span><span class="sxs-lookup"><span data-stu-id="d5df9-116">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="d5df9-117">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="d5df9-117">Return values</span></span>

<span data-ttu-id="d5df9-118">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="d5df9-118">*Boolean*</span></span>

<span data-ttu-id="d5df9-119">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="d5df9-119">The resulting *Boolean* value.</span></span>

## <a name=""></a><span data-ttu-id="d5df9-120"><a name="usage_note">Használati megjegyzések</a></span><span class="sxs-lookup"><span data-stu-id="d5df9-120"><a name="usage_note">Usage notes</a></span></span>

<span data-ttu-id="d5df9-121">Amikor a megadott bemenet egy *Int64* vagy *Egész szám* típusú adatforrás elemként jeleni meg , akkor a hívás egy közvetlen SQL-utasításnak van lefordítva, a megadott lista ideiglenes SQL-táblára lesz alakítva, és egyetlen `EXISTS JOIN` lekérdezés végrehajtásával történik meg a egyeztetés az adatbázisban.</span><span class="sxs-lookup"><span data-stu-id="d5df9-121">When the specified input represents an *Int64* or *Integer* type of a data source item, the call to which is translatable to a direct SQL statement, the specified list is converted to a temporary SQL table and matching is performed in the database by executing a single `EXISTS JOIN` query.</span></span> <span data-ttu-id="d5df9-122">Ellenkező esetben ez a függvény a [`VALUEIN`](er-functions-logical-valuein.md) függvénnyel megegyezően működik.</span><span class="sxs-lookup"><span data-stu-id="d5df9-122">Otherwise, this function works as the [`VALUEIN`](er-functions-logical-valuein.md) function.</span></span>

<span data-ttu-id="d5df9-123">Ha a megadott bemenet egy olyan adatforrás-elemet jelent, amely nem *Int64* vagy *Egész szám* típusú, akkor a tervezéskor hiba történik, ha a `VALUEINLARGE` függvény nem alkalmazható a konfigurált ER kifejezésre.</span><span class="sxs-lookup"><span data-stu-id="d5df9-123">When the specified input represents a data source item that is designed as an item other than *Int64* and *Integer* type, an error occurs at design time informing you that the `VALUEINLARGE` function is not applicable for the configured ER expression.</span></span>

<span data-ttu-id="d5df9-124">Ha `VALUEINLARGE` függvénykifejezés végre van hajtva , és a végrehajtásban egynél több ideiglenes tábla van használatban, futásidejű hiba történik.</span><span class="sxs-lookup"><span data-stu-id="d5df9-124">When the `VALUEINLARGE` function expression is executed and more than one temporary table is used in scope of this execution, a runtime error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="d5df9-125">Példa</span><span class="sxs-lookup"><span data-stu-id="d5df9-125">Example</span></span>

<span data-ttu-id="d5df9-126">A következő adatforrás megadása a modell-hozzárendelésben:</span><span class="sxs-lookup"><span data-stu-id="d5df9-126">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="d5df9-127">A *Táblázatbejegyzés* típus **Tartalmazza** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="d5df9-127">The **In** data source of the *Table records* type.</span></span>
    - <span data-ttu-id="d5df9-128">Ez az adatforrás az **Intrastat** táblára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="d5df9-128">This data source refers to the **Intrastat** table.</span></span>
    - <span data-ttu-id="d5df9-129">A **Több vállalatot érintő** beállítás **Nem** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="d5df9-129">The **Cross-company** option is set to **No**.</span></span>
- <span data-ttu-id="d5df9-130">A *Számított mező* típus **InMemory** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="d5df9-130">The **InMemory** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="d5df9-131">Az adatforrás tartalmazza a `WHERE (In, In.Port <> "")` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d5df9-131">This data source contains the expression `WHERE (In, In.Port <> "")`.</span></span>
- <span data-ttu-id="d5df9-132">A *Számított mező* típus **InFiltered** adatforrása.</span><span class="sxs-lookup"><span data-stu-id="d5df9-132">The **InFiltered** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="d5df9-133">Az adatforrás tartalmazza a `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)` kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d5df9-133">This data source contains the expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span></span>

<span data-ttu-id="d5df9-134">Amikor az adatforrás **InFiltered** vállalat **DEMF** környezetében van meghívva , az alkalmazás-adatbázisban egy új ideiglenes tábla jön létre, akkor a rendszer beilleszti a rekordok azonosító kódjainak a mezőbe történő beolvasását a táblába, és a következő SQL-utasítást hozza létre az **Intrastat** tábla szűrt rekordjainak visszaküldéséhez .</span><span class="sxs-lookup"><span data-stu-id="d5df9-134">When the data source **InFiltered** is called under the context of the company **DEMF**, a new temporary table is created in the application database, the collected in memory list of record identification codes are inserted to this table, and the following SQL statement is generated to return filtered records of the **Intrastat** table.</span></span>

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a><span data-ttu-id="d5df9-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d5df9-135">Additional resources</span></span>

[<span data-ttu-id="d5df9-136">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="d5df9-136">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="d5df9-137">VALUEIN függvények</span><span class="sxs-lookup"><span data-stu-id="d5df9-137">VALUEIN functions</span></span>](er-functions-logical-valuein.md)

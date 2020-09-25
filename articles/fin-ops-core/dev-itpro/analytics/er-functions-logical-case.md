---
title: CASE ER-függvény
description: A témakör tájékoztatást nyújt a CASE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 605bd50005ee4e5866a5be9e16df6da3139ad19c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744767"
---
# <a name="case-er-function"></a><span data-ttu-id="0ce8f-103">CASE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="0ce8f-103">CASE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ce8f-104">A `CASE` függvény kiértékeli a megadott kifejezés értékét a megadott alternatív beállításokkal, és visszaadja az első beállítás eredményét, amely megegyezik a megadott kifejezés értékével.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-104">The `CASE` function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="0ce8f-105">Ellenkező esetben a nem kötelező alapértelmezett eredményt adja vissza, ha az alapértelmezett eredmény a hívott függvény utolsó argumentumaként van megadva, amelyet nem előz meg beállítás.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-105">Otherwise, it returns the optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="0ce8f-106">A visszaadott érték bármely támogatott adattípus értéke lehet.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ce8f-107">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0ce8f-107">Syntax</span></span>

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a><span data-ttu-id="0ce8f-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0ce8f-108">Arguments</span></span>

<span data-ttu-id="0ce8f-109">`expression`: *Primitív adattípus* (logikai, numerikus vagy szöveg)</span><span class="sxs-lookup"><span data-stu-id="0ce8f-109">`expression`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="0ce8f-110">Érvényes kifejezés, amely a primitív adattípus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-110">A valid expression that returns a value of the primitive data type.</span></span>

<span data-ttu-id="0ce8f-111">`option 1`: *Primitív adattípus* (logikai, numerikus vagy szöveg)</span><span class="sxs-lookup"><span data-stu-id="0ce8f-111">`option 1`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="0ce8f-112">Érvényes kifejezés, amely ugyanazt a primitív adattípust adja eredményül, mint a hívott függvény `expression` argumentuma.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-112">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="0ce8f-113">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-113">This argument is required.</span></span>

<span data-ttu-id="0ce8f-114">`result 1`: *A támogatott adattípusok bármelyike*</span><span class="sxs-lookup"><span data-stu-id="0ce8f-114">`result 1`: *Any of the supported data types*</span></span>

<span data-ttu-id="0ce8f-115">Az előző beállításnak megfelelő visszaadott eredmény.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-115">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="0ce8f-116">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-116">This argument is required.</span></span>

<span data-ttu-id="0ce8f-117">`option N`: *Primitív adattípus* (logikai, numerikus vagy szöveg)</span><span class="sxs-lookup"><span data-stu-id="0ce8f-117">`option N`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="0ce8f-118">Érvényes kifejezés, amely ugyanazt a primitív adattípust adja eredményül, mint a hívott függvény `expression` argumentuma.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-118">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="0ce8f-119">Ez az argumentum nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-119">This argument is optional.</span></span>

<span data-ttu-id="0ce8f-120">`result N`: *A támogatott adattípusok bármelyike*</span><span class="sxs-lookup"><span data-stu-id="0ce8f-120">`result N`: *Any of the supported data types*</span></span>

<span data-ttu-id="0ce8f-121">Az előző beállításnak megfelelő visszaadott eredmény.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-121">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="0ce8f-122">Ez az argumentum nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-122">This argument is optional.</span></span>

<span data-ttu-id="0ce8f-123">`default result`: *A támogatott adattípusok bármelyike*</span><span class="sxs-lookup"><span data-stu-id="0ce8f-123">`default result`: *Any of the supported data types*</span></span>

<span data-ttu-id="0ce8f-124">A visszaadott eredmény, ha nincs egyezés.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-124">The result that should be returned if there is no match.</span></span> <span data-ttu-id="0ce8f-125">Ez az argumentum nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-125">This argument is optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="0ce8f-126">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="0ce8f-126">Return values</span></span>

<span data-ttu-id="0ce8f-127">*A támogatott adattípusok bármelyike*</span><span class="sxs-lookup"><span data-stu-id="0ce8f-127">*Any of the supported data types*</span></span>

<span data-ttu-id="0ce8f-128">Bármely támogatott adattípus eredményül kapott értéke.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-128">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0ce8f-129">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0ce8f-129">Usage notes</span></span>

<span data-ttu-id="0ce8f-130">Ha nincs egyezés, és nincs megadva alapértelmezett eredmény, a rendszer egy kivételt dob a futtatáskor.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-130">An exception is thrown at runtime if there is no match and an optional default result isn't defined.</span></span>

<span data-ttu-id="0ce8f-131">Minden eredményt ugyanazzal az adattípusra kell megadni.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-131">All results must be specified by using the same data type.</span></span> <span data-ttu-id="0ce8f-132">Ha a konfigurált eredmények adattípusai nem egyeznek, a tervezési időben kivétel történik.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-132">An exception is thrown at design time if the data types of the configured results don't match.</span></span>

<span data-ttu-id="0ce8f-133">Ha az első eredmény értéke és az *N*. eredmény értéke a *Tároló (rekord)* vagy a *Rekordlista* adattípus értékei, az eredménynek csak a mindkét értékben létező mezői vannak.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-133">If the first result value and the *N*th result value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="0ce8f-134">Példa</span><span class="sxs-lookup"><span data-stu-id="0ce8f-134">Example</span></span>

<span data-ttu-id="0ce8f-135">A `CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` a **„TÉL”** karakterláncot adja vissza, ha az alkalmazás aktuális munkamenetdátuma október és december között van.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returns the string **"WINTER"** if the current application session date is between October and December.</span></span> <span data-ttu-id="0ce8f-136">Ellenkező esetben üres karakterláncot jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="0ce8f-136">Otherwise, it returns a blank string.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ce8f-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0ce8f-137">Additional resources</span></span>

[<span data-ttu-id="0ce8f-138">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="0ce8f-138">Logical functions</span></span>](er-functions-category-logical.md)

---
title: A típuskonverzió kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott konverziós függvényekről.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2cfa5deb3b2c00565759e4334a002bf112f888ac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917649"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="f2025-103">A típuskonverzió kategóriába tartozó ER-függvények listája</span><span class="sxs-lookup"><span data-stu-id="f2025-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2025-104">Az Elektronikus jelentéskészítés (ER) típuskonverziós függvényei az értékek típusok közötti konvertálására használhatók.</span><span class="sxs-lookup"><span data-stu-id="f2025-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="f2025-105">Ez a témakör ezeknek a függvényeknek az összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="f2025-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="f2025-106">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="f2025-106">Type conversion functions</span></span>

| <span data-ttu-id="f2025-107">Funkció</span><span class="sxs-lookup"><span data-stu-id="f2025-107">Function</span></span> | <span data-ttu-id="f2025-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="f2025-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f2025-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="f2025-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="f2025-110">Ez a függvény a megadott karakterláncot jelölő *Int64* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="f2025-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="f2025-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="f2025-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="f2025-112">Ez a függvény a megadott karakterláncot jelölő *Int* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="f2025-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="f2025-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="f2025-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="f2025-114">Ez a függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át.</span><span class="sxs-lookup"><span data-stu-id="f2025-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="f2025-115">Az átalakítás során a megadott tizedesjegy-elválasztókat és számjegy-csoportosítókat kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="f2025-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="f2025-116">Érték</span><span class="sxs-lookup"><span data-stu-id="f2025-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="f2025-117">Ez a függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át.</span><span class="sxs-lookup"><span data-stu-id="f2025-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="f2025-118">Típuskonverziós függvények a dátum és időpont kategóriában</span><span class="sxs-lookup"><span data-stu-id="f2025-118">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="f2025-119">A következő táblázat a [dátum és időpont kategória](er-functions-category-datetime.md) típuskonverziós függvényeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="f2025-119">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="f2025-120">Funkció</span><span class="sxs-lookup"><span data-stu-id="f2025-120">Function</span></span> | <span data-ttu-id="f2025-121">Leírás</span><span class="sxs-lookup"><span data-stu-id="f2025-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f2025-122">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="f2025-122">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="f2025-123">Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú *Karakterlánc* értékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum/idő értékre.</span><span class="sxs-lookup"><span data-stu-id="f2025-123">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="f2025-124">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="f2025-124">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="f2025-125">Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott *Dátum* értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban.</span><span class="sxs-lookup"><span data-stu-id="f2025-125">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="f2025-126">DateValue</span><span class="sxs-lookup"><span data-stu-id="f2025-126">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="f2025-127">Ez a függvény egy *Dátum* értéket ad eredményül, amely egy megadott formátumú *Karakterlánc* értékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum értékre.</span><span class="sxs-lookup"><span data-stu-id="f2025-127">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="f2025-128">A lista kategória típuskonverziós függvényei</span><span class="sxs-lookup"><span data-stu-id="f2025-128">Type conversion functions in the list category</span></span>

<span data-ttu-id="f2025-129">A következő táblázat a [lista kategória](er-functions-category-list.md) típuskonverziós függvényeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="f2025-129">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="f2025-130">Funkció</span><span class="sxs-lookup"><span data-stu-id="f2025-130">Function</span></span> | <span data-ttu-id="f2025-131">Leírás</span><span class="sxs-lookup"><span data-stu-id="f2025-131">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f2025-132">Lista</span><span class="sxs-lookup"><span data-stu-id="f2025-132">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="f2025-133">Ez a függvény egy *Rekordlista* értéket ad vissza a *Tároló (rekord)* típus megadott argumentumaiból létrehozott új listaként.</span><span class="sxs-lookup"><span data-stu-id="f2025-133">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="f2025-134">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="f2025-134">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="f2025-135">Ez a függvény egy *Rekordlista* értéket ad vissza, amely a *Felsorolás* vagy a *Tároló (rekord)* típus egy adott argumentumának szerkezete alapján jön létre.</span><span class="sxs-lookup"><span data-stu-id="f2025-135">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="f2025-136">Megosztás</span><span class="sxs-lookup"><span data-stu-id="f2025-136">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="f2025-137">Ez a függvény az adott *Karakterlánc* értéket alkarakterláncokká osztja szét, és az eredményt új *Rekordlista* értékként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="f2025-137">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="f2025-138">StringJoin</span><span class="sxs-lookup"><span data-stu-id="f2025-138">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="f2025-139">Ez a függvény egy *Karakterlánc* értéket ad vissza, amely a megadott *Rekordlista* érték megadott mezőjének összefűzött értékeiből áll.</span><span class="sxs-lookup"><span data-stu-id="f2025-139">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="f2025-140">Az értékeket a megadott elválasztó elválaszthatja egymástól.</span><span class="sxs-lookup"><span data-stu-id="f2025-140">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="f2025-141">A szöveg kategória típuskonverziós függvényei</span><span class="sxs-lookup"><span data-stu-id="f2025-141">Type conversion functions in the text category</span></span>

<span data-ttu-id="f2025-142">A következő táblázat a [szöveg kategória](er-functions-category-text.md) típuskonverziós függvényeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="f2025-142">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="f2025-143">Funkció</span><span class="sxs-lookup"><span data-stu-id="f2025-143">Function</span></span> | <span data-ttu-id="f2025-144">Leírás</span><span class="sxs-lookup"><span data-stu-id="f2025-144">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f2025-145">Char</span><span class="sxs-lookup"><span data-stu-id="f2025-145">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="f2025-146">Ez a függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="f2025-146">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="f2025-147">GuidValue</span><span class="sxs-lookup"><span data-stu-id="f2025-147">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="f2025-148">Ez a függvény a megadott *Karakterlánc* típusú bemenetet *GUID* típusú adatelemmé konvertálja.</span><span class="sxs-lookup"><span data-stu-id="f2025-148">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="f2025-149">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="f2025-149">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="f2025-150">Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban.</span><span class="sxs-lookup"><span data-stu-id="f2025-150">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="f2025-151">QrCode</span><span class="sxs-lookup"><span data-stu-id="f2025-151">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="f2025-152">Ez a függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód).</span><span class="sxs-lookup"><span data-stu-id="f2025-152">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="f2025-153">Szöveg</span><span class="sxs-lookup"><span data-stu-id="f2025-153">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="f2025-154">A függvény egy *Karakterlánc* értéket ad vissza, amely a megadott számot jelzi, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja.</span><span class="sxs-lookup"><span data-stu-id="f2025-154">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="f2025-155">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f2025-155">Additional resources</span></span>

[<span data-ttu-id="f2025-156">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="f2025-156">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="f2025-157">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="f2025-157">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="f2025-158">Elektronikus jelentéskészítés képletének nyelve</span><span class="sxs-lookup"><span data-stu-id="f2025-158">Electronic reporting formula language</span></span>](er-formula-language.md)

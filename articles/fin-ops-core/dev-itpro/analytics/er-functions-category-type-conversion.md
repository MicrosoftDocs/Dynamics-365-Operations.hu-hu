---
title: A típuskonverzió kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott konverziós függvényekről.
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 199d51ae8a4dbdd7d2f3bd290a2b487ceb1174dc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752604"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="715a5-103">A típuskonverzió kategóriába tartozó ER-függvények listája</span><span class="sxs-lookup"><span data-stu-id="715a5-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="715a5-104">Az Elektronikus jelentéskészítés (ER) típuskonverziós függvényei az értékek típusok közötti konvertálására használhatók.</span><span class="sxs-lookup"><span data-stu-id="715a5-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="715a5-105">Ez a témakör ezeknek a függvényeknek az összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="715a5-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="715a5-106">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="715a5-106">Type conversion functions</span></span>

| <span data-ttu-id="715a5-107">Funkció</span><span class="sxs-lookup"><span data-stu-id="715a5-107">Function</span></span> | <span data-ttu-id="715a5-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="715a5-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="715a5-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="715a5-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="715a5-110">Ez a függvény a megadott karakterláncot jelölő *Int64* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="715a5-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="715a5-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="715a5-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="715a5-112">Ez a függvény a megadott karakterláncot jelölő *Int* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="715a5-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="715a5-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="715a5-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="715a5-114">Ez a függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át.</span><span class="sxs-lookup"><span data-stu-id="715a5-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="715a5-115">Az átalakítás során a megadott tizedesjegy-elválasztókat és számjegy-csoportosítókat kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="715a5-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="715a5-116">Érték</span><span class="sxs-lookup"><span data-stu-id="715a5-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="715a5-117">Ez a függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át.</span><span class="sxs-lookup"><span data-stu-id="715a5-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-container-category"></a><span data-ttu-id="715a5-118">A tároló kategória típuskonverziós függvényei</span><span class="sxs-lookup"><span data-stu-id="715a5-118">Type conversion functions in the container category</span></span>

<span data-ttu-id="715a5-119">A következő táblázat a [tároló](er-functions-category-container.md) kategória típuskonverziós függvényeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="715a5-119">The following table describes the type conversion functions in the [container](er-functions-category-container.md) category.</span></span>

| <span data-ttu-id="715a5-120">Függvény</span><span class="sxs-lookup"><span data-stu-id="715a5-120">Function</span></span> | <span data-ttu-id="715a5-121">Leírás</span><span class="sxs-lookup"><span data-stu-id="715a5-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="715a5-122">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="715a5-122">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="715a5-123">Ez a függvény a megadott *Karakterlánc* típusú bemenetet *Tároló* típusú adatelemmé konvertálja.</span><span class="sxs-lookup"><span data-stu-id="715a5-123">This function converts the specified input of the *String* type to a data item of the *Container* type.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="715a5-124">Típuskonverziós függvények a dátum és időpont kategóriában</span><span class="sxs-lookup"><span data-stu-id="715a5-124">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="715a5-125">A következő táblázat a [dátum és időpont kategória](er-functions-category-datetime.md) típuskonverziós függvényeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="715a5-125">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="715a5-126">Funkció</span><span class="sxs-lookup"><span data-stu-id="715a5-126">Function</span></span> | <span data-ttu-id="715a5-127">Leírás</span><span class="sxs-lookup"><span data-stu-id="715a5-127">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="715a5-128">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="715a5-128">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="715a5-129">Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú *Karakterlánc* értékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum/idő értékre.</span><span class="sxs-lookup"><span data-stu-id="715a5-129">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="715a5-130">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="715a5-130">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="715a5-131">Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott *Dátum* értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban.</span><span class="sxs-lookup"><span data-stu-id="715a5-131">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="715a5-132">DateValue</span><span class="sxs-lookup"><span data-stu-id="715a5-132">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="715a5-133">Ez a függvény egy *Dátum* értéket ad eredményül, amely egy megadott formátumú *Karakterlánc* értékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum értékre.</span><span class="sxs-lookup"><span data-stu-id="715a5-133">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="715a5-134">A lista kategória típuskonverziós függvényei</span><span class="sxs-lookup"><span data-stu-id="715a5-134">Type conversion functions in the list category</span></span>

<span data-ttu-id="715a5-135">A következő táblázat a [lista kategória](er-functions-category-list.md) típuskonverziós függvényeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="715a5-135">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="715a5-136">Funkció</span><span class="sxs-lookup"><span data-stu-id="715a5-136">Function</span></span> | <span data-ttu-id="715a5-137">Leírás</span><span class="sxs-lookup"><span data-stu-id="715a5-137">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="715a5-138">Lista</span><span class="sxs-lookup"><span data-stu-id="715a5-138">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="715a5-139">Ez a függvény egy *Rekordlista* értéket ad vissza a *Tároló (rekord)* típus megadott argumentumaiból létrehozott új listaként.</span><span class="sxs-lookup"><span data-stu-id="715a5-139">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="715a5-140">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="715a5-140">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="715a5-141">Ez a függvény egy *Rekordlista* értéket ad vissza, amely a *Felsorolás* vagy a *Tároló (rekord)* típus egy adott argumentumának szerkezete alapján jön létre.</span><span class="sxs-lookup"><span data-stu-id="715a5-141">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="715a5-142">Megosztás</span><span class="sxs-lookup"><span data-stu-id="715a5-142">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="715a5-143">Ez a függvény az adott *Karakterlánc* értéket alkarakterláncokká osztja szét, és az eredményt új *Rekordlista* értékként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="715a5-143">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="715a5-144">StringJoin</span><span class="sxs-lookup"><span data-stu-id="715a5-144">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="715a5-145">Ez a függvény egy *Karakterlánc* értéket ad vissza, amely a megadott *Rekordlista* érték megadott mezőjének összefűzött értékeiből áll.</span><span class="sxs-lookup"><span data-stu-id="715a5-145">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="715a5-146">Az értékeket a megadott elválasztó elválaszthatja egymástól.</span><span class="sxs-lookup"><span data-stu-id="715a5-146">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="715a5-147">A szöveg kategória típuskonverziós függvényei</span><span class="sxs-lookup"><span data-stu-id="715a5-147">Type conversion functions in the text category</span></span>

<span data-ttu-id="715a5-148">A következő táblázat a [szöveg kategória](er-functions-category-text.md) típuskonverziós függvényeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="715a5-148">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="715a5-149">Funkció</span><span class="sxs-lookup"><span data-stu-id="715a5-149">Function</span></span> | <span data-ttu-id="715a5-150">Leírás</span><span class="sxs-lookup"><span data-stu-id="715a5-150">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="715a5-151">Char</span><span class="sxs-lookup"><span data-stu-id="715a5-151">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="715a5-152">Ez a függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="715a5-152">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="715a5-153">GuidValue</span><span class="sxs-lookup"><span data-stu-id="715a5-153">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="715a5-154">Ez a függvény a megadott *Karakterlánc* típusú bemenetet *GUID* típusú adatelemmé konvertálja.</span><span class="sxs-lookup"><span data-stu-id="715a5-154">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="715a5-155">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="715a5-155">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="715a5-156">Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban.</span><span class="sxs-lookup"><span data-stu-id="715a5-156">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="715a5-157">QrCode</span><span class="sxs-lookup"><span data-stu-id="715a5-157">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="715a5-158">Ez a függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód).</span><span class="sxs-lookup"><span data-stu-id="715a5-158">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="715a5-159">Szöveg</span><span class="sxs-lookup"><span data-stu-id="715a5-159">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="715a5-160">A függvény egy *Karakterlánc* értéket ad vissza, amely a megadott számot jelzi, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja.</span><span class="sxs-lookup"><span data-stu-id="715a5-160">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="715a5-161">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="715a5-161">Additional resources</span></span>

[<span data-ttu-id="715a5-162">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="715a5-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="715a5-163">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="715a5-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="715a5-164">Elektronikus jelentéskészítés képletének nyelve</span><span class="sxs-lookup"><span data-stu-id="715a5-164">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
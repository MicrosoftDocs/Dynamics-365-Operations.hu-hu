---
title: A dátum és időpont kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott dátum és időpont függvényekről.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2745298ae1f6787c3de5a4aaf6a2a6350f5f3e85
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686219"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="50efc-103">A dátum és időpont kategóriába tartozó ER-függvények listája</span><span class="sxs-lookup"><span data-stu-id="50efc-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50efc-104">Az Elektronikus jelentéskészítés (ER) dátum és időpont függvényeinek segítségével adatokat nyerhet ki a dátum-és időértékekből, és műveleteket hajthat végre rajtuk.</span><span class="sxs-lookup"><span data-stu-id="50efc-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="50efc-105">Ez a témakör ezeknek a függvényeknek az összefoglalása.</span><span class="sxs-lookup"><span data-stu-id="50efc-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="50efc-106">Támogatott függvények listája</span><span class="sxs-lookup"><span data-stu-id="50efc-106">List of supported functions</span></span>

| <span data-ttu-id="50efc-107">Funkció</span><span class="sxs-lookup"><span data-stu-id="50efc-107">Function</span></span> | <span data-ttu-id="50efc-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="50efc-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="50efc-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="50efc-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="50efc-110">Ez a függvény egy *DateTime* értéket ad eredményül, amely a megadott számú nappal a megadott kezdési dátum előtt vagy után van.</span><span class="sxs-lookup"><span data-stu-id="50efc-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="50efc-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="50efc-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="50efc-112">Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátumértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban.</span><span class="sxs-lookup"><span data-stu-id="50efc-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="50efc-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="50efc-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="50efc-114">Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátum-/időértéket mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban.</span><span class="sxs-lookup"><span data-stu-id="50efc-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="50efc-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="50efc-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="50efc-116">Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátum/idő értékre.</span><span class="sxs-lookup"><span data-stu-id="50efc-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="50efc-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="50efc-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="50efc-118">Ez a függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban.</span><span class="sxs-lookup"><span data-stu-id="50efc-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="50efc-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="50efc-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="50efc-120">Ez a függvény egy *Dátum* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható területi beállításokban egy dátumértékre.</span><span class="sxs-lookup"><span data-stu-id="50efc-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="50efc-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="50efc-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="50efc-122">Ez a függvény egy *Egész* értéket ad vissza, amely a január 1. és a megadott dátum közötti napok számát mutatja.</span><span class="sxs-lookup"><span data-stu-id="50efc-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="50efc-123">nap</span><span class="sxs-lookup"><span data-stu-id="50efc-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="50efc-124">Ez a függvény egy *Egész* értéket ad vissza, amely egy megadott dátum és egy másik megadott dátum közötti napok számát mutatja.</span><span class="sxs-lookup"><span data-stu-id="50efc-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="50efc-125">Now</span><span class="sxs-lookup"><span data-stu-id="50efc-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="50efc-126">Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát és idejét mutatja.</span><span class="sxs-lookup"><span data-stu-id="50efc-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="50efc-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="50efc-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="50efc-128">Ez a függvény egy *Dátum* értéket ad vissza, amely a **nulla** dátumot (1900. január 1.) jelöli.</span><span class="sxs-lookup"><span data-stu-id="50efc-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="50efc-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="50efc-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="50efc-130">Ez a függvény egy *DateTime* értéket ad eredményül, amely a **nulla** dátum/idő értékét (1900. január 1.) mutatja Egyezményes világidő formátumban.</span><span class="sxs-lookup"><span data-stu-id="50efc-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="50efc-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="50efc-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="50efc-132">Ez a függvény egy *DateTime* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát és idejét mutatja.</span><span class="sxs-lookup"><span data-stu-id="50efc-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="50efc-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="50efc-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="50efc-134">Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát mutatja.</span><span class="sxs-lookup"><span data-stu-id="50efc-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="50efc-135">Ma</span><span class="sxs-lookup"><span data-stu-id="50efc-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="50efc-136">Ez a függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja.</span><span class="sxs-lookup"><span data-stu-id="50efc-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="50efc-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="50efc-137">Additional resources</span></span>

[<span data-ttu-id="50efc-138">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="50efc-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="50efc-139">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="50efc-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="50efc-140">Elektronikus jelentéskészítés képletének nyelve</span><span class="sxs-lookup"><span data-stu-id="50efc-140">Electronic reporting formula language</span></span>](er-formula-language.md)

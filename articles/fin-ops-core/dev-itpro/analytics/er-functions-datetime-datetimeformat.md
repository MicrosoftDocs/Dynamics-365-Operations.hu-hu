---
title: DATETIMEFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a DATETIMEFORMAT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 01/04/2021
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
ms.openlocfilehash: b7516620763e87440c0fb866ce507c744223a229
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563630"
---
# <a name="datetimeformat-er-function"></a><span data-ttu-id="34ad6-103">DATETIMEFORMAT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="34ad6-103">DATETIMEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34ad6-104">A `DATETIMEFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátum-/időértéket mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállításokban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="34ad6-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="34ad6-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="34ad6-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="34ad6-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="34ad6-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="34ad6-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="34ad6-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="34ad6-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="34ad6-108">Arguments</span></span>

<span data-ttu-id="34ad6-109">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="34ad6-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="34ad6-110">A formázására szolgáló dátumot és időpontot jelölő dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="34ad6-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="34ad6-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="34ad6-111">`format`: *String*</span></span>

<span data-ttu-id="34ad6-112">A kimenő karakterlánc formátuma.</span><span class="sxs-lookup"><span data-stu-id="34ad6-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="34ad6-113">A formátum-karakterlánc a kis- és nagybetűket megkülönbözteti, ha szabványos vagy egyedi formátumot használ.</span><span class="sxs-lookup"><span data-stu-id="34ad6-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="34ad6-114">Például a [szabványos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) „d” formátum a rövid dátumminta alapján adja eredményül a dátumot, míg a szabványos „D” formátum a hosszú dátumminta használatával adja vissza a dátumot.</span><span class="sxs-lookup"><span data-stu-id="34ad6-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="34ad6-115">Ezenkívül az [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) „M” formátum a hónapot adja vissza 1 és 12 között, míg az egyéni „m” formátum a percet adja vissza 0 és 59 között.</span><span class="sxs-lookup"><span data-stu-id="34ad6-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="34ad6-116">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="34ad6-116">`culture`: *String*</span></span>

<span data-ttu-id="34ad6-117">A formázáshoz használandó területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="34ad6-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="34ad6-118">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="34ad6-118">Return values</span></span>

<span data-ttu-id="34ad6-119">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="34ad6-119">*String*</span></span>

<span data-ttu-id="34ad6-120">Az eredményül kapott karakterláncérték.</span><span class="sxs-lookup"><span data-stu-id="34ad6-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="34ad6-121">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="34ad6-121">Usage notes</span></span>

<span data-ttu-id="34ad6-122">Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="34ad6-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="34ad6-123">Ha például a `DATETIMEFORMAT` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német területi beállítás használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német területi beállítás használatával történik.</span><span class="sxs-lookup"><span data-stu-id="34ad6-123">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="34ad6-124">Az alapértelmezett `culture` érték **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="34ad6-124">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="34ad6-125">Amikor a `DATETIMEFORMAT` függvény egy adott dátum-/időértéket konvertál, annak az alkalmazásfelhasználónak az időzóna-beállítását veszi figyelembe, aki azt az ER-formátumot futtatja, amelynek a kontextusában a függvényt hívták.</span><span class="sxs-lookup"><span data-stu-id="34ad6-125">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="34ad6-126">1. példa</span><span class="sxs-lookup"><span data-stu-id="34ad6-126">Example 1</span></span>

<span data-ttu-id="34ad6-127">A `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátum-/időértékét, a 2015. december 24-et adja vissza **"24-12-2015"** formában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="34ad6-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="34ad6-128">2. példa</span><span class="sxs-lookup"><span data-stu-id="34ad6-128">Example 2</span></span>

<span data-ttu-id="34ad6-129">A `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` az aktuális alkalmazás-munkamenet dátum-/időértékét adja vissza (2015. december 24.) a **"24.12.2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.</span><span class="sxs-lookup"><span data-stu-id="34ad6-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="34ad6-130">3. példa</span><span class="sxs-lookup"><span data-stu-id="34ad6-130">Example 3</span></span>

<span data-ttu-id="34ad6-131">A `DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` a **2019-11-12T08:00:00.0000000-08:00** karakterláncértéket adja eredményül, amikor egy olyan folyamat során hívják meg a függvényt, amelyet egy olyan alkalmazás kezdeményezett, amelynek a **Nyelvre és országra/régióra vonatkozó beállítások** szakaszában a **(GMT-08:00) Csendes-óceáni idő (Egyesült Államok és Kanada)** érték van megadva.</span><span class="sxs-lookup"><span data-stu-id="34ad6-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when the function is called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="34ad6-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="34ad6-132">Additional resources</span></span>

[<span data-ttu-id="34ad6-133">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="34ad6-133">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: DATETIMEFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a DATETIMEFORMAT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 98919f40751a77465ae26acbd46af4396c588b13
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916407"
---
# <span data-ttu-id="c98c1-103"><a name="DATETIMEFORMAT">DATETIMEFORMAT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="c98c1-103"><a name="DATETIMEFORMAT">DATETIMEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c98c1-104">A `DATETIMEFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátum-/időértéket mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállításokban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="c98c1-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="c98c1-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="c98c1-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="c98c1-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="c98c1-106">Syntax 1</span></span>

```
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="c98c1-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="c98c1-107">Syntax 2</span></span>

```
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="c98c1-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c98c1-108">Arguments</span></span>

<span data-ttu-id="c98c1-109">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="c98c1-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="c98c1-110">A formázására szolgáló dátumot és időpontot jelölő dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="c98c1-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="c98c1-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c98c1-111">`format`: *String*</span></span>

<span data-ttu-id="c98c1-112">A kimenő karakterlánc formátuma.</span><span class="sxs-lookup"><span data-stu-id="c98c1-112">The format of the output string.</span></span>

<span data-ttu-id="c98c1-113">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c98c1-113">`culture`: *String*</span></span>

<span data-ttu-id="c98c1-114">A formázáshoz használandó területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="c98c1-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="c98c1-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c98c1-115">Return values</span></span>

<span data-ttu-id="c98c1-116">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c98c1-116">*String*</span></span>

<span data-ttu-id="c98c1-117">Az eredményül kapott karakterláncérték.</span><span class="sxs-lookup"><span data-stu-id="c98c1-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c98c1-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c98c1-118">Usage notes</span></span>

<span data-ttu-id="c98c1-119">Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="c98c1-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="c98c1-120">Ha például a `DATETIMEFORMAT` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német területi beállítás használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német területi beállítás használatával történik.</span><span class="sxs-lookup"><span data-stu-id="c98c1-120">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="c98c1-121">Az alapértelmezett `culture` érték **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="c98c1-121">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="c98c1-122">Amikor a `DATETIMEFORMAT` függvény egy adott dátum-/időértéket konvertál, annak az alkalmazásfelhasználónak az időzóna-beállítását veszi figyelembe, aki azt az ER-formátumot futtatja, amelynek a kontextusában a függvényt hívták.</span><span class="sxs-lookup"><span data-stu-id="c98c1-122">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="c98c1-123">1. példa</span><span class="sxs-lookup"><span data-stu-id="c98c1-123">Example 1</span></span>

<span data-ttu-id="c98c1-124">A `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátum-/időértékét, a 2015. december 24-et adja vissza **"24-12-2015"** formában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="c98c1-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="c98c1-125">2. példa</span><span class="sxs-lookup"><span data-stu-id="c98c1-125">Example 2</span></span>

<span data-ttu-id="c98c1-126">A `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` az aktuális alkalmazás-munkamenet dátum-/időértékét adja vissza (2015. december 24.) a **"24.12.2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.</span><span class="sxs-lookup"><span data-stu-id="c98c1-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="c98c1-127">3. példa</span><span class="sxs-lookup"><span data-stu-id="c98c1-127">Example 3</span></span>

<span data-ttu-id="c98c1-128">A `DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` a **2019-11-12T08:00:00.0000000-08:00** karakterláncértéket adja eredményül, amikor egy olyan folyamat során hívják meg, amelyet egy olyan alkalmazás kezdeményezett, amelynek a **Nyelvre és országra/régióra vonatkozó beállítások** szakaszában a **(GMT-08:00) Csendes-óceáni idő (Egyesült Államok és Kanada)** érték van megadva.</span><span class="sxs-lookup"><span data-stu-id="c98c1-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c98c1-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c98c1-129">Additional resources</span></span>

[<span data-ttu-id="c98c1-130">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="c98c1-130">Date and time functions</span></span>](er-functions-category-datetime.md)

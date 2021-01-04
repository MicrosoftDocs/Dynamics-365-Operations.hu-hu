---
title: DATEFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a DATEFORMAT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fa6bdef2168112aeb17e0edb9f9a6d1b3bd45c0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684932"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="40d84-103">DATEFORMAT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="40d84-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40d84-104">A `DATEFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátumértéket mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállításban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="40d84-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="40d84-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="40d84-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="40d84-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="40d84-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="40d84-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="40d84-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="40d84-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="40d84-108">Arguments</span></span>

<span data-ttu-id="40d84-109">`date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="40d84-109">`date`: *Date*</span></span>

<span data-ttu-id="40d84-110">A formázni kívánt dátumot reprezentáló dátumérték.</span><span class="sxs-lookup"><span data-stu-id="40d84-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="40d84-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="40d84-111">`format`: *String*</span></span>

<span data-ttu-id="40d84-112">A kimenő karakterlánc formátuma.</span><span class="sxs-lookup"><span data-stu-id="40d84-112">The format of the output string.</span></span>

<span data-ttu-id="40d84-113">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="40d84-113">`culture`: *String*</span></span>

<span data-ttu-id="40d84-114">A formázáshoz használandó területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="40d84-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="40d84-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="40d84-115">Return values</span></span>

<span data-ttu-id="40d84-116">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="40d84-116">*String*</span></span>

<span data-ttu-id="40d84-117">Az eredményül kapott karakterláncérték.</span><span class="sxs-lookup"><span data-stu-id="40d84-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="40d84-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="40d84-118">Usage notes</span></span>

<span data-ttu-id="40d84-119">Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="40d84-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="40d84-120">Ha például a `DATEFORMAT` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német kultúra használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német kultúra használatával történik.</span><span class="sxs-lookup"><span data-stu-id="40d84-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="40d84-121">Az alapértelmezett `culture` érték **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="40d84-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="40d84-122">1. példa</span><span class="sxs-lookup"><span data-stu-id="40d84-122">Example 1</span></span>

<span data-ttu-id="40d84-123">A `DATEFORMAT (TODAY (), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) adja vissza a **"24-12-2015"** karakterlánc formájában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="40d84-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="40d84-124">2. példa</span><span class="sxs-lookup"><span data-stu-id="40d84-124">Example 2</span></span>

<span data-ttu-id="40d84-125">A `DATEFORMAT (SESSIONTODAY (), "d", "DE")` az aktuális alkalmazás-munkamenet dátumát adja vissza (2015. december 24.) a **"24-12-2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.</span><span class="sxs-lookup"><span data-stu-id="40d84-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40d84-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="40d84-126">Additional resources</span></span>

[<span data-ttu-id="40d84-127">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="40d84-127">Date and time functions</span></span>](er-functions-category-datetime.md)

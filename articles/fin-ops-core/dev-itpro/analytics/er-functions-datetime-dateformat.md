---
title: DATEFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a DATEFORMAT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 5a38f0016f69792e5beffa5d8224c70d6e5261c4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747035"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="035e9-103">DATEFORMAT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="035e9-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="035e9-104">A `DATEFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely az adott dátumértéket mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállításban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="035e9-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="035e9-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="035e9-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="035e9-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="035e9-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="035e9-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="035e9-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="035e9-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="035e9-108">Arguments</span></span>

<span data-ttu-id="035e9-109">`date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="035e9-109">`date`: *Date*</span></span>

<span data-ttu-id="035e9-110">A formázni kívánt dátumot reprezentáló dátumérték.</span><span class="sxs-lookup"><span data-stu-id="035e9-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="035e9-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="035e9-111">`format`: *String*</span></span>

<span data-ttu-id="035e9-112">A kimenő karakterlánc formátuma.</span><span class="sxs-lookup"><span data-stu-id="035e9-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="035e9-113">A formátum-karakterlánc a kis- és nagybetűket megkülönbözteti, ha szabványos vagy egyedi formátumot használ.</span><span class="sxs-lookup"><span data-stu-id="035e9-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="035e9-114">Például a [szabványos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) „d” formátum a rövid dátumminta alapján adja eredményül a dátumot, míg a szabványos „D” formátum a hosszú dátumminta használatával adja vissza a dátumot.</span><span class="sxs-lookup"><span data-stu-id="035e9-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="035e9-115">Ezenkívül az [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) „M” formátum a hónapot adja vissza 1 és 12 között, míg az egyéni „m” formátum a percet adja vissza 0 és 59 között.</span><span class="sxs-lookup"><span data-stu-id="035e9-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="035e9-116">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="035e9-116">`culture`: *String*</span></span>

<span data-ttu-id="035e9-117">A formázáshoz használandó területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="035e9-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="035e9-118">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="035e9-118">Return values</span></span>

<span data-ttu-id="035e9-119">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="035e9-119">*String*</span></span>

<span data-ttu-id="035e9-120">Az eredményül kapott karakterláncérték.</span><span class="sxs-lookup"><span data-stu-id="035e9-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="035e9-121">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="035e9-121">Usage notes</span></span>

<span data-ttu-id="035e9-122">Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="035e9-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="035e9-123">Ha például a `DATEFORMAT` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német kultúra használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német kultúra használatával történik.</span><span class="sxs-lookup"><span data-stu-id="035e9-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="035e9-124">Az alapértelmezett `culture` érték **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="035e9-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="035e9-125">1. példa</span><span class="sxs-lookup"><span data-stu-id="035e9-125">Example 1</span></span>

<span data-ttu-id="035e9-126">A `DATEFORMAT (TODAY (), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) adja vissza a **"24-12-2015"** karakterlánc formájában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="035e9-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="035e9-127">2. példa</span><span class="sxs-lookup"><span data-stu-id="035e9-127">Example 2</span></span>

<span data-ttu-id="035e9-128">A `DATEFORMAT (SESSIONTODAY (), "d", "DE")` az aktuális alkalmazás-munkamenet dátumát adja vissza (2015. december 24.) a **"24-12-2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.</span><span class="sxs-lookup"><span data-stu-id="035e9-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="035e9-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="035e9-129">Additional resources</span></span>

[<span data-ttu-id="035e9-130">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="035e9-130">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
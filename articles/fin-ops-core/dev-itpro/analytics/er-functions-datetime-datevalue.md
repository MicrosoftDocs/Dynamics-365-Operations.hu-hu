---
title: DATEVALUE ER-függvény
description: A témakör tájékoztatást nyújt a DATEVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: cfaf183c61d3663442cbc244239b872b9e1957bb
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891233"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="7c57a-103">DATEVALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="7c57a-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c57a-104">A `DATEVALUE` függvény egy *Dátum* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható [területi beállításokban](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) egy dátumértékre.</span><span class="sxs-lookup"><span data-stu-id="7c57a-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="7c57a-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](/dotnet/standard/base-types/standard-date-and-time-format-strings) és [egyéni](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="7c57a-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="7c57a-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="7c57a-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="7c57a-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="7c57a-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="7c57a-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="7c57a-108">Arguments</span></span>

<span data-ttu-id="7c57a-109">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="7c57a-109">`text`: *String*</span></span>

<span data-ttu-id="7c57a-110">A formázni kívánt értéket reprezentáló szöveg.</span><span class="sxs-lookup"><span data-stu-id="7c57a-110">Text that represents the value to format.</span></span>

<span data-ttu-id="7c57a-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="7c57a-111">`format`: *String*</span></span>

<span data-ttu-id="7c57a-112">Az adott szöveg formátuma.</span><span class="sxs-lookup"><span data-stu-id="7c57a-112">The format of the given text.</span></span>

<span data-ttu-id="7c57a-113">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="7c57a-113">`culture`: *String*</span></span>

<span data-ttu-id="7c57a-114">A megadott szöveg formázásához használt területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="7c57a-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="7c57a-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="7c57a-115">Return values</span></span>

<span data-ttu-id="7c57a-116">*Dátum*</span><span class="sxs-lookup"><span data-stu-id="7c57a-116">*Date*</span></span>

<span data-ttu-id="7c57a-117">Az eredményül kapott dátumérték.</span><span class="sxs-lookup"><span data-stu-id="7c57a-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7c57a-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7c57a-118">Usage notes</span></span>

<span data-ttu-id="7c57a-119">Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="7c57a-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="7c57a-120">Ha például a `DATEVALUE` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német területi beállítás használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német területi beállítás használatával történik.</span><span class="sxs-lookup"><span data-stu-id="7c57a-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="7c57a-121">Az alapértelmezett `culture` érték **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="7c57a-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="7c57a-122">1. példa</span><span class="sxs-lookup"><span data-stu-id="7c57a-122">Example 1</span></span>

<span data-ttu-id="7c57a-123">A `DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` a **2016. december 21.** dátumértéket adja vissza a megadott egyéni formátum szerint, az alapértelmezett alkalmazás **EN-US** területi beállításai szerint.</span><span class="sxs-lookup"><span data-stu-id="7c57a-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="7c57a-124">2. példa</span><span class="sxs-lookup"><span data-stu-id="7c57a-124">Example 2</span></span>

<span data-ttu-id="7c57a-125">A `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` a **2016. január 21.** dátumértéket adja vissza a megadott egyéni formátum és területi beállítások alapján.</span><span class="sxs-lookup"><span data-stu-id="7c57a-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="7c57a-126">A `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` viszont kivételt dob, hogy tájékoztassa a felhasználót arról, hogy a megadott karakterlánc nem ismerhető fel a megadott területi beállítások érvényes dátumaként.</span><span class="sxs-lookup"><span data-stu-id="7c57a-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c57a-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7c57a-127">Additional resources</span></span>

[<span data-ttu-id="7c57a-128">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="7c57a-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
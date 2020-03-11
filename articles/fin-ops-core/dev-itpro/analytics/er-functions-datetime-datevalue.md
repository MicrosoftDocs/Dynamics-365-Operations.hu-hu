---
title: DATEVALUE ER-függvény
description: A témakör tájékoztatást nyújt a DATEVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ef617ebfcaeb75e0284ea3cb4e889a204120b3d3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042366"
---
# <span data-ttu-id="4d088-103"><a name="DATEVALUE">DATEVALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="4d088-103"><a name="DATEVALUE">DATEVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d088-104">A `DATEVALUE` függvény egy *Dátum* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható [területi beállításokban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) egy dátumértékre.</span><span class="sxs-lookup"><span data-stu-id="4d088-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="4d088-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="4d088-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="4d088-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="4d088-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="4d088-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="4d088-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="4d088-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="4d088-108">Arguments</span></span>

<span data-ttu-id="4d088-109">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="4d088-109">`text`: *String*</span></span>

<span data-ttu-id="4d088-110">A formázni kívánt értéket reprezentáló szöveg.</span><span class="sxs-lookup"><span data-stu-id="4d088-110">Text that represents the value to format.</span></span>

<span data-ttu-id="4d088-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="4d088-111">`format`: *String*</span></span>

<span data-ttu-id="4d088-112">Az adott szöveg formátuma.</span><span class="sxs-lookup"><span data-stu-id="4d088-112">The format of the given text.</span></span>

<span data-ttu-id="4d088-113">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="4d088-113">`culture`: *String*</span></span>

<span data-ttu-id="4d088-114">A megadott szöveg formázásához használt területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="4d088-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="4d088-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="4d088-115">Return values</span></span>

<span data-ttu-id="4d088-116">*Dátum*</span><span class="sxs-lookup"><span data-stu-id="4d088-116">*Date*</span></span>

<span data-ttu-id="4d088-117">Az eredményül kapott dátumérték.</span><span class="sxs-lookup"><span data-stu-id="4d088-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4d088-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4d088-118">Usage notes</span></span>

<span data-ttu-id="4d088-119">Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="4d088-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="4d088-120">Ha például a `DATEVALUE` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német területi beállítás használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német területi beállítás használatával történik.</span><span class="sxs-lookup"><span data-stu-id="4d088-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="4d088-121">Az alapértelmezett `culture` érték **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="4d088-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="4d088-122">1. példa</span><span class="sxs-lookup"><span data-stu-id="4d088-122">Example 1</span></span>

<span data-ttu-id="4d088-123">A `DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` a **2016. december 21.** dátumértéket adja vissza a megadott egyéni formátum szerint, az alapértelmezett alkalmazás **EN-US** területi beállításai szerint.</span><span class="sxs-lookup"><span data-stu-id="4d088-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="4d088-124">2. példa</span><span class="sxs-lookup"><span data-stu-id="4d088-124">Example 2</span></span>

<span data-ttu-id="4d088-125">A `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` a **2016. január 21.** dátumértéket adja vissza a megadott egyéni formátum és területi beállítások alapján.</span><span class="sxs-lookup"><span data-stu-id="4d088-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="4d088-126">A `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` viszont kivételt dob, hogy tájékoztassa a felhasználót arról, hogy a megadott karakterlánc nem ismerhető fel a megadott területi beállítások érvényes dátumaként.</span><span class="sxs-lookup"><span data-stu-id="4d088-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4d088-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4d088-127">Additional resources</span></span>

[<span data-ttu-id="4d088-128">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="4d088-128">Date and time functions</span></span>](er-functions-category-datetime.md)

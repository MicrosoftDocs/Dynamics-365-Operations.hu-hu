---
title: DATETIMEVALUE ER-függvény
description: A témakör tájékoztatást nyújt a DATETIMEVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 30879796b483752a578e516d8afd75f5a690cabc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684907"
---
# <a name="datetimevalue-er-function"></a><span data-ttu-id="b3512-103">DATETIMEVALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="b3512-103">DATETIMEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b3512-104">A `DATETIMEVALUE` függvény egy *DateTime* értéket ad eredményül, amely egy megadott formátumú szövegértékről kerül átalakításra egy opcionálisan megadható [területi beállításban](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) egy dátum/idő értékre.</span><span class="sxs-lookup"><span data-stu-id="b3512-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="b3512-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="b3512-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b3512-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="b3512-106">Syntax 1</span></span>

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="b3512-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="b3512-107">Syntax 2</span></span>

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="b3512-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="b3512-108">Arguments</span></span>

<span data-ttu-id="b3512-109">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b3512-109">`text`: *String*</span></span>

<span data-ttu-id="b3512-110">A formázni kívánt értéket reprezentáló szöveg.</span><span class="sxs-lookup"><span data-stu-id="b3512-110">Text that represents the value to format.</span></span>

<span data-ttu-id="b3512-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b3512-111">`format`: *String*</span></span>

<span data-ttu-id="b3512-112">Az adott szöveg formátuma.</span><span class="sxs-lookup"><span data-stu-id="b3512-112">The format of the given text.</span></span>

<span data-ttu-id="b3512-113">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b3512-113">`culture`: *String*</span></span>

<span data-ttu-id="b3512-114">A megadott szöveg formázásához használt területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="b3512-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="b3512-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="b3512-115">Return values</span></span>

<span data-ttu-id="b3512-116">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="b3512-116">*DateTime*</span></span>

<span data-ttu-id="b3512-117">Az eredményül kapott dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="b3512-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b3512-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b3512-118">Usage notes</span></span>

<span data-ttu-id="b3512-119">Ha a területi beállítás nincs definiálva a hívott függvény argumentumaként, a `culture` értékét a hívási környezet határozza meg.</span><span class="sxs-lookup"><span data-stu-id="b3512-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="b3512-120">Ha például a `DATETIMEVALUE` függvényt az 1-es szintaxis segítségével hívja meg egy Elektronikus jelentéskészítési (ER) formátumban egy német kultúra használatára konfigurált **FÁJL** elemhez, akkor a konverzió a német kultúra használatával történik.</span><span class="sxs-lookup"><span data-stu-id="b3512-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="b3512-121">Az alapértelmezett `culture` érték **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="b3512-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="b3512-122">1. példa</span><span class="sxs-lookup"><span data-stu-id="b3512-122">Example 1</span></span>

<span data-ttu-id="b3512-123">A `DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` a **2:55:00 AM on December 21, 2016** dátumértéket adja vissza a megadott egyéni formátum szerint, az alapértelmezett alkalmazás **EN-US** területi beállításai szerint.</span><span class="sxs-lookup"><span data-stu-id="b3512-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="b3512-124">2. példa</span><span class="sxs-lookup"><span data-stu-id="b3512-124">Example 2</span></span>

<span data-ttu-id="b3512-125">A `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` a **2:55:00 am december 21, 2016** értéket adja vissza a megadott egyéni formátum és területi beállítás.</span><span class="sxs-lookup"><span data-stu-id="b3512-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="b3512-126">A `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` viszont kivételt dob, hogy tájékoztassa a felhasználót arról, hogy a megadott karakterlánc nem ismerhető fel a megadott területi beállítások érvényes dátum-/időértékeként.</span><span class="sxs-lookup"><span data-stu-id="b3512-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b3512-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b3512-127">Additional resources</span></span>

[<span data-ttu-id="b3512-128">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="b3512-128">Date and time functions</span></span>](er-functions-category-datetime.md)

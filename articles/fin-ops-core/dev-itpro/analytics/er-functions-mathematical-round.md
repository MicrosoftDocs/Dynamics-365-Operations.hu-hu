---
title: ROUND ER-függvény
description: A témakör tájékoztatást nyújt a ROUND Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 10/21/2020
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
ms.openlocfilehash: ce0f50cd5e544455626862e44b774dba39cf6e57
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744487"
---
# <a name="round-er-function"></a><span data-ttu-id="236c6-103">ROUND ER-függvény</span><span class="sxs-lookup"><span data-stu-id="236c6-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="236c6-104">A `ROUND` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre kerekítve.</span><span class="sxs-lookup"><span data-stu-id="236c6-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="236c6-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="236c6-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="236c6-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="236c6-106">Arguments</span></span>

<span data-ttu-id="236c6-107">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="236c6-107">`number`: *Real*</span></span>

<span data-ttu-id="236c6-108">Kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="236c6-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="236c6-109">`decimals`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="236c6-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="236c6-110">A tizedesjegyek számát jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="236c6-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="236c6-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="236c6-111">Return values</span></span>

<span data-ttu-id="236c6-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="236c6-112">*Real*</span></span>

<span data-ttu-id="236c6-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="236c6-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="236c6-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="236c6-114">Usage notes</span></span>

<span data-ttu-id="236c6-115">Ha a megadott `decimals` argumentum értéke nagyobb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek ezen megadott számára van kerekítve.</span><span class="sxs-lookup"><span data-stu-id="236c6-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="236c6-116">Ha a `decimals` argumentum értéke **0** (nulla), a megadott szám a legközelebbi páros egészre van kerekítve.</span><span class="sxs-lookup"><span data-stu-id="236c6-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="236c6-117">Ha a `decimals` argumentum értéke kisebb, mint 0 (nulla) akkor a megadott szám a tizedesvessző bal oldalára van kerekítve.</span><span class="sxs-lookup"><span data-stu-id="236c6-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="236c6-118">1. példa</span><span class="sxs-lookup"><span data-stu-id="236c6-118">Example 1</span></span>

<span data-ttu-id="236c6-119">A `ROUND (1200.767, 2)` két tizedesjegyre kerekít és a **1200.77** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="236c6-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="236c6-120">2. példa</span><span class="sxs-lookup"><span data-stu-id="236c6-120">Example 2</span></span>

<span data-ttu-id="236c6-121">A `ROUND (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít és az **1000** értéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="236c6-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="236c6-122">3. példa</span><span class="sxs-lookup"><span data-stu-id="236c6-122">Example 3</span></span>

<span data-ttu-id="236c6-123">`ROUND (1200.5, 0)` kerekít a legközelebbi páros egész számra, és **1200**-at ad vissza, míg a `ROUND (1201.5, 0)` ugyanezt teszi, és **1202**-t ad vissza.</span><span class="sxs-lookup"><span data-stu-id="236c6-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="236c6-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="236c6-124">Additional resources</span></span>

[<span data-ttu-id="236c6-125">Matematikai függvények</span><span class="sxs-lookup"><span data-stu-id="236c6-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
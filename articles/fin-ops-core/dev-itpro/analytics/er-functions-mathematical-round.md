---
title: ROUND ER-függvény
description: A témakör tájékoztatást nyújt a ROUND Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c9384d5975e4a25d18ff741f87431daa4b0bbd7e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917074"
---
# <span data-ttu-id="2f27e-103"><a name="ROUND">ROUND ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="2f27e-103"><a name="ROUND">ROUND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f27e-104">A `ROUND` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre kerekítve.</span><span class="sxs-lookup"><span data-stu-id="2f27e-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f27e-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="2f27e-105">Syntax</span></span>

```
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="2f27e-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2f27e-106">Arguments</span></span>

<span data-ttu-id="2f27e-107">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="2f27e-107">`number`: *Real*</span></span>

<span data-ttu-id="2f27e-108">Kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="2f27e-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="2f27e-109">`decimals`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="2f27e-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="2f27e-110">A tizedesjegyek számát jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="2f27e-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="2f27e-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2f27e-111">Return values</span></span>

<span data-ttu-id="2f27e-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="2f27e-112">*Real*</span></span>

<span data-ttu-id="2f27e-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="2f27e-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2f27e-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2f27e-114">Usage notes</span></span>

<span data-ttu-id="2f27e-115">Ha a megadott `decimals` argumentum értéke nagyobb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek ezen megadott számára van kerekítve.</span><span class="sxs-lookup"><span data-stu-id="2f27e-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="2f27e-116">Ha a `decimals` argumentum értéke **0** (nulla), a megadott szám a legközelebbi egészre van kerekítve.</span><span class="sxs-lookup"><span data-stu-id="2f27e-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="2f27e-117">Ha a `decimals` argumentum értéke kisebb, mint 0 (nulla) akkor a megadott szám a tizedesvessző bal oldalára van kerekítve.</span><span class="sxs-lookup"><span data-stu-id="2f27e-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="2f27e-118">1. példa</span><span class="sxs-lookup"><span data-stu-id="2f27e-118">Example 1</span></span>

<span data-ttu-id="2f27e-119">A `ROUND (1200.767, 2)` két tizedesjegyre kerekít és a **1200.77** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2f27e-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2f27e-120">2. példa</span><span class="sxs-lookup"><span data-stu-id="2f27e-120">Example 2</span></span>

<span data-ttu-id="2f27e-121">A `ROUND (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít és az **1000** értéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="2f27e-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2f27e-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2f27e-122">Additional resources</span></span>

[<span data-ttu-id="2f27e-123">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="2f27e-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)

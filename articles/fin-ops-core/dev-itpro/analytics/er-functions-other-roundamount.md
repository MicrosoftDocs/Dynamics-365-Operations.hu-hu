---
title: ROUNDAMOUNT ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDAMOUNT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15a84b086b324ec390d88e8b2617022ad4773977
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683063"
---
# <a name="roundamount-er-function"></a><span data-ttu-id="d144a-103">ROUNDAMOUNT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="d144a-103">ROUNDAMOUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d144a-104">A `ROUNDAMOUNT` függvény egy *Valós* értéket ad vissza a megadott szám egy másik szám legközelebbi többszörösére való kerekítésének eredményeként a megadott kerekítési szabályok szerint.</span><span class="sxs-lookup"><span data-stu-id="d144a-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="d144a-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="d144a-105">Syntax</span></span>

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="d144a-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="d144a-106">Arguments</span></span>

<span data-ttu-id="d144a-107">`number`: *Int* vagy *Valós*</span><span class="sxs-lookup"><span data-stu-id="d144a-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="d144a-108">Kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="d144a-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="d144a-109">`decimals`: *Int* vagy *Valós*</span><span class="sxs-lookup"><span data-stu-id="d144a-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="d144a-110">A szám, amelynek többszörösére a `number` paraméter értékét kerekíteni kell.</span><span class="sxs-lookup"><span data-stu-id="d144a-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="d144a-111">`round rule`: *Felsorolási érték*</span><span class="sxs-lookup"><span data-stu-id="d144a-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="d144a-112">A **RoundOffType** felsorolás felsorolási értéke, amely meghatározza a kerekítési szabályt.</span><span class="sxs-lookup"><span data-stu-id="d144a-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="d144a-113">Ez a felsorolás a következő értékeket nyújtja:</span><span class="sxs-lookup"><span data-stu-id="d144a-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="d144a-114">Normál (Ordinary)</span><span class="sxs-lookup"><span data-stu-id="d144a-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="d144a-115">Lefelé (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="d144a-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="d144a-116">Felfelé kerekítés (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="d144a-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="d144a-117">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="d144a-117">Return values</span></span>

<span data-ttu-id="d144a-118">*Valós*</span><span class="sxs-lookup"><span data-stu-id="d144a-118">*Real*</span></span>

<span data-ttu-id="d144a-119">Az eredményül kapott numerikus érték a `decimals` paraméterben megadott érték többszöröse, és a legközelebb áll a `number` paraméterben megadott értékhez.</span><span class="sxs-lookup"><span data-stu-id="d144a-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d144a-120">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d144a-120">Usage notes</span></span>

<span data-ttu-id="d144a-121">Ha a `number` paraméter nulla, ez a funkció mindig nullát ad eredményül.</span><span class="sxs-lookup"><span data-stu-id="d144a-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="d144a-122">Ha a `decimals` paraméter értéke nulla, ez a függvény az alapértelmezett kerekítési értékre kerekít.</span><span class="sxs-lookup"><span data-stu-id="d144a-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="d144a-123">Ha a `round rule` paraméter értéke **RoundOffType.Ordinary**, az alapértelmezett kerekítési érték **0,01**.</span><span class="sxs-lookup"><span data-stu-id="d144a-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="d144a-124">Ellenkező esetben az alapértelmezett kerekítés értéke **1,0**.</span><span class="sxs-lookup"><span data-stu-id="d144a-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="d144a-125">Ha a `round rule` paraméter értéke **RoundOffType.Ordinary**, ez a függvény a legközelebbi kerekítési összegre kerekít.</span><span class="sxs-lookup"><span data-stu-id="d144a-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="d144a-126">Ha a `round rule` paraméter értéke **RoundOffType.RoundDown**, ez a függvény nulla irányában a legközelebbi kerekítési összegre kerekít.</span><span class="sxs-lookup"><span data-stu-id="d144a-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="d144a-127">Ha a `round rule` paraméter értéke **RoundOffType.RoundUp**, ez a függvény nullával ellenkező irányában a legközelebbi kerekítési összegre kerekít.</span><span class="sxs-lookup"><span data-stu-id="d144a-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="d144a-128">Ha a `round rule` paraméter értéke **RoundOffType.Ordinary**, ez a függvény úgy viselkedik, mint az [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel-függvény és a [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++-függvény.</span><span class="sxs-lookup"><span data-stu-id="d144a-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="d144a-129">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d144a-129">Remarks</span></span>

<span data-ttu-id="d144a-130">Ha egy numerikus értéket adott számú tizedesjegyre szeretne kerekíteni, használja a [ROUND](er-functions-mathematical-round.md) függvényt.</span><span class="sxs-lookup"><span data-stu-id="d144a-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="d144a-131">Példa</span><span class="sxs-lookup"><span data-stu-id="d144a-131">Example</span></span>

<span data-ttu-id="d144a-132">Ha a **model.RoundOff** paraméter **RoundOffType.Ordinary** értékre van beállítva, a `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 7,35 értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="d144a-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="d144a-133">Ha a **model.RoundOff** paraméter **RoundOffType.RoundDown** értékre van beállítva, a `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 7,35 értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="d144a-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="d144a-134">Ha a **model.RoundOff** paraméter **RoundOffType.RoundUp** értékre van beállítva, a `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 8,4 értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="d144a-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d144a-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d144a-135">Additional resources</span></span>

[<span data-ttu-id="d144a-136">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="d144a-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="d144a-137">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="d144a-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)

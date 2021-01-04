---
title: ROUNDDOWN ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDDOWN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 9221476c1c12a7cc3fe2367cdee3ad44e5cbe381
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686882"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="56b7f-103">ROUNDDOWN ER-függvény</span><span class="sxs-lookup"><span data-stu-id="56b7f-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56b7f-104">A `ROUNDDOWN` funkció a megadott számot adja vissza *Valós* értékként, lefelé kerekítve adott számú tizedesjegyre.</span><span class="sxs-lookup"><span data-stu-id="56b7f-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="56b7f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="56b7f-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="56b7f-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="56b7f-106">Arguments</span></span>

<span data-ttu-id="56b7f-107">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="56b7f-107">`number`: *Real*</span></span>

<span data-ttu-id="56b7f-108">Lefelé kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="56b7f-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="56b7f-109">`decimals`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="56b7f-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="56b7f-110">A tizedesjegyek számát jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="56b7f-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="56b7f-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="56b7f-111">Return values</span></span>

<span data-ttu-id="56b7f-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="56b7f-112">*Real*</span></span>

<span data-ttu-id="56b7f-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="56b7f-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="56b7f-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="56b7f-114">Usage notes</span></span>

<span data-ttu-id="56b7f-115">Ez a függvény úgy viselkedik, mint a [ROUND](er-functions-mathematical-round.md), de mindig lefelé (nulla felé) kerekíti a megadott számot.</span><span class="sxs-lookup"><span data-stu-id="56b7f-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="56b7f-116">1. példa</span><span class="sxs-lookup"><span data-stu-id="56b7f-116">Example 1</span></span>

<span data-ttu-id="56b7f-117">A `ROUNDDOWN (1200.767, 2)` két tizedesjegyre kerekít lefelé, és a **1200.76** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="56b7f-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="56b7f-118">2. példa</span><span class="sxs-lookup"><span data-stu-id="56b7f-118">Example 2</span></span>

<span data-ttu-id="56b7f-119">A `ROUNDDOWN (1700.767, -3)` az 1000 legközelebbi többszörösére kerekít lefelé, és az **1000** értéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="56b7f-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56b7f-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="56b7f-120">Additional resources</span></span>

[<span data-ttu-id="56b7f-121">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="56b7f-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)

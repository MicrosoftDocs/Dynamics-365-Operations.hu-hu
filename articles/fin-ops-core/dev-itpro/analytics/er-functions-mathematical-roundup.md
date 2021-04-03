---
title: ROUNDUP ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDUP Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d23a984bd59c4d2d37c407e3fcfed9c7017dcc7f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569335"
---
# <a name="roundup-er-function"></a><span data-ttu-id="6fc49-103">ROUNDUP ER-függvény</span><span class="sxs-lookup"><span data-stu-id="6fc49-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6fc49-104">A `ROUNDUP` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre felfelé kerekítve.</span><span class="sxs-lookup"><span data-stu-id="6fc49-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="6fc49-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="6fc49-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="6fc49-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="6fc49-106">Arguments</span></span>

<span data-ttu-id="6fc49-107">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="6fc49-107">`number`: *Real*</span></span>

<span data-ttu-id="6fc49-108">Felfelé kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="6fc49-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="6fc49-109">`decimals`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="6fc49-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="6fc49-110">A tizedesjegyek számát jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="6fc49-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="6fc49-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="6fc49-111">Return values</span></span>

<span data-ttu-id="6fc49-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="6fc49-112">*Real*</span></span>

<span data-ttu-id="6fc49-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="6fc49-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6fc49-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6fc49-114">Usage notes</span></span>

<span data-ttu-id="6fc49-115">Ez a függvény úgy viselkedik, mint a [ROUND](er-functions-mathematical-round.md), de mindig felfelé (nullával ellenkező irányba) kerekíti a megadott számot.</span><span class="sxs-lookup"><span data-stu-id="6fc49-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="6fc49-116">1. példa</span><span class="sxs-lookup"><span data-stu-id="6fc49-116">Example 1</span></span>

<span data-ttu-id="6fc49-117">A `ROUNDUP (1200.763, 2)` két tizedesjegyre kerekít fel, és az **1200.77** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="6fc49-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="6fc49-118">2. példa</span><span class="sxs-lookup"><span data-stu-id="6fc49-118">Example 2</span></span>

<span data-ttu-id="6fc49-119">A `ROUNDUP (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít fel, és az **2000** értéket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="6fc49-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6fc49-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6fc49-120">Additional resources</span></span>

[<span data-ttu-id="6fc49-121">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="6fc49-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
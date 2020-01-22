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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef7d81852a0bbb84fd8f37cd89555766cc47f5f8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915855"
---
# <span data-ttu-id="8798c-103"><a name="ROUNDDOWN">ROUNDDOWN ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="8798c-103"><a name="ROUNDDOWN">ROUNDDOWN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8798c-104">A `ROUNDDOWN` funkció a megadott számot adja vissza *Valós* értékként, lefelé kerekítve adott számú tizedesjegyre.</span><span class="sxs-lookup"><span data-stu-id="8798c-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="8798c-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="8798c-105">Syntax</span></span>

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="8798c-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="8798c-106">Arguments</span></span>

<span data-ttu-id="8798c-107">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="8798c-107">`number`: *Real*</span></span>

<span data-ttu-id="8798c-108">Lefelé kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="8798c-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="8798c-109">`decimals`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="8798c-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="8798c-110">A tizedesjegyek számát jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="8798c-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="8798c-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="8798c-111">Return values</span></span>

<span data-ttu-id="8798c-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="8798c-112">*Real*</span></span>

<span data-ttu-id="8798c-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="8798c-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8798c-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8798c-114">Usage notes</span></span>

<span data-ttu-id="8798c-115">Ez a függvény úgy viselkedik, mint a [ROUND](er-functions-mathematical-round.md), de mindig lefelé (nulla felé) kerekíti a megadott számot.</span><span class="sxs-lookup"><span data-stu-id="8798c-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="8798c-116">1. példa</span><span class="sxs-lookup"><span data-stu-id="8798c-116">Example 1</span></span>

<span data-ttu-id="8798c-117">A `ROUNDDOWN (1200.767, 2)` két tizedesjegyre kerekít lefelé, és a **1200.76** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="8798c-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="8798c-118">2. példa</span><span class="sxs-lookup"><span data-stu-id="8798c-118">Example 2</span></span>

<span data-ttu-id="8798c-119">A `ROUNDDOWN (1700.767, -3)` az 1000 legközelebbi többszörösére kerekít lefelé, és az **1000** értéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="8798c-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8798c-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8798c-120">Additional resources</span></span>

[<span data-ttu-id="8798c-121">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="8798c-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)

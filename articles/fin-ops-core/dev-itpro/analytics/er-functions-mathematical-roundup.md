---
title: ROUNDUP ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDUP Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 83262a11f92a924e5e49461cf414fb07ab278541
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744503"
---
# <a name="roundup-er-function"></a><span data-ttu-id="ed82b-103">ROUNDUP ER-függvény</span><span class="sxs-lookup"><span data-stu-id="ed82b-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed82b-104">A `ROUNDUP` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre felfelé kerekítve.</span><span class="sxs-lookup"><span data-stu-id="ed82b-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed82b-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="ed82b-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="ed82b-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="ed82b-106">Arguments</span></span>

<span data-ttu-id="ed82b-107">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="ed82b-107">`number`: *Real*</span></span>

<span data-ttu-id="ed82b-108">Felfelé kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="ed82b-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="ed82b-109">`decimals`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="ed82b-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="ed82b-110">A tizedesjegyek számát jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="ed82b-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="ed82b-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="ed82b-111">Return values</span></span>

<span data-ttu-id="ed82b-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="ed82b-112">*Real*</span></span>

<span data-ttu-id="ed82b-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="ed82b-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ed82b-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ed82b-114">Usage notes</span></span>

<span data-ttu-id="ed82b-115">Ez a függvény úgy viselkedik, mint a [ROUND](er-functions-mathematical-round.md), de mindig felfelé (nullával ellenkező irányba) kerekíti a megadott számot.</span><span class="sxs-lookup"><span data-stu-id="ed82b-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="ed82b-116">1. példa</span><span class="sxs-lookup"><span data-stu-id="ed82b-116">Example 1</span></span>

<span data-ttu-id="ed82b-117">A `ROUNDUP (1200.763, 2)` két tizedesjegyre kerekít fel, és az **1200.77** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ed82b-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ed82b-118">2. példa</span><span class="sxs-lookup"><span data-stu-id="ed82b-118">Example 2</span></span>

<span data-ttu-id="ed82b-119">A `ROUNDUP (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít fel, és az **2000** értéket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="ed82b-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ed82b-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed82b-120">Additional resources</span></span>

[<span data-ttu-id="ed82b-121">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="ed82b-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)

---
title: ROUNDUP ER-függvény
description: A témakör tájékoztatást nyújt a ROUNDUP Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 4898f596108ff3c563da55a567a10da987d62d33
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744439"
---
# <a name="roundup-er-function"></a><span data-ttu-id="1a533-103">ROUNDUP ER-függvény</span><span class="sxs-lookup"><span data-stu-id="1a533-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a533-104">A `ROUNDUP` függvény a megadott számot adja vissza *Valós* értékként, adott számú tizedesjegyre felfelé kerekítve.</span><span class="sxs-lookup"><span data-stu-id="1a533-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a533-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="1a533-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="1a533-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="1a533-106">Arguments</span></span>

<span data-ttu-id="1a533-107">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="1a533-107">`number`: *Real*</span></span>

<span data-ttu-id="1a533-108">Felfelé kerekítendő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="1a533-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="1a533-109">`decimals`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="1a533-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="1a533-110">A tizedesjegyek számát jelölő numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="1a533-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="1a533-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="1a533-111">Return values</span></span>

<span data-ttu-id="1a533-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="1a533-112">*Real*</span></span>

<span data-ttu-id="1a533-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="1a533-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1a533-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1a533-114">Usage notes</span></span>

<span data-ttu-id="1a533-115">Ez a függvény úgy viselkedik, mint a [ROUND](er-functions-mathematical-round.md), de mindig felfelé (nullával ellenkező irányba) kerekíti a megadott számot.</span><span class="sxs-lookup"><span data-stu-id="1a533-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="1a533-116">1. példa</span><span class="sxs-lookup"><span data-stu-id="1a533-116">Example 1</span></span>

<span data-ttu-id="1a533-117">A `ROUNDUP (1200.763, 2)` két tizedesjegyre kerekít fel, és az **1200.77** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="1a533-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1a533-118">2. példa</span><span class="sxs-lookup"><span data-stu-id="1a533-118">Example 2</span></span>

<span data-ttu-id="1a533-119">A `ROUNDUP (1200.767, -3)` az 1000 legközelebbi többszörösére kerekít fel, és az **2000** értéket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="1a533-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a533-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1a533-120">Additional resources</span></span>

[<span data-ttu-id="1a533-121">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="1a533-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
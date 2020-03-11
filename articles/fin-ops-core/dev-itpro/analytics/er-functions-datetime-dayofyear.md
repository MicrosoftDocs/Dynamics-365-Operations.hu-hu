---
title: DAYOFYEAR ER-függvény
description: A témakör tájékoztatást nyújt a DAYOFYEAR Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: d24aabb582151b0b357b64a988cc932a9c9f3cea
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070667"
---
# <span data-ttu-id="13598-103"><a name="DAYOFYEAR">DAYOFYEAR ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="13598-103"><a name="DAYOFYEAR">DAYOFYEAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13598-104">A `DAYOFYEAR` függvény egy *Egész* értéket ad vissza, amely a január 1. és a megadott dátum közötti napok számát mutatja.</span><span class="sxs-lookup"><span data-stu-id="13598-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="13598-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="13598-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="13598-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="13598-106">Arguments</span></span>

<span data-ttu-id="13598-107">`date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="13598-107">`date`: *Date*</span></span>

<span data-ttu-id="13598-108">A napok számának kiszámításához használandó dátumot jelképező dátumérték.</span><span class="sxs-lookup"><span data-stu-id="13598-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="13598-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="13598-109">Return values</span></span>

<span data-ttu-id="13598-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="13598-110">*Integer*</span></span>

<span data-ttu-id="13598-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="13598-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="13598-112">1. példa</span><span class="sxs-lookup"><span data-stu-id="13598-112">Example 1</span></span>

<span data-ttu-id="13598-113">A `DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` a **61** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="13598-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="13598-114">2. példa</span><span class="sxs-lookup"><span data-stu-id="13598-114">Example 2</span></span>

<span data-ttu-id="13598-115">A `DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` az **1** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="13598-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13598-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="13598-116">Additional resources</span></span>

[<span data-ttu-id="13598-117">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="13598-117">Date and time functions</span></span>](er-functions-category-datetime.md)

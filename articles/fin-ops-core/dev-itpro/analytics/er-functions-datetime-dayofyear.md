---
title: DAYOFYEAR ER-függvény
description: A témakör tájékoztatást nyújt a DAYOFYEAR Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ba63c96355a6a7a1eccaddf39e47a3edb2d1e651
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563534"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="72b42-103">DAYOFYEAR ER-függvény</span><span class="sxs-lookup"><span data-stu-id="72b42-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72b42-104">A `DAYOFYEAR` függvény egy *Egész* értéket ad vissza, amely a január 1. és a megadott dátum közötti napok számát mutatja.</span><span class="sxs-lookup"><span data-stu-id="72b42-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="72b42-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="72b42-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="72b42-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="72b42-106">Arguments</span></span>

<span data-ttu-id="72b42-107">`date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="72b42-107">`date`: *Date*</span></span>

<span data-ttu-id="72b42-108">A napok számának kiszámításához használandó dátumot jelképező dátumérték.</span><span class="sxs-lookup"><span data-stu-id="72b42-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="72b42-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="72b42-109">Return values</span></span>

<span data-ttu-id="72b42-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="72b42-110">*Integer*</span></span>

<span data-ttu-id="72b42-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="72b42-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="72b42-112">1. példa</span><span class="sxs-lookup"><span data-stu-id="72b42-112">Example 1</span></span>

<span data-ttu-id="72b42-113">A `DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` a **61** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="72b42-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="72b42-114">2. példa</span><span class="sxs-lookup"><span data-stu-id="72b42-114">Example 2</span></span>

<span data-ttu-id="72b42-115">A `DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` az **1** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="72b42-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72b42-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="72b42-116">Additional resources</span></span>

[<span data-ttu-id="72b42-117">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="72b42-117">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
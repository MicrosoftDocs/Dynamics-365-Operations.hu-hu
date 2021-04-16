---
title: DAYOFYEAR ER-függvény
description: A témakör tájékoztatást nyújt a DAYOFYEAR Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 569e988db91ff992fb7db6e7fd6e8c6aa6a1a3e8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746915"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="67cea-103">DAYOFYEAR ER-függvény</span><span class="sxs-lookup"><span data-stu-id="67cea-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67cea-104">A `DAYOFYEAR` függvény egy *Egész* értéket ad vissza, amely a január 1. és a megadott dátum közötti napok számát mutatja.</span><span class="sxs-lookup"><span data-stu-id="67cea-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="67cea-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="67cea-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="67cea-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="67cea-106">Arguments</span></span>

<span data-ttu-id="67cea-107">`date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="67cea-107">`date`: *Date*</span></span>

<span data-ttu-id="67cea-108">A napok számának kiszámításához használandó dátumot jelképező dátumérték.</span><span class="sxs-lookup"><span data-stu-id="67cea-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="67cea-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="67cea-109">Return values</span></span>

<span data-ttu-id="67cea-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="67cea-110">*Integer*</span></span>

<span data-ttu-id="67cea-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="67cea-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="67cea-112">1. példa</span><span class="sxs-lookup"><span data-stu-id="67cea-112">Example 1</span></span>

<span data-ttu-id="67cea-113">A `DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` a **61** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="67cea-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="67cea-114">2. példa</span><span class="sxs-lookup"><span data-stu-id="67cea-114">Example 2</span></span>

<span data-ttu-id="67cea-115">A `DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` az **1** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="67cea-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67cea-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="67cea-116">Additional resources</span></span>

[<span data-ttu-id="67cea-117">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="67cea-117">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
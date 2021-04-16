---
title: NOW ER-függvény
description: A témakör tájékoztatást nyújt a NOW Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: c93aa2a0e3f6aa07ab9e843d3c5f11c5265e8c40
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746867"
---
# <a name="now-er-function"></a><span data-ttu-id="5ed4b-103">NOW ER-függvény</span><span class="sxs-lookup"><span data-stu-id="5ed4b-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ed4b-104">A `NOW` függvény egy *DateTime* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát és idejét mutatja.</span><span class="sxs-lookup"><span data-stu-id="5ed4b-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ed4b-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="5ed4b-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="5ed4b-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="5ed4b-106">Return values</span></span>

<span data-ttu-id="5ed4b-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="5ed4b-107">*DateTime*</span></span>

<span data-ttu-id="5ed4b-108">Az eredményül kapott dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="5ed4b-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="5ed4b-109">Példa</span><span class="sxs-lookup"><span data-stu-id="5ed4b-109">Example</span></span>

<span data-ttu-id="5ed4b-110">A `DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátum-/időértékét, a 2015. december 24-et adja vissza **"24-12-2015"** formában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="5ed4b-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ed4b-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5ed4b-111">Additional resources</span></span>

[<span data-ttu-id="5ed4b-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="5ed4b-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
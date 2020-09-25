---
title: TODAY ER-függvény
description: A témakör tájékoztatást nyújt a TODAY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: e2ee153c1dde99810a78ed15c7505fa705088797
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745441"
---
# <a name="today-er-function"></a><span data-ttu-id="c941b-103">TODAY ER-függvény</span><span class="sxs-lookup"><span data-stu-id="c941b-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c941b-104">A `TODAY` függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja.</span><span class="sxs-lookup"><span data-stu-id="c941b-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="c941b-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c941b-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="c941b-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c941b-106">Return values</span></span>

<span data-ttu-id="c941b-107">*Dátum*</span><span class="sxs-lookup"><span data-stu-id="c941b-107">*Date*</span></span>

<span data-ttu-id="c941b-108">Az eredményül kapott dátumérték.</span><span class="sxs-lookup"><span data-stu-id="c941b-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="c941b-109">Példa</span><span class="sxs-lookup"><span data-stu-id="c941b-109">Example</span></span>

<span data-ttu-id="c941b-110">A `DATEFORMAT (TODAY (), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) adja vissza a **"24-12-2015"** karakterlánc formájában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="c941b-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c941b-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c941b-111">Additional resources</span></span>

[<span data-ttu-id="c941b-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="c941b-112">Date and time functions</span></span>](er-functions-category-datetime.md)

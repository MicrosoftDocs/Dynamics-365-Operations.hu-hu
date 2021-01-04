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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a93a9171456fb69e16c8104b0afb9ad485311b1a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683795"
---
# <a name="today-er-function"></a><span data-ttu-id="785b7-103">TODAY ER-függvény</span><span class="sxs-lookup"><span data-stu-id="785b7-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="785b7-104">A `TODAY` függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja.</span><span class="sxs-lookup"><span data-stu-id="785b7-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="785b7-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="785b7-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="785b7-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="785b7-106">Return values</span></span>

<span data-ttu-id="785b7-107">*Dátum*</span><span class="sxs-lookup"><span data-stu-id="785b7-107">*Date*</span></span>

<span data-ttu-id="785b7-108">Az eredményül kapott dátumérték.</span><span class="sxs-lookup"><span data-stu-id="785b7-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="785b7-109">Példa</span><span class="sxs-lookup"><span data-stu-id="785b7-109">Example</span></span>

<span data-ttu-id="785b7-110">A `DATEFORMAT (TODAY (), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) adja vissza a **"24-12-2015"** karakterlánc formájában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="785b7-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="785b7-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="785b7-111">Additional resources</span></span>

[<span data-ttu-id="785b7-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="785b7-112">Date and time functions</span></span>](er-functions-category-datetime.md)

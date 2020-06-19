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
ms.openlocfilehash: 94ef15d1971287e8bf13944bc8f693b567950031
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411437"
---
# <a name=""></a><span data-ttu-id="f75d5-103"><a name="TODAY">TODAY ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="f75d5-103"><a name="TODAY">TODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f75d5-104">A `TODAY` függvény egy *Dátum* értéket ad eredményül, amely az alkalmazáskiszolgáló aktuális dátumát mutatja.</span><span class="sxs-lookup"><span data-stu-id="f75d5-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="f75d5-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="f75d5-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="f75d5-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="f75d5-106">Return values</span></span>

<span data-ttu-id="f75d5-107">*Dátum*</span><span class="sxs-lookup"><span data-stu-id="f75d5-107">*Date*</span></span>

<span data-ttu-id="f75d5-108">Az eredményül kapott dátumérték.</span><span class="sxs-lookup"><span data-stu-id="f75d5-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="f75d5-109">Példa</span><span class="sxs-lookup"><span data-stu-id="f75d5-109">Example</span></span>

<span data-ttu-id="f75d5-110">A `DATEFORMAT (TODAY (), "dd-MM-yyyy")` a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) adja vissza a **"24-12-2015"** karakterlánc formájában, a megadott egyéni formátum szerint.</span><span class="sxs-lookup"><span data-stu-id="f75d5-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f75d5-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f75d5-111">Additional resources</span></span>

[<span data-ttu-id="f75d5-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="f75d5-112">Date and time functions</span></span>](er-functions-category-datetime.md)

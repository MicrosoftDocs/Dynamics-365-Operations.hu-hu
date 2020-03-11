---
title: ADDDAYS ER-függvény
description: A témakör tájékoztatást nyújt az ADDDAYS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 08b9727fb34210fecff31826cc1f2b8da022156b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042458"
---
# <span data-ttu-id="953f3-103"><a name="ADDDAYS">ADDDAYS ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="953f3-103"><a name="ADDDAYS">ADDDAYS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="953f3-104">Az `ADDDAYS` függvény egy *DateTime* értéket számít ki, amely a megadott számú nappal a megadott kezdési dátum előtt vagy után van.</span><span class="sxs-lookup"><span data-stu-id="953f3-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="953f3-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="953f3-105">Syntax</span></span>

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="953f3-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="953f3-106">Arguments</span></span>

<span data-ttu-id="953f3-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="953f3-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="953f3-108">A kezdő dátumot reprezentáló dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="953f3-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="953f3-109">`days`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="953f3-109">`days`: *Integer*</span></span>

<span data-ttu-id="953f3-110">A `datetime` előtti vagy utáni napok száma.</span><span class="sxs-lookup"><span data-stu-id="953f3-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="953f3-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="953f3-111">Return values</span></span>

<span data-ttu-id="953f3-112">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="953f3-112">*DateTime*</span></span>

<span data-ttu-id="953f3-113">Az eredményül kapott dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="953f3-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="953f3-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="953f3-114">Usage notes</span></span>

<span data-ttu-id="953f3-115">A `days` pozitív értéke egy jövőbeli dátumot eredményez.</span><span class="sxs-lookup"><span data-stu-id="953f3-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="953f3-116">A negatív érték egy múltbeli dátumot eredményez.</span><span class="sxs-lookup"><span data-stu-id="953f3-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="953f3-117">1. példa</span><span class="sxs-lookup"><span data-stu-id="953f3-117">Example 1</span></span>

<span data-ttu-id="953f3-118">Az `ADDDAYS (NOW(), 7)` megjeleníti a hét nappal későbbi dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="953f3-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="953f3-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="953f3-119">Example 2</span></span>

<span data-ttu-id="953f3-120">Az `ADDDAYS (NOW(), -3)` megjeleníti a három nappal korábbi dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="953f3-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="953f3-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="953f3-121">Additional resources</span></span>

[<span data-ttu-id="953f3-122">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="953f3-122">Date and time functions</span></span>](er-functions-category-datetime.md)

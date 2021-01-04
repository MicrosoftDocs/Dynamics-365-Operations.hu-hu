---
title: DATETODATETIME ER-függvény
description: A témakör tájékoztatást nyújt a DATETODATETIME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5ad1d304f0914a9ddbca951cdb7419dbcc1f46
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682439"
---
# <a name="datetodatetime-er-function"></a><span data-ttu-id="2d977-103">DATETODATETIME ER-függvény</span><span class="sxs-lookup"><span data-stu-id="2d977-103">DATETODATETIME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d977-104">A `DATETODATETIME` függvény egy *DateTime* értéket ad eredményül, amely egy megadott dátum értékről egy dátum/idő értékre kerül átalakításra Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) formátumban.</span><span class="sxs-lookup"><span data-stu-id="2d977-104">The `DATETODATETIME` function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="2d977-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="2d977-105">Syntax</span></span>

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a><span data-ttu-id="2d977-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2d977-106">Arguments</span></span>

<span data-ttu-id="2d977-107">`date`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="2d977-107">`date`: *Date*</span></span>

<span data-ttu-id="2d977-108">Az átalakítani kívánt dátumot reprezentáló dátumérték.</span><span class="sxs-lookup"><span data-stu-id="2d977-108">A date value that represents the date to convert.</span></span>

## <a name="return-values"></a><span data-ttu-id="2d977-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2d977-109">Return values</span></span>

<span data-ttu-id="2d977-110">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="2d977-110">*DateTime*</span></span>

<span data-ttu-id="2d977-111">Az eredményül kapott dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="2d977-111">The resulting date/time value.</span></span>

## <a name="example-1"></a><span data-ttu-id="2d977-112">1. példa</span><span class="sxs-lookup"><span data-stu-id="2d977-112">Example 1</span></span>

<span data-ttu-id="2d977-113">A `DATETODATETIME (CompInfo. 'getCurrentDate()')` a jelenlegi Microsoft Dynamics 365 Finance munkamenet dátumát (2015. december 24.) adja vissza **12/24/2015 12:00:00 AM** értékként.</span><span class="sxs-lookup"><span data-stu-id="2d977-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` returns the date of the current Microsoft Dynamics 365 Finance session, December 24, 2015, as **12/24/2015 12:00:00 AM**.</span></span> <span data-ttu-id="2d977-114">Ebben a példában a **CompInfo** a **Finance and Operations/Tábla** típus Elektronikus jelentéskészítési (ER) adatforrása, és a CompanyInfo táblára hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="2d977-114">In this example, **CompInfo** is an Electronic reporting (ER) data source of the **Finance and Operations/Table** type, and it refers to the CompanyInfo table.</span></span>

## <a name="example-2"></a><span data-ttu-id="2d977-115">2. példa</span><span class="sxs-lookup"><span data-stu-id="2d977-115">Example 2</span></span>

<span data-ttu-id="2d977-116">A `DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` a **11/12/2019 12:00:00 AM** dátum-/időértéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2d977-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returns the date/time value **11/12/2019 12:00:00 AM**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d977-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2d977-117">Additional resources</span></span>

[<span data-ttu-id="2d977-118">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="2d977-118">Date and time functions</span></span>](er-functions-category-datetime.md)

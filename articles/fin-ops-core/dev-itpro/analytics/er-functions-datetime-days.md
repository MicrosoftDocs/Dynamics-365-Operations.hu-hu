---
title: DAYS ER-függvény
description: A témakör tájékoztatást nyújt a DAYS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 4f8c12a22f7654285d5598064473bf86689ed207
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916292"
---
# <span data-ttu-id="91855-103"><a name="DAYS">DAYS ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="91855-103"><a name="DAYS">DAYS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91855-104">A `DAYS` függvény egy *Egész* értéket ad vissza, amely egy megadott dátum és egy másik megadott dátum közötti napok számát mutatja.</span><span class="sxs-lookup"><span data-stu-id="91855-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="91855-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="91855-105">Syntax</span></span>

```
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="91855-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="91855-106">Arguments</span></span>

<span data-ttu-id="91855-107">`date 1`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="91855-107">`date 1`: *Date*</span></span>

<span data-ttu-id="91855-108">A napok számának kiszámításához a kezdési dátumot jelképező dátumérték.</span><span class="sxs-lookup"><span data-stu-id="91855-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="91855-109">`date 2`: *Dátum*</span><span class="sxs-lookup"><span data-stu-id="91855-109">`date 2`: *Date*</span></span>

<span data-ttu-id="91855-110">A napok számának kiszámításához a befejező dátumot jelképező dátumérték.</span><span class="sxs-lookup"><span data-stu-id="91855-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="91855-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="91855-111">Return values</span></span>

<span data-ttu-id="91855-112">*Egész*</span><span class="sxs-lookup"><span data-stu-id="91855-112">*Integer*</span></span>

<span data-ttu-id="91855-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="91855-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="91855-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="91855-114">Usage notes</span></span>

<span data-ttu-id="91855-115">A `DAYS` függvény pozitív értéket ad vissza, ha az első dátum későbbi, mint a második dátum, **0** (nulla) értéket ad vissza, ha az első dátum megegyezik a második dátummal, vagy pedig negatív értéket ad vissza, ha az első dátum korábbi a második dátumnál.</span><span class="sxs-lookup"><span data-stu-id="91855-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="91855-116">Példa</span><span class="sxs-lookup"><span data-stu-id="91855-116">Example</span></span>

<span data-ttu-id="91855-117">A `DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` a **-1** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="91855-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="91855-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="91855-118">Additional resources</span></span>

[<span data-ttu-id="91855-119">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="91855-119">Date and time functions</span></span>](er-functions-category-datetime.md)

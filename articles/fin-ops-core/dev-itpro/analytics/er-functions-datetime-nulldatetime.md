---
title: NULLDATETIME ER-függvény
description: A témakör tájékoztatást nyújt a NULLDATETIME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: f7282b7c161b6e183186ba81e6bcf7b34ce6e612
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746819"
---
# <a name="nulldatetime-er-function"></a><span data-ttu-id="3b665-103">NULLDATETIME ER-függvény</span><span class="sxs-lookup"><span data-stu-id="3b665-103">NULLDATETIME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b665-104">A `NULLDATETIME` függvény egy *DateTime* értéket ad eredményül, amely a **nulla** dátum/idő értékét (1900. január 1.) mutatja Egyezményes világidő (Greenwichi középidő \[GMT\]) formátumban.</span><span class="sxs-lookup"><span data-stu-id="3b665-104">The `NULLDATETIME` function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="3b665-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="3b665-105">Syntax</span></span>

```vb
NULLDATETIME ()
```

## <a name="return-values"></a><span data-ttu-id="3b665-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="3b665-106">Return values</span></span>

<span data-ttu-id="3b665-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="3b665-107">*DateTime*</span></span>

<span data-ttu-id="3b665-108">Az eredményül kapott dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="3b665-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="3b665-109">Példa</span><span class="sxs-lookup"><span data-stu-id="3b665-109">Example</span></span>

<span data-ttu-id="3b665-110">A `DATETIMEFORMAT( NULLDATETIME(), "O")` az **1900-01-01T00:00:00.0000000+00:00** karakterláncértéket adja eredményül, amikor egy olyan folyamat során hívják meg, amelyet egy olyan alkalmazás kezdeményezett, amelynek a **Nyelvre és országra/régióra vonatkozó beállítások** szakaszában a **(GMT) Egyezményes Koordinált Világidő** érték van megadva.</span><span class="sxs-lookup"><span data-stu-id="3b665-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returns the string value **1900-01-01T00:00:00.0000000+00:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT) Coordinated Universal Time** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3b665-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3b665-111">Additional resources</span></span>

[<span data-ttu-id="3b665-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="3b665-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
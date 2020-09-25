---
title: SESSIONNOW ER-függvény
description: A témakör tájékoztatást nyújt a SESSIONNOW Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 00c41564b18eed477e1cefb0bc3bb2bca3fa6fdd
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745465"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="9b7e0-103">SESSIONNOW ER-függvény</span><span class="sxs-lookup"><span data-stu-id="9b7e0-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b7e0-104">A `SESSIONNOW` függvény egy *DateTime* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát és idejét mutatja.</span><span class="sxs-lookup"><span data-stu-id="9b7e0-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b7e0-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="9b7e0-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="9b7e0-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="9b7e0-106">Return values</span></span>

<span data-ttu-id="9b7e0-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="9b7e0-107">*DateTime*</span></span>

<span data-ttu-id="9b7e0-108">Az eredményül kapott dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="9b7e0-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="9b7e0-109">Példa</span><span class="sxs-lookup"><span data-stu-id="9b7e0-109">Example</span></span>

<span data-ttu-id="9b7e0-110">A `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` az aktuális alkalmazás-munkamenet dátum-/időértékét adja vissza (2015. december 24.) a **"24.12.2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.</span><span class="sxs-lookup"><span data-stu-id="9b7e0-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b7e0-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9b7e0-111">Additional resources</span></span>

[<span data-ttu-id="9b7e0-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="9b7e0-112">Date and time functions</span></span>](er-functions-category-datetime.md)

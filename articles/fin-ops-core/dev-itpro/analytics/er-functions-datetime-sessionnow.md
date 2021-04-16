---
title: SESSIONNOW ER-függvény
description: A témakör tájékoztatást nyújt a SESSIONNOW Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 47b88a1ca0ea9fd09c2a82963901d9ace78891bb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746794"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="ab571-103">SESSIONNOW ER-függvény</span><span class="sxs-lookup"><span data-stu-id="ab571-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab571-104">A `SESSIONNOW` függvény egy *DateTime* értéket ad eredményül, amely az alkalmazás-munkamenet aktuális dátumát és idejét mutatja.</span><span class="sxs-lookup"><span data-stu-id="ab571-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab571-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="ab571-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="ab571-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="ab571-106">Return values</span></span>

<span data-ttu-id="ab571-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="ab571-107">*DateTime*</span></span>

<span data-ttu-id="ab571-108">Az eredményül kapott dátum-/időérték.</span><span class="sxs-lookup"><span data-stu-id="ab571-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="ab571-109">Példa</span><span class="sxs-lookup"><span data-stu-id="ab571-109">Example</span></span>

<span data-ttu-id="ab571-110">A `DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` az aktuális alkalmazás-munkamenet dátum-/időértékét adja vissza (2015. december 24.) a **"24.12.2015"** karakterláncként a kiválasztott német területi beállítás és a megadott formátum alapján.</span><span class="sxs-lookup"><span data-stu-id="ab571-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ab571-111">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ab571-111">Additional resources</span></span>

[<span data-ttu-id="ab571-112">Dátum és idő függvények</span><span class="sxs-lookup"><span data-stu-id="ab571-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
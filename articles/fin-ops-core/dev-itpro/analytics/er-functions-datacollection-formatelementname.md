---
title: FORMATELEMENTNAME ER-függvény
description: A témakör tájékoztatást nyújt a FORMATELEMENTNAME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: ef59bb44a7096f4c095ce37a89558a717748f02e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685327"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="9caa5-103">FORMATELEMENTNAME ER-függvény</span><span class="sxs-lookup"><span data-stu-id="9caa5-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9caa5-104">A `FORMATELEMENTNAME` függvény egy *Karakterlánc* értéket ad eredményül, amely az aktuális Elektronikus jelentéskészítési (ER) formátum elemének nevét jelöli.</span><span class="sxs-lookup"><span data-stu-id="9caa5-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="9caa5-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="9caa5-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="9caa5-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="9caa5-106">Return values</span></span>

<span data-ttu-id="9caa5-107">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="9caa5-107">*String*</span></span>

<span data-ttu-id="9caa5-108">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="9caa5-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9caa5-109">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9caa5-109">Usage notes</span></span>

<span data-ttu-id="9caa5-110">Ez a funkció olyan ER-kifejezésekben hívható, amelyek egy ER-formátum összetevő **Gyűjtött adatkulcs neve** és **Gyűjtött adatkulcs értéke** tulajdonságához lettek konfigurálva, és amely ER-formátum a **Common\\File** összetevő **Szöveg** csoportjából származik, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="9caa5-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="9caa5-111">Példa</span><span class="sxs-lookup"><span data-stu-id="9caa5-111">Example</span></span>

<span data-ttu-id="9caa5-112">Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="9caa5-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9caa5-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9caa5-113">Additional resources</span></span>

[<span data-ttu-id="9caa5-114">Adatgyűjtési függvények</span><span class="sxs-lookup"><span data-stu-id="9caa5-114">Data collection functions</span></span>](er-functions-category-data-collection.md)

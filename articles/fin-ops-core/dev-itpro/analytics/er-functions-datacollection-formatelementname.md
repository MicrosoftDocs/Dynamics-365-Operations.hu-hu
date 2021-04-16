---
title: FORMATELEMENTNAME ER-függvény
description: A témakör tájékoztatást nyújt a FORMATELEMENTNAME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: f716fe779903b4e9142b7959d868256f2d84c624
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755228"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="e6c3f-103">FORMATELEMENTNAME ER-függvény</span><span class="sxs-lookup"><span data-stu-id="e6c3f-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6c3f-104">A `FORMATELEMENTNAME` függvény egy *Karakterlánc* értéket ad eredményül, amely az aktuális Elektronikus jelentéskészítési (ER) formátum elemének nevét jelöli.</span><span class="sxs-lookup"><span data-stu-id="e6c3f-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6c3f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="e6c3f-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="e6c3f-106">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="e6c3f-106">Return values</span></span>

<span data-ttu-id="e6c3f-107">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e6c3f-107">*String*</span></span>

<span data-ttu-id="e6c3f-108">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="e6c3f-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e6c3f-109">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e6c3f-109">Usage notes</span></span>

<span data-ttu-id="e6c3f-110">Ez a funkció olyan ER-kifejezésekben hívható, amelyek egy ER-formátum összetevő **Gyűjtött adatkulcs neve** és **Gyűjtött adatkulcs értéke** tulajdonságához lettek konfigurálva, és amely ER-formátum a **Common\\File** összetevő **Szöveg** csoportjából származik, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="e6c3f-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="e6c3f-111">Példa</span><span class="sxs-lookup"><span data-stu-id="e6c3f-111">Example</span></span>

<span data-ttu-id="e6c3f-112">Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="e6c3f-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6c3f-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e6c3f-113">Additional resources</span></span>

[<span data-ttu-id="e6c3f-114">Adatgyűjtési függvények</span><span class="sxs-lookup"><span data-stu-id="e6c3f-114">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
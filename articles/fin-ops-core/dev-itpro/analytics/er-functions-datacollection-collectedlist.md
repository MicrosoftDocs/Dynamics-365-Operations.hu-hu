---
title: COLLECTEDLIST ER-függvény
description: A témakör tájékoztatást nyújt a COLLECTEDLIST Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 494fb0fa1000abe8d0234d512e41926103c56f05
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755324"
---
# <a name="collectedlist-er-function"></a><span data-ttu-id="a2360-103">COLLECTEDLIST ER-függvény</span><span class="sxs-lookup"><span data-stu-id="a2360-103">COLLECTEDLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2360-104">A `COLLECTEDLIST` függvény olyan *Rekordlista* értéket ad eredményül, amely tartalmazza azon értékek listáját, amelyeket a formátumelemek **Gyűjtött adatkulcs értéke** tulajdonsága adott vissza, és amelyeket akkor gyűjtött, amikor a formátumelemeket kimenő dokumentumok létrehozására használták a formátumfuttatás során, és amelyek teljesítik a megadott követelményeket.</span><span class="sxs-lookup"><span data-stu-id="a2360-104">The `COLLECTEDLIST` function a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate outbound documents during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="a2360-105">Minden egyes feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="a2360-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2360-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="a2360-106">Syntax</span></span>

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="a2360-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="a2360-107">Arguments</span></span>

<span data-ttu-id="a2360-108">`condition 1 range`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a2360-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="a2360-109">Olyan érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="a2360-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="a2360-110">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="a2360-110">This argument is mandatory.</span></span>

<span data-ttu-id="a2360-111">`condition 1 value`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a2360-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="a2360-112">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="a2360-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="a2360-113">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="a2360-113">This argument is mandatory.</span></span>

<span data-ttu-id="a2360-114">`condition N range`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a2360-114">`condition N range`: *String*</span></span>

<span data-ttu-id="a2360-115">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="a2360-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="a2360-116">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="a2360-116">These additional arguments are optional.</span></span>

<span data-ttu-id="a2360-117">`condition N value`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a2360-117">`condition N value`: *String*</span></span>

<span data-ttu-id="a2360-118">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="a2360-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="a2360-119">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="a2360-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="a2360-120">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="a2360-120">Return values</span></span>

<span data-ttu-id="a2360-121">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="a2360-121">*Record list*</span></span>

<span data-ttu-id="a2360-122">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="a2360-122">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a2360-123">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a2360-123">Usage notes</span></span>

<span data-ttu-id="a2360-124">Az **Gyűjtött adatkulcs neve** és a **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** alatt található, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="a2360-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="a2360-125">Ez a függvény üres listát ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="a2360-125">This function returns an empty list when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="a2360-126">A `condition range` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="a2360-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="a2360-127">A `condition value` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="a2360-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="a2360-128">Példa</span><span class="sxs-lookup"><span data-stu-id="a2360-128">Example</span></span>

<span data-ttu-id="a2360-129">Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="a2360-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2360-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a2360-130">Additional resources</span></span>

[<span data-ttu-id="a2360-131">Adatgyűjtési függvények</span><span class="sxs-lookup"><span data-stu-id="a2360-131">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
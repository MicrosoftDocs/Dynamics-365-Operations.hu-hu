---
title: COUNTIFS ER-függvény
description: A témakör tájékoztatást nyújt a COUNTIFS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 9627c7835c8f3f1b6aedc1f691470dc29a11d6b5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042550"
---
# <span data-ttu-id="5cc73-103"><a name="COUNTIFS">COUNTIFS ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="5cc73-103"><a name="COUNTIFS">COUNTIFS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5cc73-104">A `COUNTIFS` függvény egy *Egész* értéket ad eredményül, amely azoknak a formátumelemeknek a számát adja vissza, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételeket.</span><span class="sxs-lookup"><span data-stu-id="5cc73-104">The `COUNTIFS` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="5cc73-105">Minden egyes feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="5cc73-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cc73-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="5cc73-106">Syntax</span></span>

```vb
COUNTIFS (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="5cc73-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="5cc73-107">Arguments</span></span>

<span data-ttu-id="5cc73-108">`condition 1 range`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="5cc73-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="5cc73-109">Olyan érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="5cc73-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="5cc73-110">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="5cc73-110">This argument is mandatory.</span></span>

<span data-ttu-id="5cc73-111">`condition 1 value`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="5cc73-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="5cc73-112">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="5cc73-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="5cc73-113">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="5cc73-113">This argument is mandatory.</span></span>

<span data-ttu-id="5cc73-114">`condition N range`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="5cc73-114">`condition N range`: *String*</span></span>

<span data-ttu-id="5cc73-115">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="5cc73-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="5cc73-116">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="5cc73-116">These additional arguments are optional.</span></span>

<span data-ttu-id="5cc73-117">`condition N value`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="5cc73-117">`condition N value`: *String*</span></span>

<span data-ttu-id="5cc73-118">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="5cc73-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="5cc73-119">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="5cc73-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="5cc73-120">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="5cc73-120">Return values</span></span>

<span data-ttu-id="5cc73-121">*Egész*</span><span class="sxs-lookup"><span data-stu-id="5cc73-121">*Integer*</span></span>

<span data-ttu-id="5cc73-122">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="5cc73-122">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5cc73-123">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5cc73-123">Usage notes</span></span>

<span data-ttu-id="5cc73-124">Az **Gyűjtött adatkulcs neve** és a **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** alatt található, ahol a **Kimeneti részletek gyűjtése** be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="5cc73-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="5cc73-125">Ez a függvény **0** (nulla) értéket ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="5cc73-125">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="5cc73-126">A `condition range` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="5cc73-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="5cc73-127">A `condition value` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="5cc73-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="5cc73-128">Példa</span><span class="sxs-lookup"><span data-stu-id="5cc73-128">Example</span></span>

<span data-ttu-id="5cc73-129">Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="5cc73-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5cc73-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5cc73-130">Additional resources</span></span>

[<span data-ttu-id="5cc73-131">Adatgyűjtési függvények</span><span class="sxs-lookup"><span data-stu-id="5cc73-131">Data collection functions</span></span>](er-functions-category-data-collection.md)

---
title: SUMIFS ER-függvény
description: A témakör tájékoztatást nyújt a SUMIFS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: ccf8d373bb081270573f6f80711d8e31ff6c0dc3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042504"
---
# <span data-ttu-id="2405a-103"><a name="SUMIFS">SUMIFS ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="2405a-103"><a name="SUMIFS">SUMIFS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2405a-104">A `SUMIFS` függvény egy *Valós* értéket ad eredményül, amely a formátumelemek kötései által visszaadott értékek összegét mutatja, amelyeket akkor gyűjtöttek össze, amikor a formázási elemek a formátum futtatása során kimenő dokumentumok létrehozására kerültek felhasználásra, és amelyek kielégítik a megadott feltételeket.</span><span class="sxs-lookup"><span data-stu-id="2405a-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="2405a-105">Minden egyes feltétel egy kulcstartományt és egy kulcsértéket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2405a-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="2405a-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="2405a-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="2405a-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2405a-107">Arguments</span></span>

<span data-ttu-id="2405a-108">`key name for summing`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2405a-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="2405a-109">Az az érték, amelyet az Elektronikus jelentéskészítési (ER) formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés ad vissza, amelynek az összegzéshez a kötés értékét kell használni.</span><span class="sxs-lookup"><span data-stu-id="2405a-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="2405a-110">Az **Gyűjtött adatkulcs neve** tulajdonság az ER-formátum **Numerikus** összetevőjéhez vagy **Karakterlánc** összetevőjéhez konfigurálható, amely a **Common\\File** összetevő alatt található, ahol a **Kimeneti részletek gyűjtése** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2405a-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="2405a-111">`condition 1 range`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2405a-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="2405a-112">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="2405a-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="2405a-113">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="2405a-113">This argument is mandatory.</span></span>

<span data-ttu-id="2405a-114">Az **Gyűjtött adatkulcs neve** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** összetevő alatt található, ahol a **Kimeneti részletek gyűjtése** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2405a-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="2405a-115">`condition 1 value`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2405a-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="2405a-116">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="2405a-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="2405a-117">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="2405a-117">This argument is mandatory.</span></span>

<span data-ttu-id="2405a-118">Az **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** összetevő alatt található, ahol a **Kimeneti részletek gyűjtése** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2405a-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="2405a-119">`condition N range`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2405a-119">`condition N range`: *String*</span></span>

<span data-ttu-id="2405a-120">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs neve** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="2405a-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="2405a-121">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="2405a-121">These additional arguments are optional.</span></span>

<span data-ttu-id="2405a-122">Az **Gyűjtött adatkulcs neve** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** összetevő alatt található, ahol a **Kimeneti részletek gyűjtése** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2405a-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="2405a-123">`condition N value`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2405a-123">`condition N value`: *String*</span></span>

<span data-ttu-id="2405a-124">Olyan érték, amelyet egy ER-formátum összetevő **Gyűjtött adatkulcs értéke** tulajdonságában konfigurált kifejezés adott vissza.</span><span class="sxs-lookup"><span data-stu-id="2405a-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="2405a-125">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="2405a-125">These additional arguments are optional.</span></span>

<span data-ttu-id="2405a-126">Az **Gyűjtött adatkulcs értéke** tulajdonság az ER-formátum **Sorrend** összetevőjéhez vagy **XML-elem** összetevőjéhez konfigurálható, amely a **Common\\File** összetevő alatt található, ahol a **Kimeneti részletek gyűjtése** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2405a-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="2405a-127">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2405a-127">Return values</span></span>

<span data-ttu-id="2405a-128">*Valós*</span><span class="sxs-lookup"><span data-stu-id="2405a-128">*Real*</span></span>

<span data-ttu-id="2405a-129">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="2405a-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2405a-130">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2405a-130">Usage notes</span></span>

<span data-ttu-id="2405a-131">Ez a függvény **0** (nulla) értéket ad vissza, ha az aktuális **Common\\File** összetevő **Kimeneti részletek gyűjtése** beállítása ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="2405a-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="2405a-132">A `condition range` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="2405a-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="2405a-133">A `condition value` argumentumokban a **„\*”** helyettesítő karakter használható tetszőleges többszörös karakter ábrázolására.</span><span class="sxs-lookup"><span data-stu-id="2405a-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="2405a-134">Példa</span><span class="sxs-lookup"><span data-stu-id="2405a-134">Example</span></span>

<span data-ttu-id="2405a-135">Ha többet szeretne megtudni e függvény használatáról, tekintse meg az [ER kimeneti adatformátum használata számlálás és összegzés céljából](tasks/er-format-counting-summing-1.md) című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része).</span><span class="sxs-lookup"><span data-stu-id="2405a-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2405a-136">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2405a-136">Additional resources</span></span>

[<span data-ttu-id="2405a-137">Adatgyűjtési függvények</span><span class="sxs-lookup"><span data-stu-id="2405a-137">Data collection functions</span></span>](er-functions-category-data-collection.md)

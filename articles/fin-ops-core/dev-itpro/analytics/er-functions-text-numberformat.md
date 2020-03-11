---
title: NUMBERFORMAT ER-függvény
description: A témakör tájékoztatást nyújt a NUMBERFORMAT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 41f48fb49b2d28acf69fe05fe87644a4c43e81fe
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070552"
---
# <span data-ttu-id="d15cc-103"><a name="NUMBERFORMAT">NUMBERFORMAT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="d15cc-103"><a name="NUMBERFORMAT">NUMBERFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d15cc-104">A `NUMBERFORMAT` függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott [területi beállítással](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span><span class="sxs-lookup"><span data-stu-id="d15cc-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="d15cc-105">A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="d15cc-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="d15cc-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="d15cc-106">Syntax 1</span></span>

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="d15cc-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="d15cc-107">Syntax 2</span></span>

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="d15cc-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="d15cc-108">Arguments</span></span>

<span data-ttu-id="d15cc-109">`number`: *Egész* vagy *Valós*</span><span class="sxs-lookup"><span data-stu-id="d15cc-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="d15cc-110">Egy numerikus érték, amely megadja a formázandó számot.</span><span class="sxs-lookup"><span data-stu-id="d15cc-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="d15cc-111">`format`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d15cc-111">`format` : *String*</span></span>

<span data-ttu-id="d15cc-112">A formátumot jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="d15cc-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="d15cc-113">`culture`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d15cc-113">`culture`: *String*</span></span>

<span data-ttu-id="d15cc-114">*Karakterlánc* érték, amely a formázáshoz használandó területi beállítást jelöli.</span><span class="sxs-lookup"><span data-stu-id="d15cc-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="d15cc-115">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="d15cc-115">Return values</span></span>

<span data-ttu-id="d15cc-116">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d15cc-116">*String*</span></span>

<span data-ttu-id="d15cc-117">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="d15cc-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d15cc-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d15cc-118">Usage notes</span></span>

<span data-ttu-id="d15cc-119">Ha a területi beállítás nem a hívott függvény argumentumaként van definiálva, a függvény által futtatott környezet határozza meg a számok formázásához használt területi beállítást.</span><span class="sxs-lookup"><span data-stu-id="d15cc-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="d15cc-120">1. példa</span><span class="sxs-lookup"><span data-stu-id="d15cc-120">Example 1</span></span>

<span data-ttu-id="d15cc-121">Az **EN-US** területi beállítás esetében a `NUMBERFORMAT (0.45, "p")` a **"45.00 %"** értéket, a `NUMBERFORMAT (10.45, "#")` pedig a **"10"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="d15cc-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d15cc-122">2. példa</span><span class="sxs-lookup"><span data-stu-id="d15cc-122">Example 2</span></span>

<span data-ttu-id="d15cc-123">A `NUMBERFORMAT (10/3, "F2", "de")` a **3,33** értéket adja vissza, míg a `NUMBERFORMAT (10/3, "F2", "en-us")` a **3.33** értéket.</span><span class="sxs-lookup"><span data-stu-id="d15cc-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d15cc-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d15cc-124">Additional resources</span></span>

[<span data-ttu-id="d15cc-125">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="d15cc-125">Text functions</span></span>](er-functions-category-text.md)

---
title: INTVALUE ER-függvény
description: A témakör tájékoztatást nyújt az INTVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 2b279de39cf91c3919145735518034fc60cd3341
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917718"
---
# <span data-ttu-id="e4d25-103"><a name="INTVALUE">INTVALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="e4d25-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4d25-104">Az `INTVALUE` függvény a megadott karakterláncot jelölő *Int* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="e4d25-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="e4d25-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="e4d25-105">Syntax 1</span></span>

```
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="e4d25-106">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="e4d25-106">Syntax 2</span></span>

```
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="e4d25-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="e4d25-107">Arguments</span></span>

<span data-ttu-id="e4d25-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e4d25-108">`text`: *String*</span></span>

<span data-ttu-id="e4d25-109">Egy szöveges érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="e4d25-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="e4d25-110">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="e4d25-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="e4d25-111">Egy numerikus *Valós* vagy *Egész* érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="e4d25-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="e4d25-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="e4d25-112">Return values</span></span>

<span data-ttu-id="e4d25-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="e4d25-113">*Int*</span></span>

<span data-ttu-id="e4d25-114">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="e4d25-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e4d25-115">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e4d25-115">Usage notes</span></span>

<span data-ttu-id="e4d25-116">Minden tizedesjegy csonkolásra kerül.</span><span class="sxs-lookup"><span data-stu-id="e4d25-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="e4d25-117">1. példa</span><span class="sxs-lookup"><span data-stu-id="e4d25-117">Example 1</span></span>

<span data-ttu-id="e4d25-118">Az `INTVALUE ("100.77")` az *Int* esetében a **100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e4d25-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e4d25-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="e4d25-119">Example 2</span></span>

<span data-ttu-id="e4d25-120">Az `INTVALUE (-100.77)` az *Int* esetében a **-100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e4d25-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4d25-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e4d25-121">Additional resources</span></span>

[<span data-ttu-id="e4d25-122">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="e4d25-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)

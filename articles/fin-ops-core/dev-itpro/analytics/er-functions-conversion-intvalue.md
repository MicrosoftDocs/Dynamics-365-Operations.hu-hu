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
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743639"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="8a9b5-103">INTVALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="8a9b5-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a9b5-104">Az `INTVALUE` függvény a megadott karakterláncot jelölő *Int* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="8a9b5-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="8a9b5-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="8a9b5-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="8a9b5-106">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="8a9b5-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="8a9b5-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="8a9b5-107">Arguments</span></span>

<span data-ttu-id="8a9b5-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="8a9b5-108">`text`: *String*</span></span>

<span data-ttu-id="8a9b5-109">Egy szöveges érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="8a9b5-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="8a9b5-110">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="8a9b5-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="8a9b5-111">Egy numerikus *Valós* vagy *Egész* érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="8a9b5-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="8a9b5-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="8a9b5-112">Return values</span></span>

<span data-ttu-id="8a9b5-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="8a9b5-113">*Int*</span></span>

<span data-ttu-id="8a9b5-114">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="8a9b5-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8a9b5-115">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8a9b5-115">Usage notes</span></span>

<span data-ttu-id="8a9b5-116">Minden tizedesjegy csonkolásra kerül.</span><span class="sxs-lookup"><span data-stu-id="8a9b5-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="8a9b5-117">1. példa</span><span class="sxs-lookup"><span data-stu-id="8a9b5-117">Example 1</span></span>

<span data-ttu-id="8a9b5-118">Az `INTVALUE ("100.77")` az *Int* esetében a **100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="8a9b5-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="8a9b5-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="8a9b5-119">Example 2</span></span>

<span data-ttu-id="8a9b5-120">Az `INTVALUE (-100.77)` az *Int* esetében a **-100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="8a9b5-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a9b5-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8a9b5-121">Additional resources</span></span>

[<span data-ttu-id="8a9b5-122">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="8a9b5-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)

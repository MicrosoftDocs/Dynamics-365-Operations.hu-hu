---
title: INTVALUE ER-függvény
description: A témakör tájékoztatást nyújt az INTVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 71eedde5a22f36a8a827824087633de32c00cc7d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755372"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="863c4-103">INTVALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="863c4-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="863c4-104">Az `INTVALUE` függvény a megadott karakterláncot jelölő *Int* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="863c4-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="863c4-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="863c4-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="863c4-106">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="863c4-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="863c4-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="863c4-107">Arguments</span></span>

<span data-ttu-id="863c4-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="863c4-108">`text`: *String*</span></span>

<span data-ttu-id="863c4-109">Egy szöveges érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="863c4-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="863c4-110">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="863c4-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="863c4-111">Egy numerikus *Valós* vagy *Egész* érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="863c4-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="863c4-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="863c4-112">Return values</span></span>

<span data-ttu-id="863c4-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="863c4-113">*Int*</span></span>

<span data-ttu-id="863c4-114">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="863c4-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="863c4-115">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="863c4-115">Usage notes</span></span>

<span data-ttu-id="863c4-116">Minden tizedesjegy csonkolásra kerül.</span><span class="sxs-lookup"><span data-stu-id="863c4-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="863c4-117">1. példa</span><span class="sxs-lookup"><span data-stu-id="863c4-117">Example 1</span></span>

<span data-ttu-id="863c4-118">Az `INTVALUE ("100.77")` az *Int* esetében a **100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="863c4-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="863c4-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="863c4-119">Example 2</span></span>

<span data-ttu-id="863c4-120">Az `INTVALUE (-100.77)` az *Int* esetében a **-100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="863c4-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="863c4-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="863c4-121">Additional resources</span></span>

[<span data-ttu-id="863c4-122">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="863c4-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
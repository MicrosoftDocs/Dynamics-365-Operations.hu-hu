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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042650"
---
# <span data-ttu-id="f174f-103"><a name="INTVALUE">INTVALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="f174f-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f174f-104">Az `INTVALUE` függvény a megadott karakterláncot jelölő *Int* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="f174f-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f174f-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="f174f-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="f174f-106">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="f174f-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="f174f-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="f174f-107">Arguments</span></span>

<span data-ttu-id="f174f-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="f174f-108">`text`: *String*</span></span>

<span data-ttu-id="f174f-109">Egy szöveges érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="f174f-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="f174f-110">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="f174f-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="f174f-111">Egy numerikus *Valós* vagy *Egész* érték, amelyet *Int* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="f174f-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="f174f-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="f174f-112">Return values</span></span>

<span data-ttu-id="f174f-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="f174f-113">*Int*</span></span>

<span data-ttu-id="f174f-114">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="f174f-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f174f-115">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f174f-115">Usage notes</span></span>

<span data-ttu-id="f174f-116">Minden tizedesjegy csonkolásra kerül.</span><span class="sxs-lookup"><span data-stu-id="f174f-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="f174f-117">1. példa</span><span class="sxs-lookup"><span data-stu-id="f174f-117">Example 1</span></span>

<span data-ttu-id="f174f-118">Az `INTVALUE ("100.77")` az *Int* esetében a **100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="f174f-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f174f-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="f174f-119">Example 2</span></span>

<span data-ttu-id="f174f-120">Az `INTVALUE (-100.77)` az *Int* esetében a **-100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="f174f-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f174f-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f174f-121">Additional resources</span></span>

[<span data-ttu-id="f174f-122">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="f174f-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)

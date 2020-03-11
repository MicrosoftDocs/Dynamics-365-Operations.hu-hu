---
title: NUMBERVALUE ER-függvény
description: A témakör tájékoztatást nyújt a NUMBERVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 6eeb66f4206eb39141a5b2573fcb9d15428ae52a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042655"
---
# <span data-ttu-id="f9569-103"><a name="NUMBERVALUE">NUMBERVALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="f9569-103"><a name="NUMBERVALUE">NUMBERVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9569-104">A `NUMBERVALUE` függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át.</span><span class="sxs-lookup"><span data-stu-id="f9569-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="f9569-105">Az átalakítás során a megadott tizedesjegy-elválasztókat és számjegy-csoportosítókat kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="f9569-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9569-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="f9569-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="f9569-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="f9569-107">Arguments</span></span>

<span data-ttu-id="f9569-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="f9569-108">`text`: *String*</span></span>

<span data-ttu-id="f9569-109">Egy szöveges érték, amelyet *Valós* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="f9569-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="f9569-110">`decimal separator`: Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="f9569-110">`decimal separator`: String</span></span>

<span data-ttu-id="f9569-111">Tizedeselválasztó.</span><span class="sxs-lookup"><span data-stu-id="f9569-111">A decimal separator.</span></span> <span data-ttu-id="f9569-112">A decimális számok egész és tört részeinek elválasztására szolgál.</span><span class="sxs-lookup"><span data-stu-id="f9569-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="f9569-113">`digit grouping separator`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="f9569-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="f9569-114">Számjegy-csoportosító elválasztó.</span><span class="sxs-lookup"><span data-stu-id="f9569-114">A digit grouping separator.</span></span> <span data-ttu-id="f9569-115">Ezreselválasztóként használják.</span><span class="sxs-lookup"><span data-stu-id="f9569-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="f9569-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="f9569-116">Return values</span></span>

<span data-ttu-id="f9569-117">*Valós*</span><span class="sxs-lookup"><span data-stu-id="f9569-117">*Real*</span></span>

<span data-ttu-id="f9569-118">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="f9569-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="f9569-119">Példa</span><span class="sxs-lookup"><span data-stu-id="f9569-119">Example</span></span>

<span data-ttu-id="f9569-120">A `NUMBERVALUE( "1 234,56", ",", " ")` az **1234,56** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="f9569-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9569-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f9569-121">Additional resources</span></span>

[<span data-ttu-id="f9569-122">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="f9569-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)

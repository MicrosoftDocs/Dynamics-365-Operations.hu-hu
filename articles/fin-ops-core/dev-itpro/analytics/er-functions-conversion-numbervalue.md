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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3eec6dc5a472f366c9029456fe05cf1e431e1c5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685979"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="50fbe-103">NUMBERVALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="50fbe-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50fbe-104">A `NUMBERVALUE` függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott *Karakterlánc* értékből alakít át.</span><span class="sxs-lookup"><span data-stu-id="50fbe-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="50fbe-105">Az átalakítás során a megadott tizedesjegy-elválasztókat és számjegy-csoportosítókat kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="50fbe-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="50fbe-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="50fbe-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="50fbe-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="50fbe-107">Arguments</span></span>

<span data-ttu-id="50fbe-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="50fbe-108">`text`: *String*</span></span>

<span data-ttu-id="50fbe-109">Egy szöveges érték, amelyet *Valós* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="50fbe-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="50fbe-110">`decimal separator`: Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="50fbe-110">`decimal separator`: String</span></span>

<span data-ttu-id="50fbe-111">Tizedeselválasztó.</span><span class="sxs-lookup"><span data-stu-id="50fbe-111">A decimal separator.</span></span> <span data-ttu-id="50fbe-112">A decimális számok egész és tört részeinek elválasztására szolgál.</span><span class="sxs-lookup"><span data-stu-id="50fbe-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="50fbe-113">`digit grouping separator`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="50fbe-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="50fbe-114">Számjegy-csoportosító elválasztó.</span><span class="sxs-lookup"><span data-stu-id="50fbe-114">A digit grouping separator.</span></span> <span data-ttu-id="50fbe-115">Ezreselválasztóként használják.</span><span class="sxs-lookup"><span data-stu-id="50fbe-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="50fbe-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="50fbe-116">Return values</span></span>

<span data-ttu-id="50fbe-117">*Valós*</span><span class="sxs-lookup"><span data-stu-id="50fbe-117">*Real*</span></span>

<span data-ttu-id="50fbe-118">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="50fbe-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="50fbe-119">Példa</span><span class="sxs-lookup"><span data-stu-id="50fbe-119">Example</span></span>

<span data-ttu-id="50fbe-120">A `NUMBERVALUE( "1 234,56", ",", " ")` az **1234,56** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="50fbe-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50fbe-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="50fbe-121">Additional resources</span></span>

[<span data-ttu-id="50fbe-122">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="50fbe-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)

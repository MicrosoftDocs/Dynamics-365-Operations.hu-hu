---
title: INT64VALUE ER-függvény
description: A témakör tájékoztatást nyújt a INT64VALUE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: bb750116312df82448f5a0048e380f9e5274f8e9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686051"
---
# <a name="int64value-er-function"></a><span data-ttu-id="22ab4-103">INT64VALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="22ab4-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22ab4-104">Az `INT64VALUE` függvény a megadott karakterláncot jelölő *Int64* értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="22ab4-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="22ab4-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="22ab4-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="22ab4-106">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="22ab4-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="22ab4-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="22ab4-107">Arguments</span></span>

<span data-ttu-id="22ab4-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="22ab4-108">`text`: *String*</span></span>

<span data-ttu-id="22ab4-109">Egy szöveges érték, amelyet *Int64* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="22ab4-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="22ab4-110">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="22ab4-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="22ab4-111">Egy numerikus *Valós* vagy *Egész* érték, amelyet *Int64* számmá kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="22ab4-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="22ab4-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="22ab4-112">Return values</span></span>

<span data-ttu-id="22ab4-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="22ab4-113">*Int64*</span></span>

<span data-ttu-id="22ab4-114">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="22ab4-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="22ab4-115">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="22ab4-115">Usage notes</span></span>

<span data-ttu-id="22ab4-116">Minden tizedesjegy csonkolásra kerül.</span><span class="sxs-lookup"><span data-stu-id="22ab4-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="22ab4-117">1. példa</span><span class="sxs-lookup"><span data-stu-id="22ab4-117">Example 1</span></span>

<span data-ttu-id="22ab4-118">Az `INT64VALUE ("22565422744")` az *Int64* esetében a **22565422744** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="22ab4-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="22ab4-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="22ab4-119">Example 2</span></span>

<span data-ttu-id="22ab4-120">Az `INT64VALUE ( VALUE("22565422744.77"))` az *Int64* esetében a **22565422744** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="22ab4-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="22ab4-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="22ab4-121">Additional resources</span></span>

[<span data-ttu-id="22ab4-122">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="22ab4-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)

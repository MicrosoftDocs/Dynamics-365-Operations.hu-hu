---
title: REPLACE ER-függvény
description: A témakör tájékoztatást nyújt a REPLACE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: ba2590635ba465dae9ea50d3e4da989365548f3b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040986"
---
# <span data-ttu-id="e92bc-103"><a name="REPLACE">REPLACE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="e92bc-103"><a name="REPLACE">REPLACE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e92bc-104">A `REPLACE` függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal.</span><span class="sxs-lookup"><span data-stu-id="e92bc-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="e92bc-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="e92bc-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="e92bc-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="e92bc-106">Arguments</span></span>

<span data-ttu-id="e92bc-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e92bc-107">`text`: *String*</span></span>

<span data-ttu-id="e92bc-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="e92bc-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="e92bc-109">`pattern`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e92bc-109">`pattern`: *String*</span></span>

<span data-ttu-id="e92bc-110">Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a cserélni kívánt szöveget.</span><span class="sxs-lookup"><span data-stu-id="e92bc-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="e92bc-111">Ha a `regular expression flag` argumentum értéke **IGAZ**, ez az argumentum egy reguláris kifejezést tartalmaz, amely a keresési mintát és a csereszöveget is definiálja.</span><span class="sxs-lookup"><span data-stu-id="e92bc-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="e92bc-112">`replacement`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e92bc-112">`replacement`: *String*</span></span>

<span data-ttu-id="e92bc-113">Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a csereként használni kívánt szöveget.</span><span class="sxs-lookup"><span data-stu-id="e92bc-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="e92bc-114">Ha a `regular expression flag` argumentum értéke **IGAZ**, ezt az argumentumot nem használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e92bc-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="e92bc-115">`regular expression flag`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="e92bc-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="e92bc-116">*Logikai* érték, amely azt jelzi, hogy a rendszer reguláris kifejezést használ-e a csere során.</span><span class="sxs-lookup"><span data-stu-id="e92bc-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="e92bc-117">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="e92bc-117">Return values</span></span>

<span data-ttu-id="e92bc-118">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="e92bc-118">*String*</span></span>

<span data-ttu-id="e92bc-119">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="e92bc-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e92bc-120">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e92bc-120">Usage notes</span></span>

<span data-ttu-id="e92bc-121">Ha a `regular expression flag` argumentum értéke **IGAZ**, ez a függvény a megadott karakterláncot adja vissza a `pattern` argumentum által meghatározott reguláris kifejezés alkalmazásával történt módosítás után.</span><span class="sxs-lookup"><span data-stu-id="e92bc-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="e92bc-122">A reguláris kifejezés segítségével meg lehet találni azokat a karaktereket, amelyeket ki kell cserélni.</span><span class="sxs-lookup"><span data-stu-id="e92bc-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="e92bc-123">Ha a `regular expression flag` argumentum **HAMIS**, ez a függvény a [TRANSLATE](er-functions-text-translate.md) függvényhez hasonlóan viselkedik.</span><span class="sxs-lookup"><span data-stu-id="e92bc-123">If the `regular expression flag` argument is **FALSE**, this function behaves like [TRANSLATE](er-functions-text-translate.md).</span></span> <span data-ttu-id="e92bc-124">A `replacement` argumentum által megadott karakterek segítségével ki lehet cserélni a megtalált karaktereket.</span><span class="sxs-lookup"><span data-stu-id="e92bc-124">The characters that are specified by the `replacement` argument are used to replace the characters that are found.</span></span> 

## <a name="example-1"></a><span data-ttu-id="e92bc-125">1. példa</span><span class="sxs-lookup"><span data-stu-id="e92bc-125">Example 1</span></span>

<span data-ttu-id="e92bc-126">A `REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` azt a reguláris kifejezést alkalmazza, amely eltávolítja az összes nem numerikus szimbólumot, és **"19234564971"** értéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="e92bc-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="e92bc-127">2. példa</span><span class="sxs-lookup"><span data-stu-id="e92bc-127">Example 2</span></span>

<span data-ttu-id="e92bc-128">A `REPLACE ("abcdef", "cd", "GH", false)` lecseréli a **"cd"** mintát a **"GH"** karakterláncra, és az **"abGHef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e92bc-128">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e92bc-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e92bc-129">Additional resources</span></span>

[<span data-ttu-id="e92bc-130">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="e92bc-130">Text functions</span></span>](er-functions-category-text.md)

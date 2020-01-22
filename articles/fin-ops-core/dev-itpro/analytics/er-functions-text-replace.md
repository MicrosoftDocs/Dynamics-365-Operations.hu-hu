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
ms.openlocfilehash: d9c66f4c96f35e3ad5fc92e7925b5cd07c956aac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916867"
---
# <span data-ttu-id="6cd78-103"><a name="REPLACE">REPLACE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="6cd78-103"><a name="REPLACE">REPLACE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6cd78-104">A `REPLACE` függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal.</span><span class="sxs-lookup"><span data-stu-id="6cd78-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="6cd78-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="6cd78-105">Syntax</span></span>

```
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="6cd78-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="6cd78-106">Arguments</span></span>

<span data-ttu-id="6cd78-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="6cd78-107">`text`: *String*</span></span>

<span data-ttu-id="6cd78-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="6cd78-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="6cd78-109">`pattern`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="6cd78-109">`pattern`: *String*</span></span>

<span data-ttu-id="6cd78-110">Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a cserélni kívánt szöveget.</span><span class="sxs-lookup"><span data-stu-id="6cd78-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="6cd78-111">Ha a `regular expression flag` argumentum értéke **IGAZ**, ez az argumentum egy reguláris kifejezést tartalmaz, amely a keresési mintát és a csereszöveget is definiálja.</span><span class="sxs-lookup"><span data-stu-id="6cd78-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="6cd78-112">`replacement`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="6cd78-112">`replacement`: *String*</span></span>

<span data-ttu-id="6cd78-113">Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a csereként használni kívánt szöveget.</span><span class="sxs-lookup"><span data-stu-id="6cd78-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="6cd78-114">Ha a `regular expression flag` argumentum értéke **IGAZ**, ezt az argumentumot nem használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="6cd78-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="6cd78-115">`regular expression flag`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="6cd78-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="6cd78-116">*Logikai* érték, amely azt jelzi, hogy a rendszer reguláris kifejezést használ-e a csere során.</span><span class="sxs-lookup"><span data-stu-id="6cd78-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="6cd78-117">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="6cd78-117">Return values</span></span>

<span data-ttu-id="6cd78-118">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="6cd78-118">*String*</span></span>

<span data-ttu-id="6cd78-119">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="6cd78-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6cd78-120">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6cd78-120">Usage notes</span></span>

<span data-ttu-id="6cd78-121">Ha a `regular expression flag` argumentum értéke **IGAZ**, ez a függvény a megadott karakterláncot adja vissza a `pattern` argumentum által meghatározott reguláris kifejezés alkalmazásával történt módosítás után.</span><span class="sxs-lookup"><span data-stu-id="6cd78-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="6cd78-122">A reguláris kifejezés segítségével meg lehet találni azokat a karaktereket, amelyeket ki kell cserélni.</span><span class="sxs-lookup"><span data-stu-id="6cd78-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="6cd78-123">Ha a `regular expression flag` argumentum **HAMIS**, ez a függvény a [TRANSLATE](er-functions-text-translate.md) függvényhez hasonlóan viselkedik.</span><span class="sxs-lookup"><span data-stu-id="6cd78-123">If the `regular expression flag` argument is **FALSE**, this function behaves like [TRANSLATE](er-functions-text-translate.md).</span></span> <span data-ttu-id="6cd78-124">A `replacement` argumentum által megadott karakterek segítségével ki lehet cserélni a megtalált karaktereket.</span><span class="sxs-lookup"><span data-stu-id="6cd78-124">The characters that are specified by the `replacement` argument are used to replace the characters that are found.</span></span> 

## <a name="example-1"></a><span data-ttu-id="6cd78-125">1. példa</span><span class="sxs-lookup"><span data-stu-id="6cd78-125">Example 1</span></span>

<span data-ttu-id="6cd78-126">A `REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` azt a reguláris kifejezést alkalmazza, amely eltávolítja az összes nem numerikus szimbólumot, és **"19234564971"** értéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="6cd78-126">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="6cd78-127">2. példa</span><span class="sxs-lookup"><span data-stu-id="6cd78-127">Example 2</span></span>

<span data-ttu-id="6cd78-128">A `REPLACE ("abcdef", "cd", "GH", false)` lecseréli a **"cd"** mintát a **"GH"** karakterláncra, és az **"abGHef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="6cd78-128">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6cd78-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6cd78-129">Additional resources</span></span>

[<span data-ttu-id="6cd78-130">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="6cd78-130">Text functions</span></span>](er-functions-category-text.md)

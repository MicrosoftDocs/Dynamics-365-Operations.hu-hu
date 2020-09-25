---
title: REPLACE ER-függvény
description: A témakör tájékoztatást nyújt a REPLACE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: c9e64bd8e039b4eeca829c3c37299f002ba03592
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743735"
---
# <a name="replace-er-function"></a><span data-ttu-id="385ee-103">REPLACE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="385ee-103">REPLACE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="385ee-104">A `REPLACE` függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal.</span><span class="sxs-lookup"><span data-stu-id="385ee-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="385ee-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="385ee-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="385ee-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="385ee-106">Arguments</span></span>

<span data-ttu-id="385ee-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="385ee-107">`text`: *String*</span></span>

<span data-ttu-id="385ee-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="385ee-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="385ee-109">`pattern`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="385ee-109">`pattern`: *String*</span></span>

<span data-ttu-id="385ee-110">Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a cserélni kívánt szöveget.</span><span class="sxs-lookup"><span data-stu-id="385ee-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="385ee-111">Ha a `regular expression flag` argumentum értéke **IGAZ**, ez az argumentum egy reguláris kifejezést tartalmaz, amely a keresési mintát és a csereszöveget is definiálja.</span><span class="sxs-lookup"><span data-stu-id="385ee-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="385ee-112">`replacement`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="385ee-112">`replacement`: *String*</span></span>

<span data-ttu-id="385ee-113">Ha a `regular expression flag` argumentum **HAMIS**, ez az argumentum tartalmazza a csereként használni kívánt szöveget.</span><span class="sxs-lookup"><span data-stu-id="385ee-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="385ee-114">Ha a `regular expression flag` argumentum értéke **IGAZ**, ezt az argumentumot nem használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="385ee-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="385ee-115">`regular expression flag`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="385ee-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="385ee-116">*Logikai* érték, amely azt jelzi, hogy a rendszer reguláris kifejezést használ-e a csere során.</span><span class="sxs-lookup"><span data-stu-id="385ee-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="385ee-117">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="385ee-117">Return values</span></span>

<span data-ttu-id="385ee-118">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="385ee-118">*String*</span></span>

<span data-ttu-id="385ee-119">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="385ee-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="385ee-120">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="385ee-120">Usage notes</span></span>

<span data-ttu-id="385ee-121">Ha a `regular expression flag` argumentum értéke **IGAZ**, ez a függvény a megadott karakterláncot adja vissza a `pattern` argumentum által meghatározott reguláris kifejezés alkalmazásával történt módosítás után.</span><span class="sxs-lookup"><span data-stu-id="385ee-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="385ee-122">A reguláris kifejezés segítségével meg lehet találni azokat a karaktereket, amelyeket ki kell cserélni.</span><span class="sxs-lookup"><span data-stu-id="385ee-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="385ee-123">Ha a `regular expression flag` argumentum **HAMIS**, akkor ez a funkció a megadott karakterláncot adja vissza, miután az `pattern` argumentumban megadott karaktereket a `replacement` argumentum karakterei cserélték le.</span><span class="sxs-lookup"><span data-stu-id="385ee-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="385ee-124">1. példa</span><span class="sxs-lookup"><span data-stu-id="385ee-124">Example 1</span></span>

<span data-ttu-id="385ee-125">A `REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` azt a reguláris kifejezést alkalmazza, amely eltávolítja az összes nem numerikus szimbólumot, és **"19234564971"** értéket jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="385ee-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="385ee-126">2. példa</span><span class="sxs-lookup"><span data-stu-id="385ee-126">Example 2</span></span>

<span data-ttu-id="385ee-127">A `REPLACE ("abcdef", "cd", "GH", false)` lecseréli a **"cd"** mintát a **"GH"** karakterláncra, és az **"abGHef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="385ee-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="385ee-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="385ee-128">Additional resources</span></span>

[<span data-ttu-id="385ee-129">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="385ee-129">Text functions</span></span>](er-functions-category-text.md)

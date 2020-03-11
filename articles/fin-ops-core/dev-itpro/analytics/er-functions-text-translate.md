---
title: TRANSLATE ER-függvény
description: A témakör tájékoztatást nyújt a TRANSLATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 07fe19c5f66c33e336f76f3a72d3bbda0c7e8d86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040917"
---
# <span data-ttu-id="02d8b-103"><a name="TRANSLATE">TRANSLATE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="02d8b-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02d8b-104">A `TRANSLATE` függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal.</span><span class="sxs-lookup"><span data-stu-id="02d8b-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="02d8b-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="02d8b-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="02d8b-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="02d8b-106">Arguments</span></span>

<span data-ttu-id="02d8b-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="02d8b-107">`text`: *String*</span></span>

<span data-ttu-id="02d8b-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="02d8b-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="02d8b-109">`pattern`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="02d8b-109">`pattern`: *String*</span></span>

<span data-ttu-id="02d8b-110">A lecserélendő szöveg.</span><span class="sxs-lookup"><span data-stu-id="02d8b-110">The text that must be replaced.</span></span>

<span data-ttu-id="02d8b-111">`replacement`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="02d8b-111">`replacement`: *String*</span></span>

<span data-ttu-id="02d8b-112">A csereként használandó szöveg.</span><span class="sxs-lookup"><span data-stu-id="02d8b-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="02d8b-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="02d8b-113">Return values</span></span>

<span data-ttu-id="02d8b-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="02d8b-114">*String*</span></span>

<span data-ttu-id="02d8b-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="02d8b-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="02d8b-116">Példa</span><span class="sxs-lookup"><span data-stu-id="02d8b-116">Example</span></span>

<span data-ttu-id="02d8b-117">A `TRANSLATE ("abcdef", "cd", "GH")` lecseréli a **"cd"** mintát a **"GH"** karakterláncra, és az **"abGHef"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="02d8b-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02d8b-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="02d8b-118">Additional resources</span></span>

[<span data-ttu-id="02d8b-119">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="02d8b-119">Text functions</span></span>](er-functions-category-text.md)

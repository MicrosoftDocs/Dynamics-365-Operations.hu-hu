---
title: TRANSLATE ER-függvény
description: A témakör tájékoztatást nyújt a TRANSLATE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5d192b8679d6df2c44a0038fe4ffc181a6a54df
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685303"
---
# <a name="translate-er-function"></a><span data-ttu-id="28b29-103">TRANSLATE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="28b29-103">TRANSLATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28b29-104">A `TRANSLATE` függvény olyan *Karakterlánc* értéket ad vissza, amely a megadott szöveg karakterrel történő helyettesítésének eredményét tartalmazza egy másik megadott halmaz karaktereivel.</span><span class="sxs-lookup"><span data-stu-id="28b29-104">The `TRANSLATE` function returns a *String* value that contains the result of the character replacement of specified text in characters of another provided set.</span></span>

## <a name="syntax"></a><span data-ttu-id="28b29-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="28b29-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="28b29-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="28b29-106">Arguments</span></span>

<span data-ttu-id="28b29-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="28b29-107">`text`: *String*</span></span>

<span data-ttu-id="28b29-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="28b29-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="28b29-109">`pattern`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="28b29-109">`pattern`: *String*</span></span>

<span data-ttu-id="28b29-110">A lecserélendő szöveg.</span><span class="sxs-lookup"><span data-stu-id="28b29-110">The text that must be replaced.</span></span>

<span data-ttu-id="28b29-111">`replacement`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="28b29-111">`replacement`: *String*</span></span>

<span data-ttu-id="28b29-112">A csereként használandó szöveg.</span><span class="sxs-lookup"><span data-stu-id="28b29-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="28b29-113">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="28b29-113">Return values</span></span>

<span data-ttu-id="28b29-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="28b29-114">*String*</span></span>

<span data-ttu-id="28b29-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="28b29-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="28b29-116">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="28b29-116">Usage notes</span></span>

<span data-ttu-id="28b29-117">A `TRANSLATE` függvény egyszerre csak egy karaktert cserél.</span><span class="sxs-lookup"><span data-stu-id="28b29-117">The `TRANSLATE` function replaces one character at a time.</span></span> <span data-ttu-id="28b29-118">A függvény cseréli a `text` argumentum első karakterét az `pattern` argumentum első karakterével, majd a második karakterrel, és a ugyanezt a folyamatot követi a befejezésig.</span><span class="sxs-lookup"><span data-stu-id="28b29-118">The function replaces the first character of the `text` argument with the first character of the `pattern` argument and then the second character and follows the same flow until finished.</span></span> <span data-ttu-id="28b29-119">Amikor egy karakter a `text` és a `pattern` az argumentumok között megegyezik, a program az `replacement` argumentumban szereplő karakternek karakterével helyettesíti, amely ugyanabban a pozícióban van, mint a `pattern` argumentum karaktere.</span><span class="sxs-lookup"><span data-stu-id="28b29-119">When a character from the `text` and `pattern` arguments match, it is replaced by a character from the `replacement` argument that is located in the same position as the character from the `pattern` argument.</span></span> <span data-ttu-id="28b29-120">Ha egy karakter többször jelenik meg az `pattern` argumentumban, akkor a `replacement` argumentum leképezése megfelel a karakter első előfordulásakor használtnak.</span><span class="sxs-lookup"><span data-stu-id="28b29-120">If a character appears multiple times in the `pattern` argument, the `replacement` argument mapping that corresponds to the first occurrence of this character is used.</span></span>

## <a name="example-1"></a><span data-ttu-id="28b29-121">1. példa</span><span class="sxs-lookup"><span data-stu-id="28b29-121">Example 1</span></span>

<span data-ttu-id="28b29-122">A `TRANSLATE ("abcdef", "cd", "GH")` cseréli a **„c”** karakterét a meghatározott **„abcdef”** szövegnek a **„G”** karkaterére a `replacement` szövegnek a következők miatt:</span><span class="sxs-lookup"><span data-stu-id="28b29-122">`TRANSLATE ("abcdef", "cd", "GH")` replaces the **"c"** character of the specified  **“abcdef”** text with the **"G"** character of the `replacement` text due to the following:</span></span>
-   <span data-ttu-id="28b29-123">A **„c ”** karakter az első pozícióban található a `pattern` szövegben.</span><span class="sxs-lookup"><span data-stu-id="28b29-123">The **"c"** character is presented in the `pattern` text in the first position.</span></span>
-   <span data-ttu-id="28b29-124">A `replacement` szöveg első pozíciójában a **„G”** karakter szerepel.</span><span class="sxs-lookup"><span data-stu-id="28b29-124">The first position of the `replacement` text contains the **"G"** character.</span></span>

## <a name="example-2"></a><span data-ttu-id="28b29-125">2. példa</span><span class="sxs-lookup"><span data-stu-id="28b29-125">Example 2</span></span>

<span data-ttu-id="28b29-126">A `TRANSLATE ("abcdef", "ccd", "GH")` az **„abGdef”** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="28b29-126">`TRANSLATE ("abcdef", "ccd", "GH")` returns **"abGdef"**.</span></span>

## <a name="example-3"></a><span data-ttu-id="28b29-127">3. példa</span><span class="sxs-lookup"><span data-stu-id="28b29-127">Example 3</span></span>

<span data-ttu-id="28b29-128">A `TRANSLATE ("abccba", "abc", "123")` a **"123321"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="28b29-128">`TRANSLATE ("abccba", "abc", "123")` returns **"123321"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28b29-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="28b29-129">Additional resources</span></span>

[<span data-ttu-id="28b29-130">Szöveges függvények</span><span class="sxs-lookup"><span data-stu-id="28b29-130">Text functions</span></span>](er-functions-category-text.md)

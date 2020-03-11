---
title: NUMERALSTOTEXT ER-függvény
description: A témakör tájékoztatást nyújt a NUMERALSTOTEXT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 31fd4076d04ce7d849555bc8301c4d23ad8e1a7e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041009"
---
# <span data-ttu-id="2edc5-103"><a name="NUMERALSTOTEXT">NUMERALSTOTEXT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="2edc5-103"><a name="NUMERALSTOTEXT">NUMERALSTOTEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2edc5-104">A `NUMERALSTOTEXT` függvény *Karakterlánc* értékként adja vissza a megadott számot, miután kiírta (azaz szöveges karakterlánccá konvertálta) a megadott nyelven.</span><span class="sxs-lookup"><span data-stu-id="2edc5-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="2edc5-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="2edc5-105">Syntax</span></span>

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="2edc5-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2edc5-106">Arguments</span></span>

<span data-ttu-id="2edc5-107">`number`: *Egész* vagy *Valós*</span><span class="sxs-lookup"><span data-stu-id="2edc5-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="2edc5-108">Egy numerikus érték, amely megadja a kiírandó számot.</span><span class="sxs-lookup"><span data-stu-id="2edc5-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="2edc5-109">`language`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2edc5-109">`language`: *String*</span></span>

<span data-ttu-id="2edc5-110">A nyelvkódot jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="2edc5-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="2edc5-111">`currency`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2edc5-111">`currency`: *String*</span></span>

<span data-ttu-id="2edc5-112">A pénznemkódot jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="2edc5-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="2edc5-113">`print currency name flag`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="2edc5-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="2edc5-114">*Logikai* érték, amely azt jelzi, hogy hozzá kell-e adni egy pénznemnevet a kiírt szöveghez.</span><span class="sxs-lookup"><span data-stu-id="2edc5-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="2edc5-115">`decimal points`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="2edc5-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="2edc5-116">Egy *Egész* érték, amely megadja, hogy hány tizedesjegyet kell tartalmaznia a kiírt szövegnek.</span><span class="sxs-lookup"><span data-stu-id="2edc5-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="2edc5-117">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2edc5-117">Return values</span></span>

<span data-ttu-id="2edc5-118">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2edc5-118">*String*</span></span>

<span data-ttu-id="2edc5-119">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="2edc5-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2edc5-120">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2edc5-120">Usage notes</span></span>

<span data-ttu-id="2edc5-121">A nyelvkód megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="2edc5-121">The language code is optional.</span></span> <span data-ttu-id="2edc5-122">Ha üres karakterláncként van megadva, akkor a futó környezet nyelvkódját használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="2edc5-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="2edc5-123">Az alapértelmezett nyelvkód az **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="2edc5-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="2edc5-124">A futó környezet nyelvkódja az Elektronikus jelentéskészítési (er) formátum **Mappa** vagy **Fájl** elemében van definiálva.</span><span class="sxs-lookup"><span data-stu-id="2edc5-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="2edc5-125">A pénznemkód megadása nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="2edc5-125">The currency code is optional.</span></span> <span data-ttu-id="2edc5-126">Ha üres karakterláncként van megadva, akkor a futó környezet vállalati pénznemét használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="2edc5-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="2edc5-127">A `print currency name flag` és `decimal points` argumentumok csak a következő nyelvkódok esetében kerülnek elemzésre: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** és **RU**.</span><span class="sxs-lookup"><span data-stu-id="2edc5-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="2edc5-128">Emellett a `print currency name flag` argumentum elemzését csak azoknak a rendszert használó vállalatoknak az esetében végzi el a rendszer, amelyek ország- vagy régiókörnyezete támogatja a valuták nevének ragozását.</span><span class="sxs-lookup"><span data-stu-id="2edc5-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="2edc5-129">1. példa</span><span class="sxs-lookup"><span data-stu-id="2edc5-129">Example 1</span></span>

<span data-ttu-id="2edc5-130">A `NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` az **"One Thousand Two Hundred Thirty Four and 56"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2edc5-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2edc5-131">2. példa</span><span class="sxs-lookup"><span data-stu-id="2edc5-131">Example 2</span></span>

<span data-ttu-id="2edc5-132">A `NUMERALSTOTEXT (120, "PL", "", false, 0)` az **"Sto dwadzieścia"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2edc5-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="2edc5-133">3. példa</span><span class="sxs-lookup"><span data-stu-id="2edc5-133">Example 3</span></span>

<span data-ttu-id="2edc5-134">A `NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` az **"Сто двадцать евро 21 евроцент"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2edc5-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2edc5-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2edc5-135">Additional resources</span></span>

[<span data-ttu-id="2edc5-136">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="2edc5-136">Text functions</span></span>](er-functions-category-text.md)

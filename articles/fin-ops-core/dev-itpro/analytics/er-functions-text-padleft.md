---
title: PADLEFT ER-függvény
description: A témakör tájékoztatást nyújt a PADLEFT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 268941d8bc0bd4dc6de6d2597c05a11c1f530f15
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680146"
---
# <a name="padleft-er-function"></a><span data-ttu-id="0dabe-103">PADLEFT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="0dabe-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0dabe-104">A `PADLEFT` függvény egy megadott hosszúságú *Karakterlánc* értéket ad vissza, amelyben az aktuális karakterlánc eleje megadott karakterekkel van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="0dabe-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="0dabe-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0dabe-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="0dabe-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0dabe-106">Arguments</span></span>

<span data-ttu-id="0dabe-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0dabe-107">`text`: *String*</span></span>

<span data-ttu-id="0dabe-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="0dabe-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="0dabe-109">`length`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="0dabe-109">`length`: *Integer*</span></span>

<span data-ttu-id="0dabe-110">A kitöltött karakterláncban a karakterek végső számát jelölő *Egész* szám.</span><span class="sxs-lookup"><span data-stu-id="0dabe-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="0dabe-111">`padding chars`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0dabe-111">`padding chars`: *String*</span></span>

<span data-ttu-id="0dabe-112">Kitöltésként használandó karakterek.</span><span class="sxs-lookup"><span data-stu-id="0dabe-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="0dabe-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="0dabe-113">Return values</span></span>

<span data-ttu-id="0dabe-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0dabe-114">*String*</span></span>

<span data-ttu-id="0dabe-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="0dabe-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0dabe-116">Példa</span><span class="sxs-lookup"><span data-stu-id="0dabe-116">Example</span></span>

<span data-ttu-id="0dabe-117">A `PADLEFT ("1234", 10, "`&nbsp;`")` a következő szöveges karakterláncot adja vissza: **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="0dabe-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0dabe-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0dabe-118">Additional resources</span></span>

[<span data-ttu-id="0dabe-119">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="0dabe-119">Text functions</span></span>](er-functions-category-text.md)

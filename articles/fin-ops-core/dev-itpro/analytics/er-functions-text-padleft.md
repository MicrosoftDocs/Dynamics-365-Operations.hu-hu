---
title: PADLEFT ER-függvény
description: A témakör tájékoztatást nyújt a PADLEFT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 806b1d318f18b0ade01f7b03909c90b1e4fd29b1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746243"
---
# <a name="padleft-er-function"></a><span data-ttu-id="fddf0-103">PADLEFT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="fddf0-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fddf0-104">A `PADLEFT` függvény egy megadott hosszúságú *Karakterlánc* értéket ad vissza, amelyben az aktuális karakterlánc eleje megadott karakterekkel van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="fddf0-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="fddf0-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="fddf0-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="fddf0-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="fddf0-106">Arguments</span></span>

<span data-ttu-id="fddf0-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fddf0-107">`text`: *String*</span></span>

<span data-ttu-id="fddf0-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="fddf0-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="fddf0-109">`length`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="fddf0-109">`length`: *Integer*</span></span>

<span data-ttu-id="fddf0-110">A kitöltött karakterláncban a karakterek végső számát jelölő *Egész* szám.</span><span class="sxs-lookup"><span data-stu-id="fddf0-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="fddf0-111">`padding chars`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fddf0-111">`padding chars`: *String*</span></span>

<span data-ttu-id="fddf0-112">Kitöltésként használandó karakterek.</span><span class="sxs-lookup"><span data-stu-id="fddf0-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="fddf0-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="fddf0-113">Return values</span></span>

<span data-ttu-id="fddf0-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fddf0-114">*String*</span></span>

<span data-ttu-id="fddf0-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="fddf0-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="fddf0-116">Példa</span><span class="sxs-lookup"><span data-stu-id="fddf0-116">Example</span></span>

<span data-ttu-id="fddf0-117">A `PADLEFT ("1234", 10, "`&nbsp;`")` a következő szöveges karakterláncot adja vissza: **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="fddf0-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fddf0-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fddf0-118">Additional resources</span></span>

[<span data-ttu-id="fddf0-119">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="fddf0-119">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
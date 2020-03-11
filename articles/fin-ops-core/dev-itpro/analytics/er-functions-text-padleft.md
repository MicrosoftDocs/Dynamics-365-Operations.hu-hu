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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d11e2d8b46614085156228ab1001d1f9340a05b0
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040963"
---
# <span data-ttu-id="44700-103"><a name="PADLEFT">PADLEFT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="44700-103"><a name="PADLEFT">PADLEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44700-104">A `PADLEFT` függvény egy megadott hosszúságú *Karakterlánc* értéket ad vissza, amelyben az aktuális karakterlánc eleje megadott karakterekkel van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="44700-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="44700-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="44700-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="44700-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="44700-106">Arguments</span></span>

<span data-ttu-id="44700-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="44700-107">`text`: *String*</span></span>

<span data-ttu-id="44700-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="44700-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="44700-109">`length`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="44700-109">`length`: *Integer*</span></span>

<span data-ttu-id="44700-110">A kitöltött karakterláncban a karakterek végső számát jelölő *Egész* szám.</span><span class="sxs-lookup"><span data-stu-id="44700-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="44700-111">`padding chars`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="44700-111">`padding chars`: *String*</span></span>

<span data-ttu-id="44700-112">Kitöltésként használandó karakterek.</span><span class="sxs-lookup"><span data-stu-id="44700-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="44700-113">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="44700-113">Return values</span></span>

<span data-ttu-id="44700-114">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="44700-114">*String*</span></span>

<span data-ttu-id="44700-115">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="44700-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="44700-116">Példa</span><span class="sxs-lookup"><span data-stu-id="44700-116">Example</span></span>

<span data-ttu-id="44700-117">A `PADLEFT ("1234", 10, "`&nbsp;`")` a következő szöveges karakterláncot adja vissza: **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="44700-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="44700-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="44700-118">Additional resources</span></span>

[<span data-ttu-id="44700-119">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="44700-119">Text functions</span></span>](er-functions-category-text.md)

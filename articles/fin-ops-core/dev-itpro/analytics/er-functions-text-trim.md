---
title: TRIM ER-függvény
description: A témakör tájékoztatást nyújt a TRIM Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1f7999ccbcd167280cca1abc48377c36d2bc15f
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744215"
---
# <a name="trim-er-function"></a><span data-ttu-id="33ae7-103">TRIM ER-függvény</span><span class="sxs-lookup"><span data-stu-id="33ae7-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33ae7-104">A `TRIM` függvény a megadott karakterláncot *Karakterlánc* értékként adja vissza, miután a kezdő és záró szóközöket levágta, és a szavak közötti több szóközt eltávolította.</span><span class="sxs-lookup"><span data-stu-id="33ae7-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="33ae7-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="33ae7-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="33ae7-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="33ae7-106">Arguments</span></span>

<span data-ttu-id="33ae7-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="33ae7-107">`text`: *String*</span></span>

<span data-ttu-id="33ae7-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="33ae7-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="33ae7-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="33ae7-109">Return values</span></span>

<span data-ttu-id="33ae7-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="33ae7-110">*String*</span></span>

<span data-ttu-id="33ae7-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="33ae7-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="33ae7-112">Példa</span><span class="sxs-lookup"><span data-stu-id="33ae7-112">Example</span></span>

<span data-ttu-id="33ae7-113">A `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` a **"Mintaszöveg"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="33ae7-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33ae7-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="33ae7-114">Additional resources</span></span>

[<span data-ttu-id="33ae7-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="33ae7-115">Text functions</span></span>](er-functions-category-text.md)

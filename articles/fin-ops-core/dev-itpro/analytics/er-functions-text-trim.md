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
ms.openlocfilehash: 2673b0167f7602a6d6eaa79be639905028e99822
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915533"
---
# <span data-ttu-id="39247-103"><a name="TRIM">TRIM ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="39247-103"><a name="TRIM">TRIM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39247-104">A `TRIM` függvény a megadott karakterláncot *Karakterlánc* értékként adja vissza, miután a kezdő és záró szóközöket levágta, és a szavak közötti több szóközt eltávolította.</span><span class="sxs-lookup"><span data-stu-id="39247-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="39247-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="39247-105">Syntax</span></span>

```
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="39247-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="39247-106">Arguments</span></span>

<span data-ttu-id="39247-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="39247-107">`text`: *String*</span></span>

<span data-ttu-id="39247-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="39247-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="39247-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="39247-109">Return values</span></span>

<span data-ttu-id="39247-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="39247-110">*String*</span></span>

<span data-ttu-id="39247-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="39247-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="39247-112">Példa</span><span class="sxs-lookup"><span data-stu-id="39247-112">Example</span></span>

<span data-ttu-id="39247-113">A `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` a **"Mintaszöveg"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="39247-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39247-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="39247-114">Additional resources</span></span>

[<span data-ttu-id="39247-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="39247-115">Text functions</span></span>](er-functions-category-text.md)

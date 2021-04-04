---
title: TRIM ER-függvény
description: A témakör tájékoztatást nyújt a TRIM Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: b671ef72a3558c17fb16db939770394b225656da
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560036"
---
# <a name="trim-er-function"></a><span data-ttu-id="7cf68-103">TRIM ER-függvény</span><span class="sxs-lookup"><span data-stu-id="7cf68-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7cf68-104">A `TRIM` függvény a megadott karakterláncot *Karakterlánc* értékként adja vissza, miután a kezdő és záró szóközöket levágta, és a szavak közötti több szóközt eltávolította.</span><span class="sxs-lookup"><span data-stu-id="7cf68-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="7cf68-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="7cf68-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="7cf68-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="7cf68-106">Arguments</span></span>

<span data-ttu-id="7cf68-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="7cf68-107">`text`: *String*</span></span>

<span data-ttu-id="7cf68-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="7cf68-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="7cf68-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="7cf68-109">Return values</span></span>

<span data-ttu-id="7cf68-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="7cf68-110">*String*</span></span>

<span data-ttu-id="7cf68-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="7cf68-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="7cf68-112">Példa</span><span class="sxs-lookup"><span data-stu-id="7cf68-112">Example</span></span>

<span data-ttu-id="7cf68-113">A `TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` a **"Mintaszöveg"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="7cf68-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7cf68-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7cf68-114">Additional resources</span></span>

[<span data-ttu-id="7cf68-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="7cf68-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: MOD_97 ER-függvény
description: A témakör tájékoztatást nyújt a MOD_97 Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: ce2192c7bc849996e08573d71d8ed43956c8fb89
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070529"
---
# <span data-ttu-id="a5d6d-103"><a name="MOD_97">MOD_97 ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="a5d6d-103"><a name="MOD_97">MOD_97 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5d6d-104">A `MOD_97` függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást MOD97-kifejezésként jelöli, a megadott számlaszám számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5d6d-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="a5d6d-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="a5d6d-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="a5d6d-106">Arguments</span></span>

<span data-ttu-id="a5d6d-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a5d6d-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="a5d6d-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="a5d6d-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="a5d6d-109">Return values</span></span>

<span data-ttu-id="a5d6d-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a5d6d-110">*String*</span></span>

<span data-ttu-id="a5d6d-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="a5d6d-112">Példa</span><span class="sxs-lookup"><span data-stu-id="a5d6d-112">Example</span></span>

<span data-ttu-id="a5d6d-113">A `MOD_97 ("VEND-200002")` a **"20000285"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5d6d-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a5d6d-114">Additional resources</span></span>

[<span data-ttu-id="a5d6d-115">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="a5d6d-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

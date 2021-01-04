---
title: NOT ER-függvény
description: A témakör tájékoztatást nyújt a NOT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2308ab4d222863312441b3f17559ac4d3afbfb29
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686954"
---
# <a name="not-er-function"></a><span data-ttu-id="b4e5f-103">NOT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="b4e5f-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4e5f-104">A `NOT` függvény a megadott feltétel sztornírozott logikai értékét adja eredményül *logikai* értékként.</span><span class="sxs-lookup"><span data-stu-id="b4e5f-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4e5f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="b4e5f-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="b4e5f-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="b4e5f-106">Arguments</span></span>

<span data-ttu-id="b4e5f-107">`condition`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="b4e5f-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="b4e5f-108">Érvényes feltételes kifejezés, amelyet meg kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="b4e5f-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="b4e5f-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="b4e5f-109">Return values</span></span>

<span data-ttu-id="b4e5f-110">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="b4e5f-110">*Boolean*</span></span>

<span data-ttu-id="b4e5f-111">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="b4e5f-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="b4e5f-112">Példa</span><span class="sxs-lookup"><span data-stu-id="b4e5f-112">Example</span></span>

<span data-ttu-id="b4e5f-113">A `NOT (TRUE)` **HAMIS** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="b4e5f-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4e5f-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b4e5f-114">Additional resources</span></span>

[<span data-ttu-id="b4e5f-115">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="b4e5f-115">Logical functions</span></span>](er-functions-category-logical.md)

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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af588c3714069040fa339d3121e6eb404b9be979
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744647"
---
# <a name="not-er-function"></a><span data-ttu-id="176ca-103">NOT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="176ca-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="176ca-104">A `NOT` függvény a megadott feltétel sztornírozott logikai értékét adja eredményül *logikai* értékként.</span><span class="sxs-lookup"><span data-stu-id="176ca-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="176ca-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="176ca-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="176ca-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="176ca-106">Arguments</span></span>

<span data-ttu-id="176ca-107">`condition`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="176ca-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="176ca-108">Érvényes feltételes kifejezés, amelyet meg kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="176ca-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="176ca-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="176ca-109">Return values</span></span>

<span data-ttu-id="176ca-110">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="176ca-110">*Boolean*</span></span>

<span data-ttu-id="176ca-111">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="176ca-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="176ca-112">Példa</span><span class="sxs-lookup"><span data-stu-id="176ca-112">Example</span></span>

<span data-ttu-id="176ca-113">A `NOT (TRUE)` **HAMIS** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="176ca-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="176ca-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="176ca-114">Additional resources</span></span>

[<span data-ttu-id="176ca-115">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="176ca-115">Logical functions</span></span>](er-functions-category-logical.md)

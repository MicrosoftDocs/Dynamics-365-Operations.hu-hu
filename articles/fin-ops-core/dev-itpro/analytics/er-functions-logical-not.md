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
ms.openlocfilehash: a518f255a4488c5ed6e007b1787e678fd88aff36
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041722"
---
# <span data-ttu-id="5baf8-103"><a name="NOT">NOT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="5baf8-103"><a name="NOT">NOT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5baf8-104">A `NOT` függvény a megadott feltétel sztornírozott logikai értékét adja eredményül *logikai* értékként.</span><span class="sxs-lookup"><span data-stu-id="5baf8-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5baf8-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="5baf8-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="5baf8-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="5baf8-106">Arguments</span></span>

<span data-ttu-id="5baf8-107">`condition`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="5baf8-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="5baf8-108">Érvényes feltételes kifejezés, amelyet meg kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="5baf8-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="5baf8-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="5baf8-109">Return values</span></span>

<span data-ttu-id="5baf8-110">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="5baf8-110">*Boolean*</span></span>

<span data-ttu-id="5baf8-111">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="5baf8-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="5baf8-112">Példa</span><span class="sxs-lookup"><span data-stu-id="5baf8-112">Example</span></span>

<span data-ttu-id="5baf8-113">A `NOT (TRUE)` **HAMIS** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="5baf8-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5baf8-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5baf8-114">Additional resources</span></span>

[<span data-ttu-id="5baf8-115">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="5baf8-115">Logical functions</span></span>](er-functions-category-logical.md)

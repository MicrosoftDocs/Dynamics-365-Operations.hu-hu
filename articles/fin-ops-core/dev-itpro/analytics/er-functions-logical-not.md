---
title: NOT ER-függvény
description: A témakör tájékoztatást nyújt a NOT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751713"
---
# <a name="not-er-function"></a><span data-ttu-id="c6488-103">NOT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="c6488-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6488-104">A `NOT` függvény a megadott feltétel sztornírozott logikai értékét adja eredményül *logikai* értékként.</span><span class="sxs-lookup"><span data-stu-id="c6488-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6488-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c6488-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="c6488-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c6488-106">Arguments</span></span>

<span data-ttu-id="c6488-107">`condition`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="c6488-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="c6488-108">Érvényes feltételes kifejezés, amelyet meg kell fordítani.</span><span class="sxs-lookup"><span data-stu-id="c6488-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="c6488-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c6488-109">Return values</span></span>

<span data-ttu-id="c6488-110">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="c6488-110">*Boolean*</span></span>

<span data-ttu-id="c6488-111">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="c6488-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="c6488-112">Példa</span><span class="sxs-lookup"><span data-stu-id="c6488-112">Example</span></span>

<span data-ttu-id="c6488-113">A `NOT (TRUE)` **HAMIS** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="c6488-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c6488-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c6488-114">Additional resources</span></span>

[<span data-ttu-id="c6488-115">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="c6488-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
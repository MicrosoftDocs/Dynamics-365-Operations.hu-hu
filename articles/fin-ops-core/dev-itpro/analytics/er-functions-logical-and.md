---
title: AND ER-függvény
description: A témakör tájékoztatást nyújt az AND Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 4a246496eca0d5a8538ac7f1577957e6b9eae4e3
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743471"
---
# <a name="and-er-function"></a><span data-ttu-id="9c3d1-103">AND ER-függvény</span><span class="sxs-lookup"><span data-stu-id="9c3d1-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c3d1-104">Az `AND` függvény **IGAZ** *Logikai* értéket ad eredményül, ha a megadott feltételek mindegyike igaz.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="9c3d1-105">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c3d1-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="9c3d1-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="9c3d1-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="9c3d1-107">Arguments</span></span>

<span data-ttu-id="9c3d1-108">`condition 1`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="9c3d1-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="9c3d1-109">Érvényes feltételes kifejezés, amelyet tesztelni kell.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="9c3d1-110">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-110">This argument is required.</span></span>

<span data-ttu-id="9c3d1-111">`condition N`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="9c3d1-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="9c3d1-112">Érvényes feltételes kifejezés, amelyet tesztelni kell.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="9c3d1-113">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="9c3d1-114">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="9c3d1-114">Return values</span></span>

<span data-ttu-id="9c3d1-115">*Logikai*</span><span class="sxs-lookup"><span data-stu-id="9c3d1-115">*Boolean*</span></span>

<span data-ttu-id="9c3d1-116">Az eredményül kapott *Logikai* érték.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9c3d1-117">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9c3d1-117">Usage notes</span></span>

<span data-ttu-id="9c3d1-118">A logikai függvények argumentumaiban az adatforrás-hivatkozások, a numerikus és szöveges értékek, a logikai értékek, az összehasonlító operátorok és más Elektronikus jelentéskészítési (ER) függvények használhatók.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="9c3d1-119">Azonban az összes argumentumot **IGAZ** vagy **HAMIS** *logikai* értékre kell értékelni.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="9c3d1-120">Példa</span><span class="sxs-lookup"><span data-stu-id="9c3d1-120">Example</span></span>

<span data-ttu-id="9c3d1-121">Az `AND (1=1, "a"="a")` **IGAZ** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="9c3d1-122">Az `AND (1=2, "a"="a")` **HAMIS** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="9c3d1-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c3d1-123">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9c3d1-123">Additional resources</span></span>

[<span data-ttu-id="9c3d1-124">Logikai függvények</span><span class="sxs-lookup"><span data-stu-id="9c3d1-124">Logical functions</span></span>](er-functions-category-logical.md)

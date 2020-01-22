---
title: ABS ER-függvény
description: A témakör tájékoztatást nyújt az ABS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 9b32c5e8a413be3583177f565e2d4909330ad1e0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917097"
---
# <span data-ttu-id="dcaf8-103"><a name="ABS">ABS ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="dcaf8-103"><a name="ABS">ABS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dcaf8-104">Az `ABS` függvény a megadott szám abszolútértékét (modulus) adja eredményül *Valós* értékként.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="dcaf8-105">Más szóval, a számot előjel nélkül adja vissza.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="dcaf8-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="dcaf8-106">Syntax</span></span>

```
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="dcaf8-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="dcaf8-107">Arguments</span></span>

<span data-ttu-id="dcaf8-108">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="dcaf8-108">`number`: *Real*</span></span>

<span data-ttu-id="dcaf8-109">Egy numerikus érték, amelynek a modulus értékét meg szeretné jeleníteni.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="dcaf8-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="dcaf8-110">Return values</span></span>

<span data-ttu-id="dcaf8-111">*Valós*</span><span class="sxs-lookup"><span data-stu-id="dcaf8-111">*Real*</span></span>

<span data-ttu-id="dcaf8-112">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="dcaf8-113">Példa</span><span class="sxs-lookup"><span data-stu-id="dcaf8-113">Example</span></span>

<span data-ttu-id="dcaf8-114">Az `ABS (-1)` az **1** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dcaf8-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dcaf8-115">Additional resources</span></span>

[<span data-ttu-id="dcaf8-116">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="dcaf8-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)

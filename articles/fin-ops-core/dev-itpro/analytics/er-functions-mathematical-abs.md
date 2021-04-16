---
title: ABS ER-függvény
description: A témakör tájékoztatást nyújt az ABS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 2a3613483d53fb265741b5d6a34a91da443dcef7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753144"
---
# <a name="abs-er-function"></a><span data-ttu-id="04122-103">ABS ER-függvény</span><span class="sxs-lookup"><span data-stu-id="04122-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04122-104">Az `ABS` függvény a megadott szám abszolútértékét (modulus) adja eredményül *Valós* értékként.</span><span class="sxs-lookup"><span data-stu-id="04122-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="04122-105">Más szóval, a számot előjel nélkül adja vissza.</span><span class="sxs-lookup"><span data-stu-id="04122-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="04122-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="04122-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="04122-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="04122-107">Arguments</span></span>

<span data-ttu-id="04122-108">`number`: *Valós*</span><span class="sxs-lookup"><span data-stu-id="04122-108">`number`: *Real*</span></span>

<span data-ttu-id="04122-109">Egy numerikus érték, amelynek a modulus értékét meg szeretné jeleníteni.</span><span class="sxs-lookup"><span data-stu-id="04122-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="04122-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="04122-110">Return values</span></span>

<span data-ttu-id="04122-111">*Valós*</span><span class="sxs-lookup"><span data-stu-id="04122-111">*Real*</span></span>

<span data-ttu-id="04122-112">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="04122-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="04122-113">Példa</span><span class="sxs-lookup"><span data-stu-id="04122-113">Example</span></span>

<span data-ttu-id="04122-114">Az `ABS (-1)` az **1** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="04122-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04122-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="04122-115">Additional resources</span></span>

[<span data-ttu-id="04122-116">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="04122-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
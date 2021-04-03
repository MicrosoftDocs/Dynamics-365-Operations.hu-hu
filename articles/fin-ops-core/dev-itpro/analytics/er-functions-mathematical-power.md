---
title: POWER ER-függvény
description: A témakör tájékoztatást nyújt a POWER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 9c45e7f9b47a3f0ff4445b1dd160def0ada3a56e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570422"
---
# <a name="power-er-function"></a><span data-ttu-id="2ea6c-103">POWER ER-függvény</span><span class="sxs-lookup"><span data-stu-id="2ea6c-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ea6c-104">A `POWER` függvény egy *Valós* értéket ad eredményül, amely a megadott pozitív számnak a megadott hatványra történő emelésének eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ea6c-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="2ea6c-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="2ea6c-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2ea6c-106">Arguments</span></span>

<span data-ttu-id="2ea6c-107">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="2ea6c-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="2ea6c-108">Egy numerikus érték, amelyet a megadott hatványra kell emelni.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="2ea6c-109">`power`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="2ea6c-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="2ea6c-110">Az adott hatványt reprezentáló numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="2ea6c-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2ea6c-111">Return values</span></span>

<span data-ttu-id="2ea6c-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="2ea6c-112">*Real*</span></span>

<span data-ttu-id="2ea6c-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="2ea6c-114">1. példa</span><span class="sxs-lookup"><span data-stu-id="2ea6c-114">Example 1</span></span>

<span data-ttu-id="2ea6c-115">A `POWER (10, 2)` az **100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2ea6c-116">2. példa</span><span class="sxs-lookup"><span data-stu-id="2ea6c-116">Example 2</span></span>

<span data-ttu-id="2ea6c-117">A `POWER (4, 0.5)` az **2** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2ea6c-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2ea6c-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2ea6c-118">Additional resources</span></span>

[<span data-ttu-id="2ea6c-119">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="2ea6c-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
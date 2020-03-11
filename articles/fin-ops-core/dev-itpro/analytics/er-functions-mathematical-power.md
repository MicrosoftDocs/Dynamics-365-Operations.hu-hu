---
title: POWER ER-függvény
description: A témakör tájékoztatást nyújt a POWER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: c57222d7fcc133faa679bab43431272c984c9d8b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041630"
---
# <span data-ttu-id="d84d4-103"><a name="POWER">POWER ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="d84d4-103"><a name="POWER">POWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d84d4-104">A `POWER` függvény egy *Valós* értéket ad eredményül, amely a megadott pozitív számnak a megadott hatványra történő emelésének eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="d84d4-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="d84d4-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="d84d4-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="d84d4-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="d84d4-106">Arguments</span></span>

<span data-ttu-id="d84d4-107">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="d84d4-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="d84d4-108">Egy numerikus érték, amelyet a megadott hatványra kell emelni.</span><span class="sxs-lookup"><span data-stu-id="d84d4-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="d84d4-109">`power`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="d84d4-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="d84d4-110">Az adott hatványt reprezentáló numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="d84d4-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="d84d4-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="d84d4-111">Return values</span></span>

<span data-ttu-id="d84d4-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="d84d4-112">*Real*</span></span>

<span data-ttu-id="d84d4-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="d84d4-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="d84d4-114">1. példa</span><span class="sxs-lookup"><span data-stu-id="d84d4-114">Example 1</span></span>

<span data-ttu-id="d84d4-115">A `POWER (10, 2)` az **100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="d84d4-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d84d4-116">2. példa</span><span class="sxs-lookup"><span data-stu-id="d84d4-116">Example 2</span></span>

<span data-ttu-id="d84d4-117">A `POWER (4, 0.5)` az **2** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="d84d4-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d84d4-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d84d4-118">Additional resources</span></span>

[<span data-ttu-id="d84d4-119">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="d84d4-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)

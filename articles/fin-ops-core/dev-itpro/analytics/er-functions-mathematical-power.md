---
title: POWER ER-függvény
description: A témakör tájékoztatást nyújt a POWER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: ce1f4c735f815c46003ded35156bb47febf177a3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750156"
---
# <a name="power-er-function"></a><span data-ttu-id="ca75d-103">POWER ER-függvény</span><span class="sxs-lookup"><span data-stu-id="ca75d-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca75d-104">A `POWER` függvény egy *Valós* értéket ad eredményül, amely a megadott pozitív számnak a megadott hatványra történő emelésének eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="ca75d-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca75d-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="ca75d-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="ca75d-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="ca75d-106">Arguments</span></span>

<span data-ttu-id="ca75d-107">`number`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="ca75d-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="ca75d-108">Egy numerikus érték, amelyet a megadott hatványra kell emelni.</span><span class="sxs-lookup"><span data-stu-id="ca75d-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="ca75d-109">`power`: *Valós* vagy *Egész*</span><span class="sxs-lookup"><span data-stu-id="ca75d-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="ca75d-110">Az adott hatványt reprezentáló numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="ca75d-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="ca75d-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="ca75d-111">Return values</span></span>

<span data-ttu-id="ca75d-112">*Valós*</span><span class="sxs-lookup"><span data-stu-id="ca75d-112">*Real*</span></span>

<span data-ttu-id="ca75d-113">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="ca75d-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="ca75d-114">1. példa</span><span class="sxs-lookup"><span data-stu-id="ca75d-114">Example 1</span></span>

<span data-ttu-id="ca75d-115">A `POWER (10, 2)` az **100** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ca75d-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ca75d-116">2. példa</span><span class="sxs-lookup"><span data-stu-id="ca75d-116">Example 2</span></span>

<span data-ttu-id="ca75d-117">A `POWER (4, 0.5)` az **2** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ca75d-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca75d-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ca75d-118">Additional resources</span></span>

[<span data-ttu-id="ca75d-119">Matematikai funkciók</span><span class="sxs-lookup"><span data-stu-id="ca75d-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
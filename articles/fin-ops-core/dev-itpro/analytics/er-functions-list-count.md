---
title: COUNT ER-függvény
description: A témakör tájékoztatást nyújt a COUNT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 2d29b82a8c3b108f7651e6d593cb17e7ec8ca872
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916246"
---
# <span data-ttu-id="0c04e-103"><a name="COUNT">COUNT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="0c04e-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c04e-104">A `COUNT` függvény egy *Egész* értéket ad eredményül, amely a megadott listában szereplő rekordok számát jelképezi, ha a lista nem üres.</span><span class="sxs-lookup"><span data-stu-id="0c04e-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="0c04e-105">Ha a lista üres, a függvény **0** (nulla) értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="0c04e-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="0c04e-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0c04e-106">Syntax</span></span>

```
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="0c04e-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0c04e-107">Arguments</span></span>

<span data-ttu-id="0c04e-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="0c04e-108">`list`: *Record list*</span></span>

<span data-ttu-id="0c04e-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="0c04e-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="0c04e-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="0c04e-110">Return values</span></span>

<span data-ttu-id="0c04e-111">*Egész*</span><span class="sxs-lookup"><span data-stu-id="0c04e-111">*Integer*</span></span>

<span data-ttu-id="0c04e-112">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="0c04e-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="0c04e-113">Példa</span><span class="sxs-lookup"><span data-stu-id="0c04e-113">Example</span></span>

<span data-ttu-id="0c04e-114">A `COUNT (SPLIT("abcd" , 3))` a **2** értéket adja vissza, mert a példában használt `SPLIT` függvény létrehoz egy listát, amely két rekordból áll.</span><span class="sxs-lookup"><span data-stu-id="0c04e-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c04e-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0c04e-115">Additional resources</span></span>

[<span data-ttu-id="0c04e-116">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="0c04e-116">List functions</span></span>](er-functions-category-list.md)

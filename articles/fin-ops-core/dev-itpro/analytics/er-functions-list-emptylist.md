---
title: EMPTYLIST ER-függvény
description: A témakör tájékoztatást nyújt az EMPTYLIST Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccb52d7d88f292720360ae913ead5be239165193
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687670"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="bed0a-103">EMPTYLIST ER-függvény</span><span class="sxs-lookup"><span data-stu-id="bed0a-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bed0a-104">Az `EMPTYLIST` függvény a megadott lista forrásként való felhasználásával egy üres *Rekordlista* értéket ad vissza a lista szerkezetére vonatkozó forrásként.</span><span class="sxs-lookup"><span data-stu-id="bed0a-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="bed0a-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="bed0a-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="bed0a-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="bed0a-106">Arguments</span></span>

<span data-ttu-id="bed0a-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="bed0a-107">`list`: *Record list*</span></span>

<span data-ttu-id="bed0a-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="bed0a-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="bed0a-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="bed0a-109">Return values</span></span>

<span data-ttu-id="bed0a-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="bed0a-110">*Record list*</span></span>

<span data-ttu-id="bed0a-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="bed0a-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="bed0a-112">Példa</span><span class="sxs-lookup"><span data-stu-id="bed0a-112">Example</span></span>

<span data-ttu-id="bed0a-113">A `EMPTYLIST (SPLIT ("abc", 1))` új üres listát ad vissza, amelynek ugyanolyan szerkezete van, mint a felhasznált `SPLIT` függvény által megjelenített listának.</span><span class="sxs-lookup"><span data-stu-id="bed0a-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bed0a-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bed0a-114">Additional resources</span></span>

[<span data-ttu-id="bed0a-115">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="bed0a-115">List functions</span></span>](er-functions-category-list.md)

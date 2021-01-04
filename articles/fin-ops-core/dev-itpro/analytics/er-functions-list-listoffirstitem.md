---
title: LISTOFFIRSTITEM ER-függvény
description: A témakör tájékoztatást nyújt a LISTOFFIRSTITEM Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 8ea81bce8cd6b922f3ef1d53ec0c4b2574780377
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686488"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="ac3fd-103">LISTOFFIRSTITEM ER-függvény</span><span class="sxs-lookup"><span data-stu-id="ac3fd-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac3fd-104">A `LISTOFFIRSTITEM` függvény egy *Rekordlista* értéket ad vissza, amely csak a megadott lista első rekordjából áll.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac3fd-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="ac3fd-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="ac3fd-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="ac3fd-106">Arguments</span></span>

<span data-ttu-id="ac3fd-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="ac3fd-107">`list`: *Record list*</span></span>

<span data-ttu-id="ac3fd-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ac3fd-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="ac3fd-109">Return values</span></span>

<span data-ttu-id="ac3fd-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="ac3fd-110">*Record list*</span></span>

<span data-ttu-id="ac3fd-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="ac3fd-112">Példa</span><span class="sxs-lookup"><span data-stu-id="ac3fd-112">Example</span></span>

<span data-ttu-id="ac3fd-113">A `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` kifejezés az **„A”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="ac3fd-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac3fd-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ac3fd-114">Additional resources</span></span>

[<span data-ttu-id="ac3fd-115">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="ac3fd-115">List functions</span></span>](er-functions-category-list.md)

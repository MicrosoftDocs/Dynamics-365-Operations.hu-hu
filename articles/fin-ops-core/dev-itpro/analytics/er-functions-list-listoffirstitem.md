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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d985ef5015bc104a83260b64418821cc715e8cb
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917258"
---
# <span data-ttu-id="c527b-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="c527b-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c527b-104">A `LISTOFFIRSTITEM` függvény egy *Rekordlista* értéket ad vissza, amely csak a megadott lista első rekordjából áll.</span><span class="sxs-lookup"><span data-stu-id="c527b-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="c527b-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c527b-105">Syntax</span></span>

```
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="c527b-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c527b-106">Arguments</span></span>

<span data-ttu-id="c527b-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="c527b-107">`list`: *Record list*</span></span>

<span data-ttu-id="c527b-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="c527b-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c527b-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c527b-109">Return values</span></span>

<span data-ttu-id="c527b-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="c527b-110">*Record list*</span></span>

<span data-ttu-id="c527b-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="c527b-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="c527b-112">Példa</span><span class="sxs-lookup"><span data-stu-id="c527b-112">Example</span></span>

<span data-ttu-id="c527b-113">A `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` kifejezés az **„A”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="c527b-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c527b-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c527b-114">Additional resources</span></span>

[<span data-ttu-id="c527b-115">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="c527b-115">List functions</span></span>](er-functions-category-list.md)

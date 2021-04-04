---
title: LISTOFFIRSTITEM ER-függvény
description: A témakör tájékoztatást nyújt a LISTOFFIRSTITEM Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: f2e1f7e55c61f883aebb9d5a522a883a9a9de694
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569840"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="524ae-103">LISTOFFIRSTITEM ER-függvény</span><span class="sxs-lookup"><span data-stu-id="524ae-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="524ae-104">A `LISTOFFIRSTITEM` függvény egy *Rekordlista* értéket ad vissza, amely csak a megadott lista első rekordjából áll.</span><span class="sxs-lookup"><span data-stu-id="524ae-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="524ae-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="524ae-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="524ae-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="524ae-106">Arguments</span></span>

<span data-ttu-id="524ae-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="524ae-107">`list`: *Record list*</span></span>

<span data-ttu-id="524ae-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="524ae-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="524ae-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="524ae-109">Return values</span></span>

<span data-ttu-id="524ae-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="524ae-110">*Record list*</span></span>

<span data-ttu-id="524ae-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="524ae-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="524ae-112">Példa</span><span class="sxs-lookup"><span data-stu-id="524ae-112">Example</span></span>

<span data-ttu-id="524ae-113">A `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` kifejezés az **„A”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="524ae-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="524ae-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="524ae-114">Additional resources</span></span>

[<span data-ttu-id="524ae-115">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="524ae-115">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
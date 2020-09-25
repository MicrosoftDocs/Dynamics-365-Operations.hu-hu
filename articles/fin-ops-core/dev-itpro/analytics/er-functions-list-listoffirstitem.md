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
ms.openlocfilehash: 069ec0c6d5578ca6ab68814adf325bd79e73b9e8
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745057"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="e13e8-103">LISTOFFIRSTITEM ER-függvény</span><span class="sxs-lookup"><span data-stu-id="e13e8-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e13e8-104">A `LISTOFFIRSTITEM` függvény egy *Rekordlista* értéket ad vissza, amely csak a megadott lista első rekordjából áll.</span><span class="sxs-lookup"><span data-stu-id="e13e8-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="e13e8-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="e13e8-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="e13e8-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="e13e8-106">Arguments</span></span>

<span data-ttu-id="e13e8-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="e13e8-107">`list`: *Record list*</span></span>

<span data-ttu-id="e13e8-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="e13e8-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="e13e8-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="e13e8-109">Return values</span></span>

<span data-ttu-id="e13e8-110">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="e13e8-110">*Record list*</span></span>

<span data-ttu-id="e13e8-111">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="e13e8-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="e13e8-112">Példa</span><span class="sxs-lookup"><span data-stu-id="e13e8-112">Example</span></span>

<span data-ttu-id="e13e8-113">A `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` kifejezés az **„A”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="e13e8-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e13e8-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e13e8-114">Additional resources</span></span>

[<span data-ttu-id="e13e8-115">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="e13e8-115">List functions</span></span>](er-functions-category-list.md)

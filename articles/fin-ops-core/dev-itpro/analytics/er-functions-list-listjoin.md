---
title: LISTJOIN ER-függvény
description: A témakör tájékoztatást nyújt a LISTJOIN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7f78b687865e63e658c1c1c4f148b50595bf063
ms.sourcegitcommit: 54bdcf8e9b6d1b1aae2a244f7a82754879d12053
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2020
ms.locfileid: "3740663"
---
# <a name=""></a><span data-ttu-id="039f3-103"><a name="LISTJOIN">LISTJOIN ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="039f3-103"><a name="LISTJOIN">LISTJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="039f3-104">A `LISTJOIN` függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új rekordlistát jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="039f3-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="039f3-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="039f3-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="039f3-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="039f3-106">Arguments</span></span>

<span data-ttu-id="039f3-107">`list 1`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="039f3-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="039f3-108">Hivatkozás a *Rekordlista* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="039f3-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="039f3-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="039f3-109">This argument is mandatory.</span></span>

<span data-ttu-id="039f3-110">`list N`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="039f3-110">`list N`: *Record list*</span></span>

<span data-ttu-id="039f3-111">Hivatkozás a *Rekordlista* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="039f3-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="039f3-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="039f3-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="039f3-113">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="039f3-113">Return values</span></span>

<span data-ttu-id="039f3-114">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="039f3-114">*Record list*</span></span>

<span data-ttu-id="039f3-115">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="039f3-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="039f3-116">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="039f3-116">Usage notes</span></span>

<span data-ttu-id="039f3-117">A létrehozott lista szerkezete csak azokat a mezőket tartalmazza, amelyek az argumentumban szereplő minden rekordlista struktúrájában láthatók.</span><span class="sxs-lookup"><span data-stu-id="039f3-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="039f3-118">Példa</span><span class="sxs-lookup"><span data-stu-id="039f3-118">Example</span></span>

<span data-ttu-id="039f3-119">Adja meg az **1. rekord** adatforrását a `Container` típushoz.</span><span class="sxs-lookup"><span data-stu-id="039f3-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="039f3-120">Ez az adatforrás a `Calculated field` típus alábbi beágyazott mezőit tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="039f3-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="039f3-121">**Kód**: Ez a mező egy olyan kifejezést tartalmaz, amely a `String` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="039f3-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="039f3-122">**Mennyiség**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Real` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="039f3-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="039f3-123">Majd adja meg a **2. rekord** adatforrását a `Container` típushoz.</span><span class="sxs-lookup"><span data-stu-id="039f3-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="039f3-124">Ez az adatforrás a `Calculated field` típus alábbi beágyazott mezőit tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="039f3-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="039f3-125">**Mennyiség**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Real` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="039f3-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="039f3-126">**IsValid**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Boolean` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="039f3-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="039f3-128">Ebben az esetben a `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` kifejezés egy új, két rekordot tartalmazó listát ad eredményül.</span><span class="sxs-lookup"><span data-stu-id="039f3-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="039f3-130">A lista szerkezete a `Real` típus egyetlen **Mennyiség** mezőjéből áll, mivel ez a mező az egyetlen olyan mező, amely szerepel a hívott függvény minden argumentumában megjelenik.</span><span class="sxs-lookup"><span data-stu-id="039f3-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="039f3-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="039f3-132">Additional resources</span></span>

[<span data-ttu-id="039f3-133">Listafüggvények</span><span class="sxs-lookup"><span data-stu-id="039f3-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="039f3-134">Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához</span><span class="sxs-lookup"><span data-stu-id="039f3-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)

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
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249035"
---
# <a name=""></a><span data-ttu-id="9be3f-103"><a name="LISTJOIN">LISTJOIN ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="9be3f-103"><a name="LISTJOIN">LISTJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9be3f-104">A `LISTJOIN` függvény egy *Rekordlista* értéket ad vissza, amely a megadott argumentumokból létrehozott új rekordlistát jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="9be3f-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="9be3f-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="9be3f-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="9be3f-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="9be3f-106">Arguments</span></span>

<span data-ttu-id="9be3f-107">`list 1`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="9be3f-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="9be3f-108">Hivatkozás a *Rekordlista* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="9be3f-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="9be3f-109">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="9be3f-109">This argument is mandatory.</span></span>

<span data-ttu-id="9be3f-110">`list N`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="9be3f-110">`list N`: *Record list*</span></span>

<span data-ttu-id="9be3f-111">Hivatkozás a *Rekordlista* adattípusú adatforrásra.</span><span class="sxs-lookup"><span data-stu-id="9be3f-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="9be3f-112">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="9be3f-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="9be3f-113">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="9be3f-113">Return values</span></span>

<span data-ttu-id="9be3f-114">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="9be3f-114">*Record list*</span></span>

<span data-ttu-id="9be3f-115">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="9be3f-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9be3f-116">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9be3f-116">Usage notes</span></span>

<span data-ttu-id="9be3f-117">A létrehozott lista szerkezete csak azokat a mezőket tartalmazza, amelyek az argumentumban szereplő minden rekordlista struktúrájában láthatók.</span><span class="sxs-lookup"><span data-stu-id="9be3f-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="9be3f-118">Példa</span><span class="sxs-lookup"><span data-stu-id="9be3f-118">Example</span></span>

<span data-ttu-id="9be3f-119">Adja meg az **1. rekord** adatforrását a `Container` típushoz.</span><span class="sxs-lookup"><span data-stu-id="9be3f-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="9be3f-120">Ez az adatforrás a `Calculated field` típus alábbi beágyazott mezőit tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="9be3f-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="9be3f-121">**Kód**: Ez a mező egy olyan kifejezést tartalmaz, amely a `String` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="9be3f-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="9be3f-122">**Mennyiség**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Real` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="9be3f-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="9be3f-123">Majd adja meg a **2. rekord** adatforrását a `Container` típushoz.</span><span class="sxs-lookup"><span data-stu-id="9be3f-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="9be3f-124">Ez az adatforrás a `Calculated field` típus alábbi beágyazott mezőit tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="9be3f-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="9be3f-125">**Mennyiség**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Real` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="9be3f-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="9be3f-126">**IsValid**: Ez a mező egy olyan kifejezést tartalmaz, amely a `Boolean` típus értékét adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="9be3f-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

<span data-ttu-id="9be3f-127">Ebben az esetben a `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` kifejezés egy új, két rekordot tartalmazó listát ad eredményül.</span><span class="sxs-lookup"><span data-stu-id="9be3f-127">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span> <span data-ttu-id="9be3f-128">A lista szerkezete a `Real` típus egyetlen **Mennyiség** mezőjéből áll, mivel ez a mező az egyetlen olyan mező, amely szerepel a hívott függvény minden argumentumában megjelenik.</span><span class="sxs-lookup"><span data-stu-id="9be3f-128">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9be3f-129">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9be3f-129">Additional resources</span></span>

[<span data-ttu-id="9be3f-130">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="9be3f-130">List functions</span></span>](er-functions-category-list.md)

---
title: SPLITLISTBYLIMIT ER-függvény
description: A témakör tájékoztatást nyújt a SPLITLISTBYLIMIT Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 1e6a4638cd32cb253261cc7fbaacb45b47f52c62
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683699"
---
# <a name="splitlistbylimit-er-function"></a><span data-ttu-id="bc417-103">SPLITLISTBYLIMIT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="bc417-103">SPLITLISTBYLIMIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bc417-104">A `SPLITLISTBYLIMIT` függvény a megadott listát az allisták (kötegek) új listájára osztja fel.</span><span class="sxs-lookup"><span data-stu-id="bc417-104">The `SPLITLISTBYLIMIT` function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="bc417-105">Az egyes kötegekben lévő rekordok számát dinamikusan számítja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="bc417-105">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="bc417-106">A függvény ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll.</span><span class="sxs-lookup"><span data-stu-id="bc417-106">The function then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc417-107">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="bc417-107">Syntax</span></span>

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a><span data-ttu-id="bc417-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="bc417-108">Arguments</span></span>

<span data-ttu-id="bc417-109">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="bc417-109">`list`: *Record list*</span></span>

<span data-ttu-id="bc417-110">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="bc417-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="bc417-111">`limit value`*Egész* vagy *Valós*</span><span class="sxs-lookup"><span data-stu-id="bc417-111">`limit value`: *Integer* or *Real*</span></span>

<span data-ttu-id="bc417-112">Az eredeti listának a kötegekben való felosztása során használt korlát maximális értéke.</span><span class="sxs-lookup"><span data-stu-id="bc417-112">The maximum value of the limit that is used to split the original list into batches.</span></span>

<span data-ttu-id="bc417-113">`limit source`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="bc417-113">`limit source`: *Field*</span></span>

<span data-ttu-id="bc417-114">Az *Egész* vagy *Valós* típusú mezők érvényes elérési útja a megadott listában.</span><span class="sxs-lookup"><span data-stu-id="bc417-114">The valid path of a field of the *Integer* or *Real* type in the specified list.</span></span> <span data-ttu-id="bc417-115">Ennek a mezőnek az értéke azt a lépést határozza meg, amellyel a teljes összeg növelhető.</span><span class="sxs-lookup"><span data-stu-id="bc417-115">The value of this field defines the step that the total sum is increased on.</span></span>

## <a name="return-values"></a><span data-ttu-id="bc417-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="bc417-116">Return values</span></span>

<span data-ttu-id="bc417-117">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="bc417-117">*Record list*</span></span>

<span data-ttu-id="bc417-118">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="bc417-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bc417-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bc417-119">Usage notes</span></span>

<span data-ttu-id="bc417-120">A visszaadott kötegek listája a következő elemeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="bc417-120">The list of batches that is returned contains the following elements:</span></span>

- <span data-ttu-id="bc417-121">**Érték**: *Lista*</span><span class="sxs-lookup"><span data-stu-id="bc417-121">**Value**: *List*</span></span>

    <span data-ttu-id="bc417-122">Az aktuális köteghez tartozó rekordlista.</span><span class="sxs-lookup"><span data-stu-id="bc417-122">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="bc417-123">**BatchNumber**: *Egész*</span><span class="sxs-lookup"><span data-stu-id="bc417-123">**BatchNumber**: *Integer*</span></span>

    <span data-ttu-id="bc417-124">Az aktuális köteg száma a visszaadott listában.</span><span class="sxs-lookup"><span data-stu-id="bc417-124">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="bc417-125">A rendszer nem használja a korlátot az eredeti lista egyetlen eleménél, amikor a korlát forrása meghaladja a meghatározott határértéket.</span><span class="sxs-lookup"><span data-stu-id="bc417-125">The limit isn't applied to a single item of the original list if the limit source exceeds the defined limit.</span></span>

## <a name="example"></a><span data-ttu-id="bc417-126">Példa</span><span class="sxs-lookup"><span data-stu-id="bc417-126">Example</span></span>

<span data-ttu-id="bc417-127">A következő ábrán egy Elektronikus jelentéskészítési (ER) formátum látható.</span><span class="sxs-lookup"><span data-stu-id="bc417-127">The following illustration shows an Electronic reporting (ER) format.</span></span>

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

<span data-ttu-id="bc417-128">Az alábbi ábrákon láthatók az adatforrások, amelyek használatosak a formátumhoz.</span><span class="sxs-lookup"><span data-stu-id="bc417-128">The following illustration shows the data sources that are used for the format.</span></span>

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

<span data-ttu-id="bc417-129">Az alábbi ábrán a formátum futtatásának eredménye látható.</span><span class="sxs-lookup"><span data-stu-id="bc417-129">The following illustration shows the result when the format is run.</span></span> <span data-ttu-id="bc417-130">Ebben az esetben a kimenet egy egyszerű lista árucikkekről.</span><span class="sxs-lookup"><span data-stu-id="bc417-130">In this case, the output is a flat list of commodity items.</span></span>

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

<span data-ttu-id="bc417-131">A következő ábrákon ugyanezt a formázást módosítottuk, hogy az árucikkcsoportok listáját kötegekben mutassa be, amikor egy-egy kötegnek árucikkeket kell tartalmaznia, és a teljes súly nem haladhatja meg a 9-es határértéket.</span><span class="sxs-lookup"><span data-stu-id="bc417-131">In the following illustrations, the same format has been adjusted so that it presents the list of commodity items in batches if a single batch must include commodities and the total weight should not exceed a limit of 9.</span></span>

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

<span data-ttu-id="bc417-132">Az alábbi ábrán a módosított formátum futtatásának eredménye látható.</span><span class="sxs-lookup"><span data-stu-id="bc417-132">The following illustration shows the result when the adjusted format is run.</span></span>

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> <span data-ttu-id="bc417-133">A korlát nem vonatkozik az eredeti lista utolsó elemére, mivel a korlát forrásának (**súly**) értéke (**11**) meghaladja a meghatározott határértéket (**9**).</span><span class="sxs-lookup"><span data-stu-id="bc417-133">The limit isn't applied to the last item of the original list, because the value (**11**) of the limit source (**weight**) exceeds the defined limit (**9**).</span></span> <span data-ttu-id="bc417-134">Az allisták figyelmen kívül hagyásához a jelentéskészítés során használja a `WHERE` függvényt vagy a megfelelő formátumelem **Engedélyezett** kifejezését, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="bc417-134">To ignore sublists during report generation, use either the `WHERE` function or the **Enabled** expression of the corresponding format element, as you require.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc417-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bc417-135">Additional resources</span></span>

[<span data-ttu-id="bc417-136">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="bc417-136">List functions</span></span>](er-functions-category-list.md)

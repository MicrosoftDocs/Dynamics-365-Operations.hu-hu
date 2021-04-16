---
title: SPLITLIST ER-függvény
description: A témakör tájékoztatást nyújt a SPLITLIST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: 99e199e238b3132622a8b305895637b430e8f6d2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745569"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="f6181-103">SPLITLIST ER-függvény</span><span class="sxs-lookup"><span data-stu-id="f6181-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f6181-104">A `SPLITLIST` függvény a megadott listát allistákká (vagy kötegekké) osztja fel, amelynek mindegyike megadott számú rekordot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="f6181-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="f6181-105">Ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll.</span><span class="sxs-lookup"><span data-stu-id="f6181-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f6181-106">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="f6181-106">Syntax 1</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a><span data-ttu-id="f6181-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="f6181-107">Syntax 2</span></span>

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a><span data-ttu-id="f6181-108">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="f6181-108">Arguments</span></span>

<span data-ttu-id="f6181-109">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="f6181-109">`list`: *Record list*</span></span>

<span data-ttu-id="f6181-110">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="f6181-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="f6181-111">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="f6181-111">`number`: *Integer*</span></span>

<span data-ttu-id="f6181-112">A rekordok maximális száma kötegenként.</span><span class="sxs-lookup"><span data-stu-id="f6181-112">The maximum number of records per batch.</span></span>

<span data-ttu-id="f6181-113">`on-demand reading flag`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="f6181-113">`on-demand reading flag`: *Boolean*</span></span>

<span data-ttu-id="f6181-114">Egy *Logikai* érték, amely meghatározza, hogy az allisták elemeit igény szerint létre kell-e hozni.</span><span class="sxs-lookup"><span data-stu-id="f6181-114">A *Boolean* value that specifies whether elements of sublists should be generated on demand.</span></span>

## <a name="return-values"></a><span data-ttu-id="f6181-115">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="f6181-115">Return values</span></span>

<span data-ttu-id="f6181-116">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="f6181-116">*Record list*</span></span>

<span data-ttu-id="f6181-117">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="f6181-117">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f6181-118">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f6181-118">Usage notes</span></span>

<span data-ttu-id="f6181-119">A visszaadott kötegek listája a következő elemeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="f6181-119">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="f6181-120">**Érték:** *Lista*</span><span class="sxs-lookup"><span data-stu-id="f6181-120">**Value:** *List*</span></span>

    <span data-ttu-id="f6181-121">Az aktuális köteghez tartozó rekordlista.</span><span class="sxs-lookup"><span data-stu-id="f6181-121">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="f6181-122">**BatchNumber:** *Egész*</span><span class="sxs-lookup"><span data-stu-id="f6181-122">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="f6181-123">Az aktuális köteg száma a visszaadott listában.</span><span class="sxs-lookup"><span data-stu-id="f6181-123">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="f6181-124">Ha az igény szerinti olvasási jelző **Igaz** értékre van állítva, kérésre allisták jönnek létre, amelyek lehetővé teszik a memóriafelhasználás csökkentését, de teljesítménycsökkenést okozhatnak, ha az elemeket nem egymás után használják.</span><span class="sxs-lookup"><span data-stu-id="f6181-124">When the on-demand reading flag is set to **True**, sublists are generated upon request which allows for a reduction in memory consumption but may cause performance degradation if elements aren't used sequentially.</span></span>

## <a name="example"></a><span data-ttu-id="f6181-125">Példa</span><span class="sxs-lookup"><span data-stu-id="f6181-125">Example</span></span>

<span data-ttu-id="f6181-126">Az alábbi példában egy **Sorok** adatforrás jön létre rekordlistaként, amely három rekorddal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="f6181-126">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="f6181-127">Ez a kötegekre tételekre oszlik, amelyek mindegyike legfeljebb két rekordot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="f6181-127">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="f6181-128">Az alábbi ábrán a tervezett formátumelrendezés látható.</span><span class="sxs-lookup"><span data-stu-id="f6181-128">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="f6181-129">Ebben a formátumelrendezésben a **Sorok** adatforráshoz kötések jönnek létre a kimenet XML-formátumú előállításához.</span><span class="sxs-lookup"><span data-stu-id="f6181-129">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="f6181-130">Ez a kimenet minden egyes kötethez és a hozzá tartozó rekordokhoz egyedi csomópontokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="f6181-130">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="f6181-131">Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.</span><span class="sxs-lookup"><span data-stu-id="f6181-131">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="f6181-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f6181-132">Additional resources</span></span>

[<span data-ttu-id="f6181-133">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="f6181-133">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

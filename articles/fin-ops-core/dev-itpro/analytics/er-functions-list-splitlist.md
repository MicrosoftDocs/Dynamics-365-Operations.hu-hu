---
title: SPLITLIST ER-függvény
description: A témakör tájékoztatást nyújt a SPLITLIST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: d0f527dcf313a6a5e3b6601cac9a0f6495f66833
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680339"
---
# <a name="splitlist-er-function"></a><span data-ttu-id="1a367-103">SPLITLIST ER-függvény</span><span class="sxs-lookup"><span data-stu-id="1a367-103">SPLITLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a367-104">A `SPLITLIST` függvény a megadott listát allistákká (vagy kötegekké) osztja fel, amelynek mindegyike megadott számú rekordot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1a367-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="1a367-105">Ezt követően az eredményt új *Rekordlista* értékként adja vissza, amely a kötegekből áll.</span><span class="sxs-lookup"><span data-stu-id="1a367-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a367-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="1a367-106">Syntax</span></span>

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="1a367-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="1a367-107">Arguments</span></span>

<span data-ttu-id="1a367-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="1a367-108">`list`: *Record list*</span></span>

<span data-ttu-id="1a367-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="1a367-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="1a367-110">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="1a367-110">`number`: *Integer*</span></span>

<span data-ttu-id="1a367-111">A rekordok maximális száma kötegenként.</span><span class="sxs-lookup"><span data-stu-id="1a367-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="1a367-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="1a367-112">Return values</span></span>

<span data-ttu-id="1a367-113">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="1a367-113">*Record list*</span></span>

<span data-ttu-id="1a367-114">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="1a367-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1a367-115">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1a367-115">Usage notes</span></span>

<span data-ttu-id="1a367-116">A visszaadott kötegek listája a következő elemeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="1a367-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="1a367-117">**Érték:** *Lista*</span><span class="sxs-lookup"><span data-stu-id="1a367-117">**Value:** *List*</span></span>

    <span data-ttu-id="1a367-118">Az aktuális köteghez tartozó rekordlista.</span><span class="sxs-lookup"><span data-stu-id="1a367-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="1a367-119">**BatchNumber:** *Egész*</span><span class="sxs-lookup"><span data-stu-id="1a367-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="1a367-120">Az aktuális köteg száma a visszaadott listában.</span><span class="sxs-lookup"><span data-stu-id="1a367-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="1a367-121">Példa</span><span class="sxs-lookup"><span data-stu-id="1a367-121">Example</span></span>

<span data-ttu-id="1a367-122">Az alábbi példában egy **Sorok** adatforrás jön létre rekordlistaként, amely három rekorddal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="1a367-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="1a367-123">Ez a kötegekre tételekre oszlik, amelyek mindegyike legfeljebb két rekordot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1a367-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="1a367-124">Az alábbi ábrán a tervezett formátumelrendezés látható.</span><span class="sxs-lookup"><span data-stu-id="1a367-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="1a367-125">Ebben a formátumelrendezésben a **Sorok** adatforráshoz kötések jönnek létre a kimenet XML-formátumú előállításához.</span><span class="sxs-lookup"><span data-stu-id="1a367-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="1a367-126">Ez a kimenet minden egyes kötethez és a hozzá tartozó rekordokhoz egyedi csomópontokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1a367-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="1a367-127">Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.</span><span class="sxs-lookup"><span data-stu-id="1a367-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="1a367-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1a367-128">Additional resources</span></span>

[<span data-ttu-id="1a367-129">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="1a367-129">List functions</span></span>](er-functions-category-list.md)

---
title: WHERE ER-függvény
description: A témakör tájékoztatást nyújt a WHERE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 1cc47c5001cf456b1fc600b326f826ea3b8b43ee
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687050"
---
# <a name="where-er-function"></a><span data-ttu-id="cd91c-103">WHERE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="cd91c-103">WHERE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cd91c-104">A `WHERE` függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott feltételek szerint szűrésre került.</span><span class="sxs-lookup"><span data-stu-id="cd91c-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="cd91c-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="cd91c-105">Syntax</span></span>

```vb
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="cd91c-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="cd91c-106">Arguments</span></span>

<span data-ttu-id="cd91c-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="cd91c-107">`list`: *Record list*</span></span>

<span data-ttu-id="cd91c-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="cd91c-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="cd91c-109">`condition`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="cd91c-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="cd91c-110">Érvényes feltételes kifejezés, amely a megadott lista rekordjainak szűrésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="cd91c-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="cd91c-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="cd91c-111">Return values</span></span>

<span data-ttu-id="cd91c-112">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="cd91c-112">*Record list*</span></span>

<span data-ttu-id="cd91c-113">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="cd91c-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cd91c-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cd91c-114">Usage notes</span></span>

<span data-ttu-id="cd91c-115">Ez a függvény eltér a [FILTER](er-functions-list-filter.md) függvénytől, mivel a megadott feltétel a memóriában található összes *Rekordlista* típusú Elektronikus jelentéskészítési (ER) adatforrására alkalmazásra kerül.</span><span class="sxs-lookup"><span data-stu-id="cd91c-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="cd91c-116">Ha a függvényhez konfigurált argumentumok (`list` és `condition`) nem engedélyezi ennek a kérésnek a lefordítását a közvetlen SQL-hívásra, akkor a tervezési időben egy figyelmeztető üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="cd91c-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="cd91c-117">Ez az üzenet arról tájékoztatja a felhasználót, hogy a teljesítmény javulhat, ha a [FILTER](er-functions-list-filter.md) függvényt használja a `WHERE` helyett.</span><span class="sxs-lookup"><span data-stu-id="cd91c-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="cd91c-118">1. példa</span><span class="sxs-lookup"><span data-stu-id="cd91c-118">Example 1</span></span>

<span data-ttu-id="cd91c-119">Ha a **Szállító** a VendTable táblára hivatkozó ER-adatforrásként van konfigurálva, akkor a `WHERE (Vendors, Vendors.VendGroup = "40")` kifejezés csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="cd91c-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="cd91c-120">2. példa</span><span class="sxs-lookup"><span data-stu-id="cd91c-120">Example 2</span></span>

<span data-ttu-id="cd91c-121">Ha megadja a *Számított mező* típusú **DS** adatforrását, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `WHERE( DS, DS.Value = "B")` kifejezés egyetlen rekordból álló listát ad vissza, ami tartalmazza a **„B”** szöveget az **Érték** mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd91c-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cd91c-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cd91c-122">Additional resources</span></span>

[<span data-ttu-id="cd91c-123">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="cd91c-123">List functions</span></span>](er-functions-category-list.md)

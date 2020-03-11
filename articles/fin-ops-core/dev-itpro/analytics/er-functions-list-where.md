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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 392cf7acebd7ad95bcc0f5d4b7a67500a412a795
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041833"
---
# <span data-ttu-id="1d071-103"><a name="WHERE">WHERE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="1d071-103"><a name="WHERE">WHERE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d071-104">A `WHERE` függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott feltételek szerint szűrésre került.</span><span class="sxs-lookup"><span data-stu-id="1d071-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d071-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="1d071-105">Syntax</span></span>

```vb
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="1d071-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="1d071-106">Arguments</span></span>

<span data-ttu-id="1d071-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="1d071-107">`list`: *Record list*</span></span>

<span data-ttu-id="1d071-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="1d071-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="1d071-109">`condition`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="1d071-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="1d071-110">Érvényes feltételes kifejezés, amely a megadott lista rekordjainak szűrésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="1d071-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="1d071-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="1d071-111">Return values</span></span>

<span data-ttu-id="1d071-112">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="1d071-112">*Record list*</span></span>

<span data-ttu-id="1d071-113">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="1d071-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1d071-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1d071-114">Usage notes</span></span>

<span data-ttu-id="1d071-115">Ez a függvény eltér a [FILTER](er-functions-list-filter.md) függvénytől, mivel a megadott feltétel a memóriában található összes *Rekordlista* típusú Elektronikus jelentéskészítési (ER) adatforrására alkalmazásra kerül.</span><span class="sxs-lookup"><span data-stu-id="1d071-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="1d071-116">Ha a függvényhez konfigurált argumentumok (`list` és `condition`) nem engedélyezi ennek a kérésnek a lefordítását a közvetlen SQL-hívásra, akkor a tervezési időben egy figyelmeztető üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1d071-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="1d071-117">Ez az üzenet arról tájékoztatja a felhasználót, hogy a teljesítmény javulhat, ha a [FILTER](er-functions-list-filter.md) függvényt használja a `WHERE` helyett.</span><span class="sxs-lookup"><span data-stu-id="1d071-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="1d071-118">1. példa</span><span class="sxs-lookup"><span data-stu-id="1d071-118">Example 1</span></span>

<span data-ttu-id="1d071-119">Ha a **Szállító** a VendTable táblára hivatkozó ER-adatforrásként van konfigurálva, akkor a `WHERE (Vendors, Vendors.VendGroup = "40")` kifejezés csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="1d071-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="1d071-120">2. példa</span><span class="sxs-lookup"><span data-stu-id="1d071-120">Example 2</span></span>

<span data-ttu-id="1d071-121">Ha megadja a *Számított mező* típusú **DS** adatforrását, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `WHERE( DS, DS.Value = "B")` kifejezés egyetlen rekordból álló listát ad vissza, ami tartalmazza a **„B”** szöveget az **Érték** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1d071-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1d071-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1d071-122">Additional resources</span></span>

[<span data-ttu-id="1d071-123">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="1d071-123">List functions</span></span>](er-functions-category-list.md)

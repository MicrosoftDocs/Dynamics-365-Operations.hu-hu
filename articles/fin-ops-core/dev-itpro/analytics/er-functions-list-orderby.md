---
title: ORDERBY ER-függvény
description: A témakör tájékoztatást nyújt az ORDERBY Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 51da7f3766f5af901c8be6668bc2511cd8e2f9e9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753192"
---
# <a name="orderby-er-function"></a><span data-ttu-id="0e749-103">ORDERBY ER-függvény</span><span class="sxs-lookup"><span data-stu-id="0e749-103">ORDERBY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e749-104">Az `ORDERBY` függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott argumentumok szerint rendezésre került.</span><span class="sxs-lookup"><span data-stu-id="0e749-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="0e749-105">Ezek az argumentumok kifejezésként adhatók meg.</span><span class="sxs-lookup"><span data-stu-id="0e749-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e749-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0e749-106">Syntax</span></span>

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="0e749-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0e749-107">Arguments</span></span>

<span data-ttu-id="0e749-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="0e749-108">`list`: *Record list*</span></span>

<span data-ttu-id="0e749-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="0e749-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="0e749-110">`expression 1`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="0e749-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="0e749-111">Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="0e749-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="0e749-112">A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="0e749-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="0e749-113">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="0e749-113">This argument is required.</span></span>

<span data-ttu-id="0e749-114">`expression N`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="0e749-114">`expression N`: *Field*</span></span>

<span data-ttu-id="0e749-115">Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="0e749-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="0e749-116">A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="0e749-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="0e749-117">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="0e749-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="0e749-118">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="0e749-118">Return values</span></span>

<span data-ttu-id="0e749-119">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="0e749-119">*Record list*</span></span>

<span data-ttu-id="0e749-120">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="0e749-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="0e749-121">1. példa</span><span class="sxs-lookup"><span data-stu-id="0e749-121">Example 1</span></span>

<span data-ttu-id="0e749-122">Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("C|B|A", "|")` kifejezést, akkor a `FIRST( ORDERBY( DS, DS. Value)).Value` kifejezés az **„A”** szöveges értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0e749-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0e749-123">2. példa</span><span class="sxs-lookup"><span data-stu-id="0e749-123">Example 2</span></span>

<span data-ttu-id="0e749-124">Ha **Szállító** a VendTable táblára hivatkozó Elektronikus jelentéskészítési (ER) adatforrásként van konfigurálva, akkor a `ORDERBY (Vendors, Vendors.'name()')` kifejezés megjeleníti a név szerinti növekvő sorrendben rendezett szállítók listáját.</span><span class="sxs-lookup"><span data-stu-id="0e749-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e749-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0e749-125">Additional resources</span></span>

[<span data-ttu-id="0e749-126">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="0e749-126">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
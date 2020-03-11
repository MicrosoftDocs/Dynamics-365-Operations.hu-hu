---
title: ORDERBY ER-függvény
description: A témakör tájékoztatást nyújt az ORDERBY Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 0a6b5cddc325625dc5b3d677ffcc1da1f8b829cd
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041952"
---
# <span data-ttu-id="a2b33-103"><a name="ORDERBY">ORDERBY ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="a2b33-103"><a name="ORDERBY">ORDERBY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2b33-104">Az `ORDERBY` függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott argumentumok szerint rendezésre került.</span><span class="sxs-lookup"><span data-stu-id="a2b33-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="a2b33-105">Ezek az argumentumok kifejezésként adhatók meg.</span><span class="sxs-lookup"><span data-stu-id="a2b33-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2b33-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="a2b33-106">Syntax</span></span>

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="a2b33-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="a2b33-107">Arguments</span></span>

<span data-ttu-id="a2b33-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="a2b33-108">`list`: *Record list*</span></span>

<span data-ttu-id="a2b33-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="a2b33-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a2b33-110">`expression 1`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="a2b33-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="a2b33-111">Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="a2b33-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="a2b33-112">A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a2b33-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="a2b33-113">Az argumentum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="a2b33-113">This argument is required.</span></span>

<span data-ttu-id="a2b33-114">`expression N`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="a2b33-114">`expression N`: *Field*</span></span>

<span data-ttu-id="a2b33-115">Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="a2b33-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="a2b33-116">A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a2b33-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="a2b33-117">Ezek a további argumentumok nem kötelezők.</span><span class="sxs-lookup"><span data-stu-id="a2b33-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="a2b33-118">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="a2b33-118">Return values</span></span>

<span data-ttu-id="a2b33-119">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="a2b33-119">*Record list*</span></span>

<span data-ttu-id="a2b33-120">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="a2b33-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="a2b33-121">1. példa</span><span class="sxs-lookup"><span data-stu-id="a2b33-121">Example 1</span></span>

<span data-ttu-id="a2b33-122">Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("C|B|A", "|")` kifejezést, akkor a `FIRST( ORDERBY( DS, DS. Value)).Value` kifejezés az **„A”** szöveges értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="a2b33-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a2b33-123">2. példa</span><span class="sxs-lookup"><span data-stu-id="a2b33-123">Example 2</span></span>

<span data-ttu-id="a2b33-124">Ha **Szállító** a VendTable táblára hivatkozó Elektronikus jelentéskészítési (ER) adatforrásként van konfigurálva, akkor a `ORDERBY (Vendors, Vendors.'name()')` kifejezés megjeleníti a név szerinti növekvő sorrendben rendezett szállítók listáját.</span><span class="sxs-lookup"><span data-stu-id="a2b33-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2b33-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a2b33-125">Additional resources</span></span>

[<span data-ttu-id="a2b33-126">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="a2b33-126">List functions</span></span>](er-functions-category-list.md)

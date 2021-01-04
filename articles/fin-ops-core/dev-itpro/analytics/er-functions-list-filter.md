---
title: FILTER ER-funkció
description: A témakör tájékoztatást nyújt a FILTER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 55fa3d4ad4427e2a45f7c5fce679c50a91c40b6d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679438"
---
# <a name="filter-er-function"></a><span data-ttu-id="48761-103">FILTER ER-funkció</span><span class="sxs-lookup"><span data-stu-id="48761-103">FILTER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48761-104">A `FILTER` függvény a megadott listát egy *Rekordlista* értékként adja vissza, miután a lekérdezés módosult, és a megadott feltételt szűri.</span><span class="sxs-lookup"><span data-stu-id="48761-104">The `FILTER` function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="48761-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="48761-105">Syntax</span></span>

```vb
FILTER (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="48761-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="48761-106">Arguments</span></span>

<span data-ttu-id="48761-107">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="48761-107">`list`: *Record list*</span></span>

<span data-ttu-id="48761-108">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="48761-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="48761-109">`condition`: *Logikai*</span><span class="sxs-lookup"><span data-stu-id="48761-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="48761-110">Érvényes feltételes kifejezés, amely a megadott lista rekordjainak szűrésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="48761-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="48761-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="48761-111">Return values</span></span>

<span data-ttu-id="48761-112">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="48761-112">*Record list*</span></span>

<span data-ttu-id="48761-113">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="48761-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="48761-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="48761-114">Usage notes</span></span>

<span data-ttu-id="48761-115">Ez a függvény eltér a [WHERE](er-functions-list-where.md) függvénytől, mivel a megadott feltétel az adatbázis szintjén kerül alkalmazásra a *Táblarekordok* típus bármely Elektronikus jelentéskészítés (ER) adatforrására.</span><span class="sxs-lookup"><span data-stu-id="48761-115">This function differs from the [WHERE](er-functions-list-where.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Table records* type at the database level.</span></span> <span data-ttu-id="48761-116">A lista és a feltétel táblák és kapcsolatok segítségével határozhatók meg.</span><span class="sxs-lookup"><span data-stu-id="48761-116">The list and condition can be defined by using tables and relations.</span></span>

<span data-ttu-id="48761-117">Ha a függvényhez konfigurált egyik vagy mindkét argumentum (`list` és `condition`) nem engedélyezi ennek a kérésnek a lefordítását a közvetlen SQL-hívásra, akkor a tervezési időben kivétel történik.</span><span class="sxs-lookup"><span data-stu-id="48761-117">If one or both arguments that are configured for this function (`list` and `condition`) don't allow this request to be translated to the direct SQL call, an exception is thrown at design time.</span></span> <span data-ttu-id="48761-118">Ez a kivétel tájékoztatja a felhasználót, hogy a `list` vagy `condition` nem használható az adatbázis lekérdezéséhez.</span><span class="sxs-lookup"><span data-stu-id="48761-118">This exception informs the user that either `list` or `condition` can't be used to query the database.</span></span>

## <a name="example-1"></a><span data-ttu-id="48761-119">1. példa</span><span class="sxs-lookup"><span data-stu-id="48761-119">Example 1</span></span>

<span data-ttu-id="48761-120">Ha a **Szállító** a VendTable táblára hivatkozó ER-adatforrásként van konfigurálva, akkor a `FILTER (Vendors, Vendors.VendGroup = "40")` kifejezés csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="48761-120">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `FILTER (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="48761-121">2. példa</span><span class="sxs-lookup"><span data-stu-id="48761-121">Example 2</span></span>

<span data-ttu-id="48761-122">Ha a **Szállító** ER-adatforrásként van konfigurálva, amely a VendTable táblára hivatkozik, és ha a **parmVendorBankGroup** ER-adatforrásként van konfigurálva, amely az értéket *Karakterlánc* adattípusként adja vissza, a `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` kifejezés csak az adott bankcsoporthoz tartozó szállítói számlák listáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="48761-122">If **Vendor** is configured as an ER data source that refers to the VendTable table, and if **parmVendorBankGroup** is configured as an ER data source that returns a value of the *String* data type, the expression `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returns a list of only vendor accounts that belong to a specific bank group.</span></span>

## <a name="example-3"></a><span data-ttu-id="48761-123">3. példa</span><span class="sxs-lookup"><span data-stu-id="48761-123">Example 3</span></span>

<span data-ttu-id="48761-124">A **Számított mező** típushoz adja meg a *DS* adatforrást, és az a `SPLIT ("A,B,C", ",")` kifejezést tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="48761-124">You enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A,B,C", ",")`.</span></span> <span data-ttu-id="48761-125">Ezután adjon meg egy másik kifejezést: `FILTER( DS, DS.Value = "B")`.</span><span class="sxs-lookup"><span data-stu-id="48761-125">You then enter another expression, `FILTER( DS, DS.Value = "B")`.</span></span> <span data-ttu-id="48761-126">Amikor megpróbálja menteni ezt a kifejezést az ER-képlettervezőben, a következő kivétel történik: „Érvényesítési hiba: A FILTER függvény listakifejezése nem elérhető.”</span><span class="sxs-lookup"><span data-stu-id="48761-126">When you try to save this expression in the ER formula designer, the following exception is thrown: "Validation error: The list expression of FILTER function is not queryable."</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48761-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="48761-127">Additional resources</span></span>

[<span data-ttu-id="48761-128">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="48761-128">List functions</span></span>](er-functions-category-list.md)

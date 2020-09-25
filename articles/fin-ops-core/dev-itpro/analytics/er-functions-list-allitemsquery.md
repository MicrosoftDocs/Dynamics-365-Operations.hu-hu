---
title: ALLITEMSQUERY ER-függvény
description: A témakör tájékoztatást nyújt az ALLITEMSQUERY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 37546fccf804a4522638147d39206997e8c0c24c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745369"
---
# <a name="allitemsquery-er-function"></a><span data-ttu-id="37728-103">ALLITEMSQUERY ER-függvény</span><span class="sxs-lookup"><span data-stu-id="37728-103">ALLITEMSQUERY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37728-104">Az `ALLITEMSQUERY` függvény illesztett SQL-lekérdezésként fut.</span><span class="sxs-lookup"><span data-stu-id="37728-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="37728-105">Egy új, összevont *Rekordlista* értéket ad vissza, amely rekordok olyan listájából áll, amely a megadott útvonalnak megfelelő minden rekordot képvisel.</span><span class="sxs-lookup"><span data-stu-id="37728-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="37728-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="37728-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="37728-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="37728-107">Arguments</span></span>

<span data-ttu-id="37728-108">`path`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="37728-108">`path`: *Record list*</span></span>

<span data-ttu-id="37728-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="37728-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="37728-110">Legalább egy objektumkapcsolatot kell tartalmaznia.</span><span class="sxs-lookup"><span data-stu-id="37728-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="37728-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="37728-111">Return values</span></span>

<span data-ttu-id="37728-112">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="37728-112">*Record list*</span></span>

<span data-ttu-id="37728-113">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="37728-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="37728-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="37728-114">Usage notes</span></span>

<span data-ttu-id="37728-115">A megadott elérési utat egy érvényes adatforrás útvonalaként kell megadni a *Rekordlista* adattípus adatforrásához.</span><span class="sxs-lookup"><span data-stu-id="37728-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="37728-116">Legalább egy objektumkapcsolatot is kell tartalmaznia.</span><span class="sxs-lookup"><span data-stu-id="37728-116">It must also contain at least one relation.</span></span> <span data-ttu-id="37728-117">Adatelemek (például az elérési út *Karakterlánc* és *Dátum* eleme) hibaüzenetet jelenítenek meg az Elektronikus jelentéskészítés (ER) kifejezésszerkesztőben tervezéskor.</span><span class="sxs-lookup"><span data-stu-id="37728-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="37728-118">Ha ez a függvény olyan *Rekordlista* típusú adatforrásokon kerül alkalmazásra, amelyek olyan alkalmazásobjektumra hivatkoznak, amely az SQL használatával közvetlenül hívható (például tábla, entitás vagy lekérdezés), akkor illesztett SQL-lekérdezésként fut.</span><span class="sxs-lookup"><span data-stu-id="37728-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="37728-119">Ellenkező esetben a memóriában fut, mint az [ALLITEMS](er-functions-list-allitems.md) függvény.</span><span class="sxs-lookup"><span data-stu-id="37728-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="37728-120">Példa</span><span class="sxs-lookup"><span data-stu-id="37728-120">Example</span></span>

<span data-ttu-id="37728-121">A következő adatforrás megadása a modell-hozzárendelésben:</span><span class="sxs-lookup"><span data-stu-id="37728-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="37728-122">A *Táblarekordok* típus **CustInv** adatforrása, amely a CustInvoiceTable táblára hivatkozik</span><span class="sxs-lookup"><span data-stu-id="37728-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="37728-123">A *Számított mező* típus **FilteredInv** adatforrása, amely a `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")` kifejezést tartalmazza</span><span class="sxs-lookup"><span data-stu-id="37728-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="37728-124">A *Számított mező* típus **JourLines** adatforrása, amely a `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)` kifejezést tartalmazza</span><span class="sxs-lookup"><span data-stu-id="37728-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="37728-125">A modell-leképezés futtatásakor a **JourLines** adatforrás meghívásához a következő SQL-utasítás kerül futtatásra:</span><span class="sxs-lookup"><span data-stu-id="37728-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="37728-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="37728-126">Additional resources</span></span>

[<span data-ttu-id="37728-127">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="37728-127">List functions</span></span>](er-functions-category-list.md)

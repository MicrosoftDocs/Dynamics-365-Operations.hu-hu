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
ms.openlocfilehash: 99f2aa9863e36a2f2eb1db5d0569d2a82402969a
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070644"
---
# <span data-ttu-id="3d141-103"><a name="ALLITEMSQUERY">ALLITEMSQUERY ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="3d141-103"><a name="ALLITEMSQUERY">ALLITEMSQUERY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d141-104">Az `ALLITEMSQUERY` függvény illesztett SQL-lekérdezésként fut.</span><span class="sxs-lookup"><span data-stu-id="3d141-104">The `ALLITEMSQUERY` function runs as a joined SQL query.</span></span> <span data-ttu-id="3d141-105">Egy új, összevont *Rekordlista* értéket ad vissza, amely rekordok olyan listájából áll, amely a megadott útvonalnak megfelelő minden rekordot képvisel.</span><span class="sxs-lookup"><span data-stu-id="3d141-105">It returns a new flattened *Record list* value that consists of a list of records that represent all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="3d141-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="3d141-106">Syntax</span></span>

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a><span data-ttu-id="3d141-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="3d141-107">Arguments</span></span>

<span data-ttu-id="3d141-108">`path`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="3d141-108">`path`: *Record list*</span></span>

<span data-ttu-id="3d141-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="3d141-109">The valid path of a data source of the *Record list* data type.</span></span> <span data-ttu-id="3d141-110">Legalább egy objektumkapcsolatot kell tartalmaznia.</span><span class="sxs-lookup"><span data-stu-id="3d141-110">It must contain at least one relation.</span></span>

## <a name="return-values"></a><span data-ttu-id="3d141-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="3d141-111">Return values</span></span>

<span data-ttu-id="3d141-112">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="3d141-112">*Record list*</span></span>

<span data-ttu-id="3d141-113">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="3d141-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3d141-114">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="3d141-114">Usage notes</span></span>

<span data-ttu-id="3d141-115">A megadott elérési utat egy érvényes adatforrás útvonalaként kell megadni a *Rekordlista* adattípus adatforrásához.</span><span class="sxs-lookup"><span data-stu-id="3d141-115">The specified path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="3d141-116">Legalább egy objektumkapcsolatot is kell tartalmaznia.</span><span class="sxs-lookup"><span data-stu-id="3d141-116">It must also contain at least one relation.</span></span> <span data-ttu-id="3d141-117">Adatelemek (például az elérési út *Karakterlánc* és *Dátum* eleme) hibaüzenetet jelenítenek meg az Elektronikus jelentéskészítés (ER) kifejezésszerkesztőben tervezéskor.</span><span class="sxs-lookup"><span data-stu-id="3d141-117">Data elements such as the path *String* and *Date* should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="3d141-118">Ha ez a függvény olyan *Rekordlista* típusú adatforrásokon kerül alkalmazásra, amelyek olyan alkalmazásobjektumra hivatkoznak, amely az SQL használatával közvetlenül hívható (például tábla, entitás vagy lekérdezés), akkor illesztett SQL-lekérdezésként fut.</span><span class="sxs-lookup"><span data-stu-id="3d141-118">When this function is applied to data sources of the *Record list* data type that refer to an application object that can be directly called by using SQL (for example, an table, entity, or query), it runs as a joined SQL query.</span></span> <span data-ttu-id="3d141-119">Ellenkező esetben a memóriában fut, mint az [ALLITEMS](er-functions-list-allitems.md) függvény.</span><span class="sxs-lookup"><span data-stu-id="3d141-119">Otherwise, it runs in memory as the [ALLITEMS](er-functions-list-allitems.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="3d141-120">Példa</span><span class="sxs-lookup"><span data-stu-id="3d141-120">Example</span></span>

<span data-ttu-id="3d141-121">A következő adatforrás megadása a modell-hozzárendelésben:</span><span class="sxs-lookup"><span data-stu-id="3d141-121">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="3d141-122">A *Táblarekordok* típus **CustInv** adatforrása, amely a CustInvoiceTable táblára hivatkozik</span><span class="sxs-lookup"><span data-stu-id="3d141-122">A **CustInv** data source of the *Table records* type that refers to the CustInvoiceTable table</span></span>
- <span data-ttu-id="3d141-123">A *Számított mező* típus **FilteredInv** adatforrása, amely a `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")` kifejezést tartalmazza</span><span class="sxs-lookup"><span data-stu-id="3d141-123">A **FilteredInv** data source of the *Calculated field* type that contains the expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`</span></span>
- <span data-ttu-id="3d141-124">A *Számított mező* típus **JourLines** adatforrása, amely a `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)` kifejezést tartalmazza</span><span class="sxs-lookup"><span data-stu-id="3d141-124">A **JourLines** of the *Calculated field* type that contains the expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`</span></span>

<span data-ttu-id="3d141-125">A modell-leképezés futtatásakor a **JourLines** adatforrás meghívásához a következő SQL-utasítás kerül futtatásra:</span><span class="sxs-lookup"><span data-stu-id="3d141-125">When you run the model mapping to call the **JourLines** data source, the following SQL statement is run:</span></span>

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a><span data-ttu-id="3d141-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3d141-126">Additional resources</span></span>

[<span data-ttu-id="3d141-127">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="3d141-127">List functions</span></span>](er-functions-category-list.md)

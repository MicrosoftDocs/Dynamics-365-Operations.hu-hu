---
title: LISTDISTINCT ER funkció
description: A témakör tájékoztatást nyújt arról, hogy hogyan kell használni a LISTDISTINCT Elektronikus jelentéskészítés (ER) funkciót.
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: f20565d73cea8d0cc1361bd03cda86a79a97955e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563824"
---
# <a name="listdistinct-er-function"></a><span data-ttu-id="8f7f1-103">LISTDISTINCT ER funkció</span><span class="sxs-lookup"><span data-stu-id="8f7f1-103">LISTDISTINCT ER Function</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="8f7f1-104">A `LISTDISTINCT` funkció kiszámítja a meghatározott kifejezések értékét, mint egy megadott lista minden rekordjához hozzárendelt választó.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-104">The `LISTDISTINCT` function calculates the specified expression as a selector for every record of the specified list.</span></span> <span data-ttu-id="8f7f1-105">Ez visszaállít egy új *Rekordlista* értéket, amely egyetlen rekordot tartalmaz minden egyedi választóértékhez.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-105">It returns a new *Record list* value that contains a single record for each unique selector value.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f7f1-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="8f7f1-106">Syntax</span></span>

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a><span data-ttu-id="8f7f1-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="8f7f1-107">Arguments</span></span>

<span data-ttu-id="8f7f1-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="8f7f1-108">`list`: *Record list*</span></span>

<span data-ttu-id="8f7f1-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="8f7f1-110">`selector`: *Primitív adattípus*</span><span class="sxs-lookup"><span data-stu-id="8f7f1-110">`selector`: *Primitive data type*</span></span>

<span data-ttu-id="8f7f1-111">Egy érvényes kifejezés, amely egy választóérték kiszámítására szolgál minden rekordhoz egy megadott listában.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-111">A valid expression that is used to calculate a selector value for every record in the specified list.</span></span>

<span data-ttu-id="8f7f1-112">A következő adattípusok támogatottak ehhez a paraméterhez:</span><span class="sxs-lookup"><span data-stu-id="8f7f1-112">The following data types are supported for this parameter:</span></span>

- <span data-ttu-id="8f7f1-113">Logikai</span><span class="sxs-lookup"><span data-stu-id="8f7f1-113">Boolean</span></span>
- <span data-ttu-id="8f7f1-114">Dátum</span><span class="sxs-lookup"><span data-stu-id="8f7f1-114">Date</span></span>
- <span data-ttu-id="8f7f1-115">DateTime</span><span class="sxs-lookup"><span data-stu-id="8f7f1-115">DateTime</span></span>
- <span data-ttu-id="8f7f1-116">GUID azonosító</span><span class="sxs-lookup"><span data-stu-id="8f7f1-116">GUID</span></span>
- <span data-ttu-id="8f7f1-117">Egész</span><span class="sxs-lookup"><span data-stu-id="8f7f1-117">Integer</span></span>
- <span data-ttu-id="8f7f1-118">Int64</span><span class="sxs-lookup"><span data-stu-id="8f7f1-118">Int64</span></span>
- <span data-ttu-id="8f7f1-119">Valós</span><span class="sxs-lookup"><span data-stu-id="8f7f1-119">Real</span></span>
- <span data-ttu-id="8f7f1-120">Karakterlánc</span><span class="sxs-lookup"><span data-stu-id="8f7f1-120">String</span></span>

## <a name="return-values"></a><span data-ttu-id="8f7f1-121">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="8f7f1-121">Return values</span></span>

<span data-ttu-id="8f7f1-122">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="8f7f1-122">*Record list*</span></span>

<span data-ttu-id="8f7f1-123">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-123">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8f7f1-124">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8f7f1-124">Usage notes</span></span>

<span data-ttu-id="8f7f1-125">A létrehozott lista szerkezete egyezik a megadott lista struktúrájával.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-125">The structure of the list that is created matches the structure of the specified list.</span></span>

<span data-ttu-id="8f7f1-126">A megadott listában ugyanaz a választóérték kiszámítható több rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-126">The same selector value might be calculated for multiple records in the specified list.</span></span> <span data-ttu-id="8f7f1-127">Ebben az esetben a megfelelő rekord mezőértékei a létrehozott listában megegyeznek az első rekord értékével a megadott listából, amit a választóérték kiszámításra került.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-127">In this case, field values of the corresponding record in the created list equal the values of the first record from the specified list that the selector value is calculated for.</span></span>

<span data-ttu-id="8f7f1-128">Ennek a funkciónak bármely [Elektronikus jelentéskészítés (ER)](general-electronic-reporting.md) *Rekordlista* típusú adatforrása végrehajtásra kerül, a memória által.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-128">The execution of this function is done on any [Electronic reporting (ER)](general-electronic-reporting.md) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="8f7f1-129">Az a **GROUPBY** adatforrás használható fel rekordok listájának előállítására is, amely egyedi értékű választóértékkel számol.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-129">The **GROUPBY** data source can also be used to generate the list of records that the selector that has distinct values is calculated for.</span></span> <span data-ttu-id="8f7f1-130">Azonban a teljesítmény és a memóriahasználat szempontjából jobban ajánlott a `LISTDISTINCT` funkció a **GROUPBY** adatforrásnál, mivel a funkció végrehajtása a memóriában történik.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-130">However, from a performance and memory consumption perspective, it's better to use the `LISTDISTINCT` function than the **GROUPBY** data source, because the execution of the function is done in memory.</span></span>

## <a name="example"></a><span data-ttu-id="8f7f1-131">Példa</span><span class="sxs-lookup"><span data-stu-id="8f7f1-131">Example</span></span>

<span data-ttu-id="8f7f1-132">A következő példa azt mutatja be, hogyan lehet lekérni azokat az egyedi vevői számlaszámú listákat, amelyek legalább egy értékesítési számlát vagy egy projekt számlát bocsátottak ki egy adott időszakban.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-132">The following example shows how you can get the list of unique customer account numbers that at least one sales invoice or project invoice has been issued to during a specific period.</span></span>

1. <span data-ttu-id="8f7f1-133">Adja meg azt a **SalesInvoice** adatforrást a `Record list` típusból, amely a **CustInvoiceJour** alkalmazástáblára hivatkozik, és szűri az egyes időszakok értékesítési számláit.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-133">Enter the **SalesInvoice** data source of the `Record list` type that refers to the **CustInvoiceJour** application table and filters sales invoices for specific periods.</span></span>

    <span data-ttu-id="8f7f1-134">Az `InvoiceAccount` mezője ebből az adatforrásból téríti vissza egy számlázott vevő számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-134">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

2. <span data-ttu-id="8f7f1-135">Adja meg azt a **ProjectInvoice** adatforrást a `Record list` típusból, amely a **ProjInvoiceJour** alkalmazástáblára hivatkozik, és szűri az egyes időszakok értékesítési számláit.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-135">Enter the **ProjectInvoice** data source of the `Record list` type that refers to the **ProjInvoiceJour** application table and filters project invoices for specific periods.</span></span>

    <span data-ttu-id="8f7f1-136">Az `InvoiceAccount` mezője ebből az adatforrásból téríti vissza egy számlázott vevő számlaszámát.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-136">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

3. <span data-ttu-id="8f7f1-137">Adja meg az  **AllInvoices** adatforrást a `Calculated field` típusból, ami a kifejezést tartalmazza `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-137">Configure the **AllInvoices** data source of the `Calculated field` type that contains the expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span></span>

    <span data-ttu-id="8f7f1-138">Ez az adatforrás téríti vissza az értékesítési számlák és a projekt-számlák összekapcsolt listáját.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-138">This data source returns the joined list of sales invoices and project invoices.</span></span>

4. <span data-ttu-id="8f7f1-139">Adja meg az  **InvoicedCustomer** adatforrást a `Record list` típusból, ami a kifejezést tartalmazza `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-139">Configure the **InvoicedCustomer** data source of the `Record list` type that contains the expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span></span>

    <span data-ttu-id="8f7f1-140">Ez az adatforrás egy új listát térít vissza, amely egyetlen rekordot tartalmaz minden olyan egyedi vevőnek, aki a megadott időszakban számlázva lett.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-140">This data source returns a new list that contains a single record for every unique customer that has been invoiced during the defined period.</span></span> <span data-ttu-id="8f7f1-141">A `InvoiceAccount` mezője erről a listáról tartalmaz egy vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="8f7f1-141">The `InvoiceAccount` field of this list contains a customer account number.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f7f1-142">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8f7f1-142">Additional resources</span></span>

[<span data-ttu-id="8f7f1-143">Listafüggvények</span><span class="sxs-lookup"><span data-stu-id="8f7f1-143">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
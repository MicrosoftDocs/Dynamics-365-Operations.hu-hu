---
title: Áfameghatározás főkönyvi tranzakció jelentésenként
description: Ez a témakör azt mutatja be, hogyan lehet a főkönyvi tranzakció jelentés alapján az ÁFA-specifikációt az ÁFA kiszámításához használt főkönyvi tranzakciókra vonatkozó adatok megjelenítésére és kinyomtatására használni.
author: ericwang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 75913edcbac0151d5d27d866ff5430b194c62738
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815260"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a><span data-ttu-id="27aa2-103">Áfameghatározás főkönyvi tranzakció jelentésenként</span><span class="sxs-lookup"><span data-stu-id="27aa2-103">Sales tax specification by ledger transaction report</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="27aa2-104">Ez a témakör azt mutatja be, hogyan lehet a **főkönyvi tranzakció jelentés alapján az ÁFA-specifikációt** az ÁFA kiszámításához használt főkönyvi tranzakciókra vonatkozó adatok megjelenítésére és kinyomtatására használni.</span><span class="sxs-lookup"><span data-stu-id="27aa2-104">This topic explains how to use the **Sales tax specification by ledger transaction** report to view and print information about ledger transactions that sales tax is calculated for.</span></span>

## <a name="tax-accounts-vs-non-tax-accounts"></a><span data-ttu-id="27aa2-105">Adóügyi és nem adóügyi számlák</span><span class="sxs-lookup"><span data-stu-id="27aa2-105">Tax accounts vs. non-tax accounts</span></span>

<span data-ttu-id="27aa2-106">A **főkönyvi tranzakció jelentés szerinti ÁFA-meghatározás** mind az adóügyi, mind a nem adóügyi számlákra vonatkozó adózási tranzakciókat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="27aa2-106">The **Sales tax specification by ledger transaction** report shows tax transactions for both tax accounts and non-tax accounts.</span></span> <span data-ttu-id="27aa2-107">Ezeket a számlákat a következő módon sorolják be:</span><span class="sxs-lookup"><span data-stu-id="27aa2-107">These accounts are categorized in the following way:</span></span>

- <span data-ttu-id="27aa2-108">**Adóügyi számla** – A számlát adóügyi számlának kell tekinteni, amikor egy adózási tranzakció fel van adva, és az **áfakód** sorában a fő számla egy adóügyi számla, például egy fizetendő forgalmiadó-számla vagy egy visszaigényelhető forgalmiadó számla.</span><span class="sxs-lookup"><span data-stu-id="27aa2-108">**Tax account** – An account is considered a tax account when a tax transaction is posted, and the main account on the **Sales Tax** journal line is a tax account, such as a sales tax payable account or a sales tax receivable account.</span></span>
- <span data-ttu-id="27aa2-109">**Nem adóügyi számla** – A számlát nem adóügyi számlának kell tekinteni, amikor egy adózási tranzakció fel van adva, és az eredeti tranzakció fő számlája nem adóügyi számla, például egy forgalmi számla vagy egy költségszámla.</span><span class="sxs-lookup"><span data-stu-id="27aa2-109">**Non-tax account** – An account is considered a non-tax account when a tax transaction is posted, and the main account on the original transaction is a non-tax account, such as a revenue account or an expense account.</span></span>

<span data-ttu-id="27aa2-110">Az adóbevallások esetében a jelentés **Eredet**, **Visszaigényelhető áfa** és **Fizetendő áfa** oszlopa **0** (nulla).</span><span class="sxs-lookup"><span data-stu-id="27aa2-110">For tax accounts, the **Origin**, **Sales tax receivable**, and **Sales tax payable** columns on the report show **0** (zero).</span></span> <span data-ttu-id="27aa2-111">A nem adóügyi számláknál az oszlopok összegeket jelenítenek meg.</span><span class="sxs-lookup"><span data-stu-id="27aa2-111">For non-tax accounts, those columns show amounts.</span></span>

## <a name="filtering-the-data-on-the-report"></a><span data-ttu-id="27aa2-112">A jelentésen látható adatok szűrése</span><span class="sxs-lookup"><span data-stu-id="27aa2-112">Filtering the data on the report</span></span>

<span data-ttu-id="27aa2-113">Ennek a jelentésnek a létrehozásakor a következő alapértelmezett mezők állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="27aa2-113">When you generate the report, the following default fields are available.</span></span> <span data-ttu-id="27aa2-114">Ezekkel a mezőkkel szűrheti a jelentésben megjelenített adatokat.</span><span class="sxs-lookup"><span data-stu-id="27aa2-114">You can use these fields to filter the data that is shown on the report.</span></span>

| <span data-ttu-id="27aa2-115">Mező</span><span class="sxs-lookup"><span data-stu-id="27aa2-115">Field</span></span>                      | <span data-ttu-id="27aa2-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="27aa2-116">Description</span></span> |
|----------------------------|-------------|
| <span data-ttu-id="27aa2-117">Dátum</span><span class="sxs-lookup"><span data-stu-id="27aa2-117">Date</span></span>                       | <span data-ttu-id="27aa2-118">A **Kezdő** és a **Záró** szakasz mezőivel meghatározhatja az adózási tranzakciók dátumtartományát.</span><span class="sxs-lookup"><span data-stu-id="27aa2-118">Use the fields in the **From** and **To** sections to define a date range for the tax transactions.</span></span> |
| <span data-ttu-id="27aa2-119">Fő számla</span><span class="sxs-lookup"><span data-stu-id="27aa2-119">Main account</span></span>               | <span data-ttu-id="27aa2-120">A **Kezdő** és a **Záró** szakasz mezőivel meghatározhatja a fő számlák tartományát.</span><span class="sxs-lookup"><span data-stu-id="27aa2-120">Use the fields in the **From** and **To** sections to define a range of main accounts.</span></span> |
| <span data-ttu-id="27aa2-121">Áfakód</span><span class="sxs-lookup"><span data-stu-id="27aa2-121">Sales tax code</span></span>             | <span data-ttu-id="27aa2-122">A **Kezdő** és a **Záró** szakasz mezőivel meghatározhatja az áfakódok tartományát.</span><span class="sxs-lookup"><span data-stu-id="27aa2-122">Use the fields in the **From** and **To** sections to define a range of sales tax codes.</span></span> |
| <span data-ttu-id="27aa2-123">Csoportosítás</span><span class="sxs-lookup"><span data-stu-id="27aa2-123">Grouping</span></span>                   | <span data-ttu-id="27aa2-124">Annak megadása, hogy a jelentést főkönyvi számla vagy áfakód szerint kell csoportosítani.</span><span class="sxs-lookup"><span data-stu-id="27aa2-124">Select whether the report should be grouped by ledger account or sales tax code.</span></span> |
| <span data-ttu-id="27aa2-125">Részösszeg áfakód szerint</span><span class="sxs-lookup"><span data-stu-id="27aa2-125">Subtotal by sales tax code</span></span> | <span data-ttu-id="27aa2-126">Ez a beállítás **Igen** értékre állítható a részösszegek áfakód szerinti megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="27aa2-126">Set this option to **Yes** to show subtotals by sales tax code.</span></span> |
| <span data-ttu-id="27aa2-127">Csak összegek</span><span class="sxs-lookup"><span data-stu-id="27aa2-127">Totals only</span></span>                | <span data-ttu-id="27aa2-128">Az **Igen** értékre állítása esetén csak az összesítések jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="27aa2-128">Set this option to **Yes** to show only totals.</span></span> |
| <span data-ttu-id="27aa2-129">Csak a fő számlák</span><span class="sxs-lookup"><span data-stu-id="27aa2-129">Main accounts only</span></span>         | <span data-ttu-id="27aa2-130">Ezt a beállítást **Igen** értékre állítva a jelentésben csak a fő számlák szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="27aa2-130">Set this option to **Yes** to include only main accounts on the report.</span></span> |

## <a name="showing-only-non-tax-accounts-on-the-report"></a><span data-ttu-id="27aa2-131">Csak a nem adóügyi számlák megjelenítése a jelentésben</span><span class="sxs-lookup"><span data-stu-id="27aa2-131">Showing only non-tax accounts on the report</span></span>

<span data-ttu-id="27aa2-132">Ha csak a nem adóügyi számlákat szeretné megjeleníteni a jelentésben, állítsa be a szűrési feltételt, például csillag (\*), ahogy az a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="27aa2-132">To show only non-tax accounts on the report, set up a filter condition, such as an asterisk (\*), as shown in the following illustration.</span></span>

![Nem adóügyi számlákat mutató jelentés](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
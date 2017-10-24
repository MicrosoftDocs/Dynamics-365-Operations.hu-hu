---
title: "Könyvelések áttekintése"
description: "A cikk leírást ad a könyveléseket illetően és információt biztosít azok beállításairól és a tranzakciók létrehozásáról."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fb120715090638bf7c6c3833822d942cb6dda8c5
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="accruals-overview"></a><span data-ttu-id="be42d-103">Könyvelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="be42d-103">Accruals overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="be42d-104">A cikk leírást ad a könyveléseket illetően és információt biztosít azok beállításairól és a tranzakciók létrehozásáról.</span><span class="sxs-lookup"><span data-stu-id="be42d-104">This article describes accruals, and provides information about how to set them up and create transactions.</span></span>

<span data-ttu-id="be42d-105">Könyvelések az elhatárolásban használtak, az olyan bevétel követésére, amelyet a megkeresési időszakban ismertek fel, nem a bevételezési időszakhoz, és kiadások (költségek) követésére, amelyeket akkor ismertek fel, amikor megjelentek, nem amikor a fizetés megtörtént.</span><span class="sxs-lookup"><span data-stu-id="be42d-105">Accruals are used in accrual accounting to track revenue that is recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.</span></span>

## <a name="accrual-schemes"></a><span data-ttu-id="be42d-106">Könyvelési sémák</span><span class="sxs-lookup"><span data-stu-id="be42d-106">Accrual schemes</span></span>
<span data-ttu-id="be42d-107">Könyvelési sémák a halasztott bevételek és költségek beállítására szolgálnak, és ugyanaz a könyvelési séma használható bevételekre és a költségekre is.</span><span class="sxs-lookup"><span data-stu-id="be42d-107">Accrual schemes are used to set up the deferred revenue and costs, and the same accrual scheme can be used for both revenue and costs.</span></span> <span data-ttu-id="be42d-108">A főkönyvi könyvelések során újra elosztják a naplósorok költségeit és a bevételt, hogy a költségek és bevételek a megfelelő időszakban legyenek elismerve.</span><span class="sxs-lookup"><span data-stu-id="be42d-108">Ledger accruals redistribute the costs or revenue of a journal line so that the costs and revenues are recognized in the appropriate periods.</span></span> <span data-ttu-id="be42d-109">Az a **Könyvelési séma** lapon megadhatja, a terhelési és a követel számlákat, amelyek a könyvelési séma alkalmazásakor használandóak.</span><span class="sxs-lookup"><span data-stu-id="be42d-109">On the **Accrual scheme** page, you specify the debit and the credit accounts that will be used when the accrual scheme is applied.</span></span>

-   <span data-ttu-id="be42d-110">**Terhelés** – A fő számla, amelyet megad lecseréli a terhelési fő számlát a naplóbizonylat soron.</span><span class="sxs-lookup"><span data-stu-id="be42d-110">**Debit** – The main account that you define will replace the debit main account on the journal voucher line.</span></span> <span data-ttu-id="be42d-111">A sztornírozás halasztására ez a számla lesz használva, a főkönyvi könyvelési tranzakciók alapján.</span><span class="sxs-lookup"><span data-stu-id="be42d-111">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>
-   <span data-ttu-id="be42d-112">**Követelés** – a fő számla, amelyet megad lecseréli a követelési fő számlát a naplóbizonylat soron.</span><span class="sxs-lookup"><span data-stu-id="be42d-112">**Credit** – the main account that you define will replace the credit main account on the journal voucher line.</span></span> <span data-ttu-id="be42d-113">A sztornírozás halasztására ez a számla lesz használva, a főkönyvi könyvelési tranzakciók alapján.</span><span class="sxs-lookup"><span data-stu-id="be42d-113">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>

<span data-ttu-id="be42d-114">Miután meghatározhatja, hogy milyen számlákat használjon, megadhatja, hogyan jöjjön létre a bizonylatszám, a könyvelési tranzakciók létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="be42d-114">After you determine which accounts to use, you can specify how the voucher number is created when accrual transactions are created.</span></span> <span data-ttu-id="be42d-115">Ezen kívül megadhatja, hogy milyen gyakran fordulnak elő a tranzakciók, a tranzakciók létrehozásának számát, és a tranzakciók feladásának számát.</span><span class="sxs-lookup"><span data-stu-id="be42d-115">You can also specify how often the transactions occur, the number of times that the transactions are created, and when the transactions are posted.</span></span> <span data-ttu-id="be42d-116">A könyvelési séma létrehozása után használhatja azt egyes naplókban, a Főkönyvi könyvelések funkció használatával.</span><span class="sxs-lookup"><span data-stu-id="be42d-116">After the accrual scheme has been created, you can use it in some of the journals by using the Ledger accruals function.</span></span>

## <a name="ledger-accruals"></a><span data-ttu-id="be42d-117">Főkönyvi könyvelések</span><span class="sxs-lookup"><span data-stu-id="be42d-117">Ledger accruals</span></span>
<span data-ttu-id="be42d-118">Amikor beír egy naplót, kattintson **Főkönyvi könyvelések** a **Funkciók** menüben.</span><span class="sxs-lookup"><span data-stu-id="be42d-118">When you enter a journal, you can click **Ledger accruals** on the **Functions** menu.</span></span> <span data-ttu-id="be42d-119">Ezután a könyvelési séma kiválasztásakor megjelenik az alapösszeg, a könyvelési séma által meghatározott időszakban terjedő naplóból.</span><span class="sxs-lookup"><span data-stu-id="be42d-119">Then, when you select the accrual scheme, you will see the base amount from the journal that will be spread over the period, as determined by the accrual scheme.</span></span> <span data-ttu-id="be42d-120">Például ha januárban az egész évre kifizeti az alkalmazott biztosítását, és az összeg 12 000, a költséget minden hónapban realizálni kell.</span><span class="sxs-lookup"><span data-stu-id="be42d-120">For example, if you pay an employee's insurance for the whole year in January, and the amount is 12,000, you must recognize that expense each month.</span></span> <span data-ttu-id="be42d-121">A kezdő dátumot kiválaszthatja.</span><span class="sxs-lookup"><span data-stu-id="be42d-121">You can select the start date.</span></span> <span data-ttu-id="be42d-122">Megadhatja azt is, hogy számla vagy az ellenszámla a könyvelt összeg alapja.</span><span class="sxs-lookup"><span data-stu-id="be42d-122">You can also specify whether the amount that is accrued is based on the account or the offset account.</span></span> <span data-ttu-id="be42d-123">Miután végrehajtotta a kívánt beállításokat, kattintson a **Tranzakciók** elemre a könyvelési séma alapján létrehozott összes tranzakció megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="be42d-123">After you make your selections, click **Transactions** to view all the transactions that have been created based on the accrual scheme.</span></span> <span data-ttu-id="be42d-124">Például ha a 12 000-et biztosítási költségként osztotta el az év folyamán, minden hónapnál 1000 jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="be42d-124">For example, if you spread the 12,000 in insurance expenses over the year, you will see 1,000 for each month.</span></span> <span data-ttu-id="be42d-125">A napló feladása után a tranzakciók megtekintéséhez használja a **Bizonylattranzakciók** lekérdezési oldalt.</span><span class="sxs-lookup"><span data-stu-id="be42d-125">After you post the journal, you can view the transactions by using the **Voucher transactions** inquiry page.</span></span> <span data-ttu-id="be42d-126">Ha nem lehet használni a könyvelési sémát (például egy értékesítési rendelési számla vagy a beszerzési rendelési számla érintett), jóváírhatja az előre fizetett összeget és terhelheti a költségösszeget.</span><span class="sxs-lookup"><span data-stu-id="be42d-126">If an accrual scheme can't be applied (for example, when a sales order invoice or purchase order invoice is involved), you can credit the prepaid amount and debit the expense amount.</span></span> <span data-ttu-id="be42d-127">Ezután kiválaszthatja az **Ellenszámla** lehetőséget a könyvelési séma alkalmazásakor.</span><span class="sxs-lookup"><span data-stu-id="be42d-127">You can then select **Offset** when you apply the accrual scheme.</span></span>


<span data-ttu-id="be42d-128">További tudnivalókért lásd: [Könyvelési sémák létrehozása](tasks/create-accrual-schemes.md) és [Főkönyvi könyvelés tranzakcióinak létrehozása](tasks/create-ledger-accrual-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="be42d-128">For more information, see [Create accrual schemes](tasks/create-accrual-schemes.md) and [Create ledger accrual transactions](tasks/create-ledger-accrual-transactions.md).</span></span>


---
title: Feladásdefiníció-példák
description: Ez a cikk arra tartalmaz példákat, hogyan használatosak feladásdefiníciók beszerzési rendelések terheléséhez és költségvetési előirányzatokhoz.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 301f15f1d7d8f0e10bbaf2546fcf727aff284624
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443864"
---
# <a name="posting-definition-examples"></a><span data-ttu-id="2a7de-103">Példák feladásdefiníciókra</span><span class="sxs-lookup"><span data-stu-id="2a7de-103">Posting definition examples</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a7de-104">Ez a cikk arra tartalmaz példákat, hogyan használatosak feladásdefiníciók beszerzési rendelések terheléséhez és költségvetési előirányzatokhoz.</span><span class="sxs-lookup"><span data-stu-id="2a7de-104">This article provides examples that show how posting definitions are used for purchase order encumbrances and budget appropriations.</span></span>

<span data-ttu-id="2a7de-105">Mielőtt ezt a témakört elolvassa, a feladási definíciókkal és a tranzakciós feladási feladási definíciókkal tisztában kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2a7de-105">Before you read this topic, you should be familiar with posting definitions and transaction posting definitions.</span></span> <span data-ttu-id="2a7de-106">Információ: lásd a [Feladási definíciók](posting-definitions.md) részt.</span><span class="sxs-lookup"><span data-stu-id="2a7de-106">For information, see [Posting definitions](posting-definitions.md).</span></span> <span data-ttu-id="2a7de-107">Az alábbi példákat be kell állítani a **Feladási definíciók** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2a7de-107">The following examples can be set up on the **Posting definitions** page.</span></span> <span data-ttu-id="2a7de-108">Mindegyik példa ezeket a szakaszokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="2a7de-108">Each example contains these sections:</span></span>

-   <span data-ttu-id="2a7de-109">Feladási definíció – Egyeztetési feltételek</span><span class="sxs-lookup"><span data-stu-id="2a7de-109">Posting definition – Match criteria</span></span>
-   <span data-ttu-id="2a7de-110">Feladási definíció – Generált tételek</span><span class="sxs-lookup"><span data-stu-id="2a7de-110">Posting definition – Generated entries</span></span>
-   <span data-ttu-id="2a7de-111">Tranzakciók a számlákkal, a dimenzióértékekkel és összegekkel.</span><span class="sxs-lookup"><span data-stu-id="2a7de-111">Transactions with the accounts, dimension values, and amounts</span></span>
-   <span data-ttu-id="2a7de-112">A feladási definíció által létrehozott főkönyvi bejegyzések</span><span class="sxs-lookup"><span data-stu-id="2a7de-112">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="2a7de-113">Egyezés esetén a számlák és dimenzióértékek között az **Egyeztetési feltételek** ablakban a feladási definíciónál és a számláknál és dimenzióértékeknél a tranzakcióm, főkönyvi bejegyzések készülnek a **Létrehozott bejegyzések** ablak alapján a feladási definíciónál.</span><span class="sxs-lookup"><span data-stu-id="2a7de-113">When a match occurs between the accounts and dimension values in the **Match criteria** pane for the posting definition and the accounts and dimension values on the transaction, ledger entries are generated based on the **Generated entries** pane for the posting definition.</span></span> 
> [!NOTE]
> <span data-ttu-id="2a7de-114">Feladásdefiníciók tranzakciótípusokhoz rendeléséhez használja a **Tranzakció-feladásdefiníciók** oldalt.</span><span class="sxs-lookup"><span data-stu-id="2a7de-114">To associate a posting definition with a specific transaction type, use the **Transaction posting definitions** page.</span></span> <span data-ttu-id="2a7de-115">Miután társítja a feladásdefiníciót a tranzakciótípussal, és bejelöli a **Feladásdefiníciók használata** opciót a **Főkönyvi paraméterek** oldalon, a kijelölt tranzakciótípus minden tranzakciójának feladásdefiníciókat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="2a7de-115">After you associate a posting definition with a transaction type and select **Use posting definitions** on the **General ledger parameters** page, all transactions of the selected transaction type must use posting definitions.</span></span>

## <a name="example-purchase-order-encumbrances"></a><span data-ttu-id="2a7de-116">Példa: beszerzési rendelések terhelései</span><span class="sxs-lookup"><span data-stu-id="2a7de-116">Example: Purchase order encumbrances</span></span>
<span data-ttu-id="2a7de-117">Amikor engedélyezi a kötelezettségvállalás feldolgozását a **Kötelezettségvállalási folyamat engedélyezése** lehetőség kiválasztásával a **Főkönyvi paraméterek** lapon, feladásdefiníciókat kell használni a kötelezettségvállalások rögzítéséhez főkönyvi számlában, bármely lefoglalandó számla esetében.</span><span class="sxs-lookup"><span data-stu-id="2a7de-117">When you enable encumbrance processing by selecting **Enable encumbrance process** on the **General ledger parameters** page, posting definitions must be used to record encumbrances to the general ledger for any accounts that should be reserved.</span></span> <span data-ttu-id="2a7de-118">A legtöbb esetben az összes költségszámla fenn van tartva a mérlegben.</span><span class="sxs-lookup"><span data-stu-id="2a7de-118">In most cases, all expense accounts are reserved on the balance sheet.</span></span> 

<span data-ttu-id="2a7de-119">Feladásdefiníciók a kötelezettségvállalásokhoz a **Beszerzés** modulban a **Feladásdefiníciók** oldalon állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="2a7de-119">Posting definitions for encumbrances are set up for the **Purchasing** module on the **Posting definitions** page.</span></span> <span data-ttu-id="2a7de-120">Ezután a **Beszerzés** területen a **Tranzakció-feladásdefiníciók** lapon kiválaszthatja a **Beszerzési rendelés** tranzakciótípust a feladási definíciók beszerzési rendeléshez való társításához.</span><span class="sxs-lookup"><span data-stu-id="2a7de-120">Then, in the **Purchasing** area of the **Transaction posting definitions** page, you can select the **Purchase order** transaction type to associate the posting definition with purchase orders.</span></span> 

<span data-ttu-id="2a7de-121">A beszerzési rendelés kötelezettségvállalások összes bizonylattranzakciójának ki kell futnia nullára (vagyis a tartozás legyen ugyanannyi, mint a követelés) minden egyes bizonylatdimenzióban.</span><span class="sxs-lookup"><span data-stu-id="2a7de-121">All voucher transactions for purchase order encumbrances must balance (that is, debits must equal credits) in each unique dimension on a voucher.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="2a7de-122">Feladási definíció – Egyeztetési feltételek</span><span class="sxs-lookup"><span data-stu-id="2a7de-122">Posting definition – Match criteria</span></span>

| <span data-ttu-id="2a7de-123">Számlastruktúra</span><span class="sxs-lookup"><span data-stu-id="2a7de-123">Account structure</span></span>       | <span data-ttu-id="2a7de-124">Számlaszám egyeztetése</span><span class="sxs-lookup"><span data-stu-id="2a7de-124">Match account number</span></span> | <span data-ttu-id="2a7de-125">. prioritás</span><span class="sxs-lookup"><span data-stu-id="2a7de-125">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="2a7de-126">Számlastruktúra - P&L (eredmény)</span><span class="sxs-lookup"><span data-stu-id="2a7de-126">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="2a7de-127">1</span><span class="sxs-lookup"><span data-stu-id="2a7de-127">1</span></span>        |

<span data-ttu-id="2a7de-128"><em>Az üres érték a \**Számlaszám egyeztetése</em>* mezőben azt jelzi, hogy az összes egyeztetési számla a definiált számlastruktúrában része az egyeztetési szabályoknak.</span><span class="sxs-lookup"><span data-stu-id="2a7de-128"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="2a7de-129">Feladási definíció – Generált tételek</span><span class="sxs-lookup"><span data-stu-id="2a7de-129">Posting definition – Generated entries</span></span>

| <span data-ttu-id="2a7de-130">Számlastruktúra</span><span class="sxs-lookup"><span data-stu-id="2a7de-130">Account structure</span></span> | <span data-ttu-id="2a7de-131">Létrehozott számlaszám</span><span class="sxs-lookup"><span data-stu-id="2a7de-131">Generated account number</span></span>                    | <span data-ttu-id="2a7de-132">Létrehozott terhelés/jóváírás</span><span class="sxs-lookup"><span data-stu-id="2a7de-132">Generated debit/credit</span></span> |
|-------------------|---------------------------------------------|------------------------|
| <span data-ttu-id="2a7de-133">Egyenleg</span><span class="sxs-lookup"><span data-stu-id="2a7de-133">Balance</span></span>           | <span data-ttu-id="2a7de-134">300143 --(Kötelezettségvállalási számla)</span><span class="sxs-lookup"><span data-stu-id="2a7de-134">300143 - -(Encumbrance account)</span></span>             | <span data-ttu-id="2a7de-135">Egyező</span><span class="sxs-lookup"><span data-stu-id="2a7de-135">Same</span></span>                   |
| <span data-ttu-id="2a7de-136">Egyenleg</span><span class="sxs-lookup"><span data-stu-id="2a7de-136">Balance</span></span>           | <span data-ttu-id="2a7de-137">300144 --(Tartalék a kötelezettségvállalási számlához)</span><span class="sxs-lookup"><span data-stu-id="2a7de-137">300144 - -(Reserve for encumbrance account)</span></span> | <span data-ttu-id="2a7de-138">Egyensúlyozás</span><span class="sxs-lookup"><span data-stu-id="2a7de-138">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="2a7de-139">Tranzakciók a számlákkal, a dimenzióértékekkel és összegekkel.</span><span class="sxs-lookup"><span data-stu-id="2a7de-139">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="2a7de-140">A számlák és dimenzióértékek vagy a beszerzési rendelés sorához beírt könyvelési felosztásokból származnak, vagy a számlák és dimenziók, szállítók, cikkek, kategóriák és dimenziók sablonjaihoz az alapbeállítások alapján automatikusan generált számlákból és dimenziókból.</span><span class="sxs-lookup"><span data-stu-id="2a7de-140">The accounts and dimension values come either from the accounting distributions that you enter for a purchase order line, or from the accounts and dimensions that are automatically generated based on the default settings for vendors, items, categories, and dimension templates.</span></span>

| <span data-ttu-id="2a7de-141">Számla + dimenzió</span><span class="sxs-lookup"><span data-stu-id="2a7de-141">Account + dimensions</span></span>           | <span data-ttu-id="2a7de-142">Tartozik</span><span class="sxs-lookup"><span data-stu-id="2a7de-142">Debit</span></span>  | <span data-ttu-id="2a7de-143">Követel</span><span class="sxs-lookup"><span data-stu-id="2a7de-143">Credit</span></span> | <span data-ttu-id="2a7de-144">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="2a7de-144">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="2a7de-145">606400-OU\_1-OU\_3566-Oktatás</span><span class="sxs-lookup"><span data-stu-id="2a7de-145">606400-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="2a7de-146">250.00</span><span class="sxs-lookup"><span data-stu-id="2a7de-146">250.00</span></span> |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="2a7de-147">A feladási definíció által létrehozott főkönyvi bejegyzések</span><span class="sxs-lookup"><span data-stu-id="2a7de-147">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="2a7de-148">A létrehozott főkönyvi bejegyzések a kötelezettségvállalások rögzítésére jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="2a7de-148">Generated ledger entries are created to record the encumbrances.</span></span>

| <span data-ttu-id="2a7de-149">Számla + dimenzió</span><span class="sxs-lookup"><span data-stu-id="2a7de-149">Account + dimensions</span></span>           | <span data-ttu-id="2a7de-150">Tartozik</span><span class="sxs-lookup"><span data-stu-id="2a7de-150">Debit</span></span>  | <span data-ttu-id="2a7de-151">Követel</span><span class="sxs-lookup"><span data-stu-id="2a7de-151">Credit</span></span> | <span data-ttu-id="2a7de-152">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="2a7de-152">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="2a7de-153">300143-OU\_1-OU\_3566-Oktatás</span><span class="sxs-lookup"><span data-stu-id="2a7de-153">300143-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="2a7de-154">250.00</span><span class="sxs-lookup"><span data-stu-id="2a7de-154">250.00</span></span> |        |         |
| <span data-ttu-id="2a7de-155">300144-OU\_1-OU\_3566-Oktatás</span><span class="sxs-lookup"><span data-stu-id="2a7de-155">300144-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="2a7de-156">250.00</span><span class="sxs-lookup"><span data-stu-id="2a7de-156">250.00</span></span> |         |

<span data-ttu-id="2a7de-157">Az alábbi példában minden számla esetében, amely része a Számlastruktúrának - a P&L (eredmény) megfelel a feladási definíció kritériumainak.</span><span class="sxs-lookup"><span data-stu-id="2a7de-157">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="2a7de-158">Ezért amikor a 606500-OU\_1-OU\_3566-Oktatást vizsgálja meg a program, a létrehozott bejegyzések a **Létrehozott bejegyzések** ablakban definiált számlákhoz jönnek létre, a feladásdefiníció esetében.</span><span class="sxs-lookup"><span data-stu-id="2a7de-158">Therefore, when 606500-OU\_1-OU\_3566-Training is evaluated, generated entries are created for the accounts that are defined in the **Generated entries** pane for the posting definition.</span></span>

## <a name="example-budget-appropriations"></a><span data-ttu-id="2a7de-159">Példa: Költségvetési előirányzatok</span><span class="sxs-lookup"><span data-stu-id="2a7de-159">Example: Budget appropriations</span></span>
<span data-ttu-id="2a7de-160">Amikor engedélyezi a költségvetési előirányzatot a **Költségvetési előirányzat engedélyezése** bejelölésével a **Főkönyvi paraméterek** lapon, feladásdefiníciókat kell használni a költségvetési tételjegyzék-bejegyzések főkönyvbe történő rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="2a7de-160">When you enable budget appropriation by selecting **Enable budget appropriation** on the **General ledger parameters** page, posting definitions must be used to record budget register entries to the general ledger.</span></span> <span data-ttu-id="2a7de-161">Amikor egy költségvetés-ellenőrzési konfiguráció aktív, és be van kapcsolva, feladásdefiníciók és tranzakció-feladásdefiníciók használhatók a bejegyzések rögzítésére az előirányzatokról, változatokról, átvitelekről, projektekről, tárgyi eszközökről és kereslet-kínálati előrejelzésekről a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="2a7de-161">When a budget control configuration is active and is turned on, posting definitions and transaction posting definitions can be used to support the recording of entries for appropriations, revisions, transfers, projects, fixed assets, and supply and demand forecasts to the general ledger.</span></span> 

<span data-ttu-id="2a7de-162">Egy feladásdefiníció beállításához olyan költségvetési tételjegyzék-bejegyzéseknél, amelyeknek a költségvetési típusa **Eredeti költségvetés**, és az előirányzatok engedélyezve vannak, jelölje be a **Költségvetés** modult a **Feladásdefiníciók** lapon.</span><span class="sxs-lookup"><span data-stu-id="2a7de-162">To set up a posting definition for budget register entries that has a budget type of **Original budget**, and that has appropriations enabled, select the **Budget** module on the **Posting definitions** page.</span></span> <span data-ttu-id="2a7de-163">Ezután a **Költségvetés** területen, a **Tranzakció-feladásdefiníciók** lapon költségvetési kódok segítségével a feladásdefiníciót társítani tudja a költségvetési tételjegyzék-bejegyzésekkel, amelyeknek a költségvetési típusa **Eredeti költségvetés**.</span><span class="sxs-lookup"><span data-stu-id="2a7de-163">Then, in the **Budget** area of the **Transaction posting definitions** page, you can use budget codes to associate the posting definition with budget register entries that have a budget type of **Original budget**.</span></span> 

<span data-ttu-id="2a7de-164">Ha engedélyezve vannak a költségvetési előirányzatok és a feladásdefiníciók, a költségvetési tételjegyzék-bejegyzések rögzítésre kerülnek a költségvetés-ellenőrzésre és a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="2a7de-164">When budget appropriations and posting definitions are enabled, the budget register entries are recorded for budget control and in the general ledger.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="2a7de-165">Feladási definíció – Egyeztetési feltételek</span><span class="sxs-lookup"><span data-stu-id="2a7de-165">Posting definition – Match criteria</span></span>

| <span data-ttu-id="2a7de-166">Számlastruktúra</span><span class="sxs-lookup"><span data-stu-id="2a7de-166">Account structure</span></span>       | <span data-ttu-id="2a7de-167">Számlaszám egyeztetése</span><span class="sxs-lookup"><span data-stu-id="2a7de-167">Match account number</span></span> | <span data-ttu-id="2a7de-168">. prioritás</span><span class="sxs-lookup"><span data-stu-id="2a7de-168">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="2a7de-169">Számlastruktúra - P&L (eredmény)</span><span class="sxs-lookup"><span data-stu-id="2a7de-169">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="2a7de-170">1</span><span class="sxs-lookup"><span data-stu-id="2a7de-170">1</span></span>        |

<span data-ttu-id="2a7de-171"><em>Az üres érték a \**Számlaszám egyeztetése</em>* mezőben azt jelzi, hogy az összes egyeztetési számla a definiált számlastruktúrában része az egyeztetési szabályoknak.</span><span class="sxs-lookup"><span data-stu-id="2a7de-171"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="2a7de-172">Feladási definíció – Generált tételek</span><span class="sxs-lookup"><span data-stu-id="2a7de-172">Posting definition – Generated entries</span></span>

| <span data-ttu-id="2a7de-173">Számlastruktúra</span><span class="sxs-lookup"><span data-stu-id="2a7de-173">Account structure</span></span> | <span data-ttu-id="2a7de-174">Létrehozott számlaszám</span><span class="sxs-lookup"><span data-stu-id="2a7de-174">Generated account number</span></span>              | <span data-ttu-id="2a7de-175">Létrehozott terhelés/jóváírás</span><span class="sxs-lookup"><span data-stu-id="2a7de-175">Generated debit/credit</span></span> |
|-------------------|---------------------------------------|------------------------|
| <span data-ttu-id="2a7de-176">Számlastruktúra</span><span class="sxs-lookup"><span data-stu-id="2a7de-176">Account structure</span></span> | <span data-ttu-id="2a7de-177">300145 - -(Becsült bevételhez használt számla)</span><span class="sxs-lookup"><span data-stu-id="2a7de-177">300145 - -(Estimated revenue account)</span></span> | <span data-ttu-id="2a7de-178">Egyező</span><span class="sxs-lookup"><span data-stu-id="2a7de-178">Same</span></span>                   |
| <span data-ttu-id="2a7de-179">Számlastruktúra</span><span class="sxs-lookup"><span data-stu-id="2a7de-179">Account structure</span></span> | <span data-ttu-id="2a7de-180">300146 --(Előirányzati számla)</span><span class="sxs-lookup"><span data-stu-id="2a7de-180">300146 - -(Appropriation account)</span></span>     | <span data-ttu-id="2a7de-181">Egyensúlyozás</span><span class="sxs-lookup"><span data-stu-id="2a7de-181">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="2a7de-182">Tranzakciók a számlákkal, a dimenzióértékekkel és összegekkel.</span><span class="sxs-lookup"><span data-stu-id="2a7de-182">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="2a7de-183">A számlákat, a dimenzióértékeket és az összegeket a költségvetési számlabejegyzéshez a **Költségvetési tételjegyzék-bejegyzés** oldalon adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="2a7de-183">You enter the accounts, dimension values, and amounts for the budget account entry on the **Budget register entry** page.</span></span>

| <span data-ttu-id="2a7de-184">Számla + dimenzió</span><span class="sxs-lookup"><span data-stu-id="2a7de-184">Account + dimensions</span></span>           | <span data-ttu-id="2a7de-185">Tartozik</span><span class="sxs-lookup"><span data-stu-id="2a7de-185">Debit</span></span> | <span data-ttu-id="2a7de-186">Követel</span><span class="sxs-lookup"><span data-stu-id="2a7de-186">Credit</span></span> | <span data-ttu-id="2a7de-187">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="2a7de-187">Comment</span></span> |
|--------------------------------|-------|--------|---------|
| <span data-ttu-id="2a7de-188">606400-OU\_1-OU\_3566-Oktatás</span><span class="sxs-lookup"><span data-stu-id="2a7de-188">606400-OU\_1-OU\_3566-Training</span></span> |       | <span data-ttu-id="2a7de-189">250.00</span><span class="sxs-lookup"><span data-stu-id="2a7de-189">250.00</span></span> |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="2a7de-190">A feladási definíció által létrehozott főkönyvi bejegyzések</span><span class="sxs-lookup"><span data-stu-id="2a7de-190">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="2a7de-191">A generált főkönyvi bejegyzések az eredeti költségvetés rögzítésére jönnek létre az egyes dimenziókban.</span><span class="sxs-lookup"><span data-stu-id="2a7de-191">Generated ledger entries are created to record the original budget in each dimension.</span></span>

| <span data-ttu-id="2a7de-192">Számla + dimenzió</span><span class="sxs-lookup"><span data-stu-id="2a7de-192">Account + dimensions</span></span>           | <span data-ttu-id="2a7de-193">Tartozik</span><span class="sxs-lookup"><span data-stu-id="2a7de-193">Debit</span></span>  | <span data-ttu-id="2a7de-194">Követel</span><span class="sxs-lookup"><span data-stu-id="2a7de-194">Credit</span></span> | <span data-ttu-id="2a7de-195">Megjegyzés</span><span class="sxs-lookup"><span data-stu-id="2a7de-195">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="2a7de-196">300145-OU\_1-OU\_3566-Oktatás</span><span class="sxs-lookup"><span data-stu-id="2a7de-196">300145-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="2a7de-197">250.00</span><span class="sxs-lookup"><span data-stu-id="2a7de-197">250.00</span></span> |         |
| <span data-ttu-id="2a7de-198">300146-OU\_1-OU\_3566-Oktatás</span><span class="sxs-lookup"><span data-stu-id="2a7de-198">300146-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="2a7de-199">250.00</span><span class="sxs-lookup"><span data-stu-id="2a7de-199">250.00</span></span> |        |         |

<span data-ttu-id="2a7de-200">Az alábbi példában minden számla esetében, amely része a Számlastruktúrának - a P&L (eredmény) megfelel a feladási definíció kritériumainak.</span><span class="sxs-lookup"><span data-stu-id="2a7de-200">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="2a7de-201">Ezért amikor a 606400-OU\_1-OU\_3566-Oktatást vizsgálja meg a program, létrejönnek a generált főkönyvi bejegyzések.</span><span class="sxs-lookup"><span data-stu-id="2a7de-201">Therefore, when 606400-OU\_1-OU\_3566-Training is evaluated, the generated ledger entries are created.</span></span>






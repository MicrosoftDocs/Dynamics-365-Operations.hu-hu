---
title: "könyvelési felosztások és az analitikusnapló-bejegyzései a szabadszöveges számlákhoz"
description: "A könyvelési felosztások alkalmazásával meg lehet határozni, hogy hogyan legyen az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán. Minden olyan összeg, amelyet könyvelni kell a szabadszöveges számla naplózása esetén, egy vagy több könyvelési felosztással rendelkezik."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d13fbd98597fc8138bfb4d549608d75f790e0e52
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a><span data-ttu-id="d543e-104">könyvelési felosztások és az analitikusnapló-bejegyzései a szabadszöveges számlákhoz</span><span class="sxs-lookup"><span data-stu-id="d543e-104">Accounting distributions and subledger journal entries for free text invoices</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d543e-105">A könyvelési felosztások alkalmazásával meg lehet határozni, hogy hogyan legyen az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán.</span><span class="sxs-lookup"><span data-stu-id="d543e-105">Accounting distributions are used to define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span> <span data-ttu-id="d543e-106">Minden olyan összeg, amelyet könyvelni kell a szabadszöveges számla naplózása esetén, egy vagy több könyvelési felosztással rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="d543e-106">Every amount that must be accounted for when the free text invoice is journalized will have one or more accounting distributions.</span></span>

<a name="accounting-distributions"></a><span data-ttu-id="d543e-107">Könyvelési felosztások</span><span class="sxs-lookup"><span data-stu-id="d543e-107">Accounting distributions</span></span>
------------------------

<span data-ttu-id="d543e-108">A következő gombokat használhatja a Szabadszöveges számla oldalon a szabadszöveges számlán szereplő minden összeg könyvelési felosztásának megtekintéséhez és lehetséges módosításához.</span><span class="sxs-lookup"><span data-stu-id="d543e-108">You can use the following buttons in the Free text invoice page to view, and possibly change, the accounting distributions for each amount on the free text invoice.</span></span>

-   <span data-ttu-id="d543e-109">**Összegek felosztása**—Egy bizonyos sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása.</span><span class="sxs-lookup"><span data-stu-id="d543e-109">**Distribute amounts**—View and change the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="d543e-110">Megtekintheti és módosíthatja a könyvelési felosztásokat az alárendelt sorra vonatkozóan a Forgalmi adó tranzakciók vagy a Költségtranzakciók lapon is.</span><span class="sxs-lookup"><span data-stu-id="d543e-110">You can also view and change the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="d543e-111">Módosítsa a szabadszöveges számla fejléc összegeit, például a költség vagy a pénznemben megadott kerekítési összegeket.</span><span class="sxs-lookup"><span data-stu-id="d543e-111">Change free text invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="d543e-112">Módosítsa a Szabadszöveges számla sor összegeit.</span><span class="sxs-lookup"><span data-stu-id="d543e-112">Change free text invoice line amounts.</span></span>
-   <span data-ttu-id="d543e-113">**Felosztások megtekintése**—A dokumentumban szereplő összes sorhoz tartozó könyvelési felosztás megtekintése.</span><span class="sxs-lookup"><span data-stu-id="d543e-113">**View distributions**—View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="d543e-114">A könyvelési felosztásokat ebből a nézetből nem módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="d543e-114">You can't change the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="d543e-115">A fejléc és a sorösszegek áttekintése.</span><span class="sxs-lookup"><span data-stu-id="d543e-115">View header and line amounts.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="d543e-116">Összegek elosztása</span><span class="sxs-lookup"><span data-stu-id="d543e-116">Distributing amounts</span></span>
<span data-ttu-id="d543e-117">Szabadszöveges számla bevitelekor minden összeg felosztása a következőképpen történik.</span><span class="sxs-lookup"><span data-stu-id="d543e-117">When you enter a free text invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d543e-118">Az pénzösszeg típusa</span><span class="sxs-lookup"><span data-stu-id="d543e-118">Type of monetary amount</span></span></th>
<th><span data-ttu-id="d543e-119">Ahol a fő számla látható.</span><span class="sxs-lookup"><span data-stu-id="d543e-119">Where the main account is displayed from</span></span></th>
<th><span data-ttu-id="d543e-120">Prioritási sorrend, amely meghatározza, hogy mely alapértelmezett pénzügyi dimenzió jelenik meg</span><span class="sxs-lookup"><span data-stu-id="d543e-120">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d543e-121">Szabadszöveges számla sora</span><span class="sxs-lookup"><span data-stu-id="d543e-121">Free text invoice line</span></span></td>
<td><span data-ttu-id="d543e-122">A főkönyv számlasor a szabadszöveges számlasoron.</span><span class="sxs-lookup"><span data-stu-id="d543e-122">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="d543e-123">Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</span><span class="sxs-lookup"><span data-stu-id="d543e-123">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d543e-124">Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</span><span class="sxs-lookup"><span data-stu-id="d543e-124">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-125">Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</span><span class="sxs-lookup"><span data-stu-id="d543e-125">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-126">Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="d543e-126">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d543e-127">A tárgyi eszköz száma és értékmodell kombinációjának szabadszöveges számlasora</span><span class="sxs-lookup"><span data-stu-id="d543e-127">Free text invoice line for a fixed asset number and value model combination</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d543e-128"><strong>Megjegyzés </strong></span><span class="sxs-lookup"><span data-stu-id="d543e-128"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d543e-129">A szabadszöveges számlasoron található fő számla a tárgyi eszköz kivezetési számlája.</span><span class="sxs-lookup"><span data-stu-id="d543e-129">The main account on the free text invoice line will be the fixed asset disposal account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
<td><span data-ttu-id="d543e-130">A főkönyv számlasor a szabadszöveges számlasoron.</span><span class="sxs-lookup"><span data-stu-id="d543e-130">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="d543e-131">Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</span><span class="sxs-lookup"><span data-stu-id="d543e-131">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-132">Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="d543e-132">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d543e-133">Szabadszöveges számla engedmény összege</span><span class="sxs-lookup"><span data-stu-id="d543e-133">Free text invoice discount amount</span></span></td>
<td><span data-ttu-id="d543e-134">A vevő fő számlája engedmény a készpénzfizetési engedmények lapján található engedmények mezője.</span><span class="sxs-lookup"><span data-stu-id="d543e-134">The Main account for customer discounts field in the Cash discounts page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d543e-135">Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</span><span class="sxs-lookup"><span data-stu-id="d543e-135">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d543e-136">Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</span><span class="sxs-lookup"><span data-stu-id="d543e-136">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-137">Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</span><span class="sxs-lookup"><span data-stu-id="d543e-137">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-138">Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="d543e-138">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d543e-139">Szabadszöveges számla adó összege</span><span class="sxs-lookup"><span data-stu-id="d543e-139">Free text invoice sales tax amount</span></span></td>
<td><span data-ttu-id="d543e-140">A főkönyvi feladási csoportok lapon található forgalmi adó kötelezettségek mezője.</span><span class="sxs-lookup"><span data-stu-id="d543e-140">The Sales tax payable field in the Ledger posting groups page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d543e-141">Hazsnálja a pénzügyi dimenziókat, amelyeket a költség sor összeg felosztások vagy a szabadszöveges számla sor összegek szerint határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="d543e-141">Use the financial dimensions that are defined on the free text invoice line amount or the distributions for the charge line amount.</span></span></li>
<li><span data-ttu-id="d543e-142">Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</span><span class="sxs-lookup"><span data-stu-id="d543e-142">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-143">Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="d543e-143">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d543e-144">Szabadszöveges számla kötlség sor összege</span><span class="sxs-lookup"><span data-stu-id="d543e-144">Free text invoice charge line amount</span></span></td>
<td><span data-ttu-id="d543e-145">A költségek kódlapon található hitel számla mezője.</span><span class="sxs-lookup"><span data-stu-id="d543e-145">The Credit account field in the Charges code page.</span></span></td>
<td><ol>
<li><span data-ttu-id="d543e-146">Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</span><span class="sxs-lookup"><span data-stu-id="d543e-146">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="d543e-147">Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</span><span class="sxs-lookup"><span data-stu-id="d543e-147">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-148">Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</span><span class="sxs-lookup"><span data-stu-id="d543e-148">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="d543e-149">Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</span><span class="sxs-lookup"><span data-stu-id="d543e-149">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a><span data-ttu-id="d543e-150">Adók elosztása</span><span class="sxs-lookup"><span data-stu-id="d543e-150">Distributing taxes</span></span>
<span data-ttu-id="d543e-151">Az adókra vonatkozó könyvelési felosztások nem hozhatók létre, amíg az adókat ki nem számítja.</span><span class="sxs-lookup"><span data-stu-id="d543e-151">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="d543e-152">Forgalmi adó kiszámításához fejezzen be egyet a következő feladatok közül a Szabadszöveges számla képernyőjén:</span><span class="sxs-lookup"><span data-stu-id="d543e-152">To calculate sales taxes, you must complete one of the following tasks in the Free text invoice form:</span></span>
-   <span data-ttu-id="d543e-153">Az áfa megtekintése.</span><span class="sxs-lookup"><span data-stu-id="d543e-153">View the sales tax.</span></span>
-   <span data-ttu-id="d543e-154">Számla végösszegének megtekintése.</span><span class="sxs-lookup"><span data-stu-id="d543e-154">View the invoice total.</span></span>
-   <span data-ttu-id="d543e-155">Pénzforgalom megtekintése.</span><span class="sxs-lookup"><span data-stu-id="d543e-155">View the cash flow.</span></span>
-   <span data-ttu-id="d543e-156">Az egész szabadszöveges számla könyvelési felosztásainak megtekintése.</span><span class="sxs-lookup"><span data-stu-id="d543e-156">View accounting distributions for the whole free text invoice.</span></span>
-   <span data-ttu-id="d543e-157">Analitikus napló megtekintése.</span><span class="sxs-lookup"><span data-stu-id="d543e-157">View the subledger journal.</span></span>

## <a name="subledger-journals-for-free-text-invoices"></a><span data-ttu-id="d543e-158"> A szabadszöveges számlák analitikus naplóinak megtekintése</span><span class="sxs-lookup"><span data-stu-id="d543e-158">Subledger journals for free text invoices</span></span>
<span data-ttu-id="d543e-159">Szabadszöveges számla feladása előtt meg lehet tekinteni a számla teljes könyvelési bejegyzését, amely tartalmazza a terheléseket és követeléseket, azért, hogy igazolják, hogy a számla a megfelelő számlákra van elküldve.</span><span class="sxs-lookup"><span data-stu-id="d543e-159">Before you post a free text invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="d543e-160">A teljes könyvelési bejegyzésnek ezt a nézetét analitikus naplónak hívják.</span><span class="sxs-lookup"><span data-stu-id="d543e-160">This view of the full accounting entry is called a subledger journal.</span></span> <span data-ttu-id="d543e-161">Ha az analitikus napló bejegyzése helytelen, amikor megtekinti azt a szabadszöveges számla naplózása előtt, az analitikus napló bejegyzése nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="d543e-161">If the subledger journal entry is incorrect when you preview it before you journalize the free text invoice, you can't change the subledger journal entry.</span></span> <span data-ttu-id="d543e-162">Ehelyett módosítania kell a könyvelési felosztásokat vagy a feladási profilt.</span><span class="sxs-lookup"><span data-stu-id="d543e-162">Instead, you must change the accounting distributions or the posting profile.</span></span> <span data-ttu-id="d543e-163">A könyvelési felosztásokat a könyvelési tétel, a tartozás tétel vagy a jóváírás egy részének meghatározására használják.</span><span class="sxs-lookup"><span data-stu-id="d543e-163">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="d543e-164">Az beszámítási analitikus naplószámla számlabejegyzése a feladási profilok feladásából, például a vevői számlából vagy az adóból jön létre.</span><span class="sxs-lookup"><span data-stu-id="d543e-164">The offsetting subledger journal account entry is created from the posting profiles, such as from the customer account or the tax.</span></span>





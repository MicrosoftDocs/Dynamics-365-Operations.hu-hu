---
title: Szállítási költség egyeztetése a szállításkezelésben
description: A témakör a szállítási költség egyeztetési folyamatot ismerteti.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac07155e4dde77689b1994abfb8b30f45d5a5a30
ms.sourcegitcommit: b6686265314499056690538eaa95ca51cff7c720
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5014508"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="e23ad-103">Szállítási költség egyeztetése a szállításkezelésben</span><span class="sxs-lookup"><span data-stu-id="e23ad-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e23ad-104">A témakör a szállítási költség egyeztetési folyamatot ismerteti.</span><span class="sxs-lookup"><span data-stu-id="e23ad-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="e23ad-105">Szállítási költség egyeztetés elvégezhető manuálisan vagy beállítható automatikusra.</span><span class="sxs-lookup"><span data-stu-id="e23ad-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="e23ad-106">Automatikus szállítási egyeztetés használatához vizsgálati alapadatok beállítása szükséges, ahol megadhatja a feltételeket, amelyek meghatározzák, hogy mely fuvarszámla egyeztetése legyen automatikus.</span><span class="sxs-lookup"><span data-stu-id="e23ad-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="e23ad-107">A fuvaregyeztetési folyamat</span><span class="sxs-lookup"><span data-stu-id="e23ad-107">The freight reconciliation process</span></span>

<span data-ttu-id="e23ad-108">A szállítási díjakat a megfelelő szállítási fuvarozóval társított díjkalkulátor számítja ki.</span><span class="sxs-lookup"><span data-stu-id="e23ad-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="e23ad-109">Rakomány megerősítése esetén a fuvarlevélszámla létrejön, és a szállítási díjak átvitele a fuvarlevélszámlára megtörténik.</span><span class="sxs-lookup"><span data-stu-id="e23ad-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="e23ad-110">A fuvardíjak vegyes költségek szerint vannak arányosítva a vonatkozó forrásbizonylat (beszerzési rendelés, értékesítési rendelés és/vagy átmozgatási rendelés) alapján, a rendszeres számlázási folyamat beállításaitól függően.</span><span class="sxs-lookup"><span data-stu-id="e23ad-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="e23ad-111">A szállítási költség egyeztetési folyamata elindítható, amint a fuvarszámla megérkezik a szállítmányozótól.</span><span class="sxs-lookup"><span data-stu-id="e23ad-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="e23ad-112">A számla elektronikus úton vagy nyomtatott papíron érkezhet.</span><span class="sxs-lookup"><span data-stu-id="e23ad-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="e23ad-113">Ha papíralapú számla érkezik, elektronikus számlát hozhat létre a fuvarlevelet használva sablonként.</span><span class="sxs-lookup"><span data-stu-id="e23ad-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span>

<span data-ttu-id="e23ad-114">[![Fuvaregyeztetési folyamat](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="e23ad-114">[![Freight reconciliation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="e23ad-115">Manuális egyeztetés</span><span class="sxs-lookup"><span data-stu-id="e23ad-115">Manual reconciliation</span></span>

<span data-ttu-id="e23ad-116">Ha az egyeztetést manuálisan végzi, minden számlázási sorral minden fuvarlevélsort vagy a számlázandó rakománysort egyeztetnie kell.</span><span class="sxs-lookup"><span data-stu-id="e23ad-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="e23ad-117">Ezt a **Fuvarlevél és számlaegyeztetés** oldalon végezheti el.</span><span class="sxs-lookup"><span data-stu-id="e23ad-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="e23ad-118">Ha a számlasor összege nem egyezik meg a fuvardíj összegével, az eltérés egyeztetés okát kell kiválasztania.</span><span class="sxs-lookup"><span data-stu-id="e23ad-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="e23ad-119">Ha több egyeztetési ok fordul elő, a nem egyeztetett összeget feloszthatja.</span><span class="sxs-lookup"><span data-stu-id="e23ad-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="e23ad-120">Az egyeztetés oka határozza meg, hogyan kerülnek a különbözet összegei feladásra a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="e23ad-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="e23ad-121">Amikor a teljes számlaösszeg egyeztetése számba lett véve, jóváhagyás céljából elküldik és a napló feladásra kerül.</span><span class="sxs-lookup"><span data-stu-id="e23ad-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="e23ad-122">Az alábbi ábra bemutatja, hogyan készíthető szállítási számla és hajtható végre a fuvarlevél-egyeztetés.</span><span class="sxs-lookup"><span data-stu-id="e23ad-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span>

<span data-ttu-id="e23ad-123">[![Fuvaregyeztetési feladatok](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="e23ad-123">[![Freight reconciliation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>

## <a name="automatic-reconciliation"></a><span data-ttu-id="e23ad-124">Automatikus egyeztetés</span><span class="sxs-lookup"><span data-stu-id="e23ad-124">Automatic reconciliation</span></span>

<span data-ttu-id="e23ad-125">Automatikus egyeztetéshez meg kell adnia a használni kívánt egyeztetés, számlák, és szállítmányozók ütemezését.</span><span class="sxs-lookup"><span data-stu-id="e23ad-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="e23ad-126">A számlasorok és fuvarlevelek ellenőrzése alapvizsgálat beállításainak és a fuvarlevél típusának megfelelően történik.</span><span class="sxs-lookup"><span data-stu-id="e23ad-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="e23ad-127">Az automatikus egyeztetés futtatása után kezelnie kell azokat a számlákat, melyeket a rendszer nem tudott.</span><span class="sxs-lookup"><span data-stu-id="e23ad-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="e23ad-128">Manuálisan kell feldolgoznia ezeket a számlákat a kifizetés előtt.</span><span class="sxs-lookup"><span data-stu-id="e23ad-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a><span data-ttu-id="e23ad-129">Fuvarlevelek egyeztetése a fuvarszámlákkal automatikus vagy manuális módon</span><span class="sxs-lookup"><span data-stu-id="e23ad-129">Match freight bills with freight invoices using automatic or manual reconciliation</span></span>

<span data-ttu-id="e23ad-130">Az *egyeztetés* az egyes fuvarleveleknek megfelelő fuvarszámlák megkeresésének folyamatát jelenti.</span><span class="sxs-lookup"><span data-stu-id="e23ad-130">*Matching* is the process of finding the freight bills that correspond to each freight invoice.</span></span> <span data-ttu-id="e23ad-131">Ez a számlasorok egyenként történő (kézi egyeztetés) vagy az összes rendelkezésre álló számla egyszerre történő egyeztetésével (automatikus egyeztetés) hajtható végre.</span><span class="sxs-lookup"><span data-stu-id="e23ad-131">This can be done by matching the invoice lines one-by-one (manual matching), or by matching all available invoices at once (auto matching).</span></span>

### <a name="auto-matching"></a><span data-ttu-id="e23ad-132">Automatikus egyeztetés</span><span class="sxs-lookup"><span data-stu-id="e23ad-132">Auto matching</span></span>

<span data-ttu-id="e23ad-133">Ha több fuvarszámlát egyeztet ugyanahhoz a fuvarlevélhez, az automatikus egyeztetés folyamata a következőképpen működik:</span><span class="sxs-lookup"><span data-stu-id="e23ad-133">When matching multiple freight invoices to the same freight bill, the process for auto matching works as follows:</span></span>

1. <span data-ttu-id="e23ad-134">A nem egyeztetett fuvarszámlák összeg szerint vannak rendezve, kezdve a legnagyobb összeggel.</span><span class="sxs-lookup"><span data-stu-id="e23ad-134">All freight invoices not matched are sorted by amount, with largest amount first.</span></span>
1. <span data-ttu-id="e23ad-135">A fuvarszámlák egyeztetése egyenként történik, amíg a fuvarlevél fennmaradó összege nem lesz pozitív.</span><span class="sxs-lookup"><span data-stu-id="e23ad-135">The freight invoices are matched one-by-one, until the freight bill has no positive amount remaining.</span></span>
1. <span data-ttu-id="e23ad-136">Az alapvizsgálat beállításaitól és a fuvarszámlák fennmaradó összegétől függően a fennmaradó összeg be van állítva.</span><span class="sxs-lookup"><span data-stu-id="e23ad-136">Depending on the setup of the audit master and the remaining amount on the freight invoices, the remaining amount is set.</span></span>

### <a name="manual-matching"></a><span data-ttu-id="e23ad-137">Manuális egyeztetés</span><span class="sxs-lookup"><span data-stu-id="e23ad-137">Manual matching</span></span>

<span data-ttu-id="e23ad-138">A pozitív összeget tartalmazó fuvarlevelek egyeztetésre elérhetők.</span><span class="sxs-lookup"><span data-stu-id="e23ad-138">All freight bills with positive amounts will be available for matching.</span></span> <span data-ttu-id="e23ad-139">Az automatikus egyeztetéshez hasonlóan a felhasználó csak a negatív összegű fuvarszámlákat tudja egyezteti a nem teljesen egyező fuvarlevelekkel.</span><span class="sxs-lookup"><span data-stu-id="e23ad-139">Similar to auto matching, the user will only be able to match freight invoices with negative amounts to freight bills not fully matched.</span></span>

### <a name="example"></a><span data-ttu-id="e23ad-140">Példa</span><span class="sxs-lookup"><span data-stu-id="e23ad-140">Example</span></span>

<span data-ttu-id="e23ad-141">Tegyük fel, hogy van egy 1500 összegű fuvarlevél (FB), és Ön létrehozott három fuvarszámlát a fuvarlevélhez, mindegyik számlához egy számlasorral, a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="e23ad-141">Suppose that you have a freight bill (FB) for an amount of 1500 and you have created three freight invoices for the freight bill with one invoice line for each invoice with following settings:</span></span>

- <span data-ttu-id="e23ad-142">Eredeti fuvarlevél (FB): 1500 összeg</span><span class="sxs-lookup"><span data-stu-id="e23ad-142">Original freight bill (FB): Amount 1500</span></span>
- <span data-ttu-id="e23ad-143">1. számla (Inv1): 1000 összeg</span><span class="sxs-lookup"><span data-stu-id="e23ad-143">Invoice 1 (Inv1): Amount 1000</span></span>
- <span data-ttu-id="e23ad-144">2. számla (Inv2): 600 összeg</span><span class="sxs-lookup"><span data-stu-id="e23ad-144">Invoice 2 (Inv2): Amount 600</span></span>
- <span data-ttu-id="e23ad-145">3. számla (Inv3): -100 összeg</span><span class="sxs-lookup"><span data-stu-id="e23ad-145">Invoice 3 (Inv3): Amount -100</span></span>

#### <a name="automatic-matching-result"></a><span data-ttu-id="e23ad-146">Automatikus egyeztetés eredménye</span><span class="sxs-lookup"><span data-stu-id="e23ad-146">Automatic matching result</span></span>

<span data-ttu-id="e23ad-147">Az automatikus egyeztetés a következő sorrendben lesz végrehajtva:</span><span class="sxs-lookup"><span data-stu-id="e23ad-147">Auto matching will execute in following order:</span></span>

1. <span data-ttu-id="e23ad-148">Az összes fuvarszámla rendezése összeg szerint csökkenő sorrendben: Inv1 -> Inv2 -> Inv3.</span><span class="sxs-lookup"><span data-stu-id="e23ad-148">Sort all freight invoices descending by amount: Inv1 -> Inv2 -> Inv3.</span></span>
1. <span data-ttu-id="e23ad-149">Egyeztesse az Inv1-et az FB-vel.</span><span class="sxs-lookup"><span data-stu-id="e23ad-149">Match Inv1 with FB.</span></span> <span data-ttu-id="e23ad-150">Az Inv1 1000 értékű összegének egyeztetése megtörtént, és az FB-n 500 fennmaradó összeg szerepel, így az állapot *Részben egyező* lesz.</span><span class="sxs-lookup"><span data-stu-id="e23ad-150">Inv1 has 1000 matched and FB has 500 amount remaining, so the status is set to *Partially matched*.</span></span>
1. <span data-ttu-id="e23ad-151">Egyeztesse az Inv2-t az FB-vel.</span><span class="sxs-lookup"><span data-stu-id="e23ad-151">Match Inv2 with FB.</span></span> <span data-ttu-id="e23ad-152">Az Inv2 500 értékű összegének egyeztetése megtörtént, és az FB-n 0 fennmaradó összeg szerepel, így az állapot *Teljesen egyező* lesz.</span><span class="sxs-lookup"><span data-stu-id="e23ad-152">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="e23ad-153">Mivel az FB már teljesen egyeztetve van, az Inv3 nem lesz feldolgozva.</span><span class="sxs-lookup"><span data-stu-id="e23ad-153">Because FB is now fully matched, Inv3 won't be processed.</span></span>

#### <a name="manual-matching-result"></a><span data-ttu-id="e23ad-154">Kézi egyeztetés eredménye</span><span class="sxs-lookup"><span data-stu-id="e23ad-154">Manual matching result</span></span>

<span data-ttu-id="e23ad-155">A kézi egyeztetésnél az eredmények az egyeztetés sorrendjétől függenek, mint azt az alábbi példák mutatják.</span><span class="sxs-lookup"><span data-stu-id="e23ad-155">For manual matching, the results vary depending on the order of the matching, as illustrated in the following example cases.</span></span>

##### <a name="manual-matching-case-1"></a><span data-ttu-id="e23ad-156">1. manuális egyeztetési eset</span><span class="sxs-lookup"><span data-stu-id="e23ad-156">Manual matching case 1</span></span>

<span data-ttu-id="e23ad-157">A manuális egyeztetés egyik módja például a következő:</span><span class="sxs-lookup"><span data-stu-id="e23ad-157">One way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="e23ad-158">Egyeztesse az FB-t az Inv1-gyel.</span><span class="sxs-lookup"><span data-stu-id="e23ad-158">Match FB with Inv1.</span></span> <span data-ttu-id="e23ad-159">Az FB-n 500 fennmaradó összeg szerepel, így az állapot *Részben egyező* lesz.</span><span class="sxs-lookup"><span data-stu-id="e23ad-159">FB has 500 amount remaining, so the status set to *Partially matched*.</span></span>
1. <span data-ttu-id="e23ad-160">Egyeztesse az Inv2-t az FB-vel.</span><span class="sxs-lookup"><span data-stu-id="e23ad-160">Match Inv2 with FB.</span></span> <span data-ttu-id="e23ad-161">Az Inv2 500 értékű összegének egyeztetése megtörtént, és az FB-n 0 fennmaradó összeg szerepel, így az állapot *Teljesen egyező* lesz.</span><span class="sxs-lookup"><span data-stu-id="e23ad-161">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="e23ad-162">Ha manuálisan egyezteti az Inv3-at, nem fog találni nem egyező fuvarleveleket.</span><span class="sxs-lookup"><span data-stu-id="e23ad-162">When manually matching Inv3, you won't find any unmatched freight bills.</span></span>

<span data-ttu-id="e23ad-163">Ez az eset alapvetően megegyezik az automatikus egyeztetéssel</span><span class="sxs-lookup"><span data-stu-id="e23ad-163">This case is essentially the same as auto matching</span></span>

##### <a name="manual-matching-case-2"></a><span data-ttu-id="e23ad-164">2. manuális egyeztetési eset</span><span class="sxs-lookup"><span data-stu-id="e23ad-164">Manual matching case 2</span></span>

<span data-ttu-id="e23ad-165">A manuális egyeztetés egy másik módja például a következő:</span><span class="sxs-lookup"><span data-stu-id="e23ad-165">Another way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="e23ad-166">Egyeztesse az Inv3-at az FB-vel.</span><span class="sxs-lookup"><span data-stu-id="e23ad-166">Match Inv3 with FB.</span></span> <span data-ttu-id="e23ad-167">Az FB fennmaradó összege most 1600, ami megegyezik az 1500-as értékkel, ha 1600-ból kivonunk 100-at.</span><span class="sxs-lookup"><span data-stu-id="e23ad-167">Now FB has amount remaining 1600, which is the same as subtracting negative 100 on top of 1500.</span></span> <span data-ttu-id="e23ad-168">Az FB és az Inv3 is -100 mennyiséggel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="e23ad-168">Both FB and Inv3 have a matched quantity of -100.</span></span>
1. <span data-ttu-id="e23ad-169">Egyeztesse az Inv1-et és a Inv 2-t az FB-vel egymás után.</span><span class="sxs-lookup"><span data-stu-id="e23ad-169">Match Inv1 and Inv 2 with FB one after another.</span></span> <span data-ttu-id="e23ad-170">Az FB teljesen egyezik.</span><span class="sxs-lookup"><span data-stu-id="e23ad-170">FB is fully matched.</span></span>

<span data-ttu-id="e23ad-171">Mint a példa mutatja, a fuvarszámlák negatív összegekkel való egyeztetését csak manuálisan szabad elvégezni.</span><span class="sxs-lookup"><span data-stu-id="e23ad-171">As this example shows, matching freight invoices with negative amounts should only be done manually.</span></span> <span data-ttu-id="e23ad-172">Így mindig lehet egyeztetni a negatív összegű fuvarszámlákat egy nem teljesen egyező fuvarszámlával, mert így lehetősége van szabályozni az egyeztetési sorrendet.</span><span class="sxs-lookup"><span data-stu-id="e23ad-172">This will ensure that it is always possible to match the freight invoices with negative amounts to a freight bill not fully matched because that enables you to control the matching sequence.</span></span>

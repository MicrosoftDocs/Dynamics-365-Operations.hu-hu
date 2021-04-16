---
title: Lízingfeladási típusok
description: Ez a témakör az eszközlízing-tranzakciókhoz használt feladási típusokat ismerteti.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddc229f3ab8e048390f27503e2c6c26bd1a6f24f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841141"
---
# <a name="lease-posting-types"></a><span data-ttu-id="eed44-103">Lízingfeladási típusok</span><span class="sxs-lookup"><span data-stu-id="eed44-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eed44-104">Ez a témakör az eszközlízing-tranzakciókhoz használt feladási típusokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="eed44-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="eed44-105">Lízingeszköz</span><span class="sxs-lookup"><span data-stu-id="eed44-105">Lease asset</span></span>

<span data-ttu-id="eed44-106">A számla a használatijog-eszközhöz (ROU) van társítva.</span><span class="sxs-lookup"><span data-stu-id="eed44-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="eed44-107">Ezt a számlát akkor terhelik meg, ha a lízinget először az új lízingszámviteli standardok, a könyvelési standardok kodifikációs témakör 842 (ASC 842) és a nemzetközi Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="eed44-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="eed44-108">Módosított lízing esetén ez a számla megterhelhető vagy jóváírható, attól függően, hogy a módosítás növeli vagy csökkenti a lízingkötelezettséget.</span><span class="sxs-lookup"><span data-stu-id="eed44-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="eed44-109">**Példa naplóbejegyzések:** Kezdeti elszámolás</span><span class="sxs-lookup"><span data-stu-id="eed44-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="eed44-110">**Terhelés:** XXX lízingeszköz</span><span class="sxs-lookup"><span data-stu-id="eed44-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="eed44-111">**Jóváírás:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="eed44-112">Lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-112">Lease liability</span></span>

<span data-ttu-id="eed44-113">A számla a lízingkötelezettséghez kapcsolódik, amely akkor jelentkezik, amikor a kifizetéseket az új IFRS 16 és ASC 842 szabványok szerint árazzák le.</span><span class="sxs-lookup"><span data-stu-id="eed44-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="eed44-114">Ez a számla akkor kerül jóváírásra, ha a lízinget először az új standardok szerint ismerik el.</span><span class="sxs-lookup"><span data-stu-id="eed44-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="eed44-115">Megterhelik a lízingfizetésekkel, és jóváírják a kamatelhatárolások miatt.</span><span class="sxs-lookup"><span data-stu-id="eed44-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="eed44-116">**Példa naplóbejegyzések:** Kezdeti elszámolás</span><span class="sxs-lookup"><span data-stu-id="eed44-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="eed44-117">**Terhelés:** XXX lízingeszköz</span><span class="sxs-lookup"><span data-stu-id="eed44-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="eed44-118">**Jóváírás:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="eed44-119">**Példa naplóbejegyzések:** Kamatelhatárolás</span><span class="sxs-lookup"><span data-stu-id="eed44-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="eed44-120">**Terhelés:** XXX kamatköltség</span><span class="sxs-lookup"><span data-stu-id="eed44-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="eed44-121">**Jóváírás:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="eed44-122">**Példa naplóbejegyzések:** Lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="eed44-123">**Terhelés:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="eed44-124">**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="eed44-125">Rövid lejáratú lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-125">Short-term lease liability</span></span>

<span data-ttu-id="eed44-126">A számla a rövid távú lízingkötelezettséghez kapcsolódik a rövid távú lízingkötelezettség átsorolás naplóbejegyzésének feladásakor.</span><span class="sxs-lookup"><span data-stu-id="eed44-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="eed44-127">Ezt a számlát a hónap utolsó napján az amortizációs ütemezésből származó rövid távú kötelezettségjóváírásból írják jóvá.</span><span class="sxs-lookup"><span data-stu-id="eed44-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="eed44-128">Ugyanezt az összeget azonban a következő hónap első napján vonják le.</span><span class="sxs-lookup"><span data-stu-id="eed44-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="eed44-129">**Példa naplóbejegyzésekre:** Rövid távú lízingkötelezettség átsorlása</span><span class="sxs-lookup"><span data-stu-id="eed44-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="eed44-130">**Terhelés:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="eed44-131">**Terhelés:** XXX rövid távú lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="eed44-132">**Jóváírás:** XXX rövid távú lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="eed44-133">**Jóváírás:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="eed44-134">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="eed44-134">Depreciation expense</span></span>

<span data-ttu-id="eed44-135">A számla az IFRS 16 és ASC 842 szerinti ROU-eszköz értékcsökkenéséhez kapcsolódó ráfordításhoz, és a IFRS 17 és az ASC 840 szabványok alatti pénzügyi lízinghez kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="eed44-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="eed44-136">Ez a számla akkor kerül megterhelésre, ha egy ROU-eszköz havi értékcsökkenéssen esik át.</span><span class="sxs-lookup"><span data-stu-id="eed44-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="eed44-137">**Példa naplóbejegyzések:** Értékcsökkenés-elhatárolás</span><span class="sxs-lookup"><span data-stu-id="eed44-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="eed44-138">**Terhelés:** XXX értékcsökkenési költség</span><span class="sxs-lookup"><span data-stu-id="eed44-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="eed44-139">**Jóváírás:** XXX halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="eed44-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="eed44-140">Nyereség/veszteség a lízing módosításakor</span><span class="sxs-lookup"><span data-stu-id="eed44-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="eed44-141">A számla a lízingmódosításából származó nyereséghez vagy veszteséghez kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="eed44-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="eed44-142">Nyereség keletkezhet a lízing módosítása során, ha a módosítás a lízingkötelezettséget olyan összeggel csökkenti, amely meghaladja a ROU-eszköz szerinti értékét.</span><span class="sxs-lookup"><span data-stu-id="eed44-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="eed44-143">Például a lízingnek 150.000 dollár a lízingkötelezettségének könyv szerinti értéke és a ROU-eszköznek 100.000 dollár a könyv szerinti értéke.</span><span class="sxs-lookup"><span data-stu-id="eed44-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="eed44-144">A lízing módosult, és ez a módosítás a jövőbeli minimális lízingfizetések (PVFMLP) új, 40.000 dolláros jelen értékét hozza létre elő.</span><span class="sxs-lookup"><span data-stu-id="eed44-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="eed44-145">Ezért a lízingkötelezettséget 110.000 dollárral (150.000 dollár – 40.000 dollár) terhelik meg.</span><span class="sxs-lookup"><span data-stu-id="eed44-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="eed44-146">Mivel a ROU.eszköz csak 100.000 dollár, ezért a 110.000 dollár 0 (nulla) alá csökkenti az eszközt.</span><span class="sxs-lookup"><span data-stu-id="eed44-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="eed44-147">Ezért a könyvelési útmutató kimondja, hogy a fennmaradó részt egy nyereségszámlára kell könyvelni.</span><span class="sxs-lookup"><span data-stu-id="eed44-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="eed44-148">Ebben az esetben a záró naplóbejegyzés a 110.000 dollár lízingkötelezettségének terhelési értéke, a 100.000 dollár lízingeszközhöz történő jóváírása, és a 10.000 dollár nyereségszámláján történő jóváírás.</span><span class="sxs-lookup"><span data-stu-id="eed44-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="eed44-149">**Példa naplóbejegyzések:** Lízingmódosítás</span><span class="sxs-lookup"><span data-stu-id="eed44-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="eed44-150">**Terhelés:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="eed44-151">**Jóváírás:** XXX lízingeszköz</span><span class="sxs-lookup"><span data-stu-id="eed44-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="eed44-152">**Terhelés:** XXX nyereség</span><span class="sxs-lookup"><span data-stu-id="eed44-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="eed44-153">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="eed44-153">Accumulated depreciation</span></span>

<span data-ttu-id="eed44-154">A számla a ROU-eszköz elleneszköz-számlájához van társítva.</span><span class="sxs-lookup"><span data-stu-id="eed44-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="eed44-155">Ezen a számlán az értékcsökkenési költség feladásakor egy követel tétel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="eed44-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="eed44-156">**Példa naplóbejegyzések:** Értékcsökkenés-elhatárolás</span><span class="sxs-lookup"><span data-stu-id="eed44-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="eed44-157">**Terhelés:** XXX értékcsökkenési költség</span><span class="sxs-lookup"><span data-stu-id="eed44-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="eed44-158">**Jóváírás:** XXX halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="eed44-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="eed44-159">Változó fizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-159">Variable payment</span></span>

<span data-ttu-id="eed44-160">A számla olyan változó lízingfizetésekhez kapcsolódik, amelyeket az ASC 842, ASC 840 és IAS 17 lízingek indexátértékelése alapján állítanak elő.</span><span class="sxs-lookup"><span data-stu-id="eed44-160">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="eed44-161">A lízingfizetési ütemezésben a változó fizetések a **Változó fizetés** oszlopban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="eed44-161">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="eed44-162">Ez a számla terhelt, ha számlát hoz létre egy változó kifizetést tartalmazó fizetési ütemezési sorral szemben.</span><span class="sxs-lookup"><span data-stu-id="eed44-162">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="eed44-163">**Példa naplóbejegyzések:** Lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-163">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="eed44-164">**Terhelés:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-164">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="eed44-165">**Terhelés:** XXX változó fizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-165">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="eed44-166">**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-166">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="eed44-167">Halasztott bérleti díjjal rendelkező eszköz (kötelezettség)</span><span class="sxs-lookup"><span data-stu-id="eed44-167">Deferred rent asset (liability)</span></span>

<span data-ttu-id="eed44-168">A számla a halasztott bérleti díj eszközhöz vagy kötelezettséghez kapcsolódik, amelyet egy halasztott bérleti díjkezelési lízing állít elő.</span><span class="sxs-lookup"><span data-stu-id="eed44-168">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="eed44-169">Ez a számla akkor lesz megterhelve, ha a számlát halasztott bérleti díjkezelési lízinggel szemben adják fel, ha a lízing kifizetésének összege meghaladja az időszak egyenes körű bérleti költségeit.</span><span class="sxs-lookup"><span data-stu-id="eed44-169">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="eed44-170">Jóváírásra kerül, ha a lízingfizetés kisebb, mint az időszak lineáris bérleti költsége.</span><span class="sxs-lookup"><span data-stu-id="eed44-170">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="eed44-171">**Példa naplóbejegyzésekre:** Lízingfizetés (halasztott bérleti díjkezelési lízing)</span><span class="sxs-lookup"><span data-stu-id="eed44-171">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="eed44-172">**Terhelés:** XXX bérleti költség</span><span class="sxs-lookup"><span data-stu-id="eed44-172">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="eed44-173">**Jóváírás:** Halasztott bérleti díj kötelezettség XXX</span><span class="sxs-lookup"><span data-stu-id="eed44-173">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="eed44-174">**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-174">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="eed44-175">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="eed44-175">Lease expense</span></span>

<span data-ttu-id="eed44-176">A számla akkor kapcsolódik a lízingköltséghez, ha a lízing halasztott bérleti díjkezelési lízingként van besorolva.</span><span class="sxs-lookup"><span data-stu-id="eed44-176">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="eed44-177">Ez a számla akkor kerül megterhelésre, ha egy számlát halasztott bérleti díjkezelési lízingbe adnak fel.</span><span class="sxs-lookup"><span data-stu-id="eed44-177">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="eed44-178">**Példa naplóbejegyzésekre:** Lízingfizetés (halasztott bérleti díjkezelési lízing)</span><span class="sxs-lookup"><span data-stu-id="eed44-178">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="eed44-179">**Terhelés:** XXX bérleti költség</span><span class="sxs-lookup"><span data-stu-id="eed44-179">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="eed44-180">**Jóváírás:** Halasztott bérleti díj kötelezettség XXX</span><span class="sxs-lookup"><span data-stu-id="eed44-180">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="eed44-181">**Jóváírás:** XXX szállítói kötelezettségek/lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-181">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="eed44-182">Értékvesztési költség</span><span class="sxs-lookup"><span data-stu-id="eed44-182">Impairment expense</span></span>

<span data-ttu-id="eed44-183">A fiók fel lesz adva, ha a lízing értékvesztett.</span><span class="sxs-lookup"><span data-stu-id="eed44-183">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="eed44-184">Ez a számla megterhelve, míg a ROU-eszközszámla közvetlenül jóváírásra kerül.</span><span class="sxs-lookup"><span data-stu-id="eed44-184">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="eed44-185">**Példa naplóbejegyzések:** Lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-185">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="eed44-186">**Terhelés:** Értékvesztési költség XXX</span><span class="sxs-lookup"><span data-stu-id="eed44-186">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="eed44-187">**Jóváírás:** ROU-eszköz XXX</span><span class="sxs-lookup"><span data-stu-id="eed44-187">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="eed44-188">Lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-188">Lease payment</span></span>

<span data-ttu-id="eed44-189">A számla fel lesz adva, ha a **Fizetés a szállítónak** paraméter ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="eed44-189">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="eed44-190">Ez a számla jóváírásra kerül a fizetendő szállító helyett, ha a paraméter ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="eed44-190">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="eed44-191">**Példa naplóbejegyzések:** Lízingdíjfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-191">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="eed44-192">**Terhelés:** XXX lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="eed44-192">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="eed44-193">**Jóváírás:** Lízingfizetés XXX</span><span class="sxs-lookup"><span data-stu-id="eed44-193">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="eed44-194">Költségtípus feladásai</span><span class="sxs-lookup"><span data-stu-id="eed44-194">Expense type postings</span></span>

<span data-ttu-id="eed44-195">Az egyes költségtípusokhoz kiválasztott számla terhelve van, amikor az adott költségtípushoz kifizetés jön létre.</span><span class="sxs-lookup"><span data-stu-id="eed44-195">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="eed44-196">Például a **Biztosítás** költségtípusához megadott számla meg lesz terhelve, amikor számla vagy kifizetési naplóbejegyzés jön létre a biztosítási költségek végrehajtási költségütemezéséből.</span><span class="sxs-lookup"><span data-stu-id="eed44-196">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="eed44-197">**Példa naplóbejegyzések:** Biztosításfizetés</span><span class="sxs-lookup"><span data-stu-id="eed44-197">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="eed44-198">**Terhelés:** Biztosítási költség típusú számla XXX</span><span class="sxs-lookup"><span data-stu-id="eed44-198">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="eed44-199">**Jóváírás:** Ellenszámla XXX</span><span class="sxs-lookup"><span data-stu-id="eed44-199">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="eed44-200">Az ellenszámla a végrehajtási költségfizetési ütemezés soraiban a lízing szintjén van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="eed44-200">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="eed44-201">Ez az ellenszámla társítható a szállítóhoz vagy egy főkönyvi számlához.</span><span class="sxs-lookup"><span data-stu-id="eed44-201">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

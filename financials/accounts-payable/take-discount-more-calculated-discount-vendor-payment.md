---
title: "A szállítói kifizetésre vonatkozóan kiszámított engedménynél nagyobb engedmény alkalmazása"
description: "A cikk végigvezeti egy eseten, ahol egy készpénzfizetési engedmény nagyobb, mint az az engedmény, ami a számlán eredeti rendelkezésre álló összegként szerepelt. Ez az eset akkor fordulhat elő, ha egy szervezet megállapodik a szállítóval a számlán szereplő kisebb összeg kifizetésére."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 39830014593b7b1bc2868afffcca0f77a0c8a029
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="e2dc1-104">A szállítói kifizetésre vonatkozóan kiszámított engedménynél nagyobb engedmény alkalmazása</span><span class="sxs-lookup"><span data-stu-id="e2dc1-104">Take a discount that is more than the calculated discount for a vendor payment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e2dc1-105">A cikk végigvezeti egy eseten, ahol egy készpénzfizetési engedmény nagyobb, mint az az engedmény, ami a számlán eredeti rendelkezésre álló összegként szerepelt.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="e2dc1-106">Ez az eset akkor fordulhat elő, ha egy szervezet megállapodik a szállítóval a számlán szereplő kisebb összeg kifizetésére.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="e2dc1-107">A 3051. számú szállító 4 százalékos készpénzfizetési engedményt ad a Fabrikamnak, ha a számlát hét napon belül fizetik.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="e2dc1-108">Június 29-én April egy 1000,00 értékű számlát rögzít.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="e2dc1-109">A szállító 60,00 értékű kedvezményt ad Aprilnek az alapértelmezett engedmény helyett, amely a számlára vonatkozóan 40,00 lenne.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="e2dc1-110">April egyszeri kifizetést rögzít a Kötelezettségek fizetési naplóban.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="e2dc1-111">Megadja a kifizetéshez tartozó szállítót, majd megnyitja a **Tranzakciók kiegyenlítése** oldalt.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="e2dc1-112">Megjelöli a számlát, és a **Készpénzfizetési engedmény összege** mezőt **-60,00** értékre módosítja.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>
| <span data-ttu-id="e2dc1-113">Jelölés</span><span class="sxs-lookup"><span data-stu-id="e2dc1-113">Mark</span></span>     | <span data-ttu-id="e2dc1-114">Készpénzfizetési engedmény használata</span><span class="sxs-lookup"><span data-stu-id="e2dc1-114">Use cash discount</span></span> | <span data-ttu-id="e2dc1-115">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="e2dc1-115">Voucher</span></span>   | <span data-ttu-id="e2dc1-116">Fiók</span><span class="sxs-lookup"><span data-stu-id="e2dc1-116">Account</span></span> | <span data-ttu-id="e2dc1-117">Dátum</span><span class="sxs-lookup"><span data-stu-id="e2dc1-117">Date</span></span>      | <span data-ttu-id="e2dc1-118">Fiz. határidő</span><span class="sxs-lookup"><span data-stu-id="e2dc1-118">Due date</span></span>  | <span data-ttu-id="e2dc1-119">Számla</span><span class="sxs-lookup"><span data-stu-id="e2dc1-119">Invoice</span></span> | <span data-ttu-id="e2dc1-120">Összeg a tranzakció pénznemében.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-120">Amount in transaction currency</span></span> | <span data-ttu-id="e2dc1-121">Pénznem</span><span class="sxs-lookup"><span data-stu-id="e2dc1-121">Currency</span></span> | <span data-ttu-id="e2dc1-122">Kiegyenlítendő összeg</span><span class="sxs-lookup"><span data-stu-id="e2dc1-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="e2dc1-123">Kijelölve</span><span class="sxs-lookup"><span data-stu-id="e2dc1-123">Selected</span></span> | <span data-ttu-id="e2dc1-124">Normál</span><span class="sxs-lookup"><span data-stu-id="e2dc1-124">Normal</span></span>            | <span data-ttu-id="e2dc1-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="e2dc1-125">Inv-10040</span></span> | <span data-ttu-id="e2dc1-126">3051</span><span class="sxs-lookup"><span data-stu-id="e2dc1-126">3051</span></span>    | <span data-ttu-id="e2dc1-127">2015/29/6</span><span class="sxs-lookup"><span data-stu-id="e2dc1-127">6/29/2015</span></span> | <span data-ttu-id="e2dc1-128">2015/29/7</span><span class="sxs-lookup"><span data-stu-id="e2dc1-128">7/29/2015</span></span> | <span data-ttu-id="e2dc1-129">10040</span><span class="sxs-lookup"><span data-stu-id="e2dc1-129">10040</span></span>   | <span data-ttu-id="e2dc1-130">1000,00</span><span class="sxs-lookup"><span data-stu-id="e2dc1-130">1,000.00</span></span>                       | <span data-ttu-id="e2dc1-131">dollár</span><span class="sxs-lookup"><span data-stu-id="e2dc1-131">USD</span></span>      | <span data-ttu-id="e2dc1-132">940,00</span><span class="sxs-lookup"><span data-stu-id="e2dc1-132">940.00</span></span>           |

<span data-ttu-id="e2dc1-133">Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>
|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="e2dc1-134">Készpénzfizetési engedmény dátuma</span><span class="sxs-lookup"><span data-stu-id="e2dc1-134">Cash discount date</span></span>           | <span data-ttu-id="e2dc1-135">2015/7/12</span><span class="sxs-lookup"><span data-stu-id="e2dc1-135">7/12/2015</span></span> |
| <span data-ttu-id="e2dc1-136">Készpénzfizetési engedmény összege</span><span class="sxs-lookup"><span data-stu-id="e2dc1-136">Cash discount amount</span></span>         | <span data-ttu-id="e2dc1-137">60,00</span><span class="sxs-lookup"><span data-stu-id="e2dc1-137">60.00</span></span>     |
| <span data-ttu-id="e2dc1-138">Készpénzfizetési engedmény használata</span><span class="sxs-lookup"><span data-stu-id="e2dc1-138">Use cash discount</span></span>            | <span data-ttu-id="e2dc1-139">Normál</span><span class="sxs-lookup"><span data-stu-id="e2dc1-139">Normal</span></span>    |
| <span data-ttu-id="e2dc1-140">Alkalmazott készpénzfizetési engedmény</span><span class="sxs-lookup"><span data-stu-id="e2dc1-140">Cash discount taken</span></span>          | <span data-ttu-id="e2dc1-141">0,00</span><span class="sxs-lookup"><span data-stu-id="e2dc1-141">0.00</span></span>      |
| <span data-ttu-id="e2dc1-142">Alkalmazandó készpénzfizetési engedmény összege</span><span class="sxs-lookup"><span data-stu-id="e2dc1-142">Cash discount amount to take</span></span> | <span data-ttu-id="e2dc1-143">60,00</span><span class="sxs-lookup"><span data-stu-id="e2dc1-143">60.00</span></span>     |

<span data-ttu-id="e2dc1-144">April ezután feladja ezt a naplót.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-144">April posts the payment journal.</span></span> <span data-ttu-id="e2dc1-145">A számla teljesen ki van egyenlítve a 940,00 értékű fizetéssel és a 60,00 engedménnyel.</span><span class="sxs-lookup"><span data-stu-id="e2dc1-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>





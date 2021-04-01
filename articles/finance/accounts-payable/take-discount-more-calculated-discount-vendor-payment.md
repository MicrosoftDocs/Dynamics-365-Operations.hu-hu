---
title: A szállítói kifizetésre vonatkozóan kiszámított engedménynél nagyobb engedmény alkalmazása
description: A cikk végigvezeti egy eseten, ahol egy készpénzfizetési engedmény nagyobb, mint az az engedmény, ami a számlán eredeti rendelkezésre álló összegként szerepelt. Ez az eset akkor fordulhat elő, ha egy szervezet megállapodik a szállítóval a számlán szereplő kisebb összeg kifizetésére.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a56331f76867aeac0bad0912749d96f959513e0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235885"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="1940f-104">A szállítói kifizetésre vonatkozóan kiszámított engedménynél nagyobb engedmény alkalmazása</span><span class="sxs-lookup"><span data-stu-id="1940f-104">Take more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1940f-105">A cikk végigvezeti egy eseten, ahol egy készpénzfizetési engedmény nagyobb, mint az az engedmény, ami a számlán eredeti rendelkezésre álló összegként szerepelt.</span><span class="sxs-lookup"><span data-stu-id="1940f-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="1940f-106">Ez az eset akkor fordulhat elő, ha egy szervezet megállapodik a szállítóval a számlán szereplő kisebb összeg kifizetésére.</span><span class="sxs-lookup"><span data-stu-id="1940f-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="1940f-107">A 3051. számú szállító 4 százalékos készpénzfizetési engedményt ad a Fabrikamnak, ha a számlát hét napon belül fizetik.</span><span class="sxs-lookup"><span data-stu-id="1940f-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="1940f-108">Június 29-én April egy 1000,00 értékű számlát rögzít.</span><span class="sxs-lookup"><span data-stu-id="1940f-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="1940f-109">A szállító 60,00 értékű kedvezményt ad Aprilnek az alapértelmezett engedmény helyett, amely a számlára vonatkozóan 40,00 lenne.</span><span class="sxs-lookup"><span data-stu-id="1940f-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="1940f-110">April egyszeri kifizetést rögzít a Kötelezettségek fizetési naplóban.</span><span class="sxs-lookup"><span data-stu-id="1940f-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="1940f-111">Megadja a kifizetéshez tartozó szállítót, majd megnyitja a **Tranzakciók kiegyenlítése** oldalt.</span><span class="sxs-lookup"><span data-stu-id="1940f-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="1940f-112">Megjelöli a számlát, és a **Készpénzfizetési engedmény összege** mezőt **-60,00** értékre módosítja.</span><span class="sxs-lookup"><span data-stu-id="1940f-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="1940f-113">Jelölés</span><span class="sxs-lookup"><span data-stu-id="1940f-113">Mark</span></span>     | <span data-ttu-id="1940f-114">Készpénzfizetési engedmény használata</span><span class="sxs-lookup"><span data-stu-id="1940f-114">Use cash discount</span></span> | <span data-ttu-id="1940f-115">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="1940f-115">Voucher</span></span>   | <span data-ttu-id="1940f-116">Fiók</span><span class="sxs-lookup"><span data-stu-id="1940f-116">Account</span></span> | <span data-ttu-id="1940f-117">Dátum</span><span class="sxs-lookup"><span data-stu-id="1940f-117">Date</span></span>      | <span data-ttu-id="1940f-118">Fiz. határidő</span><span class="sxs-lookup"><span data-stu-id="1940f-118">Due date</span></span>  | <span data-ttu-id="1940f-119">Számla</span><span class="sxs-lookup"><span data-stu-id="1940f-119">Invoice</span></span> | <span data-ttu-id="1940f-120">Összeg a tranzakció pénznemében.</span><span class="sxs-lookup"><span data-stu-id="1940f-120">Amount in transaction currency</span></span> | <span data-ttu-id="1940f-121">Pénznem</span><span class="sxs-lookup"><span data-stu-id="1940f-121">Currency</span></span> | <span data-ttu-id="1940f-122">Kiegyenlítendő összeg</span><span class="sxs-lookup"><span data-stu-id="1940f-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="1940f-123">Kijelölve</span><span class="sxs-lookup"><span data-stu-id="1940f-123">Selected</span></span> | <span data-ttu-id="1940f-124">Normál</span><span class="sxs-lookup"><span data-stu-id="1940f-124">Normal</span></span>            | <span data-ttu-id="1940f-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="1940f-125">Inv-10040</span></span> | <span data-ttu-id="1940f-126">3051</span><span class="sxs-lookup"><span data-stu-id="1940f-126">3051</span></span>    | <span data-ttu-id="1940f-127">2015/29/6</span><span class="sxs-lookup"><span data-stu-id="1940f-127">6/29/2015</span></span> | <span data-ttu-id="1940f-128">2015/29/7</span><span class="sxs-lookup"><span data-stu-id="1940f-128">7/29/2015</span></span> | <span data-ttu-id="1940f-129">10040</span><span class="sxs-lookup"><span data-stu-id="1940f-129">10040</span></span>   | <span data-ttu-id="1940f-130">1000,00</span><span class="sxs-lookup"><span data-stu-id="1940f-130">1,000.00</span></span>                       | <span data-ttu-id="1940f-131">dollár</span><span class="sxs-lookup"><span data-stu-id="1940f-131">USD</span></span>      | <span data-ttu-id="1940f-132">940,00</span><span class="sxs-lookup"><span data-stu-id="1940f-132">940.00</span></span>           |

<span data-ttu-id="1940f-133">Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="1940f-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="1940f-134">Készpénzfizetési engedmény dátuma</span><span class="sxs-lookup"><span data-stu-id="1940f-134">Cash discount date</span></span>           | <span data-ttu-id="1940f-135">2015/7/12</span><span class="sxs-lookup"><span data-stu-id="1940f-135">7/12/2015</span></span> |
| <span data-ttu-id="1940f-136">Készpénzfizetési engedmény összege</span><span class="sxs-lookup"><span data-stu-id="1940f-136">Cash discount amount</span></span>         | <span data-ttu-id="1940f-137">60,00</span><span class="sxs-lookup"><span data-stu-id="1940f-137">60.00</span></span>     |
| <span data-ttu-id="1940f-138">Készpénzfizetési engedmény használata</span><span class="sxs-lookup"><span data-stu-id="1940f-138">Use cash discount</span></span>            | <span data-ttu-id="1940f-139">Normál</span><span class="sxs-lookup"><span data-stu-id="1940f-139">Normal</span></span>    |
| <span data-ttu-id="1940f-140">Alkalmazott készpénzfizetési engedmény</span><span class="sxs-lookup"><span data-stu-id="1940f-140">Cash discount taken</span></span>          | <span data-ttu-id="1940f-141">0,00</span><span class="sxs-lookup"><span data-stu-id="1940f-141">0.00</span></span>      |
| <span data-ttu-id="1940f-142">Alkalmazandó készpénzfizetési engedmény összege</span><span class="sxs-lookup"><span data-stu-id="1940f-142">Cash discount amount to take</span></span> | <span data-ttu-id="1940f-143">60,00</span><span class="sxs-lookup"><span data-stu-id="1940f-143">60.00</span></span>     |

<span data-ttu-id="1940f-144">April ezután feladja ezt a naplót.</span><span class="sxs-lookup"><span data-stu-id="1940f-144">April posts the payment journal.</span></span> <span data-ttu-id="1940f-145">A számla teljesen ki van egyenlítve a 940,00 értékű fizetéssel és a 60,00 engedménnyel.</span><span class="sxs-lookup"><span data-stu-id="1940f-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
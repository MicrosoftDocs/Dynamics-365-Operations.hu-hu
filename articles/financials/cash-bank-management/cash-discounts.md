---
title: "Készpénzfizetési engedmények"
description: "A készpénzfizetési engedmények be vannak állítva és a meg vannak osztva a kötelezettségek és kinnlevőségek számára.  Az elérhető készpénzfizetési engedmény megadható a vevői számlán vagy a szállítói számlán, és ott meg fog jelenni, ha a számla kifizetése megtörténik a készpénzfizetési engedmény dátuma előtt."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 668e3ebdd2729efb48e2833fd5beec3cefdb17b0
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="cash-discounts"></a><span data-ttu-id="8b757-104">Készpénzfizetési engedmények</span><span class="sxs-lookup"><span data-stu-id="8b757-104">Cash discounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8b757-105">A készpénzfizetési engedmények be vannak állítva és a meg vannak osztva a kötelezettségek és kinnlevőségek számára.</span><span class="sxs-lookup"><span data-stu-id="8b757-105">Cash discounts are setup and shared for Accounts payable and Accounts receivable.</span></span>  <span data-ttu-id="8b757-106">Az elérhető készpénzfizetési engedmény megadható a vevői számlán vagy a szállítói számlán, és ott meg fog jelenni, ha a számla kifizetése megtörténik a készpénzfizetési engedmény dátuma előtt.</span><span class="sxs-lookup"><span data-stu-id="8b757-106">The cash discount available can be defined on the customer invoice or vendor invoice, and will be taken if the invoice is paid within the cash discount date.</span></span> 

<a name="cash-discounts"></a><span data-ttu-id="8b757-107">Készpénzfizetési engedmények</span><span class="sxs-lookup"><span data-stu-id="8b757-107">Cash discounts</span></span>
--------------

<span data-ttu-id="8b757-108">A vevők vagy szállítók készpénzfizetési engedményei a készpénzfizetési engedmények lapján is létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="8b757-108">Cash discounts for both customers or vendors can be created in the Cash discounts page.</span></span> <span data-ttu-id="8b757-109">Azt is meghatározhatja a Következő engedmény kód mező használatával, hogy követik egymást az előző készpénzfizetési engedmény dátum lejárataként.</span><span class="sxs-lookup"><span data-stu-id="8b757-109">You can also define, by using the Next discount code field, a series of cash discounts that succeed each other as previous cash discount dates expire.</span></span> <span data-ttu-id="8b757-110">További tájékoztatás, lásd "Példa: készpénzfizetési engedmények sorozata" később a témakörben.</span><span class="sxs-lookup"><span data-stu-id="8b757-110">For more information, see “Example: Series of cash discounts” later in this topic.</span></span> <span data-ttu-id="8b757-111">Ha a számla vagy jóváírási tranzakció (jóváírás vagy kifizetés) vagy mindekettő a jogi személy könyvelési pénznemében eltérő pénznemben vannak megadva, a készpénzfizetési engedmény számítása a kifizetések vagy jóváírások napja alapján az érvényes árfolyamának felhasználásával történik.</span><span class="sxs-lookup"><span data-stu-id="8b757-111">If the invoice, credit transaction (either a payment or a credit note), or both are entered in a currency other than the accounting currency of the legal entity, the cash discount is calculated using the exchange rate based on the date of the payment or credit note.</span></span> <span data-ttu-id="8b757-112">Ha a számlák és jóváírási bizonylat különböző jogi személyek esetében vannak megadva, és ha a jogi személyek könyvelési pénznemei különböznek, az átváltási árfolyam a számla jogi személyétől származnak, mint a hitel dokumentum dátuma.</span><span class="sxs-lookup"><span data-stu-id="8b757-112">If the invoice and credit document are entered in different legal entities, and if the accounting currencies for the legal entities differ, the exchange rate is taken from the legal entity of the invoice, as of the date of the credit document.</span></span> <span data-ttu-id="8b757-113">További információkat, lásd "Példa: készpénzfizetési engedmények átváltási díjai" később a témakörben.</span><span class="sxs-lookup"><span data-stu-id="8b757-113">For more information, see “Example: Exchange rates for cash discounts” later in this topic.</span></span>
<span data-ttu-id="8b757-114">Fő számla készpénzfizetési engedmény alapértelmezési sorrendje</span><span class="sxs-lookup"><span data-stu-id="8b757-114">Defaulting order of cash discount main account</span></span>
----------------------------------------------

<span data-ttu-id="8b757-115">Ha a számla kiegyenlítése időben megtörténik ahhoz, hogy a vevő készpénzfizetési engedményt kapjon, a program automatikusan feladja a készpénzfizetési engedményt a készpénzfizetési engedmény fő számlájára, az alábbi alapértelmezési prioritást figyelembe véve:</span><span class="sxs-lookup"><span data-stu-id="8b757-115">If an invoice is settled in time to obtain a cash discount, the cash discount is automatically posted to a cash discount main account according to the following defaulting priority:</span></span>
1.  <span data-ttu-id="8b757-116">A fő számla a vevői váltókiegyenlítési nyitott tranzakciók vagy a szállítói kiegyenlítési nyitott tranzakciók lapon a másik készpénzfizetésiengedmény-számla mezőben van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="8b757-116">The main account specified in the Alternative cash discount account field on the customer Settle open transactions page or the vendor Settle open transactions page.</span></span>
2.  <span data-ttu-id="8b757-117">A fő számla a számla adókódjához rendelt főkönyv feladó csoport Vevő készpénzfizetési engedmény mezőjében vagy a szállító készpénzfizetési engedmény mezőjében van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="8b757-117">The main account specified in the Customer cash discount field or the Vendor cash discount field of the ledger posting group that is assigned to the sales tax code of the invoice.</span></span> <span data-ttu-id="8b757-118">Állítsa be a főkönyvi feladási csoportokat a főkönyvi feladási csoportok lapon, és rendelje hozzá az áfakódokhoz a forgalmi adó kódjainak lapján.</span><span class="sxs-lookup"><span data-stu-id="8b757-118">Set up ledger posting groups on the Ledger posting groups page and assign them to sales tax codes in the Sales tax codes page.</span></span>
3.  <span data-ttu-id="8b757-119">A fő feladási számla a készpénzfizetési engedmények lapján vagy a vevő Fő számlája engedmények mezőben vagy a Szállító Fő számlája mezőben a kiegyenlített számláko szereplő készpénzfizetési engedmény kódokhoz.</span><span class="sxs-lookup"><span data-stu-id="8b757-119">The main posting account on the Cash discounts page in either the Main account for customer discounts field or the Main account for vendor discounts field for the cash discount code that is on the settled invoice.</span></span>
4.  <span data-ttu-id="8b757-120">A készpénzfizetési engedmények fő számlája az automatikus tranzakciók lapok számláján van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="8b757-120">The main account for cash discounts, as defined in the Accounts for automatic transactions page.</span></span>

## <a name="example-series-of-cash-discounts"></a><span data-ttu-id="8b757-121"> Példa: Készpénzfizetési engedmények sorozatai</span><span class="sxs-lookup"><span data-stu-id="8b757-121">Example: Series of cash discounts</span></span>
<span data-ttu-id="8b757-122">Állítson be három kódot a készpénzfizetési engedményekhez a következők szerint:</span><span class="sxs-lookup"><span data-stu-id="8b757-122">Set up three cash discount codes as follows:</span></span>
-   <span data-ttu-id="8b757-123">5D10% kód - 10%-os készpénzfizetési engedmény, amikor az összeg 5 napon belül kerül kiegyenlítésre.</span><span class="sxs-lookup"><span data-stu-id="8b757-123">Code 5D10% – A cash discount of 10% when the amount is paid within 5 days.</span></span>
-   <span data-ttu-id="8b757-124">10D5% kód - 5%-os készpénzfizetési engedmény, ha az összeg 10 napon belül kerül kiegyenlítésre.</span><span class="sxs-lookup"><span data-stu-id="8b757-124">Code 10D5% – A cash discount of 5% when the amount is paid within 10 days.</span></span>
-   <span data-ttu-id="8b757-125">14D2% kód - 2%-os készpénzfizetési engedmény, ha az összeg 14 napon belül kerül kiegyenlítésre.</span><span class="sxs-lookup"><span data-stu-id="8b757-125">Code 14D2% – A cash discount of 2% when the amount is paid within 14 days.</span></span>

<span data-ttu-id="8b757-126">A Következő engedmény kódja mezőben:</span><span class="sxs-lookup"><span data-stu-id="8b757-126">In the Next discount code field:</span></span>
-   <span data-ttu-id="8b757-127">Az 5D10% kódnál válassza a 10D5% elemet.</span><span class="sxs-lookup"><span data-stu-id="8b757-127">For the 5D10% code, select 10D5%.</span></span>
-   <span data-ttu-id="8b757-128">A 10D5% kódnál válassza a 14D2% elemet.</span><span class="sxs-lookup"><span data-stu-id="8b757-128">For the 10D5% code, select 14D2%.</span></span>
-   <span data-ttu-id="8b757-129">A 14N2% kódnál hagyja üresen a Következő engedménykód mezőt.</span><span class="sxs-lookup"><span data-stu-id="8b757-129">For the 14D2% code, leave the Next discount code field blank.</span></span>

<span data-ttu-id="8b757-130">A készpénzfizetési engedmény három kódja követi egymást mivel a fizetési dátum meghaladja a számlán szereplő előző készpénzfizetési engedmény dátumát.</span><span class="sxs-lookup"><span data-stu-id="8b757-130">The three cash discounts succeed each other as the payment date exceeds the previous cash discount date on the invoice.</span></span> <span data-ttu-id="8b757-131">Egy készpénzfizetési engedmény csak akkor van engedélyezve, amikro a számla ki van egyenlítve, azon alapul, hogy melyik készpénzfizetési engedmény dátuma felel meg a készpénzfizetési engedmények sorozatában.</span><span class="sxs-lookup"><span data-stu-id="8b757-131">Only one cash discount is granted when the invoice is paid, based on which cash discount date is meet in the sequence of cash discounts.</span></span>

## <a name="example-exchange-rates-for-cash-discounts"></a><span data-ttu-id="8b757-132"> Példa: Készpénzfizetési engedmények átváltási díjai</span><span class="sxs-lookup"><span data-stu-id="8b757-132">Example: Exchange rates for cash discounts</span></span>
<span data-ttu-id="8b757-133">A jogi személy könyvelési pénzneme EUR és a következő árfolyamok USD-ben vannak megadva:</span><span class="sxs-lookup"><span data-stu-id="8b757-133">Your legal entity’s accounting currency is EUR and the following exchange rates are specified for USD:</span></span>
-   <span data-ttu-id="8b757-134">február 1 = 110</span><span class="sxs-lookup"><span data-stu-id="8b757-134">February 1 = 110</span></span>
-   <span data-ttu-id="8b757-135">március 1 = 80</span><span class="sxs-lookup"><span data-stu-id="8b757-135">March 1 = 80</span></span>

<span data-ttu-id="8b757-136">Február 15-én adnak fel egy 20D2%-os készpénzfizetési engedménnyel rendelkező 1000 USD-s számlát.</span><span class="sxs-lookup"><span data-stu-id="8b757-136">An invoice for 1000 USD with cash discount terms of 20D2% is posted on February 15.</span></span> <span data-ttu-id="8b757-137">A számla összege a könyvelési pénznemben 1100 EUR.</span><span class="sxs-lookup"><span data-stu-id="8b757-137">The accounting currency amount of the invoice is 1100 EUR.</span></span> <span data-ttu-id="8b757-138">A számlaösszegből 980 USD kifizetése történik meg március 1-jén.</span><span class="sxs-lookup"><span data-stu-id="8b757-138">A payment for 980 USD is settled with the invoice on March 1.</span></span> <span data-ttu-id="8b757-139">A készpénzfizetési engedmény összege 20 USD.</span><span class="sxs-lookup"><span data-stu-id="8b757-139">The cash discount amount is 20 USD.</span></span> <span data-ttu-id="8b757-140">A fizetés könyvelési pénznemének összege 784 EUR.</span><span class="sxs-lookup"><span data-stu-id="8b757-140">The accounting currency amount of the payment is 784 EUR.</span></span> <span data-ttu-id="8b757-141">A készpénzfizetési engedmény összegének a könyvelési pénznemben történő kiszámítása március 1-jei átváltási árfolyam alapján történik: 20 \* 80 / 100 = 16 EUR.</span><span class="sxs-lookup"><span data-stu-id="8b757-141">The accounting currency amount of the cash discount is calculated by using the exchange rate as of March 1: 20 \* 80 / 100 = 16 EUR.</span></span>
| <span data-ttu-id="8b757-142">**Megjegyzés**</span><span class="sxs-lookup"><span data-stu-id="8b757-142">**Note**</span></span>                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8b757-143">Ha a részfizetés beállítás készpénzfizetési engedmény számítása van kiválasztva a Számla kötelezettségek paramétereinek vagy a Kötelezettségi paramétereinek lapjain, az az átváltási díj használatos, amely hatással van minden egyes részlet fizetés dátumára.</span><span class="sxs-lookup"><span data-stu-id="8b757-143">If the Calculate cash discounts for partial payments option is selected in the Accounts receivable parameters or Accounts payable parameters pages, the exchange rate that is in effect on the date of each partial payment is used.</span></span> |

 
=

 




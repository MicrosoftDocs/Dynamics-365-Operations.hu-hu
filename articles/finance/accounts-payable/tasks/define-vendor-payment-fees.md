---
title: Szállítói kifizetési díjak meghatározása
description: Szállítói kifizetési díjak beállítása.
author: abruer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e0871e0889b078c08e4bcbd86bf749bcfe39463
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837264"
---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="0f15c-103">Szállítói kifizetési díjak meghatározása</span><span class="sxs-lookup"><span data-stu-id="0f15c-103">Define vendor payment fees</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0f15c-104">Szállítói kifizetési díjak beállítása.</span><span class="sxs-lookup"><span data-stu-id="0f15c-104">Set up vendor payment fees.</span></span> <span data-ttu-id="0f15c-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0f15c-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="0f15c-106">Ugrás a Kötelezettségek > Kifizetés beállítása > Fizetési díj elemre.</span><span class="sxs-lookup"><span data-stu-id="0f15c-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="0f15c-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f15c-107">Click New.</span></span>
3. <span data-ttu-id="0f15c-108">Írjon be egy értéket a Díj azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0f15c-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="0f15c-109">A díj azonosítójának mutatnia kell, hogy mikor használatos a díj, pl. „elektronikus átutalási díj”.</span><span class="sxs-lookup"><span data-stu-id="0f15c-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="0f15c-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0f15c-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0f15c-111">A „Díj leírása” mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0f15c-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="0f15c-112">Adjon meg leírást, amelyben további részleteket közöl a díj értékeléséről.</span><span class="sxs-lookup"><span data-stu-id="0f15c-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="0f15c-113">A Költség mezőben válassza ki a Szállító vagy Főkönyv lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0f15c-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="0f15c-114">A főkönyv akkor kerül használatra, ha a díj költségként megjelenik a szervezetében.</span><span class="sxs-lookup"><span data-stu-id="0f15c-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="0f15c-115">A Szállítót akkor használja, ha a díj a szállítónál kerül értékelésre.</span><span class="sxs-lookup"><span data-stu-id="0f15c-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="0f15c-116">Adjon meg egy fő számlát, ahová a díj elszámolása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="0f15c-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="0f15c-117">Ez a lehetőség csak akkor használható, ha meg van adva a Főkönyv a Költség lehetőségnél.</span><span class="sxs-lookup"><span data-stu-id="0f15c-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="0f15c-118">Válassza ki a naplót, amelyben ez a díj felhasználható.</span><span class="sxs-lookup"><span data-stu-id="0f15c-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="0f15c-119">Szállítói fizetési díj esetén válassza a „Szállítói kifizetés” naplót.</span><span class="sxs-lookup"><span data-stu-id="0f15c-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="0f15c-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0f15c-120">Click Save.</span></span>
10. <span data-ttu-id="0f15c-121">Kattintson a Kifizetési díj beállítására.</span><span class="sxs-lookup"><span data-stu-id="0f15c-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="0f15c-122">Folytassa a Fizetési díj beállítást, és adja meg a díj alapértelmezett idejét a kiválasztott naplóban.</span><span class="sxs-lookup"><span data-stu-id="0f15c-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="0f15c-123">Válassza ki a Tábla, Csoport vagy Összes lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0f15c-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="0f15c-124">A Tábla lehetőséget egyetlen bankszámla kiválasztására használhatja, a Csoporttal bankcsoportot választhat ki, az Összes lehetőséggel pedig minden bankszámlához használhatja a mostani díjbeállítást.</span><span class="sxs-lookup"><span data-stu-id="0f15c-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="0f15c-125">Válasszon bankcsoportot vagy bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="0f15c-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="0f15c-126">A keresés bankcsoportot jelenít meg, ha a Csoport lehetőséget választotta, és bankszámlákat, ha a Tábla lehetőséget választotta.</span><span class="sxs-lookup"><span data-stu-id="0f15c-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="0f15c-127">Válassza ki a fizetési módnál a díj értékelésének idejét.</span><span class="sxs-lookup"><span data-stu-id="0f15c-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="0f15c-128">Válassza ki a kiválasztott fizetési mód fizetési meghatározását.</span><span class="sxs-lookup"><span data-stu-id="0f15c-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="0f15c-129">A Fizetési meghatározás a kifizetések elektronikus alapok átutalási módjainak használatos.</span><span class="sxs-lookup"><span data-stu-id="0f15c-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="0f15c-130">Adja meg, hogy a díj százalék, összeg vagy intervallum legyen.</span><span class="sxs-lookup"><span data-stu-id="0f15c-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="0f15c-131">Adja meg a díj százalékos értékét vagy összegét.</span><span class="sxs-lookup"><span data-stu-id="0f15c-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="0f15c-132">Ha a díj százalék, adja meg a százalékot.</span><span class="sxs-lookup"><span data-stu-id="0f15c-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="0f15c-133">Ha a díj összeg, adja meg a díj összegét.</span><span class="sxs-lookup"><span data-stu-id="0f15c-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="0f15c-134">Ha a díj intervallum, az Intervallum lapon határozza meg a díjak szintjeit.</span><span class="sxs-lookup"><span data-stu-id="0f15c-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="0f15c-135">A Díj pénzneme mezőben válassza ki a díj értékelésének pénznemét.</span><span class="sxs-lookup"><span data-stu-id="0f15c-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="0f15c-136">Ez a pénznem a díjra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="0f15c-136">This currency is for the fee.</span></span> <span data-ttu-id="0f15c-137">A fizetési pénznem azt határozza meg, hogy a díj szabálya a fizetés pénzneme alapján kerüljön-e értékelésre.</span><span class="sxs-lookup"><span data-stu-id="0f15c-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="0f15c-138">Előfordulhat például, hogy a bank díjat számít fel, ha a fizetés EUR pénznemben történik, de az egyéb fizetések díjmentesek.</span><span class="sxs-lookup"><span data-stu-id="0f15c-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="0f15c-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0f15c-139">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
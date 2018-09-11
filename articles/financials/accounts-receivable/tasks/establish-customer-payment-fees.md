--- 
title: "Vevői kifizetések díjainak kialakítása"
description: "Fizetési díj létrehozása vevői kifizetésekhez."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 3be8db49bab80fa8765b685d73d54a42975870c3
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="establish-customer-payment-fees"></a><span data-ttu-id="e59cd-103">Vevői kifizetések díjainak kialakítása</span><span class="sxs-lookup"><span data-stu-id="e59cd-103">Establish customer payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e59cd-104">Fizetési díj létrehozása vevői kifizetésekhez.</span><span class="sxs-lookup"><span data-stu-id="e59cd-104">Create payment fees for customer payments.</span></span>

<span data-ttu-id="e59cd-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e59cd-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="e59cd-106">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési díj pontra.</span><span class="sxs-lookup"><span data-stu-id="e59cd-106">Go to Accounts receivable > Payments setup > Payment fee.</span></span>
2. <span data-ttu-id="e59cd-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e59cd-107">Click New.</span></span>
3. <span data-ttu-id="e59cd-108">A Díj azonosítója mezőben adjon meg egy azonosítót.</span><span class="sxs-lookup"><span data-stu-id="e59cd-108">In the Fee ID field, enter a Fee ID.</span></span>
    * <span data-ttu-id="e59cd-109">A díj azonosítója megjelenik a kifizetési naplókban, ezért érdemes leíróvá tenni, hogy megértse, milyen díj kezelésére történik.</span><span class="sxs-lookup"><span data-stu-id="e59cd-109">The Fee ID displays on payment journals, so make it descriptive to understand what fee is being assessed.</span></span>  
4. <span data-ttu-id="e59cd-110">A Név mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="e59cd-110">In the Name field, enter a fee Name.</span></span>
5. <span data-ttu-id="e59cd-111">A Díj leírása mezőben adjon meg egy leírást a díjhoz.</span><span class="sxs-lookup"><span data-stu-id="e59cd-111">In the Fee description field, enter a description for the fee.</span></span>
6. <span data-ttu-id="e59cd-112">Adja meg, hogy a díjat a vevőnek vagy a főkönyvnek számítsák fel.</span><span class="sxs-lookup"><span data-stu-id="e59cd-112">Select whether the fee will be charged to the Customer or a Ledger account.</span></span>
    * <span data-ttu-id="e59cd-113">Ha a vevő kezelte a díjat, válassza a Vevő lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e59cd-113">If the customer is assessed the fee, select Customer.</span></span> <span data-ttu-id="e59cd-114">Ha a díj kezelése a szervezetnél történik költségként, válassza a főkönyvet.</span><span class="sxs-lookup"><span data-stu-id="e59cd-114">If the fee will be assess to your organization as an expense, select Ledger.</span></span> <span data-ttu-id="e59cd-115">Ehhez válassza ki a Vevőt.</span><span class="sxs-lookup"><span data-stu-id="e59cd-115">For this task, select Customer.</span></span>  
7. <span data-ttu-id="e59cd-116">Válassza ki a naplótípust, amely használhatja ezt a kifizetési díjat.</span><span class="sxs-lookup"><span data-stu-id="e59cd-116">Select the type of  journal that can use this payment fee.</span></span>
    * <span data-ttu-id="e59cd-117">Ha ezeket a díjakat vevőkifizetéshez használja, a naplótípus valószínűleg vevői kifizetés.</span><span class="sxs-lookup"><span data-stu-id="e59cd-117">If these fees are used for customer payments, the journal type will likely be Customer payment.</span></span>  
8. <span data-ttu-id="e59cd-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e59cd-118">Click Save.</span></span>
9. <span data-ttu-id="e59cd-119">Kattintson a Kifizetési díj beállítására.</span><span class="sxs-lookup"><span data-stu-id="e59cd-119">Click Payment fee setup.</span></span>
    * <span data-ttu-id="e59cd-120">A kifizetési díj beállításában meghatározhatja a kifizetési díj értékelésének feltételét.</span><span class="sxs-lookup"><span data-stu-id="e59cd-120">The Payment fee setup is used to define the criteria for when the payment fee will be assessed.</span></span>  <span data-ttu-id="e59cd-121">Meghatározhatja például, hogy a díj akkor kerül kiszámításra, ha a bankszámla USMF OPER, és a fizetési mód csekk.</span><span class="sxs-lookup"><span data-stu-id="e59cd-121">For example, you can define that the fee will be calculated if the bank account is USMF OPER, and the method of payment is check.</span></span>  
10. <span data-ttu-id="e59cd-122">Válassza ki a Tábla, Csoport vagy Összes lehetőséget, hogy meghatározza, mely bankszámlák értékeljék ezt a díjat.</span><span class="sxs-lookup"><span data-stu-id="e59cd-122">Select either Table, Group or All to define which bank accounts will be assessed this fee.</span></span>
    * <span data-ttu-id="e59cd-123">Ha az Összes lehetőséget választja, minden bankszámla értékeli ezt a díjat.</span><span class="sxs-lookup"><span data-stu-id="e59cd-123">If you select All, all bank accounts could be assessed this fee.</span></span>  <span data-ttu-id="e59cd-124">Ha a Tábla lehetőséget választja, csak a kiválasztott bankszámla értékeli ezt a díjat.</span><span class="sxs-lookup"><span data-stu-id="e59cd-124">If you select Table, only the bank account you select could be assessed this fee.</span></span> <span data-ttu-id="e59cd-125">Ha a Csoport lehetőséget választja, csak a kiválasztott csoportban lévő bankszámlák értékelik ezt a díjat.</span><span class="sxs-lookup"><span data-stu-id="e59cd-125">If you select Group, only the bank accounts in the selected bank group could be assessed this fee.</span></span>  
11. <span data-ttu-id="e59cd-126">Válasszon bankcsoportot vagy bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="e59cd-126">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="e59cd-127">Ha a Tábla lehetőséget választja, a keresés megjeleníti a bankszámlákat.</span><span class="sxs-lookup"><span data-stu-id="e59cd-127">If you selected Table, the lookup will display bank accounts.</span></span> <span data-ttu-id="e59cd-128">Ha a Csoport lehetőséget választja, a keresés megjeleníti a bankcsoportokat.</span><span class="sxs-lookup"><span data-stu-id="e59cd-128">If you selected Group, the lookup will display bank groups.</span></span>  
12. <span data-ttu-id="e59cd-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e59cd-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e59cd-130">Válassza ki azt a Fizetési módot, amelyhez ezt a díjat értékelik.</span><span class="sxs-lookup"><span data-stu-id="e59cd-130">Select the Method of payment for which this fee will be assessed.</span></span>
    * <span data-ttu-id="e59cd-131">Például előfordulhat, hogy egy díjat akkor értékel a vevők számára, ha csekként küldenek fizetést elektronikus kifizetés helyett.</span><span class="sxs-lookup"><span data-stu-id="e59cd-131">For example, you may assess a fee to your customers if they send payments as a check, rather than as an electronic payment.</span></span>  
14. <span data-ttu-id="e59cd-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e59cd-132">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="e59cd-133">Ha szükséges, adja meg a kifizetés pénznemét.</span><span class="sxs-lookup"><span data-stu-id="e59cd-133">If relevant, enter a payment currency.</span></span>
    * <span data-ttu-id="e59cd-134">A kifizetés pénzneme további feltétel a díj értékelésére.</span><span class="sxs-lookup"><span data-stu-id="e59cd-134">The payment currency is used as an additional criteria for whether the fee will be assessed.</span></span>  <span data-ttu-id="e59cd-135">Például a bank további díjat számíthat fel az USD pénznemben megkapott kifizetésekre, mert az általános tranzakciók EUR pénznemben történnek.</span><span class="sxs-lookup"><span data-stu-id="e59cd-135">For example, your bank may charge an extra fee for payments received in USD currency, since they normally only transact in EUR currency.</span></span>  
16. <span data-ttu-id="e59cd-136">Adja meg, hogy a díj százalék, összeg vagy intervallum legyen.</span><span class="sxs-lookup"><span data-stu-id="e59cd-136">Select whether the fee will be a percent, amount or interval.</span></span>
17. <span data-ttu-id="e59cd-137">Adja meg a díj százalékát vagy összegét.</span><span class="sxs-lookup"><span data-stu-id="e59cd-137">Enter either percentage or amount of the fee.</span></span>
    * <span data-ttu-id="e59cd-138">Ha a Százalék/Összeg mező Százalék, akkor az itt bevitt érték százalék.</span><span class="sxs-lookup"><span data-stu-id="e59cd-138">If the Percentage/Amount field is Percent, then the value enter here will be a percentage.</span></span> <span data-ttu-id="e59cd-139">Ha a Százalék/Összeg mező Összeg, akkor az itt bevitt érték összeg.</span><span class="sxs-lookup"><span data-stu-id="e59cd-139">If the Percentage/Amount field is Amount, then the value you enter here will be an amount.</span></span> <span data-ttu-id="e59cd-140">Ha a Százalék/Összeg mező Intervallum, akkor a szintek meghatározásához használja az Intervallum lapot.</span><span class="sxs-lookup"><span data-stu-id="e59cd-140">If the Percentage/Amount field is Interval, use the Interval tab to define the tiers.</span></span>  
18. <span data-ttu-id="e59cd-141">A Díj pénzneme mezőben válassza ki a díj pénznemét.</span><span class="sxs-lookup"><span data-stu-id="e59cd-141">In the Fee currency field, select the currency of the fee.</span></span>
    * <span data-ttu-id="e59cd-142">A díj ebben a pénznemben kerül létrehozásra.</span><span class="sxs-lookup"><span data-stu-id="e59cd-142">This is the currency in which the fee will be created.</span></span>  
19. <span data-ttu-id="e59cd-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e59cd-143">Click Save.</span></span>



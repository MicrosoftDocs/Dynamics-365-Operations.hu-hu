--- 
title: "Vevői kifizetések feltételeinek kialakítása"
description: "Ez az eljárás a készpénzfizetési engedményt és az esedékességi dátumot állítja be."
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e0e43962bea3ff1c3adafa73da4ce3862963a51
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="establish-customer-payment-terms"></a><span data-ttu-id="d40aa-103">Vevői kifizetések feltételeinek kialakítása</span><span class="sxs-lookup"><span data-stu-id="d40aa-103">Establish customer payment terms</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d40aa-104">Ez az eljárás a készpénzfizetési engedményt és az esedékességi dátumot állítja be.</span><span class="sxs-lookup"><span data-stu-id="d40aa-104">This procedure defines a cash discount and due date setup.</span></span> <span data-ttu-id="d40aa-105">Ez az útmutató-feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d40aa-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="d40aa-106">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napok pontra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-106">Go to Accounts receivable > Payments setup > Payment days.</span></span>
    * <span data-ttu-id="d40aa-107">A fizetési feltételek beállítását a Kötelezettségek és a Kinnlevőségek közösen használják.</span><span class="sxs-lookup"><span data-stu-id="d40aa-107">The setup for the Terms of payment is shared for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="d40aa-108">Ha azt megadja ebben a modulban, úgy az a többi modulban is elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="d40aa-108">If you define it in module, it will be available in the other module also.</span></span> <span data-ttu-id="d40aa-109">Ebben a feladat-útmutatóban beállítom a Kinnlevőségekre vonatkozó fizetési feltételeket.</span><span class="sxs-lookup"><span data-stu-id="d40aa-109">For this task guide, I set up all the terms of payment under Accounts receivable.</span></span>  
2. <span data-ttu-id="d40aa-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d40aa-110">Click New.</span></span>
    * <span data-ttu-id="d40aa-111">Hozzon létre fizetési napot, amennyiben a fizetési feltételei a hét (hétfő, kedd stb.) vagy a hónap egy adott napját (5-e, 10-e stb.) írják elő.</span><span class="sxs-lookup"><span data-stu-id="d40aa-111">Create a payment day if your terms of payment require a specific day of the week (Monday, Tuesday, etc) or a specific date of the month (5th, 10th, etc).</span></span>  
3. <span data-ttu-id="d40aa-112">A fizetési nap mezőben szereplő fizetési naphoz adjon meg egy Fizetési nap mező azonosítót.</span><span class="sxs-lookup"><span data-stu-id="d40aa-112">In the Payment day field, enter an ID for the Payment day in the payment day field.</span></span>
4. <span data-ttu-id="d40aa-113">Adja meg a fizetési nap leírását a Leírás mezőben.</span><span class="sxs-lookup"><span data-stu-id="d40aa-113">In the Description field, enter a description of the payment day.</span></span>
5. <span data-ttu-id="d40aa-114">A hét/hónap mezőben válassza a Hét vagy a Hónap lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d40aa-114">In the Week/Month field, select either Week or Month.</span></span>
    * <span data-ttu-id="d40aa-115">Válassza ki a Hét lehetőséget, ha a hét egy adott napját szeretné megadni, például a hétfőt.</span><span class="sxs-lookup"><span data-stu-id="d40aa-115">If you want to enter a day of the week, such as Monday, select Week.</span></span> <span data-ttu-id="d40aa-116">Válassza ki a Hónap lehetőséget, ha a hónap egy adott napját szeretné megadni, például a 10-ét.</span><span class="sxs-lookup"><span data-stu-id="d40aa-116">If you want to enter a date in the month, such as the 10th, select Month.</span></span> <span data-ttu-id="d40aa-117">Ehhez a példához válassza a Hónap lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d40aa-117">Select Month for this example.</span></span>  
6. <span data-ttu-id="d40aa-118">Adjon meg egy dátumot A hónap napja mezőben.</span><span class="sxs-lookup"><span data-stu-id="d40aa-118">In the Day of month field, enter a date.</span></span>
    * <span data-ttu-id="d40aa-119">A dátumot szám formájában kell megadni, azaz például „10” és nem „10.”</span><span class="sxs-lookup"><span data-stu-id="d40aa-119">The date should be entered as a number, such as '10', and not as '10th'.</span></span>  
7. <span data-ttu-id="d40aa-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-120">Click Save.</span></span>
8. <span data-ttu-id="d40aa-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d40aa-121">Close the page.</span></span>
9. <span data-ttu-id="d40aa-122">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési feltételek pontra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-122">Go to Accounts receivable > Payments setup > Terms of payment.</span></span>
10. <span data-ttu-id="d40aa-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d40aa-123">Click New.</span></span>
    * <span data-ttu-id="d40aa-124">A fizetési feltételek segítségével tudja meghatározni az esedékességi dátum számítását.</span><span class="sxs-lookup"><span data-stu-id="d40aa-124">Terms of payment is used to define how the due dates will be calculated.</span></span> <span data-ttu-id="d40aa-125">A készpénzfizetési engedmény dátuma egy külön lapon kerül beállításra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-125">The cash discount date setup is defined in a separate page.</span></span>  
11. <span data-ttu-id="d40aa-126">A Fizetési feltételek mezőben adjon meg egy Fizetési feltételek mező azonosítót.</span><span class="sxs-lookup"><span data-stu-id="d40aa-126">In the Terms of payment field, enter an ID in the Terms of payment field.</span></span>
12. <span data-ttu-id="d40aa-127">Adjon meg egy leírást a Leírás mezőben.</span><span class="sxs-lookup"><span data-stu-id="d40aa-127">In the Description field, enter a description.</span></span>
13. <span data-ttu-id="d40aa-128">Válassza ki a fizetési módot, például: Utánvét, Nettó, Jelenlegi hónap stb.</span><span class="sxs-lookup"><span data-stu-id="d40aa-128">Select a Payment method such as COD, Net, Current month, etc.</span></span>
    * <span data-ttu-id="d40aa-129">A Fizetési mód segítségével tudja meghatározni az esedékességi dátum kiszámításának kezdetét.</span><span class="sxs-lookup"><span data-stu-id="d40aa-129">The Payment method is used to define the start of how the due will be calculated.</span></span>  <span data-ttu-id="d40aa-130">A rendszer például a Nettó értéket használja, ha az esedékességi dátum minden esetben a számladátumot követő, meghatározott számú nap vagy hónap.</span><span class="sxs-lookup"><span data-stu-id="d40aa-130">For example, Net is used if the due date is always a set number of months or days after the invoice date.</span></span> <span data-ttu-id="d40aa-131">Amennyiben a fizetés a számla ellenében esedékes, úgy használhatja az Utánvét lehetőséget, hogy a rendszer ne számoljon esedékességet.</span><span class="sxs-lookup"><span data-stu-id="d40aa-131">COD can be used to when payment is required upon invoice, so a due date wouldn't be calculated.</span></span> <span data-ttu-id="d40aa-132">Ehhez a feladat-útmutatóhoz válassza a Jelenlegi hónap lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d40aa-132">Select Current month for this task guide.</span></span>  
14. <span data-ttu-id="d40aa-133">Válasszon egy Fizetési napot, ha a számításban szerepel a hét egy adott napja vagy egy adott dátum.</span><span class="sxs-lookup"><span data-stu-id="d40aa-133">Select a Payment day if a specific day of the  week or date are included in the calculation.</span></span>
    * <span data-ttu-id="d40aa-134">Az Ön fizetési feltételei függvényében adja meg a kívánt Hónapok vagy Napok számát.</span><span class="sxs-lookup"><span data-stu-id="d40aa-134">Depending on your terms of payment, you may enter a quantity in Months or Days.</span></span> <span data-ttu-id="d40aa-135">Vagy használhatja a fizetési módhoz hozzáadandó Fizetési ütemezés vagy Fizetési nap lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d40aa-135">Or you can use the Payment schedule or Payment day to 'add' to the end of the Payment method.</span></span> <span data-ttu-id="d40aa-136">Amennyiben az esedékességi dátum minden esetben a következő hónap 10-e, úgy válassza ki a 10-ét, mint Fizetési napot.</span><span class="sxs-lookup"><span data-stu-id="d40aa-136">If the due date will always be the 10th of the next month, select a Payment day of the 10th.</span></span>  
15. <span data-ttu-id="d40aa-137">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-137">Click Save.</span></span>
16. <span data-ttu-id="d40aa-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d40aa-138">Close the page.</span></span>
17. <span data-ttu-id="d40aa-139">Ugorjon a Kinnlevőségek > Kifizetés beállítása > Készpénzfizetési engedmények pontra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-139">Go to Accounts receivable > Payments setup > Cash discounts.</span></span>
18. <span data-ttu-id="d40aa-140">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d40aa-140">Click New.</span></span>
    * <span data-ttu-id="d40aa-141">Ez az oldal a készpénzfizetési engedmény dátumának kiszámítására használható.</span><span class="sxs-lookup"><span data-stu-id="d40aa-141">This page is used to define how the cash discount date will be calculated.</span></span>  
19. <span data-ttu-id="d40aa-142">A Készpénzfizetési engedmény mezőben adjon meg egy Készpénzfizetési engedmény mező azonosítót.</span><span class="sxs-lookup"><span data-stu-id="d40aa-142">In the Cash discount field, enter an ID in the Cash discount field.</span></span>
20. <span data-ttu-id="d40aa-143">Adjon meg egy leírást a Leírás mezőben.</span><span class="sxs-lookup"><span data-stu-id="d40aa-143">In the Description field, enter a description.</span></span>
21. <span data-ttu-id="d40aa-144">Többszintű készpénzfizetési engedmény esetén válassza ki az új készpénzfizetési engedmény után releváns Következő engedmény kódját.</span><span class="sxs-lookup"><span data-stu-id="d40aa-144">If a tiered cash discount is available, select the Next discount code that is relevant after this new cash discount.</span></span>
22. <span data-ttu-id="d40aa-145">Adja meg a készpénzfizetési engedmény dátumához használandó napok számát.</span><span class="sxs-lookup"><span data-stu-id="d40aa-145">Enter the number of days used to calculate the cash dicount date.</span></span>
    * <span data-ttu-id="d40aa-146">Ha a Nettó irányelv lehetőséget választotta, a napok száma hozzáadódik a számla dátumához, és így kerül kiszámításra a készpénzfizetési engedmény dátuma.</span><span class="sxs-lookup"><span data-stu-id="d40aa-146">If Net principle is selected, the number of days will be added to the invoice date to calculate the cash discount date.</span></span>  
23. <span data-ttu-id="d40aa-147">Adja meg a készpénzfizetési engedmény százalékát.</span><span class="sxs-lookup"><span data-stu-id="d40aa-147">Enter the percentage of the cash discount.</span></span>
24. <span data-ttu-id="d40aa-148">Adja meg a fő számlát, amelyhez a vevői számlákon feladásra kerül a készpénzfizetési engedmény.</span><span class="sxs-lookup"><span data-stu-id="d40aa-148">Enter the main account to which the cash discount will post for customer invoices.</span></span>
25. <span data-ttu-id="d40aa-149">Válasszon egy lehetőséget a Kedvezmény ellenszámlák mezőben.</span><span class="sxs-lookup"><span data-stu-id="d40aa-149">In the Discount offset accounts field, select an option.</span></span>
    * <span data-ttu-id="d40aa-150">Ha a „Számlák a számlasorokban” beállítást választja, úgy a készpénzfizetési engedmény a szállítói számlasorok ugyanazon eszköz/költség főszámlájára kerül feladásra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-150">If you select 'Accounts on the invoice lines', the cash discount will post to the same asset/expense main account on the lines of the vendor invoice.</span></span> <span data-ttu-id="d40aa-151">A „Fő számla használata szállítói számlákhoz” lehetőség használata esetén a készpénzfizetési engedmény feladása a „Fő számla szállítói számlákhoz” elemnél megjelölt fő számlára történik.</span><span class="sxs-lookup"><span data-stu-id="d40aa-151">If you select 'Use main account for vendor invoices', the cash discount will post to the main account you define in the 'Main account for vendor invoices'.</span></span> <span data-ttu-id="d40aa-152">Ehhez a példához válassza a „Fő számla használata szállítói számlákhoz” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d40aa-152">For this example, select 'Use main account for vendor invoices.'</span></span>  
26. <span data-ttu-id="d40aa-153">Adja meg a fő számlát, amelyhez a szállítói számlákon feladásra kerül a készpénzfizetési engedmény.</span><span class="sxs-lookup"><span data-stu-id="d40aa-153">Enter the main account to which the cash discount will post for vendor invoices.</span></span>
27. <span data-ttu-id="d40aa-154">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d40aa-154">Click Save.</span></span>


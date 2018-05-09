--- 
title: "A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával"
description: "Ez a feladat-útmutató bemutatja, hogy hogyan tud számlákat hozni létre a számlajegyzék segítségével."
author: abruer
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
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a1273593f221963064c15a6404d4d92453f69d40
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="53c9a-103">A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával</span><span class="sxs-lookup"><span data-stu-id="53c9a-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="53c9a-104">Ez a feladat-útmutató bemutatja, hogy hogyan tud számlákat hozni létre a számlajegyzék segítségével.</span><span class="sxs-lookup"><span data-stu-id="53c9a-104">This task guide will show you how to use the invoice register to create invoices.</span></span>  <span data-ttu-id="53c9a-105">Ezután egyeztesse a számlát egy beszerzési rendeléssel a számlagyűjtő segítségével, majd véglegesítse a költséget a szállítói számla oldalon.</span><span class="sxs-lookup"><span data-stu-id="53c9a-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="53c9a-106">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="53c9a-106">Create a purchase order</span></span>
1. <span data-ttu-id="53c9a-107">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Beszerzési rendelések.</span><span class="sxs-lookup"><span data-stu-id="53c9a-107">Go to Accounts payable > Purchase orders > Purchase orders.</span></span>
2. <span data-ttu-id="53c9a-108">Új beszerzési rendelés létrehozásához kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-108">Click New to create a purchase order.</span></span>
3. <span data-ttu-id="53c9a-109">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="53c9a-109">In the Vendor account field, click the drop down button to open the lookup.</span></span>
4. <span data-ttu-id="53c9a-110">Válasszon ki a listából a szállítót.</span><span class="sxs-lookup"><span data-stu-id="53c9a-110">Select the vendor from the list.</span></span> <span data-ttu-id="53c9a-111">Például a 1001-es szállítót.</span><span class="sxs-lookup"><span data-stu-id="53c9a-111">For example, vendor 1001.</span></span>
5. <span data-ttu-id="53c9a-112">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53c9a-112">Click OK.</span></span>
6. <span data-ttu-id="53c9a-113">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="53c9a-113">In the Item number field, click the drop down button to open the lookup.</span></span>
7. <span data-ttu-id="53c9a-114">A listából keresse ki a szolgáltatási cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="53c9a-114">Find the services item number in the list.</span></span> <span data-ttu-id="53c9a-115">Válassza, például az S0001-t.</span><span class="sxs-lookup"><span data-stu-id="53c9a-115">For example, select S0001.</span></span>
8. <span data-ttu-id="53c9a-116">Kattintson a cikkszámra, majd válassza ki azt.</span><span class="sxs-lookup"><span data-stu-id="53c9a-116">Click on the item number and select it.</span></span>
    * <span data-ttu-id="53c9a-117">A nettó összeg 75,00.</span><span class="sxs-lookup"><span data-stu-id="53c9a-117">The net amount is 75.00.</span></span>  <span data-ttu-id="53c9a-118">Ezt az összeget szeretnénk viszontlátni a számlán is.</span><span class="sxs-lookup"><span data-stu-id="53c9a-118">That is the amount that we will expect on the invoice.</span></span>  
9. <span data-ttu-id="53c9a-119">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-119">On the action pane, click Purchase.</span></span>
10. <span data-ttu-id="53c9a-120">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="53c9a-120">Click Confirm.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="53c9a-121">Számla létrehozása és feladása</span><span class="sxs-lookup"><span data-stu-id="53c9a-121">Create and post and invoice</span></span>
1. <span data-ttu-id="53c9a-122">Ugorjon a Kötelezettségek > Számlák > Számlajegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-122">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="53c9a-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-123">Click New.</span></span>
3. <span data-ttu-id="53c9a-124">Nyissa meg a keresőlistát a használni kívánt számlajegyzék nevének kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="53c9a-124">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="53c9a-125">Válassza ki a használni kívánt számlajegyzék nevét.</span><span class="sxs-lookup"><span data-stu-id="53c9a-125">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="53c9a-126">Kattintson a Sorokra a jegyzék megnyitásához, adjon meg költségsorokat.</span><span class="sxs-lookup"><span data-stu-id="53c9a-126">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="53c9a-127">A keresőben válasszon egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="53c9a-127">In the lookup, select a vendor.</span></span> <span data-ttu-id="53c9a-128">Például, kattintson a 1001 szállító lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-128">For example, click on vendor 1001.</span></span>
7. <span data-ttu-id="53c9a-129">A Számla mezőben adja meg a számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="53c9a-129">In the Invoice field, enter the invoice number.</span></span>
8. <span data-ttu-id="53c9a-130">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="53c9a-130">In the Description field, type a value.</span></span>
9. <span data-ttu-id="53c9a-131">A Hitelkeret mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="53c9a-131">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="53c9a-132">A Beszerzési rendelés mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="53c9a-132">In the Purchase order field, click the drop down button to open the lookup.</span></span>
11. <span data-ttu-id="53c9a-133">Válassza ki a korábban létrehozott beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="53c9a-133">Select the purchase order that you created earlier.</span></span>
12. <span data-ttu-id="53c9a-134">A Jóváhagyó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="53c9a-134">In the Approved by field, click the drop down button to open the lookup.</span></span>
13. <span data-ttu-id="53c9a-135">Jelöljön ki egy jóváhagyót és kattintson a Kijelölés gombra a jóváhagyó kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="53c9a-135">Highlight an approver and click Select to select that approver.</span></span>
14. <span data-ttu-id="53c9a-136">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-136">Click Post.</span></span>
15. <span data-ttu-id="53c9a-137">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="53c9a-137">Close the form.</span></span>
16. <span data-ttu-id="53c9a-138">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="53c9a-138">Close the form.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="53c9a-139">A számlafolyamat befejezéséhez nyisson meg egy számlát a gyűjtőből, és válassza ki hozzá a megfelelő beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="53c9a-139">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="53c9a-140">Ugorjon a Kötelezettségek > Számlák > Számlajegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-140">Go to Accounts payable > Invoices > Invoice pool.</span></span>
2. <span data-ttu-id="53c9a-141">Kattintson a Beszerzési rendelés elemre, ha szállítói számlát kíván létrehozni a számlajegyzékből.</span><span class="sxs-lookup"><span data-stu-id="53c9a-141">Click Purchase order to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="53c9a-142">Válassza ki a megtekinteni kívánt számlát.</span><span class="sxs-lookup"><span data-stu-id="53c9a-142">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="53c9a-143">Az egyeztetés befejezéséhez kattintson az Egyeztetési állapot frissítése elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-143">Click Update match status to complete the matching.</span></span>
5. <span data-ttu-id="53c9a-144">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-144">On the action pane, click Options.</span></span>
6. <span data-ttu-id="53c9a-145">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-145">Click Change view.</span></span>
7. <span data-ttu-id="53c9a-146">Kattintson a Rács nézet elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-146">Click Grid view.</span></span>
8. <span data-ttu-id="53c9a-147">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-147">Click Post.</span></span>
9. <span data-ttu-id="53c9a-148">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="53c9a-148">Close the form.</span></span>
10. <span data-ttu-id="53c9a-149">Nyissa meg a következőt: Kötelezettségek > Szállítók > Szállítók.</span><span class="sxs-lookup"><span data-stu-id="53c9a-149">Go to Accounts payable > Vendors > Vendors.</span></span>
11. <span data-ttu-id="53c9a-150">Válassza ki a beszerzési rendeléshez tartozó szállítót.</span><span class="sxs-lookup"><span data-stu-id="53c9a-150">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="53c9a-151">Válassza ki például az 1001-es szállítót.</span><span class="sxs-lookup"><span data-stu-id="53c9a-151">For example, select vendor 1001.</span></span>
12. <span data-ttu-id="53c9a-152">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="53c9a-152">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="53c9a-153">A Művelet ablaktáblában kattintson a Szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-153">On the action pane, click Vendor.</span></span>
14. <span data-ttu-id="53c9a-154">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="53c9a-154">Click Transactions.</span></span>
15. <span data-ttu-id="53c9a-155">Válassza ki a létrehozott számlát.</span><span class="sxs-lookup"><span data-stu-id="53c9a-155">Select the invoice that you created.</span></span>
    * <span data-ttu-id="53c9a-156">A számlajegyzék-elhatárolás sztornírozásra, illetve a megfelelő költségszámlára feladásra került.</span><span class="sxs-lookup"><span data-stu-id="53c9a-156">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  



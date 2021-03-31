---
title: A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával
description: Ez a témakör azt mutatja be, hogyan lehet számlákat létrehozni a számlajegyzékben.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 670dd2ec15aa26791758ec4bea2b431482499436
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227160"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="e6892-103">A legfontosabb számlaadatok a kötelezettségkezelési rendszerbe számlagyűjtő használatával</span><span class="sxs-lookup"><span data-stu-id="e6892-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e6892-104">Ez a témakör azt mutatja be, hogyan lehet számlákat létrehozni a számlajegyzékben.</span><span class="sxs-lookup"><span data-stu-id="e6892-104">This topic describes how to use the invoice register to create invoices.</span></span> <span data-ttu-id="e6892-105">Ezután egyeztesse a számlát egy beszerzési rendeléssel a számlagyűjtő segítségével, majd véglegesítse a költséget a szállítói számla oldalon.</span><span class="sxs-lookup"><span data-stu-id="e6892-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="e6892-106">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="e6892-106">Create a purchase order</span></span>
1. <span data-ttu-id="e6892-107">A navigációs ablaktáblán nyissa meg a **Modulok > Kötelezettségek > beszerzési rendelések > Beszerzési rendelések** pontot.</span><span class="sxs-lookup"><span data-stu-id="e6892-107">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders**.</span></span>
2. <span data-ttu-id="e6892-108">Új beszerzési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="e6892-108">Select **New** to create a purchase order.</span></span>
3. <span data-ttu-id="e6892-109">A **Szállítói számla** mezőben nyissa meg válasszon egy beszállítót a legördülő listához.</span><span class="sxs-lookup"><span data-stu-id="e6892-109">In the **Vendor account** field, select a vendor for the drop-down list.</span></span> <span data-ttu-id="e6892-110">Válassza ki például az **1001**-es szállítót.</span><span class="sxs-lookup"><span data-stu-id="e6892-110">For example, select vendor **1001**.</span></span>
4. <span data-ttu-id="e6892-111">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e6892-111">Select **OK**.</span></span>
5. <span data-ttu-id="e6892-112">A **Cikkszám** mezőben válassza ki a kívánt szolgáltatási cikkszámot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="e6892-112">In the **Item number** field, select the services item number in the drop-down list.</span></span> <span data-ttu-id="e6892-113">Válassza például a **S0001-t**.</span><span class="sxs-lookup"><span data-stu-id="e6892-113">For example, select **S0001**.</span></span> <span data-ttu-id="e6892-114">A nettó összeg 75,00.</span><span class="sxs-lookup"><span data-stu-id="e6892-114">The net amount is 75.00.</span></span>  <span data-ttu-id="e6892-115">Ezt az összeget szeretnénk viszontlátni a számlán is.</span><span class="sxs-lookup"><span data-stu-id="e6892-115">That is the amount that we will expect on the invoice.</span></span>  
6. <span data-ttu-id="e6892-116">A Műveleti ablaktáblán válassza ki a **Beszerzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e6892-116">On the action pane, select **Purchase**.</span></span>
7. <span data-ttu-id="e6892-117">Válassza ki a **Megerősítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="e6892-117">Select **Confirm**.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="e6892-118">Számla létrehozása és feladása</span><span class="sxs-lookup"><span data-stu-id="e6892-118">Create and post and invoice</span></span>
1. <span data-ttu-id="e6892-119">Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlajegyzék** elemre.</span><span class="sxs-lookup"><span data-stu-id="e6892-119">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="e6892-120">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e6892-120">Select **New**.</span></span>
3. <span data-ttu-id="e6892-121">Nyissa meg a keresőlistát a használni kívánt számlajegyzék nevének kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="e6892-121">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="e6892-122">Válassza ki a használni kívánt számlajegyzék nevét.</span><span class="sxs-lookup"><span data-stu-id="e6892-122">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="e6892-123">Kattintson a **Sorokra** a jegyzék megnyitásához, adjon meg költségsorokat.</span><span class="sxs-lookup"><span data-stu-id="e6892-123">Select **Lines** to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="e6892-124">A keresőben válasszon egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="e6892-124">In the lookup, select a vendor.</span></span> <span data-ttu-id="e6892-125">Válassza ki például az **1001**-es szállítót.</span><span class="sxs-lookup"><span data-stu-id="e6892-125">For example, select vendor **1001**.</span></span>
7. <span data-ttu-id="e6892-126">A **Számla** mezőben adja meg a számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="e6892-126">In the **Invoice** field, enter the invoice number.</span></span>
8. <span data-ttu-id="e6892-127">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e6892-127">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="e6892-128">A **Hitelkeret** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e6892-128">In the **Credit** field, enter a number.</span></span>
10. <span data-ttu-id="e6892-129">A **Beszerzési rendelés** mezőben nyissa meg a legördülő listát a korábban létrehozott beszerzési rendelés kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="e6892-129">In the **Purchase order** field, open the drop-down list to select the purchase order that you created earlier.</span></span>
11. <span data-ttu-id="e6892-130">A **Jóváhagyó** mezőben jelöljön ki egy jóváhagyót a legördülő listából, majd a **Kiválasztás** gombra kattintva válassza ki a jóváhagyót.</span><span class="sxs-lookup"><span data-stu-id="e6892-130">In the **Approved by** field, highlight an approver in the drop-down list and click **Select** to select that approver.</span></span>
12. <span data-ttu-id="e6892-131">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e6892-131">Select **Post**.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="e6892-132">A számlafolyamat befejezéséhez nyisson meg egy számlát a gyűjtőből, és válassza ki hozzá a megfelelő beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="e6892-132">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="e6892-133">Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlagyűjtő** elemre.</span><span class="sxs-lookup"><span data-stu-id="e6892-133">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice pool**.</span></span>
2. <span data-ttu-id="e6892-134">Kattintson a **Beszerzési rendelés** elemre, ha szállítói számlát kíván létrehozni a számlajegyzékből.</span><span class="sxs-lookup"><span data-stu-id="e6892-134">Select **Purchase order** to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="e6892-135">Válassza ki a megtekinteni kívánt számlát.</span><span class="sxs-lookup"><span data-stu-id="e6892-135">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="e6892-136">Az egyeztetés befejezéséhez kattintson az **Egyeztetési állapot frissítése** elemre.</span><span class="sxs-lookup"><span data-stu-id="e6892-136">Select **Update match status** to complete the matching.</span></span>
5. <span data-ttu-id="e6892-137">A műveleti ablaktáblán válassza ki a **Beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="e6892-137">On the action pane, select **Options**.</span></span>
6. <span data-ttu-id="e6892-138">Válassza ki a **Nézetváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e6892-138">Select **Change view**.</span></span>
7. <span data-ttu-id="e6892-139">Válassza a **Rácsnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="e6892-139">Select **Grid view**.</span></span>
8. <span data-ttu-id="e6892-140">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e6892-140">Select **Post**.</span></span>
9. <span data-ttu-id="e6892-141">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="e6892-141">Close the form.</span></span>
10. <span data-ttu-id="e6892-142">A Navigációs ablaktáblán válassza a **Modulok > Kötelezettségek > Szállítók > Beszállítók** elemet.</span><span class="sxs-lookup"><span data-stu-id="e6892-142">In the navigation pane, go to **Modules > Accounts payable > Vendors > Vendors**.</span></span>
11. <span data-ttu-id="e6892-143">Válassza ki a beszerzési rendeléshez tartozó szállítót.</span><span class="sxs-lookup"><span data-stu-id="e6892-143">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="e6892-144">Válassza ki például az **1001**-es szállítót.</span><span class="sxs-lookup"><span data-stu-id="e6892-144">For example, select vendor **1001**.</span></span>
12. <span data-ttu-id="e6892-145">A műveleti ablaktáblán válassza a **Szállító** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e6892-145">On the action pane, select **Vendor**.</span></span>
13. <span data-ttu-id="e6892-146">Válassza a **Tranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e6892-146">Select **Transactions**.</span></span>
14. <span data-ttu-id="e6892-147">Válassza ki a létrehozott számlát.</span><span class="sxs-lookup"><span data-stu-id="e6892-147">Select the invoice that you created.</span></span> <span data-ttu-id="e6892-148">A számlajegyzék-elhatárolás sztornírozásra, illetve a megfelelő költségszámlára feladásra került.</span><span class="sxs-lookup"><span data-stu-id="e6892-148">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
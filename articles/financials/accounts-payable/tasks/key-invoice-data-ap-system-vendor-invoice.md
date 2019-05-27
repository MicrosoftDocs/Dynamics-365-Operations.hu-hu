---
title: Fő számlaadatok a Kintlevőségek rendszerben, szállítói számla használatával
description: Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés).
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1d2e31a5de7cefd20996c18bf4771296a587997
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569632"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a><span data-ttu-id="c248d-103">Fő számlaadatok a Kintlevőségek rendszerben, szállítói számla használatával</span><span class="sxs-lookup"><span data-stu-id="c248d-103">Key invoice data in AP system using vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c248d-104">Ez a feladat-útmutató segít Önnek szállítói számla létrehozásában egy beszerzési rendelésből, valamint a beszerzési rendelés, nyugta és számla egyeztetési eredményeinek megtekintésében (háromirányú egyeztetés).</span><span class="sxs-lookup"><span data-stu-id="c248d-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="c248d-105">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c248d-105">Create a purchase order</span></span>
1. <span data-ttu-id="c248d-106">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="c248d-106">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="c248d-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c248d-107">Click New.</span></span>
3. <span data-ttu-id="c248d-108">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c248d-108">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="c248d-109">Keressen egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="c248d-109">Find a vendor to select.</span></span> <span data-ttu-id="c248d-110">Például görgessen le a US-104 lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c248d-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="c248d-111">US-104 szállító kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c248d-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="c248d-112">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c248d-112">Click OK.</span></span>
7. <span data-ttu-id="c248d-113">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c248d-113">In the Item number field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="c248d-114">Készletcikk kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c248d-114">Select an inventory item.</span></span> <span data-ttu-id="c248d-115">Példábul válassza ki az 1000 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="c248d-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="c248d-116">Bontsa ki vagy csukja össze a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c248d-116">Expand or collapse the Line details section.</span></span>
10. <span data-ttu-id="c248d-117">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="c248d-117">Click the Setup tab.</span></span>
    * <span data-ttu-id="c248d-118">Felülírhatja az egyeztetési irányelvet egyeztetés nélkülire, kétirányú egyeztetésre vagy háromirányú egyeztetésre.</span><span class="sxs-lookup"><span data-stu-id="c248d-118">You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="c248d-119">Bontsa ki vagy csukja össze a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c248d-119">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="c248d-120">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="c248d-120">On the Action Pane, click Purchase.</span></span>
13. <span data-ttu-id="c248d-121">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="c248d-121">Click Confirm.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="c248d-122">A termékek bevételezése</span><span class="sxs-lookup"><span data-stu-id="c248d-122">Receive the products</span></span>
1. <span data-ttu-id="c248d-123">A Művelet panelen kattintson a Bevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="c248d-123">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="c248d-124">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="c248d-124">Click Product receipt.</span></span>
3. <span data-ttu-id="c248d-125">A Termékbevételezés mezőbe írja be a termékbevételezés számát.</span><span class="sxs-lookup"><span data-stu-id="c248d-125">In the Product receipt field, enter the product receipt number.</span></span> <span data-ttu-id="c248d-126">Például írja be, hogy PR123.</span><span class="sxs-lookup"><span data-stu-id="c248d-126">For example, enter PR123.</span></span>
4. <span data-ttu-id="c248d-127">Kattintson az OK gombra a termékbevételezés feladásához.</span><span class="sxs-lookup"><span data-stu-id="c248d-127">Click OK to post the product receipt.</span></span>
5. <span data-ttu-id="c248d-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c248d-128">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="c248d-129">Szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="c248d-129">Create a vendor invoice</span></span>
1. <span data-ttu-id="c248d-130">Ugorjon a Kötelezettségek > Beszerzési rendelések > Bevételezett, de még ki nem számlázott beszerzési rendelések pontra.</span><span class="sxs-lookup"><span data-stu-id="c248d-130">Go to Accounts payable > Purchase orders > Purchase orders received but not invoiced.</span></span>
2. <span data-ttu-id="c248d-131">Válassza ki a létrehozott beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c248d-131">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="c248d-132">A Művelet panelen kattintson a Számla elemre.</span><span class="sxs-lookup"><span data-stu-id="c248d-132">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="c248d-133">Kattintson a Számlára.</span><span class="sxs-lookup"><span data-stu-id="c248d-133">Click Invoice.</span></span>
5. <span data-ttu-id="c248d-134">A Szám mezőben adja meg a számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c248d-134">In the Number field, enter the invoice number.</span></span>
6. <span data-ttu-id="c248d-135">A Számla leírása mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c248d-135">In the Invoice description field, type a value.</span></span>
7. <span data-ttu-id="c248d-136">A Számla dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="c248d-136">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="c248d-137">Írjon be 1200 értéket az Egységár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c248d-137">In the Unit price field, enter 1200.</span></span>
9. <span data-ttu-id="c248d-138">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="c248d-138">Click Add line.</span></span>
10. <span data-ttu-id="c248d-139">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c248d-139">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="c248d-140">Keresse meg a listában a telepítési költség cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="c248d-140">In the list, find the installation charge item number.</span></span> <span data-ttu-id="c248d-141">Például az S0001 elem</span><span class="sxs-lookup"><span data-stu-id="c248d-141">For example, S0001</span></span>
12. <span data-ttu-id="c248d-142">Válassza ki a telepítési költség cikkszámát.</span><span class="sxs-lookup"><span data-stu-id="c248d-142">Select the installation charge item number.</span></span>
    * <span data-ttu-id="c248d-143">Vegye figyelembe, hogy egyeztetés a módosítások óta nem lett végrehajtva.</span><span class="sxs-lookup"><span data-stu-id="c248d-143">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="c248d-144">Kattintson az Egyeztetési állapot frissítése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c248d-144">Click Update match status.</span></span>
14. <span data-ttu-id="c248d-145">A Művelet panelen kattintson az Áttekintés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c248d-145">On the Action Pane, click Review.</span></span>
15. <span data-ttu-id="c248d-146">Kattintson a Részletek egyeztetése elemre.</span><span class="sxs-lookup"><span data-stu-id="c248d-146">Click Matching details.</span></span>
    * <span data-ttu-id="c248d-147">A szolgáltatásokkal rendelkező új sorokat nem kell egyeztetni, ezért az állapotuk „Kihagyva” marad.</span><span class="sxs-lookup"><span data-stu-id="c248d-147">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="c248d-148">Válassza ki a termékbevételezést a bevételezett készletcikkhez.</span><span class="sxs-lookup"><span data-stu-id="c248d-148">Select the product receipt for the inventory item that you received.</span></span>
    * <span data-ttu-id="c248d-149">A termékbevételezés sora egyeztetve lett, de eltérés található az árban vagy a mennyiségben, ezért sikertelen.</span><span class="sxs-lookup"><span data-stu-id="c248d-149">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="c248d-150">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="c248d-150">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="c248d-151">Most, hogy az egységár megegyezik, az állapot Sikeres értékre frissül.</span><span class="sxs-lookup"><span data-stu-id="c248d-151">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="c248d-152">Ha az irányelve megengedi az eltéréseket, vagy az egyeztetés csak egy figyelmeztetés, akkor ettől függetlenül fel tudja adni a számlát.</span><span class="sxs-lookup"><span data-stu-id="c248d-152">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="c248d-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c248d-153">Close the page.</span></span>
19. <span data-ttu-id="c248d-154">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c248d-154">Click Post.</span></span>
20. <span data-ttu-id="c248d-155">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="c248d-155">Close the form.</span></span>
    * <span data-ttu-id="c248d-156">Ne felejtse, hogy a beszerzési rendelés már nem bevételezettként, hanem nem számlázottként van listázva.</span><span class="sxs-lookup"><span data-stu-id="c248d-156">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  


--- 
title: "Akkreditív importálása"
description: "Ez az eljárás bemutatja egy akkreditív importálásának folyamatát."
author: kweekley
manager: AnnBe
ms.date: 02/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 02be2627186a149a05eaccfa3e5906a9fe1d74dd
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="import-a-letter-of-credit"></a><span data-ttu-id="7765a-103">Akkreditív importálása</span><span class="sxs-lookup"><span data-stu-id="7765a-103">Import a letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7765a-104">Ez az eljárás bemutatja egy akkreditív importálásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="7765a-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="7765a-105">Az eljárás végrehajtása előtt be kell állítani a következőket: banki hitelek, feladási profilok, egy banki hitelmegállapodás és szállító banki adatai.</span><span class="sxs-lookup"><span data-stu-id="7765a-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="7765a-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7765a-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="7765a-107">Beszerzési rendelés létrehozása akkreditívvel</span><span class="sxs-lookup"><span data-stu-id="7765a-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="7765a-108">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="7765a-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="7765a-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-109">Click New.</span></span>
3. <span data-ttu-id="7765a-110">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="7765a-111">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="7765a-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="7765a-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7765a-113">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7765a-113">Expand the General section.</span></span>
7. <span data-ttu-id="7765a-114">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="7765a-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7765a-116">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="7765a-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="7765a-118">Adja meg a dátumot a Könyvelés dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="7765a-119">Adjon meg egy dátumot a Kiszállítási dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="7765a-120">Megjegyzés: A „Banki okmány típusa” mezőnél az „Akkreditív” értéknek kell kiválasztva lennie.</span><span class="sxs-lookup"><span data-stu-id="7765a-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="7765a-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-121">Click OK.</span></span>
14. <span data-ttu-id="7765a-122">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="7765a-123">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7765a-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="7765a-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="7765a-125">A Sorrészletek szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="7765a-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="7765a-126">Kattintson a Kiszállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="7765a-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="7765a-127">Adjon meg egy dátumot a Kiszállítási dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="7765a-128">Adjon meg egy dátumot a Visszaigazolt szállítási dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="7765a-129">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="7765a-130">Adja meg az Akkreditív adatait.</span><span class="sxs-lookup"><span data-stu-id="7765a-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="7765a-131">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="7765a-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="7765a-132">Kattintson az Akkreditív / importbeszedvény lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="7765a-133">Az Alkalmazás dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="7765a-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="7765a-134">Győződjön meg róla, hogy a „Bankszámla” mezőben az alapértelmezett aktív Bankszámla szerepel, az alkalmazás dátuma alapján.</span><span class="sxs-lookup"><span data-stu-id="7765a-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="7765a-135">A Banki okmány száma mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="7765a-136">A Kézhezvétel dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="7765a-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="7765a-137">Bontsa ki a A banki bizonylat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7765a-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="7765a-138">Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="7765a-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="7765a-139">Bontsa ki a Bank részletei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7765a-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="7765a-140">Az Értesítő bank mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="7765a-141">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="7765a-142">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-142">Click Save.</span></span>
33. <span data-ttu-id="7765a-143">Kattintson a Beszerzési rendelés szállítmányainak beolvasása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="7765a-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-144">Close the page.</span></span>
35. <span data-ttu-id="7765a-145">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="7765a-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="7765a-146">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-146">Click Confirm.</span></span>
37. <span data-ttu-id="7765a-147">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="7765a-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="7765a-148">Kattintson az Akkreditív / importbeszedvény lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="7765a-149">Kattintson a Folyamat gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-149">Click Process.</span></span>
40. <span data-ttu-id="7765a-150">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-150">Click Confirm.</span></span>
    * <span data-ttu-id="7765a-151">Győződjön meg róla, hogy a Hitel egyenlege levonja a beszerzési rendelés összegét.</span><span class="sxs-lookup"><span data-stu-id="7765a-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="7765a-152">Ebben a példában a Beszerzési összeg = 500,00, a Hitelmegállapodás határértéke = 10000,00, tehát a Hitel egyenlege = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="7765a-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="7765a-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-153">Close the page.</span></span>
42. <span data-ttu-id="7765a-154">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="7765a-155">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-155">Click Save.</span></span>
44. <span data-ttu-id="7765a-156">A Művelet panelen kattintson a Beszerzés elemre.</span><span class="sxs-lookup"><span data-stu-id="7765a-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="7765a-157">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-157">Click Confirm.</span></span>
    * <span data-ttu-id="7765a-158">Az Akkreditív módosítása Egységárban bekövetkező változás miatt.</span><span class="sxs-lookup"><span data-stu-id="7765a-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="7765a-159">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="7765a-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="7765a-160">Kattintson az Akkreditív / importbeszedvény lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="7765a-161">Az Akkreditív módosítása Beszerzési árban bekövetkező változás miatt.</span><span class="sxs-lookup"><span data-stu-id="7765a-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="7765a-162">Kattintson a Folyamat gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-162">Click Process.</span></span>
49. <span data-ttu-id="7765a-163">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-163">Click Amend.</span></span>
50. <span data-ttu-id="7765a-164">Kattintson az Eltávolítás gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-164">Click Remove.</span></span>
51. <span data-ttu-id="7765a-165">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-165">Click Yes.</span></span>
52. <span data-ttu-id="7765a-166">Kattintson a Beszerzési rendelés szállítmányainak beolvasása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="7765a-167">Kattintson a Folyamat gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-167">Click Process.</span></span>
54. <span data-ttu-id="7765a-168">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-168">Click Confirm.</span></span>
    * <span data-ttu-id="7765a-169">Győződjön meg róla, hogy a Hitel egyenlege levonja a beszerzési rendelés összegét.</span><span class="sxs-lookup"><span data-stu-id="7765a-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="7765a-170">Ebben a példában a szerkesztett Beszerzési összeg = 600,00, a Hitelmegállapodás határértéke = 10000,00, tehát a Hitel egyenlege = 9400,00.</span><span class="sxs-lookup"><span data-stu-id="7765a-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="7765a-171">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="7765a-172">Szállítólevél feladása</span><span class="sxs-lookup"><span data-stu-id="7765a-172">Post Packing slip</span></span>
1. <span data-ttu-id="7765a-173">A Művelet panelen kattintson a Bevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="7765a-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="7765a-174">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="7765a-174">Click Product receipt.</span></span>
3. <span data-ttu-id="7765a-175">Írjon be egy értéket a PurchParmTable_Num mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7765a-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="7765a-176">Válassza ki a az Akkreditívre való hivatkozással létrehozott Szállítmányszámot.</span><span class="sxs-lookup"><span data-stu-id="7765a-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="7765a-177">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7765a-178">Adjon meg egy dátumot a Termékbevételezési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="7765a-179">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-179">Click OK.</span></span>
7. <span data-ttu-id="7765a-180">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-180">Close the page.</span></span>
8. <span data-ttu-id="7765a-181">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="7765a-182">Ellenőrizze az Importakkreditív állapotát.</span><span class="sxs-lookup"><span data-stu-id="7765a-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="7765a-183">Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Importakkreditív és importbeszedvény pontra.</span><span class="sxs-lookup"><span data-stu-id="7765a-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="7765a-184">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7765a-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7765a-185">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7765a-186">Ellenőrizze az Importakkreditív állapotát.</span><span class="sxs-lookup"><span data-stu-id="7765a-186">Verify the Import letter of credit status.</span></span>  
4. <span data-ttu-id="7765a-187">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-187">Close the page.</span></span>
5. <span data-ttu-id="7765a-188">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="7765a-189">Beszerzési számla feladása</span><span class="sxs-lookup"><span data-stu-id="7765a-189">Post purchase invoice</span></span>
1. <span data-ttu-id="7765a-190">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="7765a-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="7765a-191">Válassza ki az akkreditívvel létrehozott beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="7765a-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="7765a-192">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7765a-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7765a-193">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7765a-194">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="7765a-195">Kattintson a Számlára.</span><span class="sxs-lookup"><span data-stu-id="7765a-195">Click Invoice.</span></span>
6. <span data-ttu-id="7765a-196">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7765a-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="7765a-197">A Szállítmányszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="7765a-198">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7765a-199">A Számla dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="7765a-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="7765a-200">Kattintson az Egyeztetési állapot frissítése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-200">Click Update match status.</span></span>
11. <span data-ttu-id="7765a-201">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-201">Click Post.</span></span>
12. <span data-ttu-id="7765a-202">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-202">Close the page.</span></span>
13. <span data-ttu-id="7765a-203">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="7765a-204">Ellenőrizze az Importakkreditív állapotát.</span><span class="sxs-lookup"><span data-stu-id="7765a-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="7765a-205">Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Importakkreditív és importbeszedvény pontra.</span><span class="sxs-lookup"><span data-stu-id="7765a-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="7765a-206">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7765a-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7765a-207">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7765a-208">Ellenőrizze az Importakkreditív2 állapotát.</span><span class="sxs-lookup"><span data-stu-id="7765a-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="7765a-209">Ellenőrzés : Szállítmány állapota = Számlázva Banki hitelmegállapodás részletei</span><span class="sxs-lookup"><span data-stu-id="7765a-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="7765a-210">Kattintson a Megtekintés menüpontra.</span><span class="sxs-lookup"><span data-stu-id="7765a-210">Click View.</span></span>
5. <span data-ttu-id="7765a-211">Kattintson az Igénylés nyomtatása gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-211">Click Print application.</span></span>
6. <span data-ttu-id="7765a-212">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-212">Click OK.</span></span>
    * <span data-ttu-id="7765a-213">Győződjön meg róla, hogy az Akkreditívigénylés nyomtatása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="7765a-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="7765a-214">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-214">Close the page.</span></span>
8. <span data-ttu-id="7765a-215">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-215">Close the page.</span></span>
9. <span data-ttu-id="7765a-216">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="7765a-217">Az akreditívvel létrehozott beszerzési számlára vonatkozó Szállító kifizetési napló feladása</span><span class="sxs-lookup"><span data-stu-id="7765a-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="7765a-218">Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="7765a-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="7765a-219">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-219">Click New.</span></span>
3. <span data-ttu-id="7765a-220">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="7765a-221">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7765a-222">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="7765a-222">Click Lines.</span></span>
6. <span data-ttu-id="7765a-223">Adja meg a dátumot a Dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="7765a-224">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="7765a-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="7765a-225">Kattintson a Tranzakcióinak kiegyenlítése gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="7765a-226">Bontsa ki az Összegek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7765a-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="7765a-227">Válasszon ki egy lehetőséget a Megjelenítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="7765a-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="7765a-228">Győződjön meg róla, hogy a Banki okmány száma és a Szállítmányszám mezőket frissítették.</span><span class="sxs-lookup"><span data-stu-id="7765a-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="7765a-229">Jelölje be a Megjelölve jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7765a-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="7765a-230">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-230">Click OK.</span></span>
13. <span data-ttu-id="7765a-231">Kattintson a Fizetések fülre.</span><span class="sxs-lookup"><span data-stu-id="7765a-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="7765a-232">Győződjön meg róla, hogy a Banki okmány száma és a Szállítmányszám mezőket frissítették.</span><span class="sxs-lookup"><span data-stu-id="7765a-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="7765a-233">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7765a-233">Click Post.</span></span>
15. <span data-ttu-id="7765a-234">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-234">Close the page.</span></span>
16. <span data-ttu-id="7765a-235">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="7765a-236">Az Importakkreditív állapotának ellenőrzése a Számla kifizetése után</span><span class="sxs-lookup"><span data-stu-id="7765a-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="7765a-237">Ugorjon a Készpénz- és bankkezelés > Akkreditívek > Importakkreditív és importbeszedvény pontra.</span><span class="sxs-lookup"><span data-stu-id="7765a-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="7765a-238">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7765a-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7765a-239">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7765a-240">Ellenőrizze az Importakkreditív állapotát.</span><span class="sxs-lookup"><span data-stu-id="7765a-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="7765a-241">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="7765a-242">Banki hitelmegállapodás korlát és a terheléskihasználtsági jelentés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="7765a-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="7765a-243">Ugorjon a Készpénz- és bankkezelés > Lekérdezések és jelentések > Akkreditívek vagy garancialevél > Banki hitelek és kihasználtságuk – jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="7765a-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="7765a-244">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7765a-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="7765a-245">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="7765a-245">Click Filter.</span></span>
    * <span data-ttu-id="7765a-246">A Feltételek mezőben adja meg a szükséges bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="7765a-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="7765a-247">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7765a-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="7765a-248">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7765a-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7765a-249">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-249">Click OK.</span></span>
7. <span data-ttu-id="7765a-250">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7765a-250">Click OK.</span></span>
    * <span data-ttu-id="7765a-251">Ellenőrizze a tranzakciókat felsoroló jelentést.</span><span class="sxs-lookup"><span data-stu-id="7765a-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="7765a-252">Győződjön meg róla, hogy a jelentés felsorolja a tranzakciókat a Banki okmány számával, a Hitelmegállapodás határértékével, a felhasznált összeggel és a hitel egyenlegének összegével együtt.</span><span class="sxs-lookup"><span data-stu-id="7765a-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="7765a-253">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7765a-253">Close the page.</span></span>



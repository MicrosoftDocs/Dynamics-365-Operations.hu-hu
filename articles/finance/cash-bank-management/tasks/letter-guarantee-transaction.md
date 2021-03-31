---
title: Garancialevél-tranzakció
description: Ez az eljárás végigvezeti a Garancialevélhez kapcsolódó folyamaton.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 566849cfcedd29f4bb92d08a17b67e16b1cbc372
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225369"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="5fe77-103">Garancialevél-tranzakció</span><span class="sxs-lookup"><span data-stu-id="5fe77-103">Letter of guarantee transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5fe77-104">Ez az eljárás végigvezeti a Garancialevélhez kapcsolódó folyamaton.</span><span class="sxs-lookup"><span data-stu-id="5fe77-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="5fe77-105">A következő feladatoknak kell készen lenniük az eljárás végrehajtása előtt:</span><span class="sxs-lookup"><span data-stu-id="5fe77-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="5fe77-106">A garancialevélre vonatkozóan állítsa be a banki hiteleket és a feladási profilokat.</span><span class="sxs-lookup"><span data-stu-id="5fe77-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="5fe77-107">Hozzon létre egy banki hitelmegállapodást a garancialevélhez.</span><span class="sxs-lookup"><span data-stu-id="5fe77-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="5fe77-108">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5fe77-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="5fe77-109">Értékesítési rendelés létrehozása garancialevéllel</span><span class="sxs-lookup"><span data-stu-id="5fe77-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="5fe77-110">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="5fe77-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-111">Click New.</span></span>
3. <span data-ttu-id="5fe77-112">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="5fe77-113">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5fe77-113">Expand the General section.</span></span>
5. <span data-ttu-id="5fe77-114">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="5fe77-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="5fe77-116">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="5fe77-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="5fe77-118">A Banki bizonylat típusa mezőben válassza ki a „Garancialevél” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5fe77-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="5fe77-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-119">Click OK.</span></span>
11. <span data-ttu-id="5fe77-120">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="5fe77-121">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5fe77-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="5fe77-122">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5fe77-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="5fe77-123">Kattintson a Kiszállítás lapra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="5fe77-124">Megjegyzés: A Szállítási dátum ellenőrzése lehetőségnél a „Nincs” lehetőséget válassza</span><span class="sxs-lookup"><span data-stu-id="5fe77-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="5fe77-125">Adjon meg egy dátumot a Kért szállítási dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="5fe77-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="5fe77-126">Adjon meg egy dátumot a Visszaigazolt szállítási dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="5fe77-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="5fe77-127">Garancialevél-kérelem feldolgozása</span><span class="sxs-lookup"><span data-stu-id="5fe77-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="5fe77-128">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="5fe77-129">Kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="5fe77-130">A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="5fe77-131">A Kérelem gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="5fe77-132">A Típus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="5fe77-133">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="5fe77-134">Adjon meg egy számot az Érték mezőben.</span><span class="sxs-lookup"><span data-stu-id="5fe77-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="5fe77-135">Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="5fe77-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-136">Click OK.</span></span>
10. <span data-ttu-id="5fe77-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="5fe77-138">Garancialevél feldolgozása Elküldés a banknak</span><span class="sxs-lookup"><span data-stu-id="5fe77-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="5fe77-139">Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="5fe77-140">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5fe77-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5fe77-141">Kattintson a Feladás a bankhoz gombra a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5fe77-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="5fe77-142">A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="5fe77-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="5fe77-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="5fe77-145">Garancialevél feldolgozása Fogadás a banktól</span><span class="sxs-lookup"><span data-stu-id="5fe77-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="5fe77-146">A Banktól fogadott gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="5fe77-147">A Banki szám mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="5fe77-148">Ellenőrizze a Nyereség és a Költség mezőkben szereplő kiszámított értékeket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="5fe77-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-149">Click OK.</span></span>
4. <span data-ttu-id="5fe77-150">Bontsa ki a Műveletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5fe77-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="5fe77-151">Ellenőrizze a „Fogadás a banktól” bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="5fe77-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="5fe77-152">Kattintson a Naplóköteg száma mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="5fe77-153">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-153">Click Lines.</span></span>
    * <span data-ttu-id="5fe77-154">Ellenőrizze a naplóbejegyzések feladását.</span><span class="sxs-lookup"><span data-stu-id="5fe77-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="5fe77-155">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="5fe77-156">Garancialevél feldolgozása Átadás a kedvezményezettnek</span><span class="sxs-lookup"><span data-stu-id="5fe77-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="5fe77-157">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="5fe77-158">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="5fe77-159">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="5fe77-160">Kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="5fe77-161">A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="5fe77-162">Kattintson a Kedvezményezettnek átadás gombra a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5fe77-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="5fe77-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-163">Click OK.</span></span>
8. <span data-ttu-id="5fe77-164">Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="5fe77-165">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5fe77-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="5fe77-166">Kattintson a Kedvezményezettnek átadás gombra a legördülő párbeszédablak megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5fe77-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="5fe77-167">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-167">Click OK.</span></span>
12. <span data-ttu-id="5fe77-168">Bontsa ki a Műveletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5fe77-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="5fe77-169">Érvényesítse a „Kedvezményezettnek való átadás” bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="5fe77-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="5fe77-170">Garancialevél feldolgozása Értéknövelés</span><span class="sxs-lookup"><span data-stu-id="5fe77-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="5fe77-171">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="5fe77-172">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="5fe77-173">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="5fe77-174">Kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="5fe77-175">A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="5fe77-176">Az Értéknövelés gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="5fe77-177">Adjon meg egy számot az Érték hozzáadása mezőben.</span><span class="sxs-lookup"><span data-stu-id="5fe77-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="5fe77-178">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-178">Click OK.</span></span>
9. <span data-ttu-id="5fe77-179">Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="5fe77-180">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5fe77-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="5fe77-181">Az Értéknövelés gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="5fe77-182">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-182">Click OK.</span></span>
13. <span data-ttu-id="5fe77-183">Bontsa ki a Műveletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5fe77-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="5fe77-184">Ellenőrizze az „Érték növelése” bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="5fe77-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="5fe77-185">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5fe77-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="5fe77-186">Kattintson a Naplóköteg száma mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="5fe77-187">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-187">Click Lines.</span></span>
    * <span data-ttu-id="5fe77-188">Érvényesítse a feladott naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="5fe77-189">Garancialevél feldolgozása Likvidálás</span><span class="sxs-lookup"><span data-stu-id="5fe77-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="5fe77-190">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="5fe77-191">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="5fe77-192">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="5fe77-193">Kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="5fe77-194">A Műveleti ablaktáblán kattintson a Garancialevél lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="5fe77-195">A Likvidálás gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="5fe77-196">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-196">Click OK.</span></span>
8. <span data-ttu-id="5fe77-197">Ugrás a Készpénz- és bankkezelés > Garancialevelek > Garancialevelek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe77-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="5fe77-198">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5fe77-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="5fe77-199">A Likvidálás gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="5fe77-200">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-200">Click OK.</span></span>
12. <span data-ttu-id="5fe77-201">Bontsa ki a Műveletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5fe77-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="5fe77-202">Érvényesítse a „Likvidálás” bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="5fe77-203">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5fe77-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="5fe77-204">Kattintson a Naplóköteg száma mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="5fe77-205">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="5fe77-205">Click Lines.</span></span>
    * <span data-ttu-id="5fe77-206">Érvényesítse a feladott naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="5fe77-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="5fe77-207">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5fe77-207">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
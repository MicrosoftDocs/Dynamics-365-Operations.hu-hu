--- 
title: "A minimum-maximum feltöltési folyamat beállítása"
description: "Ez az eljárás bemutatja, hogy hogyan állíthat be egy új feltöltési folyamatot, amely a minimális/maximális feltöltési stratégiát használja."
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 02af5d1beb2d4eb6a7162b47c42854725fbdbec2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-min-max-replenishment-process"></a><span data-ttu-id="12a0d-103">A minimum-maximum feltöltési folyamat beállítása</span><span class="sxs-lookup"><span data-stu-id="12a0d-103">Set up a min-max replenishment process</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12a0d-104">Ez az eljárás bemutatja, hogy hogyan állíthat be egy új feltöltési folyamatot, amely a minimális/maximális feltöltési stratégiát használja.</span><span class="sxs-lookup"><span data-stu-id="12a0d-104">This procedure shows you how to set up a new replenishment process which uses the minimum/maximum replenishment strategy.</span></span> <span data-ttu-id="12a0d-105">Amikor a készlet a minimális szint alá esik, a rendszer a hely feltöltéséhez hozza létre munkát.</span><span class="sxs-lookup"><span data-stu-id="12a0d-105">When inventory falls below the minimum level, work will be created to replenish the location.</span></span> <span data-ttu-id="12a0d-106">Az eljárás azt is bemutatja, hogy hogyan lehet a rögzített kitárolási helyek segítségével az újratelepítést engedélyezni, ha a készlet a minimális szint alá esik, és hogyan lehet a feltöltési folyamatot engedélyezni a rendszeres futtatáshoz egy kötegelt feladat használatával.</span><span class="sxs-lookup"><span data-stu-id="12a0d-106">The procedure also shows how to use fixed picking locations to allow restocking even if inventory falls below the minimum level, and how to enable the replenishment process to run regularly using a batch job.</span></span> <span data-ttu-id="12a0d-107">Ezeket a feladatokat jellemzően egy raktári vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="12a0d-107">These tasks would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="12a0d-108">A megjegyzések példaértékeinek használatával futtathatja ezt az eljárást az USMF bemutató vállalatnál, vagy a saját adatait vagy futtathatja.</span><span class="sxs-lookup"><span data-stu-id="12a0d-108">You can run this procedure in the USMF demo data company using the example values in the notes, or can run it on your own data.</span></span> <span data-ttu-id="12a0d-109">Ha a saját adatait használja, győződjön meg arról, hogy egy olyan raktárral rendelkezik, amely engedélyezve van a Raktárkezelési folyamatok számára.</span><span class="sxs-lookup"><span data-stu-id="12a0d-109">If you’re using your own data, make sure that you have a warehouse that’s enabled for Warehouse management processes.</span></span>


## <a name="create-a-fixed-picking-location"></a><span data-ttu-id="12a0d-110">A fix kitárolási helyek létrehozása</span><span class="sxs-lookup"><span data-stu-id="12a0d-110">Create a fixed picking location</span></span>
1. <span data-ttu-id="12a0d-111">Ugorjon a Raktárkezelés > Beállítás > Raktár > Rögzített helyek pontra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-111">Go to Warehouse management > Setup > Warehouse > Fixed locations.</span></span>
    * <span data-ttu-id="12a0d-112">A minimum-maximum feltöltésre vonatkozóan ez egy választható feladat, de ha a fix kivételi helyeket használja, akkor lehetővé válik a készlet feltöltése még akkor is, ha a minimális szint alá esik, mert a rendszer meghatározhatja, hogy mely termékeket kell feltölteni, még akkor is, ha nincs a készleten.</span><span class="sxs-lookup"><span data-stu-id="12a0d-112">This is an optional task for min-max replenishment, but if you use fixed picking location, this allows stock to be replenished even if it falls below the minimum level, because the system can determine which items need to be replenished, even if there aren't any left.</span></span>  
2. <span data-ttu-id="12a0d-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-113">Click New.</span></span>
3. <span data-ttu-id="12a0d-114">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-114">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-115">Az USMF használata esetén választhatja a „A0001” cikket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-115">If you’re using USMF, you can select item A0001.</span></span>  
4. <span data-ttu-id="12a0d-116">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-116">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-117">Az USMF használata esetén választhatja a 2-es helyet.</span><span class="sxs-lookup"><span data-stu-id="12a0d-117">If you’re using USMF, you can select site 2.</span></span>  
5. <span data-ttu-id="12a0d-118">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-118">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-119">Az USMF használata esetén kiválaszthatja az 24-es raktárt.</span><span class="sxs-lookup"><span data-stu-id="12a0d-119">If you’re using USMF, you can select warehouse 24.</span></span>  
6. <span data-ttu-id="12a0d-120">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-120">In the Location field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-121">Az USMF használata esetén választhatja a CP-003 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-121">If you’re using USMF, you can select CP-003.</span></span>  
7. <span data-ttu-id="12a0d-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12a0d-122">Close the page.</span></span>

## <a name="create-a-replenishment-location-directive"></a><span data-ttu-id="12a0d-123">A feltöltési helyutasítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="12a0d-123">Create a replenishment location directive</span></span>
1. <span data-ttu-id="12a0d-124">Ugrás a Raktárkezelés > Beállítás > Helyutasítások elemre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-124">Go to Warehouse management > Setup > Location directives.</span></span>
    * <span data-ttu-id="12a0d-125">A Helyutasítások segítségével határozza meg, hogy honnan kell kitárolni a cikkeket a feltöltési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="12a0d-125">Location directives are used to determine where items should be picked from in the replenishment process.</span></span>  
2. <span data-ttu-id="12a0d-126">A Munkarendelés típusa mezőben válassza ki a „Feltöltés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-126">In the Work order type field, select 'Replenishment'.</span></span>
3. <span data-ttu-id="12a0d-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-127">Click New.</span></span>
4. <span data-ttu-id="12a0d-128">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12a0d-128">In the Name field, type a value.</span></span>
5. <span data-ttu-id="12a0d-129">A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-129">In the Work type field, select 'Pick'.</span></span>
6. <span data-ttu-id="12a0d-130">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-130">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-131">Az USMF használata esetén választhatja a 2-es helyet.</span><span class="sxs-lookup"><span data-stu-id="12a0d-131">If you’re using USMF, you can select site 2.</span></span>  
7. <span data-ttu-id="12a0d-132">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-132">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-133">Az USMF használata esetén kiválaszthatja az 24-es raktárt.</span><span class="sxs-lookup"><span data-stu-id="12a0d-133">If you’re using USMF, you can select warehouse 24.</span></span>  
8. <span data-ttu-id="12a0d-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-134">Click Save.</span></span>
9. <span data-ttu-id="12a0d-135">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-135">Click New.</span></span>
10. <span data-ttu-id="12a0d-136">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12a0d-136">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="12a0d-137">Adjon meg egy számot a Célmennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="12a0d-137">In the To quantity field, enter a number.</span></span>
    * <span data-ttu-id="12a0d-138">Például beállíthatja 9999 értékre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-138">For example, you can set it to 9999.</span></span>  
12. <span data-ttu-id="12a0d-139">Jelölje be a Felosztás engedélyezése jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="12a0d-139">Select the Allow split check box.</span></span>
    * <span data-ttu-id="12a0d-140">Ha ezt a lehetőséget választja, a munka-létrehozási folyamat a munka mennyiségek több helyen történő szétosztását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="12a0d-140">If you select this option, the work creation process will allow work line quantities to be split across multiple locations.</span></span>  
13. <span data-ttu-id="12a0d-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-141">Click Save.</span></span>
14. <span data-ttu-id="12a0d-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-142">Click New.</span></span>
15. <span data-ttu-id="12a0d-143">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12a0d-143">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="12a0d-144">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12a0d-144">In the Name field, type a value.</span></span>
17. <span data-ttu-id="12a0d-145">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-145">Click Save.</span></span>
18. <span data-ttu-id="12a0d-146">Kattintson A lekérdezés szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-146">Click Edit query.</span></span>
    * <span data-ttu-id="12a0d-147">Ezt a lekérdezést beállíthatja azon korlátozások hozzáadására, ahonnan ki lehet választani a készletet a feltöltési folyamat során.</span><span class="sxs-lookup"><span data-stu-id="12a0d-147">You can edit this query to add restrictions where inventory can be selected from in the replenishment process.</span></span> <span data-ttu-id="12a0d-148">Például ez lehet az a készlet is, amelyet csak a raktárház raktárából lehet használni.</span><span class="sxs-lookup"><span data-stu-id="12a0d-148">For example, it could be that inventory should only be used from the Bulk area of the warehouse.</span></span>  
19. <span data-ttu-id="12a0d-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-149">Click OK.</span></span>
20. <span data-ttu-id="12a0d-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12a0d-150">Close the page.</span></span>

## <a name="create-a-replenishment-work-template"></a><span data-ttu-id="12a0d-151">A feltöltési munkasablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="12a0d-151">Create a replenishment work template</span></span>
1. <span data-ttu-id="12a0d-152">Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-152">Go to Warehouse management > Setup > Work > Work templates.</span></span>
    * <span data-ttu-id="12a0d-153">A munkasablon segítségével adhat utasításokat a rendszernek, hogy miként kell létrehozni a Min./max. feltöltési munkát.</span><span class="sxs-lookup"><span data-stu-id="12a0d-153">The work template is use to guide the system as to how the min/max replenishment work must be created.</span></span> <span data-ttu-id="12a0d-154">Legalább egy kitárolási és betárolási munkasablonnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="12a0d-154">As a minimum, there must be a work template line for a pick and a put.</span></span> <span data-ttu-id="12a0d-155">A munkasablon azt jeleníti meg, hogy ez Érvénytelen addig, amíg az összes szükséges információt ki nem töltötték.</span><span class="sxs-lookup"><span data-stu-id="12a0d-155">The work template will say that it’s Invalid until all the necessary information has been filled in.</span></span>  
2. <span data-ttu-id="12a0d-156">A Munkarendelés típusa mezőben válassza ki a „Feltöltés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-156">In the Work order type field, select 'Replenishment'.</span></span>
3. <span data-ttu-id="12a0d-157">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-157">Click New.</span></span>
4. <span data-ttu-id="12a0d-158">Írjon be egy értéket a Munkasablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12a0d-158">In the Work template field, type a value.</span></span>
5. <span data-ttu-id="12a0d-159">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-159">Click Save.</span></span>
6. <span data-ttu-id="12a0d-160">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-160">Click New.</span></span>
7. <span data-ttu-id="12a0d-161">A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-161">In the Work type field, select 'Pick'.</span></span>
8. <span data-ttu-id="12a0d-162">A Munkaosztály-azonosító mezőben írjon be vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-162">In the Work class ID field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-163">Ennek a feltöltéshez kapcsolódó munkaosztálynak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="12a0d-163">This should be a work class related to replenishment.</span></span> <span data-ttu-id="12a0d-164">Ha az USMF-et használ, jelölje be a „Feltöltés” opciót.</span><span class="sxs-lookup"><span data-stu-id="12a0d-164">If you’re using USMF, select Replenish.</span></span>  
9. <span data-ttu-id="12a0d-165">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-165">Click New.</span></span>
10. <span data-ttu-id="12a0d-166">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12a0d-166">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="12a0d-167">A Munkatípus mezőben válassza a „Betárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-167">In the Work type field, select 'Put'.</span></span>
12. <span data-ttu-id="12a0d-168">A Munkaosztály-azonosító mezőben írjon be vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-168">In the Work class ID field, enter or select a value.</span></span>
13. <span data-ttu-id="12a0d-169">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-169">Click Save.</span></span>
14. <span data-ttu-id="12a0d-170">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12a0d-170">Close the page.</span></span>

## <a name="create-a-new-replenishment-template"></a><span data-ttu-id="12a0d-171">Egy új feltöltési sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="12a0d-171">Create a new replenishment template</span></span>
1. <span data-ttu-id="12a0d-172">Ugorjon a Raktárkezelés > Beállítás > Feltöltés > Feltöltési sablonok pontra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-172">Go to Warehouse management > Setup > Replenishment > Replenishment templates.</span></span>
    * <span data-ttu-id="12a0d-173">A feltöltési sablon segítségével határozza meg a cikkeket, a mennyiségeket és a feltöltési helyet.</span><span class="sxs-lookup"><span data-stu-id="12a0d-173">The replenishment template is used to define the items and quantities, and the location to replenish.</span></span>  
2. <span data-ttu-id="12a0d-174">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-174">Click New.</span></span>
3. <span data-ttu-id="12a0d-175">Írjon be egy értéket a Feltöltési sablon mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12a0d-175">In the Replenish template field, type a value.</span></span>
    * <span data-ttu-id="12a0d-176">Adjon a sablonnak egy nevet, amely azt jelzi, hogy ez minimális vagy maximális feltöltés.</span><span class="sxs-lookup"><span data-stu-id="12a0d-176">Give the template a name to indicate that it’s for min/max replenishment.</span></span>  
4. <span data-ttu-id="12a0d-177">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-177">In the Description field, type a value.</span></span>
5. <span data-ttu-id="12a0d-178">Jelölje be a Hullámigény engedélyezése a nem lefoglalt mennyiségek használatához jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="12a0d-178">Select the Allow wave demand to use unreserved quantities check box.</span></span>
    * <span data-ttu-id="12a0d-179">Ha ezt a lehetőséget választja, lehetővé válik a hullám igényfeltöltése min./max. feltöltéshez kapcsolódó mennyiségek felhasználására.</span><span class="sxs-lookup"><span data-stu-id="12a0d-179">If you select this option, it enables wave demand replenishment to consume quantities that are related to min/max replenishment.</span></span> <span data-ttu-id="12a0d-180">Ez például akkor lehet hasznos, ha a minimális/maximális feltöltési munka azonnali feldolgozása nem történik meg annak érdekében, hogy a szükségtelen igény feltöltési munka létrehozását megakadályozzák.</span><span class="sxs-lookup"><span data-stu-id="12a0d-180">For example, this might be useful if the min/max replenishment work isn’t processed immediately, to avoid unnecessary demand replenishment work from being created.</span></span>  
6. <span data-ttu-id="12a0d-181">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-181">Click New.</span></span>
7. <span data-ttu-id="12a0d-182">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="12a0d-182">In the Sequence number field, enter a number.</span></span>
8. <span data-ttu-id="12a0d-183">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-183">In the Description field, type a value.</span></span>
9. <span data-ttu-id="12a0d-184">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12a0d-184">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="12a0d-185">A Feltöltési egység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-185">In the Replenishment unit field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-186">Válassza ki például a darab lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-186">For example, select pcs.</span></span> <span data-ttu-id="12a0d-187">Ez a beállítás kötelező.</span><span class="sxs-lookup"><span data-stu-id="12a0d-187">This setting is mandatory.</span></span> <span data-ttu-id="12a0d-188">Lehetővé teszi egy másik mértékegység meghatározását a feltöltési munkára vonatkozóan, amely összes van hasonlítva az ezen sablon minimális és maximális készletszintjére vonatkozóan meghatározott egységgel.</span><span class="sxs-lookup"><span data-stu-id="12a0d-188">It allows you to specify a different unit of measurement for replenishment work compared to the unit specified for the minimum and maximum stock levels in this template.</span></span>  
11. <span data-ttu-id="12a0d-189">A Munkasablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-189">In the Work template field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-190">Válassza ki a korábban létrehozott munkasablont.</span><span class="sxs-lookup"><span data-stu-id="12a0d-190">Choose the work template that you created earlier.</span></span>  
12. <span data-ttu-id="12a0d-191">A Minimális mennyiség mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="12a0d-191">In the Minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="12a0d-192">Jelölje be a minimális mennyiséget, amely elindítja a feltöltést.</span><span class="sxs-lookup"><span data-stu-id="12a0d-192">Select the minimum quantity that should trigger the replenishment.</span></span> <span data-ttu-id="12a0d-193">Állítsa be például 50 értékre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-193">For example, set this to 50.</span></span> <span data-ttu-id="12a0d-194">Azt is megteheti, hogy a nulla értékű beállítást nem módosítja, ha feltölti a rögzített helyeket és az Üres rögzített helyek feltöltése lehetőséget Igen értékre állítja.</span><span class="sxs-lookup"><span data-stu-id="12a0d-194">It is possible to leave this set to zero, if you’re replenishing a fixed location and the Replenish empty fixed locations option is set to Yes.</span></span> <span data-ttu-id="12a0d-195">Szintén ajánlott, hogy Csak a rögzített helyek feltöltése lehetőséget választja ki a teljesítményszempontok miatt.</span><span class="sxs-lookup"><span data-stu-id="12a0d-195">We also recommend that you select the Replenish only fixed locations option for performance reasons.</span></span>  
13. <span data-ttu-id="12a0d-196">A Maximális mennyiség mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="12a0d-196">In the Maximum quantity field, enter a number.</span></span>
    * <span data-ttu-id="12a0d-197">Állítsa be például 100 értékre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-197">For example, set this to 100.</span></span>  
14. <span data-ttu-id="12a0d-198">Az Egység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-198">In the Unit field, enter or select a value.</span></span>
    * <span data-ttu-id="12a0d-199">Rendelje hozzá az egységet a minimális és maximális mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="12a0d-199">Assign the unit for the minimum and maximum quantities.</span></span> <span data-ttu-id="12a0d-200">Állítsa be például darab lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-200">For example, set this to pcs.</span></span>  
15. <span data-ttu-id="12a0d-201">Jelölje be az Üres rögzített helyek feltöltése jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="12a0d-201">Select the Replenish empty fixed locations check box.</span></span>
    * <span data-ttu-id="12a0d-202">Jelölje be ezt a jelölőnégyzetet a rögzített helyek feltöltéséhez, ha azok üresek.</span><span class="sxs-lookup"><span data-stu-id="12a0d-202">Select this check box to replenish fixed locations when they are empty.</span></span> <span data-ttu-id="12a0d-203">Ellenkező esetben csak azok a helyek lesznek feltöltve, ahol van készleten lévő mennyiség.</span><span class="sxs-lookup"><span data-stu-id="12a0d-203">Otherwise, only the locations where there is a quantity on hand will be replenished.</span></span>  
16. <span data-ttu-id="12a0d-204">Jelölje be a Csak a rögzített helyek feltöltése jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="12a0d-204">Select the Replenish only fixed locations check box.</span></span>
17. <span data-ttu-id="12a0d-205">Kattintson a Termékek kijelölése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-205">Click Select products.</span></span>
    * <span data-ttu-id="12a0d-206">Ez a hely határozza meg. hogy mely termékeket kell feltölteni.</span><span class="sxs-lookup"><span data-stu-id="12a0d-206">This is the place to define which products should be replenished.</span></span> <span data-ttu-id="12a0d-207">Ha a Rögzített kitárolási helyek lehetőséget választja, akkor is meg kell határoznia a helyeket a lekérdezésben.</span><span class="sxs-lookup"><span data-stu-id="12a0d-207">If the Fixed picking locations option is selected, you also need to define the locations in this query.</span></span> <span data-ttu-id="12a0d-208">A változat-specifikus lekérdezések is ugyanúgy elérhetőek, mint a termékspecifikus lekérdezések.</span><span class="sxs-lookup"><span data-stu-id="12a0d-208">Variant-specific queries are available as well product-specific queries.</span></span>  
18. <span data-ttu-id="12a0d-209">Válassza ki a Cikkek sora lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-209">Select the Items row.</span></span>
19. <span data-ttu-id="12a0d-210">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12a0d-210">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="12a0d-211">Válassza ki azokat a cikkeket, amelyeket fel kell tölteni a rögzített helyeken.</span><span class="sxs-lookup"><span data-stu-id="12a0d-211">Select the items that should be replenished at the fixed locations.</span></span> <span data-ttu-id="12a0d-212">Írja be például A* szöveget az összes A betűvel kezdődő cikkszám kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="12a0d-212">For example, type A* to select all item numbers beginning with A.</span></span>  
20. <span data-ttu-id="12a0d-213">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-213">Click Add.</span></span>
    * <span data-ttu-id="12a0d-214">Adja hozzá a Hely entitást (kivéve, ha már létezik) annak érdekében, hogy lehetővé váljon a Fix kivételi helyekhez történő feltöltési munka korlátozása a raktár meghatározott területén belül.</span><span class="sxs-lookup"><span data-stu-id="12a0d-214">Add the Location entity (unless it already exists) to be able to restrict the replenishment work to the fixed picking locations within a specific area of the warehouse.</span></span>  
21. <span data-ttu-id="12a0d-215">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12a0d-215">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="12a0d-216">Állítsa be a Tábla mezőt a Helyek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-216">Set the Table field to Locations.</span></span>
23. <span data-ttu-id="12a0d-217">Válassza ki a Helyprofil azonosítója értéket a Mező mezőben.</span><span class="sxs-lookup"><span data-stu-id="12a0d-217">In the Field field, select Location profile ID.</span></span>
24. <span data-ttu-id="12a0d-218">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-218">In the Criteria field, enter or select a value.</span></span>
25. <span data-ttu-id="12a0d-219">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-219">Click OK.</span></span>
26. <span data-ttu-id="12a0d-220">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12a0d-220">Close the page.</span></span>

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a><span data-ttu-id="12a0d-221">A feltöltési folyamat beállítása a kötegelt feladatként történő futtatáshoz</span><span class="sxs-lookup"><span data-stu-id="12a0d-221">Set the replenishment process to run as a batch job</span></span>
1. <span data-ttu-id="12a0d-222">Ugorjon a Raktárkezelés > Feltöltés > Feltöltések pontra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-222">Go to Warehouse management > Replenishment > Replenishments.</span></span>
    * <span data-ttu-id="12a0d-223">A Feltöltések lap lehetővé teszi, hogy egy kötegelt feladatként futassa a feltöltést vagy azt követeli, hogy manuálisan elindult feltöltésre legyen beállítva.</span><span class="sxs-lookup"><span data-stu-id="12a0d-223">The Replenishments page allows you to set up replenishment to run as a batch job, or to require that it’s started manually.</span></span>  
2. <span data-ttu-id="12a0d-224">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-224">Click Filter.</span></span>
3. <span data-ttu-id="12a0d-225">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12a0d-225">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="12a0d-226">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12a0d-226">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="12a0d-227">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-227">Click OK.</span></span>
6. <span data-ttu-id="12a0d-228">Bontsa ki a Futtatás a háttérben szakaszt.</span><span class="sxs-lookup"><span data-stu-id="12a0d-228">Expand the Run in the background section.</span></span>
7. <span data-ttu-id="12a0d-229">Állítsa be a Kötegelt feldolgozás lehetőséget Igen értékre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-229">Set the Batch processing option to Yes.</span></span>
8. <span data-ttu-id="12a0d-230">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="12a0d-230">Click Recurrence.</span></span>
9. <span data-ttu-id="12a0d-231">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-231">Select the No end date option.</span></span>
10. <span data-ttu-id="12a0d-232">Válassza ki az Ismétlődési mintát.</span><span class="sxs-lookup"><span data-stu-id="12a0d-232">Set the Recurrance pattern.</span></span>
    * <span data-ttu-id="12a0d-233">Válassza ki a Napok lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="12a0d-233">For example, select Days.</span></span>  
11. <span data-ttu-id="12a0d-234">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-234">Click OK.</span></span>
12. <span data-ttu-id="12a0d-235">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12a0d-235">Click OK.</span></span>


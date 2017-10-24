--- 
title: "Kamatfeldolgozás"
description: "Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 543ac29ac1b1cbad52f1c155ac90b04d0c122a1f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="process-interest"></a><span data-ttu-id="798f1-103">Kamatfeldolgozás</span><span class="sxs-lookup"><span data-stu-id="798f1-103">Process interest</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="798f1-104">Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="798f1-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="798f1-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="798f1-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="798f1-106">Állítsa be a kamatot a feladási profilon</span><span class="sxs-lookup"><span data-stu-id="798f1-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="798f1-107">Ugorjon a Követel és beszedések > Beállítás > Vevői feladási profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="798f1-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="798f1-108">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="798f1-108">Click Edit.</span></span>
    * <span data-ttu-id="798f1-109">Válasszon ki egy kamatkódot a legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="798f1-109">Select an interest code from the drop-down list.</span></span> <span data-ttu-id="798f1-110">Ha nem szeretne kamatot számítani a tranzakciókhoz ehhez a feladói profilhoz, hagyja a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="798f1-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="798f1-111">A Tábla korlátozási lapján módosíthatja a kamatfeldolgozás módját.</span><span class="sxs-lookup"><span data-stu-id="798f1-111">The Table restriction tab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="798f1-112">Ha ez a mező Igen értékre van állítva, a rendszer számít kamatot a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="798f1-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="798f1-113">Kamatszámítás</span><span class="sxs-lookup"><span data-stu-id="798f1-113">Calculate interest</span></span>
1. <span data-ttu-id="798f1-114">Ugorjon a Követel és beszedések > Kamat > Kamatlevél létrehozása pontra.</span><span class="sxs-lookup"><span data-stu-id="798f1-114">Go to Credit and collections > Interest > Create interest notes.</span></span>
    * <span data-ttu-id="798f1-115">Ki kell választania azokat a tranzakciótípusokat, amelyekhez kamatot kíván számítani.</span><span class="sxs-lookup"><span data-stu-id="798f1-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="798f1-116">Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.</span><span class="sxs-lookup"><span data-stu-id="798f1-116">All of the open transactions for these types will be included in the calculation.</span></span>  
    * <span data-ttu-id="798f1-117">Ha a Kamat lehetőséget választja, kamatos kamatot számíthat.</span><span class="sxs-lookup"><span data-stu-id="798f1-117">If you select Interest, you will calculate interest on interest.</span></span> <span data-ttu-id="798f1-118">A kamatos kamat számításához ellenőrizze az adott törvényeket, mielőtt ilyen tranzakciókat végezne.</span><span class="sxs-lookup"><span data-stu-id="798f1-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
    * <span data-ttu-id="798f1-119">A kamat számítása ettől a dátumtól a „Záró dátum” dátumig történik.</span><span class="sxs-lookup"><span data-stu-id="798f1-119">Interest will be calculated from this date to the "To date".</span></span> <span data-ttu-id="798f1-120">Ha nem ad meg „Kezdő dátum” dátumot, akkor a fel nem adott kamatlevelek törlésre kerülnek, és a kamat újraszámításra kerül a tranzakció dátumától.</span><span class="sxs-lookup"><span data-stu-id="798f1-120">If you do not specific a "From date", then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>  
2. <span data-ttu-id="798f1-121">Adja meg a kamatlevél dátumát.</span><span class="sxs-lookup"><span data-stu-id="798f1-121">Enter the date of the interest note.</span></span>
    * <span data-ttu-id="798f1-122">Háromféle feladási profil lehetőség létezik: Számla – a vevő számlájához rendelt feladási profil minden kamatlevél esetén.</span><span class="sxs-lookup"><span data-stu-id="798f1-122">There are three posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="798f1-123">Kiválasztott – a Feladási mezőben megadott feladási profil használata.</span><span class="sxs-lookup"><span data-stu-id="798f1-123">Select – Use the posting profile that you select in the Posting profile field.</span></span>   <span data-ttu-id="798f1-124">Tranzakció – az egyes kamatleveleknél kamat számításához használt tranzakciók egyéni feladási profiljának használata.</span><span class="sxs-lookup"><span data-stu-id="798f1-124">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="798f1-125">Az olyan tranzakciók esetében, amelyekhez nincs hozzárendelve feladási profil, a rendszer a Kinnlevőségek paraméterei képernyő Főkönyv és áfa területén megadott feladási profilt fogja használni.</span><span class="sxs-lookup"><span data-stu-id="798f1-125">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
    * <span data-ttu-id="798f1-126">Válasszon ki egy feladási profilt itt, ha módosította a „Feladási profil használata képernyő” lehetőséget „Kiválasztott” lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="798f1-126">Select a posting profile here if you changed "Use posting profile from" to "Select".</span></span>  
3. <span data-ttu-id="798f1-127">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="798f1-127">Expand or collapse the Records to include section.</span></span>
4. <span data-ttu-id="798f1-128">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="798f1-128">Click Filter.</span></span>
5. <span data-ttu-id="798f1-129">A Feltétel mezőben adjon meg Vevőazonosítót.</span><span class="sxs-lookup"><span data-stu-id="798f1-129">In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="798f1-130">Adja meg például az „US-001”-et.</span><span class="sxs-lookup"><span data-stu-id="798f1-130">For example, enter 'US-001'..</span></span>
6. <span data-ttu-id="798f1-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="798f1-131">Click OK.</span></span>
7. <span data-ttu-id="798f1-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="798f1-132">Click OK.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="798f1-133">Kamatlevelek nyomtatása</span><span class="sxs-lookup"><span data-stu-id="798f1-133">Print interest notes</span></span>
1. <span data-ttu-id="798f1-134">Ugorjon a Követel és beszedések > Kamat > Kamatlevél ellenőrzése és feldolgozása pontra.</span><span class="sxs-lookup"><span data-stu-id="798f1-134">Go to Credit and collections > Interest > Review and process interest notes.</span></span>
2. <span data-ttu-id="798f1-135">Az Állapot mezőben válassza ki a „Létrehozva” értéket.</span><span class="sxs-lookup"><span data-stu-id="798f1-135">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="798f1-136">A Nyomtatott mezőben válassza a „Nem nyomtatva” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="798f1-136">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="798f1-137">Kattintson a Nyomtatás parancsra.</span><span class="sxs-lookup"><span data-stu-id="798f1-137">Click Print.</span></span>
5. <span data-ttu-id="798f1-138">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="798f1-138">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="798f1-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="798f1-139">Click OK.</span></span>
7. <span data-ttu-id="798f1-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="798f1-140">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="798f1-141">Kamatlevél feladása</span><span class="sxs-lookup"><span data-stu-id="798f1-141">Post the interest note</span></span>
1. <span data-ttu-id="798f1-142">Válasszon ki egy olyan kamatlevelet, amely már feladásra kész (az állapota létrehozott).</span><span class="sxs-lookup"><span data-stu-id="798f1-142">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="798f1-143">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="798f1-143">Click Post.</span></span>
3. <span data-ttu-id="798f1-144">A kamatlevél feladási dátumának megadása.</span><span class="sxs-lookup"><span data-stu-id="798f1-144">Enter the posting date for the interest note.</span></span>
    * <span data-ttu-id="798f1-145">Jelölje be az Igent, ha az egyes kamatlevelekhez egyenként szeretné létrehozni a főkönyvi tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="798f1-145">Select Yes to create a general ledger transaction for each interest note.</span></span>     <span data-ttu-id="798f1-146">Ha nem jelöli be az Igent, akkor a vevő kamatleveleinek kamatai halmozódnak és egyetlen tranzakcióként kerülnek a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="798f1-146">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="798f1-147">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="798f1-147">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="798f1-148">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="798f1-148">Click OK.</span></span>
6. <span data-ttu-id="798f1-149">Az Állapot mezőben válassza ki a „Feladott” értéket.</span><span class="sxs-lookup"><span data-stu-id="798f1-149">In the Status field, select 'Posted'.</span></span>


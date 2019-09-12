---
title: Kamatfeldolgozás
description: Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7170a7a14237058064ed3091e9437cae312e6bd5
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916276"
---
# <a name="process-interest"></a><span data-ttu-id="a4181-103">Kamatfeldolgozás</span><span class="sxs-lookup"><span data-stu-id="a4181-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a4181-104">Ez az eljárás a kamatlevél létrehozását, nyomtatását és feladását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="a4181-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="a4181-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a4181-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="a4181-106">Állítsa be a kamatot a feladási profilon</span><span class="sxs-lookup"><span data-stu-id="a4181-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="a4181-107">A **navigációs ablaktáblán** lépjen a **Modulok > Követelések és beszedések > Beállítás > Vevői feladási profilok** részre.</span><span class="sxs-lookup"><span data-stu-id="a4181-107">In the **Navigation pane**, go to **Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="a4181-108">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a4181-108">Click **Edit**.</span></span>
3. <span data-ttu-id="a4181-109">A **Beállítás** gyorslap **Kamatkód** mezőjében válassza ki a kamatkódot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="a4181-109">In the **Setup fastTab**, in the **Interest code** field, select an interest code from the drop-down list.</span></span> <span data-ttu-id="a4181-110">Ha nem szeretne kamatot számítani a tranzakciókhoz ehhez a feladói profilhoz, hagyja a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="a4181-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span> <span data-ttu-id="a4181-111">A **Táblakorlátozások** gyorslapon módosíthatja a kamatfeldolgozás módját.</span><span class="sxs-lookup"><span data-stu-id="a4181-111">The **Table restriction** fastTab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="a4181-112">Ha ez a mező Igen értékre van állítva, a rendszer számít kamatot a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="a4181-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="a4181-113">Kamatszámítás</span><span class="sxs-lookup"><span data-stu-id="a4181-113">Calculate interest</span></span>
1. <span data-ttu-id="a4181-114">A **navigációs ablaktáblán** lépjen a **Modulok > Követelések és beszedések > Kamat > Kamatlevelek létrehozása** részre.</span><span class="sxs-lookup"><span data-stu-id="a4181-114">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Create interest notes**.</span></span>
2. <span data-ttu-id="a4181-115">Ki kell választania azokat a tranzakciótípusokat, amelyekhez kamatot kíván számítani.</span><span class="sxs-lookup"><span data-stu-id="a4181-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="a4181-116">Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.</span><span class="sxs-lookup"><span data-stu-id="a4181-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="a4181-117">Ha a **Kamat** beállításnál az „Igen” értéket adja meg, kamatos kamatot számíthat.</span><span class="sxs-lookup"><span data-stu-id="a4181-117">If you set **Interest** to 'Yes', you will calculate interest on interest.</span></span> <span data-ttu-id="a4181-118">A kamatos kamat számításához ellenőrizze az adott törvényeket, mielőtt ilyen tranzakciókat végezne.</span><span class="sxs-lookup"><span data-stu-id="a4181-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
4. <span data-ttu-id="a4181-119">A **Kezdő dátum** mezőben adja meg a dátumot, amikortól kamatot szeretne számolni.</span><span class="sxs-lookup"><span data-stu-id="a4181-119">In the **From date** field, enter a date from which the interest will be calculated.</span></span> <span data-ttu-id="a4181-120">Ha nem ad meg értéket a **Kezdő dátum** mezőben, akkor a rendszer törli a fel nem adott kamatleveleket, majd újraszámítja a kamatot a tranzakció dátumától.</span><span class="sxs-lookup"><span data-stu-id="a4181-120">If you do not specific a **From date**, then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>
5. <span data-ttu-id="a4181-121">A **Záró dátum** mezőben adja meg a dátumot, ameddig kamatot szeretne számolni.</span><span class="sxs-lookup"><span data-stu-id="a4181-121">In the **To date** field, enter a date to which the interest would be calculated.</span></span>
6. <span data-ttu-id="a4181-122">A **Használt feladási profil helye** mezőben válasszon ki egy beállítást.</span><span class="sxs-lookup"><span data-stu-id="a4181-122">In the **Use posting profile from** field, select an option.</span></span> <span data-ttu-id="a4181-123">Háromféle feladási profil létezik:</span><span class="sxs-lookup"><span data-stu-id="a4181-123">There are three posting profile options:</span></span>
    - <span data-ttu-id="a4181-124">Számla – az egyes kamatlevelek vevőkódjához rendelt feladási profil használata.</span><span class="sxs-lookup"><span data-stu-id="a4181-124">Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span> 
    - <span data-ttu-id="a4181-125">Kiválasztott – a Feladási mezőben megadott feladási profil használata.</span><span class="sxs-lookup"><span data-stu-id="a4181-125">Select – Use the posting profile that you select in the Posting profile field.</span></span>
    - <span data-ttu-id="a4181-126">Tranzakció – az egyes kamatleveleknél kamat számításához használt tranzakciók egyéni feladási profiljának használata.</span><span class="sxs-lookup"><span data-stu-id="a4181-126">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="a4181-127">Az olyan tranzakciók esetében, amelyekhez nincs hozzárendelve feladási profil, a rendszer a Kinnlevőségek paraméterei képernyő Főkönyv és áfa területén megadott feladási profilt fogja használni.</span><span class="sxs-lookup"><span data-stu-id="a4181-127">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
7. <span data-ttu-id="a4181-128">Bontsa ki a **Szerepeltetni kívánt rekordok** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="a4181-128">Expand the **Records to include** fastTab.</span></span>
8. <span data-ttu-id="a4181-129">Kattintson a **Szűrő** parancsra.</span><span class="sxs-lookup"><span data-stu-id="a4181-129">Click **Filter**.</span></span>
9. <span data-ttu-id="a4181-130">A **Feltétel** mezőben adjon meg Vevőazonosítót.</span><span class="sxs-lookup"><span data-stu-id="a4181-130">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="a4181-131">Adja meg például az „US-001”értéket.</span><span class="sxs-lookup"><span data-stu-id="a4181-131">For example, enter 'US-001'.</span></span>
6. <span data-ttu-id="a4181-132">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a4181-132">Click **OK**.</span></span>
7. <span data-ttu-id="a4181-133">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a4181-133">Click **OK**.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="a4181-134">Kamatlevelek nyomtatása</span><span class="sxs-lookup"><span data-stu-id="a4181-134">Print interest notes</span></span>
1. <span data-ttu-id="a4181-135">A **navigációs ablaktáblán** lépjen a **Modulok > Követelések és beszedések > Kamat > Kamatlevelek áttekintése és feldolgozása** részre.</span><span class="sxs-lookup"><span data-stu-id="a4181-135">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Review and process interest notes**.</span></span>
2. <span data-ttu-id="a4181-136">Az **Állapot** mezőben válassza ki a „Létrehozva” értéket.</span><span class="sxs-lookup"><span data-stu-id="a4181-136">In the **Status** field, select 'Created'.</span></span>
3. <span data-ttu-id="a4181-137">A **Nyomtatott** mezőben válassza a „Nem nyomtatva” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a4181-137">In the **Printed** field, select 'Not printed'.</span></span>
4. <span data-ttu-id="a4181-138">Kattintson a **Nyomtatás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="a4181-138">Click **Print**.</span></span>
5. <span data-ttu-id="a4181-139">Bontsa ki a **Szerepeltetni kívánt rekordok** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="a4181-139">Expand the **Records to include** fastTab.</span></span>
6. <span data-ttu-id="a4181-140">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a4181-140">Click **OK**.</span></span>
7. <span data-ttu-id="a4181-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a4181-141">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="a4181-142">Kamatlevél feladása</span><span class="sxs-lookup"><span data-stu-id="a4181-142">Post the interest note</span></span>
1. <span data-ttu-id="a4181-143">Válasszon ki egy olyan kamatlevelet, amely már feladásra kész (az állapota létrehozott).</span><span class="sxs-lookup"><span data-stu-id="a4181-143">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="a4181-144">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a4181-144">Click **Post**.</span></span>
3. <span data-ttu-id="a4181-145">A kamatlevél feladási dátumának megadása.</span><span class="sxs-lookup"><span data-stu-id="a4181-145">Enter the posting date for the interest note.</span></span> <span data-ttu-id="a4181-146">Jelölje be az Igent, ha az egyes kamatlevelekhez egyenként szeretné létrehozni a főkönyvi tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="a4181-146">Select Yes to create a general ledger transaction for each interest note.</span></span> <span data-ttu-id="a4181-147">Ha nem jelöli be az Igent, akkor a vevő kamatleveleinek kamatai halmozódnak és egyetlen tranzakcióként kerülnek a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="a4181-147">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="a4181-148">Bontsa ki a **Szerepeltetni kívánt rekordok** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="a4181-148">Expand the **Records to include** fastTab.</span></span>
5. <span data-ttu-id="a4181-149">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a4181-149">Click **OK**.</span></span>
6. <span data-ttu-id="a4181-150">Az **Állapot** mezőben válassza ki a „Feladott” értéket.</span><span class="sxs-lookup"><span data-stu-id="a4181-150">In the **Status** field, select 'Posted'.</span></span>


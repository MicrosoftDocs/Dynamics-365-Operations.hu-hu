---
title: A pénzügyi év lezárása
description: Ez a folyamat bemutatja az év végi zárás folyamatát, amely az egyenlegeket áthelyezi az új pénzügyi évbe.
author: aprilolson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b82cc7e4077a1bd50eab30f234c2f63c79e81d84
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994690"
---
# <a name="close-the-fiscal-year"></a><span data-ttu-id="2225e-103">A pénzügyi év lezárása</span><span class="sxs-lookup"><span data-stu-id="2225e-103">Close the fiscal year</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2225e-104">Ez a folyamat bemutatja az év végi zárás folyamatát, amely az egyenlegeket áthelyezi az új pénzügyi évbe.</span><span class="sxs-lookup"><span data-stu-id="2225e-104">This procedure steps through the year end close process that transfers balances to a new fiscal year.</span></span>


## <a name="validate-year-end-close-parameters"></a><span data-ttu-id="2225e-105">Ellenőrizze az év végi zárás paramétereit</span><span class="sxs-lookup"><span data-stu-id="2225e-105">Validate year-end close parameters</span></span>
1. <span data-ttu-id="2225e-106">Válassz a **Navigációs panel >Modulok > Főkönyv > Főkönyv beállítás > Főkönyv paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2225e-106">Go to **Navigation pane > Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="2225e-107">Bontsa ki a **Pénzügyi év zárása** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2225e-107">Expand the **Fiscal year close** section.</span></span>
3. <span data-ttu-id="2225e-108">Válassza az „Igen” vagy „Nem” lehetőséget az **Évzáró tranzakciók törlése átvezetés közben** beállításnál.</span><span class="sxs-lookup"><span data-stu-id="2225e-108">Select 'Yes' or 'No' for the **Delete close-of-year transactions during transfer** option.</span></span>
    
    <span data-ttu-id="2225e-109">Ha a pénzügyi év már le van zárva, és újrafuttatják az év végi zárást, ez a beállítás fontos.</span><span class="sxs-lookup"><span data-stu-id="2225e-109">If the fiscal year has already been closed and the year-end close is being run again, this setting is important.</span></span> <span data-ttu-id="2225e-110">Ha Igen értékre van állítva, az előző év végi zárási bizonylat törlésre kerül, és az összes számla nyitóegyenlegéhez új bizonylat jön létre.</span><span class="sxs-lookup"><span data-stu-id="2225e-110">If set to Yes, the voucher for the previous year-end close will be deleted, and a new voucher will be created for all accounts beginning balances.</span></span> <span data-ttu-id="2225e-111">Ha Nem értékre van állítva, a korábbi bizonylat megmarad, és új bizonylat csak az utolsó évlezárás után könyvelt tételek helyesbítéséhez jön létre.</span><span class="sxs-lookup"><span data-stu-id="2225e-111">If set to No, the previous voucher will remain and a new voucher will only be created for adjusting entries that were posted after the last year-end close.</span></span>

4. <span data-ttu-id="2225e-112">Válassza az „Igen” vagy „Nem” elemet a **Záró tranzakciók létrehozása átvezetés közben** lehetőségnél.</span><span class="sxs-lookup"><span data-stu-id="2225e-112">Select 'Yes' or 'No' for the **Create closing transactions during transfer** option.</span></span>

    <span data-ttu-id="2225e-113">Ha Igen értékre van állítva, két tranzakció jön létre.</span><span class="sxs-lookup"><span data-stu-id="2225e-113">If set to Yes, two transactions are created.</span></span> <span data-ttu-id="2225e-114">Egy bizonylat jön létre a lezárás alatt álló pénzügyi évhez, hogy az eredménykimutatási főkönyvi számlák egyenlegét lenullázza, és egy második bizonylat is létrejön a következő pénzügyi évi nyitó egyenlegekhez.</span><span class="sxs-lookup"><span data-stu-id="2225e-114">One voucher is created in the fiscal year being closed to bring the balances of the P&L ledger accounts down to zero and a second voucher is created in the next fiscal year for the beginning balances.</span></span> <span data-ttu-id="2225e-115">Ha Nem értékre van állítva, egyetlen bizonylat jön létre a következő pénzügyi évi nyitó egyenlegekhez.</span><span class="sxs-lookup"><span data-stu-id="2225e-115">If set to No, a single voucher is created in the next fiscal year for the beginning balances.</span></span>  

5. <span data-ttu-id="2225e-116">Válassza az „Igen” vagy „Nem” elemet a **Pénzügyi év beállítása véglegesen lezárt állapotúra** lehetőségnél.</span><span class="sxs-lookup"><span data-stu-id="2225e-116">Select 'Yes' or 'No' for the **Set fiscal year status to permanently closed** option.</span></span>

    <span data-ttu-id="2225e-117">Ha Igen értékre van állítva, a pénzügyi év állapota „Véglegesen lezárva” lesz.</span><span class="sxs-lookup"><span data-stu-id="2225e-117">If set to Yes, the fiscal year status will be set to Permanently closed.</span></span>  <span data-ttu-id="2225e-118">Mivel a véglegesen lezárt év nem nyitható meg újra, az ajánlott gyakorlat a beállítás Nem értékre állítása.</span><span class="sxs-lookup"><span data-stu-id="2225e-118">Because a permanently closed year cannot be reopened, it would be a best practice to set this option to No.</span></span>  

6. <span data-ttu-id="2225e-119">Válassza „Igen” vagy „Nem” elemet a **Bizonylatszámot meg kell adni az év végi zárás során** lehetőségnél.</span><span class="sxs-lookup"><span data-stu-id="2225e-119">Select 'Yes' or 'No' for the **Voucher number must be filled in during the year end close** option.</span></span>

    <span data-ttu-id="2225e-120">Ha Igen értékre van állítva, a bizonylatszámot manuálisan kell megadni az év végi zárás során.</span><span class="sxs-lookup"><span data-stu-id="2225e-120">If set to Yes, a voucher number must be manually entered during the year end close process.</span></span> <span data-ttu-id="2225e-121">Ennek a bizonylatszámnak a létrehozásához nem használatos számsorozat.</span><span class="sxs-lookup"><span data-stu-id="2225e-121">A number sequence is not used to generate this voucher number.</span></span> <span data-ttu-id="2225e-122">Az ajánlott gyakorlat a beállítás Igen értékre állítása.</span><span class="sxs-lookup"><span data-stu-id="2225e-122">It's a best practice to set this to Yes.</span></span>  

7. <span data-ttu-id="2225e-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2225e-123">Close the page.</span></span>
8. <span data-ttu-id="2225e-124">Ugorjon a **Főkönyv > Időszaki lezárás > Év végi lezárás** pontra.</span><span class="sxs-lookup"><span data-stu-id="2225e-124">Go to **General ledger > Period close > Year end close**.</span></span>
9. <span data-ttu-id="2225e-125">Az év végi zárási sablon létrehozásához kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="2225e-125">Click **New** to create a year-end close template.</span></span>

    <span data-ttu-id="2225e-126">Létrehozható egy sablon azon jogi személyek csoportjához, amelyhez az év zárást futtatni kívánjuk.</span><span class="sxs-lookup"><span data-stu-id="2225e-126">A template can be created for a group of legal entities for which to run the year-end close.</span></span> <span data-ttu-id="2225e-127">Ez a sablon újra felhasználható évről évre.</span><span class="sxs-lookup"><span data-stu-id="2225e-127">This template can be reused year after year.</span></span>  

10. <span data-ttu-id="2225e-128">A **Csoport neve** mezőben adja meg egy év végi zárási sablon nevét.</span><span class="sxs-lookup"><span data-stu-id="2225e-128">In the **Group name** field, enter a year-end close template name..</span></span>
11. <span data-ttu-id="2225e-129">A **Pénzügyi naptár** mezőben válassza ki azt az üzleti évet, amelyhez a sablont létre fogja hozna.</span><span class="sxs-lookup"><span data-stu-id="2225e-129">In the **Fiscal calendar** field, select the fiscal year for which the template will be created.</span></span>

    <span data-ttu-id="2225e-130">Az év végi zárási sablonban csak olyan jogi személyeket lehet csoportosítani, amelyek ugyanazt a pénzügyi évet használják.</span><span class="sxs-lookup"><span data-stu-id="2225e-130">Only legal entities which use the same fiscal year can be grouped together in the year-end close template.</span></span> <span data-ttu-id="2225e-131">Ennek oka, hogy az év zárása a pénzügyi év, nem pedig egy dátum kiválasztásával történik.</span><span class="sxs-lookup"><span data-stu-id="2225e-131">This is because the year end close is done by selecting a fiscal year, not a date.</span></span>  

12. <span data-ttu-id="2225e-132">A **Művelet panelen** kattintson a **Mentés** elemre.</span><span class="sxs-lookup"><span data-stu-id="2225e-132">On the **Action pane**, click **Save**.</span></span>
13. <span data-ttu-id="2225e-133">A **Jogi személyek** szakaszban kattintson a **Hozzáadás** gombra a sablonhoz tartozó jogi entitások kijelöléséhez.</span><span class="sxs-lookup"><span data-stu-id="2225e-133">In the **Legal entities** section, click **Add** to select the legal entities for this template.</span></span>
    
    <span data-ttu-id="2225e-134">Jogi személyek hozzáadhatók a kívánt jogi személyek vagy vagy szervezeti hierarchia kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="2225e-134">Legal entities can be added by either selecting the legal entities or by selecting an organizational hierarchy.</span></span>  <span data-ttu-id="2225e-135">Csak az ugyanazt a pénzügyi naptárat használó szervezeti hierarchiába tartozó jogi személyek adhatók hozzá.</span><span class="sxs-lookup"><span data-stu-id="2225e-135">Only legal entities with the organizational hierarchy with the same fiscal calendar selected will be added.</span></span>  

14. <span data-ttu-id="2225e-136">Válassza ki a jogi személyeket vagy a szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="2225e-136">Select either the legal entities or the organizational hierarchy.</span></span>
15. <span data-ttu-id="2225e-137">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2225e-137">Click **OK**.</span></span>
16. <span data-ttu-id="2225e-138">Az **Mérlegdimenziók átvitele** helyen válassza az „igen” vagy a „nem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2225e-138">Select 'Yes' or 'No' in the **Transfer balance sheet dimension**.</span></span>

    <span data-ttu-id="2225e-139">Mérlegszámláknál az ajánlott gyakorlat a beállítás Igen értékre állítása.</span><span class="sxs-lookup"><span data-stu-id="2225e-139">It's best practice to set this option to Yes for Balance sheet accounts.</span></span> <span data-ttu-id="2225e-140">Ez megőrzi a feladott tranzakciók pénzügyi dimenzióit a mérlegszámlák nyitó egyenlegének létrehozásánál.</span><span class="sxs-lookup"><span data-stu-id="2225e-140">This will maintain the financial dimensions on posted transactions when creating the beginning balances for the balance sheet accounts.</span></span> <span data-ttu-id="2225e-141">Eredményszámláknál dönthet úgy, hogy megőrzi a pénzügyi dimenziókat (Az összes lezárása), amikor az egyenlegek átkerülnek a Mérleg szerinti eredménybe, illetve dönthet úgy, hogy a pénzügyi dimenziókat lecseréli egy eltérő dimenzióértékre (Egyetlen lezárása).</span><span class="sxs-lookup"><span data-stu-id="2225e-141">For profit and loss accounts, you can select to maintain the financial dimensions (Close all) when the balances are moved to Retained earnings or you can select to have the financial dimensions replaced with a different dimension value (Close single).</span></span> <span data-ttu-id="2225e-142">Ha az Egyetlen lezárása lehetőséget választja, minden egyes dimenzióhoz megadhat egy dimenzióértéket, illetve dönthet úgy is, hogy üresen hagyja a mezőt.</span><span class="sxs-lookup"><span data-stu-id="2225e-142">If you choose Close single, you can define a specific dimension value for each dimension or even choose to leave it blank.</span></span>  

17. <span data-ttu-id="2225e-143">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="2225e-143">Click **Save**.</span></span>
18. <span data-ttu-id="2225e-144">A **Műveletpanelen** található **Pénzügyi zárás futtatása** kiválasztásával indítsa el az év végi zárást.</span><span class="sxs-lookup"><span data-stu-id="2225e-144">Start the year-end close by choosing **Run fiscal close** on the **Action Pane**.</span></span> <span data-ttu-id="2225e-145">Az év végi zárás lefut a kijelölt sablonon.</span><span class="sxs-lookup"><span data-stu-id="2225e-145">The year-end close will be run for the selected template.</span></span>  
19. <span data-ttu-id="2225e-146">Válassza ki az összes jogi személyt vagy egy részhalmazukat, amelyeken futtatni kívánja az év végi zárást.</span><span class="sxs-lookup"><span data-stu-id="2225e-146">Select all or a subset of legal entities from the template for which to run the year-end close.</span></span>

    <span data-ttu-id="2225e-147">Amikor először futtatnak év végi zárást, a nyitó egyenlegek beszerzéséhez a legtöbb szervezet dönthet úgy, hogy az év végi zárást a sablonon belüli valamennyi jogi személyen lefuttatják.</span><span class="sxs-lookup"><span data-stu-id="2225e-147">When first running the year-end close, to get beginning balance,s most organizations may choose to run the year-end close for all legal entities within the template.</span></span> <span data-ttu-id="2225e-148">Ha ezután kiigazító tételekre kerül sor, dönthet úgy, hogy az év végi zárást csak azon jogi személyeken futtatja le, amelyeknél kiigazítások történtek.</span><span class="sxs-lookup"><span data-stu-id="2225e-148">If adjusting entries are made after that, you may choose to run the year-end close for only the legal entities that have adjustments.</span></span>  

20. <span data-ttu-id="2225e-149">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2225e-149">Click **OK**.</span></span>
21. <span data-ttu-id="2225e-150">Válassza ki a pénzügyi évet, amelyen futtatni kívánja az év végi zárást.</span><span class="sxs-lookup"><span data-stu-id="2225e-150">Select the fiscal year for which to run the year-end close.</span></span>
22. <span data-ttu-id="2225e-151">A **Bizonylat mezőben** adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2225e-151">In the **Voucher field**, type a value.</span></span> <span data-ttu-id="2225e-152">Az ajánlott gyakorlat a pénzügyi év belefoglalása a bizonylatszámba, mivel így könnyebb megtalálni a létrehozott év végi zárási bizonylatot.</span><span class="sxs-lookup"><span data-stu-id="2225e-152">It's best practice to include the fiscal year in the voucher number, to make it easier to find the year-end close voucher that is created.</span></span>  
23. <span data-ttu-id="2225e-153">Az év végi zárás alapértelmezés szerint kötegelten fut.</span><span class="sxs-lookup"><span data-stu-id="2225e-153">The year-end close defaults to run in batch.</span></span> <span data-ttu-id="2225e-154">Az ajánlott gyakorlat a hosszú ideig futó folyamatok futtatását kötegelt módban végezni.</span><span class="sxs-lookup"><span data-stu-id="2225e-154">It's best practice for long-running processes to run in batch mode.</span></span> <span data-ttu-id="2225e-155">Ez általában egyike ezeknek a folyamatoknak, ezért a kötegelt módban történő futtatás az alapértelmezett.</span><span class="sxs-lookup"><span data-stu-id="2225e-155">This is typically one of those processes, which is why the default is to use batch mode.</span></span>  
24. <span data-ttu-id="2225e-156">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2225e-156">Click **OK**.</span></span>


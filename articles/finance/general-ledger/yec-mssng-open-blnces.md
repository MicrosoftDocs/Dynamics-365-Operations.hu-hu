---
title: Év végi záráskor hiányzó nyitó egyenlegek
description: Ez a témakör ismerteti, hogy miért hiányozhatnak nyitó egyenlegek egy év zárásakor, és hogyan tudja újból létrehozni ezeket az egyenlegeket, amennyiben hiányoznak.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028567"
---
# <a name="year-end-close-missing-opening-balances"></a><span data-ttu-id="e2119-103">Év végi záráskor hiányzó nyitó egyenlegek</span><span class="sxs-lookup"><span data-stu-id="e2119-103">Year-end close missing opening balances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2119-104">Ez a témakör ismerteti, hogy miért hiányozhatnak nyitó egyenlegek egy év zárásakor, és hogyan tudja újból létrehozni ezeket az egyenlegeket, amennyiben hiányoznak.</span><span class="sxs-lookup"><span data-stu-id="e2119-104">This topic explains why opening balances might be missing when you close a year, and how to rebuild those balances if they are missing.</span></span>

### <a name="symptom"></a><span data-ttu-id="e2119-105">Tünet</span><span class="sxs-lookup"><span data-stu-id="e2119-105">Symptom</span></span>

<span data-ttu-id="e2119-106">Miért nincsenek nyitó egyenlegek a Főkönyv év végi zárásának futtatása után?</span><span class="sxs-lookup"><span data-stu-id="e2119-106">Why are there no beginning balances after running the General ledger year-end close?</span></span> 

### <a name="resolution"></a><span data-ttu-id="e2119-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="e2119-107">Resolution</span></span>

<span data-ttu-id="e2119-108">Az alábbiakat érdemes ellenőriznie, ha végrehajtotta az év zárását a Főkönyvben, majd létrehozott egy főkönyvi kivonatot, amelyben nem láthatók nyitó egyenlegek a következő pénzügyi évre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="e2119-108">Here are things to check if you've closed a year in General ledger, and then generated a trial balance that doesn't display opening balances for the next fiscal year.</span></span>

<span data-ttu-id="e2119-109">Ha az **Előző zárás visszavonása** mezőnél az **Igen** érték szerepel, a rendszer ugyanarra a pénzügyi évre vonatkozóan vissza fogja vonni az előző év végi zárást.</span><span class="sxs-lookup"><span data-stu-id="e2119-109">If the **Undo previous close** field is set to **Yes**, the previous year-end close for the same fiscal year is being reversed.</span></span> <span data-ttu-id="e2119-110">Az év végi zárás visszavonási folyamatának futtatásakor a program a záró és nyitó egyenlegekhez kapcsolódó összes bejegyzést törli, mintha az évet nem zárták volna még le.</span><span class="sxs-lookup"><span data-stu-id="e2119-110">When running a process to reverse the year-end close, all entries for both closing and opening balances will be deleted, as if the year had never been closed.</span></span> <span data-ttu-id="e2119-111">A program a bizonylatokat is törli.</span><span class="sxs-lookup"><span data-stu-id="e2119-111">The vouchers are also deleted.</span></span> <span data-ttu-id="e2119-112">A program nem indítja el automatikusan újra az év végi zárás folyamatát.</span><span class="sxs-lookup"><span data-stu-id="e2119-112">The year-end close process will not run again automatically.</span></span> <span data-ttu-id="e2119-113">A folyamatot Önnek kell újraindítania. Ügyeljen rá, hogy az **Előző zárás visszavonása** lehetőség értékét a **Nem** értékre frissítse.</span><span class="sxs-lookup"><span data-stu-id="e2119-113">You must start the process again, this time updating the **Undo previous close** option to **No**.</span></span>

<span data-ttu-id="e2119-114">Ezt a forgatókönyvet az év végi zárással kapcsolatos GYIK témakör tárgyalja.</span><span class="sxs-lookup"><span data-stu-id="e2119-114">This scenario is covered in the year-end close FAQ topic.</span></span> <span data-ttu-id="e2119-115">További információ: [Év végi tevékenységek GYIK](faq-year-end-activities.md).</span><span class="sxs-lookup"><span data-stu-id="e2119-115">For more information, see [Year-end activities FAQ](faq-year-end-activities.md).</span></span>

### <a name="symptom"></a><span data-ttu-id="e2119-116">Tünet</span><span class="sxs-lookup"><span data-stu-id="e2119-116">Symptom</span></span>

<span data-ttu-id="e2119-117">Az év végi zárást úgy futtattam, hogy az **Előző zárás visszavonása** beállítás értéke **Nem** volt, de még mindig nem jelennek meg nyitó egyenlegek a pénzügyi évhez.</span><span class="sxs-lookup"><span data-stu-id="e2119-117">I ran year-end close with the **Undo previous close** option set to **No**, and I still do not have opening balances for my fiscal year.</span></span>

### <a name="resolution"></a><span data-ttu-id="e2119-118">Megoldás</span><span class="sxs-lookup"><span data-stu-id="e2119-118">Resolution</span></span>

<span data-ttu-id="e2119-119">Először ellenőrizze a kötegelt feladat állapotát.</span><span class="sxs-lookup"><span data-stu-id="e2119-119">First check the status of the batch job.</span></span> <span data-ttu-id="e2119-120">Az év lezárásához több különálló feladat tartozik, de a legkritikusabb lépés a **5.0.0. lépés** feladatleírással rendelkező kötegelt feladat.</span><span class="sxs-lookup"><span data-stu-id="e2119-120">Closing a year includes a number of separate tasks, but the most critical step is the batch task with the task description **Step 5.0.0**.</span></span> <span data-ttu-id="e2119-121">A nyitótranzakciók és opcionálisan a záró tranzakciók feladása a főkönyvbe ebben a lépésben történik.</span><span class="sxs-lookup"><span data-stu-id="e2119-121">Posting the opening transactions, and optionally the closing transactions, to General ledger takes place during this step.</span></span> 

<span data-ttu-id="e2119-122">[![Kötegelőzmény-lista](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span><span class="sxs-lookup"><span data-stu-id="e2119-122">[![Batch history list](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span></span>

<span data-ttu-id="e2119-123">Ha ez a lépés sikeresen befejeződött, de nem láthatók nyitó egyenlegek a **Főkönyvi kivonat lekérdezése** oldalon (**Főkönyv > Lekérdezések és jelentések > Főkönyvi kivonat**), vizsgálja meg az év végi zárás kötegelt feladatának eredményeit, hogy az Egyenlegek újbóli létrehozása lépés sikeresen befejeződött-e.</span><span class="sxs-lookup"><span data-stu-id="e2119-123">If this step ended successfully but you don’t see opening balances on the **Trial balance inquiry** page (**General ledger > Inquires and reports > Trial balance**), review the results of the year-end close batch job to see if the Rebuild balances step completed successfully.</span></span>

<span data-ttu-id="e2119-124">[![Az év végi zárás kötegelt feladatának eredményei](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span><span class="sxs-lookup"><span data-stu-id="e2119-124">[![Results of year-end close batch job](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span></span>

<span data-ttu-id="e2119-125">Ha ez a lépés bármilyen okból sikertelen volt, a nyitó (és opcionálisan a záró) tranzakciók feladása valószínűleg sikeres volt.</span><span class="sxs-lookup"><span data-stu-id="e2119-125">If this step has failed for any reason, the opening (and optionally closing) transactions were likely posted successfully.</span></span> <span data-ttu-id="e2119-126">A főkönyvi tranzakciók feladásának sikerességét a **Bizonylattranzakciók lekérdezése** oldal használatával ellenőrizheti, ha megadja a lezárt év év végi zárásakor megjelenő párbeszédablakán megadott bizonylat számát és dátumát (**Főkönyv > Lekérdezések és jelentések > Bizonylattranzakciók**).</span><span class="sxs-lookup"><span data-stu-id="e2119-126">You can verify that the General ledger transactions were posted successfully using the **Voucher transactions inquiry** page by specifying the voucher number and date provided on the year-end close dialog for the year that you closed, (**General Ledger > Inquiries and reports > Voucher transactions**).</span></span>

<span data-ttu-id="e2119-127">[![Bizonylattranzakciók lekérdezése](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span><span class="sxs-lookup"><span data-stu-id="e2119-127">[![Voucher transactions inquiry](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span></span>

<span data-ttu-id="e2119-128">Ha a nyitó (és opcionálisan a záró) bizonylatok jelen vannak, akkor nem kell újra futtatnia az év végi zárást.</span><span class="sxs-lookup"><span data-stu-id="e2119-128">If the opening (and optionally closing) vouchers are present, you don’t need to run the year-end close again.</span></span> <span data-ttu-id="e2119-129">Ehelyett olvassa el a következő szakaszt a következő lépésekkel kapcsolatos információkért.</span><span class="sxs-lookup"><span data-stu-id="e2119-129">Instead refer to the next section for information about how to move forward.</span></span>

### <a name="symptom"></a><span data-ttu-id="e2119-130">Tünet</span><span class="sxs-lookup"><span data-stu-id="e2119-130">Symptom</span></span>

<span data-ttu-id="e2119-131">Az év végi zárás „Egyenlegek újbóli létrehozása” lépés sikertelen volt, újra kell-e futtatnom a teljes év végi zárási folyamatot?</span><span class="sxs-lookup"><span data-stu-id="e2119-131">The “Rebuild balances” step in the year-end close failed, do I need to re-run the entire year-end close process?</span></span>

### <a name="resolution"></a><span data-ttu-id="e2119-132">Megoldás</span><span class="sxs-lookup"><span data-stu-id="e2119-132">Resolution</span></span>

<span data-ttu-id="e2119-133">Az Egyenlegek újbóli létrehozása lépés frissíti a Főkönyvi kivonat lekérdezésének létrehozása során használt Főkönyvi egyenlegek értékét.</span><span class="sxs-lookup"><span data-stu-id="e2119-133">The Rebuild balances step updates the General ledger balances that are used when the Trial balance inquiry is generated.</span></span>  <span data-ttu-id="e2119-134">Ez az év végi zárási folyamat utolsó lépése.</span><span class="sxs-lookup"><span data-stu-id="e2119-134">It is the final step in the year-end close process.</span></span>  <span data-ttu-id="e2119-135">Ha ez a lépés az egyetlen sikertelen lépés, a főkönyvi tranzakciók feladása sikerült.</span><span class="sxs-lookup"><span data-stu-id="e2119-135">If this step is the only step that failed, the General ledger transactions have posted successfully.</span></span>  <span data-ttu-id="e2119-136">Nem szükséges újra futtatnia az év végi zárást.</span><span class="sxs-lookup"><span data-stu-id="e2119-136">You do not need to run the year-end close again.</span></span> <span data-ttu-id="e2119-137">A folyamat futtatásával manuálisan újból létrehozhatja az egyenlegeket a **Pénzügyi dimenziókészletek** oldalon (**Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziókészletek**).</span><span class="sxs-lookup"><span data-stu-id="e2119-137">You can run the process to rebuild the balances manually using the **Financial dimension sets** page (**General ledger > Chart of accounts > Dimensions > Financial dimension sets**).</span></span>

<span data-ttu-id="e2119-138">[![Egyenlegek újbóli létrehozása gomb a Pénzügyi dimenziókészletek oldalon](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span><span class="sxs-lookup"><span data-stu-id="e2119-138">[![Rebuild balances button on Financial dimension sets page](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span></span>

<span data-ttu-id="e2119-139">Ha a lépés feldolgozása hosszú időt vesz igénybe, javasoljuk, hogy tekintse át a pénzügyi dimenziókészletekre vonatkozó gyakorlati tanácsokat a [Pénzügyi dimenziókészletek frissítésére vonatkozó gyakorlati tanácsok](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets) részben.</span><span class="sxs-lookup"><span data-stu-id="e2119-139">If this step takes a long time to process, we recommend reviewing the best practices for financial dimension sets as described in [Best practices for updating Financial dimension sets](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span></span> 


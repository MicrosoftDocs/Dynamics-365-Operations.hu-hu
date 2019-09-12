---
title: Fizetési felszólítások feldolgozása
description: Ez a cikk a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 326d9375670cb4f4990a4f7070bf923a28b2c025
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867655"
---
# <a name="process-collection-letters"></a><span data-ttu-id="25e9d-103">Fizetési felszólítások feldolgozása</span><span class="sxs-lookup"><span data-stu-id="25e9d-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25e9d-104">Ez a cikk a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="25e9d-104">This topic shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="25e9d-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="25e9d-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="25e9d-106">Állítson be egy fizetésifelszólítás-sorozatot a feladási profilon.</span><span class="sxs-lookup"><span data-stu-id="25e9d-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="25e9d-107">Lépjen a **navigációs ablaktábla > Modulok > Követelések és beszedések > Beállítás > Vevői feladási profilok** részre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="25e9d-108">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-108">Click **Edit**.</span></span>
3. <span data-ttu-id="25e9d-109">Válasszon egy fizetésifelszólítás-sorozatot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="25e9d-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="25e9d-110">Ha nem szeretne fizetési felszólításokat létrehozni a tranzakciókhoz ezzel a feladói profillal, hagyja a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="25e9d-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="25e9d-111">A **Táblakorlátozások** lap kibontásával módosíthatja a fizetési felszólítások feldolgozási módját.</span><span class="sxs-lookup"><span data-stu-id="25e9d-111">Expand the **Table restrictions** tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="25e9d-112">Ha ez a mező **Igen** értékre van állítva, fizetési felszólítások kerülnek létrehozásra a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="25e9d-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="25e9d-113">Fizetési felszólítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="25e9d-113">Create collection letters</span></span>
1. <span data-ttu-id="25e9d-114">Lépjen a **navigációs ablaktábla > Modulok > Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások létrehozása** részre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-114">Go to **Navigation pane > Modules > Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="25e9d-115">Válassza ki azokat a tranzakciótípusokat, amelyekre fizetési felszólítást szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="25e9d-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="25e9d-116">Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.</span><span class="sxs-lookup"><span data-stu-id="25e9d-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="25e9d-117">A **Fizetési felszólítás** mezőben válassza ki a kívánt beállítást.</span><span class="sxs-lookup"><span data-stu-id="25e9d-117">In the **Collection letter** field, select an option.</span></span>
4. <span data-ttu-id="25e9d-118">A **Fizetési felszólítás dátuma** mezőbe írja be a fizetési felszólítás dátumát.</span><span class="sxs-lookup"><span data-stu-id="25e9d-118">In the **Collection letter date** field, enter the date of the collection letter.</span></span>
5. <span data-ttu-id="25e9d-119">Válasszon ki egy feladási profilt, ha módosította a **Feladási profil használata képernyő** lehetőséget **Kiválasztott** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="25e9d-120">Kétféle feladási profil létezik:</span><span class="sxs-lookup"><span data-stu-id="25e9d-120">There are two posting profile options:</span></span>   

   - <span data-ttu-id="25e9d-121">**Számla** – az egyes kamatlevelek vevőkódjához rendelt feladási profil használata.</span><span class="sxs-lookup"><span data-stu-id="25e9d-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="25e9d-122">**Kiválasztott** – a Feladási mezőben megadott **Feladási profil** használata.</span><span class="sxs-lookup"><span data-stu-id="25e9d-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  

6. <span data-ttu-id="25e9d-123">Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="25e9d-123">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="25e9d-124">Válassza ki a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="25e9d-124">Select **Filter**.</span></span>
8. <span data-ttu-id="25e9d-125">A **Feltétel** mezőben adjon meg Vevőazonosítót.</span><span class="sxs-lookup"><span data-stu-id="25e9d-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="25e9d-126">Adja meg például az „US-001”értéket.</span><span class="sxs-lookup"><span data-stu-id="25e9d-126">For example, enter 'US-001'.</span></span>
9. <span data-ttu-id="25e9d-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25e9d-127">Select **OK**.</span></span>
10. <span data-ttu-id="25e9d-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25e9d-128">Select **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="25e9d-129">Fizetési felszólítások nyomtatása</span><span class="sxs-lookup"><span data-stu-id="25e9d-129">Print collection letters</span></span>
1. <span data-ttu-id="25e9d-130">Lépjen a **navigációs ablaktábla > Modulok > Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása** részre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-130">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="25e9d-131">Az **Állapot** mezőben válassza ki a **Létrehozva** értéket.</span><span class="sxs-lookup"><span data-stu-id="25e9d-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="25e9d-132">A **Nyomtatott** mezőben válassza a **Nem nyomtatva** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25e9d-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="25e9d-133">Válassza a **Nyomtatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25e9d-133">Select **Print**.</span></span>
5. <span data-ttu-id="25e9d-134">Válassza a **Fizetésre felszólítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25e9d-134">Select **Collection letter note**.</span></span>
6. <span data-ttu-id="25e9d-135">A **Paraméterek** szakaszban adja meg a feladások fordulónapjának dátumát.</span><span class="sxs-lookup"><span data-stu-id="25e9d-135">In the **Parameters** section, enter the cutoff date for postings.</span></span>
7. <span data-ttu-id="25e9d-136">Bontsa **Belefoglalandó rekordok** szakaszt, és adja meg a fizetési felszólítási részleteit.</span><span class="sxs-lookup"><span data-stu-id="25e9d-136">Expand the **Records to include** section and enter the details of the Collection letter note.</span></span>
8. <span data-ttu-id="25e9d-137">Kattintson az **OK** gombra a fizetési felszólítás nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="25e9d-137">Select **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="25e9d-138">Adja fel a fizetési felszólítást.</span><span class="sxs-lookup"><span data-stu-id="25e9d-138">Post the collection letter.</span></span>

    1. <span data-ttu-id="25e9d-139">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="25e9d-139">Select **Post**.</span></span>
    1. <span data-ttu-id="25e9d-140">Adja meg a fizetési felszólítás feladási dátumát.</span><span class="sxs-lookup"><span data-stu-id="25e9d-140">Enter the posting date for the collection letter.</span></span>
    1. <span data-ttu-id="25e9d-141">Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="25e9d-141">Expand the **Records to include** section.</span></span>
    1. <span data-ttu-id="25e9d-142">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25e9d-142">Select **OK**.</span></span>
    1. <span data-ttu-id="25e9d-143">Az **Állapot** mezőben válassza ki a **Feladott** értéket.</span><span class="sxs-lookup"><span data-stu-id="25e9d-143">In the **Status** field, select **Posted**.</span></span>
    1. <span data-ttu-id="25e9d-144">Válasszon ki egy lehetőséget a **Nyomtatott** mezőben.</span><span class="sxs-lookup"><span data-stu-id="25e9d-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="25e9d-145">A fizetési felszólítások ellenőrzése a vevő szintjén</span><span class="sxs-lookup"><span data-stu-id="25e9d-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="25e9d-146">Fizetési felszólításokat a vevők szintjén is beállíthatja, hogy a fizetésifelszólítás-kód az egyes tranzakciókhoz nyomon legyen követve de a fizetési felszólítás feldolgozása a vevőhöz tárolt egyetlen fizetésifelszólítás-szinten alapuljon.</span><span class="sxs-lookup"><span data-stu-id="25e9d-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="25e9d-147">Az egyetlen fizetési felszólítás aí vevőhöz tartozó összes lejárt tranzakció fogja tartalmazni.</span><span class="sxs-lookup"><span data-stu-id="25e9d-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="25e9d-148">Mivel a türelmi napok mostantól nyomon követhetők a vevői szinten, a következő fizetési felszólítás nem lesz elküldve mindaddig, amíg a sorozatban következő fizetési felszólításhoz kapcsolódó türelmi időszak le nem jár, annak ellenére, a tranzakciók késedelmessé váltak az utolsó fizetési felszólítás elküldése után.</span><span class="sxs-lookup"><span data-stu-id="25e9d-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="25e9d-149">Ez a lehetőség csökkenti a vevőnként elküldött a fizetési felszólítások számát.</span><span class="sxs-lookup"><span data-stu-id="25e9d-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="25e9d-150">A fizetési felszólítások ellenőrzésének beállítása a vevő szintjén</span><span class="sxs-lookup"><span data-stu-id="25e9d-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="25e9d-151">Ugorjon a **navigációs ablaktábla > Modulok > Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei** helyre, és kattintson a **Beszedések** lapfülre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-151">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and select the **Collections** tab.</span></span> 
2.  <span data-ttu-id="25e9d-152">A **Fizetési felszólítás létrehozása a következő szerint:** értékét módosítsa **Vevő** értékre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="25e9d-153">Lépjen a **navigációs ablaktábla > Modulok > Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása** részre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-153">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="25e9d-154">Csak egy fizetési felszólítás jön létre a vevőhöz az összes lejárt tranzakció tekintetében.</span><span class="sxs-lookup"><span data-stu-id="25e9d-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="25e9d-155">Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során</span><span class="sxs-lookup"><span data-stu-id="25e9d-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="25e9d-156">Ha kifizetéseket és jóváírásokat is szerepeltetni kíván a tranzakciókban, amelyek szerepelni fognak a fizetési felszólításokban, előfordulhat, hogy vannak olyan kifizetések vagy jóváírások, amely elindítják a fizetési felszólítást.</span><span class="sxs-lookup"><span data-stu-id="25e9d-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="25e9d-157">Megadhatja, hogy kifizetések és jóváírások, hogyan vezéreljék a fizetésifelszólítás-kódokat a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** paraméter értékének módosításával.</span><span class="sxs-lookup"><span data-stu-id="25e9d-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="25e9d-158">Fizetések és jóváírások figyelmen kívül hagyásához a fizetési felszólítás kódjának kiszámítása során tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="25e9d-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>

1. <span data-ttu-id="25e9d-159">Ugorjon a **navigációs ablaktábla > Modulok > Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei** helyre, és kattintson a **Beszedések** lapfülre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-159">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="25e9d-160">A **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** paramétert állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="25e9d-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>

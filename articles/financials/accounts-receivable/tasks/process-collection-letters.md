--- 
title: "Fizetési felszólítások feldolgozása"
description: "Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.translationtype: HT
ms.sourcegitcommit: 075d0f5dc0c9dc4e46dc92a2da75da9f7a207472
ms.openlocfilehash: 33d9fd62a780ab109474eefa9e322a9c529f9e72
ms.contentlocale: hu-hu
ms.lasthandoff: 12/06/2018

---
# <a name="process-collection-letters"></a><span data-ttu-id="55d72-103">Fizetési felszólítások feldolgozása</span><span class="sxs-lookup"><span data-stu-id="55d72-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

<span data-ttu-id="55d72-104">Ez az eljárás a fizetési felszólítások létrehozását, nyomtatását és feladását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="55d72-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="55d72-105">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="55d72-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="55d72-106">Állítson be egy fizetésifelszólítás-sorozatot a feladási profilon.</span><span class="sxs-lookup"><span data-stu-id="55d72-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="55d72-107">Ugorjon a **Követelések és beszedések > Beállítás > Vevői feladási profilok pontra**.</span><span class="sxs-lookup"><span data-stu-id="55d72-107">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="55d72-108">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="55d72-108">Click **Edit**.</span></span>
3. <span data-ttu-id="55d72-109">Válasszon egy fizetésifelszólítás-sorozatot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="55d72-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="55d72-110">Ha nem szeretne fizetési felszólításokat létrehozni a tranzakciókhoz ezzel a feladói profillal, hagyja a mezőt üresen.</span><span class="sxs-lookup"><span data-stu-id="55d72-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="55d72-111">A Tábla korlátozási lapjának kinyitásával módosíthatja a fizetési felszólítások feldolgozásának módját.</span><span class="sxs-lookup"><span data-stu-id="55d72-111">Expand the table restriction tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="55d72-112">Ha ez a mező **Igen** értékre van állítva, fizetési felszólítások kerülnek létrehozásra a feladási profilhoz.</span><span class="sxs-lookup"><span data-stu-id="55d72-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="55d72-113">Fizetési felszólítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="55d72-113">Create collection letters</span></span>
1. <span data-ttu-id="55d72-114">Ugorjon a **Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások létrehozása** pontra.</span><span class="sxs-lookup"><span data-stu-id="55d72-114">Go to **Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="55d72-115">Válassza ki azokat a tranzakciótípusokat, amelyekre fizetési felszólítást szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="55d72-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="55d72-116">Ez ilyen típusokhoz tartozó nyitott tranzakciók szerepelni fognak a számításban.</span><span class="sxs-lookup"><span data-stu-id="55d72-116">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="55d72-117">A **Fizetési felszólítás** mezőben válassza ki a kívánt beállítást.</span><span class="sxs-lookup"><span data-stu-id="55d72-117">In the **Collection letter** field, select an option.</span></span>
3. <span data-ttu-id="55d72-118">Adja meg a fizetési felszólítás dátumát.</span><span class="sxs-lookup"><span data-stu-id="55d72-118">Enter the date of the collection letter.</span></span>
4. <span data-ttu-id="55d72-119">Válasszon ki egy feladási profilt, ha módosította a **Feladási profil használata képernyő** lehetőséget **Kiválasztott** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="55d72-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="55d72-120">Kétféle feladási profil létezik:</span><span class="sxs-lookup"><span data-stu-id="55d72-120">There are two posting profile options:</span></span>   
   - <span data-ttu-id="55d72-121">**Számla** – az egyes kamatlevelek vevőkódjához rendelt feladási profil használata.</span><span class="sxs-lookup"><span data-stu-id="55d72-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="55d72-122">**Kiválasztott** – a Feladási mezőben megadott **Feladási profil** használata.</span><span class="sxs-lookup"><span data-stu-id="55d72-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  
5. <span data-ttu-id="55d72-123">Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="55d72-123">Expand the **Records to include** section.</span></span>
6. <span data-ttu-id="55d72-124">Kattintson a **Szűrő** parancsra.</span><span class="sxs-lookup"><span data-stu-id="55d72-124">Click **Filter**.</span></span>
7. <span data-ttu-id="55d72-125">A **Feltétel** mezőben adjon meg Vevőazonosítót.</span><span class="sxs-lookup"><span data-stu-id="55d72-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="55d72-126">Adja meg például az „US-001”értéket.</span><span class="sxs-lookup"><span data-stu-id="55d72-126">For example, enter 'US-001'.</span></span>
8. <span data-ttu-id="55d72-127">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="55d72-127">Click **OK**.</span></span>
9. <span data-ttu-id="55d72-128">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="55d72-128">Click **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="55d72-129">Fizetési felszólítások nyomtatása</span><span class="sxs-lookup"><span data-stu-id="55d72-129">Print collection letters</span></span>
1. <span data-ttu-id="55d72-130">Ugorjon a **Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása** pontra.</span><span class="sxs-lookup"><span data-stu-id="55d72-130">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="55d72-131">Az **Állapot** mezőben válassza ki a **Létrehozva** értéket.</span><span class="sxs-lookup"><span data-stu-id="55d72-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="55d72-132">A **Nyomtatott** mezőben válassza a **Nem nyomtatva** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="55d72-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="55d72-133">Kattintson a **Nyomtatás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="55d72-133">Click **Print**.</span></span>
5. <span data-ttu-id="55d72-134">Kattintson a **Fizetésre felszólítás** gombra.</span><span class="sxs-lookup"><span data-stu-id="55d72-134">Click **Collection letter note**.</span></span>
6. <span data-ttu-id="55d72-135">Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="55d72-135">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="55d72-136">Adja meg a feladások fordulónapjának dátumát.</span><span class="sxs-lookup"><span data-stu-id="55d72-136">Enter the cutoff date for postings.</span></span>
8. <span data-ttu-id="55d72-137">Kattintson az **OK** gombra a fizetési felszólítás nyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="55d72-137">Click **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="55d72-138">Adja fel a fizetési felszólítást.</span><span class="sxs-lookup"><span data-stu-id="55d72-138">Post the collection letter.</span></span>
   1. <span data-ttu-id="55d72-139">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="55d72-139">Click **Post**.</span></span>
   2. <span data-ttu-id="55d72-140">Adja meg a fizetési felszólítás feladási dátumát.</span><span class="sxs-lookup"><span data-stu-id="55d72-140">Enter the posting date for the collection letter.</span></span>
   3. <span data-ttu-id="55d72-141">Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="55d72-141">Expand the **Records to include** section.</span></span>
   4. <span data-ttu-id="55d72-142">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="55d72-142">Click **OK**.</span></span>
   5. <span data-ttu-id="55d72-143">Az **Állapot** mezőben válassza ki a **Feladott** értéket.</span><span class="sxs-lookup"><span data-stu-id="55d72-143">In the **Status** field, select **Posted**.</span></span>
   6. <span data-ttu-id="55d72-144">Válasszon ki egy lehetőséget a **Nyomtatott** mezőben.</span><span class="sxs-lookup"><span data-stu-id="55d72-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="55d72-145">A fizetési felszólítások ellenőrzése a vevő szintjén</span><span class="sxs-lookup"><span data-stu-id="55d72-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="55d72-146">Fizetési felszólításokat a vevők szintjén is beállíthatja, hogy a fizetésifelszólítás-kód az egyes tranzakciókhoz nyomon legyen követve de a fizetési felszólítás feldolgozása a vevőhöz tárolt egyetlen fizetésifelszólítás-szinten alapuljon.</span><span class="sxs-lookup"><span data-stu-id="55d72-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="55d72-147">Az egyetlen fizetési felszólítás aí vevőhöz tartozó összes lejárt tranzakció fogja tartalmazni.</span><span class="sxs-lookup"><span data-stu-id="55d72-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="55d72-148">Mivel a türelmi napok mostantól nyomon követhetők a vevői szinten, a következő fizetési felszólítás nem lesz elküldve mindaddig, amíg a sorozatban következő fizetési felszólításhoz kapcsolódó türelmi időszak le nem jár, annak ellenére, a tranzakciók késedelmessé váltak az utolsó fizetési felszólítás elküldése után.</span><span class="sxs-lookup"><span data-stu-id="55d72-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="55d72-149">Ez a lehetőség csökkenti a vevőnként elküldött a fizetési felszólítások számát.</span><span class="sxs-lookup"><span data-stu-id="55d72-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="55d72-150">A fizetési felszólítások ellenőrzésének beállítása a vevő szintjén</span><span class="sxs-lookup"><span data-stu-id="55d72-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="55d72-151">Ugorjon a **Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei**, és kattintson a **Beszedések** lapra.</span><span class="sxs-lookup"><span data-stu-id="55d72-151">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2.  <span data-ttu-id="55d72-152">A **Fizetési felszólítás létrehozása a következő szerint:** értékét módosítsa **Vevő** értékre.</span><span class="sxs-lookup"><span data-stu-id="55d72-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="55d72-153">Ugorjon a **Követelések és beszedések > Fizetési felszólítás > Fizetési felszólítások áttekintése és feldolgozása** pontra.</span><span class="sxs-lookup"><span data-stu-id="55d72-153">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="55d72-154">Csak egy fizetési felszólítás jön létre a vevőhöz az összes lejárt tranzakció tekintetében.</span><span class="sxs-lookup"><span data-stu-id="55d72-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="55d72-155">Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során</span><span class="sxs-lookup"><span data-stu-id="55d72-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="55d72-156">Ha kifizetéseket és jóváírásokat is szerepeltetni kíván a tranzakciókban, amelyek szerepelni fognak a fizetési felszólításokban, előfordulhat, hogy vannak olyan kifizetések vagy jóváírások, amely elindítják a fizetési felszólítást.</span><span class="sxs-lookup"><span data-stu-id="55d72-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="55d72-157">Megadhatja, hogy kifizetések és jóváírások, hogyan vezéreljék a fizetésifelszólítás-kódokat a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** paraméter értékének módosításával.</span><span class="sxs-lookup"><span data-stu-id="55d72-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="55d72-158">Fizetések és jóváírások figyelmen kívül hagyásához a fizetési felszólítás kódjának kiszámítása során tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="55d72-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>
1. <span data-ttu-id="55d72-159">Ugorjon a **Követelések és beszedések > Beállítás > Kinnlevőségek paraméterei**, és kattintson a **Beszedések** lapra.</span><span class="sxs-lookup"><span data-stu-id="55d72-159">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="55d72-160">A **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** paramétert állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="55d72-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>


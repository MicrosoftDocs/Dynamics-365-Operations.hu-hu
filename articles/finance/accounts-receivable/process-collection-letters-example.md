---
title: Fizetési felszólítások feldolgozása (példa)
description: Ez a témakör egy példán keresztül bemutatja a fizetési felszólítások létrehozásának, nyomtatásának és feladásának folyamatát.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021416"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="4cacf-103">Fizetési felszólítások feldolgozása (példa)</span><span class="sxs-lookup"><span data-stu-id="4cacf-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4cacf-104">Ez a témakör egy példán keresztül bemutatja a fizetési felszólítások létrehozásának, nyomtatásának és feladásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="4cacf-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="4cacf-105">A példa a Követelések és beszedések rész **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőségén alapul.</span><span class="sxs-lookup"><span data-stu-id="4cacf-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="4cacf-106">Az USMF bemutatóvállalat és egy új vevő, az US-045 adatait használja.</span><span class="sxs-lookup"><span data-stu-id="4cacf-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="4cacf-107">A kezdéshez lépjen a **Kinnlevőségek \> Vevők \> Összes vevő** lehetőségre, válassza az **Új** lehetőséget, majd adja meg az US-045 vevő létrehozásához szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="4cacf-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="4cacf-108">Amikor befejezte, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4cacf-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="4cacf-109">Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetésifelszólítás-sorozat beállítása** lehetőségre, és állítsa be a fizetésifelszólítás-sorozatot a vevői feladási profilhoz rendelt alábbi táblának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="4cacf-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="4cacf-110">Fizetési felszólítás kódja</span><span class="sxs-lookup"><span data-stu-id="4cacf-110">Collection   letter code</span></span>      |     <span data-ttu-id="4cacf-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="4cacf-111">Description</span></span>                           |     <span data-ttu-id="4cacf-112">Pénznem</span><span class="sxs-lookup"><span data-stu-id="4cacf-112">Currency</span></span>      |     <span data-ttu-id="4cacf-113">Fő számla</span><span class="sxs-lookup"><span data-stu-id="4cacf-113">Main   account</span></span>        |     <span data-ttu-id="4cacf-114">Illeték pénznemben</span><span class="sxs-lookup"><span data-stu-id="4cacf-114">Fee   in currency</span></span>     |     <span data-ttu-id="4cacf-115">Minimális késedelmes</span><span class="sxs-lookup"><span data-stu-id="4cacf-115">Minimum   over</span></span>        |     <span data-ttu-id="4cacf-116">Nap zárolás</span><span class="sxs-lookup"><span data-stu-id="4cacf-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="4cacf-117">1. fizetési felszólítás</span><span class="sxs-lookup"><span data-stu-id="4cacf-117">Collection   letter 1</span></span>         |     <span data-ttu-id="4cacf-118">Második értesítés díjjal</span><span class="sxs-lookup"><span data-stu-id="4cacf-118">Second   notification with fee</span></span>        |     <span data-ttu-id="4cacf-119">USD</span><span class="sxs-lookup"><span data-stu-id="4cacf-119">USD</span></span>           |                           |     <span data-ttu-id="4cacf-120">0,00</span><span class="sxs-lookup"><span data-stu-id="4cacf-120">0.00</span></span>                  |     <span data-ttu-id="4cacf-121">0,00</span><span class="sxs-lookup"><span data-stu-id="4cacf-121">0.00</span></span>                  |     <span data-ttu-id="4cacf-122">2</span><span class="sxs-lookup"><span data-stu-id="4cacf-122">2</span></span>                 |
|     <span data-ttu-id="4cacf-123">2. fizetési felszólítás</span><span class="sxs-lookup"><span data-stu-id="4cacf-123">Collection   letter 2</span></span>         |     <span data-ttu-id="4cacf-124">Második értesítés díjjal</span><span class="sxs-lookup"><span data-stu-id="4cacf-124">Second   notification with fee</span></span>        |     <span data-ttu-id="4cacf-125">USC</span><span class="sxs-lookup"><span data-stu-id="4cacf-125">USC</span></span>           |     <span data-ttu-id="4cacf-126">403150</span><span class="sxs-lookup"><span data-stu-id="4cacf-126">403150</span></span>                |     <span data-ttu-id="4cacf-127">20.00</span><span class="sxs-lookup"><span data-stu-id="4cacf-127">20.00</span></span>                 |     <span data-ttu-id="4cacf-128">10,00</span><span class="sxs-lookup"><span data-stu-id="4cacf-128">10.00</span></span>                 |     <span data-ttu-id="4cacf-129">3</span><span class="sxs-lookup"><span data-stu-id="4cacf-129">3</span></span>                 |
|     <span data-ttu-id="4cacf-130">Beszedés</span><span class="sxs-lookup"><span data-stu-id="4cacf-130">Collection</span></span>                    |     <span data-ttu-id="4cacf-131">Utolsó értesítés díjjal</span><span class="sxs-lookup"><span data-stu-id="4cacf-131">Final   notification with fee</span></span>         |     <span data-ttu-id="4cacf-132">USD</span><span class="sxs-lookup"><span data-stu-id="4cacf-132">USD</span></span>           |     <span data-ttu-id="4cacf-133">403150</span><span class="sxs-lookup"><span data-stu-id="4cacf-133">403150</span></span>                |     <span data-ttu-id="4cacf-134">50.00</span><span class="sxs-lookup"><span data-stu-id="4cacf-134">50.00</span></span>                 |     <span data-ttu-id="4cacf-135">100.00</span><span class="sxs-lookup"><span data-stu-id="4cacf-135">100.00</span></span>                |     <span data-ttu-id="4cacf-136">15</span><span class="sxs-lookup"><span data-stu-id="4cacf-136">15</span></span>                |

<span data-ttu-id="4cacf-137">A következő ábra a tábla azon adatait mutatja be, amelyek a **Fizetési felszólítás** oldalon jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="4cacf-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="4cacf-138">[![Fizetésifelszólítás-sorozat beállítása](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="4cacf-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="4cacf-139">Most be kell állítania a példához szükséges két paramétert.</span><span class="sxs-lookup"><span data-stu-id="4cacf-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="4cacf-140">Lépjen a **Követelések és beszedések \> Beállítás \> Kinnlevőségek paraméterei** lehetőségre, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-141">A **Követelések és beszedések** lapon állítsa a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="4cacf-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="4cacf-142">Győződjön meg arról, hogy a **Fizetési felszólítás létrehozása a következő szerint:** mező értéke a **Vevő** legyen.</span><span class="sxs-lookup"><span data-stu-id="4cacf-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="4cacf-143">[![Kinnlevőségek paramétereinek beállítása a beszedésekhez](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="4cacf-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="4cacf-144">Lépjen a **Kinnlevőségek \> Számlák \> Kizárólag szabadszöveges számlák** lehetőségre, válassza az **Új** lehetőséget, majd kövesse a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-145">A **Vevői számla** mezőben válassza a következőt: **US-045**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="4cacf-146">A **Számla dátuma** mezőbe írja be a következő értéket: **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="4cacf-147">A **Határidő** mezőbe írja be a következő értéket: **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="4cacf-148">A **Számlasorok** gyorslapon a **Fő számla** mezőbe írja be a következőt: **401100**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="4cacf-149">Írjon be **500.00** értéket az **Egységár** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4cacf-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="4cacf-150">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="4cacf-150">Select **Post**.</span></span>

    <span data-ttu-id="4cacf-151">Most két jóváírást kell megadnia a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="4cacf-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="4cacf-152">Válassza az **Új** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-153">A **Vevői számla** mezőben válassza a következőt: **US-045**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="4cacf-154">A **Számla dátuma** mezőbe írja be a következő értéket: **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="4cacf-155">A **Határidő** mezőbe írja be a következő értéket: **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="4cacf-156">A **Számlasorok** gyorslapon a **Fő számla** mezőbe írja be a következőt: **401100**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="4cacf-157">Az **Egységár** mezőbe írja be a következő értéket: **-100,00**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="4cacf-158">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="4cacf-158">Select **Post**.</span></span>

5. <span data-ttu-id="4cacf-159">Ismételje meg a 4. lépést, de írja a **-200,00** értéket az **Egységár** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4cacf-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="4cacf-160">Menjen a **Kinnlevőségek \> Vevők \> Összes vevő** lehetőségre, és válassza ki az **US-045** vevőt.</span><span class="sxs-lookup"><span data-stu-id="4cacf-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="4cacf-161">Ezután a műveleti ablaktáblán válassza a **Tranzakciók \> Tranzakciók** lehetőséget a korábban feladott vevői tranzakciók ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="4cacf-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="4cacf-162">[![Feladott vevői tranzakciók ellenőrzése](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="4cacf-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="4cacf-163">Most fizetési felszólításokat kell létrehoznia az US-045 vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="4cacf-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="4cacf-164">Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások létrehozása** részre, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-165">A **Számla** és a **Jóváírás** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="4cacf-166">Alapértelmezés szerint a **Fizetési felszólítás** mező beállítása **Felszólítás vevőnként**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="4cacf-167">A **Fizetési felszólítás dátuma** mezőbe írja be a következő értéket: **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="4cacf-168">A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrés** lehetőséget, majd a **Vevői számla** mezőben adja hozzá az **US-045** vevőt.</span><span class="sxs-lookup"><span data-stu-id="4cacf-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="4cacf-169">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cacf-169">Select **OK**.</span></span>
    5. <span data-ttu-id="4cacf-170">Kattintson az **OK** gombra a fizetési felszólítások létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4cacf-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="4cacf-171">Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások áttekintése és feldolgozása** részre, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-172">Figyelje meg, hogy a fizetési felszólítás kódja a fejlécben és a tranzakciósorban is **1. fizetési felszólítás**, mivel ez a fizetési felszólítás a sorozat első fizetési felszólítása.</span><span class="sxs-lookup"><span data-stu-id="4cacf-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="4cacf-173">(A tranzakciósorok megtekintéséhez lehet, hogy ki kell választania a **Tranzakciók** gyorslapot.)</span><span class="sxs-lookup"><span data-stu-id="4cacf-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="4cacf-174">[![Annak ellenőrzése, hogy ugyanaz a fizetésifelszólítás-kód jelenik-e meg a fejlécben és a sorokban](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="4cacf-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="4cacf-175">A műveleti ablaktáblán válassza ki a **Feladás** elemet.</span><span class="sxs-lookup"><span data-stu-id="4cacf-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="4cacf-176">A **Feladás dátuma** mezőbe írja be a következő értéket: **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="4cacf-177">Most ismét létre kell hoznia a fizetési felszólításokat az US-045 vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="4cacf-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="4cacf-178">Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások létrehozása** részre, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-179">A **Számla** és a **Jóváírás** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="4cacf-180">Alapértelmezés szerint a **Fizetési felszólítás** mező beállítása **Felszólítás vevőnként**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="4cacf-181">A **Fizetési felszólítás dátuma** mezőbe írja be a következő értéket: **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="4cacf-182">A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrés** lehetőséget, majd a **Vevői számla** mezőben adja hozzá az **US-045** vevőt.</span><span class="sxs-lookup"><span data-stu-id="4cacf-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="4cacf-183">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cacf-183">Select **OK**.</span></span>
    5. <span data-ttu-id="4cacf-184">Kattintson az **OK** gombra a fizetési felszólítások létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4cacf-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="4cacf-185">Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások áttekintése és feldolgozása** részre, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-186">Figyelje meg, hogy a fizetési felszólítás kódja a fejlécen: **1. fizetési felszólítás**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="4cacf-187">A tranzakciósorok kódja azonban **2. fizetési felszólítás**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="4cacf-188">[![Annak ellenőrzése, hogy különböző fizetésifelszólítás-kódok jelennek-e meg a fejlécben és a sorokban](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="4cacf-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="4cacf-189">A kódok eltérőek, mivel a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőség **Igen** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="4cacf-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="4cacf-190">Ne adja fel ezt a fizetési felszólítást.</span><span class="sxs-lookup"><span data-stu-id="4cacf-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="4cacf-191">Lépjen a **Követelések és beszedések \> Beállítás \> Kinnlevőségek paraméterei** pontra, majd a **Beszedések** lapon állítsa a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőséget **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="4cacf-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="4cacf-192">[![Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során beállítása Nem értékre](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="4cacf-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="4cacf-193">Most ismét létre kell hoznia a fizetési felszólításokat az US-045 vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="4cacf-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="4cacf-194">Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások létrehozása** részre, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="4cacf-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="4cacf-195">A **Számla** és a **Jóváírás** beállítása legyen **Igen**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="4cacf-196">Alapértelmezés szerint a **Fizetési felszólítás** mező beállítása **Felszólítás vevőnként**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="4cacf-197">A **Fizetési felszólítás dátuma** mezőbe írja be a következő értéket: **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="4cacf-198">A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrés** lehetőséget, majd a **Vevői számla** mezőben adja hozzá az **US-045** vevőt.</span><span class="sxs-lookup"><span data-stu-id="4cacf-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="4cacf-199">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4cacf-199">Select **OK**.</span></span>
    5. <span data-ttu-id="4cacf-200">Kattintson az **OK** gombra a fizetési felszólítások létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="4cacf-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="4cacf-201">Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások áttekintése és feldolgozása** pontra, és figyelje meg, hogy a fizetési felszólítás kódja a fejlécben és a tranzakciósorban is **2. fizetési felszólítás**.</span><span class="sxs-lookup"><span data-stu-id="4cacf-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="4cacf-202">[![Annak ismételt megjelenítése, hogy ugyanaz a fizetésifelszólítás-kód jelenik meg a fejlécben és a sorokban](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="4cacf-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="4cacf-203">Ugyanaz a kód jelenik meg mindkét helyen, mivel a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőség **Nem** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="4cacf-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>

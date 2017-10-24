--- 
title: "Jelentések készítése Microsoft Office formátumban beágyazott képekkel az elektronikus jelentéskészítéshez (ER) (1. rész)"
description: "A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tervezhet meg egy új Elektronikus jelentés (ER) konfigurációkat, beágyazott képeket tartalmazó MS Office (Excel vagy Word) formátumú elektronikus dokumentumok létrehozásához."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 93a40f36e38ef5ea393cf429ad9244b56504bbfc
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="make-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er--part-1"></a><span data-ttu-id="76813-103">Jelentések készítése Microsoft Office formátumban beágyazott képekkel az elektronikus jelentéskészítéshez (ER) (1. rész)</span><span class="sxs-lookup"><span data-stu-id="76813-103">Make reports in Microsoft Office formats with embedded images for electronic reporting (ER)  (Part 1)</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76813-104">A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tervezhet meg egy új Elektronikus jelentés (ER) konfigurációkat, beágyazott képeket tartalmazó MS Office (Excel vagy Word) formátumú elektronikus dokumentumok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="76813-104">The following steps explain how a user playing either ‘System administrator’ or ‘Electronic reporting developer’ role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="76813-105">Ebben a példában a Litware, Inc. mintavállalatra vonatkozóan létrehozott ER-konfigurációkat használjuk.</span><span class="sxs-lookup"><span data-stu-id="76813-105">In this example, you will use created ER configurations for sample company, ‘Litware, Inc.’.</span></span>  <span data-ttu-id="76813-106">A lépések végrehajtásához először végre kell hajtani az „ER – Jelentések létrehozása Microsoft Office-formátumokban, beágyazott képekkel (2. rész: Konfigurációk áttekintése)” feladat-útmutató lépéseit.</span><span class="sxs-lookup"><span data-stu-id="76813-106">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)” task guide.</span></span> <span data-ttu-id="76813-107">Ezeket a lépéseket a USMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="76813-107">These steps can be performed in ‘USMF’ company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="76813-108">Futtassa a formátumot a kiindulási modell-hozzárendeléssel</span><span class="sxs-lookup"><span data-stu-id="76813-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="76813-109">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="76813-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="76813-110">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="76813-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="76813-111">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="76813-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="76813-112">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-112">Click Check.</span></span>
5. <span data-ttu-id="76813-113">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-113">Click Print test.</span></span>
    * <span data-ttu-id="76813-114">Futtassa a formátumot tesztelési céllal.</span><span class="sxs-lookup"><span data-stu-id="76813-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="76813-115">Válassza az Igen lehetőséget az Átruházható csekkformátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="76813-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="76813-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-116">Click OK.</span></span>
    * <span data-ttu-id="76813-117">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="76813-117">Review the created output.</span></span> <span data-ttu-id="76813-118">Vegye figyelembe, hogy a vállalati embléma megjelenik a jelentésben, a jogosult személy aláírásával együtt.</span><span class="sxs-lookup"><span data-stu-id="76813-118">Note that the company logo is presented in the report as well as the authorized person’s signature.</span></span> <span data-ttu-id="76813-119">Az aláírás képe a kiválasztott bankszámlával társított csekkelrendezése-rekord „Konténer” adattípusú mezőjéből származik.</span><span class="sxs-lookup"><span data-stu-id="76813-119">The signature image is taken from the field of the ‘Container’ data type of the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="76813-120">Bontsa ki a Példányok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="76813-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="76813-121">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-121">Click Edit.</span></span>
10. <span data-ttu-id="76813-122">A Vízjel mezőjébe írja be a következőt: „Vízjel nyomtatása érvénytelenként”.</span><span class="sxs-lookup"><span data-stu-id="76813-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="76813-123">Módosítsa a vízjel elrendezése beállítást, hogy egy Excel-alakzat elemen dokumentum létrehozásakor megjelenjen a vízjel szövege.</span><span class="sxs-lookup"><span data-stu-id="76813-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="76813-124">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-124">Click Print test.</span></span>
12. <span data-ttu-id="76813-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-125">Click OK.</span></span>
    * <span data-ttu-id="76813-126">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="76813-126">Review the created output.</span></span> <span data-ttu-id="76813-127">Vegye figyelembe, hogy a vízjel a beállítással összhangban jelenik meg a létrehozott jelentésen.</span><span class="sxs-lookup"><span data-stu-id="76813-127">Note that the watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="76813-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-128">Close the page.</span></span>
14. <span data-ttu-id="76813-129">A Művelet panelen kattintson a Kifizetések kezelése elemre.</span><span class="sxs-lookup"><span data-stu-id="76813-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="76813-130">Kattintson a Csekkek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-130">Click Checks.</span></span>
16. <span data-ttu-id="76813-131">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="76813-131">Click Show filters.</span></span>
17. <span data-ttu-id="76813-132">Alkalmazza a következő szűrőket: adja meg a „381”, „385”, „389” szűrőértéket a „Csekk száma” mezőben „a következők valamelyike” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="76813-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="76813-133">A listában jelöljön ki minden sort.</span><span class="sxs-lookup"><span data-stu-id="76813-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="76813-134">Kattintson a Csekk másolatának nyomtatása elemre.</span><span class="sxs-lookup"><span data-stu-id="76813-134">Click Print check copy.</span></span>
    * <span data-ttu-id="76813-135">Futtassa a formátumot a kiválasztott csekkek újranyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="76813-135">Run the format to re-print the selected cheques.</span></span>  
    * <span data-ttu-id="76813-136">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="76813-136">Review the created output.</span></span> <span data-ttu-id="76813-137">Ne feledje, hogy a kiválasztott csekkek újra lettek nyomtatva.</span><span class="sxs-lookup"><span data-stu-id="76813-137">Note that the selected cheques have been re-printed.</span></span> <span data-ttu-id="76813-138">A vállalati embléma és a címkék nem lesznek kinyomtatva, mivel azok megjelennek az előre nyomtatott űrlapon.</span><span class="sxs-lookup"><span data-stu-id="76813-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="76813-139">Módosítsa az importált adatok modell-hozzárendelését</span><span class="sxs-lookup"><span data-stu-id="76813-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="76813-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-140">Close the page.</span></span>
2. <span data-ttu-id="76813-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-141">Close the page.</span></span>
3. <span data-ttu-id="76813-142">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="76813-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="76813-143">A fastruktúrában válassza ki ezt: „Model for cheques”.</span><span class="sxs-lookup"><span data-stu-id="76813-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="76813-144">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="76813-144">Click Designer.</span></span>
6. <span data-ttu-id="76813-145">Kattintson a Modell hozzárendelése adatforráshoz gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="76813-146">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="76813-146">Click Designer.</span></span>
    * <span data-ttu-id="76813-147">Megváltoztatjuk az adatmodell aláírás elemének kötését, hogy a kiválasztott bankszámlával társított csekkelrendezése-rekordhoz társított fájlból vegye az aláírás képét.</span><span class="sxs-lookup"><span data-stu-id="76813-147">We will change the binding of the data model’s signature item to get the signature image from the file that has been attached to the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="76813-148">Kapcsolja ki a Részletek megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="76813-148">Turn Show details off.</span></span>
9. <span data-ttu-id="76813-149">A fastruktúrában bontsa ki ezt: „layout”.</span><span class="sxs-lookup"><span data-stu-id="76813-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="76813-150">A fában bontsa ki az „layout\signature” elemet.</span><span class="sxs-lookup"><span data-stu-id="76813-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="76813-151">A fában válassza ki ezt: „layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp”.</span><span class="sxs-lookup"><span data-stu-id="76813-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="76813-152">A fában bontsa ki a „chequesaccount” elemet.</span><span class="sxs-lookup"><span data-stu-id="76813-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="76813-153">A fastruktúrában bontsa ki a „chequesaccount\<Relations” elemet.</span><span class="sxs-lookup"><span data-stu-id="76813-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="76813-154">A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout” elemet.</span><span class="sxs-lookup"><span data-stu-id="76813-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="76813-155">A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout\<Relations” elemet.</span><span class="sxs-lookup"><span data-stu-id="76813-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="76813-156">A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents” elemet.</span><span class="sxs-lookup"><span data-stu-id="76813-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="76813-157">A fában válassza ki a „chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()” elemet.</span><span class="sxs-lookup"><span data-stu-id="76813-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="76813-158">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-158">Click Bind.</span></span>
19. <span data-ttu-id="76813-159">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-159">Click Save.</span></span>
20. <span data-ttu-id="76813-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-160">Close the page.</span></span>
21. <span data-ttu-id="76813-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-161">Close the page.</span></span>
22. <span data-ttu-id="76813-162">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-162">Close the page.</span></span>
23. <span data-ttu-id="76813-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="76813-164">Futtassa a formátumot a módosított modell-hozzárendeléssel</span><span class="sxs-lookup"><span data-stu-id="76813-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="76813-165">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="76813-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="76813-166">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="76813-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="76813-167">Például szűkítsen a Bankszámla mezővel az „USMF OPER” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="76813-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="76813-168">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="76813-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="76813-169">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-169">Click Check.</span></span>
5. <span data-ttu-id="76813-170">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-170">Click Print test.</span></span>
6. <span data-ttu-id="76813-171">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-171">Click OK.</span></span>
    * <span data-ttu-id="76813-172">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="76813-172">Review the created output.</span></span> <span data-ttu-id="76813-173">Vegye figyelembe, hogy a Dokumentumkezelés mellékletéből származó kép jelenik meg a jogosult személy aláírásaként.</span><span class="sxs-lookup"><span data-stu-id="76813-173">Note that the image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="76813-174">Microsoft Word dokumentum sablonként való használata az importált formátumban</span><span class="sxs-lookup"><span data-stu-id="76813-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="76813-175">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-175">Close the page.</span></span>
2. <span data-ttu-id="76813-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-176">Close the page.</span></span>
3. <span data-ttu-id="76813-177">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="76813-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="76813-178">A fastruktúrában bontsa ki ezt: „Model for cheques”.</span><span class="sxs-lookup"><span data-stu-id="76813-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="76813-179">A fában válassza ki ezt: „Model for cheques\Cheques printing format”.</span><span class="sxs-lookup"><span data-stu-id="76813-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="76813-180">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="76813-180">Click Designer.</span></span>
7. <span data-ttu-id="76813-181">Kattintson a Mellékletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-181">Click Attachments.</span></span>
8. <span data-ttu-id="76813-182">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-182">Click Delete.</span></span>
9. <span data-ttu-id="76813-183">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-183">Click Yes.</span></span>
10. <span data-ttu-id="76813-184">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-184">Click New.</span></span>
11. <span data-ttu-id="76813-185">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="76813-185">Click File.</span></span>
    * <span data-ttu-id="76813-186">Kattintson a Tallózás gombra, és töltse le előre a „Cheque template Word.docx” fájlt.</span><span class="sxs-lookup"><span data-stu-id="76813-186">Click Browse and select the downloaded in advance ‘Cheque template Word.docx’ file.</span></span>  
12. <span data-ttu-id="76813-187">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-187">Close the page.</span></span>
13. <span data-ttu-id="76813-188">A Sablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="76813-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="76813-189">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-189">Click Save.</span></span>
15. <span data-ttu-id="76813-190">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-190">Close the page.</span></span>
16. <span data-ttu-id="76813-191">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-191">Click Edit.</span></span>
17. <span data-ttu-id="76813-192">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="76813-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="76813-193">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="76813-193">Close the page.</span></span>
19. <span data-ttu-id="76813-194">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="76813-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="76813-195">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="76813-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="76813-196">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-196">Click Check.</span></span>
22. <span data-ttu-id="76813-197">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76813-197">Click Print test.</span></span>
23. <span data-ttu-id="76813-198">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="76813-198">Click OK.</span></span>
    * <span data-ttu-id="76813-199">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="76813-199">Review the created output.</span></span> <span data-ttu-id="76813-200">Vegye figyelembe, hogy a kimenet Microsoft Word dokumentumként jött létre beágyazott képekkel, amelyek a vállalati emblémát, a jogosult személy aláírását és vízjel kiválasztott szövegét tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="76813-200">Note that the output has been generated as a MS Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  



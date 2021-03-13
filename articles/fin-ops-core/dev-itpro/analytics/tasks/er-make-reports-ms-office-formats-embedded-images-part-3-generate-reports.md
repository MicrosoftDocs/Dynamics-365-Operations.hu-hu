---
title: Jelentések készítése Office formátumokban, beágyazott képekkel
description: Ez a témakör azt mutatja be, hogyan tervezhetők elektronikus jelentési (ER) konfigurációk Excel és Word programokban beágyazott képeket tartalmazó elektronikus dokumentumok létrehozására.
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e15162251e5d6fa91c5a938fd846ef5b5c8cd7f
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093823"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="cd830-103">Jelentések készítése Office formátumokban, beágyazott képekkel</span><span class="sxs-lookup"><span data-stu-id="cd830-103">Generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cd830-104">A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tervezhet meg egy új Elektronikus jelentés (ER) konfigurációkat, beágyazott képeket tartalmazó MS Office (Excel vagy Word) formátumú elektronikus dokumentumok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="cd830-104">The following steps explain how a user playing either 'System administrator' or 'Electronic reporting developer' role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="cd830-105">Ebben a példában a Litware, Inc. mintavállalatra vonatkozóan létrehozott ER-konfigurációkat használjuk.</span><span class="sxs-lookup"><span data-stu-id="cd830-105">In this example, you will use created ER configurations for sample company, 'Litware, Inc.'.</span></span>  <span data-ttu-id="cd830-106">A lépések végrehajtásához először végre kell hajtani az „ER – Jelentések létrehozása Microsoft Office-formátumokban, beágyazott képekkel (2. rész: Konfigurációk áttekintése)” feladat-útmutató lépéseit.</span><span class="sxs-lookup"><span data-stu-id="cd830-106">To complete these steps, you must first complete the steps in the "ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)" task guide.</span></span> <span data-ttu-id="cd830-107">Ezeket a lépéseket a USMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="cd830-107">These steps can be performed in 'USMF' company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="cd830-108">Futtassa a formátumot a kiindulási modell-hozzárendeléssel</span><span class="sxs-lookup"><span data-stu-id="cd830-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="cd830-109">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="cd830-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="cd830-110">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="cd830-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="cd830-111">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="cd830-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="cd830-112">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-112">Click Check.</span></span>
5. <span data-ttu-id="cd830-113">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-113">Click Print test.</span></span>
    * <span data-ttu-id="cd830-114">Futtassa a formátumot tesztelési céllal.</span><span class="sxs-lookup"><span data-stu-id="cd830-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="cd830-115">Válassza az Igen lehetőséget az Átruházható csekkformátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd830-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="cd830-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-116">Click OK.</span></span>
    * <span data-ttu-id="cd830-117">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="cd830-117">Review the created output.</span></span> <span data-ttu-id="cd830-118">A vállalati embléma megjelenik a jelentésben, a jogosult személy aláírásával együtt.</span><span class="sxs-lookup"><span data-stu-id="cd830-118">The company logo is presented in the report as well as the authorized person's signature.</span></span> <span data-ttu-id="cd830-119">Az aláírás képe a kiválasztott bankszámlával társított csekkelrendezése-rekord „Konténer” adattípusú mezőjéből származik.</span><span class="sxs-lookup"><span data-stu-id="cd830-119">The signature image is taken from the field of the 'Container' data type of the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="cd830-120">Bontsa ki a Példányok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cd830-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="cd830-121">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-121">Click Edit.</span></span>
10. <span data-ttu-id="cd830-122">A Vízjel mezőjébe írja be a következőt: „Vízjel nyomtatása érvénytelenként”.</span><span class="sxs-lookup"><span data-stu-id="cd830-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="cd830-123">Módosítsa a vízjel elrendezése beállítást, hogy egy Excel-alakzat elemen dokumentum létrehozásakor megjelenjen a vízjel szövege.</span><span class="sxs-lookup"><span data-stu-id="cd830-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="cd830-124">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-124">Click Print test.</span></span>
12. <span data-ttu-id="cd830-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-125">Click OK.</span></span>
    * <span data-ttu-id="cd830-126">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="cd830-126">Review the created output.</span></span> <span data-ttu-id="cd830-127">A vízjel a beállítással összhangban jelenik meg a létrehozott jelentésen.</span><span class="sxs-lookup"><span data-stu-id="cd830-127">The watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="cd830-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-128">Close the page.</span></span>
14. <span data-ttu-id="cd830-129">A Művelet panelen kattintson a Kifizetések kezelése elemre.</span><span class="sxs-lookup"><span data-stu-id="cd830-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="cd830-130">Kattintson a Csekkek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-130">Click Checks.</span></span>
16. <span data-ttu-id="cd830-131">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="cd830-131">Click Show filters.</span></span>
17. <span data-ttu-id="cd830-132">Alkalmazza a következő szűrőket: adja meg a „381”, „385”, „389” szűrőértéket a „Csekk száma” mezőben „a következők valamelyike” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="cd830-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="cd830-133">A listában jelöljön ki minden sort.</span><span class="sxs-lookup"><span data-stu-id="cd830-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="cd830-134">Kattintson a Csekk másolatának nyomtatása elemre.</span><span class="sxs-lookup"><span data-stu-id="cd830-134">Click Print check copy.</span></span>
    * <span data-ttu-id="cd830-135">Futtassa a formátumot a kiválasztott csekkek újranyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="cd830-135">Run the format to reprint the selected cheques.</span></span>  
    * <span data-ttu-id="cd830-136">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="cd830-136">Review the created output.</span></span> <span data-ttu-id="cd830-137">A kiválasztott csekkek újra lettek nyomtatva.</span><span class="sxs-lookup"><span data-stu-id="cd830-137">The selected cheques have been reprinted.</span></span> <span data-ttu-id="cd830-138">A vállalati embléma és a címkék nem lesznek kinyomtatva, mivel azok megjelennek az előre nyomtatott űrlapon.</span><span class="sxs-lookup"><span data-stu-id="cd830-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="cd830-139">Módosítsa az importált adatok modell-hozzárendelését</span><span class="sxs-lookup"><span data-stu-id="cd830-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="cd830-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-140">Close the page.</span></span>
2. <span data-ttu-id="cd830-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-141">Close the page.</span></span>
3. <span data-ttu-id="cd830-142">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="cd830-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="cd830-143">A fastruktúrában válassza ki ezt: „Model for cheques”.</span><span class="sxs-lookup"><span data-stu-id="cd830-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="cd830-144">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="cd830-144">Click Designer.</span></span>
6. <span data-ttu-id="cd830-145">Kattintson a Modell hozzárendelése adatforráshoz gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="cd830-146">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="cd830-146">Click Designer.</span></span>
    * <span data-ttu-id="cd830-147">Megváltoztatjuk az adatmodell aláírás elemének kötését, hogy a kiválasztott bankszámlával társított csekkelrendezése-rekordhoz társított fájlból vegye az aláírás képét.</span><span class="sxs-lookup"><span data-stu-id="cd830-147">We will change the binding of the data model's signature item to get the signature image from the file that has been attached to the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="cd830-148">Kapcsolja ki a Részletek megjelenítését.</span><span class="sxs-lookup"><span data-stu-id="cd830-148">Turn off Show details.</span></span>
9. <span data-ttu-id="cd830-149">A fastruktúrában bontsa ki ezt: „layout”.</span><span class="sxs-lookup"><span data-stu-id="cd830-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="cd830-150">A fában bontsa ki az „layout\signature” elemet.</span><span class="sxs-lookup"><span data-stu-id="cd830-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="cd830-151">A fában válassza ki ezt: „layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp”.</span><span class="sxs-lookup"><span data-stu-id="cd830-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="cd830-152">A fában bontsa ki a „chequesaccount” elemet.</span><span class="sxs-lookup"><span data-stu-id="cd830-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="cd830-153">A fastruktúrában bontsa ki a „chequesaccount\<Relations” elemet.</span><span class="sxs-lookup"><span data-stu-id="cd830-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="cd830-154">A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout” elemet.</span><span class="sxs-lookup"><span data-stu-id="cd830-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="cd830-155">A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout\<Relations” elemet.</span><span class="sxs-lookup"><span data-stu-id="cd830-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="cd830-156">A fában bontsa ki a „chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents” elemet.</span><span class="sxs-lookup"><span data-stu-id="cd830-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="cd830-157">A fában válassza ki a „chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()” elemet.</span><span class="sxs-lookup"><span data-stu-id="cd830-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="cd830-158">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-158">Click Bind.</span></span>
19. <span data-ttu-id="cd830-159">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-159">Click Save.</span></span>
20. <span data-ttu-id="cd830-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-160">Close the page.</span></span>
21. <span data-ttu-id="cd830-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-161">Close the page.</span></span>
22. <span data-ttu-id="cd830-162">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-162">Close the page.</span></span>
23. <span data-ttu-id="cd830-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="cd830-164">Futtassa a formátumot a módosított modell-hozzárendeléssel</span><span class="sxs-lookup"><span data-stu-id="cd830-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="cd830-165">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="cd830-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="cd830-166">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="cd830-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="cd830-167">Például szűkítsen a Bankszámla mezővel az „USMF OPER” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="cd830-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="cd830-168">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="cd830-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="cd830-169">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-169">Click Check.</span></span>
5. <span data-ttu-id="cd830-170">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-170">Click Print test.</span></span>
6. <span data-ttu-id="cd830-171">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-171">Click OK.</span></span>
    * <span data-ttu-id="cd830-172">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="cd830-172">Review the created output.</span></span> <span data-ttu-id="cd830-173">A Dokumentumkezelés mellékletéből származó kép jelenik meg a jogosult személy aláírásaként.</span><span class="sxs-lookup"><span data-stu-id="cd830-173">The image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="cd830-174">Microsoft Word dokumentum sablonként való használata az importált formátumban</span><span class="sxs-lookup"><span data-stu-id="cd830-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="cd830-175">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-175">Close the page.</span></span>
2. <span data-ttu-id="cd830-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-176">Close the page.</span></span>
3. <span data-ttu-id="cd830-177">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="cd830-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="cd830-178">A fastruktúrában bontsa ki ezt: „Model for cheques”.</span><span class="sxs-lookup"><span data-stu-id="cd830-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="cd830-179">A fában válassza ki ezt: „Model for cheques\Cheques printing format”.</span><span class="sxs-lookup"><span data-stu-id="cd830-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="cd830-180">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="cd830-180">Click Designer.</span></span>
7. <span data-ttu-id="cd830-181">Kattintson a Mellékletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-181">Click Attachments.</span></span>
8. <span data-ttu-id="cd830-182">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-182">Click Delete.</span></span>
9. <span data-ttu-id="cd830-183">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-183">Click Yes.</span></span>
10. <span data-ttu-id="cd830-184">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-184">Click New.</span></span>
11. <span data-ttu-id="cd830-185">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="cd830-185">Click File.</span></span>
    * <span data-ttu-id="cd830-186">Kattintson a Tallózás gombra, és töltse le előre a „Cheque template Word.docx” fájlt.</span><span class="sxs-lookup"><span data-stu-id="cd830-186">Click Browse and select the downloaded in advance 'Cheque template Word.docx' file.</span></span>  
12. <span data-ttu-id="cd830-187">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-187">Close the page.</span></span>
13. <span data-ttu-id="cd830-188">A Sablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cd830-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="cd830-189">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-189">Click Save.</span></span>
15. <span data-ttu-id="cd830-190">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-190">Close the page.</span></span>
16. <span data-ttu-id="cd830-191">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-191">Click Edit.</span></span>
17. <span data-ttu-id="cd830-192">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd830-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="cd830-193">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="cd830-193">Close the page.</span></span>
19. <span data-ttu-id="cd830-194">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="cd830-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="cd830-195">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="cd830-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="cd830-196">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-196">Click Check.</span></span>
22. <span data-ttu-id="cd830-197">Kattintson a Tesztnyomtatás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd830-197">Click Print test.</span></span>
23. <span data-ttu-id="cd830-198">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cd830-198">Click OK.</span></span>
    * <span data-ttu-id="cd830-199">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="cd830-199">Review the created output.</span></span> <span data-ttu-id="cd830-200">A kimenet Word dokumentumként jött létre beágyazott képekkel, amelyek a vállalati emblémát, a jogosult személy aláírását és vízjel kiválasztott szövegét tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="cd830-200">The output has been generated as a Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  


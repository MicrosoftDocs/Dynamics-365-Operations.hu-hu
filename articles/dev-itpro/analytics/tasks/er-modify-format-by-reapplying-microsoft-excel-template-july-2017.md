--- 
title: "Formátum módosítása Microsoft Excel sablon újbóli alkalmazásával az elektronikus jelentéskészítésben (ER)"
description: "Az alábbi lépések végrehajtásához először hajtsa végre az „ER-konfiguráció létrehozása az OPENXML formátumban létrejövő jelentésekre vonatkozóan” eljárás lépéseit."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: b49cfe39732a450e4723419c50d8bcc3d64b7ec9
ms.openlocfilehash: 2f35727376812b0de428ce929ebe0d33bc497984
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="modify-a-format-by-reapplying-a-microsoft-excel-template-for-electronic-reporting-er"></a><span data-ttu-id="6e639-103">Formátum módosítása Microsoft Excel sablon újbóli alkalmazásával az elektronikus jelentéskészítésben (ER)</span><span class="sxs-lookup"><span data-stu-id="6e639-103">Modify a format by reapplying a Microsoft Excel template for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e639-104">Az alábbi lépések végrehajtásához először hajtsa végre az „ER-konfiguráció létrehozása az OPENXML formátumban létrejövő jelentésekre vonatkozóan” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="6e639-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="6e639-105">Ez az eljárás azt ismerteti, hogyan módosíthatja egy elektronikus jelentési (ER) formátum konfigurációját egy módosított Microsoft Excel-sablon ismételt alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="6e639-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="6e639-106">Ebben az eljárásban egy módosított Excel-sablont importálunk az ER-formátum konfigurációkba, amelyeket a Litware, Inc. mintavállalathoz hoztak létre, és ezután elvégezzük az elektronikus dokumentumok létrehozását.</span><span class="sxs-lookup"><span data-stu-id="6e639-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="6e639-107">Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="6e639-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="6e639-108">A lépések a GBSI-adathalmazzal hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="6e639-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="6e639-109">A kezdés előtt töltse le és mentse a SampleVendPaymWsReport2.xlsx fájlt, amely a Elektronikus jelentéskészítési formátum módosítása egy Microsoft Excel-sablon ismételt alkalmazásával súgótémakörben szerepel (modify-electronic-reporting-format-reapply-excel-template/).</span><span class="sxs-lookup"><span data-stu-id="6e639-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="6e639-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="6e639-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="6e639-111">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="6e639-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="6e639-112">Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6e639-112">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="6e639-113">Az ER-formátum kiválasztása</span><span class="sxs-lookup"><span data-stu-id="6e639-113">Select the ER format</span></span>
1. <span data-ttu-id="6e639-114">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e639-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="6e639-115">A fában bontsa ki a „Payment model” elemet.</span><span class="sxs-lookup"><span data-stu-id="6e639-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="6e639-116">A fastruktúrában válassza ki a „Fizetési modell\Minta munkalap jelentés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6e639-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="6e639-117">Kattintson a Mellékletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e639-117">Click Attachments.</span></span>
    * <span data-ttu-id="6e639-118">Vegye figyelembe, hogy jelenleg az SampleVendPaymWsReport.xlsx Excel-fájl van használatban sablonként a fizetési napló feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="6e639-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="6e639-119">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="6e639-119">Click Open.</span></span>
    * <span data-ttu-id="6e639-120">Kattintson a Megnyitás elemre az Excel-sablon elrendezésének megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="6e639-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="6e639-121">Végezze el a sablon felülvizsgálatát.</span><span class="sxs-lookup"><span data-stu-id="6e639-121">Review the template.</span></span> <span data-ttu-id="6e639-122">Megjegyzés: jelenleg a következő adatokat tartalmazza minden kifizetési sorhoz: szállító számlaszáma, szállító neve, bank, bank regisztrációs azonosítója, számlaszám, tartozik, követel és pénznem.</span><span class="sxs-lookup"><span data-stu-id="6e639-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="6e639-123">Ebben a példában ki szeretnénk bővíteni a listát a fizetési dátum részletes adatainak hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="6e639-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="6e639-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6e639-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="6e639-125">Új Excel-sablon újbóli alkalmazása az ER-formátumra</span><span class="sxs-lookup"><span data-stu-id="6e639-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="6e639-126">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="6e639-126">Click Designer.</span></span>
    * <span data-ttu-id="6e639-127">Nyissa meg szerkesztésre kijelölt ER-formátum piszkozatverzióját.</span><span class="sxs-lookup"><span data-stu-id="6e639-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="6e639-128">A Művelet panelen kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="6e639-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="6e639-129">Kattintson a Frissítés az Excel programból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e639-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="6e639-130">Kattintson a 'Sablon frissítése' lehetőségre, és jelölje ki a SampleVendPaymWsReport2.xlsx fájlt.</span><span class="sxs-lookup"><span data-stu-id="6e639-130">Click ‘Update template’, and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="6e639-131">Kattintson a Sablon frissítése lehetőségre, és tallózással keresse meg a korábban letöltött SampleVendPaymWsReport2.xlsx fájlt.</span><span class="sxs-lookup"><span data-stu-id="6e639-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="6e639-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6e639-132">Click OK.</span></span>
    * <span data-ttu-id="6e639-133">A SampleVendPaymWsReport2.xlsx sablont alkalmazza a program.</span><span class="sxs-lookup"><span data-stu-id="6e639-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="6e639-134">A rendszer szinkronizálja az ER-formátum struktúráját a sablon tartalmával, amelynek az elemei hozzáadódnak az ER-formátumhoz.</span><span class="sxs-lookup"><span data-stu-id="6e639-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="6e639-135">Bármely meglévő elem az ER-formátumban, amely nem szerepel a sablonban, törlődik a formátum definíciójából.</span><span class="sxs-lookup"><span data-stu-id="6e639-135">Any existing elements in the ER format that aren’t included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="6e639-136">A fastruktúrában válassza ki ezt: 'Excel'.</span><span class="sxs-lookup"><span data-stu-id="6e639-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="6e639-137">Vegye figyelembe, hogy a Sablon mező most már az új sablonra mutató hivatkozást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="6e639-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="6e639-138">Kattintson a Mellékletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e639-138">Click Attachments.</span></span>
7. <span data-ttu-id="6e639-139">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="6e639-139">Click Open.</span></span>
    * <span data-ttu-id="6e639-140">Kattintson a Megnyitás elemre a módosított Excel-sablon elrendezésének megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="6e639-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="6e639-141">Végezze el a sablon felülvizsgálatát.</span><span class="sxs-lookup"><span data-stu-id="6e639-141">Review the template.</span></span> <span data-ttu-id="6e639-142">Vegye figyelembe, hogy most már tartalmaz egy sort a fizetési dátumnak.</span><span class="sxs-lookup"><span data-stu-id="6e639-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="6e639-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6e639-143">Close the page.</span></span>
9. <span data-ttu-id="6e639-144">A fastruktúrában bontsa ki ezt: „Excel”.</span><span class="sxs-lookup"><span data-stu-id="6e639-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="6e639-145">A fában bontsa ki az „Excel\PaymLines” elemet.</span><span class="sxs-lookup"><span data-stu-id="6e639-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="6e639-146">A fastruktúrában válassza ki ezt: „Excel\PaymLines\PaymDate”.</span><span class="sxs-lookup"><span data-stu-id="6e639-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="6e639-147">Megjegyzendő, hogy az ER-formátum most eggyel több elemet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="6e639-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="6e639-148">A cella PaymDate cella hozzá lett adva az Excel-sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="6e639-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="6e639-149">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="6e639-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="6e639-150">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="6e639-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="6e639-151">A fában bontsa ki a „model\Payments” elemet.</span><span class="sxs-lookup"><span data-stu-id="6e639-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="6e639-152">A fán válassza ki a „model\Payments= Transactions\Transaction date(TransactionDate)” pontot.</span><span class="sxs-lookup"><span data-stu-id="6e639-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="6e639-153">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="6e639-153">Click Bind.</span></span>
    * <span data-ttu-id="6e639-154">Adja meg, hogy milyen adatok lesznek hozzáadva az új cellához futásidőben.</span><span class="sxs-lookup"><span data-stu-id="6e639-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="6e639-155">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6e639-155">Click Save.</span></span>
18. <span data-ttu-id="6e639-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6e639-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="6e639-157">Az ER-formátum módosított piszkozatverziójának engedélyezése a fizetési napló feldolgozásának használatához</span><span class="sxs-lookup"><span data-stu-id="6e639-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="6e639-158">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="6e639-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="6e639-159">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e639-159">Click User parameters.</span></span>
3. <span data-ttu-id="6e639-160">Válassza az Igen lehetőséget a Beállítások futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="6e639-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="6e639-161">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6e639-161">Click OK.</span></span>
5. <span data-ttu-id="6e639-162">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6e639-162">Click Edit.</span></span>
6. <span data-ttu-id="6e639-163">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="6e639-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="6e639-164">Az ER-formátum módosított piszkozatverziójának használata a fizetési napló feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="6e639-164">Use the modified draft version of the ER format for payment journal processing</span></span>
    * <span data-ttu-id="6e639-165">Tekintse át a létrehozott munkalapot, beleértve a fizetési sorok új adatát, a fizetési dátumot.</span><span class="sxs-lookup"><span data-stu-id="6e639-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  


---
title: A létrehozott ER-jelentések eredményeinek nyomon követésében és a kiindulási értékekkel való összehasonlításukban végzett fejlesztések
description: Ez a témakör az ER alaptervfunkcióban végzett fejlesztésekről tájékoztat a Microsoft Dynamics 365 for Finance and Operations 10.0.3-as (2019. júniusi) verziójában.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: a260be0f8659106907b26bf69bee3b33b09d0c24
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181335"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="403dd-103">A létrehozott ER-jelentések eredményeinek nyomon követésében és a kiindulási értékekkel való összehasonlításukban végzett fejlesztések</span><span class="sxs-lookup"><span data-stu-id="403dd-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="403dd-104">Ez a témakör bemutatja a fejlesztések első körét, amelyet az Elektronikus jelentéskészítés (ER) keretrendszer alaptervfunkciójában végeztek.</span><span class="sxs-lookup"><span data-stu-id="403dd-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="403dd-105">Ezek a fejlesztések a Microsoft Dynamics 365 for Finance and Operations 10.0.3-as (2019. júniusi) és a újabb verziókban érhetők el.</span><span class="sxs-lookup"><span data-stu-id="403dd-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="403dd-106">Alaptervszabályok beállításának automatizálása</span><span class="sxs-lookup"><span data-stu-id="403dd-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="403dd-107">[A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md) témakör bemutatja, hogy az ER-keretrendszer konfigurálása segítségével hogyan lehet információt gyűjteni az ER formátum-végrehajtásokról, és értékelni a végrehajtások eredményeit.</span><span class="sxs-lookup"><span data-stu-id="403dd-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="403dd-108">Az ebben a témakörben szereplő példa bemutatja, hogy milyen lépéseket kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="403dd-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="403dd-109">Az alábbiakban látható néhány ilyen lépés:</span><span class="sxs-lookup"><span data-stu-id="403dd-109">Here are some of the steps:</span></span>

- <span data-ttu-id="403dd-110">Futtasson egy ER-formátumot egy kimenő fájl létrehozásához, és tárolja a fájlt helyileg.</span><span class="sxs-lookup"><span data-stu-id="403dd-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="403dd-111">Adja hozzá a helyileg tárolt fájlt a alapterv mellékleteként, amelyet egy ER-formátumhoz hozzáadott.</span><span class="sxs-lookup"><span data-stu-id="403dd-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="403dd-112">Konfigurálja az alaptervszabályt a hozzáadott alaptervhez.</span><span class="sxs-lookup"><span data-stu-id="403dd-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="403dd-113">Ez a konfiguráció a következő lépéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="403dd-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="403dd-114">Adja meg a kimenő fájlok előállításához használt, ER-formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="403dd-115">Válassza ki a létrejövő kimenő fájlra hivatkozó mellékletet.</span><span class="sxs-lookup"><span data-stu-id="403dd-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="403dd-116">Ezeket a lépéseket manuálisan kell elvégezni, még akkor is, ha az új ER-lehetőségek lehetővé teszik, hogy automatizáltak legyenek.</span><span class="sxs-lookup"><span data-stu-id="403dd-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="403dd-117">Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.</span><span class="sxs-lookup"><span data-stu-id="403dd-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="403dd-118">Példa: Alaptervszabályok beállításának automatizálása</span><span class="sxs-lookup"><span data-stu-id="403dd-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="403dd-119">A példa lépéseinek végrehajtásához először végre kell hajtania [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a alaptervértékekkel](er-trace-reports-compare-baseline.md) témakör példájának lépéseit, egészen az „Új alapterv hozzáadása egy megtervezett ER-formátumhoz” szakaszig.</span><span class="sxs-lookup"><span data-stu-id="403dd-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="403dd-120">Hozzáadott alapterv áttekintése</span><span class="sxs-lookup"><span data-stu-id="403dd-120">Review added baseline</span></span>

1. <span data-ttu-id="403dd-121">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="403dd-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="403dd-122">Válassza az **Alaptervek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="403dd-123">Az **Alaptervek** gomb a műveleti ablaktáblán csak akkor elérhető, ha a **Futtatás hibakeresési módban** felhasználói ER-paraméter be van kapcsolva a jelenlegi vállalathoz.</span><span class="sxs-lookup"><span data-stu-id="403dd-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="403dd-124">A alaptervet a a rendszer hozzáadta a kiválasztott **ER-alaptervek tanulási formátuma** formátumhoz, de a alaptervszabályokat még nem adták hozzá az adott alaptervhez.</span><span class="sxs-lookup"><span data-stu-id="403dd-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="403dd-125">![Elektronikus jelentéskészítés alaptervformátumai oldal](media/GER-BaselineSample-AddBaseline2.PNG "Képernyőkép – Elektronikus jelentéskészítés alaptervformátumai oldal")</span><span class="sxs-lookup"><span data-stu-id="403dd-125">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="403dd-126">Új alaptervszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="403dd-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="403dd-127">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="403dd-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="403dd-128">A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="403dd-129">A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="403dd-130">A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="403dd-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="403dd-131">Az **Azonosító megadása** mezőbe írja az **1** értéket.</span><span class="sxs-lookup"><span data-stu-id="403dd-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="403dd-132">A **Alaptervfájlok létrehozása** beállítást állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="403dd-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="403dd-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-133">Select **OK**.</span></span>

    <span data-ttu-id="403dd-134">![Elektronikus jelentés paraméterei párbeszédpanel](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Képernyőkép – Elektronikus jelentés paraméterei párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="403dd-134">![Electronic report parameters dialog box](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Screenshot of the Electronic report parameters dialog box")</span></span>

8. <span data-ttu-id="403dd-135">Válassza az **Alaptervek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-135">Select **Baselines**.</span></span>

    <span data-ttu-id="403dd-136">![Elektronikus jelentéskészítés alaptervformátumai oldal](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Képernyőkép – Elektronikus jelentéskészítés alaptervformátumai oldal")</span><span class="sxs-lookup"><span data-stu-id="403dd-136">![Electronic reporting format baselines page](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="403dd-137">A létrejövő kimenő fájl automatikusan a végrehajtott ER-formátum alaptervéhez van csatolva.</span><span class="sxs-lookup"><span data-stu-id="403dd-137">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="403dd-138">A alaptervszabály automatikusan hozzáadódott ehhez az alaptervhez, és a csatolt fájlra mutató hivatkozást is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="403dd-138">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="403dd-139">A **Név** mezőbe írja be: **1. alapterv**.</span><span class="sxs-lookup"><span data-stu-id="403dd-139">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="403dd-140">Az **Fájlnév-maszk** mezőbe írja be a következőt: **.xml**.</span><span class="sxs-lookup"><span data-stu-id="403dd-140">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="403dd-141">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-141">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="403dd-142">A formátum futtatása</span><span class="sxs-lookup"><span data-stu-id="403dd-142">Run the format</span></span>

<span data-ttu-id="403dd-143">Most már készen áll [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a alaptervértékekkel](er-trace-reports-compare-baseline.md) témakör példájának fennmaradó lépéseit megtenni, a „Megtervezett ER-formátum futtatása, és a napló áttekintése az eredmények elemzéséhez” szakasztól kezdve.</span><span class="sxs-lookup"><span data-stu-id="403dd-143">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="403dd-144">Amikor törli az automatikusan hozzáadott alaptervszabályt az **Alaptervek** gyorslapon, a hivatkozott mellékletet nem törli automatikusan a program.</span><span class="sxs-lookup"><span data-stu-id="403dd-144">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="403dd-145">Úgy konfigurálja az alaptervet, hogy figyelmen kívül hagyja az ER-kimenet állandóan változó részeit.</span><span class="sxs-lookup"><span data-stu-id="403dd-145">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="403dd-146">Ha egy ER-formátum úgy van kialakítva, hogy a formátum futtatásakor módosuló adatokat tartalmazzon, akkor a formátumnak kötelezően az ER alaptervfunkcióját kell alkalmaznia a létrejövő eredmények és a kiindulási érétkek összehasonlítására.</span><span class="sxs-lookup"><span data-stu-id="403dd-146">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="403dd-147">Például előfordulhat, hogy az információ a dátumot és időpontot, vagy a létrehozott dokumentum egyedi azonosítóját különböző formátumban dolgozza fel (globálisan egyedi azonosító \[GUID\] stb.).</span><span class="sxs-lookup"><span data-stu-id="403dd-147">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="403dd-148">Az új ER-lehetőséges segítségével az alaptervszabályokat úgy konfigurálhatja, hogy figyelmen kívül hagyja az ER-formátum módosítható elemeit, amikor a formátumot a kiindulási értékek és a formátum végrehajtási eredményeinek összehasonlítása céljából futtatták.</span><span class="sxs-lookup"><span data-stu-id="403dd-148">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="403dd-149">Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.</span><span class="sxs-lookup"><span data-stu-id="403dd-149">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="403dd-150">Példa: Alapterv konfigurálása úgy, hogy figyelmen kívül hagyja az ER-kimenet állandóan változó részeit</span><span class="sxs-lookup"><span data-stu-id="403dd-150">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="403dd-151">A példa lépéseinek végrehajtásához először végre kell hajtania [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md) témakör példájának lépéseit.</span><span class="sxs-lookup"><span data-stu-id="403dd-151">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="403dd-152">Konfigurált ER-formátum módosítása</span><span class="sxs-lookup"><span data-stu-id="403dd-152">Modify a configured ER format</span></span>

1. <span data-ttu-id="403dd-153">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="403dd-153">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="403dd-154">A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-154">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="403dd-155">A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-155">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="403dd-156">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-156">Select **Designer**.</span></span>
5. <span data-ttu-id="403dd-157">A fában válassza ki a **Output\\Document** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="403dd-157">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="403dd-158">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-158">Select **Add**.</span></span>
7. <span data-ttu-id="403dd-159">A fastruktúra legördülő párbeszédpaneljében válassza az **XML\\Attribútum** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-159">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="403dd-160">A **Név** mezőbe írja be a következőt: **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="403dd-160">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="403dd-161">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-161">Select **OK**.</span></span>
10. <span data-ttu-id="403dd-162">A **Hozzárendelés** lap fastruktúrájában válassza ki a **Kimenet\\Dokumentum\\ProcessingDateTime** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-162">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="403dd-163">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-163">Select **Edit formula**.</span></span>
12. <span data-ttu-id="403dd-164">A **Képlet** mezőben adja meg a következő kifejezést: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="403dd-164">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="403dd-165">Válassza a **Mentés** parancsot, majd válassza a **Teszt** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-165">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="403dd-166">A konfigurált kifejezés újrateszteléséhez válassza újra a **Teszt** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-166">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="403dd-167">![Képlettervező lap](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Képernyőkép – Képlettervező lap")</span><span class="sxs-lookup"><span data-stu-id="403dd-167">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="403dd-168">A **Teszteredmények** lap mutatja, hogy a konfigurált kifejezés más dátumot és időpontot ad vissza, amikor a lehívás történik.</span><span class="sxs-lookup"><span data-stu-id="403dd-168">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="403dd-169">Zárja be a **Képlettervező** lapot, majd válassza a **Mentés** gombot.</span><span class="sxs-lookup"><span data-stu-id="403dd-169">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="403dd-170">![Formátumtervező lap](media/GER-BaselineSample-FormatMappingDesign2.PNG "Képernyőkép – Formátumtervező lap")</span><span class="sxs-lookup"><span data-stu-id="403dd-170">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="403dd-171">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="403dd-171">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="403dd-172">Létező alaptervszabály eltávolítása</span><span class="sxs-lookup"><span data-stu-id="403dd-172">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="403dd-173">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="403dd-173">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="403dd-174">Válassza az **Alaptervek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-174">Select **Baselines**.</span></span>
3. <span data-ttu-id="403dd-175">Az alaptervek listájában válassza ki azt az alaptervet, amely az **ER-kiindulások tanulási formátuma** formátumra van beállítva.</span><span class="sxs-lookup"><span data-stu-id="403dd-175">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="403dd-176">Az **Alaptervek** gyorslapon válassza a **Törlés** parancsot a korábban konfigurált alaptervszabály eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="403dd-176">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="403dd-177">![Elektronikus jelentéskészítés formátum-alaptervei oldal](media/GER-BaselineSample-AddBaseline3.PNG "Képernyőkép – Elektronikus jelentéskészítés formátum-alaptervei oldal")</span><span class="sxs-lookup"><span data-stu-id="403dd-177">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="403dd-178">A megtervezett ER-formátum kötéseihez tartozó helyettesítések meghatározása</span><span class="sxs-lookup"><span data-stu-id="403dd-178">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="403dd-179">Válassza a **Konfigurációk** lap **Helyettesítések** gyorslapján az **Összetevők kiválasztása** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-179">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="403dd-180">A formátum-összetevők fastruktúrájában bontsa ki a **Kimenet** elemet, majd a **Kimenet\\Dokumentum** pontot, és jelölje be a **Kimenet\\Dokumentum\\ProcessingDateTime** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="403dd-180">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>

    <span data-ttu-id="403dd-181">![Összetevők kiválasztása párbeszédpanel](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Képernyőkép – Összetevők kiválasztása párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="403dd-181">![Select Components dialog box](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Screenshot of the Select Components dialog box")</span></span>

3. <span data-ttu-id="403dd-182">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-182">Select **OK**.</span></span>

<span data-ttu-id="403dd-183">![Elektronikus jelentéskészítés formátum-alaptervei oldal](media/GER-BaselineSample-AddBaseline4.PNG "Képernyőkép – Elektronikus jelentéskészítés formátum-alaptervei oldal")</span><span class="sxs-lookup"><span data-stu-id="403dd-183">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="403dd-184">A kiválasztott ER-formátum-összetevő hozzá van adva az összetevők listájához a **Helyettesítések** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="403dd-184">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="403dd-185">Ha a program hibakeresési módban futtatja az ER alapformátumát, akkor az egyes összetevők formátumának kötését a program a **Kötés** oszlopban szereplő kötéssel helyettesíti.</span><span class="sxs-lookup"><span data-stu-id="403dd-185">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="403dd-186">Ha módosítani szeretné a **Helyettesítések** gyorslapon felsorolt összetevő alapértelmezett kötését, válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="403dd-186">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="403dd-187">Új alaptervszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="403dd-187">Make a new baseline rule</span></span>

<span data-ttu-id="403dd-188">Kövesse az aktuális témakör korábbi, „Példa: Kiindulási szabályok beállításának automatizálása” szakaszának lépéseit.</span><span class="sxs-lookup"><span data-stu-id="403dd-188">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="403dd-189">Egy értesítés figyelmeztet arra, hogy a kimenő fájl az alapterv-beállítások alapján lett létrehozva, és a formátum kötésének kényszerű helyettesítése történt.</span><span class="sxs-lookup"><span data-stu-id="403dd-189">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="403dd-190">![Értesítés a konfigurációk lapon](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Képernyőkép – Értesítés a konfigurációk lapon")</span><span class="sxs-lookup"><span data-stu-id="403dd-190">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="403dd-191">A formátumkötések helyettesítésével kapcsolatos figyelmeztetések figyelmen kívül hagyása</span><span class="sxs-lookup"><span data-stu-id="403dd-191">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="403dd-192">Meghatározott ER-paraméterek beállításával figyelmen kívül hagyhatja a formátumkötések helyettesítésével kapcsolatos figyelmeztetéseket.</span><span class="sxs-lookup"><span data-stu-id="403dd-192">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="403dd-193">Ez a figyelmen kívül hagyás akkor lehet hasznos, ha a kötések formátumát egy felügyelet nélküli módban cseréli le a Regression Suite Automation Tool eszköz használatával.</span><span class="sxs-lookup"><span data-stu-id="403dd-193">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="403dd-194">Ebben az esetben a figyelmeztetés a futó teszteset meghibásodását eredményezheti.</span><span class="sxs-lookup"><span data-stu-id="403dd-194">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="403dd-195">A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="403dd-196">Állítsa az **Alaptervvel kapcsolatos figyelmeztetések figyelmen kívül hagyása** beállítást **Igen** értékre, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-196">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

<span data-ttu-id="403dd-197">![Felhasználói paraméterek párbeszédpanel](media/GER-BaselineSample-ERUserParameters1.png "Képernyőkép – Felhasználói paraméterek párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="403dd-197">![User parameters dialog box](media/GER-BaselineSample-ERUserParameters1.png "Screenshot of the User parameters dialog box")</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="403dd-198">A létrehozott alaptervfájl ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="403dd-198">Review the generated baseline file</span></span>

1. <span data-ttu-id="403dd-199">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="403dd-199">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="403dd-200">Válassza az **Alaptervek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-200">Select **Baselines**.</span></span>
3. <span data-ttu-id="403dd-201">Válassza a **Mellékletek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-201">Select **Attachments**.</span></span>

    <span data-ttu-id="403dd-202">![Mellékletek lap](media/GER-BaselineSample-AttachedBaselineFile.PNG "Képernyőkép – mellékletek lap")</span><span class="sxs-lookup"><span data-stu-id="403dd-202">![Attachments page](media/GER-BaselineSample-AttachedBaselineFile.PNG "Screenshot of the Attachments page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="403dd-203">A létrehozott fájl tartalmazza a feldolgozás dátumának és időpontját szövegét (**"#"**), amely a hozzáadott alaptervszabályban konfigurált kötésből származik, nem pedig a formátum kötéséből.</span><span class="sxs-lookup"><span data-stu-id="403dd-203">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>

4. <span data-ttu-id="403dd-204">Zárja be a **Mellékletek** lapot.</span><span class="sxs-lookup"><span data-stu-id="403dd-204">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="403dd-205">A tervezett ER formátum futtatása és a napló áttekintése az eredmények elemzéséhez</span><span class="sxs-lookup"><span data-stu-id="403dd-205">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="403dd-206">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="403dd-206">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="403dd-207">A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-207">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="403dd-208">A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.</span><span class="sxs-lookup"><span data-stu-id="403dd-208">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="403dd-209">A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="403dd-209">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="403dd-210">Az **Azonosító megadása** mezőbe írja az **1** értéket.</span><span class="sxs-lookup"><span data-stu-id="403dd-210">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="403dd-211">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-211">Select **OK**.</span></span>
7. <span data-ttu-id="403dd-212">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk hibakeresési naplói**.</span><span class="sxs-lookup"><span data-stu-id="403dd-212">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="403dd-213">A végrehajtási napló a megadott alapterv és a létrejövő fájl összehasonlításának eredményeiről tartalmaz információkat.</span><span class="sxs-lookup"><span data-stu-id="403dd-213">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="403dd-214">A napló azt jelzi, hogy a létrejövő fájl és az alapterv egyenlő, még akkor is, ha a végrehajtott formátum tartalmazza a kimenő fájlban folyamatosan változó dátum- és időpontértékének megadására vonatkozó kötést.</span><span class="sxs-lookup"><span data-stu-id="403dd-214">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="403dd-215">Annak ellenére, hogy a kimenő fájl olyan alaptervi beállításokkal lett létrehozva, amelyek a formátum kötéseinek helyettesítését kényszerítik, nem kap figyelmeztetést a helyettesítéssel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="403dd-215">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="403dd-216">Alaptervi beállítások kicserélése környezetek között</span><span class="sxs-lookup"><span data-stu-id="403dd-216">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="403dd-217">Alaptervi beállítások exportálása</span><span class="sxs-lookup"><span data-stu-id="403dd-217">Export baseline settings</span></span>

<span data-ttu-id="403dd-218">Az új ER-funkciók lehetővé teszik a kiválasztott ER-formátum alaptervi beállításainak exportálását az aktuális környezetből, és tárolásukat XML-fájlként.</span><span class="sxs-lookup"><span data-stu-id="403dd-218">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="403dd-219">Az alaptervi beállítások exportálásához kattintson az **Elektronikus jelentéskészítés formátumának alaptervei** oldalon az **Exportálás** elemre.</span><span class="sxs-lookup"><span data-stu-id="403dd-219">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="403dd-220">Kiindulási beállítások importálása</span><span class="sxs-lookup"><span data-stu-id="403dd-220">Import baseline settings</span></span>

<span data-ttu-id="403dd-221">Az exportált alaptervi beállításokat másik környezetbe importálhatja.</span><span class="sxs-lookup"><span data-stu-id="403dd-221">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="403dd-222">A környezetet előbb ER-formátumként kell importálni.</span><span class="sxs-lookup"><span data-stu-id="403dd-222">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="403dd-223">Ezt követően importálhatja az alaptervi beállításokat.</span><span class="sxs-lookup"><span data-stu-id="403dd-223">You can then import the baseline settings.</span></span>

<span data-ttu-id="403dd-224">Ha egy helyileg tárolt XML-fájlból szeretne alaptervi beállításokat importálni, válassza az **Elektronikus jelentéskészítés formátumának alaptervei** lapot, válassza az **importálás** lehetőséget, majd válassza a **Tallózás** lehetőséget az XML-fájl kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="403dd-224">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="403dd-225">![Alaptervi beállítások importálása párbeszédpanel](media/GER-BaselineSample-ImportBaseline1.PNG "Képernyőkép – Alaptervi beállítások importálása párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="403dd-225">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="403dd-226">Ha a Microsoft SharePoint Server felületén tárolt XML-fájlból szeretne alaptervi beállításokat importálni, az aktuális Dokumentumkezelési beállítások és a kiválasztott dokumentumtípus alapján, válassza az **Elektronikus jelentéskészítés formátumának alaptervei** oldalon az **Importálás forrásból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="403dd-226">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="403dd-227">Majd válassza ki a dokumentumtípust és az XML-fájlt.</span><span class="sxs-lookup"><span data-stu-id="403dd-227">Then select the document type and the XML file.</span></span> <span data-ttu-id="403dd-228">A SharePoint-mappához való hozzáféréshez szükséges dokumentumtípust be kell állítani előre.</span><span class="sxs-lookup"><span data-stu-id="403dd-228">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="403dd-229">![Importálás forrásból párbeszédpanel](media/GER-BaselineSample-ImportBaseline2.PNG "Képernyőkép – Importálás forrásból párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="403dd-229">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="403dd-230">A Feladatrögzítő segítségével rögzítheti a szükség dokumentumtípus kiválasztásának lépéseit és a fájlnevet az **Importálás forrásból** párbeszédpanelben.</span><span class="sxs-lookup"><span data-stu-id="403dd-230">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="403dd-231">Ily módon a szükséges alaptervi beállításokat SharePoint Server felületén tárolhatja, és automatikusan importálhatja őket egy feladatrögzítés lejátszásával a Regression Suite Automation Tool használatával futtatott automatizált tesztek futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="403dd-231">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="403dd-232">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="403dd-232">Additional resources</span></span>

- [<span data-ttu-id="403dd-233">A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel</span><span class="sxs-lookup"><span data-stu-id="403dd-233">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="403dd-234">Feladatrögzítő</span><span class="sxs-lookup"><span data-stu-id="403dd-234">Task recorder</span></span>](../user-interface/task-recorder.md)

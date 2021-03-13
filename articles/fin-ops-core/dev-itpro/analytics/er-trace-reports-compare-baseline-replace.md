---
title: A létrehozott ER-jelentések eredményeinek nyomon követésében és a kiindulási értékekkel való összehasonlításukban végzett fejlesztések
description: Ez a témakör a Microsoft Dynamics 365 for Finance and Operations 10.0.3-as verzió (2019. június) kiindulási ER-funkciójának javításait ismerteti.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1c00a5d9e2804f6ec0f6cb4c544029a1235ee58d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094004"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="cb48d-103">A létrehozott ER-jelentések eredményeinek nyomon követésében és a kiindulási értékekkel való összehasonlításukban végzett fejlesztések</span><span class="sxs-lookup"><span data-stu-id="cb48d-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cb48d-104">Ez a témakör bemutatja a fejlesztések első körét, amelyet az Elektronikus jelentéskészítés (ER) keretrendszer alaptervfunkciójában végeztek.</span><span class="sxs-lookup"><span data-stu-id="cb48d-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="cb48d-105">Ezek a fejlesztések a Microsoft Dynamics 365 for Finance and Operations 10.0.3-as (2019. júniusi) és a újabb verziókban érhetők el.</span><span class="sxs-lookup"><span data-stu-id="cb48d-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="cb48d-106">Alaptervszabályok beállításának automatizálása</span><span class="sxs-lookup"><span data-stu-id="cb48d-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="cb48d-107">[A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md) témakör bemutatja, hogy az ER-keretrendszer konfigurálása segítségével hogyan lehet információt gyűjteni az ER formátum-végrehajtásokról, és értékelni a végrehajtások eredményeit.</span><span class="sxs-lookup"><span data-stu-id="cb48d-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="cb48d-108">Az ebben a témakörben szereplő példa bemutatja, hogy milyen lépéseket kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="cb48d-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="cb48d-109">Az alábbiakban látható néhány ilyen lépés:</span><span class="sxs-lookup"><span data-stu-id="cb48d-109">Here are some of the steps:</span></span>

- <span data-ttu-id="cb48d-110">Futtasson egy ER-formátumot egy kimenő fájl létrehozásához, és tárolja a fájlt helyileg.</span><span class="sxs-lookup"><span data-stu-id="cb48d-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="cb48d-111">Adja hozzá a helyileg tárolt fájlt a alapterv mellékleteként, amelyet egy ER-formátumhoz hozzáadott.</span><span class="sxs-lookup"><span data-stu-id="cb48d-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="cb48d-112">Konfigurálja az alaptervszabályt a hozzáadott alaptervhez.</span><span class="sxs-lookup"><span data-stu-id="cb48d-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="cb48d-113">Ez a konfiguráció a következő lépéseket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="cb48d-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="cb48d-114">Adja meg a kimenő fájlok előállításához használt, ER-formátumelemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="cb48d-115">Válassza ki a létrejövő kimenő fájlra hivatkozó mellékletet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="cb48d-116">Ezeket a lépéseket manuálisan kell elvégezni, még akkor is, ha az új ER-lehetőségek lehetővé teszik, hogy automatizáltak legyenek.</span><span class="sxs-lookup"><span data-stu-id="cb48d-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="cb48d-117">Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.</span><span class="sxs-lookup"><span data-stu-id="cb48d-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="cb48d-118">Példa: Alaptervszabályok beállításának automatizálása</span><span class="sxs-lookup"><span data-stu-id="cb48d-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="cb48d-119">A példa lépéseinek végrehajtásához először végre kell hajtania [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a alaptervértékekkel](er-trace-reports-compare-baseline.md) témakör példájának lépéseit, egészen az „Új alapterv hozzáadása egy megtervezett ER-formátumhoz” szakaszig.</span><span class="sxs-lookup"><span data-stu-id="cb48d-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="cb48d-120">Hozzáadott alapterv áttekintése</span><span class="sxs-lookup"><span data-stu-id="cb48d-120">Review added baseline</span></span>

1. <span data-ttu-id="cb48d-121">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="cb48d-122">Válassza az **Alaptervek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb48d-123">Az **Alaptervek** gomb a műveleti ablaktáblán csak akkor elérhető, ha a **Futtatás hibakeresési módban** felhasználói ER-paraméter be van kapcsolva a jelenlegi vállalathoz.</span><span class="sxs-lookup"><span data-stu-id="cb48d-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="cb48d-124">A alaptervet a a rendszer hozzáadta a kiválasztott **ER-alaptervek tanulási formátuma** formátumhoz, de a alaptervszabályokat még nem adták hozzá az adott alaptervhez.</span><span class="sxs-lookup"><span data-stu-id="cb48d-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="cb48d-125">![Elektronikus jelentéskészítés formátumának alaptervei oldal, még nincsenek szabályok](media/GER-BaselineSample-AddBaseline2.PNG "Képernyőkép – az elektronikus jelentéskészítés formátumának alaptervei lap")</span><span class="sxs-lookup"><span data-stu-id="cb48d-125">![Electronic reporting format baselines page, no rules yet](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="cb48d-126">Új alaptervszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="cb48d-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="cb48d-127">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="cb48d-128">A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="cb48d-129">A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="cb48d-130">A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb48d-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="cb48d-131">Az **Azonosító megadása** mezőbe írja az **1** értéket.</span><span class="sxs-lookup"><span data-stu-id="cb48d-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="cb48d-132">A **Alaptervfájlok létrehozása** beállítást állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="cb48d-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="cb48d-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-133">Select **OK**.</span></span>
8. <span data-ttu-id="cb48d-134">**Alaptervek** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="cb48d-134">Select **Baselines**.</span></span>

    <span data-ttu-id="cb48d-135">![Az elektronikus jelentéskészítés formátumának alaptervei oldal, alapok kiválasztva](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Képernyőkép – az elektronikus jelentéskészítés formátumának alaptervei lap")</span><span class="sxs-lookup"><span data-stu-id="cb48d-135">![Electronic reporting format baselines page, baselines selected](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="cb48d-136">A létrejövő kimenő fájl automatikusan a végrehajtott ER-formátum alaptervéhez van csatolva.</span><span class="sxs-lookup"><span data-stu-id="cb48d-136">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="cb48d-137">A alaptervszabály automatikusan hozzáadódott ehhez az alaptervhez, és a csatolt fájlra mutató hivatkozást is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="cb48d-137">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="cb48d-138">A **Név** mezőbe írja be: **1. alapterv**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-138">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="cb48d-139">Az **Fájlnév-maszk** mezőbe írja be a következőt: **.xml**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-139">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="cb48d-140">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-140">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="cb48d-141">A formátum futtatása</span><span class="sxs-lookup"><span data-stu-id="cb48d-141">Run the format</span></span>

<span data-ttu-id="cb48d-142">Most már készen áll [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a alaptervértékekkel](er-trace-reports-compare-baseline.md) témakör példájának fennmaradó lépéseit megtenni, a „Megtervezett ER-formátum futtatása, és a napló áttekintése az eredmények elemzéséhez” szakasztól kezdve.</span><span class="sxs-lookup"><span data-stu-id="cb48d-142">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="cb48d-143">Amikor törli az automatikusan hozzáadott alaptervszabályt az **Alaptervek** gyorslapon, a hivatkozott mellékletet nem törli automatikusan a program.</span><span class="sxs-lookup"><span data-stu-id="cb48d-143">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="cb48d-144">Úgy konfigurálja az alaptervet, hogy figyelmen kívül hagyja az ER-kimenet állandóan változó részeit.</span><span class="sxs-lookup"><span data-stu-id="cb48d-144">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="cb48d-145">Ha egy ER-formátum úgy van kialakítva, hogy a formátum futtatásakor módosuló adatokat tartalmazzon, akkor a formátumnak kötelezően az ER alaptervfunkcióját kell alkalmaznia a létrejövő eredmények és a kiindulási érétkek összehasonlítására.</span><span class="sxs-lookup"><span data-stu-id="cb48d-145">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="cb48d-146">Például előfordulhat, hogy az információ a dátumot és időpontot, vagy a létrehozott dokumentum egyedi azonosítóját különböző formátumban dolgozza fel (globálisan egyedi azonosító \[GUID\] stb.).</span><span class="sxs-lookup"><span data-stu-id="cb48d-146">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="cb48d-147">Az új ER-lehetőséges segítségével az alaptervszabályokat úgy konfigurálhatja, hogy figyelmen kívül hagyja az ER-formátum módosítható elemeit, amikor a formátumot a kiindulási értékek és a formátum végrehajtási eredményeinek összehasonlítása céljából futtatták.</span><span class="sxs-lookup"><span data-stu-id="cb48d-147">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="cb48d-148">Ha további tájékoztatást szeretne erről a funkcióról, hajtsa végre a következő példát.</span><span class="sxs-lookup"><span data-stu-id="cb48d-148">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="cb48d-149">Példa: Alapterv konfigurálása úgy, hogy figyelmen kívül hagyja az ER-kimenet állandóan változó részeit</span><span class="sxs-lookup"><span data-stu-id="cb48d-149">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="cb48d-150">A példa lépéseinek végrehajtásához először végre kell hajtania [A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel](er-trace-reports-compare-baseline.md) témakör példájának lépéseit.</span><span class="sxs-lookup"><span data-stu-id="cb48d-150">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="cb48d-151">Konfigurált ER-formátum módosítása</span><span class="sxs-lookup"><span data-stu-id="cb48d-151">Modify a configured ER format</span></span>

1. <span data-ttu-id="cb48d-152">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-152">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="cb48d-153">A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-153">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="cb48d-154">A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-154">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="cb48d-155">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-155">Select **Designer**.</span></span>
5. <span data-ttu-id="cb48d-156">A fában válassza ki a **Output\\Document** csomópontot.</span><span class="sxs-lookup"><span data-stu-id="cb48d-156">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="cb48d-157">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-157">Select **Add**.</span></span>
7. <span data-ttu-id="cb48d-158">A fastruktúra legördülő párbeszédpaneljében válassza az **XML\\Attribútum** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-158">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="cb48d-159">A **Név** mezőbe írja be a következőt: **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-159">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="cb48d-160">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-160">Select **OK**.</span></span>
10. <span data-ttu-id="cb48d-161">A **Hozzárendelés** lap fastruktúrájában válassza ki a **Kimenet\\Dokumentum\\ProcessingDateTime** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-161">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="cb48d-162">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-162">Select **Edit formula**.</span></span>
12. <span data-ttu-id="cb48d-163">A **Képlet** mezőben adja meg a következő kifejezést: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="cb48d-163">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="cb48d-164">Válassza a **Mentés** parancsot, majd válassza a **Teszt** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-164">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="cb48d-165">A konfigurált kifejezés újrateszteléséhez válassza újra a **Teszt** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-165">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="cb48d-166">![Képletszerkesztő oldala](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Képernyőkép – Képlettervező oldala")</span><span class="sxs-lookup"><span data-stu-id="cb48d-166">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb48d-167">A **Teszteredmények** lap mutatja, hogy a konfigurált kifejezés más dátumot és időpontot ad vissza, amikor a lehívás történik.</span><span class="sxs-lookup"><span data-stu-id="cb48d-167">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="cb48d-168">Zárja be a **Képlettervező** lapot, majd válassza a **Mentés** gombot.</span><span class="sxs-lookup"><span data-stu-id="cb48d-168">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="cb48d-169">![Formátumtervező oldal](media/GER-BaselineSample-FormatMappingDesign2.PNG "Képernyőkép – Formátumtervező oldala")</span><span class="sxs-lookup"><span data-stu-id="cb48d-169">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="cb48d-170">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="cb48d-170">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="cb48d-171">Létező alaptervszabály eltávolítása</span><span class="sxs-lookup"><span data-stu-id="cb48d-171">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="cb48d-172">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-172">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="cb48d-173">Válassza az **Alaptervek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-173">Select **Baselines**.</span></span>
3. <span data-ttu-id="cb48d-174">Az alaptervek listájában válassza ki azt az alaptervet, amely az **ER-kiindulások tanulási formátuma** formátumra van beállítva.</span><span class="sxs-lookup"><span data-stu-id="cb48d-174">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="cb48d-175">Az **Alaptervek** gyorslapon válassza a **Törlés** parancsot a korábban konfigurált alaptervszabály eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="cb48d-175">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="cb48d-176">![Elektronikus jelentéskészítés formátumának alaptervei oldal, törölve](media/GER-BaselineSample-AddBaseline3.PNG "Képernyőkép – az elektronikus jelentéskészítés formátumának alaptervei lap")</span><span class="sxs-lookup"><span data-stu-id="cb48d-176">![Electronic reporting format baselines page, deleted](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="cb48d-177">A megtervezett ER-formátum kötéseihez tartozó helyettesítések meghatározása</span><span class="sxs-lookup"><span data-stu-id="cb48d-177">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="cb48d-178">Válassza a **Konfigurációk** lap **Helyettesítések** gyorslapján az **Összetevők kiválasztása** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-178">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="cb48d-179">A formátum-összetevők fastruktúrájában bontsa ki a **Kimenet** elemet, majd a **Kimenet\\Dokumentum** pontot, és jelölje be a **Kimenet\\Dokumentum\\ProcessingDateTime** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-179">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>
3. <span data-ttu-id="cb48d-180">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-180">Select **OK**.</span></span>

<span data-ttu-id="cb48d-181">![Elektronikus jelentéskészítés formátumának alaptervei oldal, összetevők](media/GER-BaselineSample-AddBaseline4.PNG "Képernyőkép – az elektronikus jelentéskészítés formátumának alaptervei lap")</span><span class="sxs-lookup"><span data-stu-id="cb48d-181">![Electronic reporting format baselines page, components](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="cb48d-182">A kiválasztott ER-formátum-összetevő hozzá van adva az összetevők listájához a **Helyettesítések** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="cb48d-182">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="cb48d-183">Ha a program hibakeresési módban futtatja az ER alapformátumát, akkor az egyes összetevők formátumának kötését a program a **Kötés** oszlopban szereplő kötéssel helyettesíti.</span><span class="sxs-lookup"><span data-stu-id="cb48d-183">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="cb48d-184">Ha módosítani szeretné a **Helyettesítések** gyorslapon felsorolt összetevő alapértelmezett kötését, válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cb48d-184">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="cb48d-185">Új alaptervszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="cb48d-185">Make a new baseline rule</span></span>

<span data-ttu-id="cb48d-186">Kövesse az aktuális témakör korábbi, „Példa: Kiindulási szabályok beállításának automatizálása” szakaszának lépéseit.</span><span class="sxs-lookup"><span data-stu-id="cb48d-186">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="cb48d-187">Egy értesítés figyelmeztet arra, hogy a kimenő fájl az alapterv-beállítások alapján lett létrehozva, és a formátum kötésének kényszerű helyettesítése történt.</span><span class="sxs-lookup"><span data-stu-id="cb48d-187">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="cb48d-188">![Konfigurációk oldal értesítése](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Képernyőkép – Értesítés a Konfigurációk oldalon")</span><span class="sxs-lookup"><span data-stu-id="cb48d-188">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="cb48d-189">A formátumkötések helyettesítésével kapcsolatos figyelmeztetések figyelmen kívül hagyása</span><span class="sxs-lookup"><span data-stu-id="cb48d-189">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="cb48d-190">Meghatározott ER-paraméterek beállításával figyelmen kívül hagyhatja a formátumkötések helyettesítésével kapcsolatos figyelmeztetéseket.</span><span class="sxs-lookup"><span data-stu-id="cb48d-190">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="cb48d-191">Ez a figyelmen kívül hagyás akkor lehet hasznos, ha a kötések formátumát egy felügyelet nélküli módban cseréli le a Regression Suite Automation Tool eszköz használatával.</span><span class="sxs-lookup"><span data-stu-id="cb48d-191">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="cb48d-192">Ebben az esetben a figyelmeztetés a futó teszteset meghibásodását eredményezheti.</span><span class="sxs-lookup"><span data-stu-id="cb48d-192">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="cb48d-193">A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-193">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="cb48d-194">Állítsa az **Alaptervvel kapcsolatos figyelmeztetések figyelmen kívül hagyása** beállítást **Igen** értékre, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-194">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="cb48d-195">A létrehozott alaptervfájl ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="cb48d-195">Review the generated baseline file</span></span>

1. <span data-ttu-id="cb48d-196">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="cb48d-197">**Alaptervek** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="cb48d-197">Select **Baselines**.</span></span>
3. <span data-ttu-id="cb48d-198">**Mellékletek** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="cb48d-198">Select **Attachments**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cb48d-199">A létrehozott fájl tartalmazza a feldolgozás dátumának és időpontját szövegét (**"#"**), amely a hozzáadott alaptervszabályban konfigurált kötésből származik, nem pedig a formátum kötéséből.</span><span class="sxs-lookup"><span data-stu-id="cb48d-199">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>
    
4. <span data-ttu-id="cb48d-200">Zárja be a **Mellékletek** lapot.</span><span class="sxs-lookup"><span data-stu-id="cb48d-200">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="cb48d-201">A tervezett ER formátum futtatása és a napló áttekintése az eredmények elemzéséhez</span><span class="sxs-lookup"><span data-stu-id="cb48d-201">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="cb48d-202">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-202">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="cb48d-203">A fastruktúrában bontsa ki az **ER-alaptervek tanulásához használatos modell** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-203">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="cb48d-204">A fastruktúrában válassza ki az **ER-alaptervek tanulásához használatos modell\\ER-alaptervek tanulási formátuma** elemet.</span><span class="sxs-lookup"><span data-stu-id="cb48d-204">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="cb48d-205">A **Verziók** gyorslapon kattintson a **Futtatás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb48d-205">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="cb48d-206">Az **Azonosító megadása** mezőbe írja az **1** értéket.</span><span class="sxs-lookup"><span data-stu-id="cb48d-206">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="cb48d-207">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-207">Select **OK**.</span></span>
7. <span data-ttu-id="cb48d-208">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk hibakeresési naplói**.</span><span class="sxs-lookup"><span data-stu-id="cb48d-208">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="cb48d-209">A végrehajtási napló a megadott alapterv és a létrejövő fájl összehasonlításának eredményeiről tartalmaz információkat.</span><span class="sxs-lookup"><span data-stu-id="cb48d-209">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="cb48d-210">A napló azt jelzi, hogy a létrejövő fájl és az alapterv egyenlő, még akkor is, ha a végrehajtott formátum tartalmazza a kimenő fájlban folyamatosan változó dátum- és időpontértékének megadására vonatkozó kötést.</span><span class="sxs-lookup"><span data-stu-id="cb48d-210">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="cb48d-211">Annak ellenére, hogy a kimenő fájl olyan alaptervi beállításokkal lett létrehozva, amelyek a formátum kötéseinek helyettesítését kényszerítik, nem kap figyelmeztetést a helyettesítéssel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="cb48d-211">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="cb48d-212">Alaptervi beállítások kicserélése környezetek között</span><span class="sxs-lookup"><span data-stu-id="cb48d-212">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="cb48d-213">Alaptervi beállítások exportálása</span><span class="sxs-lookup"><span data-stu-id="cb48d-213">Export baseline settings</span></span>

<span data-ttu-id="cb48d-214">Az új ER-funkciók lehetővé teszik a kiválasztott ER-formátum alaptervi beállításainak exportálását az aktuális környezetből, és tárolásukat XML-fájlként.</span><span class="sxs-lookup"><span data-stu-id="cb48d-214">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="cb48d-215">Az alaptervi beállítások exportálásához kattintson az **Elektronikus jelentéskészítés formátumának alaptervei** oldalon az **Exportálás** elemre.</span><span class="sxs-lookup"><span data-stu-id="cb48d-215">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="cb48d-216">Kiindulási beállítások importálása</span><span class="sxs-lookup"><span data-stu-id="cb48d-216">Import baseline settings</span></span>

<span data-ttu-id="cb48d-217">Az exportált alaptervi beállításokat másik környezetbe importálhatja.</span><span class="sxs-lookup"><span data-stu-id="cb48d-217">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="cb48d-218">A környezetet előbb ER-formátumként kell importálni.</span><span class="sxs-lookup"><span data-stu-id="cb48d-218">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="cb48d-219">Ezt követően importálhatja az alaptervi beállításokat.</span><span class="sxs-lookup"><span data-stu-id="cb48d-219">You can then import the baseline settings.</span></span>

<span data-ttu-id="cb48d-220">Ha egy helyileg tárolt XML-fájlból szeretne alaptervi beállításokat importálni, válassza az **Elektronikus jelentéskészítés formátumának alaptervei** lapot, válassza az **importálás** lehetőséget, majd válassza a **Tallózás** lehetőséget az XML-fájl kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="cb48d-220">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="cb48d-221">![Kiindulási beállítások importálása párbeszédablak](media/GER-BaselineSample-ImportBaseline1.PNG "Képernyőkép – Kiindulási beállítások importálása párbeszédablak")</span><span class="sxs-lookup"><span data-stu-id="cb48d-221">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="cb48d-222">Ha a Microsoft SharePoint Server felületén tárolt XML-fájlból szeretne alaptervi beállításokat importálni, az aktuális Dokumentumkezelési beállítások és a kiválasztott dokumentumtípus alapján, válassza az **Elektronikus jelentéskészítés formátumának alaptervei** oldalon az **Importálás forrásból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cb48d-222">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="cb48d-223">Majd válassza ki a dokumentumtípust és az XML-fájlt.</span><span class="sxs-lookup"><span data-stu-id="cb48d-223">Then select the document type and the XML file.</span></span> <span data-ttu-id="cb48d-224">A SharePoint-mappához való hozzáféréshez szükséges dokumentumtípust be kell állítani előre.</span><span class="sxs-lookup"><span data-stu-id="cb48d-224">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="cb48d-225">![Importálás a forrásból párbeszédpanel](media/GER-BaselineSample-ImportBaseline2.PNG "Képernyőkép – Importálás a forrásból párbeszédpanel")</span><span class="sxs-lookup"><span data-stu-id="cb48d-225">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="cb48d-226">A Feladatrögzítő segítségével rögzítheti a szükség dokumentumtípus kiválasztásának lépéseit és a fájlnevet az **Importálás forrásból** párbeszédpanelben.</span><span class="sxs-lookup"><span data-stu-id="cb48d-226">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="cb48d-227">Ily módon a szükséges alaptervi beállításokat SharePoint Server felületén tárolhatja, és automatikusan importálhatja őket egy feladatrögzítés lejátszásával a Regression Suite Automation Tool használatával futtatott automatizált tesztek futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="cb48d-227">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb48d-228">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cb48d-228">Additional resources</span></span>

- [<span data-ttu-id="cb48d-229">A létrehozott jelentés eredményeinek nyomon követése és összehasonlításuk a kiindulási értékekkel</span><span class="sxs-lookup"><span data-stu-id="cb48d-229">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="cb48d-230">Feladatrögzítő erőforrásai</span><span class="sxs-lookup"><span data-stu-id="cb48d-230">Task recorder resources</span></span>](../user-interface/task-recorder.md)

---
title: "A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után"
description: "Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Finance and Operations adatbázis visszaállítása után."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 08a420a776f47119a5dc47f9119545aa448ffdbd
ms.contentlocale: hu-hu
ms.lasthandoff: 08/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="c710e-103">A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után</span><span class="sxs-lookup"><span data-stu-id="c710e-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c710e-104">Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Finance and Operations adatbázis visszaállítása után.</span><span class="sxs-lookup"><span data-stu-id="c710e-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="c710e-105">Ha bármikor visszaállítsa a Dynamics 365 for Operations adatbázist egy biztonsági másolatból, vagy másolja az adatbázist egy másik környezetből, biztosítania kell, hogy a pénzügyi jelentési adatpiac megfelelően használja a visszaállított 365 Dynamics for Finance and Operations adatbázist.</span><span class="sxs-lookup"><span data-stu-id="c710e-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
<!--If you have questions about resetting the financial reporting data mart for a reason outside of restoring a Finance and Operations database, refer to the [Resetting the Management Reporter data mart](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) for more information. -->
> [!Note] 
> <span data-ttu-id="c710e-106">A folyamat lépéseit a Dynamics 365 for Operations 2016 májusi kiadása támogatja (7.0.1265.23014 alkalmazásbild és 7.0.10000.4 pénzügyi jelentési build), valamint az újabb verziók.</span><span class="sxs-lookup"><span data-stu-id="c710e-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="c710e-107">Ha a Dynamics 365 for Finance and Operations egy korábbi verziójával rendelkezik, lépjen kapcsolatba támogatási csoportunkkal segítségért.</span><span class="sxs-lookup"><span data-stu-id="c710e-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="c710e-108">Jelentésdefiníciók exportálása</span><span class="sxs-lookup"><span data-stu-id="c710e-108">Export report definitions</span></span>
<span data-ttu-id="c710e-109">Először exportálja a Jelentéstervezőben található jelentésterveket, a következő lépések végrehajtásával:</span><span class="sxs-lookup"><span data-stu-id="c710e-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="c710e-110">A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="c710e-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="c710e-111">Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c710e-111">Select the building block group to export, and click **Export**.</span></span> 
    > [!Note] 
    > <span data-ttu-id="c710e-112">A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.</span><span class="sxs-lookup"><span data-stu-id="c710e-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
3.  <span data-ttu-id="c710e-113">Válassza ki a jelentésdefiníciókat az exportáláshoz:</span><span class="sxs-lookup"><span data-stu-id="c710e-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="c710e-114">Az összes jelentésdefiníció illetve a társított építőelemek exportálásához kattintson az **Összes kijelölése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c710e-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="c710e-115">Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket.</span><span class="sxs-lookup"><span data-stu-id="c710e-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="c710e-116">Ha több cikket szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt.</span><span class="sxs-lookup"><span data-stu-id="c710e-116">Press and hold the Ctrl key to select multiple items in a tab.</span></span> <span data-ttu-id="c710e-117">Ha exportálandó jelentéseket jelöl ki, úgy kiválasztásra kerülnek a társított sorok, oszlopok, fák és dimenziókészletek is.</span><span class="sxs-lookup"><span data-stu-id="c710e-117">When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="c710e-118">Kattintson az **Exportálás** elemre.</span><span class="sxs-lookup"><span data-stu-id="c710e-118">Click **Export**.</span></span>
5.  <span data-ttu-id="c710e-119">Adjon meg egy fájlnevet, és jelöljön ki egy biztonságos helyet, ahol menteni szeretné az exportált jelentésdefiníciókat.</span><span class="sxs-lookup"><span data-stu-id="c710e-119">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="c710e-120">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="c710e-120">Click **Save**.</span></span>

<span data-ttu-id="c710e-121">A fájl másolhatók, illetve feltölthető egy biztonságos helyre, hogy később importálható legyen egy másik környezetbe.</span><span class="sxs-lookup"><span data-stu-id="c710e-121">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="c710e-122">A Microsoft Azure tárolófiók használatával kapcsolatos információkért lásd: [Adatátvitel az AzCopy parancssori segédprogrammal](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="c710e-122">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="c710e-123">A Dynamics 365 for Finance and Operations megállapodás részeként a Microsoft nem biztosít tárolófiókot.</span><span class="sxs-lookup"><span data-stu-id="c710e-123">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="c710e-124">Be kell szereznie egy tárolófiókot, vagy egy külön Azure-előfizetésből származó tárolófiókot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="c710e-124">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="c710e-125">Legyen tisztában a D-meghajtó viselkedésével az Azure virtuális gépeken</span><span class="sxs-lookup"><span data-stu-id="c710e-125">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="c710e-126">Ne tárolja itt véglegesen az exportált építőelem-csoportokat.</span><span class="sxs-lookup"><span data-stu-id="c710e-126">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="c710e-127">További információt az ideiglenes meghajtókkal kapcsolatban itt talál: [A Windows Azure virtuális gépek ideiglenes meghajtóinak ismertetése](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="c710e-127">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="c710e-128">Szolgáltatások leállítása</span><span class="sxs-lookup"><span data-stu-id="c710e-128">Stop services</span></span>
<span data-ttu-id="c710e-129">A Távoli asztal segítségével csatlakozzon az összes számítógéphez a környezetében, és állítsa le a következő Windows-szolgáltatásokat a services.msc segítségével:</span><span class="sxs-lookup"><span data-stu-id="c710e-129">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="c710e-130">Webes közzétételi szolgáltatás (az összes AOS-számítógépen)</span><span class="sxs-lookup"><span data-stu-id="c710e-130">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="c710e-131">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="c710e-131">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="c710e-132">Management Reporter 2012 Process Service (csak a BI-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="c710e-132">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="c710e-133">Ezek a szolgáltatások nyitott kapcsolattal rendelkeznek a Dynamics 365 for Finance and Operations-adatbázissal.</span><span class="sxs-lookup"><span data-stu-id="c710e-133">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="c710e-134">Alaphelyzet</span><span class="sxs-lookup"><span data-stu-id="c710e-134">Reset</span></span>
#### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="c710e-135">Keresse meg és töltse le a legújabb MinorVersionDataUpgrade.zip csomagot</span><span class="sxs-lookup"><span data-stu-id="c710e-135">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="c710e-136">Keresse meg a legújabb MinorVersionDataUpgrade.zip csomagot a következő utasításokkal: [A legfrissebb adatok frissítési telepíthető csomag letöltése](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span><span class="sxs-lookup"><span data-stu-id="c710e-136">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span></span> <span data-ttu-id="c710e-137">Az utasítások ismertetik, hogyan keresse meg és töltse le az adatfrissítési csomag megfelelő verzióját.</span><span class="sxs-lookup"><span data-stu-id="c710e-137">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="c710e-138">A MinorVersionDataUpgrade.zip csomag letöltéséhez nincs szükség frissítésre.</span><span class="sxs-lookup"><span data-stu-id="c710e-138">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="c710e-139">A MinorVersionDataUpgrade.zip csomag másolatának visszaszerzéséhez végre kell hajtania „A legfrissebb adatok frissítési telepíthető csomag letöltése” rész lépéseit a többi lépés végrehajtása nélkül.</span><span class="sxs-lookup"><span data-stu-id="c710e-139">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

#### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="c710e-140">Parancsfájl-műveletek végrehajtása a Dynamics 365 for Finance and Operations adatbázison</span><span class="sxs-lookup"><span data-stu-id="c710e-140">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="c710e-141">Futtassa a következő parancsfájlokat a Dynamics 365 for Finance and Operations adatbázison (nem pénzügyi jelentési adatbázison).</span><span class="sxs-lookup"><span data-stu-id="c710e-141">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="c710e-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="c710e-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="c710e-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="c710e-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="c710e-144">Ezeket a parancsfájlok gondoskodnak arról, hogy helyesek legyenek a felhasználók, a szerepkörök és a változáskövetési beállítások.</span><span class="sxs-lookup"><span data-stu-id="c710e-144">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="c710e-145">Adatbázis alaphelyzetbe állításához PowerShell-parancs végrehajtása</span><span class="sxs-lookup"><span data-stu-id="c710e-145">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="c710e-146">Hajtsa végre a következő parancsot közvetlenül az AOS-számítógépen Dynamics 365 for Finance and Operations és a pénzügyi jelentéskészítés közti integráció alaphelyzetbe állításához:</span><span class="sxs-lookup"><span data-stu-id="c710e-146">Execute the following command, directly on the AOS computer, to reset the integration between Finance and Operations and financial reporting:</span></span>

1.  <span data-ttu-id="c710e-147">Nyissa meg a Windows PowerShell alkalmazást rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="c710e-147">Open Windows PowerShell as Administrator.</span></span>
2.  <span data-ttu-id="c710e-148">Hajtsa végre: F:</span><span class="sxs-lookup"><span data-stu-id="c710e-148">Execute: F:</span></span>
3.  <span data-ttu-id="c710e-149">Hajtsa végre: cd F:\\MRApplicationService\\MRInstallDirectory</span><span class="sxs-lookup"><span data-stu-id="c710e-149">Execute: cd F:\\MRApplicationService\\MRInstallDirectory</span></span>
4.  <span data-ttu-id="c710e-150">Hajtsa végre: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span><span class="sxs-lookup"><span data-stu-id="c710e-150">Execute: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span></span>
5.  <span data-ttu-id="c710e-151">Hajtsa végre: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;az ok, amiért alaphelyzetbe állítom&gt;”</span><span class="sxs-lookup"><span data-stu-id="c710e-151">Execute: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;my reason for resetting&gt;”</span></span>
    -   <span data-ttu-id="c710e-152">Adja meg az „Y”-t megerősítésként.</span><span class="sxs-lookup"><span data-stu-id="c710e-152">You will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="c710e-153">A paraméterek magyarázata:</span><span class="sxs-lookup"><span data-stu-id="c710e-153">Explanation of parameters:</span></span>

-   <span data-ttu-id="c710e-154">A -Reason érvényes értékei: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="c710e-154">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="c710e-155">A -ReasonDetail paraméter szabad szöveg.</span><span class="sxs-lookup"><span data-stu-id="c710e-155">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="c710e-156">A távmérő/környezet felügyelete végzi az ok és reasonDetail rögzítését.</span><span class="sxs-lookup"><span data-stu-id="c710e-156">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="c710e-157">Szolgáltatások indítása</span><span class="sxs-lookup"><span data-stu-id="c710e-157">Start services</span></span>
<span data-ttu-id="c710e-158">A korábban leállított szolgáltatások újraindításához használja a Services.msc parancsot:</span><span class="sxs-lookup"><span data-stu-id="c710e-158">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="c710e-159">Webes közzétételi szolgáltatás (az összes AOS-számítógépen)</span><span class="sxs-lookup"><span data-stu-id="c710e-159">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="c710e-160">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="c710e-160">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="c710e-161">Management Reporter 2012 Process Service (csak a BI-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="c710e-161">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="c710e-162">Jelentésdefiníciók importálása</span><span class="sxs-lookup"><span data-stu-id="c710e-162">Import report definitions</span></span>
<span data-ttu-id="c710e-163">Importálja a jelentésterveket a Jelentéstervezőből, az exportálás során létrehozott fájl használatával:</span><span class="sxs-lookup"><span data-stu-id="c710e-163">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="c710e-164">A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="c710e-164">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="c710e-165">Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c710e-165">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="c710e-166">A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.</span><span class="sxs-lookup"><span data-stu-id="c710e-166">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="c710e-167">Válassza ki az **Alapértelmezett** építőelemet, és kattintson az **Importálás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c710e-167">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="c710e-168">Válassza ki az exportált jelentésdefiníciókat tartalmazó fájlt, és kattintson a **Megnyitás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c710e-168">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="c710e-169">Jelölje ki az importálandó jelentésdefiníciókat az Importálás párbeszédpanelben:</span><span class="sxs-lookup"><span data-stu-id="c710e-169">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="c710e-170">Az összes jelentésdefiníció illetve az azt támogató építőelemek importálásához kattintson az **Összes kijelölése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c710e-170">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="c710e-171">Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.</span><span class="sxs-lookup"><span data-stu-id="c710e-171">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="c710e-172">Kattintson az **Importálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="c710e-172">Click **Import**.</span></span>






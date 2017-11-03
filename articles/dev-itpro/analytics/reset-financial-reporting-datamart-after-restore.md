---
title: "A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után"
description: "Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Finance and Operations adatbázis visszaállítása után."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e3f78fb2f6528449d2a411225cd0e14ca33443e
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="88265-103">A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után</span><span class="sxs-lookup"><span data-stu-id="88265-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="88265-104">Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Finance and Operations adatbázis visszaállítása után.</span><span class="sxs-lookup"><span data-stu-id="88265-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="88265-105">Ha bármikor visszaállítsa a Dynamics 365 for Operations adatbázist egy biztonsági másolatból, vagy másolja az adatbázist egy másik környezetből, biztosítania kell, hogy a pénzügyi jelentési adatpiac megfelelően használja a visszaállított 365 Dynamics for Finance and Operations adatbázist.</span><span class="sxs-lookup"><span data-stu-id="88265-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
> [!Note] 
> <span data-ttu-id="88265-106">A folyamat lépéseit a Dynamics 365 for Operations 2016 májusi kiadása támogatja (7.0.1265.23014 alkalmazásbild és 7.0.10000.4 pénzügyi jelentési build), valamint az újabb verziók.</span><span class="sxs-lookup"><span data-stu-id="88265-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="88265-107">Ha a Dynamics 365 for Finance and Operations egy korábbi verziójával rendelkezik, lépjen kapcsolatba támogatási csoportunkkal segítségért.</span><span class="sxs-lookup"><span data-stu-id="88265-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="88265-108">Jelentésdefiníciók exportálása</span><span class="sxs-lookup"><span data-stu-id="88265-108">Export report definitions</span></span>
<span data-ttu-id="88265-109">Először exportálja a Jelentéstervezőben található jelentésterveket, a következő lépések végrehajtásával:</span><span class="sxs-lookup"><span data-stu-id="88265-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="88265-110">A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="88265-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="88265-111">Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88265-111">Select the building block group to export, and click **Export**.</span></span> 

    > [!Note] 
    > <span data-ttu-id="88265-112">A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.</span><span class="sxs-lookup"><span data-stu-id="88265-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="88265-113">Válassza ki a jelentésdefiníciókat az exportáláshoz:</span><span class="sxs-lookup"><span data-stu-id="88265-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="88265-114">Az összes jelentésdefiníció illetve a társított építőelemek exportálásához kattintson az **Összes kijelölése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88265-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="88265-115">Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket.</span><span class="sxs-lookup"><span data-stu-id="88265-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="88265-116">Ha több tételt szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt. Ha jelentéseket jelöl ki az exportálásához, a rendszer a társított sorokat, oszlopokat, fákat és dimenziókészleteket is kijelöli.</span><span class="sxs-lookup"><span data-stu-id="88265-116">Press and hold the Ctrl key to select multiple items in a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="88265-117">Kattintson az **Exportálás** elemre.</span><span class="sxs-lookup"><span data-stu-id="88265-117">Click **Export**.</span></span>
5.  <span data-ttu-id="88265-118">Adjon meg egy fájlnevet, és jelöljön ki egy biztonságos helyet, ahol menteni szeretné az exportált jelentésdefiníciókat.</span><span class="sxs-lookup"><span data-stu-id="88265-118">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="88265-119">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="88265-119">Click **Save**.</span></span>

<span data-ttu-id="88265-120">A fájl másolhatók, illetve feltölthető egy biztonságos helyre, hogy később importálható legyen egy másik környezetbe.</span><span class="sxs-lookup"><span data-stu-id="88265-120">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="88265-121">A Microsoft Azure tárolófiók használatával kapcsolatos információkért lásd: [Adatátvitel az AzCopy parancssori segédprogrammal](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="88265-121">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="88265-122">A Dynamics 365 for Finance and Operations megállapodás részeként a Microsoft nem biztosít tárolófiókot.</span><span class="sxs-lookup"><span data-stu-id="88265-122">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="88265-123">Be kell szereznie egy tárolófiókot, vagy egy külön Azure-előfizetésből származó tárolófiókot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="88265-123">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="88265-124">Legyen tisztában a D-meghajtó viselkedésével az Azure virtuális gépeken</span><span class="sxs-lookup"><span data-stu-id="88265-124">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="88265-125">Ne tárolja itt véglegesen az exportált építőelem-csoportokat.</span><span class="sxs-lookup"><span data-stu-id="88265-125">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="88265-126">További információt az ideiglenes meghajtókkal kapcsolatban itt talál: [A Windows Azure virtuális gépek ideiglenes meghajtóinak ismertetése](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="88265-126">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="88265-127">Szolgáltatások leállítása</span><span class="sxs-lookup"><span data-stu-id="88265-127">Stop services</span></span>
<span data-ttu-id="88265-128">A Távoli asztal segítségével csatlakozzon az összes számítógéphez a környezetében, és állítsa le a következő Windows-szolgáltatásokat a services.msc segítségével:</span><span class="sxs-lookup"><span data-stu-id="88265-128">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="88265-129">Webes közzétételi szolgáltatás (az összes AOS-számítógépen)</span><span class="sxs-lookup"><span data-stu-id="88265-129">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="88265-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="88265-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="88265-131">Management Reporter 2012 Process Service (csak a BI-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="88265-131">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="88265-132">Ezek a szolgáltatások nyitott kapcsolattal rendelkeznek a Dynamics 365 for Finance and Operations-adatbázissal.</span><span class="sxs-lookup"><span data-stu-id="88265-132">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="88265-133">Alaphelyzet</span><span class="sxs-lookup"><span data-stu-id="88265-133">Reset</span></span>
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="88265-134">Keresse meg és töltse le a legújabb MinorVersionDataUpgrade.zip csomagot</span><span class="sxs-lookup"><span data-stu-id="88265-134">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="88265-135">Keresse meg a legújabb MinorVersionDataUpgrade.zip csomagot a következő utasításokkal: [A legfrissebb adatok frissítési telepíthető csomag letöltése](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="88265-135">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="88265-136">Az utasítások ismertetik, hogyan keresse meg és töltse le az adatfrissítési csomag megfelelő verzióját.</span><span class="sxs-lookup"><span data-stu-id="88265-136">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="88265-137">A MinorVersionDataUpgrade.zip csomag letöltéséhez nincs szükség frissítésre.</span><span class="sxs-lookup"><span data-stu-id="88265-137">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="88265-138">A MinorVersionDataUpgrade.zip csomag másolatának visszaszerzéséhez végre kell hajtania „A legfrissebb adatok frissítési telepíthető csomag letöltése” rész lépéseit a többi lépés végrehajtása nélkül.</span><span class="sxs-lookup"><span data-stu-id="88265-138">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="88265-139">Parancsfájl-műveletek végrehajtása a Dynamics 365 for Finance and Operations adatbázison</span><span class="sxs-lookup"><span data-stu-id="88265-139">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="88265-140">Futtassa a következő parancsfájlokat a Dynamics 365 for Finance and Operations adatbázison (nem pénzügyi jelentési adatbázison).</span><span class="sxs-lookup"><span data-stu-id="88265-140">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="88265-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="88265-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="88265-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="88265-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="88265-143">Ezeket a parancsfájlok gondoskodnak arról, hogy helyesek legyenek a felhasználók, a szerepkörök és a változáskövetési beállítások.</span><span class="sxs-lookup"><span data-stu-id="88265-143">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="88265-144">Adatbázis alaphelyzetbe állításához PowerShell-parancs végrehajtása</span><span class="sxs-lookup"><span data-stu-id="88265-144">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="88265-145">Az AOS-számítógépen a PowerShellben rendszergazdaként hajtsa végre a következő parancsot a Dynamics 365 for Finance and Operations és a pénzügyi jelentéskészítés közti integráció alaphelyzetbe állításához:</span><span class="sxs-lookup"><span data-stu-id="88265-145">On the AOS computer, execute the following commands in PowerShell as an Administrator to reset the integration between Finance and Operations and financial reporting:</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> <span data-ttu-id="88265-146">A parancsok végrehajtását követően adja meg az „Y”-t megerősítésként.</span><span class="sxs-lookup"><span data-stu-id="88265-146">After executing the commands, you will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="88265-147">A paraméterek magyarázata:</span><span class="sxs-lookup"><span data-stu-id="88265-147">Explanation of parameters:</span></span>

-   <span data-ttu-id="88265-148">A -Reason érvényes értékei: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="88265-148">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="88265-149">A -ReasonDetail paraméter szabad szöveg.</span><span class="sxs-lookup"><span data-stu-id="88265-149">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="88265-150">A távmérő/környezet felügyelete végzi az ok és reasonDetail rögzítését.</span><span class="sxs-lookup"><span data-stu-id="88265-150">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="88265-151">Szolgáltatások indítása</span><span class="sxs-lookup"><span data-stu-id="88265-151">Start services</span></span>
<span data-ttu-id="88265-152">A korábban leállított szolgáltatások újraindításához használja a Services.msc parancsot:</span><span class="sxs-lookup"><span data-stu-id="88265-152">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="88265-153">Webes közzétételi szolgáltatás (az összes AOS-számítógépen)</span><span class="sxs-lookup"><span data-stu-id="88265-153">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="88265-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="88265-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="88265-155">Management Reporter 2012 Process Service (csak a BI-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="88265-155">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="88265-156">Jelentésdefiníciók importálása</span><span class="sxs-lookup"><span data-stu-id="88265-156">Import report definitions</span></span>
<span data-ttu-id="88265-157">Importálja a jelentésterveket a Jelentéstervezőből, az exportálás során létrehozott fájl használatával:</span><span class="sxs-lookup"><span data-stu-id="88265-157">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="88265-158">A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="88265-158">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="88265-159">Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88265-159">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="88265-160">A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.</span><span class="sxs-lookup"><span data-stu-id="88265-160">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="88265-161">Válassza ki az **Alapértelmezett** építőelemet, és kattintson az **Importálás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88265-161">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="88265-162">Válassza ki az exportált jelentésdefiníciókat tartalmazó fájlt, és kattintson a **Megnyitás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88265-162">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="88265-163">Jelölje ki az importálandó jelentésdefiníciókat az Importálás párbeszédpanelben:</span><span class="sxs-lookup"><span data-stu-id="88265-163">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="88265-164">Az összes jelentésdefiníció illetve az azt támogató építőelemek importálásához kattintson az **Összes kijelölése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="88265-164">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="88265-165">Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.</span><span class="sxs-lookup"><span data-stu-id="88265-165">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="88265-166">Kattintson az **Importálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="88265-166">Click **Import**.</span></span>






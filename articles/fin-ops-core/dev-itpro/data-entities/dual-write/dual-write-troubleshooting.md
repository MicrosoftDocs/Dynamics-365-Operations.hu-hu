---
title: Általános hibaelhárítás
description: Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f7ee0b5aa4e72614205e129acd986376b33efc70
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172691"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="2e626-103">Általános hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="2e626-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="2e626-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2e626-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e626-105">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="2e626-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="2e626-106">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="2e626-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="2e626-107">Amikor a Package Deployer eszközzel próbálja meg telepíteni a kettős írású csomagot, nem jelennek meg a rendelkezésre álló megoldások</span><span class="sxs-lookup"><span data-stu-id="2e626-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="2e626-108">A Package Deployer eszköz egyes verziói nem kompatibilisek a kettős írású megoldáscsomaggal.</span><span class="sxs-lookup"><span data-stu-id="2e626-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="2e626-109">A csomag sikeres telepítéséhez győződjön meg arról, hogy a Package Deployer eszköz [9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) vagy újabb verzióját használja.</span><span class="sxs-lookup"><span data-stu-id="2e626-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="2e626-110">A Package Deployer eszköz telepítését követően telepítse a megoldást tartalmazó csomagot a következő lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="2e626-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="2e626-111">Töltse le a legújabb megoldáscsomag-fájlt a Yammer.com oldalról.</span><span class="sxs-lookup"><span data-stu-id="2e626-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="2e626-112">A csomag zip-fájljának letöltése után kattintson rá jobb gombbal, és válassza a **Tulajdonságok** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e626-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="2e626-113">Válassza ki a **Zárolás feloldása** jelölőnégyzetet, majd válassza az **Alkalmazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e626-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="2e626-114">Ha nem látja a **Zárolás feloldása** jelölőnégyzetet, akkor a zip-fájl zárolása már fel van oldva, és kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="2e626-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Tulajdonságok párbeszédpanel](media/unblock_option.png)

2. <span data-ttu-id="2e626-116">Csomagolja ki a csomag zip-fájlját, és másolja az összes fájlt a **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** mappába.</span><span class="sxs-lookup"><span data-stu-id="2e626-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![A Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438 mappa tartalma](media/extract_package.png)

3. <span data-ttu-id="2e626-118">Illessze be az összes másolt fájlt a Package Deployer eszköz **Eszközök** mappájába.</span><span class="sxs-lookup"><span data-stu-id="2e626-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="2e626-119">Futtassa a **PackageDeployer.exe** fájlt a Common Data Service-környezet kiválasztásához és a megoldások telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="2e626-119">Run **PackageDeployer.exe** to select the Common Data Service environment and install the solutions.</span></span>

    ![Az Eszközök mappa tartalma](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a><span data-ttu-id="2e626-121">A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Common Data Service szolgáltatásban a hiba részleteinek megtekintéséhez</span><span class="sxs-lookup"><span data-stu-id="2e626-121">Enable and view the plug-in trace log in Common Data Service to view error details</span></span>

<span data-ttu-id="2e626-122">**A nyomkövetési napló bekapcsolásához és a hibák megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="2e626-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="2e626-123">Ha be szeretné kapcsolni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2e626-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="2e626-124">Jelentkezzen be az Finance and Operations alkalmazásba, nyissa meg a **Beállítások** lapot, majd a **Rendszer** területen válassza a **Felügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e626-124">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="2e626-125">A **Felügyelet** oldalon válassza az **Rendszerbeállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e626-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="2e626-126">A **Testreszabás** lap **Beépülő modul és egyéni munkafolyamat tevékenységének nyomon követése** mezőjében válassza az **Összes** lehetőséget, ha engedélyezni szeretné a beépülő modul nyomkövetési naplóját.</span><span class="sxs-lookup"><span data-stu-id="2e626-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** field, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="2e626-127">Ha csak a kivételek bekövetkezésekor szeretné naplózni a nyomkövetési naplókat, akkor válassza ehelyett a **Kivétel** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e626-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="2e626-128">Ha meg szeretné tekinteni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="2e626-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="2e626-129">Jelentkezzen be az Finance and Operations alkalmazásba, nyissa meg a **Beállítások** lapot, majd a **Testreszabások** területen válassza a **Beépülő modul nyomkövetési naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e626-129">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="2e626-130">Keresse meg azokat a nyomkövetési naplókat, ahol a **Típus neve** mező értéke **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span><span class="sxs-lookup"><span data-stu-id="2e626-130">Find the trace logs where the **Type Name** field is set to **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span></span>
3. <span data-ttu-id="2e626-131">A teljes napló megjelenítéséhez kattintson duplán egy elemre, majd a **Végrehajtás** gyorslapján tekintse át az **Üzenetblokk** szövegét.</span><span class="sxs-lookup"><span data-stu-id="2e626-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="2e626-132">Hibakeresési mód engedélyezése az Finance and Operations alkalmazások élő szinkronizálási problémáinak elhárításához</span><span class="sxs-lookup"><span data-stu-id="2e626-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="2e626-133">**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="2e626-133">**Required role to view the errors:** System admin</span></span>

<span data-ttu-id="2e626-134">A Common Data Service alkalmazásból származó kettős írású hibák megjelenhetnek a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="2e626-134">Dual-write errors that originate in Common Data Service can appear in the Finance and Operations app.</span></span> <span data-ttu-id="2e626-135">Bizonyos esetekben a hibaüzenet teljes szövege nem érhető el, mivel az üzenet túl hosszú, vagy személyes azonosításra alkalmas adatokat (PII) tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2e626-135">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="2e626-136">A hibák részletes naplózását a következő lépések végrehajtásával kapcsolhatja be.</span><span class="sxs-lookup"><span data-stu-id="2e626-136">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="2e626-137">A Finance and Operations-alkalmazások minden projektkonfigurációjában van egy **IsDebugMode** tulajdonság a **DualWriteProjectConfiguration** entitásban.</span><span class="sxs-lookup"><span data-stu-id="2e626-137">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** entity.</span></span> <span data-ttu-id="2e626-138">Nyissaa meg a **DualWriteProjectConfiguration** entitást az Excel-bővítmény használatával.</span><span class="sxs-lookup"><span data-stu-id="2e626-138">Open the **DualWriteProjectConfiguration** entity by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="2e626-139">Az entitás megnyitásának egyszerű módja a **Tervező** mód bekapcsolása az Excel-bővítményben, majd adja hozzá a **DualWriteProjectConfigurationEntity** entitást a munkalaphoz.</span><span class="sxs-lookup"><span data-stu-id="2e626-139">An easy way to open the entity is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="2e626-140">További információért lásd: [Entitásadatok megnyitása az Excel programban, és frissítésük az Excel-bővítmény használatával](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="2e626-140">For more information, see [Open entity data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="2e626-141">Állítsa a projekt **IsDebugMode** tulajdonságát **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="2e626-141">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="2e626-142">Futtassa a hibákat létrehozó esetet.</span><span class="sxs-lookup"><span data-stu-id="2e626-142">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="2e626-143">A részletes naplók a DualWriteErrorLog táblában érhetők el.</span><span class="sxs-lookup"><span data-stu-id="2e626-143">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="2e626-144">Az adatoknak a tábla böngészőjében való kereséséhez használja a következő URL-címet (helyettesítse az **XXX** részt a megfelelő elemmel):</span><span class="sxs-lookup"><span data-stu-id="2e626-144">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="2e626-145">Szinkronizálási hibák keresése a Finance and Operations alkalmazás virtuális gépén</span><span class="sxs-lookup"><span data-stu-id="2e626-145">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="2e626-146">**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="2e626-146">**Required role to view the errors:** System admin</span></span>

1. <span data-ttu-id="2e626-147">Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="2e626-147">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="2e626-148">Nyissa meg azt az LCS-projektet, amelyhez kettős írású tesztelést szeretne végezni.</span><span class="sxs-lookup"><span data-stu-id="2e626-148">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="2e626-149">Válassza a **Felhőbeli környezetek** csempét.</span><span class="sxs-lookup"><span data-stu-id="2e626-149">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="2e626-150">A távoli asztal használatával jelentkezzen be a Finance and Operations-alkalmazás virtuális gépébe (VM).</span><span class="sxs-lookup"><span data-stu-id="2e626-150">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="2e626-151">Az LCS képernyőn látható helyi fiókot használja.</span><span class="sxs-lookup"><span data-stu-id="2e626-151">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="2e626-152">Nyissa meg az eseménynaplót.</span><span class="sxs-lookup"><span data-stu-id="2e626-152">Open Event viewer.</span></span>
6. <span data-ttu-id="2e626-153">Válassza az **Alkalmazás- és szolgáltatásnaplók \> Microsoft \> Dynamics \> AX-DualWriteSync \> Működő** részt.</span><span class="sxs-lookup"><span data-stu-id="2e626-153">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="2e626-154">A legutóbbi hibák listájának áttekintése.</span><span class="sxs-lookup"><span data-stu-id="2e626-154">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="2e626-155">A Common Data Service-környezet leválasztása és másik csatolása a Finance and Operations-alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="2e626-155">Unlink and link another Common Data Service environment from a Finance and Operations app</span></span>

<span data-ttu-id="2e626-156">**A környezet leválasztásához szükséges hitelesítő adatok:** Azure AD bérlői rendszergazda</span><span class="sxs-lookup"><span data-stu-id="2e626-156">**Required credentials to unlink the environment:** Azure AD tenant admin</span></span>

1. <span data-ttu-id="2e626-157">Bejelentkezés a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="2e626-157">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="2e626-158">Nyissa meg a **Munkaterületek \> Adatkezelés** pontot, és válassza a **Kettős írás** csempét.</span><span class="sxs-lookup"><span data-stu-id="2e626-158">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="2e626-159">Válassza ki az összes futó leképezést, és kattintson a **Leállítás** elemre.</span><span class="sxs-lookup"><span data-stu-id="2e626-159">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="2e626-160">Válassza a **Környezet leválasztása** elemet.</span><span class="sxs-lookup"><span data-stu-id="2e626-160">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="2e626-161">A művelet jóváhagyásához válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2e626-161">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="2e626-162">Ezután új környezet csatolható.</span><span class="sxs-lookup"><span data-stu-id="2e626-162">You can now link a new environment.</span></span>

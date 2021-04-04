---
title: Általános hibaelhárítás
description: Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 4b97fffce6d1c3ea143e0d8445769e794d0c46a4
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566100"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="47216-103">Általános hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="47216-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="47216-104">Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="47216-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47216-105">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="47216-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="47216-106">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="47216-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="47216-107">Amikor a Package Deployer eszközzel próbálja meg telepíteni a kettős írású csomagot, nem jelennek meg a rendelkezésre álló megoldások</span><span class="sxs-lookup"><span data-stu-id="47216-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="47216-108">A Package Deployer eszköz egyes verziói nem kompatibilisek a kettős írású megoldáscsomaggal.</span><span class="sxs-lookup"><span data-stu-id="47216-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="47216-109">A csomag sikeres telepítéséhez győződjön meg arról, hogy a Package Deployer eszköz [9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) vagy újabb verzióját használja.</span><span class="sxs-lookup"><span data-stu-id="47216-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="47216-110">A Package Deployer eszköz telepítését követően telepítse a megoldást tartalmazó csomagot a következő lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="47216-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="47216-111">Töltse le a legújabb megoldáscsomag-fájlt a Yammer.com oldalról.</span><span class="sxs-lookup"><span data-stu-id="47216-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="47216-112">A csomag zip-fájljának letöltése után kattintson rá jobb gombbal, és válassza a **Tulajdonságok** elemet.</span><span class="sxs-lookup"><span data-stu-id="47216-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="47216-113">Válassza ki a **Zárolás feloldása** jelölőnégyzetet, majd válassza az **Alkalmazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47216-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="47216-114">Ha nem látja a **Zárolás feloldása** jelölőnégyzetet, akkor a zip-fájl zárolása már fel van oldva, és kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="47216-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Tulajdonságok párbeszédpanel](media/unblock_option.png)

2. <span data-ttu-id="47216-116">Csomagolja ki a csomag zip-fájlját, és másolja az összes fájlt a **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** mappába.</span><span class="sxs-lookup"><span data-stu-id="47216-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![A Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438 mappa tartalma](media/extract_package.png)

3. <span data-ttu-id="47216-118">Illessze be az összes másolt fájlt a Package Deployer eszköz **Eszközök** mappájába.</span><span class="sxs-lookup"><span data-stu-id="47216-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="47216-119">Futtassa a **PackageDeployer.exe** fájlt a Dataverse-környezet kiválasztásához és a megoldások telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="47216-119">Run **PackageDeployer.exe** to select the Dataverse environment and install the solutions.</span></span>

    ![Az Eszközök mappa tartalma](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a><span data-ttu-id="47216-121">A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez</span><span class="sxs-lookup"><span data-stu-id="47216-121">Enable and view the plug-in trace log in Dataverse to view error details</span></span>

<span data-ttu-id="47216-122">**A nyomkövetési napló bekapcsolásához és a hibák megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="47216-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="47216-123">Ha be szeretné kapcsolni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="47216-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="47216-124">Jelentkezzen be az a modellel vezérelt alkalmazásba a Dynamics 365-ben, nyissa meg a **Beállítások** lapot, majd a **Rendszer** területen válassza a **Felügyelet** elemet.</span><span class="sxs-lookup"><span data-stu-id="47216-124">Sign in to the model-driven app in Dynamics 365, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="47216-125">A **Felügyelet** oldalon válassza az **Rendszerbeállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47216-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="47216-126">A **Testreszabás** lap **Beépülő modul és egyéni munkafolyamat tevékenységének nyomon követése** oszlopában válassza az **Összes** lehetőséget, ha engedélyezni szeretné a beépülő modul nyomkövetési naplóját.</span><span class="sxs-lookup"><span data-stu-id="47216-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** column, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="47216-127">Ha csak a kivételek bekövetkezésekor szeretné naplózni a nyomkövetési naplókat, akkor válassza ehelyett a **Kivétel** elemet.</span><span class="sxs-lookup"><span data-stu-id="47216-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="47216-128">Ha meg szeretné tekinteni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="47216-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="47216-129">Jelentkezzen be az a modellel vezérelt alkalmazásba a Dynamics 365-ben, nyissa meg a **Beállítások** lapot, majd a **Testreszabások** területen válassza a **Beépülő modul nyomkövetési naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="47216-129">Sign in to the model-driven app in Dynamics 365, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="47216-130">Keresse meg azokat a nyomkövetési naplókat, ahol a **Típus neve** oszlop értéke **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span><span class="sxs-lookup"><span data-stu-id="47216-130">Find the trace logs where the **Type Name** column is set to **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span></span>
3. <span data-ttu-id="47216-131">A teljes napló megjelenítéséhez kattintson duplán egy elemre, majd a **Végrehajtás** gyorslapján tekintse át az **Üzenetblokk** szövegét.</span><span class="sxs-lookup"><span data-stu-id="47216-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="47216-132">Hibakeresési mód engedélyezése az Finance and Operations alkalmazások élő szinkronizálási problémáinak elhárításához</span><span class="sxs-lookup"><span data-stu-id="47216-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="47216-133">**A hibák megtekintéséhez szükséges szerepkör:** a rendszeradminisztrátor A kettős írás hibák, amelyek származhatnak a Dataverse szolgáltatásból, megjelenhetnek a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="47216-133">**Required role to view the errors:** System admin Dual-write errors that originate in Dataverse can appear in the Finance and Operations app.</span></span> <span data-ttu-id="47216-134">Bizonyos esetekben a hibaüzenet teljes szövege nem érhető el, mivel az üzenet túl hosszú, vagy személyes azonosításra alkalmas adatokat (PII) tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="47216-134">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="47216-135">A hibák részletes naplózását a következő lépések végrehajtásával kapcsolhatja be.</span><span class="sxs-lookup"><span data-stu-id="47216-135">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="47216-136">A Finance and Operations-alkalmazások minden projektkonfigurációjában van egy **IsDebugMode** tulajdonság a **DualWriteProjectConfiguration** táblában.</span><span class="sxs-lookup"><span data-stu-id="47216-136">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** table.</span></span> <span data-ttu-id="47216-137">Nyissaa meg a **DualWriteProjectConfiguration** táblát az Excel-bővítmény használatával.</span><span class="sxs-lookup"><span data-stu-id="47216-137">Open the **DualWriteProjectConfiguration** table by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="47216-138">A tábla megnyitásának egyszerű módja a **Tervező** mód bekapcsolása az Excel-bővítményben, majd adja hozzá a **DualWriteProjectConfigurationEntity** entitást a munkalaphoz.</span><span class="sxs-lookup"><span data-stu-id="47216-138">An easy way to open the table is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="47216-139">További információért lásd: [Táblaadatok megnyitása az Excel programban, és frissítésük az Excel-bővítmény használatával](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="47216-139">For more information, see [Open table data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="47216-140">Állítsa a projekt **IsDebugMode** tulajdonságát **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="47216-140">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="47216-141">Futtassa a hibákat létrehozó esetet.</span><span class="sxs-lookup"><span data-stu-id="47216-141">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="47216-142">A részletes naplók a DualWriteErrorLog táblában érhetők el.</span><span class="sxs-lookup"><span data-stu-id="47216-142">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="47216-143">Az adatoknak a tábla böngészőjében való kereséséhez használja a következő URL-címet (helyettesítse az **XXX** részt a megfelelő elemmel):</span><span class="sxs-lookup"><span data-stu-id="47216-143">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="47216-144">Szinkronizálási hibák keresése a Finance and Operations alkalmazás virtuális gépén</span><span class="sxs-lookup"><span data-stu-id="47216-144">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="47216-145">**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="47216-145">**Required role to view the errors:** System administrator</span></span>

1. <span data-ttu-id="47216-146">Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="47216-146">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="47216-147">Nyissa meg azt az LCS-projektet, amelyhez kettős írású tesztelést szeretne végezni.</span><span class="sxs-lookup"><span data-stu-id="47216-147">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="47216-148">Válassza a **Felhőbeli környezetek** csempét.</span><span class="sxs-lookup"><span data-stu-id="47216-148">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="47216-149">A távoli asztal használatával jelentkezzen be a Finance and Operations-alkalmazás virtuális gépébe (VM).</span><span class="sxs-lookup"><span data-stu-id="47216-149">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="47216-150">Az LCS képernyőn látható helyi fiókot használja.</span><span class="sxs-lookup"><span data-stu-id="47216-150">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="47216-151">Nyissa meg az eseménynaplót.</span><span class="sxs-lookup"><span data-stu-id="47216-151">Open Event viewer.</span></span>
6. <span data-ttu-id="47216-152">Válassza az **Alkalmazás- és szolgáltatásnaplók \> Microsoft \> Dynamics \> AX-DualWriteSync \> Működő** részt.</span><span class="sxs-lookup"><span data-stu-id="47216-152">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="47216-153">A legutóbbi hibák listájának áttekintése.</span><span class="sxs-lookup"><span data-stu-id="47216-153">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="47216-154">A Dataverse-környezet leválasztása és másik csatolása a Finance and Operations-alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="47216-154">Unlink and link another Dataverse environment from a Finance and Operations app</span></span>

<span data-ttu-id="47216-155">**A környezet szétválasztásához szükséges szerepkör:** Rendszergazda vagy a Finance and Operations alkalmazásban vagy a Dataverse szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="47216-155">**Required role to unlink the environment:** System administrator for either Finance and Operations app or Dataverse.</span></span>

1. <span data-ttu-id="47216-156">Bejelentkezés a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="47216-156">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="47216-157">Nyissa meg a **Munkaterületek \> Adatkezelés** pontot, és válassza a **Kettős írás** csempét.</span><span class="sxs-lookup"><span data-stu-id="47216-157">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="47216-158">Válassza ki az összes futó leképezést, és kattintson a **Leállítás** elemre.</span><span class="sxs-lookup"><span data-stu-id="47216-158">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="47216-159">Válassza a **Környezet leválasztása** elemet.</span><span class="sxs-lookup"><span data-stu-id="47216-159">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="47216-160">A művelet jóváhagyásához válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47216-160">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="47216-161">Ezután új környezet csatolható.</span><span class="sxs-lookup"><span data-stu-id="47216-161">You can now link a new environment.</span></span>

## <a name="unable-to-view-the-sales-order-line-information-form"></a><span data-ttu-id="47216-162">Nem lehet megtekinteni az értékesítésirendelés-sor adatai képernyőt</span><span class="sxs-lookup"><span data-stu-id="47216-162">Unable to view the sales order line Information form</span></span> 

<span data-ttu-id="47216-163">Amikor értékesítési rendelést hoz létre a Dynamics 365 Sales modulban, akkor ha a **+ Termékek hozzáadása** gombra kattint, előfordulhat, hogy a rendszer átirányítja a Dynamics 365 Project Operations rendelési sor űrlapjára.</span><span class="sxs-lookup"><span data-stu-id="47216-163">When you create a sales order in Dynamics 365 Sales, clicking on **+ Add products** might redirect you to the Dynamics 365 Project Operations order line form.</span></span> <span data-ttu-id="47216-164">Az értékesítésirendelés-sor **adatainak** űrlapját nem lehet arról az űrlapról megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="47216-164">There is no way from that form to view the sales order line **Information** form.</span></span> <span data-ttu-id="47216-165">Az **adatok** beállítása nem jelenik meg a legördülő listában az **új rendelési sor** alatt.</span><span class="sxs-lookup"><span data-stu-id="47216-165">The option for **Information** does not appear in the dropdown below **New Order Line**.</span></span> <span data-ttu-id="47216-166">Ennek az az oka, hogy a Projektműveletek már telepítve van a környezetben.</span><span class="sxs-lookup"><span data-stu-id="47216-166">This happens because Project Operations has been installed in your environment.</span></span>

<span data-ttu-id="47216-167">Az **Adatok** űrlapbeállítás újbóli engedélyezéséhez kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="47216-167">To re-enable the **Information** form option, follow these steps:</span></span>
1. <span data-ttu-id="47216-168">Lépjen a **Rendeléssor** táblára.</span><span class="sxs-lookup"><span data-stu-id="47216-168">Navigate to the **Order Line** table.</span></span>
2. <span data-ttu-id="47216-169">Keresse meg az **Adatok** űrlapot az űrlapok csomópont alatt.</span><span class="sxs-lookup"><span data-stu-id="47216-169">Find the **Information** form under the forms node.</span></span> 
3. <span data-ttu-id="47216-170">Válassza ki az **Adatok** űrlapot, és kattintson a **Biztonsági szerepkörök engedélyezése** pontra.</span><span class="sxs-lookup"><span data-stu-id="47216-170">Select the **Information** form and click **Enable security roles**.</span></span> 
4. <span data-ttu-id="47216-171">Módosítsa a biztonsági beállítást: **Megjelenítés mindenkinek**.</span><span class="sxs-lookup"><span data-stu-id="47216-171">Change the security setting to **Display to everyone**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
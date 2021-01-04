---
title: A Regression Suite Automation Tool beállítása és telepítése oktatóanyag
description: Ez a témakör azt mutatja be, hogyan lehet beállítani és telepíteni a Regression Suite Automation Tool (RSAT) szolgáltatást.
author: robinarh
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 4757d506239e309dcbc3e181469b17e3286cc111
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4695115"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="ab1ea-103">A Regression Suite Automation Tool beállítása és telepítése oktatóanyag</span><span class="sxs-lookup"><span data-stu-id="ab1ea-103">Set up and install Regression suite automation tool tutorial</span></span>
<span data-ttu-id="ab1ea-104">Ez a témakör egy olyan oktatóanyag, amely segítséget nyújt a beállítások végrehajtásában, és az RSAT-tal, valamint a RSAT használatával kapcsolatos eszközökkel való megismerkedésben.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-104">This topic is a tutorial that helps you get setup and get started with RSAT and the tools associated with using RSAT.</span></span> 

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ab1ea-105">Az internetböngésző eszközeivel letöltheti és mentheti ezt a lapot PDF-formátumban.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-105">Use your internet browser tools to download and save this page in PDF format.</span></span> 

## <a name="key-concepts"></a><span data-ttu-id="ab1ea-106">Alapfogalmak</span><span class="sxs-lookup"><span data-stu-id="ab1ea-106">Key concepts</span></span>

- <span data-ttu-id="ab1ea-107">A Regression Suite Automation Tool (RSAT) eszközt támogató különböző alkalmazásokhoz szükséges telepítési és előfeltételként megadott beállítások megértése.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-107">Understand the installation and prerequisite setup that are required for the various applications that support Regression suite automation tool (RSAT).</span></span>
- <span data-ttu-id="ab1ea-108">Annak megértése, hogy a Feladatrögzítő funkciója a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásával és a Microsoft Azure DevOps szolgáltatással együtt lehetővé teszi a tesztesetek létrehozását, konfigurálását, futtatásáv, vizsgálatát és a róluk szóló jelentések készítését.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-108">Understand how the Task recorder feature, together with Microsoft Dynamics Lifecycle Services (LCS) and Microsoft Azure DevOps, let you create, configure, run, investigate, and report on test cases.</span></span>
- <span data-ttu-id="ab1ea-109">Funkcionális felhasználók bátorítása arra, hogy az üzleti feladatokat a Feladatrögzítővel rögzítsék a szolgáltatásban, majd a feladatrögzítéseket automatizált testek sorozatává alakítsák forráskód írása nélkül.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-109">Empower functional users to record business tasks by using Task recorder, and then convert the task recordings into a suite of automated tests, without having to write source code.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ab1ea-110">Előzetes feladatok</span><span class="sxs-lookup"><span data-stu-id="ab1ea-110">Before you begin</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ab1ea-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ab1ea-111">Prerequisites</span></span>

- <span data-ttu-id="ab1ea-112">Az oktatóanyaghoz olyan környezet szükséges, amely a Microsoft Dynamics 365 for Finance and Operations 10.0-s (2019. áprilisi) vagy újabb verzióját futtatja.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-112">An environment that runs Microsoft Dynamics 365 for Finance and Operations version 10.0 (April 2019) or later is required for this tutorial.</span></span> <span data-ttu-id="ab1ea-113">A Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 szolgáltatást használó ügyfelek számára a Platform update 20 (PU 20) vagy újabb verzió is támogatott.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-113">For customers who are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, Platform update 20 (PU20) or later is also supported.</span></span>
- <span data-ttu-id="ab1ea-114">A felhasználónak rendszergazdai jogosultsággal kell rendelkeznie a környezethez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-114">The user must have admin rights to the environment.</span></span>
- <span data-ttu-id="ab1ea-115">Rendelkeznie kell hozzáféréssel az ügyfél bérlői LCS-éhez és Azure DevOps szolgáltatásához (korábban Microsoft Visual Studio Team Services \[VSTS\] néven volt ismert).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-115">You must have access to the customer tenant LCS and Azure DevOps (previously known as Microsoft Visual Studio Team Services \[VSTS\]).</span></span>
- <span data-ttu-id="ab1ea-116">A tesztek létrehozásához és kezeléséhez a felhasználónak Azure DevOps Test Plans- vagy Test Manager-licenccel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-116">The user that is creating and managing tests suites must have an Azure DevOps Test Plans or Test Manager license.</span></span> <span data-ttu-id="ab1ea-117">A következő licencekkel szintén hozzáférést nyerhet a Test Plans felületéhez:</span><span class="sxs-lookup"><span data-stu-id="ab1ea-117">The following licenses will also give you access to Test Plans:</span></span>
    - <span data-ttu-id="ab1ea-118">Visual Studio Enterprise-licenc</span><span class="sxs-lookup"><span data-stu-id="ab1ea-118">Visual Studio Enterprise license</span></span>
    - <span data-ttu-id="ab1ea-119">Visual Studio Test Professional-licenc</span><span class="sxs-lookup"><span data-stu-id="ab1ea-119">Visual Studio Test Professional license</span></span>
    - <span data-ttu-id="ab1ea-120">MSDN platformok előfizetői licenc</span><span class="sxs-lookup"><span data-stu-id="ab1ea-120">MSDN Platforms subscriber license</span></span>
- <span data-ttu-id="ab1ea-121">Az RSAT szolgáltatásnak hozzá kell férnie a tesztkörnyezethez internetböngészőn keresztül.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-121">RSAT must have access to the test environment via a web browser.</span></span>
- <span data-ttu-id="ab1ea-122">A tesztparaméterek létrehozásához és szerkesztéséhez a Microsoft Excel alkalmazásnak telepítve kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-122">To generate and edit test parameters, you must have Microsoft Excel installed.</span></span>

## <a name="configure-azure-devops"></a><span data-ttu-id="ab1ea-123">Azure DevOps konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-123">Configure Azure DevOps</span></span>

### <a name="user-eligibility"></a><span data-ttu-id="ab1ea-124">Felhasználhatói jogosultság</span><span class="sxs-lookup"><span data-stu-id="ab1ea-124">User eligibility</span></span>

<span data-ttu-id="ab1ea-125">Győződjön meg arról, hogy létrehozták a felhasználót az Azure DevOps szolgáltatásban, és van egy előfizetési szintje, amely hozzáférést biztosít az Azure Test Plans szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-125">Make sure that the user is created in Azure DevOps and has a subscription level that provides access to Azure Test Plans.</span></span> <span data-ttu-id="ab1ea-126">Az Azure DevOps Test Plans-licenc csak akkor szükséges, ha a felhasználó teszteseteket fog létrehozni és kezelni (azaz nem minden RSAT-felhasználónak szükséges ez a licenc).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-126">An Azure DevOps Test Plans license is required only if the user will create and manage test cases (that is, not all RSAT users require this license).</span></span> <span data-ttu-id="ab1ea-127">A licenc követelményeivel kapcsolatos tudnivalókat lásd: [Licenckövetelmények](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-127">For information about the license requirements, see [License requirements](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span></span>

### <a name="create-a-new-azure-devops-project"></a><span data-ttu-id="ab1ea-128">Új Azure DevOps-projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-128">Create a new Azure DevOps project</span></span>
<span data-ttu-id="ab1ea-129">Az RSAT Azure Devops szolgáltatást használ a tesztesetek és tesztcsomag kezeléséhez, jelentéskészítéséhez és a tesztfuttatás eredményeinek vizsgálatához.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-129">RSAT uses Azure Devops for test case and test suite management, reporting, and investigating test run results.</span></span> 

> [!NOTE]
> <span data-ttu-id="ab1ea-130">Egy meglévő Azure DevOps-projekt használható.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-130">You can use an existing Azure DevOps project.</span></span> <span data-ttu-id="ab1ea-131">Ha azonban a meglévő Azure DevOps-projekt úgy van beállítva, hogy egyéni sablonnal rendelkezik, akkor egy „VSTS Sync Failure ” hibaüzenet jelenik meg, amikor a teszteseteket szinkronizálja az Üzletifolyamat-modellező (BPM) segítségével az Azure DevOps szolgáltatásba (lásd a következő szakaszt: [Szinkronizálás tesztelése a BPM-ből az Azure DevOps szolgáltatásba](#test-the-synchronization-from-bpm-to-azure-devops)).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-131">However, if your existing Azure DevOps project is set up so that it has a custom template, you will receive a "VSTS Sync Failure" error when you sync test cases from Business process modeler (BPM) to Azure DevOps (see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section).</span></span> <span data-ttu-id="ab1ea-132">Ha az egyéni sablonhoz a következő gyakorlati tanácsokat követték, akkor szinkronizálni lehet a teszteseteket az Azure DevOps szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-132">If the following best practices have been followed for the custom template, you will be able to sync the test cases to Azure DevOps.</span></span> <span data-ttu-id="ab1ea-133">(Ezek a gyakorlati tanácsok a hibaüzenetben láthatók.)</span><span class="sxs-lookup"><span data-stu-id="ab1ea-133">(These best practices are listed in the error message.)</span></span>

- <span data-ttu-id="ab1ea-134">Ne töröljön semmilyen munkaelemtípust vagy beépített mezőt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-134">Do not delete any work item types or out-of-the-box fields.</span></span>
- <span data-ttu-id="ab1ea-135">Ne törölje a munkaelemtípusok állapotát.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-135">Do not delete any state of a work item type.</span></span>
- <span data-ttu-id="ab1ea-136">Ne adjon kötelező mezőket a munkaelemtípusokhoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-136">Do not add any required fields to a work item type.</span></span>

![A gyakorlati tanácsok listáját tartalmazó hibaüzenet](./media/setup_rsa_tool_02.png)

<span data-ttu-id="ab1ea-138">Ha nem, akkor ehhez az oktatóanyaghoz javasoljuk, hogy hozzon létre egy új Azure DevOps-projektet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-138">Otherwise, for this tutorial, we recommend that you create a new Azure DevOps project.</span></span> <span data-ttu-id="ab1ea-139">További tudnivalókért lásd: [Felmerülő problémák a BPM egyéni Azure DevOps (VSTS) folyamatsablon segítségével történő szinkronizálása során](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-139">For more information, see [Issues when syncing to BPM using a custom Azure DevOps (VSTS) process template](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span></span>

1. <span data-ttu-id="ab1ea-140">Nyissa meg az Azure DevOps URL-címét (`https://dev.azure.com/<Azure DevOps Name>`).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-140">Open the Azure DevOps URL (`https://dev.azure.com/<Azure DevOps Name>`).</span></span>
2. <span data-ttu-id="ab1ea-141">Válassz a **Projekt létrehozása** lehetőséget az Azure DevOps oldal jobb felső sarkában.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-141">Select **Create project** in the upper-right corner of the Azure DevOps page.</span></span>

    ![Projekt létrehozása gomb](./media/setup_rsa_tool_03.png)

3. <span data-ttu-id="ab1ea-143">Töltse ki a következő mezőket, majd válassza a **Létrehozás** lehetőséget:</span><span class="sxs-lookup"><span data-stu-id="ab1ea-143">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="ab1ea-144">**Projekt neve**</span><span class="sxs-lookup"><span data-stu-id="ab1ea-144">**Project name**</span></span>
    - <span data-ttu-id="ab1ea-145">**Verziókövetés** – Válassza ki **Team Foundation Version Control** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-145">**Version control** – Select **Team Foundation Version Control**.</span></span> <span data-ttu-id="ab1ea-146">Ne feledje, hogy az alapértelmezett beállítás, **Git** nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-146">Note that the default option, **Git**, isn't supported.</span></span>
    - <span data-ttu-id="ab1ea-147">**Munkaelem-folyamat**</span><span class="sxs-lookup"><span data-stu-id="ab1ea-147">**Work item process**</span></span>

    ![Új projekt létrehozása párbeszédpanel](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a><span data-ttu-id="ab1ea-149">Személyes hozzáférési jogkivonat létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-149">Create a personal access token</span></span>

<span data-ttu-id="ab1ea-150">Ebben az oktatóanyagban az LCS Üzletifolyamat-modellező (BPM) szolgáltatással létrehoz egy teszteseteket tartalmazó tárat, és szinkronizálja a teszteseteket az Azure DevOps szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-150">In this tutorial, you will use the LCS Business Process Modeler (BPM) to create a test case library and synchronize your test cases with Azure DevOps.</span></span> <span data-ttu-id="ab1ea-151">A BPM Azure DevOps szolgáltatással való szinkronizálásához személyes hozzáférési jogkivonat szükséges.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-151">You will need a personal access token to sync BPM with Azure DevOps.</span></span>

1. <span data-ttu-id="ab1ea-152">Válassza ki a Azure DevOps-projekthez tartozó lap jobb felső sarkában látható profil ikont, majd válassza a **Biztonság** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-152">Select the profile icon in the upper-right corner of the page for your Azure DevOps project, and then select **Security**.</span></span>

    ![Biztonsági parancs](./media/setup_rsa_tool_05.png)

2. <span data-ttu-id="ab1ea-154">A bal oldali panelen a **Biztonság** részben válassza ki a **Személyes hozzáférési jogkivonat** pontot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-154">In the left pane, under **Security**, select **Personal access tokens**.</span></span> <span data-ttu-id="ab1ea-155">Majd válassza az **Új jogkivonat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-155">Then select **New Token**.</span></span>

    ![Új token gomb a felhasználói beállítások személyes hozzáférési jogkivonat lapján.](./media/setup_rsa_tool_06.png)

3. <span data-ttu-id="ab1ea-157">Töltse ki a következő mezőket, majd válassza a **Létrehozás** lehetőséget:</span><span class="sxs-lookup"><span data-stu-id="ab1ea-157">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="ab1ea-158">**Név**</span><span class="sxs-lookup"><span data-stu-id="ab1ea-158">**Name**</span></span>
    - <span data-ttu-id="ab1ea-159">**Lejárat (UTC)** – Válassza az **Egyénileg meghatározott** lehetőséget, majd a dátumválasztó segítségével válassza ki a legutóbbi elérhető dátumot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-159">**Expiration (UTC)** – Select **Custom defined**, and then use the date picker to select the last available date.</span></span>
    - <span data-ttu-id="ab1ea-160">**Hatókörök** – Válassza a **Teljes hozzáférés** beállítást.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-160">**Scopes** – Select the **Full access** option.</span></span>

    ![Új személyes hozzáférési token létrehozása párbeszédpanel](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > <span data-ttu-id="ab1ea-162">Jegyezze fel a létrehozott személyes hozzáférési jogkivonatot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-162">Make a note of the personal access token that is created.</span></span> <span data-ttu-id="ab1ea-163">A RSAT-konfiguráció beállítása után a későbbiekben szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-163">You will need it later when you set up the RSAT configuration.</span></span>

    ![Személyes hozzáférési jogkivonat](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a><span data-ttu-id="ab1ea-165">LCS-projekt konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-165">Configure the LCS project</span></span>

<span data-ttu-id="ab1ea-166">A tesztek alaptárához szüksége van egy Lifecycle Services (LCS) projektre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-166">You need a Lifecycle Services (LCS) project for your master test library.</span></span> <span data-ttu-id="ab1ea-167">Az LCS Üzletifolyamat-modellező (BPM) használatos alaptárként a tesztesetekhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-167">The LCS Business Process Modeler (BPM) is used as the master library for your test cases.</span></span> <span data-ttu-id="ab1ea-168">A BPM a teszttáraknak az LCS-projektekben történő kezelésére és terjesztésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-168">BPM is used to manage and distribute test libraries across LCS projects.</span></span> <span data-ttu-id="ab1ea-169">Például egy Microsoft partner vagy független szoftvergyártó (ISV) teszttárakat épít, azzal BPM-tárak formájában adja ki a teszteseteket.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-169">For example, a Microsoft partner or independent software vendor (ISV) building test libraries will release test cases in the form of BPM libraries.</span></span> <span data-ttu-id="ab1ea-170">A BPM esetében a teszteseteket az üzleti folyamatok szerint szervezik.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-170">In BPM, test cases are organized by business process.</span></span> <span data-ttu-id="ab1ea-171">A BPM nem határozza meg a végrehajtási sorrendet vagy a sikeres tesztek gyakoriságát.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-171">BPM doesn't define the execution order or frequency of your test pass.</span></span> <span data-ttu-id="ab1ea-172">Ezeket a részleteket az Azure DevOps szolgáltatásban kezelheti, ahogy a témakör későbbi részében le van írva.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-172">These details are managed in Azure DevOps, as described later in this topic.</span></span>  

<span data-ttu-id="ab1ea-173">A LCS-projekthez meglévő ügyfélvégrehajtás vagy Partner projekt használható.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-173">For your LCS project, you can use an existing customer implementation or partner project.</span></span>

### <a name="update-the-lcs-language"></a><span data-ttu-id="ab1ea-174">LCS-nyelv frissítése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-174">Update the LCS language</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ea-175">A felhasználói felületen (UI) az üzleti folyamatok helyes megjelenítéséhez az LCS preferált nyelvét **Angol (Egyesült Államok)** értékre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-175">For the user interface (UI) to correctly show business processes, the LCS preferred language must be set to **English (United States)**.</span></span>

1. <span data-ttu-id="ab1ea-176">Lépjen az LCS végrehajtási projekthez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-176">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="ab1ea-177">Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum) a lap jobb felső sarkában, majd válassza a **Nyelvi preferencia** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-177">Select the **Settings** button (the gear symbol) in the upper-right corner, and then select **Language preference**.</span></span>

    ![Parancsok a Beállítások menüben](./media/setup_rsa_tool_09.png)

3. <span data-ttu-id="ab1ea-179">A **Preferált nyelv** mezőben válassza az **Angol (Egyesült Államok)** lehetőséget, majd a **Mentés** gombot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-179">In the **Preferred language** field, select **English (United States)**, and then select **Save**.</span></span>

    ![Felhasználói beállítások nyelvi preferencia lapja](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a><span data-ttu-id="ab1ea-181">Az LCS konfigurálása a Azure DevOps-projekthez való kapcsolódáshoz</span><span class="sxs-lookup"><span data-stu-id="ab1ea-181">Configure LCS to connect to the Azure DevOps project</span></span>

<span data-ttu-id="ab1ea-182">Ha korábban létrehozott egy új Azure DevOps-projektet, konfigurálja az LCS-projektet, hogy csatlakozhasson hozzá.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-182">If you created a new Azure DevOps project earlier, configure the LCS project to connect to it.</span></span> <span data-ttu-id="ab1ea-183">Ellenkező esetben, ha az LCS-projekt már csatlakozott az Azure DevOps-projekthez, folytathatja a következő szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-183">Otherwise, if your LCS project is already connected to your Azure DevOps project, you can continue to the next section.</span></span>

1. <span data-ttu-id="ab1ea-184">Lépjen az LCS végrehajtási projekthez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-184">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="ab1ea-185">Válassza a **Menü** gombot, majd válassza ki **Projektbeállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-185">Select the **Menu** button, and then select **Project settings**.</span></span>

    ![Projektbeállítások parancs](./media/setup_rsa_tool_11.png)

3. <span data-ttu-id="ab1ea-187">A bal oldali ablaktáblán válassza **Visual Studio Team Services** elemet, majd a **Visual Studio Team Services beállítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-187">In the left pane, select **Visual Studio Team Services**, and then select **Setup Visual Studio Team Services**.</span></span>

    ![A Visual Studio Team Services lap a projektbeállításokban](./media/setup_rsa_tool_12.png)

4. <span data-ttu-id="ab1ea-189">Az **Azure DevOps webhely URL-címe** mezőbe írja be az Azure DevOps-webhely URL-címét.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-189">In the **Azure DevOps site URL** field, enter the URL of the Azure DevOps site.</span></span> <span data-ttu-id="ab1ea-190">A **Személyes hozzáférési token** mezőbe írja be a korábban létrehozott személyes hozzáférési tokent.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-190">In the **Personal access token** field, enter the personal access token that was created earlier.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-191">Bár a VSTS mára úgy ismert, hogy Azure DevOps, az LCS Azure DevOps-projekthez csatlakoztatásához használja a régi URL-címet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-191">Although VSTS is now known as Azure DevOps, to connect LCS to your Azure DevOps project, use the old URL.</span></span> <span data-ttu-id="ab1ea-192">Például a Azure DevOps URL-cím, amelyet az oktatóanyagban használunk: `https://dev.azure.com/D365FOFastTrack/`.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-192">For example, the Azure DevOps URL that is used in this tutorial is `https://dev.azure.com/D365FOFastTrack/`.</span></span> <span data-ttu-id="ab1ea-193">A következő ábrán azonban így van beírva: `https://D365FOFastTrack.visualstudio.com/`.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-193">However, in the following illustration, it's entered as `https://D365FOFastTrack.visualstudio.com/`.</span></span>

    ![1. lépés a Visual Studio Team Services beállításaiban](./media/setup_rsa_tool_13.png)

5. <span data-ttu-id="ab1ea-195">Válassza **Folytatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-195">Select **Continue**.</span></span>
6. <span data-ttu-id="ab1ea-196">A **Visual Studio Team Services-projekt** mezőben válassza a kiválasztott webhelyen a VSTS-projektet, hogy összekapcsolja az LCS-projekttel.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-196">In the **Visual Studio Team Services project** field, select the VSTS project on the selected site to link with the LCS project.</span></span> <span data-ttu-id="ab1ea-197">A **Feldolgozási sablon** mező értéke alapértelmezés szerinti értéke **Agilis**.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-197">The **Process template** field is set to **Agile** by default.</span></span> <span data-ttu-id="ab1ea-198">Egy egyéni sablon esetében tekintse át az [Új Azure DevOps-projekt létrehozása](#create-a-new-azure-devops-project) szakasz gyakorlati tanácsokat tartalmazó útmutatóját.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-198">For a custom template, review the best practice guidance in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span> <span data-ttu-id="ab1ea-199">Válassza **Folytatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-199">Then select **Continue**.</span></span>

    ![2. lépés a Visual Studio Team Services beállításaiban](./media/setup_rsa_tool_14.png)

7. <span data-ttu-id="ab1ea-201">Ellenőrizze a beállításokat, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-201">Review your settings, and then select **Save**.</span></span>

    ![3. lépés a Visual Studio Team Services beállításaiban](./media/setup_rsa_tool_15.png)

8. <span data-ttu-id="ab1ea-203">Válassza az **Engedélyezés** lehetőséget, ha engedélyezni szeretné az LCS számára a konfigurált Azure DevOps-webhelyhez az Ön nevében való hozzáférést, és a VSTS-sel integráló funkciók bekapcsolását.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-203">Select **Authorize** to authorize LCS to access the configured Azure DevOps site on your behalf and to turn on features that integrate with VSTS.</span></span>

    ![Engedélyezés gomb](./media/setup_rsa_tool_16.png)

9. <span data-ttu-id="ab1ea-205">Megjelenik egy üzenetablak: „A rendszer átirányítja Önt egy külső webhelyre, ahol engedélyezheti a LCS számára, hogy az Ön nevében csatlakozzon a Visual Studio Team Services rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-205">A message box appears that states, "You are about to be redirected to an eternal site to authorize LCS to connect to Visual Studio Team Services on your behalf.</span></span> <span data-ttu-id="ab1ea-206">Folytatja?”</span><span class="sxs-lookup"><span data-stu-id="ab1ea-206">Proceed?"</span></span> <span data-ttu-id="ab1ea-207">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-207">Select **Yes**.</span></span>

    ![Üzenetpanel](./media/setup_rsa_tool_17.png)

10. <span data-ttu-id="ab1ea-209">Válassza az **Elfogadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-209">Select **Accept**.</span></span>

    ![Hozzáférés engedélyezése](./media/setup_rsa_tool_18.png)

11. <span data-ttu-id="ab1ea-211">Ha felhasználóként engedélyezve van, akkor a felhasználói felületnek vissza kell térnie az LCS projekt beállításai lapra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-211">If you're authorized as a user, the UI should you return to the LCS project settings page.</span></span>

    ![Jogosult felhasználó](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a><span data-ttu-id="ab1ea-213">Új BPM-tár létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-213">Create a new BPM library</span></span>

1. <span data-ttu-id="ab1ea-214">Lépjen az LCS végrehajtási projekthez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-214">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="ab1ea-215">Válassza a **Menü** gombot, majd válassza ki **Üzletifolyamat-modellező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-215">Select the **Menu** button, and then select **Business process modeler**.</span></span>

    ![Üzletifolyamat-modellező parancs](./media/setup_rsa_tool_20.png)

3. <span data-ttu-id="ab1ea-217">Válassza az **Új tár** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-217">Select **New library**.</span></span>

    ![Új tár gomb](./media/setup_rsa_tool_21.png)

4. <span data-ttu-id="ab1ea-219">A **Tár neve** mezőbe írjon be egy nevet, majd válassza a **Létrehozás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-219">In the **Library name** field, enter a name, and then select **Create**.</span></span> <span data-ttu-id="ab1ea-220">Ehhez az oktatóanyaghoz nevezze el a BPM-tárat **RSAT** névre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-220">For this tutorial, name the BPM library **RSAT**.</span></span>

    ![Új tár létrehozása párbeszédpanel](./media/setup_rsa_tool_22.png)

5. <span data-ttu-id="ab1ea-222">Nyissa meg az új **RSAT** BPM-tárat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-222">Open the new **RSAT** BPM library.</span></span>
6. <span data-ttu-id="ab1ea-223">Válassza ki az **Minta alapvető üzleti folyamat** folyamatot, majd a jobb oldalon a **Szerkesztési mód** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-223">Select the **Sample Core Business Process** process, and then, on the right, select **Edit mode**.</span></span>

    ![Szerkesztési mód gomb](./media/setup_rsa_tool_23.png)

7. <span data-ttu-id="ab1ea-225">A **Név** és a **Leírás** mező értékét módosítsa **Termék létrehozása** értékre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-225">Change the value of both the **Name** field and the **Description** field to **Create a product**.</span></span> <span data-ttu-id="ab1ea-226">Majd válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-226">Then select **Save**.</span></span>

    ![Név és leírás mezők](./media/setup_rsa_tool_24.png)

## <a name="environment"></a><span data-ttu-id="ab1ea-228">Környezet</span><span class="sxs-lookup"><span data-stu-id="ab1ea-228">Environment</span></span>

### <a name="version-requirement"></a><span data-ttu-id="ab1ea-229">Verziókövetelmények</span><span class="sxs-lookup"><span data-stu-id="ab1ea-229">Version requirement</span></span>

<span data-ttu-id="ab1ea-230">10-es verziót futtató tesztkörnyezet szükséges.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-230">A test or sandbox environment that runs version 10 is required.</span></span> <span data-ttu-id="ab1ea-231">A 7.3-as verziót használó ügyfelek számára a Platform update 20 vagy újabb verzió is támogatott.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-231">For customers that are using version 7.3, Platform update 20 or later is also supported.</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ea-232">Az RSAT szolgáltatásnak hozzá kell férnie a tesztkörnyezetéhez internetböngészőn keresztül.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-232">RSAT must have access to your test environment via a web browser.</span></span>

### <a name="user-criteria"></a><span data-ttu-id="ab1ea-233">Felhasználói feltételek</span><span class="sxs-lookup"><span data-stu-id="ab1ea-233">User criteria</span></span>

<span data-ttu-id="ab1ea-234">A felhasználónak rendszergazdai jogosultsággal kell rendelkeznie ehhez a környezethez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-234">The user must have admin rights to this environment.</span></span>

### <a name="set-up-help-settings-to-connect-with-lcs"></a><span data-ttu-id="ab1ea-235">Adja meg az LCS-kapcsolathoz tartozó súgóbeállításokat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-235">Set up Help settings to connect with LCS</span></span>

<span data-ttu-id="ab1ea-236">Ezt a lépést szükséges megtenni annak érdekében, hogy csatlakozhasson az LCS-hez, így a feladatrögzítéseket az LCS megfelelő BPM-tárába tudja menteni a kliensen keresztül.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-236">This step is required in order to connect with LCS so that task recordings can be saved to the appropriate BPM library in LCS through the client.</span></span>

1. <span data-ttu-id="ab1ea-237">Nyissa meg az ügyfélprogramot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-237">Open the client.</span></span>
2. <span data-ttu-id="ab1ea-238">Lépjen a **Rendszerfelügyelet \> Beállítás \> Rendszerparaméterek** elemre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-238">Go to **System Administration \> Setup \> System parameters**.</span></span>
3. <span data-ttu-id="ab1ea-239">A **Súgó** lap **Lifecycle Services súgókonfiguráció** mezőjében válassza a releváns LCS-projektet (**RSAT** ehhez az oktatóanyaghoz).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-239">On the **Help** tab, in the **Lifecycle Services help configuration** field, select the relevant LCS project (**RSAT** for this tutorial).</span></span>

    ![A Lifecycle Services súgókonfiguráció mezője a Súgó lapon](./media/setup_rsa_tool_25.png)

    <span data-ttu-id="ab1ea-241">A BPM-tárak a megfelelő LCS-projektben kerülnek kitöltésre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-241">BPM libraries are filled in under the appropriate LCS project.</span></span>

4. <span data-ttu-id="ab1ea-242">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-242">Select **Save**.</span></span>
5. <span data-ttu-id="ab1ea-243">A frissített súgótartalom megtekintéséhez előfordulhat, hogy frissíteni kell a böngészőt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-243">You might have to refresh the browser to see the updated Help content.</span></span>

    ![Értesítés a böngésző frissítéséről](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a><span data-ttu-id="ab1ea-245">Feladatrögzítések</span><span class="sxs-lookup"><span data-stu-id="ab1ea-245">Task recordings</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ea-246">Győződjön meg róla, hogy az összes feladatrögzítés a fő irányítópulton kezdődik.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-246">Make sure that all your task recordings start on the main dashboard.</span></span> <span data-ttu-id="ab1ea-247">Az egyes rögzítések legyenek rövidek és egy üzleti feladatra koncentráljanak, például egy értékesítési rendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-247">Keep individual recordings short, and focus on one business task, such as creating a sales order.</span></span>

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a><span data-ttu-id="ab1ea-248">Feladatrögzítés létrehozása és BPM-tárba mentése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-248">Create a task recording and save it to the BPM library</span></span>

<span data-ttu-id="ab1ea-249">Hozzon létre egy megfelelő feladatrögzítést, amely az új BPM-tárban létrehozott egyszerű üzleti folyamathoz kapcsolható.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-249">Create a corresponding task recording that you can attach to the simple business process that was created in the new BPM library.</span></span>

1. <span data-ttu-id="ab1ea-250">Nyissa meg az ügyfélprogramot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-250">Open the client.</span></span>
2. <span data-ttu-id="ab1ea-251">Válassza ki a fő irányítópulton a **Beállítások** gombot (a fogaskerék szimbólumát), majd válassza ki a **Feladatrögzítőt**.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-251">On the main dashboard, select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>

    ![Parancsok a Beállítások menüben](./media/setup_rsa_tool_27.png)

3. <span data-ttu-id="ab1ea-253">Válassza a **Rögzítés létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-253">Select **Create recording**.</span></span>

    ![Rögzítés létrehozása gomb](./media/setup_rsa_tool_28.png)

4. <span data-ttu-id="ab1ea-255">Töltse ki a **Rögzítés neve** és **Rögzítés leírása** mezőket, majd válassza az **Indítás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-255">Fill in the **Recording name** and **Recording description** fields, and then select **Start**.</span></span>

    ![Rögzítés neve és Rögzítés leírása mezők](./media/setup_rsa_tool_29.png)

5. <span data-ttu-id="ab1ea-257">Rögzítse a termék létrehozásához szükséges lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-257">Record the steps for creating a product.</span></span> <span data-ttu-id="ab1ea-258">Ha befejezte, **Leállítás** paranccsal leállíthatja a rögzítést.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-258">When you've finished, select **Stop** to stop recording.</span></span>

    ![A termék létrehozásának lépései](./media/setup_rsa_tool_30.png)

6. <span data-ttu-id="ab1ea-260">Válassza a **Mentés a Lifecycle Services szolgáltatásba** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-260">Select **Save to Lifecycle Services**.</span></span>

    ![Mentési beállítások](./media/setup_rsa_tool_31.png)

    <span data-ttu-id="ab1ea-262">A tár adatait a rendszer az LCS-ből tölti be.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-262">Library information is loaded from LCS.</span></span>

    ![Folyamatjelző](./media/setup_rsa_tool_32.png)

7. <span data-ttu-id="ab1ea-264">Válassza ki a feladatrögzítéshez társítandó BPM-tárat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-264">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="ab1ea-265">Ehhez az oktatóanyaghoz válassza ki a korábban létrehozott **RSAT** BPM-tárat, és az alatta lévő **termék létrehozása** üzleti folyamatot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-265">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Create a product** business process under it.</span></span> <span data-ttu-id="ab1ea-266">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-266">Then select **OK**.</span></span>

    ![A feladatrögzítés társítása egy BPM-könyvtárral és egy üzleti folyamattal](./media/setup_rsa_tool_33.png)

    <span data-ttu-id="ab1ea-268">A „mentés a Lifecycle Services szolgáltatásba sikeresen megtörtént” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-268">A "Saving to Lifecycle Services was successful" message appears.</span></span>

    ![Üzenet az LCS-re történt sikeres mentésről](./media/setup_rsa_tool_34.png)

8. <span data-ttu-id="ab1ea-270">Ha azt szeretné, hogy a feladat rögzítése helyileg történjen, és utána töltse fel a BPM-tárba az LCS-en keresztül, hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="ab1ea-270">If you want to save the task recording locally and then upload it to BPM through LCS, follow these steps:</span></span>

    1. <span data-ttu-id="ab1ea-271">A rögzítés befejezése után válassza a **Mentés erre a számítógépre** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-271">After the recording is completed, select **Save to this PC**.</span></span>

        ![Mentési beállítások](./media/setup_rsa_tool_35.png)

    2. <span data-ttu-id="ab1ea-273">A böngésző értesítési sávján válassza a **Mentés** vagy a **Mentés másként** parancsot, ha menteni szeretné a fájlokat a helyi számítógépen.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-273">In the browser's Notification bar, select **Save** or **Save As** to save the file on your local computer.</span></span>

        ![Értesítési sáv](./media/setup_rsa_tool_36.png)

    3. <span data-ttu-id="ab1ea-275">Nyissa meg a **RSAT** BPM-tárat, és válassza ki azt az üzleti folyamatot, amellyel menteni szeretné a feladatrögzítést.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-275">Go to the **RSAT** BPM library, and select the business process to save the task recording against.</span></span>
    4. <span data-ttu-id="ab1ea-276">Az **Áttekintés** lapon válassza a **feltöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-276">On the **Overview** tab, select **Upload**.</span></span>

        ![Feltöltés gomb](./media/setup_rsa_tool_37.png)

    5. <span data-ttu-id="ab1ea-278">Válassza a **Tallózás** lehetőséget, majd válassza ki a korábban mentett .axtr-fájltípust.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-278">Select **Browse**, and select the .axtr file that you saved earlier.</span></span> <span data-ttu-id="ab1ea-279">Ezután válassza a **feltöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-279">Then select **Upload**.</span></span>

        ![A feltölteni kívánt .axtr-fájl kiválasztása](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a><span data-ttu-id="ab1ea-281">A BPM-ről Azure DevOps szolgáltatásba történő szinkronizálás tesztelése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-281">Test the synchronization from BPM to Azure DevOps</span></span>

<span data-ttu-id="ab1ea-282">Miután az üzleti folyamathoz csatolt egy feladatrögzítést, ellenőriznie kell, hogy az üzleti folyamat és a társított feladatrögzítés funkcióként és tesztesetként (adott esetben) szinkronizálható-e az Azure DevOps szolgáltatásba a VSTS szinkronizálási funkciónak a LCS modulban való használatával.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-282">Now that a task recording is attached to the business process, you must validate that the business process and the associated task recording can be synced to Azure DevOps as a feature and a test case (respectively) by using the VSTS sync feature in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ea-283">Az Azure DevOps szolgáltatásban létrehozott kapcsolódó munkaelemtípus változhat, az LCS-projekt Azure DevOps-szolgáltatással való konfigurálása során kiválasztott folyamatsablontól függően, az [Új Azure DevOps-projekt létrehozása](#create-a-new-azure-devops-project) szakaszban leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-283">The corresponding work item type that is created in Azure DevOps will vary, depending on the process template that you selected when you configured the LCS project with Azure DevOps, as described in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span>

1. <span data-ttu-id="ab1ea-284">Nyissa meg a BPM-tárat, és nyissa meg a korábban létrehozott **RSAT**-tárat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-284">Go to the BPM library, and open the **RSAT** library that you created earlier.</span></span>
2. <span data-ttu-id="ab1ea-285">Válassza ki a három pont gombot(**...**), és válassza a **vsts szinkronizálás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-285">Select the ellipsis button (**...**), and select **VSTS sync**.</span></span>

    ![VSTS szinkronizálás parancs a három pont menün](./media/setup_rsa_tool_39.png)

    <span data-ttu-id="ab1ea-287">A VSTS szinkronizálásának befejezése után megjelenik a **Követelmények** lap a bal oldalon, amely a megfelelő Azure DevOps-munkaelemet tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-287">After VSTS sync is completed, a **Requirements** tab appears on the left side and includes the corresponding Azure DevOps work item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-288">Az Azure DevOps szolgáltatásban létrehozott munkatételnek a BPM-tár nevének kell lennie a cím előtagjának.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-288">The work item that is created in Azure DevOps will have the BPM library name as the title prefix.</span></span>

    ![Követelmények lap](./media/setup_rsa_tool_40.png)

3. <span data-ttu-id="ab1ea-290">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="ab1ea-290">Refresh the page.</span></span>
4. <span data-ttu-id="ab1ea-291">Válassza ki a három pont gombot(**...**). További beállítást, a **Tesztesetek szinkronizálása** fog látni.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-291">Select the ellipsis button (**...**). You will see an additional option, **Sync test cases**.</span></span> <span data-ttu-id="ab1ea-292">Válassza ki ezt a lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-292">Select this option.</span></span>

    ![Tesztesetek szinkronizálása parancs a három pont menün](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > <span data-ttu-id="ab1ea-294">Ha a **Tesztesetek szinkronizálása** beállítás nem érhető el a lap frissítése után, nyissa meg a BPM főoldalát, és válassza a **Tesztesetek szinkronizálása** lehetőséget a teljes könyvtárhoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-294">If the **Sync test cases** option isn't available after you refresh the page, go to main page for BPM, and select **Sync test cases** for the whole library itself.</span></span> <span data-ttu-id="ab1ea-295">Ily módon gyakorlatilag egy szinkronizálást hajthat végre az egész könyvtárhoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-295">In this way, you effectively force a synchronization for the whole library.</span></span>
    > 
    > ![A Tesztesetek szinkronizálása kiválasztása az egész könyvtárhoz](./media/setup_rsa_tool_42.png)

    <span data-ttu-id="ab1ea-297">A Tesztesetek szinkronizálását követően létrejön egy új tesztelési eset a **Követelmények** lapon.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-297">After Sync test cases is completed, a new test case is created on the **Requirements** tab.</span></span>

    ![Új teszteset a követelmények lapon](./media/setup_rsa_tool_43.png)

5. <span data-ttu-id="ab1ea-299">Nyissa meg az Azure DevOps-projektet, és válassza a **Táblák \> Munkaelemek** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-299">Go to your Azure DevOps project, and select **Boards \> Work Items**.</span></span>

    ![Munkaelemek parancs a Táblák alatt](./media/setup_rsa_tool_44.png)

6. <span data-ttu-id="ab1ea-301">Ellenőrizze, hogy létezik-e a BPM-szinkronizálással létrehozott munkaelem és a teszteset.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-301">Validate that the work item and test case that you created through BPM synchronization exist.</span></span>

    ![Munkaelem és teszteset](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a><span data-ttu-id="ab1ea-303">Az RSAT konfigurálása és telepítése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-303">Install and Configure RSAT</span></span>

<span data-ttu-id="ab1ea-304">Az RSAT minden olyan számítógépre telepíthető, amelyen fut a Windows 10, és amely webböngészőn (Internet Explorer vagy Google Chrome) keresztül csatlakozhat a környezethez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-304">RSAT can be installed on any computer that runs Windows 10 and that can connect to the environment via a web browser (Internet Explorer or Google Chrome).</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ea-305">Az eszköz új verziójának telepítése előtt ajánlott eltávolítani a korábbi verziót.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-305">Before you install a new version of the tool, we recommend that you uninstall the previous version.</span></span>

### <a name="install-an-authentication-certificate"></a><span data-ttu-id="ab1ea-306">Hitelesítési tanúsítvány telepítése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-306">Install an authentication certificate</span></span>

<span data-ttu-id="ab1ea-307">Ha engedélyezni szeretné a hitelesítést, akkor ugyanazon a számítógépen kell létrehoznia és telepítenie a tanúsítványt, amelyen az RSAT fut.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-307">To enable authentication, you must generate and install a certificate on the same computer that RSAT is running on.</span></span>

#### <a name="generate-a-certificate"></a><span data-ttu-id="ab1ea-308">Tanúsítvány létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-308">Generate a certificate</span></span>

1. <span data-ttu-id="ab1ea-309">A tanúsítványfájl létrehozásához nyissa meg a Microsoft Windows PowerShell ablakát rendszergazdaként, majd futtassa a következő parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-309">To generate a certificate file, open a Microsoft Windows PowerShell window as an admin, and run the following command.</span></span>

    ```
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. <span data-ttu-id="ab1ea-310">A Tanúsítványkezelő megnyitásához adja meg a **certlm.msc** parancsot a **Futtatás** párbeszédpanelen, és győződjön meg arról, hogy a **D365 automatikus teszttanúsítványa** a **Személyes \> Tanúsítványok** szakaszban létrejött.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-310">Open certificate manager by entering **certlm.msc** in the **Run** dialog box, and confirm that the **D365 Automated testing certificate** certificate is created under **Personal \> Certificates**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-311">Győződjön meg róla, hogy a **certlm.msc**, és nem a **certmgr.msc** parancsot írja be, mivel a tanúsítványok a helyi számítógépen vannak tárolva.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-311">Be sure to enter **certlm.msc**, not **certmgr.msc**, because the certificates are stored on the local computer.</span></span>

    ![D365 Automatizált teszttanúsítvány tanúsítványa](./media/setup_rsa_tool_46.png)

3. <span data-ttu-id="ab1ea-313">Kattintson a jobb gombbal a tanúsítványra, majd válassza a **Másolás** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-313">Right-click the certificate, and then select **Copy**.</span></span>
4. <span data-ttu-id="ab1ea-314">Ugorjon a **Megbízható legfelső szintű hitelesítésszolgáltatók \> Tanúsítványok** pontra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-314">Go to **Trusted Root Certification Authorities \> Certificates**.</span></span>

    ![A megbízható legfelső szintű hitelesítésszolgáltatók mappa alatti tanúsítványok mappa](./media/setup_rsa_tool_47.png)

5. <span data-ttu-id="ab1ea-316">A **Művelet** menüben válassza a **beillesztés** parancsot, hogy a tanúsítványt a **Megbízható legfelső szintű hitelesítésszolgáltatók** helyre másolja.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-316">On the **Action** menu, select **Paste** to copy the certificate to the **Trusted Root Certification Authorities** location.</span></span>

    ![Beszúrás parancs a Művelet menüben](./media/setup_rsa_tool_48.png)

6. <span data-ttu-id="ab1ea-318">Ha meg szeretné kapni a telepített tanúsítvány ujjlenyomatát, de szóközöket vagy speciális karaktereket nem, rendszergazdaként nyissa meg a Windows PowerShell ablakát, és futtassa a következő parancsokat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-318">To get the thumbprint of the installed certificate, but without spaces or special characters, open a Windows PowerShell window as an admin, and run the following commands.</span></span>

    ```
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > <span data-ttu-id="ab1ea-319">Mentse az ujjlenyomatot, mert az Alkalmazásobjektum-kiszolgáló (AOS) .wif-fájljainak frissítéséhez és a RSAT-konfiguráció beállításához később szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-319">Save the thumbprint, because you will need it later when you update the .wif files for Application Object Server (AOS) and set up the RSAT configuration.</span></span>

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a><span data-ttu-id="ab1ea-320">Az AOS-számítógép konfigurálása a kapcsolatban való megbízásra</span><span class="sxs-lookup"><span data-stu-id="ab1ea-320">Configure the AOS computer to trust the connection</span></span>

> [!NOTE]
> <span data-ttu-id="ab1ea-321">Ha a környezet egy 2. vagy magasabb szintű környezet, a tanúsítvány ujjlenyomatát frissíteni kell a wif.config fájlban a környezet **összes** AOS-számítógépéhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-321">If the environment is a Tier 2+ environment, the certificate thumbprint must be updated in the wif.config file for **all** AOS computers for the environment.</span></span>

1. <span data-ttu-id="ab1ea-322">Hozzon létre egy távoli asztali protokoll (RDP) kapcsolatot az AOS-számítógéppel.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-322">Establish a Remote Desktop Protocol (RDP) connection to the AOS computer.</span></span> <span data-ttu-id="ab1ea-323">A bejelentkezési adatok az LCS környezeti adatok lapján érhetők el.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-323">Sign-in details are available on the environment details page in LCS.</span></span>
2. <span data-ttu-id="ab1ea-324">Nyissa meg a Microsoft Internet Information Services (IIS) alkalmazást, és keresse meg az **AOSService** elemet a webhelyek listáján.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-324">Open Microsoft Internet Information Services (IIS), and find **AOSService** in the list of sites.</span></span>

    ![AOSService a webhelyek listáján](./media/setup_rsa_tool_49.png)

3. <span data-ttu-id="ab1ea-326">Kattintson a jobb gombbal a **Felfedezés** gombra a **\<Drive\>: \\AosService\\WebRoot** mappa megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-326">Right-click **Explore** to open the **\<Drive\>: \\AosService\\WebRoot** folder.</span></span> <span data-ttu-id="ab1ea-327">Keresse meg a **wif.config** fájlját.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-327">Find the **wif.config** file.</span></span>

    ![Wif.config fájl a WebRoot mappában](./media/setup_rsa_tool_50.png)

4. <span data-ttu-id="ab1ea-329">A **wif.config** fájl frissítéséhez adjon hozzá egy új hitelesítésszolgáltatói bejegyzést a tanúsítványhoz és a hitelesítésszolgáltató nevét, amint az a következő példában látható.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-329">Update the **wif.config** file by adding a new authority entry for your certificate and authority name, as shown in the following example.</span></span>

    ```
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > <span data-ttu-id="ab1ea-330">Ha több felhasználó ugyanazt az alkalmazást használja, akkor mindegyik felhasználónak külön ujjlenyomatot kell létrehoznia, és ezeket a ujjlenyomatokat is hozzá kell adni a **\<keys\>** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-330">If multiple users are using the same application, each user must generate separate thumbprints, and each of those thumbprints must be added in the **\<keys\>** section.</span></span>

5. <span data-ttu-id="ab1ea-331">Ha egynél több AOS-számítógép van, akkor minden további számítógép esetében ismételje meg a 3. és 4. lépést.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-331">If there is more than one AOS computer, repeat steps 3 through 4 for each additional computer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-332">A régebbi 2. szintű környezetekkel ellentétben az új 2. szintű környezetek két AOS-példányon telepíthetők.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-332">Unlike older Tier 2 environments, new Tier 2 environments are deployed with two AOS instances.</span></span>

6. <span data-ttu-id="ab1ea-333">Futtassa az **iisreset** parancsot az összes AOS-számítógépen.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-333">Run **iisreset** on all the AOS computers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-334">Ha egy 1. szintű számítógépnél nem rendelkezik rendszergazdai jogosultsággal az **iisreset** parancs futtatásához, válassza a Karbantartás > Szolgáltatások újraindítása lehetőséget az LCS Környezet adatai oldalán.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-334">If you don't have admin rights to run **iisreset** on a Tier 1 computer, on the Environment details page in LCS, select Maintain > Restart services.</span></span>

#### <a name="tier-2-environment"></a><span data-ttu-id="ab1ea-335">2. vagy magasabb szintű környezet</span><span class="sxs-lookup"><span data-stu-id="ab1ea-335">Tier 2+ environment</span></span>

<span data-ttu-id="ab1ea-336">Ha egy 2. vagy magasabb szintű (szabványos elfogadási tesztkörnyezet vagy magasabb) környezet van használatban, ellenőrizze vagy állítsa be a következő jegyzékbeállítást azon a számítógépen, amelyen a RSAT telepítve van.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-336">If a Tier 2+ (Standard Acceptance Test sandbox or higher) environment is used, verify or set the following registry setting on the computer where RSAT is installed.</span></span> <span data-ttu-id="ab1ea-337">Ezt a lépést kötelező végrehajtani, mert segít elkerülni a hitelesítési vagy RSAT-kapcsolati hibákat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-337">This step is required because it helps you avoid authentication or RSAT connection errors.</span></span>

```
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a><span data-ttu-id="ab1ea-338">RSAT telepítése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-338">Install RSAT</span></span>

1. <span data-ttu-id="ab1ea-339">Lépjen a <https://www.microsoft.com/download/details.aspx?id=57357> oldalra, majd válassza a **letöltés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-339">Go to <https://www.microsoft.com/download/details.aspx?id=57357>, and select **Download**.</span></span>
2. <span data-ttu-id="ab1ea-340">Válassza ki az összes fájlt, majd kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-340">Select all the files, and then select **Next**.</span></span>

    ![Az összes fájl kiválasztása](./media/setup_rsa_tool_51.png)

3. <span data-ttu-id="ab1ea-342">A telepítő futtatásához kattintson duplán a .msi csomagra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-342">Double-click the .msi package to run the installer.</span></span> <span data-ttu-id="ab1ea-343">Ezt követően a telepítés befejezése után válassza a **Befejezés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-343">Then, when the installation is completed, select **Finish**.</span></span>

    ![RSAT-telepítőfájl](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a><span data-ttu-id="ab1ea-345">A Selenium és böngésző illesztőprogramjainak telepítése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-345">Install Selenium and browser drivers</span></span>

<span data-ttu-id="ab1ea-346">Az RSAT régebbi verzióiban telepíteni kellett a Seleniumot és a böngésző-illesztőprogramokat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-346">In older versions of RSAT, you had to install Selenium and browser drivers.</span></span> <span data-ttu-id="ab1ea-347">Ezeket az illesztőprogramokat már nem kell telepíteni, mert a program automatikusan telepíti azokat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-347">You no longer have to install these drivers because they are automatically installed.</span></span>

1. <span data-ttu-id="ab1ea-348">A RSAT első megnyitásakor a program megkérdezi, hogy automatikusan letölti és telepíti a Seleniumot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-348">The first time that you open RSAT, you're prompted to automatically download and install Selenium.</span></span> <span data-ttu-id="ab1ea-349">További információ: [RSAT konfigurálása](#configure-rsat).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-349">For more information, see the [Configure RSAT](#configure-rsat) section.</span></span>
2. <span data-ttu-id="ab1ea-350">A tesztesetek futtatása előtt a program rákérdez, hogy automatikusan letölti és telepíti-e a böngésző illesztőprogramját, amely megfelel a RSAT-konfigurációban kiválasztott alapértelmezett böngészőnek.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-350">Before you can run a test case, you're prompted to automatically download and install the browser driver that corresponds to the default browser that is selected in the RSAT configuration.</span></span> <span data-ttu-id="ab1ea-351">A további információkat megtekintheti a [Tesztesetek betöltése és futtatása](#load-and-run-test-cases) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-351">For more information, see the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

## <a name="get-started-with-rsat"></a><span data-ttu-id="ab1ea-352">Első lépések az RSAT használatában</span><span class="sxs-lookup"><span data-stu-id="ab1ea-352">Get started with RSAT</span></span>

### <a name="create-a-test-plan-and-test-suites"></a><span data-ttu-id="ab1ea-353">Tesztelési terv és a tesztcsomagok létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-353">Create a test plan and test suites</span></span>

1. <span data-ttu-id="ab1ea-354">Nyissa meg Azure DevOps-projektet, és válassza ki a **Tesztelési tervek** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-354">Go to the Azure DevOps project, and select **Test Plans**.</span></span>

    ![Tesztelési tervek parancs](./media/setup_rsa_tool_53.png)

2. <span data-ttu-id="ab1ea-356">Válassza az **Új tesztelési terv** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-356">Select **New Test Plan**.</span></span>

    ![Új tesztelési terv gomb](./media/setup_rsa_tool_54.png)

3. <span data-ttu-id="ab1ea-358">Töltse ki a **Név** mezőt, majd válassza a **Létrehozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-358">Fill in the **Name** field, and then select **Create**.</span></span> <span data-ttu-id="ab1ea-359">Ehhez az oktatóanyaghoz nevezze el a tesztelési tervet **RSAT tesztelési terv** néven.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-359">For this tutorial, name the test plan **RSAT Test Plan**.</span></span>

    ![Új tesztelési terv párbeszédpanel](./media/setup_rsa_tool_55.png)

4. <span data-ttu-id="ab1ea-361">Kattintson a pluszjelre (**+**), majd válassza a **Statikus csomag** lehetőséget, amellyel az új tesztelési terv alatt létrehozhat egy statikus csomagot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-361">Select the plus sign (**+**), and then select **Static suite** to create a static suite under the new test plan.</span></span> <span data-ttu-id="ab1ea-362">Nevezze el az új tesztcsomagot **T01 – Készletre gyártás** néven.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-362">Name the new test suite **T01 – Make to Stock**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-363">Lekérdezés alapú csomagot is létre lehet hozni, ha azt szeretné, hogy a rendszer automatikusan behúzza az új teszteseteket a BPM-ből az RSAT tesztcsomagba.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-363">You can also create a query-based suite, if you want the new test cases from BPM to be automatically pulled into the RSAT test suite.</span></span>

    ![Statikus csomag létrehozása](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a><span data-ttu-id="ab1ea-365">Tesztelési esetek csatolása a tesztcsomagokhoz</span><span class="sxs-lookup"><span data-stu-id="ab1ea-365">Attach test cases to test suites</span></span>

1. <span data-ttu-id="ab1ea-366">A jobb oldali **Meglévő hozzáadása** gombbal hozzáadhat meglévő teszteket a tesztcsomaghoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-366">Select **Add existing** on the right side to add existing test cases to the test suite.</span></span>

    ![Meglévő hozzáadása gomb](./media/setup_rsa_tool_57.png)

2. <span data-ttu-id="ab1ea-368">A **Tesztesetek hozzáadása csomaghoz** oldalon válassza a **Lekérdezés futtatása** parancsot, majd válassza ki a tesztcsomaghoz hozzáadni kívánt tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-368">On the **Add test cases to suite** page, select **Run query**, and then select the test case to add to the test suite.</span></span> <span data-ttu-id="ab1ea-369">Ehhez az oktatóanyaghoz válassza az **Új termék létrehozása** esetet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-369">For this tutorial, select the **Create a new product** test case.</span></span> <span data-ttu-id="ab1ea-370">Ezután válassza a **Tesztesetek hozzáadása** lehetőséget az oldal jobb alsó sarkában (ez a gomb nem látható az alábbi ábrán).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-370">Then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Lekérdezés futtatása gomb](./media/setup_rsa_tool_58.png)

    <span data-ttu-id="ab1ea-372">A tesztesetet hozzáadta a **T01 – Készletre gyártás** tesztcsomaghoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-372">The test case is added to the **T01-Make to Stock** test suite.</span></span>

    ![Teszteset hozzáadva a tesztcsomaghoz](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a><span data-ttu-id="ab1ea-374">RSAT beállítása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-374">Configure RSAT</span></span>

1. <span data-ttu-id="ab1ea-375">Nyissa meg az RSAT-ot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-375">Open RSAT.</span></span>

    ![RSAT ikon](./media/setup_rsa_tool_60.png)

2. <span data-ttu-id="ab1ea-377">Figyelmeztető üzenet jelenik meg, amely kijelenti, hogy: „A Regression Suite Automation Tool használatához Selenium szükséges, szeretné automatikusan letölteni és telepíteni most?”</span><span class="sxs-lookup"><span data-stu-id="ab1ea-377">You receive a warning message that states, "The Regression Suite Automation Tool requires Selenium, do you want to automatically download and install it now?"</span></span> <span data-ttu-id="ab1ea-378">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-378">Select **Yes**.</span></span>

    ![Figyelmeztető üzenet](./media/setup_rsa_tool_61.png)

3. <span data-ttu-id="ab1ea-380">Válassza a jobb felső sarokban a **Beállítások** gombot (fogaskerék szimbólum), majd a megjelenő párbeszédpanelen töltse ki a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="ab1ea-380">Select the **Settings** button (the gear symbol) in the upper-right corner, and then, in the dialog box that appears, fill in the following fields:</span></span>

    - <span data-ttu-id="ab1ea-381">**Azure DevOps URL** – Adja meg a Azure DevOps-projekt URL-címét, például `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-381">**Azure DevOps Url** – Enter the URL of your Azure DevOps project, such as `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span></span>
    - <span data-ttu-id="ab1ea-382">**Hozzáférési token** – adja meg azt a hozzáférési tokent, amely lehetővé teszi, hogy az eszköz csatlakozhasson az Azure DevOps rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-382">**Access Token** – Enter the access token that lets the tool connect to Azure DevOps.</span></span> <span data-ttu-id="ab1ea-383">Az oktatóprogramban korábban létrehozott személyes hozzáférési tokent használja.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-383">Use the personal access token that you created earlier in this tutorial.</span></span> <span data-ttu-id="ab1ea-384">A további tudnivalókat lásd: [Hozzáférés hitelesítése személyes hozzáférési jogkivonatokkal](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-384">For more information, see [Authenticate access with personal access tokens](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span></span>
    - <span data-ttu-id="ab1ea-385">**Projekt neve** – válassza ki a Azure DevOps-projekt nevét.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-385">**Project Name** – Select the name of your Azure DevOps project.</span></span>
    - <span data-ttu-id="ab1ea-386">**Tesztelési terv** – válassza ki azt a Azure DevOps-tesztelési tervet, amely a teszt eseteit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-386">**Test Plan** – Select the Azure DevOps test plan that contains your test cases.</span></span> <span data-ttu-id="ab1ea-387">A további tudnivalókat lásd: [Tesztelési tervek és tesztcsomagok létrehozása](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-387">For more information, see [Create test plans and test suites](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span></span> <span data-ttu-id="ab1ea-388">Miután kiválasztotta a tesztelési tervet, válassza a **Kapcsolat ellenőrzése** lehetőséget, és tesztelje a kapcsolatot az Azure DevOps rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-388">After you select a test plan, select **Test Connection** to test your connection to Azure DevOps.</span></span>
    - <span data-ttu-id="ab1ea-389">**Állomásnév** – adja meg a tesztkörnyezet állomásnevét, például **\<myaos\>.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-389">**Hostname** – Enter the host name of the test environment, such as **\<myaos\>.cloudax.dynamics.com**.</span></span> <span data-ttu-id="ab1ea-390">Ne szerepeljen a **https://** vagy **http://** előtag.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-390">Don't include the **https://** or **http://** prefix.</span></span>
    - <span data-ttu-id="ab1ea-391">**SOAP állomásnév** – adja meg a tesztkörnyezet SOAP-állomásnevét.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-391">**SOAP Hostname** – Enter the SOAP host name of the test environment.</span></span> <span data-ttu-id="ab1ea-392">A SOAP-állomásnév általában ugyanaz, mint az állomásnév, de van **soap** -utótagja.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-392">Typically, the SOAP host name is the same as the host name, but it has a **soap** suffix.</span></span> <span data-ttu-id="ab1ea-393">Itt egy példa: **\<myaos\>soap.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-393">Here is an example: **\<myaos\>soap.cloudax.dynamics.com**.</span></span> <span data-ttu-id="ab1ea-394">Ne szerepeljen a **https://** vagy **http://** előtag.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-394">Don't include the **https://** or **http://** prefix.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ab1ea-395">Az állomásnév és a SOAP-állomás nevének megkereséséhez nyissa meg az IIS-kezelőt, kattintson a jobb gombbal a **Webhelyek \> AOSService** elemre, majd válassza a **Kötések szerkesztése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-395">To find the host name and SOAP host name, open IIS Manager, right-click **Sites \> AOSService**, and then select **Edit bindings**.</span></span> <span data-ttu-id="ab1ea-396">Az **állomásnév** oszlopban szereplő értékek adják meg az állomásnevet és a SOAP-állomásnevet (a SOAP-állomásnév URL-címében **SOAP**-utótagnak kell lennie).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-396">The values in the **Host Name** column give you the host name and SOAP host name (the SOAP host name has the suffix **soap** in the URL).</span></span>

        ![Az állomásnév és SOAP-állomásnév az állomásnév oszlopban](./media/setup_rsa_tool_63.png)

    - <span data-ttu-id="ab1ea-398">**Rendszergazda felhasználóneve** – Adja meg a rendszergazda felhasználó e-mail-címét a tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-398">**Admin user name** – Enter the email address of an admin user in the test environment.</span></span>
    - <span data-ttu-id="ab1ea-399">**Ujjlenyomat** – adja meg a hitelesítési tanúsítvány ujjlenyomatát az oktatóanyagban korábban leírt módon.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-399">**Thumbprint** – Enter the thumbprint of the authentication certificate, as described earlier in this tutorial.</span></span>
    - <span data-ttu-id="ab1ea-400">**Munkakönyvtár** – adja meg a mappa helyét a tesztautomatizálás fájljainak (például az Excel tesztadatfájlok) tárolásához.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-400">**Working directory** – Specify the folder location for storing test automation files, such as Excel test data files.</span></span> <span data-ttu-id="ab1ea-401">Például írja be vagy válassza ki **C:\\Temp\\RegressionTool** mappát.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-401">For example, enter or select **C:\\Temp\\RegressionTool**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ab1ea-402">Ha a mappa neve szóközöket tartalmaz, akkor a végrehajtás sikertelen lesz, mert a mappa nem található.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-402">If the name of the folder has spaces, execution will fail because the folder can't be found.</span></span> <span data-ttu-id="ab1ea-403">Ez a probléma ismert probléma, és kijavítjuk az eszköz egy későbbi verziójában.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-403">This issue is a known issue and should be fixed in the latest version of the tool.</span></span>

    - <span data-ttu-id="ab1ea-404">**Alapértelmezett böngésző** – válassza vagy az **Internet Explorer** vagy **Google Chrome** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-404">**Default browser** – Select either **Internet Explorer** or **Google Chrome**.</span></span> <span data-ttu-id="ab1ea-405">Ellenőrizze, hogy telepítve vannak-e a megfelelő böngésző-illesztőprogramok.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-405">Make sure that the appropriate browser drivers have been installed.</span></span>
    - <span data-ttu-id="ab1ea-406">**Tesztfuttatás időtúllépése** – Adja meg az időtúllépés hosszát percben megadva a tesztfutásokhoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-406">**Test run timeout** – Specify the time-out period, in minutes, for test runs.</span></span> <span data-ttu-id="ab1ea-407">Amikor az időtúllépési időszak eltelik, az összes aktív ablak le lesz zárva, és a függőben lévő tesztesetek sikertelenek lesznek.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-407">When the time-out period elapses, all active windows are closed, and pending test cases fail.</span></span>
    - <span data-ttu-id="ab1ea-408">**Tesztelési művelet időtúllépése** – ez a mező a Finance and Operations környezet kiszolgálói kérelmeinek időtúllépési idejét határozza meg percben.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-408">**Test action timeout** – This field controls the time-out period, in minutes, for Finance and Operation environment server requests.</span></span> <span data-ttu-id="ab1ea-409">Általában az alapértelmezett értéknek (2 perc) elégnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-409">Usually, the default value (2 minutes) should be enough.</span></span> <span data-ttu-id="ab1ea-410">A lassabb környezetek esetében azonban előfordulhat, hogy érdemes az értéket növelni, ha időtúllépéssel kapcsolatos hibák történnek.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-410">However, for slower environments, you might want to increase the value if errors that are related to time-outs occur.</span></span>
    - <span data-ttu-id="ab1ea-411">**Vállalatnév** – Adja meg annak a vállalatnak a nevét, amelyet alapértelmezett vállalatként kell használni az Excel-paraméterfájlok létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-411">**Company name** – Enter the company name to use as your default company when Excel parameter files are created.</span></span> <span data-ttu-id="ab1ea-412">A vállalat később módosítható az Excel-paraméterfájl szerkesztésével.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-412">You can change the company later by editing the Excel parameter file.</span></span>

    ![Beállítások párbeszédpanel](./media/setup_rsa_tool_62.png)

4. <span data-ttu-id="ab1ea-414">Válassza az **Alkalmazás** parancsot a beállítások alkalmazásához és mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-414">Select **Apply** to apply and save your settings.</span></span>

    <span data-ttu-id="ab1ea-415">Ha menteni szeretné az aktuális beállításokat a számítógép konfigurációs fájljába, válassza a **Mentés másként** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-415">To save your current settings to a configuration file on your computer, select **Save as**.</span></span> <span data-ttu-id="ab1ea-416">Ha vissza szeretné állítani a beállításokat a számítógép konfigurációs fájljából, válassza a **Megnyitás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-416">To restore your settings from a configuration file on your computer, select **Open**.</span></span>

5. <span data-ttu-id="ab1ea-417">A **Bezárás** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-417">Select **Close** to close the dialog box.</span></span>

### <a name="load-and-run-test-cases"></a><span data-ttu-id="ab1ea-418">Tesztesetek betöltése és futtatása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-418">Load and run test cases</span></span>

1. <span data-ttu-id="ab1ea-419">Válassza a **Betöltés** parancsot az **RSAT tesztelési terv** tesztelési terv betöltéséhez az Azure DevOps projektből.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-419">Select **Load** to load the **RSAT Test Plan** test plan from the Azure DevOps project.</span></span>

    ![Betöltés gomb](./media/setup_rsa_tool_64.png)

2. <span data-ttu-id="ab1ea-421">Válassza a tesztcsomagból az **Új termék létrehozása** tesztesetet, majd az **Új \> Tesztvégrehajtás és paraméterfájlok létrehozása**.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-421">Select the **Create a new product** test case from the test suite, and then select **New \> Generate Test Execution and Parameter files**.</span></span>

    ![Tesztvégrehajtás és paraméterfájlok létrehozása parancs az Új menüben](./media/setup_rsa_tool_65.png)

    <span data-ttu-id="ab1ea-423">A program az Excel-paraméterfájlt a RSAT-konfigurációban megadott helyi mappában hozza létre (például **C:\\Temp\\RegressionTool**).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-423">The Excel parameter file is created in the local folder that you specified in the RSAT configuration (for example, **C:\\Temp\\RegressionTool**).</span></span>

    ![Excel-paraméterfájl létrehozva](./media/setup_rsa_tool_66.png)

3. <span data-ttu-id="ab1ea-425">Ha menteni szeretné a paraméterfájlokat, válassza a **Feltöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-425">If you want to save the parameter files, select **Upload**.</span></span> <span data-ttu-id="ab1ea-426">A program az összes kiválasztott teszteset tesztautomatizálási fájljait feltölti az Azure DevOps rendszerbe jövőbeli használatra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-426">Test automation files of all selected test cases are uploaded to Azure DevOps for future use.</span></span> <span data-ttu-id="ab1ea-427">(Ezek a fájlok tartalmazzák az Excel teszt-paraméterfájlokat.)</span><span class="sxs-lookup"><span data-stu-id="ab1ea-427">(These files include Excel test parameter files.)</span></span>

    <span data-ttu-id="ab1ea-428">Ilyenmódon a **Betöltés** paranccsal a paraméterfájlokat (és automatizálási fájlokat) a tesztesetből közvetlenül az Azure DevOps rendszerből töltheti be.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-428">In this way, you can select **Load** to load the parameter files (and automation files) from the test case directly from Azure DevOps.</span></span> <span data-ttu-id="ab1ea-429">Nem kell újragenerálni a paraméterfájlokat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-429">You don't have to regenerate the parameter files.</span></span> <span data-ttu-id="ab1ea-430">Ez a megközelítés később fontos lesz, amikor meg szeretné tartani a módosításokat a paraméterfájlban, és nem szeretné, hogy felülírják őket.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-430">This approach will become important later, when you want to keep the modifications in the parameter file and don't want them to be overwritten.</span></span>

4. <span data-ttu-id="ab1ea-431">Ha ellenőrizni szeretné, hogy az automatizálási fájlok és a paraméterfájlok mentésre kerültek az Azure DevOps rendszerbe, nyissa meg az Azure DevOps-projektet, válassza ki a **Táblák \> Munkaelemek** pontot, majd az **Új termék létrehozása** tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-431">To verify that the automation files and parameter files are saved to Azure DevOps, go to the Azure DevOps project, select **Boards \> Work Items**, and select the **Create a new product** test case.</span></span> <span data-ttu-id="ab1ea-432">A **Mellékletek** lapon négy fájl jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="ab1ea-432">On the **Attachments** tab, you should see four files:</span></span>

    - <span data-ttu-id="ab1ea-433">**.cs** – C\# automatizálási fájl</span><span class="sxs-lookup"><span data-stu-id="ab1ea-433">**.cs** – C\# automation file</span></span>
    - <span data-ttu-id="ab1ea-434">**.dll** – Lefordított automatizálási fájl szerelvényként</span><span class="sxs-lookup"><span data-stu-id="ab1ea-434">**.dll** – Compiled automation file as an assembly</span></span>
    - <span data-ttu-id="ab1ea-435">**.xlsx** – Excel-paraméterfájl</span><span class="sxs-lookup"><span data-stu-id="ab1ea-435">**.xlsx** – Excel parameter file</span></span>
    - <span data-ttu-id="ab1ea-436">**.xml** – Rögzítési fájl</span><span class="sxs-lookup"><span data-stu-id="ab1ea-436">**.xml** – Recording file</span></span>

    ![A mellékletek lap fájljai](./media/setup_rsa_tool_67.png)

5. <span data-ttu-id="ab1ea-438">Válassza ki a futtatni kívánt tesztesetet, majd válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-438">Select the test case to run, and then select **Run**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-439">Ha a használt böngésző Internet Explorer, akkor a tesztesetek futtatása előtt győződjön meg arról. hogy az Asztal felbontása **100%**-ra van állítva a **Windows képernyőbeállításai \> Méretezés és elrendezés** pontban.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-439">Before you run test cases, if you're using Internet Explorer as the browser, make sure that your desktop resolution is set to **100%** at **Windows Display settings \> Scale and layout**.</span></span> <span data-ttu-id="ab1ea-440">Ha nem tudja megváltoztatni ezt a beállítást egy virtuális gépen (VM), akkor módosítsa azt a kliensen (laptop), amelyről a VM-et szeretné elérni.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-440">If you can't change this setting on a virtual machine (VM), change it on the client (laptop) that you're trying to access the VM from.</span></span> <span data-ttu-id="ab1ea-441">A felbontás beállításait a VM képernyőbeállításai öröklik.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-441">The resolution settings will then be inherited by the VM display settings.</span></span>

    ![Asztali felbontás 100%-ra állítva](./media/setup_rsa_tool_68.png)

6. <span data-ttu-id="ab1ea-443">Ha a böngésző illesztőprogramjai nincsenek telepítve a rendszerben, akkor egy figyelmeztető üzenet jelenik meg, amely kijelenti: „Ehhez a művelethez a \<browser name\> illesztőprogram szükséges.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-443">If the browser drivers aren't installed in the system, you receive a warning message that states, "This operation requires the \<browser name\> driver.</span></span> <span data-ttu-id="ab1ea-444">Automatikusan letölti és telepíti most?”</span><span class="sxs-lookup"><span data-stu-id="ab1ea-444">Do you want to automatically downloads and install it now?"</span></span> <span data-ttu-id="ab1ea-445">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-445">Select **Yes**.</span></span>

    ![Figyelmeztető üzenet az Internet Explorer böngészőhöz](./media/setup_rsa_tool_69.png)

    ![Figyelmeztető üzenet az Chrome böngészőhöz](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > <span data-ttu-id="ab1ea-448">Ha a Chrome böngészőt használja, és egy hibaüzenet jelenik meg, amely azt jelzi, hogy a munkamenet nem lett létrehozva, mert a Chrome-verzió nem megfelelő, töltse le a legfrissebb Chrome-illesztőprogramot a <http://chromedriver.chromium.org/downloads> oldalról a **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** mappába.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-448">If you're using Chrome as the browser and receive an error message that states that the session wasn't created because the Chrome version isn't correct, download the latest Chrome driver from <http://chromedriver.chromium.org/downloads> to the **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** folder.</span></span>

    ![Hibaüzenet az Chrome böngészőhöz](./media/setup_rsa_tool_71.png)

    <span data-ttu-id="ab1ea-450">A program futtatja a tesztesetet, és frissíti az **eredmény** mezőt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-450">The test case is run, and the **Result** field is updated.</span></span>

    ![Folyamatjelző](./media/setup_rsa_tool_72.png)

    <span data-ttu-id="ab1ea-452">Ha a leírtaknak megfelelően követte az oktatóanyagot, az **Új termék létrehozása** teszteset sikertelen lesz, mert a termék létrehozásához tartozó feladatrögzítés a terméknevet beégetett értékként mentette.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-452">If you've followed this tutorial as it's written, the **Create a new product** test case will fail, because the task recording for creating a product saved the product name as a hard-coded value.</span></span> <span data-ttu-id="ab1ea-453">Ha újból futtatja ugyanazt a tesztesetet, hibaüzenetet kap, mert a termék már létezik.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-453">If you rerun the same test case, you should receive an error message, because the product already exists.</span></span>

    ![Eredménymező értéke Sikertelen](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a><span data-ttu-id="ab1ea-455">Teszteredmények megtekintése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-455">View the test results</span></span>

1. <span data-ttu-id="ab1ea-456">Kattintson duplán a sikertelen tesztesetre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-456">Double-click the failed test case.</span></span>

    <span data-ttu-id="ab1ea-457">Hibaüzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-457">You receive an error message.</span></span>

    ![Hibaüzenet](./media/setup_rsa_tool_73.png)

2. <span data-ttu-id="ab1ea-459">A teljes hibaüzenet megjelenítéséhez kattintson a **Részletek** gombra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-459">Select **Details** to view the whole error message.</span></span>

    ![Teljes hibaüzenet](./media/setup_rsa_tool_74.png)

3. <span data-ttu-id="ab1ea-461">A hibaüzenet részletes verziójának Azure DevOps rendszerben való megtekintéséhez válassza a **Megnyitás Azure DevOps rendszerben** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-461">To view a detailed version of the error message in Azure DevOps, select **Open in Azure DevOps**.</span></span> <span data-ttu-id="ab1ea-462">Az Azure DevOps rendszerben megtekintheti a teszteset állapotát és a részletes hibaüzenetet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-462">In Azure DevOps, you can view the status of the test case and the detailed error message.</span></span>

    ![Részletes hibaüzenet az Azure DevOps rendszerben](./media/setup_rsa_tool_75.png)

4. <span data-ttu-id="ab1ea-464">Ha közvetlenül az Azure DevOps-projektben szeretné megtekinteni a teszt eredményeit, lépjen a **Tesztelési tervek \> Tesztelési tervek \> Futások** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-464">To view the test results directly in the Azure DevOps project, go to **Test Plans \> Test Plans \> Runs**.</span></span> <span data-ttu-id="ab1ea-465">Kattintson duplán a teszt futtatására, amelyről további részleteket szeretne látni.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-465">Double-click the test run that you want to see more details for.</span></span>

    ![Tesztfutások listája az Azure DevOps rendszerben](./media/setup_rsa_tool_76.png)

5. <span data-ttu-id="ab1ea-467">Az **Futás összefoglalása** lap azt jelzi, hogy a teszteset nem sikerült, de nem biztosítja a tényleges hibaüzenetet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-467">The **Run summary** tab indicates that the test case failed, but it doesn't provide the actual error message.</span></span> <span data-ttu-id="ab1ea-468">Ha meg szeretné tekinteni a részletes hibaüzenetet, válassza ki a **Teszteredmények** lapot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-468">To view the detailed error message, select the **Test results** tab.</span></span>

    ![Futás összefoglalása lap](./media/setup_rsa_tool_77.png)

    <span data-ttu-id="ab1ea-470">A **teszteredmények** lap a tesztesettel kapcsolatos információkat, valamint az eredményt és a hibaüzenetet tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-470">The **Test results** tab provides the test case information, together with the outcome and the error message.</span></span>

    ![Teszteredmények lap](./media/setup_rsa_tool_78.png)

6. <span data-ttu-id="ab1ea-472">A részletes hibaüzenet megjelenítéséhez kattintson duplán a megfelelő rekordra.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-472">Double-click the relevant record to view the detailed error message.</span></span>

    ![Részletes hibaüzenet](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > <span data-ttu-id="ab1ea-474">Minden hibaüzenet helyileg is elérhető itt: **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-474">All error messages are also available locally in **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span></span>

7. <span data-ttu-id="ab1ea-475">A tesztfutás eredményeit a tesztelési terv szintjéről is exportálhatja az **Export** paranccsal.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-475">You can also export the test run results from the test plan level by selecting **Export**.</span></span>

    ![Tesztelési terv exportálása](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a><span data-ttu-id="ab1ea-477">Excel-paraméterfájl módosítása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-477">Modify the Excel parameter file</span></span>

1. <span data-ttu-id="ab1ea-478">Nyissa meg az RSAT-ot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-478">Open RSAT.</span></span>
2. <span data-ttu-id="ab1ea-479">Válassza ki a tesztesetet, majd a **Szerkesztés** parancsot az Excel-paraméterfájl megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-479">Select the test case, and then select **Edit** to open the Excel parameter file.</span></span>

    <span data-ttu-id="ab1ea-480">Az **EcoResProductCreate** lapon figyelje meg, hogy a **Termékszám** mezőjének értéke nem beégetett.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-480">On the **EcoResProductCreate** sheet, notice that the value of the **Product number** field is hard-coded.</span></span> <span data-ttu-id="ab1ea-481">Ezt a mezőt új termékszámra kell frissítenie a teszteset újbóli futtatása előtt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-481">You must update this field to a new product number before you run the test case again.</span></span>

3. <span data-ttu-id="ab1ea-482">Ha minden egyes futtatáshoz egyedi termékazonosítót szeretne létrehozni anélkül, hogy minden alkalommal újra meg kelljen nyitni az Excel-paraméterfájlt, és manuálisan kelljen frissíteni a termékszámot, használja a következő Excel-formulát.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-482">To generate a unique product number for each run without having to reopen the Excel parameter file and manually update the product number every time, use the following Excel formula.</span></span>

    ```
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > <span data-ttu-id="ab1ea-483">Az **Általános** lap mellett az Excel-paraméterfájl is tartalmaz egy adatlapot minden űrlapoldalhoz, amelyet a teszteset meglátogat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-483">In addition to the **General** tab, the Excel parameter file contains a data tab for every form page the test case visits.</span></span>

    ![Termékszám mező](./media/setup_rsa_tool_81.png)

4. <span data-ttu-id="ab1ea-485">Válassza a **Mentés** gombot, majd zárja be az Excel-munkafüzetet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-485">Select **Save**, and then close the Excel workbook.</span></span>
5. <span data-ttu-id="ab1ea-486">Válassza a **Feltöltés** parancsot az Excel-paraméterfájl Azure DevOps rendszerbe való mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-486">Select **Upload** to save the Excel parameter file to Azure DevOps.</span></span>

    ![Sikeres feltöltési üzenet](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > <span data-ttu-id="ab1ea-488">Ha a teszteseteket meghatározott felhasználói környezetben szeretné futtatni, adja meg a felhasználó e-mail-azonosítóját az Excel-paraméterfájl **Általános** lapján a **Tesztfelhasználó** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-488">To run test cases in a specific user context, enter the user's email ID in the **Test User** field on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="ab1ea-489">A RSAT legutóbbi verziójában módosult az Excel-paraméterfájl mezőinek elrendezése, de a koncepció ugyanaz marad.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-489">In the latest version of RSAT, the layout of the fields in the Excel parameter file has been updated, but the concept remains the same.</span></span>
    >
    > ![Tesztfelhasználó mező](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a><span data-ttu-id="ab1ea-491">Eredmények ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-491">Validate the results</span></span>

- <span data-ttu-id="ab1ea-492">Válassza a **Futtatás** parancsot a teszt esetének újrafuttatásához, és ellenőrizze, hogy a teszteset sikeres volt-e.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-492">Select **Run** to rerun the test case, and verify that the test case has passed.</span></span> <span data-ttu-id="ab1ea-493">A teszt eredményeit a [Teszteredmények megtekintése](#view-the-test-results) szakaszban leírtaknak megfelelően tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-493">You can view the test results as described in the [View the test results](#view-the-test-results) section.</span></span>

    ![Eredménymező értéke Sikeres](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a><span data-ttu-id="ab1ea-495">Tesztesetek láncolása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-495">Chaining of test cases</span></span>

<span data-ttu-id="ab1ea-496">A RSAT egyik alapvető funkciója a tesztesetek láncolása (az a képesség, amellyel egy teszt értékeket adhat át más teszteknek).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-496">One key feature of RSAT is the chaining of test cases (that is, the capability of a test to pass values to other tests).</span></span> <span data-ttu-id="ab1ea-497">A teszteseteket az Azure DevOps tesztelési tervben meghatározott sorrendben futtatjuk.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-497">Test cases are run according to their defined order in the Azure DevOps test plan.</span></span> <span data-ttu-id="ab1ea-498">(Ez a sorrend a tesztelési eszközben is módosítható.) Így ha az egyik tesztből a másikba szeretne változókat átadni, akkor fontos, hogy a tesztek megfelelő sorrendben legyenek.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-498">(This order can also be updated in the test tool itself.) Therefore, if you want to pass variables from one test case to another, it's very important that the tests be in the correct order.</span></span>

<span data-ttu-id="ab1ea-499">Ebben a szakaszban egy mentett változót fog létrehozni az első tesztesethez, létrehoz egy második tesztesetet, majd átadja a mentett változót az első tesztesetből a második tesztesetbe.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-499">In this section, you will create a saved variable in the first test case, create a second test case, and pass the saved variable from the first test case to the second test case.</span></span> <span data-ttu-id="ab1ea-500">Ezt követően a teszteseteket láncolt tesztesetként futtatja majd az RSAT-ban.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-500">You will then run the test cases as a chained test case in RSAT.</span></span>

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a><span data-ttu-id="ab1ea-501">Meglévő feladatrögzítés módosítása mentett változó létrehozásához</span><span class="sxs-lookup"><span data-stu-id="ab1ea-501">Modify an existing task recording to create a saved variable</span></span>

1. <span data-ttu-id="ab1ea-502">Nyissa meg az ügyfélprogramot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-502">Open the client.</span></span>
2. <span data-ttu-id="ab1ea-503">Válassza ki a **Beállítások** gombot (a fogaskerék szimbólumát), majd válassza ki a **Feladatrögzítőt**.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-503">Select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>
3. <span data-ttu-id="ab1ea-504">Válassza a **Rögzítés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-504">Select **Edit Recording**.</span></span>

    ![Rögzítés szerkesztése gomb](./media/setup_rsa_tool_85.png)

4. <span data-ttu-id="ab1ea-506">Válassza a **Megnyitás a Lifecycle Services szolgáltatásból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-506">Select **Open from Lifecycle Services**.</span></span>

    ![Megnyitás a Lifecycle Services szolgáltatásból gomb](./media/setup_rsa_tool_86.png)

5. <span data-ttu-id="ab1ea-508">Válassza a **A Lifecycle Services-tár kiválasztása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-508">Select **Select the Lifecycle Services library**.</span></span>

    ![A Lifecycle Services-tár kiválasztása gomb](./media/setup_rsa_tool_87.png)

    <span data-ttu-id="ab1ea-510">A BPM-tárak a LCS modulból töltődnek be.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-510">BPM libraries are loaded from LCS.</span></span>

    ![Folyamatjelző](./media/setup_rsa_tool_88.png)

6. <span data-ttu-id="ab1ea-512">Miután megtörtént a BPM-tárak betöltése az LCS-ból, válassza ki a **RSAT** BPM-tárat, és az **Új termék létrehozása** üzleti folyamatot, amelyhez a feladatrögzítést társították.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-512">After the BPM libraries are loaded from LCS, select the **RSAT** BPM library and the **Create a new product** business process that the task recording was associated with.</span></span> <span data-ttu-id="ab1ea-513">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-513">Then select **OK**.</span></span>

    ![BPM-tár és üzleti folyamat kiválasztása](./media/setup_rsa_tool_89.png)

7. <span data-ttu-id="ab1ea-515">A megfelelő feladatrögzítés neve megadásra kerül a **Rögzítés neve** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-515">The name of the appropriate task recording is entered in the **Recording name** field.</span></span> <span data-ttu-id="ab1ea-516">Válassza az **Indítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-516">Select **Start**.</span></span>

    ![A feladatrögzítés neve a Rögzítés neve mezőben](./media/setup_rsa_tool_90.png)

8. <span data-ttu-id="ab1ea-518">Lépjen a **Termékinformációk kezelése \> Termékek** pontra, válassza az **Új** elemet az oldal megnyitásához, ahol az eredeti feladatrögzítés **Termék létrehozása** rögzítésre került.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-518">Go to **Product information management \> Products**, and select **New** to open the page where the original task recording, **Create a product**, was recorded.</span></span>
9. <span data-ttu-id="ab1ea-519">Válassza a **Lépés beszúrása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-519">Select **Insert step**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-520">A program az új lépést a panelen kiválasztott lépés **után** szúrja be.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-520">The new step is inserted **after** the step that you selected in the pane.</span></span>

    ![Lépés beszúrása gomb](./media/setup_rsa_tool_91.png)

10. <span data-ttu-id="ab1ea-522">Kattintson jobb gombbal a **Termékszám** mezőre, majd válassza a **Feladatrögzítő \> Másolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-522">Right-click the **Product number** field, and then select **Task recorder \> Copy**.</span></span>

    ![Másolás parancs](./media/setup_rsa_tool_92.png)

11. <span data-ttu-id="ab1ea-524">A program új lépést hozzáadta a panelhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-524">A new step is added in the pane.</span></span> <span data-ttu-id="ab1ea-525">Jegyezze fel a **Termékszám** mezőjének értékét, mert később szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-525">Make a note of the value in the **Product number** field, because you will need it later.</span></span>

    ![Új lépés hozzáadva](./media/setup_rsa_tool_93.png)

12. <span data-ttu-id="ab1ea-527">Válassza a **Szerkesztés kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-527">Select **Done editing**.</span></span>
13. <span data-ttu-id="ab1ea-528">Válassza a **Mentés a Lifecycle Services szolgáltatásba** parancsot, majd társítsa az új feladatrögzítést ugyanahhoz a BPM-tárhoz és üzleti folyamathoz, amelyhez az eredeti feladatrögzítést társította.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-528">Select **Save to Lifecycle Services**, and associate the new task recording with the same BPM library and business process that the original task recording was associated with.</span></span> <span data-ttu-id="ab1ea-529">További információk: [Feladatrögzítés létrehozása és mentése BPM-tárba](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-529">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>
14. <span data-ttu-id="ab1ea-530">Lépjen a BPM-tárba és válassza a **Tesztesetek szinkronizálása** lehetőséget a tesztesethez az Azure DevOps rendszerben társított feladatrögzítés felülírása érdekében a [A BPM-ről az Azure DevOps szolgáltatásba történő szinkronizálás tesztelése](#test-the-synchronization-from-bpm-to-azure-devops) szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-530">Go to the BPM library, and select **Sync testcases** to overwrite the task recording that is attached to the test case in Azure DevOps, as described in the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>
15. <span data-ttu-id="ab1ea-531">Nyissa meg az RSAT eszközt, és válassza a **Betöltés** parancsot a tesztcsomag összes tesztesetének újbóli betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-531">Open RSAT, and select **Load** to reload all the test cases in the test suite.</span></span> <span data-ttu-id="ab1ea-532">A megfelelő tesztesethez újból létre kell hoznia az automatizálási és paraméterfájlokat úgy, hogy kiválasztja a tesztesetet, majd az **Új \> Teszt-végrehajtási és paraméterfájlok létrehozása** elemet választja, a [Tesztesetek betöltése és futtatása](#load-and-run-test-cases) részben leírtaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-532">You must regenerate the automation and parameter files for the appropriate test case by selecting the test case and then selecting **New \> Generate Test Execution and Parameter files**, as described in the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-533">Ha az Excel-paraméterfájl nyitva maradt, az újbóli létrehozás nem fog sikerülni.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-533">If the Excel parameter file was left open, regeneration will fail.</span></span> <span data-ttu-id="ab1ea-534">Győződjön meg róla, hogy a tesztesethez tartozó Excel-paraméterfájl be van zárva, mielőtt létrehozza az új Excel-paraméterfájlt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-534">Therefore, make sure that the Excel parameter file for the test case is closed before you generate the new Excel parameter file.</span></span>

16. <span data-ttu-id="ab1ea-535">Az új Excel-paraméterfájl megnyitásához válassza a **Szerkesztés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-535">Select **Edit** to open the new Excel parameter file.</span></span> <span data-ttu-id="ab1ea-536">Egy új, **mentett változó** nevű bejegyzést fog látni a 9. sorban.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-536">You will see a new **Saved variable** entry on line 9.</span></span> <span data-ttu-id="ab1ea-537">Ez a változó, az **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** a feladatrögzítés XML-fájljába lett mentve, és az egymást követő teszteknél használható.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-537">This variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, is saved in the task recording's XML file and can be used in subsequent tests.</span></span>

    ![Mentett változó bejegyzése](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a><span data-ttu-id="ab1ea-539">Új teszteset létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-539">Create a new test case</span></span>

1. <span data-ttu-id="ab1ea-540">Lépjen az **RSAT** BPM-tárhoz.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-540">Go to the **RSAT** BPM library.</span></span>
2. <span data-ttu-id="ab1ea-541">Válassza ki az **Minta támogatási üzleti folyamat** folyamatot, majd a jobb oldalon a **Szerkesztési mód** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-541">Select the **Sample Support Business Process** process, and then, on the right, select **Edit mode**.</span></span>
3. <span data-ttu-id="ab1ea-542">A **Név** és a **Leírás** mező értékét módosítsa **Termék kiadása** értékre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-542">Change the value of both the **Name** field and the **Description** field to **Release a product**.</span></span> <span data-ttu-id="ab1ea-543">Majd válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-543">Then select **Save**.</span></span>

    ![Termék kiadása névre módosult a név és leírás](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a><span data-ttu-id="ab1ea-545">Ellenőrzés funkciót tartalmazó új feladatrögzítés létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-545">Create a new task recording that has a Validate function</span></span>

- <span data-ttu-id="ab1ea-546">Hozzon létre egy új feladatrögzítést, amely kiadja a korábban létrehozott terméket az USRT jogi személynek.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-546">Create a task recording to release the product that was created earlier to the USRT legal entity.</span></span> <span data-ttu-id="ab1ea-547">További információk: [Feladatrögzítés létrehozása és mentése BPM-tárba](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-547">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1ea-548">A láncolt tesztesetekhez mindig azt ajánljuk, hogy keressen rá vagy szűrjön a szükséges mezőre *az érték manuális beírásával a mezőbe*.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-548">For chained test cases, we always recommend that you find or filter for the record that you require by *manually typing the value of the field*.</span></span> <span data-ttu-id="ab1ea-549">Ily módon az eszköz meghatározhatja azt a rekordot, amelyet a műveletnek az egymást követő teszteseteken kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-549">In that way, the tool can determine the record that the action must be taken against in the subsequent test case.</span></span>

    ![Ellenőrzés funkciót tartalmazó új feladatrögzítés](./media/setup_rsa_tool_96.png)

    <span data-ttu-id="ab1ea-551">Ahogy az előző ábra mutatja, miután a terméket megtalálta a gyorsszűrő segítségével, de mielőtt kiválasztja a **Termékek kiadása** elemet, ellenőrizze a **Termékszám** mező értékét, hogy a termékszám egyezik-e a korábban létrehozott termékszámmal.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-551">As the preceding illustration shows, after the product is found by using the Quick Filter, but before you select **Release products**, you validate the value of the **Product number** field to make sure that the product ID is the product ID that was created earlier.</span></span> <span data-ttu-id="ab1ea-552">Az érték ellenőrzéséhez kattintson a jobb gombbal a **Termékszám** mezőre, majd válassza a **Feladatrögzítő \> Ellenőrzés \> Aktuális érték**</span><span class="sxs-lookup"><span data-stu-id="ab1ea-552">To validate the value, right-click the **Product number** field, and then select **Task recorder \> Validate \> Current Value**.</span></span>

    ![Az aktuális érték ellenőrzése](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a><span data-ttu-id="ab1ea-554">Feladatrögzítés mentése a BPM-be</span><span class="sxs-lookup"><span data-stu-id="ab1ea-554">Save the task recording to BPM</span></span>

1. <span data-ttu-id="ab1ea-555">A feladatrögzítés befejezése után válassza a **Mentés a Lifecycle Services szolgáltatásba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-555">After the task recording is completed, select **Save to Lifecycle Services**.</span></span>

    ![Mentési beállítások](./media/setup_rsa_tool_98.png)

2. <span data-ttu-id="ab1ea-557">A tár adatait a rendszer az LCS-ből tölti be.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-557">Library information is loaded from LCS.</span></span>

    ![Folyamatjelző](./media/setup_rsa_tool_99.png)

3. <span data-ttu-id="ab1ea-559">Válassza ki a feladatrögzítéshez társítandó BPM-tárat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-559">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="ab1ea-560">Ehhez az oktatóanyaghoz válassza ki a korábban létrehozott **RSAT** BPM-tárat, és az alatta lévő **termék kiadása** üzleti folyamatot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-560">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Release a product** business process under it.</span></span> <span data-ttu-id="ab1ea-561">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-561">Then select **OK**.</span></span>

#### <a name="sync-bpm-to-azure-devops"></a><span data-ttu-id="ab1ea-562">BPM szinkronizálása az Azure DevOps rendszerbe</span><span class="sxs-lookup"><span data-stu-id="ab1ea-562">Sync BPM to Azure DevOps</span></span>

1. <span data-ttu-id="ab1ea-563">Nyissa meg a BPM-tárat, és nyissa meg az **RSAT** -könyvtárat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-563">Go to the BPM library, and open the **RSAT** library.</span></span>
2. <span data-ttu-id="ab1ea-564">Válassza a **VSTS szinkronizálás**, majd a **Tesztesetek szinkronizálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-564">Select **VSTS sync** and then **Sync test cases**.</span></span> <span data-ttu-id="ab1ea-565">További információk: [A BPM-ről Azure DevOps szolgáltatásba történő szinkronizálás tesztelése](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-565">For more information, see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>

    <span data-ttu-id="ab1ea-566">A szinkronizálás befejezése után az új munkaelem és a kapcsolódó teszteset a **Termék kiadása** üzleti folyamathoz megjelenik az Azure DevOps rendszerben a **Táblák \> Munkaelemek** pontban.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-566">After the synchronization is completed, the new work item and the corresponding test case for the **Release a product** business process appear in Azure DevOps at **Boards \> Work Items**.</span></span>

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a><span data-ttu-id="ab1ea-567">Az új tesztelési eset hozzáadása a meglévő tesztcsomaghoz</span><span class="sxs-lookup"><span data-stu-id="ab1ea-567">Add the new test case to the existing test suite</span></span>

1. <span data-ttu-id="ab1ea-568">Lépjen a **Tesztelési tervek \> Tesztelési tervek** menüpontba, és válassza az **RSAT tesztelési terv** tervet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-568">Go to **Test plans \> Test plans**, and select the **RSAT Test Plan** plan.</span></span>
2. <span data-ttu-id="ab1ea-569">Válassza a **Meglévő hozzáadása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-569">Select **Add existing**.</span></span>
3. <span data-ttu-id="ab1ea-570">A **Tesztesetek hozzáadása a csomaghoz** oldalon válassza a **Lekérdezés futtatása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-570">On the **Add test cases to suite** page, select **Run query**.</span></span>
4. <span data-ttu-id="ab1ea-571">Válassza ki a **Termék kiadása** címmel létrehozott új tesztesetet, majd válassza az oldal jobb alsó sarkában a **Tesztesetek hozzáadása** lehetőséget (ez a gomb nem látható az alábbi ábrán).</span><span class="sxs-lookup"><span data-stu-id="ab1ea-571">Select the new test case that was created for **Release a product**, and then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Tesztesetek hozzáadása a csomaghoz oldal](./media/setup_rsa_tool_100.png)

    <span data-ttu-id="ab1ea-573">A tesztcsomagnak most két tesztesete van.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-573">The test suite now has two test cases.</span></span>

    ![Két teszteset a tesztcsomagban](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a><span data-ttu-id="ab1ea-575">Tesztesetek betöltése az RSAT-ba</span><span class="sxs-lookup"><span data-stu-id="ab1ea-575">Load test cases into RSAT</span></span>

1. <span data-ttu-id="ab1ea-576">Nyissa meg az RSAT-ot, majd válassza a **Betöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-576">Open RSAT, and select **Load**.</span></span>
2. <span data-ttu-id="ab1ea-577">A tesztesetek betöltődnek, és megjelenik egy figyelmeztetés, amit azt írja: „Ez a művelet felülírja az Excel-tesztadatfájlokat, a helyi módosítások elvesznek.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-577">The test cases are loaded, and you receive a warning that states, "This action will overwrite Excel test data files, local changes will be lost.</span></span> <span data-ttu-id="ab1ea-578">Szeretné folytatni?”</span><span class="sxs-lookup"><span data-stu-id="ab1ea-578">Do you want to proceed?"</span></span> <span data-ttu-id="ab1ea-579">Válassza az **Igen** lehetőséget, ha szeretné a helyi rendszerben található Excel-paraméterfájlokat, de azokat az Excel-paraméterfájlokat nem, amelyeket feltöltött az Azure DevOps rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-579">Select **Yes** to update the Excel parameter files in the local system but not the Excel parameter files that were uploaded to Azure DevOps.</span></span>

    ![Figyelmeztető üzenet](./media/setup_rsa_tool_102.png)

    <span data-ttu-id="ab1ea-581">Mindkét tesztesetet betölti a rendszer az első tesztesethez tartozó Excel-paraméterfájllal együtt.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-581">Both the test cases are loaded, together with the Excel parameter file for the first test case.</span></span> <span data-ttu-id="ab1ea-582">Mivel a **Feltöltést** a legutóbbi futtatáskor kiválasztotta, a program az Azure DevOps rendszerből húzza be a paraméterfájlokat.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-582">Because you selected **Upload** in the last run, the parameter files are pulled from Azure DevOps.</span></span>

    ![A tesztesetek betöltődtek](./media/setup_rsa_tool_103.png)

3. <span data-ttu-id="ab1ea-584">Válassza ki a második tesztesetet, majd válassza az **Új \> Teszt-végrehajtási és paraméterfájlok létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-584">Select only the second test case, and then select **New \> Generate test execution and parameter files**.</span></span>

#### <a name="edit-the-excel-parameter-file"></a><span data-ttu-id="ab1ea-585">Excel-paraméterfájl szerkesztése</span><span class="sxs-lookup"><span data-stu-id="ab1ea-585">Edit the Excel parameter file</span></span>

1. <span data-ttu-id="ab1ea-586">Válassza ki csak a második tesztesetet, majd a **Szerkesztés** parancsot a kapcsolódó Excel-paraméterfájl megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-586">Select only the second test case, and then select **Edit** to open the corresponding Excel parameter file.</span></span>
2. <span data-ttu-id="ab1ea-587">Másolja az **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** mentett változót (lásd: [Meglévő feladatrögzítés módosítása mentett változó létrehozásához](#modify-an-existing-task-recording-to-create-a-saved-variable) szakaszt) az első tesztesetből a termékszámot használó összes mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-587">Copy the **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** saved variable (see the [Modify an existing task recording to create a saved variable](#modify-an-existing-task-recording-to-create-a-saved-variable) section) from the first test case into all the fields where the product number is used.</span></span> <span data-ttu-id="ab1ea-588">Ebben az esetben a változót a **Termékszám** és **Termékszám ellenőrzése** mezőkbe másolja az **EcoResProductListPage** munkafüzetben.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-588">In this case, you copy the variable into the **Product number** and **Validate Product number** fields on the **EcoResProductListPage** sheet.</span></span>

    ![Termékszám és Termékszám ellenőrzése mezők](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > <span data-ttu-id="ab1ea-590">A változók csak ugyanazon tesztfutás során adhatók át a tesztek között.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-590">Variables can be passed between tests only during the same test run.</span></span> <span data-ttu-id="ab1ea-591">A változók neveinek pontosan egyezniük kell.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-591">The names of the variables must match exactly.</span></span>

3. <span data-ttu-id="ab1ea-592">Válassza a **Mentés** gombot, majd zárja be az Excel-munkafüzetet.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-592">Select **Save**, and then close the Excel workbook.</span></span>
4. <span data-ttu-id="ab1ea-593">A **Feltöltés** gombra kattintva mentheti a módosításokat, amelyeket az Excel-paraméterfájlban tett.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-593">Select **Upload** to save the changes that you made to the Excel parameter file.</span></span>

#### <a name="run-the-chained-test-cases"></a><span data-ttu-id="ab1ea-594">A láncolt tesztesetek futtatása</span><span class="sxs-lookup"><span data-stu-id="ab1ea-594">Run the chained test cases</span></span>

1. <span data-ttu-id="ab1ea-595">Válassza ki a mindkét tesztesetet, majd válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-595">Select both the test cases, and then select **Run**.</span></span>
2. <span data-ttu-id="ab1ea-596">Ellenőrizze, hogy mindkét teszteset sikeres volt-e.</span><span class="sxs-lookup"><span data-stu-id="ab1ea-596">Verify that both test cases have passed.</span></span>

    ![Eredmény mező Sikeres értékre állítva mindkét tesztesetnél](./media/setup_rsa_tool_105.png)

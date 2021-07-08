---
title: A konfiguráció feltöltése a Lifecycle Services szolgáltatásba
description: Ez a témakör egy új Elektronikus jelentéskészítési (ER) konfiguráció létrehozására és Microsoft Dynamics Lifecycle Services (LCS) rendszerbe való feltöltésére szolgáló folyamatot mutatja be.
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41a8fcf2592bde4901aba703e0cd124b1155dac6
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270559"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="d7744-103">A konfiguráció feltöltése a Lifecycle Services szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="d7744-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d7744-104">Ez a témakör leírja, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új [Elektronikus jelentés (ER) konfigurációt](../general-electronic-reporting.md#Configuration) , és hogyan töltheti fel a [projektszintű Eszközkönyvtárba](../../lifecycle-services/asset-library.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="d7744-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7744-105">Az LCS tárolási adattárként való használata az ER-konfigurációknál [elavult](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="d7744-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="d7744-106">További információért lásd a [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) tárhely elavulása](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md) részt.</span><span class="sxs-lookup"><span data-stu-id="d7744-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="d7744-107">Ebben a példában a mintavállalatra, a Litware-ra, Inc.-re vonatkozóan létrehoz egy konfigurációs szolgáltatót, és feltölti az LCS rendszerbe. Ezek a lépések bármely vállalatnál elvégezhetők, mivel az ER-konfigurációk meg vannak osztva a vállalatok között.</span><span class="sxs-lookup"><span data-stu-id="d7744-107">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="d7744-108">Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit.</span><span class="sxs-lookup"><span data-stu-id="d7744-108">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="d7744-109">Az LCS-hez való hozzáférés is szükséges.</span><span class="sxs-lookup"><span data-stu-id="d7744-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="d7744-110">Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="d7744-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="d7744-111">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="d7744-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="d7744-112">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="d7744-112">System administrator</span></span>

2. <span data-ttu-id="d7744-113">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d7744-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="d7744-114">Válassza ki a **Litware, Inc.**, és jelölje meg **Aktív** állapotúként.</span><span class="sxs-lookup"><span data-stu-id="d7744-114">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="d7744-115">Válassza a **Konfigurációk** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-115">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="d7744-116">Győződjön meg róla, hogy az aktuális Dynamics 365 Finance felhasználó tagja annak az LCS projektnek, amely tartalmazza azt az [Eszköztárat](../../lifecycle-services/asset-library.md#asset-library-support), amely az ER-konfigurációk importálásához használatos.</span><span class="sxs-lookup"><span data-stu-id="d7744-116">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="d7744-117">Nem férhet hozzá egy LCS-projekthez egy olyan ER-adattárból, amely egy másik tartományt képvisel, mint a Finance-ben használt tartomány.</span><span class="sxs-lookup"><span data-stu-id="d7744-117">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="d7744-118">Ha megpróbálja, akkor az LCS-projektek üres listája jelenik meg, és nem fogja tudni importálni a projekt-szintű Eszközökkönyvtár ER-konfigurációit az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="d7744-118">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="d7744-119">Ahhoz, hogy a projekt-szintű Eszköztárakat egy olyan ER-adattárból elérje, amely ER-konfigurációk importálására szolgál, a Finance alkalmazásba való bejelentkezéshez olyan felhasználó hitelesítő adatait használja, aki olyan bérlőhöz (tartomány) tartozik, amelyhez az aktuális Finance-példány ki lett építve.</span><span class="sxs-lookup"><span data-stu-id="d7744-119">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="d7744-120">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="d7744-120">Create a new data model configuration</span></span>

1. <span data-ttu-id="d7744-121">Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="d7744-121">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="d7744-122">A **Konfiguráció** oldalon a **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="d7744-122">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="d7744-123">Ebben a példában olyan konfigurációt hoz létre, amely tartalmazza az elektronikus dokumentumokra vonatkozó minta adatmodellt.</span><span class="sxs-lookup"><span data-stu-id="d7744-123">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="d7744-124">Később az LCS-be töltik fel ezen adatmodell konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="d7744-124">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="d7744-125">A **Név** mezőben írja be a **Minta modellkonfiguráció** szöveget.</span><span class="sxs-lookup"><span data-stu-id="d7744-125">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="d7744-126">A **Leírás** mezőbe írja be a **Minta modellkonfiguráció** szöveget.</span><span class="sxs-lookup"><span data-stu-id="d7744-126">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="d7744-127">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-127">Select **Create configuration**.</span></span>
6. <span data-ttu-id="d7744-128">Válassza ki a **Modelltervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-128">Select **Model designer**.</span></span>
7. <span data-ttu-id="d7744-129">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-129">Select **New**.</span></span>
8. <span data-ttu-id="d7744-130">A **Név** mezőbe írja be a következőt: **Belépési pont**.</span><span class="sxs-lookup"><span data-stu-id="d7744-130">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="d7744-131">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-131">Select **Add**.</span></span>
10. <span data-ttu-id="d7744-132">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-132">Select **Save**.</span></span>
11. <span data-ttu-id="d7744-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d7744-133">Close the page.</span></span>
12. <span data-ttu-id="d7744-134">Válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-134">Select **Change status**.</span></span>
13. <span data-ttu-id="d7744-135">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-135">Select **Complete**.</span></span>
14. <span data-ttu-id="d7744-136">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-136">Select **OK**.</span></span>
15. <span data-ttu-id="d7744-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d7744-137">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="d7744-138">Új tárház regisztrálása</span><span class="sxs-lookup"><span data-stu-id="d7744-138">Register a new repository</span></span>

1. <span data-ttu-id="d7744-139">Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="d7744-139">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="d7744-140">Jelölje be a **Litware, Inc.** csempét a **Konfigurációs szolgáltatók** részben.</span><span class="sxs-lookup"><span data-stu-id="d7744-140">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="d7744-141">Kattintson a **Tárak** lehetőségre a **Litware, Inc.** lapon.</span><span class="sxs-lookup"><span data-stu-id="d7744-141">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="d7744-142">Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="d7744-142">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="d7744-143">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="d7744-143">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="d7744-144">Most hozzáadhatja az adattárat.</span><span class="sxs-lookup"><span data-stu-id="d7744-144">You can now add a new repository.</span></span>

5. <span data-ttu-id="d7744-145">A **Konfiguráció tárházának megadása** mezőbe írja be az **LCS** értéket.</span><span class="sxs-lookup"><span data-stu-id="d7744-145">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="d7744-146">Válassza a **Tárház létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-146">Select **Create repository**.</span></span>
7. <span data-ttu-id="d7744-147">A **Projekt** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d7744-147">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="d7744-148">Ebben a példában válassza a kívánt LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="d7744-148">For this example, select the desired LCS project.</span></span> <span data-ttu-id="d7744-149">[Hozzáféréssel](#accessconditions) kell rendelkeznie a projekthez.</span><span class="sxs-lookup"><span data-stu-id="d7744-149">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="d7744-150">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-150">Select **OK**.</span></span>

    <span data-ttu-id="d7744-151">Fejezze be az új tárház bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="d7744-151">Complete a new repository entry.</span></span>

9. <span data-ttu-id="d7744-152">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d7744-152">In the list, mark the selected row.</span></span>

    <span data-ttu-id="d7744-153">A példa esetében válassza ki a **LCS** tárház rekordját.</span><span class="sxs-lookup"><span data-stu-id="d7744-153">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="d7744-154">Ne feledje, hogy a regisztrált tárházat az aktuális szolgáltató megjelöli.</span><span class="sxs-lookup"><span data-stu-id="d7744-154">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="d7744-155">Más szóval csak a szolgáltató tulajdonát képező konfigurációk vihetők be ebbe a tárházba, tehát tölthetők fel a kiválasztott LCS-projektbe.</span><span class="sxs-lookup"><span data-stu-id="d7744-155">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="d7744-156">Válassza ki a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-156">Select **Open**.</span></span>

    <span data-ttu-id="d7744-157">Nyissa meg a tárházat az ER konfigurációk listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="d7744-157">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="d7744-158">Ha a kiválasztott projektet még nem használta az ER-konfigurációk megosztásához, a lista üres lesz.</span><span class="sxs-lookup"><span data-stu-id="d7744-158">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="d7744-159">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d7744-159">Close the page.</span></span>
12. <span data-ttu-id="d7744-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d7744-160">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="d7744-161">Egy konfiguráció feltöltése az LCS-be</span><span class="sxs-lookup"><span data-stu-id="d7744-161">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="d7744-162">Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="d7744-162">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="d7744-163">A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Mintamodell-konfiguráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="d7744-163">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="d7744-164">Ki kell választania a létrehozott konfigurációt, ami már be lett fejezve.</span><span class="sxs-lookup"><span data-stu-id="d7744-164">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="d7744-165">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d7744-165">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="d7744-166">Ebben a példában válassza ki a konfiguráció **Befejeződött** állapotú verzióját.</span><span class="sxs-lookup"><span data-stu-id="d7744-166">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="d7744-167">Válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-167">Select **Change status**.</span></span>
5. <span data-ttu-id="d7744-168">Válassza ki a **Megosztás** elemet.</span><span class="sxs-lookup"><span data-stu-id="d7744-168">Select **Share**.</span></span>

    <span data-ttu-id="d7744-169">A konfiguráció állapotát a program az LCS modulban **Befejezett** állapotúról **Megosztott** állapotúra módosítja.</span><span class="sxs-lookup"><span data-stu-id="d7744-169">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="d7744-170">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-170">Select **OK**.</span></span>
7. <span data-ttu-id="d7744-171">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d7744-171">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="d7744-172">Ebben a példában válassza ki a konfiguráció **Megosztott** állapotú verzióját.</span><span class="sxs-lookup"><span data-stu-id="d7744-172">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="d7744-173">Vegye figyelembe, hogy a kiválasztott verzió állapota **Kész** állapotról **Megosztott** állapotra változott.</span><span class="sxs-lookup"><span data-stu-id="d7744-173">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="d7744-174">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d7744-174">Close the page.</span></span>
9. <span data-ttu-id="d7744-175">Válassza ki a **Tárházak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-175">Select **Repositories**.</span></span>

    <span data-ttu-id="d7744-176">Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="d7744-176">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="d7744-177">Válassza ki a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7744-177">Select **Open**.</span></span>

    <span data-ttu-id="d7744-178">A példa esetében válassza ki a **LCS** tárházat, majd nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="d7744-178">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="d7744-179">Vegye figyelembe, hogy a kijelölt konfiguráció a kiválasztott projekt LCS eszközeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d7744-179">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="d7744-180">Az LCS-t a <https://lcs.dynamics.com> cím meglátogatásával nyithatja meg.</span><span class="sxs-lookup"><span data-stu-id="d7744-180">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="d7744-181">A tárház regisztrálásához korábban használt projektet nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="d7744-181">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="d7744-182">Nyissa meg a projekt eszköztárát.</span><span class="sxs-lookup"><span data-stu-id="d7744-182">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="d7744-183">Válassza a **GER-konfiguráció** eszköztípust.</span><span class="sxs-lookup"><span data-stu-id="d7744-183">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="d7744-184">A feltöltött ER-konfigurációnak listázva kell lennie.</span><span class="sxs-lookup"><span data-stu-id="d7744-184">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="d7744-185">Vegye figyelembe, hogy a feltöltött LCS konfigurációt egy másik példányába importálhatja, ha a szolgáltatók rendelkeznek hozzáféréssel ehhez az LCS projekthez.</span><span class="sxs-lookup"><span data-stu-id="d7744-185">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

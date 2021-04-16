---
title: A konfiguráció feltöltése a Lifecycle Services szolgáltatásba
description: Ez a témakör egy új Elektronikus jelentéskészítési (ER) konfiguráció létrehozására és Microsoft Dynamics Lifecycle Services (LCS) rendszerbe való feltöltésére szolgáló folyamatot mutatja be.
author: NickSelin
ms.date: 09/14/2020
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
ms.openlocfilehash: 0211fea7af303fe1dd7dce26f887bed4ed3b0f1e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744915"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="9e03b-103">A konfiguráció feltöltése a Lifecycle Services szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9e03b-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e03b-104">Ez a témakör leírja, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre új [Elektronikus jelentés (ER) konfigurációt](../general-electronic-reporting.md#Configuration) , és hogyan töltheti fel a [projektszintű Eszközkönyvtárba](../../lifecycle-services/asset-library.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="9e03b-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="9e03b-105">Ebben a példában a mintavállalatra, a Litware-ra, Inc.-re vonatkozóan létrehoz egy konfigurációs szolgáltatót, és feltölti az LCS rendszerbe. Ezek a lépések bármely vállalatnál elvégezhetők, mivel az ER-konfigurációk meg vannak osztva a vállalatok között.</span><span class="sxs-lookup"><span data-stu-id="9e03b-105">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="9e03b-106">Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit.</span><span class="sxs-lookup"><span data-stu-id="9e03b-106">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="9e03b-107">Az LCS-hez való hozzáférés is szükséges.</span><span class="sxs-lookup"><span data-stu-id="9e03b-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="9e03b-108">Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="9e03b-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="9e03b-109">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="9e03b-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="9e03b-110">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="9e03b-110">System administrator</span></span>

2. <span data-ttu-id="9e03b-111">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="9e03b-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="9e03b-112">Válassza ki a **Litware, Inc.**, és jelölje meg **Aktív** állapotúként.</span><span class="sxs-lookup"><span data-stu-id="9e03b-112">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="9e03b-113">Válassza a **Konfigurációk** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-113">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="9e03b-114">Győződjön meg róla, hogy az aktuális Dynamics 365 Finance felhasználó tagja annak az LCS projektnek, amely tartalmazza azt az [Eszköztárat](../../lifecycle-services/asset-library.md#asset-library-support), amely az ER-konfigurációk importálásához használatos.</span><span class="sxs-lookup"><span data-stu-id="9e03b-114">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="9e03b-115">Nem férhet hozzá egy LCS-projekthez egy olyan ER-adattárból, amely egy másik tartományt képvisel, mint a Finance-ben használt tartomány.</span><span class="sxs-lookup"><span data-stu-id="9e03b-115">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="9e03b-116">Ha megpróbálja, akkor az LCS-projektek üres listája jelenik meg, és nem fogja tudni importálni a projekt-szintű Eszközökkönyvtár ER-konfigurációit az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="9e03b-116">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="9e03b-117">Ahhoz, hogy a projekt-szintű Eszköztárakat egy olyan ER-adattárból elérje, amely ER-konfigurációk importálására szolgál, a Finance alkalmazásba való bejelentkezéshez olyan felhasználó hitelesítő adatait használja, aki olyan bérlőhöz (tartomány) tartozik, amelyhez az aktuális Finance-példány ki lett építve.</span><span class="sxs-lookup"><span data-stu-id="9e03b-117">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="9e03b-118">Új adatmodell-konfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="9e03b-118">Create a new data model configuration</span></span>

1. <span data-ttu-id="9e03b-119">Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="9e03b-119">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="9e03b-120">A **Konfiguráció** oldalon a **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="9e03b-120">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="9e03b-121">Ebben a példában olyan konfigurációt hoz létre, amely tartalmazza az elektronikus dokumentumokra vonatkozó minta adatmodellt.</span><span class="sxs-lookup"><span data-stu-id="9e03b-121">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="9e03b-122">Később az LCS-be töltik fel ezen adatmodell konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="9e03b-122">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="9e03b-123">A **Név** mezőben írja be a **Minta modellkonfiguráció** szöveget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-123">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="9e03b-124">A **Leírás** mezőbe írja be a **Minta modellkonfiguráció** szöveget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-124">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="9e03b-125">Válassza a **Konfiguráció létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-125">Select **Create configuration**.</span></span>
6. <span data-ttu-id="9e03b-126">Válassza ki a **Modelltervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-126">Select **Model designer**.</span></span>
7. <span data-ttu-id="9e03b-127">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-127">Select **New**.</span></span>
8. <span data-ttu-id="9e03b-128">A **Név** mezőbe írja be a következőt: **Belépési pont**.</span><span class="sxs-lookup"><span data-stu-id="9e03b-128">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="9e03b-129">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-129">Select **Add**.</span></span>
10. <span data-ttu-id="9e03b-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-130">Select **Save**.</span></span>
11. <span data-ttu-id="9e03b-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9e03b-131">Close the page.</span></span>
12. <span data-ttu-id="9e03b-132">Válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-132">Select **Change status**.</span></span>
13. <span data-ttu-id="9e03b-133">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-133">Select **Complete**.</span></span>
14. <span data-ttu-id="9e03b-134">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-134">Select **OK**.</span></span>
15. <span data-ttu-id="9e03b-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9e03b-135">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="9e03b-136">Új tárház regisztrálása</span><span class="sxs-lookup"><span data-stu-id="9e03b-136">Register a new repository</span></span>

1. <span data-ttu-id="9e03b-137">Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="9e03b-137">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="9e03b-138">Jelölje be a **Litware, Inc.** csempét a **Konfigurációs szolgáltatók** részben.</span><span class="sxs-lookup"><span data-stu-id="9e03b-138">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="9e03b-139">Kattintson a **Tárak** lehetőségre a **Litware, Inc.** lapon.</span><span class="sxs-lookup"><span data-stu-id="9e03b-139">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="9e03b-140">Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="9e03b-140">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="9e03b-141">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9e03b-141">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="9e03b-142">Most hozzáadhatja az adattárat.</span><span class="sxs-lookup"><span data-stu-id="9e03b-142">You can now add a new repository.</span></span>

5. <span data-ttu-id="9e03b-143">A **Konfiguráció tárházának megadása** mezőbe írja be az **LCS** értéket.</span><span class="sxs-lookup"><span data-stu-id="9e03b-143">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="9e03b-144">Válassza a **Tárház létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-144">Select **Create repository**.</span></span>
7. <span data-ttu-id="9e03b-145">A **Projekt** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9e03b-145">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="9e03b-146">Ebben a példában válassza a kívánt LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="9e03b-146">For this example, select the desired LCS project.</span></span> <span data-ttu-id="9e03b-147">[Hozzáféréssel](#accessconditions) kell rendelkeznie a projekthez.</span><span class="sxs-lookup"><span data-stu-id="9e03b-147">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="9e03b-148">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-148">Select **OK**.</span></span>

    <span data-ttu-id="9e03b-149">Fejezze be az új tárház bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="9e03b-149">Complete a new repository entry.</span></span>

9. <span data-ttu-id="9e03b-150">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9e03b-150">In the list, mark the selected row.</span></span>

    <span data-ttu-id="9e03b-151">A példa esetében válassza ki a **LCS** tárház rekordját.</span><span class="sxs-lookup"><span data-stu-id="9e03b-151">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="9e03b-152">Ne feledje, hogy a regisztrált tárházat az aktuális szolgáltató megjelöli.</span><span class="sxs-lookup"><span data-stu-id="9e03b-152">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="9e03b-153">Más szóval csak a szolgáltató tulajdonát képező konfigurációk vihetők be ebbe a tárházba, tehát tölthetők fel a kiválasztott LCS-projektbe.</span><span class="sxs-lookup"><span data-stu-id="9e03b-153">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="9e03b-154">Válassza ki a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-154">Select **Open**.</span></span>

    <span data-ttu-id="9e03b-155">Nyissa meg a tárházat az ER konfigurációk listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="9e03b-155">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="9e03b-156">Ha a kiválasztott projektet még nem használta az ER-konfigurációk megosztásához, a lista üres lesz.</span><span class="sxs-lookup"><span data-stu-id="9e03b-156">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="9e03b-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9e03b-157">Close the page.</span></span>
12. <span data-ttu-id="9e03b-158">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9e03b-158">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="9e03b-159">Egy konfiguráció feltöltése az LCS-be</span><span class="sxs-lookup"><span data-stu-id="9e03b-159">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="9e03b-160">Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="9e03b-160">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="9e03b-161">A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Mintamodell-konfiguráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="9e03b-161">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="9e03b-162">Ki kell választania a létrehozott konfigurációt, ami már be lett fejezve.</span><span class="sxs-lookup"><span data-stu-id="9e03b-162">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="9e03b-163">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9e03b-163">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="9e03b-164">Ebben a példában válassza ki a konfiguráció **Befejeződött** állapotú verzióját.</span><span class="sxs-lookup"><span data-stu-id="9e03b-164">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="9e03b-165">Válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-165">Select **Change status**.</span></span>
5. <span data-ttu-id="9e03b-166">Válassza ki a **Megosztás** elemet.</span><span class="sxs-lookup"><span data-stu-id="9e03b-166">Select **Share**.</span></span>

    <span data-ttu-id="9e03b-167">A konfiguráció állapotát a program az LCS modulban **Befejezett** állapotúról **Megosztott** állapotúra módosítja.</span><span class="sxs-lookup"><span data-stu-id="9e03b-167">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="9e03b-168">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-168">Select **OK**.</span></span>
7. <span data-ttu-id="9e03b-169">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9e03b-169">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="9e03b-170">Ebben a példában válassza ki a konfiguráció **Megosztott** állapotú verzióját.</span><span class="sxs-lookup"><span data-stu-id="9e03b-170">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="9e03b-171">Vegye figyelembe, hogy a kiválasztott verzió állapota **Kész** állapotról **Megosztott** állapotra változott.</span><span class="sxs-lookup"><span data-stu-id="9e03b-171">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="9e03b-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9e03b-172">Close the page.</span></span>
9. <span data-ttu-id="9e03b-173">Válassza ki a **Tárházak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-173">Select **Repositories**.</span></span>

    <span data-ttu-id="9e03b-174">Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="9e03b-174">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="9e03b-175">Válassza ki a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9e03b-175">Select **Open**.</span></span>

    <span data-ttu-id="9e03b-176">A példa esetében válassza ki a **LCS** tárházat, majd nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="9e03b-176">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="9e03b-177">Vegye figyelembe, hogy a kijelölt konfiguráció a kiválasztott projekt LCS eszközeként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="9e03b-177">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="9e03b-178">Az LCS-t a <https://lcs.dynamics.com> cím meglátogatásával nyithatja meg.</span><span class="sxs-lookup"><span data-stu-id="9e03b-178">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="9e03b-179">A tárház regisztrálásához korábban használt projektet nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="9e03b-179">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="9e03b-180">Nyissa meg a projekt eszköztárát.</span><span class="sxs-lookup"><span data-stu-id="9e03b-180">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="9e03b-181">Válassza a **GER-konfiguráció** eszköztípust.</span><span class="sxs-lookup"><span data-stu-id="9e03b-181">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="9e03b-182">A feltöltött ER-konfigurációnak listázva kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9e03b-182">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="9e03b-183">Vegye figyelembe, hogy a feltöltött LCS konfigurációt egy másik példányába importálhatja, ha a szolgáltatók rendelkeznek hozzáféréssel ehhez az LCS projekthez.</span><span class="sxs-lookup"><span data-stu-id="9e03b-183">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
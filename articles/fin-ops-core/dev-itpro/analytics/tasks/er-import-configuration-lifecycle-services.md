---
title: A konfiguráció importálása a Lifecycle Services szolgáltatásból
description: Ez a témakör azt ismerteti, hogyan lehet importálni egy Elektronikus jelentéskészítési (ER) konfiguráció új verzióját a Microsoft Dynamics Lifecycle Services (LCS) alkalmazásból.
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 602886b0dd729b8ec52940f42bd1c393dac8acda
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093695"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="3c22d-103">A konfiguráció importálása a Lifecycle Services szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="3c22d-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3c22d-104">Ez a témakör leírja, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új [Elektronikus jelentés (ER) konfigurációt](../general-electronic-reporting.md#Configuration) a [projektszintű Eszközkönyvtárból](../../lifecycle-services/asset-library.md) a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="3c22d-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="3c22d-105">Az alábbi példában kiválasztja az ER konfiguráció kívánt verzióját, majd importálja a Litware, Inc. nevű minta vállalatra vonatkozóan. Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként bármely vállalatnál elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="3c22d-105">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="3c22d-106">A lépések végrehajtásához el kell végeznie először a [Töltse fel az ER konfigurációt a Lifecycle Services rendszerbe](er-upload-configuration-into-lifecycle-services.md) eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="3c22d-106">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="3c22d-107">Az LCS-hez való hozzáférés is szükséges.</span><span class="sxs-lookup"><span data-stu-id="3c22d-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="3c22d-108">Bejelentkezés az alkalmazásba az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="3c22d-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="3c22d-109">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="3c22d-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="3c22d-110">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="3c22d-110">System administrator</span></span>

2. <span data-ttu-id="3c22d-111">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="3c22d-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="3c22d-112">Válassza a **Konfigurációk** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-112">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="3c22d-113">Győződjön meg róla, hogy az aktuális Dynamics 365 Finance felhasználó tagja annak az LCS projektnek, amely tartalmazza azt az Eszköztárat, amelyet a felhasználó [elérni](../../lifecycle-services/asset-library.md#asset-library-support) szeretne az ER-konfigurációk importálásához.</span><span class="sxs-lookup"><span data-stu-id="3c22d-113">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="3c22d-114">Nem férhet hozzá egy LCS-projekthez egy olyan ER-adattárból, amely egy másik tartományt képvisel, mint a Finance-ben használt tartomány.</span><span class="sxs-lookup"><span data-stu-id="3c22d-114">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="3c22d-115">Ha megpróbálja, akkor az LCS-projektek üres listája jelenik meg, és nem fogja tudni importálni a projekt-szintű Eszközökkönyvtár ER-konfigurációit az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="3c22d-115">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="3c22d-116">Ahhoz, hogy a projekt-szintű Eszköztárakat egy olyan ER-adattárból elérje, amely ER-konfigurációk importálására szolgál, a Finance alkalmazásba való bejelentkezéshez olyan felhasználó hitelesítő adatait használja, aki olyan bérlőhöz (tartomány) tartozik, amelyhez az aktuális Finance-példány ki lett építve.</span><span class="sxs-lookup"><span data-stu-id="3c22d-116">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="3c22d-117">Az adatmodell-konfiguráció megosztott verziójának törlése</span><span class="sxs-lookup"><span data-stu-id="3c22d-117">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="3c22d-118">A **Konfigurációk** oldalon található konfigurációk fájában válassza ki a **Mintamodell-konfiguráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="3c22d-118">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="3c22d-119">A rendszer létrehozott egy minta adatmodell konfigurációjának első verzióját és közzé tette az LCS-ben, amikro elvégezte [A konfiguráció feltöltése a Lifecycle Services szolgáltatásba](er-upload-configuration-into-lifecycle-services.md) eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="3c22d-119">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="3c22d-120">Ebben az eljárásban törli az ER-konfiguráció azon verzióját.</span><span class="sxs-lookup"><span data-stu-id="3c22d-120">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="3c22d-121">Ezt a verziót később, ebben a témakörben importálja az LCS-ből.</span><span class="sxs-lookup"><span data-stu-id="3c22d-121">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="3c22d-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3c22d-122">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3c22d-123">Ebben a példában válassza ki a **Megosztott** állapotú konfiguráció verzióját.</span><span class="sxs-lookup"><span data-stu-id="3c22d-123">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="3c22d-124">Ez az állapot azt jelzi, hogy a konfigurációt közzétették az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="3c22d-124">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="3c22d-125">Válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-125">Select **Change status**.</span></span>
4. <span data-ttu-id="3c22d-126">Válassza a **Megszüntetés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="3c22d-126">Select **Discontinue**.</span></span>

    <span data-ttu-id="3c22d-127">A kiválasztott verzió állapotának módosításával **Megosztott** állapotról **Megszüntetett** állapotra annak érdekében, hogy lehetővé váljon a verzió törlése.</span><span class="sxs-lookup"><span data-stu-id="3c22d-127">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="3c22d-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-128">Select **OK**.</span></span>
6. <span data-ttu-id="3c22d-129">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3c22d-129">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3c22d-130">Ebben a példában válassza ki a **Megszüntetett** állapotú konfiguráció verzióját.</span><span class="sxs-lookup"><span data-stu-id="3c22d-130">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="3c22d-131">Válassza a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-131">Select **Delete**.</span></span>
8. <span data-ttu-id="3c22d-132">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-132">Select **Yes**.</span></span>

    <span data-ttu-id="3c22d-133">Ne feledje, hogy a most a kijelölt adatmodell konfigurációjának csak a 2-es verziója érhető el.</span><span class="sxs-lookup"><span data-stu-id="3c22d-133">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="3c22d-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3c22d-134">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="3c22d-135">Egy adatmodell konfiguráció megosztott verziójának importálása az LCS-rendszerből</span><span class="sxs-lookup"><span data-stu-id="3c22d-135">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="3c22d-136">Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="3c22d-136">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="3c22d-137">Jelölje be a **Litware, Inc.** csempét a **Konfigurációs szolgáltatók** részben.</span><span class="sxs-lookup"><span data-stu-id="3c22d-137">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="3c22d-138">Kattintson a **Tárak** lehetőségre a **Litware, Inc.** lapon.</span><span class="sxs-lookup"><span data-stu-id="3c22d-138">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="3c22d-139">Ez lehetővé teszi a Litware, Inc. tárházak listájának megnyitását. Konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="3c22d-139">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="3c22d-140">Válassza ki a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-140">Select **Open**.</span></span>

    <span data-ttu-id="3c22d-141">A példa esetében válassza ki a **LCS** tárházat, majd nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="3c22d-141">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="3c22d-142">[Hozzá kell férnie](#accessconditions) az LCS-projekthez és a kijelölt Eszköztárhoz, amit elér az ER-adattár.</span><span class="sxs-lookup"><span data-stu-id="3c22d-142">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="3c22d-143">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3c22d-143">In the list, mark the selected row.</span></span>

    <span data-ttu-id="3c22d-144">Ehhez a példához válassza ki a **Minta modell konfiguráció** első verzióját a verziók listájában.</span><span class="sxs-lookup"><span data-stu-id="3c22d-144">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="3c22d-145">Válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-145">Select **Import**.</span></span>
7. <span data-ttu-id="3c22d-146">Válassz az **Igen** lehetőséget, hogy megerősítse a kiválasztott verzió importálását az LCS-ből.</span><span class="sxs-lookup"><span data-stu-id="3c22d-146">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="3c22d-147">Egy tájékoztató üzenet megerősíti, hogy a program sikeresen importálta a kiválasztott verziót.</span><span class="sxs-lookup"><span data-stu-id="3c22d-147">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="3c22d-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3c22d-148">Close the page.</span></span>
9. <span data-ttu-id="3c22d-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3c22d-149">Close the page.</span></span>
10. <span data-ttu-id="3c22d-150">Válassza a **Konfigurációk** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-150">Select **Configurations**.</span></span>
11. <span data-ttu-id="3c22d-151">A fastruktúrában válassza ki a **Minta modell beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c22d-151">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="3c22d-152">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3c22d-152">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3c22d-153">Ebben a példában válassza ki a **Megosztott** állapotú konfiguráció verzióját.</span><span class="sxs-lookup"><span data-stu-id="3c22d-153">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="3c22d-154">Ne feledje, hogy már a kijelölt adatmodell konfigurációjának 1-es verziója is elérhető.</span><span class="sxs-lookup"><span data-stu-id="3c22d-154">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>

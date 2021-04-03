---
title: ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából
description: Ez a témakör azt mutatja be, hogyan lehet letölteni az elektronikus jelentéskészítési (ER) konfigurációkat a konfigurációs szolgáltatás globális tárából.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c4f083163db72569d91825819a904319a0fe3123
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561902"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a><span data-ttu-id="8a230-103">ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából</span><span class="sxs-lookup"><span data-stu-id="8a230-103">Download ER configurations from the Global repository of Configuration service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a230-104">Ez a témakör azt mutatja be, hogyan lehet letölteni az [Elektronikus jelentéskészítési (ER) konfigurációkat](general-electronic-reporting.md#Configuration) a konfigurációs szolgáltatás globális tárából.</span><span class="sxs-lookup"><span data-stu-id="8a230-104">This topic explains how to download [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the Global repository of configuration service.</span></span> <span data-ttu-id="8a230-105">A további tudnivalókat lásd: [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, konfigurációs szolgáltatás](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="8a230-105">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="open-configurations-repository"></a><span data-ttu-id="8a230-106">Konfigurációs tár megnyitása</span><span class="sxs-lookup"><span data-stu-id="8a230-106">Open configurations repository</span></span>

1. <span data-ttu-id="8a230-107">Jelentkezzen be a Dynamics 365 Finance alkalmazásba az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="8a230-107">Sign in to the Dynamics 365 Finance application using one of the following roles:</span></span>

    - <span data-ttu-id="8a230-108">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="8a230-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="8a230-109">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="8a230-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="8a230-110">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="8a230-110">System administrator</span></span>

2. <span data-ttu-id="8a230-111">Ugorjon a **Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="8a230-111">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="8a230-112">Jelölje be a **Microsoft** lapot a **Konfigurációs szolgáltatók** részben.</span><span class="sxs-lookup"><span data-stu-id="8a230-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
3. <span data-ttu-id="8a230-113">Kattintson a **Tárak** lehetőségre a **Microsoft** lapon.</span><span class="sxs-lookup"><span data-stu-id="8a230-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    ![Elektronikus jelentések munkaterülete](./media/er-download-configurations-global-repo-er-workspace.png)

4. <span data-ttu-id="8a230-115">A **Konfigurációs tárak** lapon lévő rácson jelölje ki a **Globális** meglévő tárházát.</span><span class="sxs-lookup"><span data-stu-id="8a230-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **Global** type.</span></span> <span data-ttu-id="8a230-116">Ha a tárház nem jelenik meg a rácson, tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="8a230-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="8a230-117">Kattintson a **Hozzáadás** lehetőségre egy új tárház hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="8a230-117">Select **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="8a230-118">Válassza a **Globális** lehetőséget a tár típusaként, majd válassza a **Tár létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="8a230-118">Select **Global** as the repository type, and then select **Create repository**.</span></span>
    3. <span data-ttu-id="8a230-119">Ha a rendszer rákérdez, kövesse engedélyezési útmutatásokat.</span><span class="sxs-lookup"><span data-stu-id="8a230-119">If prompted, follow the authorization instructions.</span></span>
    4. <span data-ttu-id="8a230-120">Adjon nevet és leírást a tárhoz, majd kattintson az **OK** gombra a tár új bejegyzésének jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="8a230-120">Enter a name and description for the repository and then select **OK** to confirm the new repository entry.</span></span>
    5. <span data-ttu-id="8a230-121">A rácsban válassza ki a **Globális** típusú új tárat.</span><span class="sxs-lookup"><span data-stu-id="8a230-121">In the grid, select the new repository of the **Global** type.</span></span>

5. <span data-ttu-id="8a230-122">Kattintson a **Megnyitás** lehetőségre a kijelölt tárház ER-konfigurációk listájának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="8a230-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    ![Konfigurációs tárak oldal](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a><span data-ttu-id="8a230-124">Egyetlen konfiguráció importálása</span><span class="sxs-lookup"><span data-stu-id="8a230-124">Import a single configuration</span></span>

1. <span data-ttu-id="8a230-125">A **Konfigurációs tárak** oldal konfigurációs fájában válassza ki a kívánt ER-konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="8a230-125">On the **Configuration repositories** page, in the configurations tree, select the ER configuration that you want.</span></span>
2. <span data-ttu-id="8a230-126">A **Verziók** gyorslapon válassza ki a kijelölt ER-konfiguráció szükséges verzióját.</span><span class="sxs-lookup"><span data-stu-id="8a230-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
3. <span data-ttu-id="8a230-127">Kattintson az **Importálás** lehetőségre a kiválasztott verzió Globális tárból a jelenlegi Finance and Operations példányba történő letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="8a230-127">Select **Import** to download the selected version from Global repository to the current Finance instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a230-128">Az **Importálás** gomb nem érhető el azon ER konfigurációs verziókhoz, amelyek már szerepelnek az aktuális Finance-példányban.</span><span class="sxs-lookup"><span data-stu-id="8a230-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance instance.</span></span>

    ![Konfigurációk tárháza oldal](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a><span data-ttu-id="8a230-130">Szűrt konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="8a230-130">Import filtered configurations</span></span>

1. <span data-ttu-id="8a230-131">A **Konfigurációs tárak** oldalon bontsa ki a **Szűrő** gyorslapot a konfigurációs fán.</span><span class="sxs-lookup"><span data-stu-id="8a230-131">On the **Configuration repositories** page, in the configurations tree, expand the **Filter** FastTab.</span></span>
2. <span data-ttu-id="8a230-132">A **Címkék** rácsban adja meg a szükséges címkéket.</span><span class="sxs-lookup"><span data-stu-id="8a230-132">In the **Tags** grid, add any tags that are needed.</span></span>
3. <span data-ttu-id="8a230-133">Az **Ország/terület alkalmazhatósága** mezőben válassza ki a megfelelő ország-/régiókódokat, majd válassza a **Szűrő alkalmazása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="8a230-133">In the **Country/region applicability** field, select the appropriate country/region codes, and then select  **Apply filter**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a230-134">A **Konfigurációk** gyorslapon a megadott kiválasztási feltételeknek megfelelő összes konfigurációt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="8a230-134">The **Configurations** FastTab shows all the configurations that satisfy the specified selection conditions.</span></span>

4. <span data-ttu-id="8a230-135">Válassza a **Konfigurációk** gyorslap **Importálás** parancsát a szűrt konfigurációknak a globális tárból a jelenlegi példányra történő letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="8a230-135">On the **Configurations** FastTab, select **Import** to download the filtered configurations from the Global repository to the current instance.</span></span>
5. <span data-ttu-id="8a230-136">Válassza a **Konfigurációk** gyorslap **Szűrő alaphelyzetbe állítása** parancsát a megadott kiválasztási feltételek törléséhez.</span><span class="sxs-lookup"><span data-stu-id="8a230-136">On the **Configurations** FastTab, select **Reset filter** to clean up the specified selection conditions.</span></span>

    ![Konfigurációk tárháza oldal](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> <span data-ttu-id="8a230-138">Az ER beállításoktól függ a konfigurációk érvényesítése azok importálását követően.</span><span class="sxs-lookup"><span data-stu-id="8a230-138">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="8a230-139">Előfordulhat, hogy bármilyen észlelt ellentmondásos problémáról értesítést kap.</span><span class="sxs-lookup"><span data-stu-id="8a230-139">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="8a230-140">Ezeket a problémákat meg kell oldania az importált konfiguráció verziójának használata előtt.</span><span class="sxs-lookup"><span data-stu-id="8a230-140">Before you can use the imported configuration version, you must resolve the issues.</span></span> <span data-ttu-id="8a230-141">További információkért nézze meg a jelen témakörrel kapcsolatos erőforrások listáját.</span><span class="sxs-lookup"><span data-stu-id="8a230-141">For more information, see the list of related resources for this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="8a230-142">Az ER-konfigurációk konfigurálható úgy, hogy más konfigurációktól függjenek.</span><span class="sxs-lookup"><span data-stu-id="8a230-142">ER configurations can be configured as being dependent on other configurations.</span></span> <span data-ttu-id="8a230-143">Ezért a kiválasztott konfigurációval együtt előfordulhat, hogy más konfigurációk is automatikusan importálódnak.</span><span class="sxs-lookup"><span data-stu-id="8a230-143">Therefore, along with a selected configuration, other configurations might be automatically imported.</span></span> <span data-ttu-id="8a230-144">A konfiguráció függőségeivel kapcsolatos további tudnivalókat lásd: [Az ER-konfigurációk függőségének meghatározása más összetevőknél](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span><span class="sxs-lookup"><span data-stu-id="8a230-144">For more about configuration dependencies, see [Define the dependency of ER configurations on other components](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a230-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8a230-145">Additional resources</span></span>

[<span data-ttu-id="8a230-146">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="8a230-146">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
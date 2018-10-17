--- 
title: "ER - A konfiguráció importálása a Lifecycle Services szolgáltatásból"
description: "A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Lifecycle Services (LCS) rendszerből."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable,  ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 036d7e7e3f79e0945d6fef866a30edd41e688c07
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---

# <a name="er-import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="442c2-103">ER - A konfiguráció importálása a Lifecycle Services szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="442c2-103">ER Import a configuration from Lifecycle Services</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="442c2-104">A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Lifecycle Services (LCS) rendszerből.</span><span class="sxs-lookup"><span data-stu-id="442c2-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="442c2-105">Az alábbi példában kiválasztja az ER konfiguráció kívánt verzióját, majd importálja a Litware, Inc. minta vállalatra vonatkozóan. Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként bármely vállalatnál végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="442c2-105">In this example, you will select the desired version of the ER configuration and import it for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="442c2-106">A lépések végrehajtásához el kell végeznie először a „Töltse fel az ER konfigurációt a Lifecycle Services rendszerbe” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="442c2-106">To complete these steps, you must first complete the steps in the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="442c2-107">Az LCS rendszerbe való hozzáféréshez végre kell hajtani ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="442c2-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="442c2-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="442c2-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="442c2-109">Kattintson a Konfigurációk lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="442c2-109">Click Configurations.</span></span>

## <a name="delete-a-shared-version-of-data-model-configuration"></a><span data-ttu-id="442c2-110">Az adatmodell megosztott verziójának törlése</span><span class="sxs-lookup"><span data-stu-id="442c2-110">Delete a shared version of data model configuration</span></span>
1. <span data-ttu-id="442c2-111">A fastruktúrában válassza ki a „Minta modell beállítása” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="442c2-111">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="442c2-112">A rendszer létrehozott egy minta adatmodell konfigurációjának első verzióját és közzé tette az LCS-ben a számára létrehozva és a „Töltse fel az ER konfigurációt a Lifecycle Services rendszerbe eljárás“ során.</span><span class="sxs-lookup"><span data-stu-id="442c2-112">The first version of a sample data model configuration has been created and published to LCS during the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="442c2-113">Ebben az eljárásban törli az ER-konfiguráció ezen verzióját.</span><span class="sxs-lookup"><span data-stu-id="442c2-113">In this procedure, you will delete this version of the ER configuration.</span></span> <span data-ttu-id="442c2-114">A minta adatmodell konfigurációjának verzióját később importálják az LCS-ből.</span><span class="sxs-lookup"><span data-stu-id="442c2-114">This version of a sample data model configuration will be imported later from LCS.</span></span>  
2. <span data-ttu-id="442c2-115">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="442c2-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="442c2-116">Válassza ki a „Megosztott” állapotú konfiguráció verzióját.</span><span class="sxs-lookup"><span data-stu-id="442c2-116">Select the version of this configuration that is in the ‘Shared’ status.</span></span> <span data-ttu-id="442c2-117">Ez az állapot azt jelzi, hogy a konfigurációt közzétették az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="442c2-117">This status indicates that the configuration has been published to LCS.</span></span>  
3. <span data-ttu-id="442c2-118">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="442c2-118">Click Change status.</span></span>
4. <span data-ttu-id="442c2-119">Kattintson a Megszüntetés gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-119">Click Discontinue.</span></span>
    * <span data-ttu-id="442c2-120">Módosítsa a kiválasztott verzió állapotát „Megosztott” állapotról „Kifutott” állapotra annak érdekében, hogy lehetővé váljon a törlése.</span><span class="sxs-lookup"><span data-stu-id="442c2-120">Change the status of the selected version from ‘Shared’ to ‘Discontinued’ to make it available for deletion.</span></span>  
5. <span data-ttu-id="442c2-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-121">Click OK.</span></span>
6. <span data-ttu-id="442c2-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="442c2-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="442c2-123">Válassza ki a „Kifutott” állapotú konfiguráció verzióját.</span><span class="sxs-lookup"><span data-stu-id="442c2-123">Select the version of this configuration that has a status of ‘Discontinued’.</span></span>  
7. <span data-ttu-id="442c2-124">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-124">Click Delete.</span></span>
8. <span data-ttu-id="442c2-125">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-125">Click Yes.</span></span>
    * <span data-ttu-id="442c2-126">Ne feledje, hogy a kijelölt adatmodell konfigurációjának csak a 2-es verziója érhető el.</span><span class="sxs-lookup"><span data-stu-id="442c2-126">Note that the only draft version 2 of the selected data model configuration is available.</span></span>  
9. <span data-ttu-id="442c2-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="442c2-127">Close the page.</span></span>

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a><span data-ttu-id="442c2-128">Az adatmodell konfigurációjának megosztott verziójának importálása az LCS-rendszerből</span><span class="sxs-lookup"><span data-stu-id="442c2-128">Import a shared version of data model configuration from LCS</span></span>
1. <span data-ttu-id="442c2-129">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="442c2-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="442c2-130">Nyissa meg a „Litware, Inc.” vállalatra vonatkozó tárházak listáját.</span><span class="sxs-lookup"><span data-stu-id="442c2-130">Open the list of repositories for the ‘Litware, Inc.’</span></span> <span data-ttu-id="442c2-131">konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="442c2-131">configuration provider.</span></span>  
2. <span data-ttu-id="442c2-132">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-132">Click Repositories.</span></span>
3. <span data-ttu-id="442c2-133">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-133">Click Open.</span></span>
    * <span data-ttu-id="442c2-134">Válassza ki a LCS tárházat és nyissa meg.</span><span class="sxs-lookup"><span data-stu-id="442c2-134">Select the LCS repository and open it.</span></span>  
4. <span data-ttu-id="442c2-135">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="442c2-135">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="442c2-136">Válassza ki a „Minta modell konfiguráció” első verzióját a verziók listájában.</span><span class="sxs-lookup"><span data-stu-id="442c2-136">Select the first version of the 'Sample model configuration' in the versions list.</span></span>  
5. <span data-ttu-id="442c2-137">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-137">Click Import.</span></span>
6. <span data-ttu-id="442c2-138">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="442c2-138">Click Yes.</span></span>
    * <span data-ttu-id="442c2-139">Erősítse meg a kiválasztott változatot az LCS rendszerből.</span><span class="sxs-lookup"><span data-stu-id="442c2-139">Confirm the import of the selected version from LCS .</span></span>  
    * <span data-ttu-id="442c2-140">Vegye figyelembe, hogy az információs üzenet (a képernyő fölött) megerősíti a kiválasztott verzió importálásának sikeres elvégzését.</span><span class="sxs-lookup"><span data-stu-id="442c2-140">Note that the information message (above the form) confirms the successful completion of the import of the selected version.</span></span>  
7. <span data-ttu-id="442c2-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="442c2-141">Close the page.</span></span>
8. <span data-ttu-id="442c2-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="442c2-142">Close the page.</span></span>
9. <span data-ttu-id="442c2-143">Kattintson a Konfigurációk lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="442c2-143">Click Configurations.</span></span>
10. <span data-ttu-id="442c2-144">A fastruktúrában válassza ki a „Minta modell beállítása” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="442c2-144">In the tree, select 'Sample model configuration'.</span></span>
11. <span data-ttu-id="442c2-145">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="442c2-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="442c2-146">Válassza ki a „Megosztott” állapotú konfiguráció verzióját.</span><span class="sxs-lookup"><span data-stu-id="442c2-146">Select the version of this configuration that has a status of ‘Shared’.</span></span>  
    * <span data-ttu-id="442c2-147">Ne feledje, hogy már a kijelölt adatmodell konfigurációjának 1-es verziója is elérhető.</span><span class="sxs-lookup"><span data-stu-id="442c2-147">Note that the shared version 1 of the selected data model configuration is available now as well.</span></span>  



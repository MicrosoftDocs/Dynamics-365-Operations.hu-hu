---
title: Manuálisan létrehozott munkarendelések
description: Ez a cikk azt mutatja be, hogyan lehet manuálisan munkarendeléseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875692"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="945a1-103">Manuálisan létrehozott munkarendelések</span><span class="sxs-lookup"><span data-stu-id="945a1-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="945a1-104">A munkarendelések manuális létrehozására két mód van:</span><span class="sxs-lookup"><span data-stu-id="945a1-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="945a1-105">Az **Összes munkarendelés** vagy az **Aktív munkrendelések** részen</span><span class="sxs-lookup"><span data-stu-id="945a1-105">in **All work orders** or **Active work orders**</span></span>  
- <span data-ttu-id="945a1-106">Az **Összes karbantartási kérés**, az **Aktív karbantartási kérések** vagy a **Saját munkavégzési helyszínhez tartozó karbantartási kérések** részen</span><span class="sxs-lookup"><span data-stu-id="945a1-106">in **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests**</span></span>  

## <a name="create-work-order"></a><span data-ttu-id="945a1-107">Munkarendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="945a1-107">Create work order</span></span>

1. <span data-ttu-id="945a1-108">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="945a1-109">Kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="945a1-109">Click the **New** button.</span></span>

3. <span data-ttu-id="945a1-110">A **Munkarendelés létrehozása** legördülő listából válassza ki a munkarendelés típusát.</span><span class="sxs-lookup"><span data-stu-id="945a1-110">In the **Create work order** drop-down, select a work order type.</span></span>

4. <span data-ttu-id="945a1-111">Ha szükséges, válasszon ki leírást.</span><span class="sxs-lookup"><span data-stu-id="945a1-111">If required, select a description.</span></span>

5. <span data-ttu-id="945a1-112">Válassza ki az eszközt a munkarendeléshez, valamint a karbantartási feladat típusát.</span><span class="sxs-lookup"><span data-stu-id="945a1-112">Select the asset for the work order as well as a maintenance job type.</span></span>

>[!NOTE]
><span data-ttu-id="945a1-113">Az eszköz kiválasztásakor három lap érhető el: A **Saját eszközök** lap azokat a munkavégzési helyszínekhez kapcsolódó eszközöket tartalmazza, amelyekhez Önt (a rendszerre bejelentkezett dolgozót) beoszthatják (a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) részen állítható be).</span><span class="sxs-lookup"><span data-stu-id="945a1-113">When you select an asset, three tabs may be available: The **My assets** tab contains assets related to the functional locations to which you (the worker who is logged on the system) may be allocated (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)).</span></span> <span data-ttu-id="945a1-114">Ha nincs beállítva munkavégzési helyszín a dolgozóhoz a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) részen, akkor a **Saját eszközök** lap nem lesz látható.</span><span class="sxs-lookup"><span data-stu-id="945a1-114">If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab will not be visible.</span></span> <span data-ttu-id="945a1-115">Az **Aktív eszközök** lap az „Aktív” eszköz-életciklus állapotú eszközök listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="945a1-115">The **Active assets** tab contains a list of all assets with asset lifecycle state "Active".</span></span> <span data-ttu-id="945a1-116">Az **Eszköznézet** lap a munkavégzési helyszínek és a helyszínekre telepített eszközök fanézetét jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="945a1-116">The **Asset view** tab displays a tree view of functional locations and assets installed on those locations.</span></span>

6. <span data-ttu-id="945a1-117">Ha szükséges, válassza ki a **karbantartási feladat típusának változatát** és az **ügyletet**.</span><span class="sxs-lookup"><span data-stu-id="945a1-117">If required, select **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="945a1-118">Ha szükséges, módosíthatja a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.</span><span class="sxs-lookup"><span data-stu-id="945a1-118">If required, you can change the work order service level in the **Service level** field.</span></span>

8. <span data-ttu-id="945a1-119">Válassza ki a várt kezdési és befejezési dátumot a megfelelő mezőkben.</span><span class="sxs-lookup"><span data-stu-id="945a1-119">Select expected start and end dates in the related fields.</span></span>

9. <span data-ttu-id="945a1-120">Az új munkarendelés létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="945a1-120">Click **OK** to create a new work order.</span></span>

10. <span data-ttu-id="945a1-121">Ha szükséges, módosítsa a munkarendelést az **Összes munkarendelés** részen.</span><span class="sxs-lookup"><span data-stu-id="945a1-121">Edit the work order in **All work orders**, if required.</span></span>

- <span data-ttu-id="945a1-122">Az **Összes munkarendelés** részen több eszközt is hozzáadhat egy munkarendeléshez a Részletek nézetben, ha hozzáadja a sorokat a **Munkarendelés karbantartási feladatai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="945a1-122">In **All work orders**, You can add several assets to a work order in Details view by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="945a1-123">Egy eszköznél csak az eszközhöz kiválasztott eszköztípuson megadott karbantartásifeladat-típusok közül lehet választani.</span><span class="sxs-lookup"><span data-stu-id="945a1-123">On an asset, you can only select the maintenance job types that are defined on the asset type selected for the asset.</span></span>  
- <span data-ttu-id="945a1-124">Ha módosította egy eszköz szolgáltatási szintjét vagy egy eszköz kritikussági típusát, miután használta az eszközt a munkarendeléshez (lásd: [Eszköz szolgáltatásszintjei](../setup-for-objects/object-priorities.md) és [Eszközkritikusságok](../setup-for-objects/object-criticalities.md)), akkor a munkarendelésen szereplő szolgáltatási szint vagy kritikusság nem frissül ennek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="945a1-124">If you have changed an asset service level or an asset criticality after you have used them on a work order (refer to [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticalities](../setup-for-objects/object-criticalities.md)), the service level or criticality on the work order is not updated accordingly.</span></span>
- <span data-ttu-id="945a1-125">A program minden alkalommal újraszámolja a munkarendelésen szereplő kritikusságot, amikor a munkarendeléshez hozzáadnak vagy róla eltávolítanak egy munkarendelési sort.</span><span class="sxs-lookup"><span data-stu-id="945a1-125">Criticality on a work order is re-calculated each time a work order line is added or deleted on the work order.</span></span>
- <span data-ttu-id="945a1-126">Az **Összes munkarendelés** Részletek nézet > **Fejléc** nézet > **Ütemezés** gyorslapon kiválaszthatja a felelős karbantartási dolgozói csoportot vagy a felelős karbantartási dolgozót a **Felelős csoport**vagy a **Felelős** mezőben.</span><span class="sxs-lookup"><span data-stu-id="945a1-126">In **All work orders** Details view > **Header** view > **Schedule** FastTab, you can select a responsible maintenance worker group or a responsible maintenance worker in the **Responsible group** or **Responsible** fields.</span></span> <span data-ttu-id="945a1-127">Ezek a beállítások mindaddig módosíthatók, amíg a munkarendelés aktív, ha például a munkarendelés életciklus-állapota megváltozik.</span><span class="sxs-lookup"><span data-stu-id="945a1-127">These settings can be changed as long as the work order is active, for example, when the work order lifecycle state changes.</span></span> <span data-ttu-id="945a1-128">A munkarendelés létrehozása során végzett automatikus kiválasztás a **Felelős karbantartási dolgozók** rész beállításain alapul.</span><span class="sxs-lookup"><span data-stu-id="945a1-128">The automatic selection made during work order creation is based on the setup in **Responsible maintenance workers**.</span></span> <span data-ttu-id="945a1-129">Ha egy munkarendelés létrehozása után hozzáadja vagy eltávolítja a munkarendelési feladatokat, és a **Felelős csoport** és a **Felelős** mező üresen marad, amikor frissíti a munkarendelést, az Eszközkezelő esetlegesen egyező felelős karbantartási dolgozói csoportot vagy felelős karbantartási dolgozót keres a beállítási képernyőn.</span><span class="sxs-lookup"><span data-stu-id="945a1-129">If you add or remove work order jobs after you have created a work order, and the **Responsible group** field and the **Responsible** field are blank when you update the work order, Asset Management searches for a possible match in the setup form for a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="945a1-130">Ha a **Felelős csoport** vagy a **Felelős** mező ki van töltve a munkarendelés frissítésekor, akkor nem történik módosítás.</span><span class="sxs-lookup"><span data-stu-id="945a1-130">If the **Responsible group** field or the **Responsible** field is already filled out when you update the work order, no changes are made.</span></span> 

- <span data-ttu-id="945a1-131">A **Karbantartás állapota** részen számítást végezhet, hogy áttekintést kapjon a beérkező és a teljesített munkarendelésekre vonatkozó terhelésekről.</span><span class="sxs-lookup"><span data-stu-id="945a1-131">In **Maintenance status**, you can make a calculation to get an overview of workload regarding incoming and completed work orders.</span></span>  

- <span data-ttu-id="945a1-132">A **Sor részletei** gyorslapon a **Szélesség** és a **Hosszúság** mezőkben földrajzi koordinátákat adhat a munkarendelési feladathoz kiválasztott eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="945a1-132">On the **Line details** FastTab, use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset selected on the work order job.</span></span>  

## <a name="create-related-work-order"></a><span data-ttu-id="945a1-133">Kapcsolódó munkarendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="945a1-133">Create related work order</span></span>

<span data-ttu-id="945a1-134">Meglévő munkarendeléshez kapcsolódó munkarendelést is létrehozhat, ha például elsődleges és másodlagos munkarendelésekkel szeretné elvégezni a munkát.</span><span class="sxs-lookup"><span data-stu-id="945a1-134">You can create a related work order to an existing work order if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="945a1-135">Az új munkarendelés egy meglévő munkarendelésből származó munkarendelési feladaton alapul.</span><span class="sxs-lookup"><span data-stu-id="945a1-135">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="945a1-136">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-136">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="945a1-137">Válassza ki azt a munkarendelést, amelyhez kapcsolódó munkarendelést szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="945a1-137">Select the work order for which you want to make a related work order.</span></span>

3. <span data-ttu-id="945a1-138">Kattintson a **Kapcsolódó munkarendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-138">Click **Related work order**.</span></span>

4. <span data-ttu-id="945a1-139">A **Kapcsolódó munkarendelés létrehozása** legördülő párbeszédpanelen válassza ki azt a munkarendelési feladatot, amelyhez kapcsolódó munkarendelést szeretne létrehozni a **Munkarendelési feladat** mezőben.</span><span class="sxs-lookup"><span data-stu-id="945a1-139">In the **Create related work order** drop-down dialog, select the work order job for which you want to create a related work order in the **Work order job** field.</span></span>

5. <span data-ttu-id="945a1-140">Válassza ki a karbantartási feladat típusát a **Karbantartási feladat típusa** mezőben, és ha szükséges, karbantartási feladat típusának változatát és az ügyletet a **Karbantartási feladat típusának változata** és az **Ügylet** mezőben.</span><span class="sxs-lookup"><span data-stu-id="945a1-140">Select a maintenance job type in the **Maintenance job type** field and, if required, a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields.</span></span>

6. <span data-ttu-id="945a1-141">Ha ez az első létrehozandó kapcsolódó munkarendelés, kapcsolja be az **Új munkarendelés** választógombot.</span><span class="sxs-lookup"><span data-stu-id="945a1-141">If this is the first related work order you make, click the **New work order** radio button.</span></span>

7. <span data-ttu-id="945a1-142">A kapcsolódó mezőkben válasszon **Munkarendelési típust** és **leírást**.</span><span class="sxs-lookup"><span data-stu-id="945a1-142">Select a **Work order type** and a **Description** in the related fields.</span></span>

8. <span data-ttu-id="945a1-143">Ha szükséges, módosítsa a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.</span><span class="sxs-lookup"><span data-stu-id="945a1-143">If required, change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="945a1-144">Szúrja be a várt kezdési és befejezési dátumot a megfelelő mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="945a1-144">Insert expected start and end dates in the related fields.</span></span>

10. <span data-ttu-id="945a1-145">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="945a1-145">Click **OK**.</span></span> <span data-ttu-id="945a1-146">Az új kapcsolódó munkarendelés az **Összes munkarendelés** listában jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="945a1-146">The new related work order is shown in the **All work orders** list.</span></span>

11. <span data-ttu-id="945a1-147">Ha olyan munkarendeléshez hoz létre kapcsolódó munkarendelést, amelyhez már tartozik kapcsolódó munkarendelés, akkor a munkarendelési feladatot a már hozzárendelt munkarendeléshez is hozzáadhatja.</span><span class="sxs-lookup"><span data-stu-id="945a1-147">If you create a related work order on a work order that already has related work orders, you can add the work order job to an already related work order.</span></span> <span data-ttu-id="945a1-148">Ehhez jelölje be a 6. lépésben említett **Hozzáadás kapcsolódó munkarendeléshez** választógombot.</span><span class="sxs-lookup"><span data-stu-id="945a1-148">This is done by clicking the **Add to related work order** radio button in step 6.</span></span> <span data-ttu-id="945a1-149">Ezután válassza ki azt a kapcsolódó munkarendelést, amelyhez hozzá szeretné adni az új munkarendelési feladatot.</span><span class="sxs-lookup"><span data-stu-id="945a1-149">Then you select the related work order to which you want to add a new work order job.</span></span> <span data-ttu-id="945a1-150">Szükség szerint módosítsa a **Szolgáltatási szint**, a **Várható kezdés** és a **Várható befejezés** mezőt, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="945a1-150">Edit the **Service level**, **Expected start**, and **Expected end** fields, as required, and click **OK**.</span></span> <span data-ttu-id="945a1-151">A munkarendelési feladatot a program hozzáadja a meglévő kapcsolódó munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="945a1-151">The work order job is added to the existing related work order.</span></span>


![1. ábra](media/03-work-orders.png)

<span data-ttu-id="945a1-153">**Megjegyzés:** Ha egy összekapcsolt munkarendeléshez maszkot állított be az **Eszközkezelés paraméterei** > **Munkarendelések** hivatkozás > **Kapcsolódó munkarendelési maszk** mezőben, akkor a program a maszk beállításaival összhangban hozza létre a munkarendelés azonosítóit.</span><span class="sxs-lookup"><span data-stu-id="945a1-153">**Note:** If you have set up a related work order mask in **Asset management parameters** > **Work orders** link > **Related work order mask** field, work order IDs will be created in accordance with the mask setup.</span></span> <span data-ttu-id="945a1-154">Ha nincs beállítva maszk a kapcsolódó munkarendeléshez, akkor a program a következő elérhető munkarendelési azonosítót fogja használni a kapcsolódó munkarendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="945a1-154">If no related work order mask is set up, the next available work order ID will be used for related work orders.</span></span>

## <a name="copy-work-order"></a><span data-ttu-id="945a1-155">Munkarendelés másolása</span><span class="sxs-lookup"><span data-stu-id="945a1-155">Copy work order</span></span>

<span data-ttu-id="945a1-156">Meglévő munkarendelésből gyorsan lehet új munkarendelést létrehozni.</span><span class="sxs-lookup"><span data-stu-id="945a1-156">It is possible to quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="945a1-157">A munkarendelések ilyen használata különbözik a munkarendelések karbantartási tervek alapján történő létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="945a1-157">This way of working with work orders is different from creating work orders based on maintenance plans.</span></span> <span data-ttu-id="945a1-158">Ez például akkor lehet hasznos, ha a munkarendelés különböző olyan munkarendelési feladatokat tartalmaz, amelyek esetében adott időszakokban különböző eszközökön kell feladatokat elvégezni.</span><span class="sxs-lookup"><span data-stu-id="945a1-158">It is useful if, for example, you have a work order containing many work order jobs with various jobs on different assets that should be completed at regular intervals.</span></span>

1. <span data-ttu-id="945a1-159">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-159">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="945a1-160">Válassza ki azt a munkarendelést, amelynek a tartalmát le szeretné másolni.</span><span class="sxs-lookup"><span data-stu-id="945a1-160">Select the work order from which you want to copy content.</span></span>

3. <span data-ttu-id="945a1-161">Kattintson a **Munkarendelés másolása** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-161">Click **Copy work order**.</span></span> <span data-ttu-id="945a1-162">Megjelenik a kiválasztott munkarendelés beállítása.</span><span class="sxs-lookup"><span data-stu-id="945a1-162">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="945a1-163">Ha szükséges, módosíthatja a mezőket.</span><span class="sxs-lookup"><span data-stu-id="945a1-163">If required, you can edit some of the fields.</span></span>

4. <span data-ttu-id="945a1-164">Az új munkarendelés létrehozásához kattintson az **OK** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-164">Click **OK** to create the new work order.</span></span>

5. <span data-ttu-id="945a1-165">Ha szükséges, módosítsa a munkarendelést az **Összes munkarendelés** részen.</span><span class="sxs-lookup"><span data-stu-id="945a1-165">Edit the work order in **All work orders**, if required.</span></span>

>[!NOTE]
><span data-ttu-id="945a1-166">Az új munkarendelés létrehozásakor néhány információt közvetlenül a meglévő munkarendelésből másol a rendszer.</span><span class="sxs-lookup"><span data-stu-id="945a1-166">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="945a1-167">A program nem másolja át az előrejelzéseket, az eszközöket, a karbantartási ellenőrzőlistákat, a munkavégzési helyszínt, a címeket és az ütemezést, de az Eszközkezelés aktuális beállításai alapján végzi az inicializálást.</span><span class="sxs-lookup"><span data-stu-id="945a1-167">Information regarding forecasts, tools, maintenance checklists, functional location, addresses, and scheduling is not copied, but initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="945a1-168">Ez azt jelenti, hogy ha az első munkarendelés létrehozási időpontja és a munkarendelés másolása közötti időszakban módosultak a munkarendelés adatai, akkor ezek a módosítások szerepelnek az újonnan létrehozott munkarendelésben.</span><span class="sxs-lookup"><span data-stu-id="945a1-168">This means that if changes were made in those data from the time of creation of the first work order until the time you made a copy of the work order, those changes are included in the new work order you have created.</span></span> <span data-ttu-id="945a1-169">Ilyenek például az előrejelzések vagy a frissített karbantartási ellenőrzőlisták változásai.</span><span class="sxs-lookup"><span data-stu-id="945a1-169">Examples are changes in forecasts or updated maintenance checklists.</span></span>


![2. ábra](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="945a1-171">Munkarendelés létrehozása karbantartási kérés alapján</span><span class="sxs-lookup"><span data-stu-id="945a1-171">Create work order based on a maintenance request</span></span>

1. <span data-ttu-id="945a1-172">Kattintson az **Eszközkezelés** > **Közös** > **Karbantartási kérések** > **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-172">Click **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="945a1-173">Válassza ki azt a karbantartási kérést, amelyhez munkarendelést szeretne létrehozni, majd kattintson a **Szerkesztés** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-173">Select the maintenance request for which you want to create a work order, and click **Edit**.</span></span>

3. <span data-ttu-id="945a1-174">Az **Összes kérelem** részen kattintson a **Munkarendelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="945a1-174">In **All requests**, click **Work order**.</span></span>

4. <span data-ttu-id="945a1-175">Töltse ki a **Munkarendelés** legördülő listát.</span><span class="sxs-lookup"><span data-stu-id="945a1-175">Fill out the **Work order** drop-down.</span></span> <span data-ttu-id="945a1-176">Ha karbantartási feladat típust választott a karbantartási kérésben, akkor szükség esetén másik karbantartási feladattípust választhat ki, amikor létrehozza a munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="945a1-176">If a maintenance job type has been selected in the maintenance request, you are able to select another maintenance job type, if required, when you create the work order.</span></span>

5. <span data-ttu-id="945a1-177">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="945a1-177">Click **OK**.</span></span> <span data-ttu-id="945a1-178">Egy üzenet jelenik meg, amely tájékoztatja a munkarendelés létrehozásáról.</span><span class="sxs-lookup"><span data-stu-id="945a1-178">You will see a message informing you that the work order has been created.</span></span>

6. <span data-ttu-id="945a1-179">Ha meg szeretné tekinteni, hogy melyik munkarendelések kapcsolódnak karbantartási kéréshez, válassza ki a karbantartási kérést az **Összes karbantartási kérés** vagy az **Aktív karbantartási kérések** listában, és kattintson a **Munkarendelések** gombra.</span><span class="sxs-lookup"><span data-stu-id="945a1-179">If you want to see which work orders are connected to a maintenance request, select the maintenance request in the **All maintenance requests** or **Active maintenance requests** lists, and click the **Work orders** button.</span></span>


![3. ábra](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="945a1-181">A munkarendeléseket automatikusan is létrehozhatja, ha ütemezi a karbantartási terv feladatait, vagy beállítja az „Automatikus létrehozás” karbantartási terveket vagy karbantartási köröket az eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="945a1-181">Work orders can also be created automatically by scheduling maintenance plan jobs, or by setting up "Auto create" maintenance plans or maintenance rounds on an asset.</span></span> <span data-ttu-id="945a1-182">A karbantartási kérésekből a **Karbantartási ütemezés** részen munkarendeléseket a karbantartási kérésekben kiválasztott karbantartási feladattípusokkal hozza létre a program.</span><span class="sxs-lookup"><span data-stu-id="945a1-182">Work orders created from maintenance requests in **Maintenance schedule** are created with the maintenance job types selected in the maintenance requests.</span></span>


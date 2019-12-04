---
title: Manuálisan létrehozott munkarendelések
description: Ez a cikk azt mutatja be, hogyan lehet manuálisan munkarendeléseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2652458a5fea9e46b8b68d3b197d2ccb1385731d
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811744"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="d9eb9-103">Manuálisan létrehozott munkarendelések</span><span class="sxs-lookup"><span data-stu-id="d9eb9-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="d9eb9-104">A munkarendelések manuális létrehozására két mód van:</span><span class="sxs-lookup"><span data-stu-id="d9eb9-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="d9eb9-105">Az **Összes munkarendelés** vagy az **Aktív munkarendelések** oldalon</span><span class="sxs-lookup"><span data-stu-id="d9eb9-105">On the **All work orders** or **Active work orders** page</span></span> 
- <span data-ttu-id="d9eb9-106">Az **Összes karbantartási kérés**, az **Aktív karbantartási kérések** vagy a **Saját munkavégzési helyszínhez tartozó karbantartási kérések** oldalon</span><span class="sxs-lookup"><span data-stu-id="d9eb9-106">On the **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests** page</span></span> 

## <a name="create-work-order"></a><span data-ttu-id="d9eb9-107">Munkarendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="d9eb9-107">Create work order</span></span>

1. <span data-ttu-id="d9eb9-108">Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-108">Selece **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="d9eb9-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-109">Select **New**.</span></span>

3. <span data-ttu-id="d9eb9-110">A **Munkarendelés létrehozása** párbeszédpanelen válassza ki a Munkarendelés típusát a **Munkarendelés típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-110">In the **Create work order** dialog, select a work order type in the **Work order type** field.</span></span>

4. <span data-ttu-id="d9eb9-111">Ha szükséges, válasszon ki egy **Leírást**.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-111">If required, select a **Description**.</span></span>

5. <span data-ttu-id="d9eb9-112">Az **Eszköz** mezőben válassza ki az eszközt.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-112">In the **Asset** field, select the asset.</span></span>

>[!NOTE]
><span data-ttu-id="d9eb9-113">Amikor kiválaszt egy eszközt, három lap érhető el az **Eszköz** legördülő listájában:</span><span class="sxs-lookup"><span data-stu-id="d9eb9-113">When you select an asset, three tabs might be available in the **Asset** drop-down:</span></span> 

- <span data-ttu-id="d9eb9-114">**Aktív eszközök** - Ez a lap az összes olyan eszköz listáját tartalmazza, amelyek „Aktív” eszközéletciklus-állapottal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-114">**Active assets** - This tab contains a list of all assets that have an "Active" asset lifecycle state.</span></span> 
- <span data-ttu-id="d9eb9-115">**Eszköznézet** – Ez a lap a munkavégzési helyszínek és az azokra telepített eszközök fanézetét jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-115">**Asset view** - This tab displays a tree view of functional locations and the assets installed on them.</span></span>
- <span data-ttu-id="d9eb9-116">**Saját eszközök** – Ez a lap olyan eszközöket tartalmaz, amelyek az Önhöz (a rendszerbe bejelentkezett dolgozó) esetlegesen hozzárendelt munkavégzési helyszínekhez vannak hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-116">**My assets** - This tab contains assets that are related to the functional locations that you (the worker who is signed in to the system) may be allocated to.</span></span> <span data-ttu-id="d9eb9-117">(A beállítással kapcsolatos további információkért lásd: [Karbantartó dolgozók és dolgozóicsoportok](../setup-for-objects/workers-and-worker-groups.md).) Ha egy dolgozónál nem állítottak be munkavégzési helyszíneket a [Karbantartási dolgozók és a dolgozócsoportok](../setup-for-objects/workers-and-worker-groups.md) számára, akkor a **Saját eszközök** lap nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-117">(For information about the setup, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).) If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab isn't available.</span></span> 

6. <span data-ttu-id="d9eb9-118">A **Karbantartási feladat típusa** mezőben válassza ki a karbantartási feladat típusát a munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-118">In the **Maintenance job type** field, select a maintenance job type for the work order.</span></span>

7. <span data-ttu-id="d9eb9-119">Ha szükséges, válassza ki a **karbantartási feladat típusának változatát** és az **ügyletet**.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-119">If required, select **Maintenance job type variant** and **Trade**.</span></span>

8. <span data-ttu-id="d9eb9-120">Ha szükséges, módosíthatja a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-120">If required, you can change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="d9eb9-121">Válassza ki a **Várt kezdési** és **Vártbefejezési dátumokat** a megfelelő mezőkben.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-121">Select **Expected start** and **Expected end** dates in the related fields.</span></span>

10. <span data-ttu-id="d9eb9-122">Az új munkarendelés létrehozásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-122">Click **OK** to create the work order.</span></span>

11. <span data-ttu-id="d9eb9-123">Az **Összess munkarendelés** listaoldalon a munkarendelést igény szerint szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-123">On the **All work orders** list page, you can edit the work order as you require.</span></span>

<span data-ttu-id="d9eb9-124">Vegye figyelembe az alábbiakat:</span><span class="sxs-lookup"><span data-stu-id="d9eb9-124">Note the following points:</span></span>

- <span data-ttu-id="d9eb9-125">Az **Összes munkarendelés** listaoldal részletek nézetén több eszközt is hozzáadhat egy munkarendeléshez, ha hozzáadja a sorokat a **Munkarendelés karbantartási feladatai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-125">In the details view on the **All work orders** list page, you can add several assets to a work order by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="d9eb9-126">Egy eszköznél csak az eszközhöz kiválasztott eszköztípuson megadott karbantartásifeladat-típusok közül lehet választani.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-126">On an asset, you can select only the maintenance job types that are defined on the asset type that is selected on the asset.</span></span>  

- <span data-ttu-id="d9eb9-127">Ha a beállítás során módosítja az eszköz szolgáltatási szintjét vagy az eszköz kritikusságát, miután már használta az eszközt egy munkarendelésen, a munkarendelés szolgáltatási szintje vagy kritikussága nem frissül ennek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-127">If you change an asset service level or an asset criticality after you've used the asset on a work order, the service level or criticality on the work order isn't updated accordingly.</span></span> <span data-ttu-id="d9eb9-128">A szolgáltatási szintekről és a kritikusságról az [Eszközök szolgáltatási szintje](../setup-for-objects/object-priorities.md) és az [Eszközök kritikusságtípusai](../setup-for-objects/object-criticalities.md) témakörök tartalmaznak további információkat.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-128">For more information about service levels and criticalities, see [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticality types](../setup-for-objects/object-criticalities.md).</span></span>

- <span data-ttu-id="d9eb9-129">A program minden alkalommal újraszámolja a munkarendelési feladaton szereplő kritikusságot, amikor a munkarendeléshez hozzáadnak vagy róla eltávolítanak egy munkarendelési feladatot.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-129">Criticality on a work order is recalculated every time a work order job is added to or deleted from the work order.</span></span>

- <span data-ttu-id="d9eb9-130">Az **Összes munkarendelés** részletek nézet > **Fejléc** lap > **Ütemezés** gyorslapon kiválaszthatja a felelős karbantartási dolgozói csoportot vagy a felelős karbantartási dolgozót a **Felelős csoport**vagy a **Felelős** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-130">In the **All work orders** details view > **Header** tab > **Schedule** FastTab, in the **Responsible group** or **Responsible** field, you can select a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="d9eb9-131">Ezek a beállítások módosíthatók, amíg a munkarendelés aktív.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-131">These settings can be changed while the work order is active.</span></span> <span data-ttu-id="d9eb9-132">Módosíthatók például akkor, amikor a munkarendelés életciklus-állapota megváltozik.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-132">For example, they can be changed when the work order lifecycle state changes.</span></span> <span data-ttu-id="d9eb9-133">A munkarendelés létrehozása során végzett automatikus kiválasztás a **Felelős karbantartási dolgozók** oldal beállításain alapul.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-133">The automatic selection that is made during work order creation is based on the setup on the **Responsible maintenance workers** page.</span></span> <span data-ttu-id="d9eb9-134">Ha egy munkarendelés létrehozása után hozzáadja vagy eltávolítja a munkarendelési feladatokat, és a **Felelős csoport** és a **Felelős** mező üresen marad, amikor frissíti a munkarendelést, az Eszközkezelő megpróbálja megtalálni a felelős karbantartási dolgozói csoportot vagy felelős karbantartási dolgozót a beállítási képernyőn.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-134">If you add or remove work order jobs after you've created a work order, and if the **Responsible group** and **Responsible** fields are blank when you update the work order, Asset Management tries to find a responsible maintenance worker group or a responsible maintenance worker for a possible match on the setup page.</span></span> <span data-ttu-id="d9eb9-135">Ha a **Felelős csoport** mező vagy a **Felelős** mező ki már be van állítva a munkarendelés frissítésekor, akkor nem történik módosítás.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-135">If the **Responsible group** or **Responsible** field is already set when you update the work order, no changes are made.</span></span> <span data-ttu-id="d9eb9-136">A karbantartási dolgozók és karbantartási dolgozói csoportok beállítására vonatkozó további tudnivalókért tanulmányozza a [Felelős karbantartási dolgozók](../setup-for-maintenance-requests/responsible-workers.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-136">For more information about responsible maintenance workers and worker groups, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

- <span data-ttu-id="d9eb9-137">A [Karbantartás állapota](../controlling-and-reporting/maintenance-status.md) oldalon számítást végezhet, hogy áttekintést kapjon a beérkező és a teljesített munkarendelésekre vonatkozó terhelésekről.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-137">From the [Maintenance status](../controlling-and-reporting/maintenance-status.md) page, you can do a calculation to get an overview of the workload for incoming and completed work orders.</span></span>  

- <span data-ttu-id="d9eb9-138">Az **Összes munkarendelés** lap részletek nézetében a **Sor részletei** gyorslapon a A **Szélesség** és a **Hosszúság** mezőket használhatja a kijelölt eszköz földrajzi koordinátáinak hozzáadására a munkarendelési feladathoz.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-138">In the details view of the **All work orders** page, on the **Line details** FastTab, you can use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset that is selected on the work order job.</span></span>  


## <a name="create-related-work-order"></a><span data-ttu-id="d9eb9-139">Kapcsolódó munkarendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="d9eb9-139">Create related work order</span></span>

<span data-ttu-id="d9eb9-140">Olyan munkarendelést hozhat létre, amely egy meglévő munkarendeléshez kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-140">You can create a work order that is related to an existing work order.</span></span> <span data-ttu-id="d9eb9-141">Ez a képesség például akkor lehet hasznos, ha elsődleges és másodlagos munkarendelésekkel szeretne dolgozni.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-141">This capability is useful if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="d9eb9-142">Az új munkarendelés egy meglévő munkarendelésből származó munkarendelési feladaton alapul.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-142">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="d9eb9-143">Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-143">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="d9eb9-144">Válassza ki a munkarendelést, amelyhez kapcsolódó munkarendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-144">Select the work order to create a related work order for.</span></span>

3. <span data-ttu-id="d9eb9-145">A Művelet ablaktábla **Munkarendelés** lapjának **Új** csoportjában válassza a **Kapcsolódó munkarendelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-145">On the Action Pane, on the **Work order** tab, in the **New** group, select **Related work order**.</span></span>

4. <span data-ttu-id="d9eb9-146">A **Kapcsolódó munkarendelés létrehozása** legördülő párbeszédpanelen a **Munkarendelési feladat** mezőben válassza ki azt a munkarendelési feladatot, amelyhez kapcsolódó munkarendelést szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-146">In the **Create related work order** dialog, in the **Work order job** field, select the work order job to create a related work order for.</span></span>

5. <span data-ttu-id="d9eb9-147">A **Karbantartási feladat típusa** mezőben válassza ki a karbantartási feladat típusát.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-147">Select a maintenance job type in the **Maintenance job type** field.</span></span>

6. <span data-ttu-id="d9eb9-148">A **Karbantartási feladattípus változója** és a **Szakma** mezőkben igény szerint válassza ki a karbantartási feladattípushoz tartozó változatot és szakmát.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-148">Select a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields, as you require.</span></span>

7. <span data-ttu-id="d9eb9-149">Ha ez a munkarendelés a kiválasztott munkarendeléshez létrehozott első kapcsolódó munkarendelés, hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="d9eb9-149">If this work order is the first related work order that has been created for the selected work order, follow these steps:</span></span>
    1. <span data-ttu-id="d9eb9-150">Válassza ki az **Új munkarendelési** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-150">Select the **New work order** option.</span></span>
    2. <span data-ttu-id="d9eb9-151">A **Munkarendelés típusa** mezőben válasszon ki egy munkarendelés-típust.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-151">In  the **Work order type** field, select a work order type.</span></span>
    3. <span data-ttu-id="d9eb9-152">Adjon meg egy leírást a **Leírás** alatt.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-152">In the **Description**, enter a description.</span></span>
    4. <span data-ttu-id="d9eb9-153">Igény szerint módosítsa a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-153">In the **Service level** field, change the work order service level as you require.</span></span>
    5. <span data-ttu-id="d9eb9-154">A **Várható kezdés** és **Várható befejezés** mezőkben válassza ki a kezdés és a befejezés várható dátumait.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-154">In the **Expected start** and **Expected end** fields, select the expected start and end dates.</span></span>
    6. <span data-ttu-id="d9eb9-155">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-155">Select **OK**.</span></span> <span data-ttu-id="d9eb9-156">Az új kapcsolódó munkarendelés az **Összes munkarendelés** listaoldalon jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-156">The new related work order is shown on the **All work orders** list page.</span></span>  

8. <span data-ttu-id="d9eb9-157">Ha a kapcsolódó munkarendelés, amelyhez létrehozza ezt a munkarendelést már rendelkezik kapcsolódó munkarendelésekkel, akkor az alábbi lépések végrehajtásával új munkarendelési feladatot adhat hozzá egy meglévő kapcsolódó munkarendeléshez:</span><span class="sxs-lookup"><span data-stu-id="d9eb9-157">If the work order that you're creating this related work order for already has related work orders, follow these steps to add a new work order job to an existing related work order:</span></span>
    1. <span data-ttu-id="d9eb9-158">Válassza a **Hozzáadás a kapcsolódó munkarendeléshez** beállítást.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-158">Select the **Add to related work order** option.</span></span>
    2. <span data-ttu-id="d9eb9-159">A **Munkarendelés** mezőben válassza ki azt a kapcsolódó munkarendelést, amelyhez hozzá szeretné adni az új munkarendelési feladatot.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-159">In the **Work order** field, select the related work order to add a new work order job to.</span></span>
    3. <span data-ttu-id="d9eb9-160">Igény szerint módosítsa a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-160">In the **Service level** field, change the work order service level as you require.</span></span>
    4. <span data-ttu-id="d9eb9-161">A **Várható kezdés** és **Várható befejezés** mezőkben igény szerint módosítsa a kezdés és a befejezés várható dátumait.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-161">In the **Expected start** and **Expected end** fields, change the expected start and end dates as you require.</span></span>
    5. <span data-ttu-id="d9eb9-162">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-162">Select **OK**.</span></span> <span data-ttu-id="d9eb9-163">A munkarendelési feladatot a program hozzáadja a meglévő kapcsolódó munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-163">The work order job is added to the existing related work order.</span></span>

<span data-ttu-id="d9eb9-164">Az alábbi ábra a **Munkarendelés létrehozása** párbeszédpanel egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-164">The illustration below shows an example of the **Create related work order** dialog.</span></span>

![1. ábra](media/03-work-orders.png)

>[!NOTE]
><span data-ttu-id="d9eb9-166">Ha egy összekapcsolt munkarendeléshez maszkot állított be az **Eszközkezelés paraméterei** > **Munkarendelések hivatkozás** lap > **Kapcsolódó munkarendelési maszk** mezőben, akkor a program a maszk beállításaival összhangban hozza létre a munkarendelés azonosítóit.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-166">If you've set up a related work order mask in **Asset management parameters** > **Work orders** tab > **Related work order mask** field, work order IDs are created according to the mask setup.</span></span> <span data-ttu-id="d9eb9-167">Ha nincs beállítva maszk a kapcsolódó munkarendeléshez, akkor a program a következő elérhető munkarendelési azonosítót használja a kapcsolódó munkarendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-167">If no related work order mask is set up, the next available work order ID is used for related work orders.</span></span>

## <a name="copy-a-work-order"></a><span data-ttu-id="d9eb9-168">Egy munkarendelés másolása</span><span class="sxs-lookup"><span data-stu-id="d9eb9-168">Copy a work order</span></span>

<span data-ttu-id="d9eb9-169">Meglévő munkarendelésből gyorsan hozhat létre új munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-169">You can quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="d9eb9-170">A munkarendelések ilyen használata különbözik a munkarendelések [karbantartási tervek](../preventive-and-reactive-maintenance/maintenance-plans.md) alapján történő létrehozásától.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-170">This way of working with work orders differs from the creation of work orders based on [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md).</span></span> <span data-ttu-id="d9eb9-171">Ez például akkor lehet hasznos, ha a munkarendelés sok olyan munkarendelési feladatot tartalmaz, amelyek esetében adott időszakokban különböző eszközökön kell feladatokat elvégezni.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-171">It's useful if, for example, a work order contains many work order jobs, and the various jobs should be completed on different assets at regular intervals.</span></span>

1. <span data-ttu-id="d9eb9-172">Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-172">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="d9eb9-173">Válassza ki azt a munkarendelést, amelyből a tartalmat másolni szeretné.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-173">Select the work order to copy content from.</span></span>

3. <span data-ttu-id="d9eb9-174">A Művelet ablaktábla > **Munkarendelés** lapjának > **Új** csoportjában válassza a **Munkarendelés másolása** elemet.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-174">On the Action Pane > **Work order** tab > **New** group, select **Copy work order**.</span></span>

4. <span data-ttu-id="d9eb9-175">Megjelenik a kiválasztott munkarendelés beállítása.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-175">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="d9eb9-176">Igény szerint módosíthatja a mezőket.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-176">You can edit some of the fields as you require.</span></span>

5. <span data-ttu-id="d9eb9-177">Az új munkarendelés létrehozásához válassza az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-177">Select **OK** to create the new work order.</span></span>

6. <span data-ttu-id="d9eb9-178">Az **Összess munkarendelés** listaoldalon a munkarendelést igény szerint szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-178">On the **All work orders** list page, you can edit the work order as you require.</span></span>

>[!NOTE]
><span data-ttu-id="d9eb9-179">Az új munkarendelés létrehozásakor néhány információt közvetlenül a meglévő munkarendelésből másol a rendszer.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-179">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="d9eb9-180">A program nem másolja az előrejelzésekre, eszközökre, karbantartási ellenőrzőlistára, munkavégzési helyre, címekre és ütemezésre vonatkozó adatokat.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-180">Information about forecasts, tools, maintenance checklists, functional location, addresses, and scheduling isn't copied.</span></span> <span data-ttu-id="d9eb9-181">Helyette a rendszer inicializálja ezeket az aktuális beállításból az Eszközkezelés modulból.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-181">Instead, it's initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="d9eb9-182">Ezért ha az adatok megváltoztak az első munkarendelés létrehozása és a munkarendelés másolásának időpontja között, akkor a módosítások az új munkarendelésben szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-182">Therefore, if that information was changed between the time when the first work order was created and the time when you made a copy of the work order, the changes are included in the new work order.</span></span> <span data-ttu-id="d9eb9-183">Ilyenek például az előrejelzések módosításai vagy a karbantartási ellenőrzőlisták frissítései.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-183">Examples include changes to forecasts and updates to maintenance checklists.</span></span>

<span data-ttu-id="d9eb9-184">Az alábbi ábra a **Munkarendelés másolása** párbeszédpanel egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-184">The illustration below shows an example of the **Copy work order** dialog.</span></span>

![2. ábra](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="d9eb9-186">Egy munkarendelés létrehozása karbantartási kérés alapján</span><span class="sxs-lookup"><span data-stu-id="d9eb9-186">Create a work order based on a maintenance request</span></span>

1. <span data-ttu-id="d9eb9-187">Válassza az **Eszközkezelés** > **Közös** > **Karbantartási kérések** > **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** elemet.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-187">Select **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="d9eb9-188">Válassza ki azt a karbantartási kérést, amelyhez munkarendelést szeretne létrehozni, majd kattintson a **Szerkesztés** elemre.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-188">Select the maintenance request to create a work order for, and click **Edit**.</span></span>

3. <span data-ttu-id="d9eb9-189">A Művelet ablaktábla > **Karbantartási kérés** lapjának > **Új** csoportjában válassza a **Munkarendelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-189">On the Action Pane > **Maintenance request** tab > **New** group, select **Work order**.</span></span>

4. <span data-ttu-id="d9eb9-190">A **Munkarendelés** párbeszédablakban állítsa be a mezőket.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-190">In the **Work order** dialog, set the fields.</span></span> <span data-ttu-id="d9eb9-191">Ha karbantartási feladat típust választott a karbantartási kérésben, akkor igény szerint eltérő karbantartási feladattípust választhat ki, amikor létrehozza a munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-191">If a maintenance job type has been selected in the maintenance request, you can select a different maintenance job type when you create the work order, as you require.</span></span>

5. <span data-ttu-id="d9eb9-192">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-192">Select **OK**.</span></span> <span data-ttu-id="d9eb9-193">Az üzenet tájékoztatja arról, hogy a munkarendelés létrehozása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-193">A message notifies you that the work order has been created.</span></span>

6. <span data-ttu-id="d9eb9-194">A karbantartási kéréshez kapcsolódó munkarendelések megtekintéséhez az **Összes karbantartási kérés** vagy az **Aktív karbantartási kérések** listaoldalonválassza ki a karbantartási kérést.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-194">To view the work orders that are connected to a maintenance request, on the **All maintenance requests** or **Active maintenance requests** list page, select the maintenance request.</span></span> <span data-ttu-id="d9eb9-195">Majd a Művelet ablaktábla **Karbantartási kérés** lapjának **Nézet** csoportjában válassza a **Munkarendelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-195">Then, on the Action Pane, on the **Maintenance request** tab, in the **View** group, select **Work orders**.</span></span>


<span data-ttu-id="d9eb9-196">Az alábbi ábra a **Munkarendelés létrehozása** párbeszédpanel egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-196">The illustration below shows an example of the **Create work order** dialog.</span></span>

![3. ábra](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="d9eb9-198">Ha a munkarendeléseket automatikusan szeretné létrehozni, ütemezheti a karbantartási terv feladatait, vagy beállíthatja az „Automatikus létrehozású” [karbantartási terveket](../preventive-and-reactive-maintenance/maintenance-plans.md) vagy [karbantartási köröket](../preventive-and-reactive-maintenance/maintenance-rounds.md) az eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-198">If you want work orders to be created automatically, you can schedule maintenance plan jobs, or you can set up "Auto create" [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md) or [maintenance rounds](../preventive-and-reactive-maintenance/maintenance-rounds.md) on an asset.</span></span> <span data-ttu-id="d9eb9-199">A karbantartási kérések, amelyek az **Összes karbantartási ütemezés** listaoldalról vannak létrehozva a kiválasztott karbantartási feladattípusokkal hozza létre a program.</span><span class="sxs-lookup"><span data-stu-id="d9eb9-199">Work orders that are created from maintenance requests on the **All maintenance schedule** list page have the maintenance job types that are selected on the maintenance requests.</span></span>


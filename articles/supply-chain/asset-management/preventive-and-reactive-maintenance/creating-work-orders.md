---
title: Munkarendelések létrehozása
description: Ez a cikk azt mutatja be, hogyan lehet munkarendeléseket létrehozni az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3982232e5008d6f8c283d6cecfaf2fa6e66150a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836734"
---
# <a name="creating-work-orders"></a><span data-ttu-id="ad618-103">Munkarendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="ad618-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad618-104">A megelőző karbantartási feladatok ütemezése után a következő lépés a feladatok munkarendeléseinek létrehozása.</span><span class="sxs-lookup"><span data-stu-id="ad618-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="ad618-105">Ezt a lépést a karbantartási ütemezések egyikének használatával lehet végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="ad618-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="ad618-106">A karbantartási ütemezésben szereplő ütemezett feladatok különböző hivatkozási típusokkal rendelkezhetnek, ahogy azt a következő táblázat ismerteti:</span><span class="sxs-lookup"><span data-stu-id="ad618-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="ad618-107">Hivatkozás típusa</span><span class="sxs-lookup"><span data-stu-id="ad618-107">Reference type</span></span> | <span data-ttu-id="ad618-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="ad618-108">Description</span></span> |
|---|---|
| <span data-ttu-id="ad618-109">Karbantartási tervek</span><span class="sxs-lookup"><span data-stu-id="ad618-109">Maintenance plans</span></span> | <span data-ttu-id="ad618-110">Megelőző karbantartási feladatok az *Idő* vagy a *Számláló* típusú karbantartási konstrukciók alapján.</span><span class="sxs-lookup"><span data-stu-id="ad618-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="ad618-111">Karbantartási körök</span><span class="sxs-lookup"><span data-stu-id="ad618-111">Maintenance rounds</span></span> | <span data-ttu-id="ad618-112">Olyan megelőző karbantartási feladatok, amelyek számos, hasonló típusú karbantartást igénylő eszközt tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="ad618-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="ad618-113">Karbantartási kérés</span><span class="sxs-lookup"><span data-stu-id="ad618-113">Maintenance request</span></span> | <span data-ttu-id="ad618-114">Manuálisan létrehozott kérés egy eszköz karbantartására vagy javítására.</span><span class="sxs-lookup"><span data-stu-id="ad618-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="ad618-115">Ez a kérés munkarendelésre konvertálható.</span><span class="sxs-lookup"><span data-stu-id="ad618-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="ad618-116">Munkarendelések létrehozása a karbantartási ütemezés alapján</span><span class="sxs-lookup"><span data-stu-id="ad618-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="ad618-117">A karbantartási ütemezésen alapuló munkarendelések létrehozásához kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ad618-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="ad618-118">Attól függően, hogy hogyan szeretné kiválasztani a munkarendelések ütemezési elemeit, a következő lapok valamelyikét nyitja meg:</span><span class="sxs-lookup"><span data-stu-id="ad618-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="ad618-119">Minden karbantartási ütemezés (**Eszközkezelés \> Ütemezéskezelés \> Minden karbantartási ütemezés**)</span><span class="sxs-lookup"><span data-stu-id="ad618-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="ad618-120">Nyitott karbantartási ütemezési sorok (**Eszközkezelés \> Ütemezéskezelés \> Nyitott karbantartási ütemezési sorok**)</span><span class="sxs-lookup"><span data-stu-id="ad618-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="ad618-121">Nyitott karbantartási ütemezési csoportok (**Eszközkezelés \> Ütemezéskezelés \> Nyitott karbantartási ütemezési csoportok**)</span><span class="sxs-lookup"><span data-stu-id="ad618-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="ad618-122">Jelölje be a rácsban mindegyik ütemezett karbantartási feladat jelölőnégyzetét, amely számára munkarendelést szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="ad618-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="ad618-123">Majd a műveleti ablaktáblán válassza ki a **Munkarendelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="ad618-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="ad618-124">Megjelenik a **Munkarendelések létrehozása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="ad618-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="ad618-125">A kiválasztott sorokhoz tartozó összes előrejelzési órák száma a **Karbantartási előrejelzési órák** mezőben látható.</span><span class="sxs-lookup"><span data-stu-id="ad618-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Megjelenik a munkarendelések létrehozása párbeszédpanel.](media/18-preventive-maintenance.png)

1. <span data-ttu-id="ad618-127">A **Paraméterek** szakaszban adja meg a létrehozni kívánt munkarendelések számát.</span><span class="sxs-lookup"><span data-stu-id="ad618-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="ad618-128">Válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="ad618-128">Select one of the following options:</span></span>

    - <span data-ttu-id="ad618-129">**Soronként egy munkarendelés** – karbantartási ütemezési soronként egy munkarendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="ad618-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="ad618-130">**Egy munkarendelés per** – olyan munkarendelések létrehozása, amelyek a beállítás kiválasztásakor elérhetővé váló egyéb beállításoknak megfelelően csoportosítva vannak.</span><span class="sxs-lookup"><span data-stu-id="ad618-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="ad618-131">A **Munkarendelés típusa** mezőben válassza ki az összes létrehozott munkarendeléshez használni kívánt munkarendelés-típust.</span><span class="sxs-lookup"><span data-stu-id="ad618-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="ad618-132">A munkarendeléseknek a beállításoknak megfelelő létrehozásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ad618-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="ad618-133">A karbantartási terv futtatásakor automatikusan létrehozott munkarendeléssorok csoportosítása</span><span class="sxs-lookup"><span data-stu-id="ad618-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

<span data-ttu-id="ad618-134">Ezzel a funkcióval szabályokat határozhat meg a munkarendeléssorok egyetlen munkarendelés alá csoportosítására, ha a rendszer úgy van beállítva, hogy a karbantartási terv alapján automatikusan generálja a munkarendeléseket.</span><span class="sxs-lookup"><span data-stu-id="ad618-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="ad618-135">Korábban az automatikusan generált munkarendelések csak egy sort tartalmazhattak.</span><span class="sxs-lookup"><span data-stu-id="ad618-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="ad618-136">A munkarendeléseket azonban csoportosíthatja például eszköz, eszköztípus vagy működési hely szerint.</span><span class="sxs-lookup"><span data-stu-id="ad618-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="ad618-137">(A manuálisan generált munkarendelések már csoportosíthatóak a témakör előző részében leírtak szerint.)</span><span class="sxs-lookup"><span data-stu-id="ad618-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="ad618-138">Csoportosítás engedélyezése az automatikusan létrehozott munkarendelések számára</span><span class="sxs-lookup"><span data-stu-id="ad618-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="ad618-139">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="ad618-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="ad618-140">A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="ad618-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="ad618-141">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="ad618-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ad618-142">**Modul:** *Tárgyieszköz-kezelés*</span><span class="sxs-lookup"><span data-stu-id="ad618-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="ad618-143">**Funkciónév:** *A munkarendelések karbantartási terv futtatása közbeni csoportosítására vonatkozó szabályok alkalmazása*</span><span class="sxs-lookup"><span data-stu-id="ad618-143">**Feature name:** *Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="ad618-144">Csoportosítás beállítása az automatikusan létrehozott munkarendelések számára</span><span class="sxs-lookup"><span data-stu-id="ad618-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="ad618-145">Kövesse ezeket a lépéseket a csoportosítás beállításához az automatikusan létrehozott munkarendelések számára.</span><span class="sxs-lookup"><span data-stu-id="ad618-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="ad618-146">Lépjen az **Eszközkezelés \> Beállítások \> Megelőző karbantartás \> Karbantartási tervek** elemre.</span><span class="sxs-lookup"><span data-stu-id="ad618-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="ad618-147">Minden olyan tervnél, ahol csoportosított munkarendeléseket szeretne létrehozni, hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="ad618-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="ad618-148">A lista ablaktáblán válassza ki a kívánt tervet.</span><span class="sxs-lookup"><span data-stu-id="ad618-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="ad618-149">A **Sorok** gyorslapon győződjön meg arról, hogy minden sorban be legyen jelölve az **Automatikus létrehozás** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="ad618-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="ad618-150">Lépjen az **Eszközkezelés \> Időszakos \> Megelőző karbantartás \> Karbantartási tervek ütemezése** elemre.</span><span class="sxs-lookup"><span data-stu-id="ad618-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="ad618-151">A **Karbantartási tervek ütemezése** párbeszédpanel **Időszak** szakaszában adja meg a terv időhatárát (mennyire kell előre látni, amikor olyan ütemezett karbantartási feladatokat keres, amelyekhez munkát hoz létre).</span><span class="sxs-lookup"><span data-stu-id="ad618-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="ad618-152">A **Munkarendelés automatikus létrehozása ütemezés alapján** beállítás legyen *Igen*.</span><span class="sxs-lookup"><span data-stu-id="ad618-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="ad618-153">A **Munkarendelés** szakaszban válasszon a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="ad618-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="ad618-154">**Soronként egy munkarendelés** – karbantartási ütemezési soronként egy munkarendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="ad618-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="ad618-155">(Ez a beállítás ugyanazt a funkciót biztosítja, mint amely akkor érhető el, ha *A munkarendelések karbantartási terv futtatása közbeni csoportosítására vonatkozó szabályok alkalmazása* funkció ki van kapcsolva.)</span><span class="sxs-lookup"><span data-stu-id="ad618-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="ad618-156">**Egy munkarendelés per** – olyan munkarendelések létrehozása, amelyek a beállítás kiválasztásakor elérhetővé váló egyéb beállításoknak megfelelően csoportosítva vannak.</span><span class="sxs-lookup"><span data-stu-id="ad618-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="ad618-157">Ha a karbantartási tervek közül csak néhány futtatásakor szeretné alkalmazni a beállításokat, akkor a **Szerepeltetni kívánt rekordok** gyorslapon igény szerint adja meg a szükséges szűrőket, akár csak a Microsoft Dynamics 365 Supply Chain Management más kötegelt munkáinál.</span><span class="sxs-lookup"><span data-stu-id="ad618-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="ad618-158">A **Futtatás a háttérben** gyorslapon adja meg a kívánt köteg- és ütemezési beállításokat, akár csak az Supply Chain Management többi kötegelt feladatához.</span><span class="sxs-lookup"><span data-stu-id="ad618-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="ad618-159">A kiválasztott karbantartási tervek futtatásához és/vagy ütemezéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ad618-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
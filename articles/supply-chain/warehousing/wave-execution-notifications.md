---
title: Hullámvégrehajtási értesítések
description: Ez a témakör bemutatja a hullámvégrehajtási értesítéseket, és elmagyarázza, hogy kell beállítani.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2022-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 0a61aff10234f40f14d603852be30fec3ba83647
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838082"
---
# <a name="wave-execution-notifications"></a><span data-ttu-id="3b255-103">Hullámvégrehajtási értesítések</span><span class="sxs-lookup"><span data-stu-id="3b255-103">Wave execution notifications</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="3b255-104">A *Hullámvégrehajtási értesítések* funkció üzleti eseményeket és a Műveletközpontot használja a hullámvégrehajtással kapcsolatos értesítések kézbesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3b255-104">The *Wave execution notifications* feature uses business events and the Action center to deliver notifications that are related to wave execution.</span></span> <span data-ttu-id="3b255-105">Lehetővé teszi az értesítéseket létrehozó események típusainak, az azokat létrehozó raktáraknak és az ezeket fogadó felhasználóknak a megadását.</span><span class="sxs-lookup"><span data-stu-id="3b255-105">It lets you specify the types of events that generate notifications, the warehouses that generate them, and the users who receive them.</span></span>

<span data-ttu-id="3b255-106">A navigációs sáv jobb oldalán található **Üzenetek megjelenítése** gomb (harang szimbólum) jelzi, ha Műveleti központ üzenete elérhető az aktuális felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="3b255-106">The **Show messages** button (bell symbol) on the right side of the navigation bar indicates when an Action center message is available for the current user.</span></span> <span data-ttu-id="3b255-107">A felhasználó az **Üzenetek megjelenítése** gomb kiválasztásával megnyithatja a Műveleti központot, és áttekintheti az üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="3b255-107">The user can select the **Show messages** button to open the Action center and review the messages.</span></span>

<span data-ttu-id="3b255-108">Üzleti események akkor történnek, amikor üzleti folyamatok futnak.</span><span class="sxs-lookup"><span data-stu-id="3b255-108">Business events occur when business processes are run.</span></span> <span data-ttu-id="3b255-109">Az üzleti folyamatok feladatokból állnak.</span><span class="sxs-lookup"><span data-stu-id="3b255-109">Business processes are made up of tasks.</span></span> <span data-ttu-id="3b255-110">Az üzleti folyamat során az abban részt vevő felhasználók üzleti műveleteket hajtanak végre a feladatok elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="3b255-110">During a business process, the users who participate in it perform business actions to complete those tasks.</span></span> <span data-ttu-id="3b255-111">Az üzleti események olyan mechanizmust biztosítanak, amely lehetővé teszi, hogy a külső rendszerek értesítéseket kapjanak a Finance and Operations-alkalmazásoktól.</span><span class="sxs-lookup"><span data-stu-id="3b255-111">Business events provide a mechanism that lets external systems receive notifications from Finance and Operations applications.</span></span> <span data-ttu-id="3b255-112">Ily módon a rendszerek üzleti műveleteket hajtanak végre az üzleti eseményekre reagálva.</span><span class="sxs-lookup"><span data-stu-id="3b255-112">In this way, the systems can perform business actions in response to the business events.</span></span> <span data-ttu-id="3b255-113">További tájékoztatás: [Üzleti események áttekintése](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span><span class="sxs-lookup"><span data-stu-id="3b255-113">For more information, see [Business events overview](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span></span>

## <a name="turn-on-the-wave-execution-notifications-feature"></a><span data-ttu-id="3b255-114">A Hullámvégrehajtási értesítések funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="3b255-114">Turn on the Wave execution notifications feature</span></span>

<span data-ttu-id="3b255-115">A *Hullámvégrehajtási értesítések* funkciót használata előtt be kell kapcsolni a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="3b255-115">Before you can use the *Wave execution notifications* feature, it must be turned on in your system.</span></span> <span data-ttu-id="3b255-116">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="3b255-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="3b255-117">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="3b255-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="3b255-118">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="3b255-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="3b255-119">**Funkció neve:** *Hullámvégrehajtási értesítések*</span><span class="sxs-lookup"><span data-stu-id="3b255-119">**Feature name:** *Wave execution notifications*</span></span>

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a><span data-ttu-id="3b255-120">Forgatókönyv: Hullám kötegelt végrehajtási értesítések küldése a Műveleti központba</span><span class="sxs-lookup"><span data-stu-id="3b255-120">Scenario: Send wave batch execution notifications to the Action center</span></span>

<span data-ttu-id="3b255-121">Ez a forgatókönyv bemutatja a végponttól végpontig tartó folyamatot a hullám kötegelt végrehajtásával kapcsolatos hibákról szóló értesítések küldéséről egy megadott szerepkörnek a Műveleti központ használatával.</span><span class="sxs-lookup"><span data-stu-id="3b255-121">This scenario shows the end-to-end flow for sending notifications about wave batch execution errors to a specific role via the Action center.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="3b255-122">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="3b255-122">Make demo data available</span></span>

<span data-ttu-id="3b255-123">A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="3b255-123">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a><span data-ttu-id="3b255-124">Győződjön meg arról, hogy a hullámok kötegelt módban futnak</span><span class="sxs-lookup"><span data-stu-id="3b255-124">Make sure that waves are run in batch mode</span></span>

1. <span data-ttu-id="3b255-125">Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.</span><span class="sxs-lookup"><span data-stu-id="3b255-125">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="3b255-126">A **Hullámfeldolgozás** gyorslapon állítsa a **Hullámok feldolgozása kötegben** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="3b255-126">On the **Wave processing** FastTab, set the **Process waves in batch** option to *Yes*.</span></span>

> [!NOTE]
> <span data-ttu-id="3b255-127">Ha le szeretné tiltani a hullám kötegelt végrehajtásával kapcsolatos értesítéseket, állítsa a **Hullámfeldolgozás kötegelt értesítéseinek letiltása** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="3b255-127">If you want to disable wave batch execution notifications, set the **Disable wave processing batch notifications** option to *Yes*.</span></span>

### <a name="configure-a-wave-notification-policy"></a><span data-ttu-id="3b255-128">Hullámértesítési házirend konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3b255-128">Configure a wave notification policy</span></span>

<span data-ttu-id="3b255-129">A hullámértesítési házirendek határozzák meg az elküldött értesítések típusait és az értesítést kapó felhasználókat.</span><span class="sxs-lookup"><span data-stu-id="3b255-129">Wave notification policies define the types of notifications that are sent and the users who are notified.</span></span>

1. <span data-ttu-id="3b255-130">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámértesítési házirendek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b255-130">Go to **Warehouse management \> Setup \> Waves \> Wave notification policies**.</span></span>
1. <span data-ttu-id="3b255-131">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="3b255-131">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="3b255-132">**Hullámértesítési házirend:** *24BatchError*</span><span class="sxs-lookup"><span data-stu-id="3b255-132">**Wave notification policy:** *24BatchError*</span></span>
    - <span data-ttu-id="3b255-133">**Leírás:** *Raktár 24 hullám kötegelt hibája*</span><span class="sxs-lookup"><span data-stu-id="3b255-133">**Description:** *Warehouse 24 wave batch error*</span></span>
    - <span data-ttu-id="3b255-134">**Értesítés küldése:** *Csak hiba*</span><span class="sxs-lookup"><span data-stu-id="3b255-134">**Send notification on:** *Error only*</span></span>
    - <span data-ttu-id="3b255-135">**Címzett szerepkör:** *Rendszergazda*</span><span class="sxs-lookup"><span data-stu-id="3b255-135">**To role:** *System administrator*</span></span>

        > [!NOTE]
        > <span data-ttu-id="3b255-136">Mivel ez a forgatókönyv bemutatóadatokat használ, a *Rendszergazda* szerepkör az egyszerűség kedvéért van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="3b255-136">Because this scenario uses demo data, the *System administrator* role is selected for the sake of simplicity.</span></span> <span data-ttu-id="3b255-137">Ezért mivel rendszergazda felhasználóként van bejelentkezve, értesítéseket fog kapni.</span><span class="sxs-lookup"><span data-stu-id="3b255-137">Therefore, because you're signed in as a system administrator user, you will receive the notifications.</span></span> <span data-ttu-id="3b255-138">A gyakorlatban azonban általában ki kell választania egy konkrétabb szerepkört, amelynek értesítést küld a hullám kötegelt végrehajtási hibáiról, például a *Raktárkezelő* szerepkört.</span><span class="sxs-lookup"><span data-stu-id="3b255-138">However, in practice, you should usually select a more specific role to notify about wave batch execution errors, such as *Warehouse manager*.</span></span>

1. <span data-ttu-id="3b255-139">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b255-139">On the Action Pane, select **Save**.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="3b255-140">Hullámsablon konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3b255-140">Configure a wave template</span></span>

<span data-ttu-id="3b255-141">A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonokkal.</span><span class="sxs-lookup"><span data-stu-id="3b255-141">Wave templates let you link specific instances of wave methods to corresponding wave label templates.</span></span>

1. <span data-ttu-id="3b255-142">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="3b255-142">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="3b255-143">A listapanelen állítsa be a **Hullámsablontípus** mezőt *Szállítás* értékre, majd válassza a *24 szállítás alapértelmezett* hullámsablont a 24. raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="3b255-143">In the list pane, set the **Wave template type** field to *Shipping*, and then select the *24 Shipping Default* wave template for warehouse 24.</span></span>
1. <span data-ttu-id="3b255-144">Az **általános** gyorslapon adja meg a **Hullámértesítési házirend** mezőt *24BatchError* értékre.</span><span class="sxs-lookup"><span data-stu-id="3b255-144">On the **General** FastTab, set the **Wave notification policy** field to *24BatchError*.</span></span>

### <a name="configure-a-work-template"></a><span data-ttu-id="3b255-145">Munkasablon konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3b255-145">Configure a work template</span></span>

<span data-ttu-id="3b255-146">A munkasablonok a hullámvégrehajtás során a munka létrehozására használhatók.</span><span class="sxs-lookup"><span data-stu-id="3b255-146">Work templates are used during wave execution to generate work.</span></span> <span data-ttu-id="3b255-147">Ebben az esetben a hullámvégrehajtásnak hibát kell kiváltania.</span><span class="sxs-lookup"><span data-stu-id="3b255-147">For this scenario, wave execution should trigger an error.</span></span> <span data-ttu-id="3b255-148">Ha a munkasablon-lekérdezést nem létező raktár használatára állítjuk be, biztosítjuk, hogy a hullámvégrehajtás sikertelen, és ezért értesítést küld.</span><span class="sxs-lookup"><span data-stu-id="3b255-148">By setting the work template query to use a nonexistent warehouse, you will ensure that wave execution fails and therefore sends a notification.</span></span>

1. <span data-ttu-id="3b255-149">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="3b255-149">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="3b255-150">A listapanelen állítsa be a **Munkasablontípus** mezőt *Értékesítési rendelések* értékre, majd válassza a *24 SO állapot* munkasablont a 24. raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="3b255-150">In the list pane, set the **Work template type** field to *Sales orders* and then select the *24 SO Stage* work template for warehouse 24.</span></span>
1. <span data-ttu-id="3b255-151">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b255-151">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="3b255-152">A lekérdezésszerkesztő párbeszédpanelben a **Tartomány** lapján szerkessze a következő sort (vagy adja hozzá, ha nem létezik):</span><span class="sxs-lookup"><span data-stu-id="3b255-152">In the query editor dialog box, on the **Range** tab, edit the following row (or add it if it doesn't exist):</span></span>

    - <span data-ttu-id="3b255-153">**Tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="3b255-153">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="3b255-154">**Származtatott tábla:** *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="3b255-154">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="3b255-155">**Mező:** *Raktár*</span><span class="sxs-lookup"><span data-stu-id="3b255-155">**Field:** *Warehouse*</span></span>
    - <span data-ttu-id="3b255-156">**Feltételek:** Módosítsa az értéket *24*-ről *Hiba* értékre.</span><span class="sxs-lookup"><span data-stu-id="3b255-156">**Criteria:** Change the value from *24* to *Error*.</span></span>

1. <span data-ttu-id="3b255-157">Válassza az **OK** gombot, és erősítse meg a módosítást.</span><span class="sxs-lookup"><span data-stu-id="3b255-157">Select **OK**, and confirm the change.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="3b255-158">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="3b255-158">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="3b255-159">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="3b255-159">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="3b255-160">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="3b255-160">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="3b255-161">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="3b255-161">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="3b255-162">**Raktár:** *24*</span><span class="sxs-lookup"><span data-stu-id="3b255-162">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="3b255-163">Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy értékesítésirendelés-sort, amely a következő beállításokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="3b255-163">On the **Sales order lines** FastTab, add a sales order line that has the following settings:</span></span>

    - <span data-ttu-id="3b255-164">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="3b255-164">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="3b255-165">**Mennyiség:** *10*</span><span class="sxs-lookup"><span data-stu-id="3b255-165">**Quantity:** *10*</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b255-166">Ezek a cikkek és mennyiségek csak példák.</span><span class="sxs-lookup"><span data-stu-id="3b255-166">These items and quantities are only examples.</span></span> <span data-ttu-id="3b255-167">A megadott raktárban elegendő készlettel kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="3b255-167">The specified warehouse must contain enough stock.</span></span>

1. <span data-ttu-id="3b255-168">Miközben az **Értékesítésirendelés-sorok** gyorslapján az új sor továbbra is be van jelölve, akkor válassza az eszköztáron a **Készlet \> Foglalás** elemet.</span><span class="sxs-lookup"><span data-stu-id="3b255-168">While the new line is still selected on the **Sales order lines** FastTab, select **Inventory \> Reservation** on the toolbar.</span></span>
1. <span data-ttu-id="3b255-169">A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet.</span><span class="sxs-lookup"><span data-stu-id="3b255-169">On the **Reservation** page, on the Action Pane, select **Reserve lot**.</span></span> <span data-ttu-id="3b255-170">Ezután zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="3b255-170">Then close the page.</span></span>
1. <span data-ttu-id="3b255-171">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b255-171">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

### <a name="notifications-from-wave-batch-job-execution"></a><span data-ttu-id="3b255-172">Értesítések hullám kötegelt feladatának végrehajtásáról</span><span class="sxs-lookup"><span data-stu-id="3b255-172">Notifications from wave batch job execution</span></span>

<span data-ttu-id="3b255-173">Az üzleti események beállításától függően végül értesítést kap a hullámvégrehajtási hibákról.</span><span class="sxs-lookup"><span data-stu-id="3b255-173">Depending on the setup of your business events, you will eventually receive a notification about wave execution failure.</span></span> <span data-ttu-id="3b255-174">A Műveletközpont üzenete a következő példához fog hasonlítani, és egy hivatkozást tartalmaz a sikertelen hullámra.</span><span class="sxs-lookup"><span data-stu-id="3b255-174">The Action center message will resemble the following example and will include a link to the wave that failed.</span></span>

> <span data-ttu-id="3b255-175">**Hiba a hullám végrehajtása során**</span><span class="sxs-lookup"><span data-stu-id="3b255-175">**Error during wave execution**</span></span>  
> <span data-ttu-id="3b255-176">Hiba történt a USMF-000000001 hullám végrehajtása során.</span><span class="sxs-lookup"><span data-stu-id="3b255-176">An error occurred while executing wave USMF-000000001.</span></span>  
> <span data-ttu-id="3b255-177">Utolsó üzenetek: Nem jött létre munka a USMF-000000001 hullámhoz.</span><span class="sxs-lookup"><span data-stu-id="3b255-177">Last messages: No Work was created for Wave USMF-000000001.</span></span>
>
> <span data-ttu-id="3b255-178">**ÁLLAPOT**</span><span class="sxs-lookup"><span data-stu-id="3b255-178">**STATUS**</span></span>  
> <span data-ttu-id="3b255-179">Aktív</span><span class="sxs-lookup"><span data-stu-id="3b255-179">Active</span></span>
>
> <span data-ttu-id="3b255-180">Nyitott hullámrészletek</span><span class="sxs-lookup"><span data-stu-id="3b255-180">Open wave details</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

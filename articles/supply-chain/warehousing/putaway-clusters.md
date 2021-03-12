---
title: Betárolási fürtök
description: A betárolási fürtökkel egyszerre több azonosítótábla felvételére is lehetőség van, majd a különböző helyeken történő betárolására. Rendkívül hasznosak lehetnek a kiskereskedelmi vállalatok számára, ahol az azonosítótábla általában nem teljes raklapnyi készletet jelentenek.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 297792e90b3d2da0d738f5cbaa14779bc17ea3c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996198"
---
# <a name="putaway-clusters"></a><span data-ttu-id="f1460-104">Betárolási fürtök</span><span class="sxs-lookup"><span data-stu-id="f1460-104">Putaway clusters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f1460-105">A betárolási fürtökkel egyszerre több azonosítótábla felvételére is lehetőség van, majd a különböző helyeken történő betárolására.</span><span class="sxs-lookup"><span data-stu-id="f1460-105">Putaway clusters offer a way to pick multiple license plates at the same time and then take them for putaway in different locations.</span></span> <span data-ttu-id="f1460-106">Ezt az folyamatot gyakran nevezik *gyűjtőszállítmánynak*.</span><span class="sxs-lookup"><span data-stu-id="f1460-106">This process is often referred to as a *milk run*.</span></span> <span data-ttu-id="f1460-107">A betárolási fürtök rendkívül hasznosak lehetnek a kiskereskedelmi vállalatok számára, ahol az azonosítótábla általában nem teljes raklapnyi készletet jelentenek.</span><span class="sxs-lookup"><span data-stu-id="f1460-107">Putaway clusters can be very useful for retail businesses, where license plates typically aren't full pallets of inventory.</span></span> 

## <a name="turn-on-the-cluster-putaway-feature"></a><span data-ttu-id="f1460-108">A fürtbetárolási funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="f1460-108">Turn on the cluster putaway feature</span></span>

<span data-ttu-id="f1460-109">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="f1460-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="f1460-110">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="f1460-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f1460-111">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="f1460-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f1460-112">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="f1460-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f1460-113">**Szolgáltatás neve:** *Fürtbetárolási funkció*</span><span class="sxs-lookup"><span data-stu-id="f1460-113">**Feature name:** *Cluster putaway feature*</span></span>

## <a name="setup-for-the-example-scenario"></a><span data-ttu-id="f1460-114">Beállítás a példahelyzethez</span><span class="sxs-lookup"><span data-stu-id="f1460-114">Setup for the example scenario</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="f1460-115">Fürtprofilok</span><span class="sxs-lookup"><span data-stu-id="f1460-115">Cluster profiles</span></span>

<span data-ttu-id="f1460-116">A betárolási fürt profilja határozza meg, hogy hova kerülnek a cikkek a bevételezés időpontjában a cikkhez társított hely alapján.</span><span class="sxs-lookup"><span data-stu-id="f1460-116">The putaway cluster profile determines where an item will go, based on the location that is assigned to the item at the time of receipt.</span></span> <span data-ttu-id="f1460-117">Ha különböző fürtökre van szükség, akkor minden mobileszköz-menüelemhez egy másik betárolási fürtöt kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="f1460-117">If different clusters are required, different putaway clusters should be created, one for each mobile device menu item.</span></span>

1. <span data-ttu-id="f1460-118">Kattintson a **Raktárkezelés \> Beállítás \> Mobileszköz \> Fürtprofilok** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1460-118">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="f1460-119">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1460-119">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f1460-120">A **Fejléc** nézetben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="f1460-120">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="f1460-121">**Betárolási fürt profiljának azonosítója:** *Fürtbetárolás*</span><span class="sxs-lookup"><span data-stu-id="f1460-121">**Putaway cluster profile ID:** *Cluster putaway*</span></span>
    - <span data-ttu-id="f1460-122">**Betárolási fürt profiljának neve:** *Fürtbetárolás*</span><span class="sxs-lookup"><span data-stu-id="f1460-122">**Putaway cluster profile ID Name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="f1460-123">**Fürttípus:** *Betárolási*</span><span class="sxs-lookup"><span data-stu-id="f1460-123">**Cluster type:** *Putaway*</span></span>
    - <span data-ttu-id="f1460-124">**Sorszám:** Fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="f1460-124">**Sequence number:** Accept the default value.</span></span>

1. <span data-ttu-id="f1460-125">A **Mentés** gombra kattintva elérhetővé válnak az **Általános** gyorslap kötelező mezői.</span><span class="sxs-lookup"><span data-stu-id="f1460-125">Select **Save** to make the required fields on the **General** FastTab available.</span></span>
1. <span data-ttu-id="f1460-126">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="f1460-126">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f1460-127">**Fürthozzárendelés ütemezése:** *Bevételezésnél*</span><span class="sxs-lookup"><span data-stu-id="f1460-127">**Cluster assignment timing:** *At receipt*</span></span>

        <span data-ttu-id="f1460-128">Ez a mező határozza meg, hogy a betárolási fürtöt azonnal hozzá kell-e rendelni a készlet beérkezésekor, vagy később kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="f1460-128">This field defines whether the putaway cluster should be assigned immediately when the inventory is received, or whether it should be sorted later.</span></span>

    - <span data-ttu-id="f1460-129">**Fürthozzárendelési szabály:** *Manuális*</span><span class="sxs-lookup"><span data-stu-id="f1460-129">**Cluster assignment rule:** *Manual*</span></span>

        <span data-ttu-id="f1460-130">Ez a mező meghatározza, hogy a fürt hozzárendelését automatikusan határozza meg a rendszer, vagy manuálisan a felhasználó.</span><span class="sxs-lookup"><span data-stu-id="f1460-130">This field defines whether the cluster assignment should be determined automatically by the system or manually by the user.</span></span>

    - <span data-ttu-id="f1460-131">**Utasításkód:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="f1460-131">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="f1460-132">**Betárolási fürt keresése:** *Bevételezés*</span><span class="sxs-lookup"><span data-stu-id="f1460-132">**Putaway cluster locate:** *Receipt*</span></span>

        <span data-ttu-id="f1460-133">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="f1460-133">The following values are available:</span></span>

        - <span data-ttu-id="f1460-134">**Bevételezés** – A hely keresése azonnal, a bevételezés során.</span><span class="sxs-lookup"><span data-stu-id="f1460-134">**Receipt** – A location is found immediately during receipt.</span></span>
        - <span data-ttu-id="f1460-135">**Fürt lezárása** – A hely keresése a fürt lezárásakor.</span><span class="sxs-lookup"><span data-stu-id="f1460-135">**Cluster close** – A location is found when the cluster is closed.</span></span>
        - <span data-ttu-id="f1460-136">**Felhasználó által irányított** – A hely keresése akkor történik, amikor az azonosítótábla kitárolásra kerül a betárolási fürtből.</span><span class="sxs-lookup"><span data-stu-id="f1460-136">**User directed** – A location is found when the license plate is picked from the cluster for putaway.</span></span> <span data-ttu-id="f1460-137">Ebben az esetben a betárolási munka létrehozásakor nincs megadva hely.</span><span class="sxs-lookup"><span data-stu-id="f1460-137">In this case, no location is specified when the putaway work is created.</span></span> <span data-ttu-id="f1460-138">Maga a betárolás során a felhasználónak be kell olvasnia az azonosítótáblát vagy munkaazonosítót a betárolási lépés kezdeményezéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1460-138">During the putaway itself, the user must scan the license plate or work ID to initiate the put step.</span></span> <span data-ttu-id="f1460-139">A rendszer ezután megkeresi a betárolási helyet, és megadja a felhasználó számára, hogy hová tegye a kitárolt mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-139">The system then finds the put location again and tells the user where to put the picked quantity.</span></span>

    - <span data-ttu-id="f1460-140">**Betárolási fürt felhasználónként:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="f1460-140">**Putaway cluster per user:** *No*</span></span>

        <span data-ttu-id="f1460-141">Ez a mező határozza meg, hogy az egyes fürtöket felhasználónként kell-e egyedivé tenni a fürtök automatikus hozzárendelésekor.</span><span class="sxs-lookup"><span data-stu-id="f1460-141">This field defines whether each cluster should be unique per user when clusters are automatically assigned.</span></span> <span data-ttu-id="f1460-142">Csak akkor érhető el, ha a **Fürthozzárendelési szabály** mezője *Automatikus* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="f1460-142">It's available only when the **Cluster assignment rule** field is set to *Automatic*.</span></span>

    - <span data-ttu-id="f1460-143">**Egység korlátozása:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="f1460-143">**Unit restriction:** Leave this field blank.</span></span>

        <span data-ttu-id="f1460-144">Ez a mező határozza meg, hogy melyik egységet kell fogadnia a profilnak, hogy érvényes legyen.</span><span class="sxs-lookup"><span data-stu-id="f1460-144">This field defines the unit that must be received for the profile to be valid.</span></span> <span data-ttu-id="f1460-145">Ha üresen marad, akkor az összes egység érvényes lesz.</span><span class="sxs-lookup"><span data-stu-id="f1460-145">If it's left blank, all units are valid.</span></span>

    - <span data-ttu-id="f1460-146">**Munka a szünetig:** *Egyéni*</span><span class="sxs-lookup"><span data-stu-id="f1460-146">**Work unit break:** *Individual*</span></span>

        <span data-ttu-id="f1460-147">Ez a mező határozza meg, hogy az összes készletet összesíteni kell-e (a fürtazonosító és az azonosítótábla használatával) egy adott azonosítótáblára, amikor egy fürt le van zárva, és hogy a betárolás egyetlen azonosítótáblaként történjen vagy külön, a bevételezett azonosítótáblákra.</span><span class="sxs-lookup"><span data-stu-id="f1460-147">This field defines whether all inventory should be consolidated (by using the cluster ID and the license plate) onto one license plate when a cluster is closed, and whether it should be put away as a single license plate or separately on the license plates that were received.</span></span> <span data-ttu-id="f1460-148">Ez a mező nem érhető el, ha a **Betárolási fürt keresése** mező a *Bevételezés* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="f1460-148">This field is unavailable when the **Putaway cluster locate** field is set to *Receipt*.</span></span>

    - <span data-ttu-id="f1460-149">**Fürt megőrzése szülő azonosítótáblaként:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="f1460-149">**Cluster persists as Parent License Plate:** *No*</span></span>

        <span data-ttu-id="f1460-150">Ha ez a beállítás *Igen* értékre van állítva, akkor az adott lépés végrehajtásakor a fürtazonosító egy szülő azonosítótáblává válik, és a fürtazonosító minden cikke ehhez a szülő azonosítótáblához lesz kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="f1460-150">If this option is set to *Yes*, when the put step is completed, the cluster ID will become a parent license plate, and all items on the cluster ID will be linked to that parent license plate.</span></span>

1. <span data-ttu-id="f1460-151">A **Fürt rendezése** gyorslapon meghatározhatja a betárolás rendezési feltételeit.</span><span class="sxs-lookup"><span data-stu-id="f1460-151">On the **Cluster sorting** FastTab, you can define putaway sorting criteria.</span></span> <span data-ttu-id="f1460-152">Válassza az **Új** lehetőséget az eszköztáron egy sor hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="f1460-152">Select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="f1460-153">**Sorszám:** Fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="f1460-153">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="f1460-154">**Mező neve:** *WMSLocationId*</span><span class="sxs-lookup"><span data-stu-id="f1460-154">**Field name:** *WMSLocationId*</span></span>

        <span data-ttu-id="f1460-155">Ez a mező azt a mezőt határozza meg, amelyet ennek a sornak rendezési feltételként kell használnia.</span><span class="sxs-lookup"><span data-stu-id="f1460-155">This field defines the field that this line should use as a sorting criterion.</span></span>

    - <span data-ttu-id="f1460-156">**Rendezés:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="f1460-156">**Sorting:** *Ascending*</span></span>

        <span data-ttu-id="f1460-157">Ez a mező határozza meg, hogy a rendezés növekvő vagy csökkenő sorrendben történjen-e.</span><span class="sxs-lookup"><span data-stu-id="f1460-157">This field defines whether sorting should be done in ascending or descending order.</span></span>

1. <span data-ttu-id="f1460-158">A **Fürt munkasablonja** gyorslapon válassza az **Új** parancsot az eszköztáron egy sor hozzáadásához, majd állítsa be a következő értékeket hozzá:</span><span class="sxs-lookup"><span data-stu-id="f1460-158">On the **Cluster work template** FastTab, select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="f1460-159">**Munkarendelés típusa:** *Beszerzési rendelések*</span><span class="sxs-lookup"><span data-stu-id="f1460-159">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="f1460-160">**Munkasablon:** *61 közvetlen beszerzési rendelés*</span><span class="sxs-lookup"><span data-stu-id="f1460-160">**Work template:** *61 PO Direct*</span></span>

1. <span data-ttu-id="f1460-161">Válassza a művelet panel **Mentés** elemét, majd válassza a **Lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1460-161">On the Action Pane, select **Save**, and then select **Edit query**.</span></span>
1. <span data-ttu-id="f1460-162">A **Fürtbetárolás** párbeszédpanelen, a **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy második sort a lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="f1460-162">In the **Cluster putaway** dialog box, on the **Range** tab, select **Add** to add a second line to the query.</span></span> <span data-ttu-id="f1460-163">Ezután frissítse a lekérdezés sorait a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="f1460-163">Then update the query lines as shown in the following table.</span></span>

    | <span data-ttu-id="f1460-164">Tábla</span><span class="sxs-lookup"><span data-stu-id="f1460-164">Table</span></span> | <span data-ttu-id="f1460-165">Származtatott tábla</span><span class="sxs-lookup"><span data-stu-id="f1460-165">Derived table</span></span> | <span data-ttu-id="f1460-166">Mező</span><span class="sxs-lookup"><span data-stu-id="f1460-166">Field</span></span> | <span data-ttu-id="f1460-167">Feltételek</span><span class="sxs-lookup"><span data-stu-id="f1460-167">Criteria</span></span> |
    |---|---|---|---|
    | <span data-ttu-id="f1460-168">Munka</span><span class="sxs-lookup"><span data-stu-id="f1460-168">Work</span></span> | <span data-ttu-id="f1460-169">Munka</span><span class="sxs-lookup"><span data-stu-id="f1460-169">Work</span></span> | <span data-ttu-id="f1460-170">Raktár</span><span class="sxs-lookup"><span data-stu-id="f1460-170">Warehouse</span></span> | <span data-ttu-id="f1460-171">*61*</span><span class="sxs-lookup"><span data-stu-id="f1460-171">*61*</span></span> |
    | <span data-ttu-id="f1460-172">Munka</span><span class="sxs-lookup"><span data-stu-id="f1460-172">Work</span></span> | <span data-ttu-id="f1460-173">Munka</span><span class="sxs-lookup"><span data-stu-id="f1460-173">Work</span></span> | <span data-ttu-id="f1460-174">Munkaazonosító</span><span class="sxs-lookup"><span data-stu-id="f1460-174">Work ID</span></span> | <span data-ttu-id="f1460-175">Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="f1460-175">Leave this field blank.</span></span> |

1. <span data-ttu-id="f1460-176">Az **OK** gombra kattintva mentse a lekérdezést, és zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f1460-176">Select **OK** to save the query and close the dialog box.</span></span>
1. <span data-ttu-id="f1460-177">A művelet panelen válassza a **Mentés** elemet, majd zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f1460-177">On the Action Pane, select **Save**, and close the page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1460-178">A fürtprofil azon mezői, amelyek elhalványítva jelennek meg, ha a **Fürtazonosító létrehozása** *Igen* értékre van beállítva, nem érhetők el, és nem lesznek figyelembe véve a funkció használata esetén.</span><span class="sxs-lookup"><span data-stu-id="f1460-178">Fields in the cluster profile that appear dimmed when **Generate cluster ID** is set to *Yes* are unavailable and won't be considered when this feature is used.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="f1460-179">Mobileszköz menüpontjai</span><span class="sxs-lookup"><span data-stu-id="f1460-179">Mobile device menu items</span></span>

<span data-ttu-id="f1460-180">Ehhez a funkcióhoz két új mobileszköz-menüelem használható.</span><span class="sxs-lookup"><span data-stu-id="f1460-180">Two new mobile device menu items are available for this feature.</span></span> <span data-ttu-id="f1460-181">A **Bevételezés és fürt rendezése** menüpont a bevételezett készletnek egy betárolási fürtbe történő rendezéséhez használatos.</span><span class="sxs-lookup"><span data-stu-id="f1460-181">The **Receive and sort cluster** menu item is used to sort the received inventory into a putaway cluster upon receipt.</span></span> <span data-ttu-id="f1460-182">A **Fürtbetárolás** menüelem a fürt betárolásához használatos, miután az hozzárendelésre került.</span><span class="sxs-lookup"><span data-stu-id="f1460-182">The **Cluster putaway** menu item is used to put the cluster away after it has been assigned.</span></span>

#### <a name="receive-and-sort-cluster"></a><span data-ttu-id="f1460-183">Fürt bevételezése és rendezése</span><span class="sxs-lookup"><span data-stu-id="f1460-183">Receive and sort cluster</span></span>

<span data-ttu-id="f1460-184">Hozzon létre egy új mobileszköz-menüelemet a készlet bevételezéséhez és egy fürtbe rendezéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1460-184">Create a new mobile device menu item for receiving inventory and sorting into a cluster.</span></span> <span data-ttu-id="f1460-185">Ez a menüelem a készlet bevételezését követően hozza létre a bejövő munkát, ami azt jelzi, hogy a bevételezés menüpontot fogja használni a betárolási fürtök esetében.</span><span class="sxs-lookup"><span data-stu-id="f1460-185">This menu item will create inbound work after inventory is received, which indicates that the receiving menu item will be used for putaway clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="f1460-186">A **Fürt bevételezése és rendezése** menüelem a következő bevételezési menüelemekkel használható:</span><span class="sxs-lookup"><span data-stu-id="f1460-186">The **Receive and sort cluster** menu item can be used with the following receiving menu items:</span></span>
>
> - <span data-ttu-id="f1460-187">Beszerzésirendelés-sor bevételezése</span><span class="sxs-lookup"><span data-stu-id="f1460-187">Purchase order line receiving</span></span>
> - <span data-ttu-id="f1460-188">Beszerzési rendelési cikk bevételezése</span><span class="sxs-lookup"><span data-stu-id="f1460-188">Purchase order item receiving</span></span>
> - <span data-ttu-id="f1460-189">Rakomány – cikk bevételezése</span><span class="sxs-lookup"><span data-stu-id="f1460-189">Load item receiving</span></span>

1. <span data-ttu-id="f1460-190">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="f1460-190">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="f1460-191">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1460-191">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f1460-192">A **Fejléc** nézetben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="f1460-192">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="f1460-193">**Menüelem neve:** *Fürt bevételezése és rendezése*</span><span class="sxs-lookup"><span data-stu-id="f1460-193">**Menu item name:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="f1460-194">**Cím:** *Fürt bevételezése és rendezése*</span><span class="sxs-lookup"><span data-stu-id="f1460-194">**Title:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="f1460-195">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="f1460-195">**Mode:** *Work*</span></span>
    - <span data-ttu-id="f1460-196">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="f1460-196">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="f1460-197">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="f1460-197">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="f1460-198">**Munkalétrehozási folyamat:** *Beszerzési rendelési cikk bevételezése*</span><span class="sxs-lookup"><span data-stu-id="f1460-198">**Work creation process:** *Purchase order item receiving*</span></span>
    - <span data-ttu-id="f1460-199">**Azonosítótábla létrehozása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="f1460-199">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="f1460-200">**Betárolási fürt hozzárendelése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="f1460-200">**Assign putaway cluster:** *Yes*</span></span>

        > [!NOTE]
        > <span data-ttu-id="f1460-201">A **Betárolási fürt hozzárendelése** beállítás csak az egylépéses *Munkalétrehozási folyamat* betárolási tevékenységéhez áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="f1460-201">The **Assign putaway cluster** option is available only for the one-step *Work creation process* activity for receiving.</span></span>

    <span data-ttu-id="f1460-202">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="f1460-202">Accept the default values for the remaining fields.</span></span>

1. <span data-ttu-id="f1460-203">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-203">On the Action Pane, select **Save**.</span></span>

#### <a name="cluster-putaway"></a><span data-ttu-id="f1460-204">Fürtbetárolás</span><span class="sxs-lookup"><span data-stu-id="f1460-204">Cluster putaway</span></span>

<span data-ttu-id="f1460-205">Hozzon létre egy új mobileszköz-menüelemet, amellyel a fürtöt betárolja, miután hozzárendelte a rendszer.</span><span class="sxs-lookup"><span data-stu-id="f1460-205">Create a new mobile device menu item for putting the cluster away after it has been assigned.</span></span>

1. <span data-ttu-id="f1460-206">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="f1460-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="f1460-207">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1460-207">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f1460-208">A **Fejléc** nézetben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="f1460-208">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="f1460-209">**Menüelem neve:** *Fürtbetárolás*</span><span class="sxs-lookup"><span data-stu-id="f1460-209">**Menu item name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="f1460-210">**Cím:** *Fürtbetárolás*</span><span class="sxs-lookup"><span data-stu-id="f1460-210">**Title:** *Cluster putaway*</span></span>
    - <span data-ttu-id="f1460-211">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="f1460-211">**Mode:** *Work*</span></span>
    - <span data-ttu-id="f1460-212">**Meglévő munka használata:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="f1460-212">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="f1460-213">Az **Általános** gyorslapon az **Irányító** mezőt *Fürtbetárolás* értékre kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="f1460-213">On the **General** FastTab, set the **Directed by** field to *Cluster putaway*.</span></span> <span data-ttu-id="f1460-214">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="f1460-214">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="f1460-215">A **Munkaosztályok** gyorslapon állítsa be a mobileszköz-menüelem érvényes munkaosztályát:</span><span class="sxs-lookup"><span data-stu-id="f1460-215">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item:</span></span>

    - <span data-ttu-id="f1460-216">**Munkaosztály azonosítója:** *Beszerzés*</span><span class="sxs-lookup"><span data-stu-id="f1460-216">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="f1460-217">**Munkarendelés típusa:** *Beszerzési rendelések*</span><span class="sxs-lookup"><span data-stu-id="f1460-217">**Work order type:** *Purchase orders*</span></span>

1. <span data-ttu-id="f1460-218">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-218">On the Action Pane, select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="f1460-219">Mobileszköz menü</span><span class="sxs-lookup"><span data-stu-id="f1460-219">Mobile device menu</span></span>

<span data-ttu-id="f1460-220">Adja hozzá a most létrehozott menüelemeket a mobilalkalmazás bejövő menüjéhez.</span><span class="sxs-lookup"><span data-stu-id="f1460-220">Add the menu items that you just created to the inbound menu of the mobile app.</span></span>

1. <span data-ttu-id="f1460-221">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1460-221">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="f1460-222">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-222">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="f1460-223">A menülistán válassza a **Bejövő** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1460-223">In the menu list, select **Inbound**.</span></span>
1. <span data-ttu-id="f1460-224">A **Rendelkezésre álló menük és menüelemek** listájában keresse meg és válassza ki a **Fürt bevételezése és rendezése** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="f1460-224">In the **Available menus and menu items** list, find and select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="f1460-225">Válassza a jobbra mutató nyílgombot a kiválasztott menüelem **Menüstruktúra** listában való elhelyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="f1460-225">Select the right arrow button to move the selected menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="f1460-226">A felfelé vagy lefelé mutató nyíllal a menüben mozgathatja a menüelemet a kívánt pozícióba.</span><span class="sxs-lookup"><span data-stu-id="f1460-226">Use the up arrow or down arrow button to move the menu item into the desired position in the menu.</span></span>
1. <span data-ttu-id="f1460-227">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-227">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f1460-228">A fennmaradó menüelemek hozzáadásához ismételje meg a 4–7. lépést.</span><span class="sxs-lookup"><span data-stu-id="f1460-228">Repeat steps 4 through 7 to add the remaining menu items:</span></span>

    - <span data-ttu-id="f1460-229">Fürt hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="f1460-229">Assign cluster</span></span>
    - <span data-ttu-id="f1460-230">Fürtbetárolás</span><span class="sxs-lookup"><span data-stu-id="f1460-230">Cluster putaway</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f1460-231">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="f1460-231">Example scenario</span></span>

<span data-ttu-id="f1460-232">Ez a forgatókönyv szimulálja a betárolási fürtök feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="f1460-232">This scenario simulates putaway cluster processing.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="f1460-233">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="f1460-233">Create a purchase order</span></span>

1. <span data-ttu-id="f1460-234">Nyissa meg a következőt: **Kötelezettségek \> Beszerzési rendelések \> Minden beszerzési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="f1460-234">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="f1460-235">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1460-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f1460-236">Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="f1460-236">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="f1460-237">**Szállítói számla:** *1001*</span><span class="sxs-lookup"><span data-stu-id="f1460-237">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="f1460-238">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="f1460-238">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="f1460-239">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-239">Select **OK**.</span></span>

    <span data-ttu-id="f1460-240">Megjelenik a **Minden beszerzési rendelés** lap.</span><span class="sxs-lookup"><span data-stu-id="f1460-240">The **All purchase orders** page appears.</span></span>

1. <span data-ttu-id="f1460-241">A **Minden beszerzési rendelés** lap **Beszerzési rendelés sorai** gyorslapján a **Sor hozzáadása** gombbal adja hozzá a következő sorokat:</span><span class="sxs-lookup"><span data-stu-id="f1460-241">On the **All purchase orders** page, on the **Purchase order lines** FastTab, use the **Add line** button to add the following lines:</span></span>

    - <span data-ttu-id="f1460-242">Beszerzési rendelés 1. sora:</span><span class="sxs-lookup"><span data-stu-id="f1460-242">Purchase order line 1:</span></span>

        - <span data-ttu-id="f1460-243">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f1460-243">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="f1460-244">**Mennyiség:** *10*</span><span class="sxs-lookup"><span data-stu-id="f1460-244">**Quantity:** *10*</span></span>

    - <span data-ttu-id="f1460-245">Beszerzési rendelés 2. sora:</span><span class="sxs-lookup"><span data-stu-id="f1460-245">Purchase order line 2:</span></span>

        - <span data-ttu-id="f1460-246">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="f1460-246">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="f1460-247">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="f1460-247">**Quantity:** *20*</span></span>

    - <span data-ttu-id="f1460-248">Beszerzési rendelés 3. sora:</span><span class="sxs-lookup"><span data-stu-id="f1460-248">Purchase order line 3:</span></span>

        - <span data-ttu-id="f1460-249">**Cikkszám:** *M9215*</span><span class="sxs-lookup"><span data-stu-id="f1460-249">**Item number:** *M9215*</span></span>
        - <span data-ttu-id="f1460-250">**Mennyiség:** *30*</span><span class="sxs-lookup"><span data-stu-id="f1460-250">**Quantity:** *30*</span></span>

1. <span data-ttu-id="f1460-251">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-251">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f1460-252">Jegyezze fel a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="f1460-252">Make a note of the purchase order number.</span></span>

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a><span data-ttu-id="f1460-253">Készlet bevételezése és eltárolása a mobileszközről</span><span class="sxs-lookup"><span data-stu-id="f1460-253">Receive inventory and put it away from the mobile device</span></span>

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a><span data-ttu-id="f1460-254">A készlet bevételezése és rendezése egy fürtbe</span><span class="sxs-lookup"><span data-stu-id="f1460-254">Receive and sort the inventory into a cluster</span></span>

1. <span data-ttu-id="f1460-255">Jelentkezzen be a raktározási alkalmazásba olyan felhasználóként, aki a *61*. raktárban be van állítva.</span><span class="sxs-lookup"><span data-stu-id="f1460-255">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="f1460-256">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="f1460-256">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="f1460-257">Válassza a **Bejövő** menü **Fürt bevételezése és rendezése** lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="f1460-257">On the **Inbound** menu, select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="f1460-258">A **Ponum** mezőben adja meg a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="f1460-258">In the **Ponum** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="f1460-259">Válassza az **OK** gombot (a pipa szimbólum gombja).</span><span class="sxs-lookup"><span data-stu-id="f1460-259">Select **OK** (the check mark button).</span></span>
1. <span data-ttu-id="f1460-260">Válassza ki a **Cikk** mezőt, majd adja meg cikkszámként az *A0001* értéket, és válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="f1460-260">Select the **Item** field, enter item number *A0001*, and then select **OK**.</span></span>
1. <span data-ttu-id="f1460-261">Válassza ki a **Mennyiség** mezőt, írja be a *10* értéket a számbillentyűzet használatával, majd jelölje be a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="f1460-261">Select the **Qty** field, enter *10* by using the number pad, and then select the check mark button.</span></span>
1. <span data-ttu-id="f1460-262">A **Mennyiség** lapon jelölje be az **OK** (pipa gomb) lehetőséget, hogy megerősítse a megadott mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-262">On the **Qty** task page, select **OK** (the check mark button) to confirm the quantity that you entered.</span></span>
1. <span data-ttu-id="f1460-263">A **Cikk** feladatoldalon válassza az **OK** gombot a megadott *A0001* cikk jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="f1460-263">On the **Item** task page, select **OK** to confirm that item *A0001* was entered.</span></span>
1. <span data-ttu-id="f1460-264">Válassza ki a **Fürtazonosító** mezőt, és adjon meg egy értéket a létrehozni kívánt fürt azonosítójának hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="f1460-264">Select the **Cluster ID** field, and enter a value to assign an ID for the cluster that you're creating.</span></span>

    <span data-ttu-id="f1460-265">Az itt megadott azonosító akkor használatos, amikor a beszerzési rendelésen szereplő két cikk bevételezésre kerül.</span><span class="sxs-lookup"><span data-stu-id="f1460-265">The ID that you enter here will be used when the two remaining items on the purchase order are received.</span></span>

1. <span data-ttu-id="f1460-266">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-266">Select **OK**.</span></span>

    <span data-ttu-id="f1460-267">Megjelenik a **Ponum** feladatoldal, és egy „Munka befejezve” üzenetet jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="f1460-267">The **Ponum** task page appears and shows a "Work completed" message.</span></span>

    <span data-ttu-id="f1460-268">Az *A0001* már bevételezésre került a *RECV* helyre, és a rendszer a 10. lépésben megadott fürtazonosítóhoz rendeli hozzá.</span><span class="sxs-lookup"><span data-stu-id="f1460-268">Item *A0001* has now been received into the *RECV* location and assigned to the cluster ID that you entered in step 10.</span></span>

1. <span data-ttu-id="f1460-269">Ismételje meg a 4–11. lépést, ha a beszerzési rendelés maradék két cikkét szeretné bevételezni, és a fürtazonosítóhoz rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="f1460-269">Repeat steps 4 through 11 to receive the remaining two items from the purchase order and assign them to the cluster ID:</span></span>

    - <span data-ttu-id="f1460-270">A *20* mennyiség az *A0002* cikkhez</span><span class="sxs-lookup"><span data-stu-id="f1460-270">A quantity of *20* for item *A0002*</span></span>
    - <span data-ttu-id="f1460-271">A *30* mennyiség az *M9215* cikkhez</span><span class="sxs-lookup"><span data-stu-id="f1460-271">A quantity of *30* for item *M9215*</span></span>

#### <a name="close-the-cluster"></a><span data-ttu-id="f1460-272">A fürt bezárása</span><span class="sxs-lookup"><span data-stu-id="f1460-272">Close the cluster</span></span>

<span data-ttu-id="f1460-273">A fürtben lévő cikkek betárolása előtt le kell zárni a fürtöt.</span><span class="sxs-lookup"><span data-stu-id="f1460-273">Before the items in the cluster can be put away, the cluster must be closed.</span></span>

1. <span data-ttu-id="f1460-274">A Supply Chain Management alkalmazásban nyissa meg a **Raktárkezelés \> Munka \> Kimenő \> Munkafürtök** elemet.</span><span class="sxs-lookup"><span data-stu-id="f1460-274">In Supply Chain Management, go to **Warehouse management \> Work \> Outbound \> Work clusters**.</span></span>
1. <span data-ttu-id="f1460-275">A **Munkafürtök** lap **Munkafürt** szakaszában keressen rá a korábban megadott fürtazonosítóra a **Fürtazonosító** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f1460-275">On the **Work clusters** page, in the **Work cluster** section, search the **Cluster ID** field for the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="f1460-276">Ha a fürt nem jelenik meg, lehet, hogy már lezárták.</span><span class="sxs-lookup"><span data-stu-id="f1460-276">If the cluster isn't shown, it might already have been closed.</span></span> <span data-ttu-id="f1460-277">Ha meg szeretné állapítani, hogy a fürt le van-e zárva, jelölje be a **Lezárt munka megjelenítése** jelölőnégyzetet, és keresse meg a korábban megadott fürtazonosítót.</span><span class="sxs-lookup"><span data-stu-id="f1460-277">To determine whether the cluster was closed, select the **Show closed work** check box, and search for the cluster ID that you entered earlier.</span></span> <span data-ttu-id="f1460-278">Majd tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="f1460-278">Then follow one of these steps:</span></span>

    - <span data-ttu-id="f1460-279">Ha a fürt le van zárva, akkor ugorja át az eljárás további lépéseit, és lépjen tovább a következő műveletre: [Fürt betárolása](#put-the-cluster-away).</span><span class="sxs-lookup"><span data-stu-id="f1460-279">If the cluster has been closed, skip the remaining steps of this procedure, and move on to the next procedure, [Put the cluster away](#put-the-cluster-away).</span></span>
    - <span data-ttu-id="f1460-280">Ha a fürt nincs lezárva, akkor az eljárás további lépéseivel zárja be manuálisan a fürtöt.</span><span class="sxs-lookup"><span data-stu-id="f1460-280">If the cluster hasn't been closed, follow the remaining steps of this procedure to manually close the cluster.</span></span> <span data-ttu-id="f1460-281">Ezután lépjen tovább a következő eljárásra.</span><span class="sxs-lookup"><span data-stu-id="f1460-281">Then move on to the next procedure.</span></span>

1. <span data-ttu-id="f1460-282">A **Munkafürt** szakaszban válassza ki a korábban megadott fürtazonosítót.</span><span class="sxs-lookup"><span data-stu-id="f1460-282">In the **Work cluster** section, select the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="f1460-283">A művelet ablaktáblán kattintson az **Fürt lezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="f1460-283">On the Action Pane, select **Close cluster**.</span></span>

    <span data-ttu-id="f1460-284">Miután a fürt le van zárva, már nem jelenik meg a **Munkafürt** szakaszban (hacsak nem jelöli be a **Lezárt munka megjelenítése** jelölőnégyzetet).</span><span class="sxs-lookup"><span data-stu-id="f1460-284">After the cluster has been closed, it's no longer shown in the **Work cluster** section (unless the **Show closed work** check box is selected).</span></span>

#### <a name="put-the-cluster-away"></a><span data-ttu-id="f1460-285">Fürt betárolása</span><span class="sxs-lookup"><span data-stu-id="f1460-285">Put the cluster away</span></span>

1. <span data-ttu-id="f1460-286">Jelentkezzen be a raktározási alkalmazásba olyan felhasználóként, aki a *61*. raktárban be van állítva.</span><span class="sxs-lookup"><span data-stu-id="f1460-286">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="f1460-287">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="f1460-287">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="f1460-288">Válassza a **Bejövő** menü **Fürtbetárolás** elemét.</span><span class="sxs-lookup"><span data-stu-id="f1460-288">On the **Inbound** menu, select **Cluster putaway**.</span></span>
1. <span data-ttu-id="f1460-289">Válassza ki a **Fürtazonosító** lehetőséget, majd adja meg a lezárt fürtnél korábban megadott fürtazonosítót.</span><span class="sxs-lookup"><span data-stu-id="f1460-289">Select **Cluster ID**, and enter the cluster ID that you entered earlier for the closed cluster.</span></span>
1. <span data-ttu-id="f1460-290">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-290">Select **OK**.</span></span>

    <span data-ttu-id="f1460-291">Megjelenik a **Fürtbetárolás: Kitárolás** oldal.</span><span class="sxs-lookup"><span data-stu-id="f1460-291">The **Cluster putaway: Pick** page appears.</span></span> <span data-ttu-id="f1460-292">A program megjeleníti a fürtazonosítót, a kitárolási helyet, a cikkeket (a *Több* érték jelenik meg), és a fürtben lévő teljes mennyiséget, amelyet ki kell tárolni.</span><span class="sxs-lookup"><span data-stu-id="f1460-292">It shows the cluster ID, the picking location, the items (the value *Multiple* will be shown), and the total quantity in the cluster that must be picked.</span></span>

1. <span data-ttu-id="f1460-293">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f1460-293">Select **OK**.</span></span>

    <span data-ttu-id="f1460-294">Megjelenik a **Fürtbetárolás: Betárolás** oldal.</span><span class="sxs-lookup"><span data-stu-id="f1460-294">The **Cluster putaway: Put** page appears.</span></span> <span data-ttu-id="f1460-295">A **Betárolás** utasításai határozzák meg a fürt azonosítóját, a betárolási helyet, a cikkeket, a teljes mennyiséget és az azonosítótábla azonosítóját a fürtön bevételezett cikkekhez.</span><span class="sxs-lookup"><span data-stu-id="f1460-295">The **Put** instructions identify the cluster ID, the put location, the items, the total quantity, and the license plate IDs for the items that have been received on the cluster.</span></span>

    <span data-ttu-id="f1460-296">A lépés felülbírálásához vagy átadásához a szokásos lehetőségek állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="f1460-296">You have the standard options to override or pass this step.</span></span>

    <span data-ttu-id="f1460-297">![Fürtbetárolás: Betárolási oldal](media/Cluster_putaway-Put.png "Fürtbetárolás: Betárolási oldal")</span><span class="sxs-lookup"><span data-stu-id="f1460-297">![Cluster putaway: Put page](media/Cluster_putaway-Put.png "Cluster putaway: Put page")</span></span>

1. <span data-ttu-id="f1460-298">A fürt betárolásának jóváhagyásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f1460-298">Select **OK** to confirm the putaway of the cluster.</span></span>

    <span data-ttu-id="f1460-299">Megjelenik a „Fürt befejezve” üzenet.</span><span class="sxs-lookup"><span data-stu-id="f1460-299">A "Cluster completed" message is shown.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="f1460-300">Megjegyzések és tippek</span><span class="sxs-lookup"><span data-stu-id="f1460-300">Notes and tips</span></span>

<span data-ttu-id="f1460-301">Azokban az esetekben, amikor a fürt azonosítója egy beágyazott raklap számára egy szülő azonosítótábla lesz, a program automatikusan beírja a betárolási pozíciót, amikor a rendszer beolvassa a fürtazonosítót.</span><span class="sxs-lookup"><span data-stu-id="f1460-301">For cases where the cluster ID becomes the parent license plate for a nested pallet, the put position is automatically given when the cluster ID is scanned.</span></span> <span data-ttu-id="f1460-302">Nem kell több azonosítótáblát beolvasni akkor sem, ha az azonosítótábla-létrehozás manuálisra van állítva.</span><span class="sxs-lookup"><span data-stu-id="f1460-302">No further license plate must be scanned, even if license plate generation is set to manual.</span></span>

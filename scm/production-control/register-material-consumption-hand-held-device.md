---
title: "Anyagfelhasználás regisztrálása mobileszköz segítségével"
description: "Ez a témakör olyan munkafolyamatot ír le, amely lehetővé teszi a nyersanyag-felhasználás regisztrálását a termelésben egy kézi eszköz használatával."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 97d374230cc6e833b9f585de000e1252f2a78b9d
ms.openlocfilehash: 83703d962d6099ba8ac107548a569c8d1f34882f
ms.contentlocale: hu-hu
ms.lasthandoff: 08/30/2017

---

# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="df3aa-103">Anyagfelhasználás regisztrálása mobileszköz segítségével</span><span class="sxs-lookup"><span data-stu-id="df3aa-103">Register material consumption using a mobile device</span></span>
<span data-ttu-id="df3aa-104">Ez a témakör olyan munkafolyamatot ír le, amely lehetővé teszi a nyersanyag-felhasználás regisztrálását a termelésben egy kézi eszköz használatával.</span><span class="sxs-lookup"><span data-stu-id="df3aa-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="df3aa-105">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="df3aa-105">Introduction</span></span>
------------

<span data-ttu-id="df3aa-106">A munkafolyamat akkor releváns, ha az anyag nyomon követhetősége szigorú követelmény.</span><span class="sxs-lookup"><span data-stu-id="df3aa-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="df3aa-107">Ebben az esetben az anyagok nyomonkövethetőségének megőrzése érdekében jelenteni kell a fogyasztás pontos időtartamát és mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="df3aa-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="df3aa-108">Ez a folyamat ellentétben áll az előzetes vagy utólagos kiürítési műveletekkel, ahol eltolás van a regisztrálás időpontja és a tényleges felhasználás időpontja között.</span><span class="sxs-lookup"><span data-stu-id="df3aa-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="df3aa-109">Ez a magyarázata annak, hogy miért nem használható az automatikus felhasználási stratégia bizonyos anyagok nyomonkövethetőségi követelményeire.</span><span class="sxs-lookup"><span data-stu-id="df3aa-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="df3aa-110">Nézzünk egy egyszerű forgatókönyvet, amely azt ismerteti, hogyan állítsunk be úgy egy munkafolyamat, hogy lehetővé tegyük a nyersanyag-felhasználás termelés során történő regisztrálását egy kézi eszközzel.</span><span class="sxs-lookup"><span data-stu-id="df3aa-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> [![](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a><span data-ttu-id="df3aa-111">Forgatókönyv részletei</span><span class="sxs-lookup"><span data-stu-id="df3aa-111">Scenario details</span></span>

<span data-ttu-id="df3aa-112">Egy folyamatos gyártási folyamat (5) az RM-100 köteg szerint nyilvántartott nyersanyagot használja fel.</span><span class="sxs-lookup"><span data-stu-id="df3aa-112">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="df3aa-113">Az anyag a Bulk-001 (1) helyen aktuálisan megtalálható a PL-1 azonosítótáblán két köteggel (B1 és B2), mindkettő mennyisége 100 kg.</span><span class="sxs-lookup"><span data-stu-id="df3aa-113">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="df3aa-114">A raktári munkát (2) kiadják és feldolgozzák az RM-100 esetében, a Bulk-001-ból az anyagot kitárolják a PIL-01 termelési bemeneti helyre (3), amely nem azonosítótáblás szabályozásúként van definiálva van.</span><span class="sxs-lookup"><span data-stu-id="df3aa-114">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="df3aa-115">A gépkezelő leméri az anyagot a termelési bemeneti helyről (3), és regisztrálja a tömeget és a ténylegesen felhasznált kötegszámot (4).</span><span class="sxs-lookup"><span data-stu-id="df3aa-115">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="df3aa-116">A termelési bemeneti helyről az anyag egy részét meghatározott időközönként manuálisan adják hozzá a termelési folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="df3aa-116">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="df3aa-117">Amikor a gépkezelő anyagot ad hozzá, az anyagot mérlegen le kell mérni, valamint regisztrálni kell a kötegszámot.</span><span class="sxs-lookup"><span data-stu-id="df3aa-117">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="df3aa-118">Állítsa be a munkafolyamatot a felhasználás kézi eszközzel történő regisztrálásához</span><span class="sxs-lookup"><span data-stu-id="df3aa-118">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="df3aa-119">Hozzon létre készterméket (FG-100) olyan anyagjegyzékkel, amely az RM-100 köteg szerint nyilvántartott nyersanyagot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="df3aa-119">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="df3aa-120">Adjon hozzá két RM-100 köteget (B1 és B2) 100-as mennyiségben a helyhez. Bulk-001 az azonosítótáblán: PL-1.</span><span class="sxs-lookup"><span data-stu-id="df3aa-120">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="df3aa-121">Az anyagjegyzék RM-100 anyagjegyzéksorában levő kiürítési elv értéke **Kézi**.</span><span class="sxs-lookup"><span data-stu-id="df3aa-121">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="df3aa-122">Állítsa a termelés alapértelmezett bemeneti helyét PIL-01 értékre.</span><span class="sxs-lookup"><span data-stu-id="df3aa-122">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="df3aa-123">Ezt úgy teheti meg, ha ezt a helyet választja alapértelmezett termelési bemeneti helynek az 51-es raktárban.</span><span class="sxs-lookup"><span data-stu-id="df3aa-123">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="df3aa-124">Új mobileszköz-menüpont létrehozása:</span><span class="sxs-lookup"><span data-stu-id="df3aa-124">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="df3aa-125">**Menüpont neve** – Anyagfelhasználás regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="df3aa-125">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="df3aa-126">**Beosztás** – Anyagfelhasználás regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="df3aa-126">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="df3aa-127">**Mód** – Közvetett.</span><span class="sxs-lookup"><span data-stu-id="df3aa-127">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="df3aa-128">**Tevékenységkód** – Anyagfelhasználás regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="df3aa-128">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="df3aa-129">Adja hozzá a menüelemet a **Production Mobile** mobileszközmenühöz.</span><span class="sxs-lookup"><span data-stu-id="df3aa-129">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="df3aa-130">Termelési rendelés létrehozása a késztermékhez:</span><span class="sxs-lookup"><span data-stu-id="df3aa-130">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="df3aa-131">**Cikkszám** – FG-100</span><span class="sxs-lookup"><span data-stu-id="df3aa-131">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="df3aa-132">**Telephely** – 5</span><span class="sxs-lookup"><span data-stu-id="df3aa-132">**Site** - 5</span></span> 
-    <span data-ttu-id="df3aa-133">**Raktár** – 51</span><span class="sxs-lookup"><span data-stu-id="df3aa-133">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="df3aa-134">**Mennyiség** – 150</span><span class="sxs-lookup"><span data-stu-id="df3aa-134">**Quantity** - 150</span></span>

<span data-ttu-id="df3aa-135">A termelési rendelés **Becsült** és **Engedélyezett** értékeket kap, és létrejön a raktárkezelési munka.</span><span class="sxs-lookup"><span data-stu-id="df3aa-135">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="df3aa-136">Hajtsa végre a munkát a kézi eszköz nyersanyag-kitároláshoz használt munkafolyamatával.</span><span class="sxs-lookup"><span data-stu-id="df3aa-136">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="df3aa-137">Ez az anyagot az ömlesztett tárolóhelyről a PIL-01 termelési bemeneti helyre viszi.</span><span class="sxs-lookup"><span data-stu-id="df3aa-137">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="df3aa-138">A munka befejezése után az anyag állapota **Kitárolás a termelési bemeneti helyén** lesz.</span><span class="sxs-lookup"><span data-stu-id="df3aa-138">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="df3aa-139">Az állapot a munka feldolgozása után **Kitárolva** vagy **Foglalt tényleges** lehet.</span><span class="sxs-lookup"><span data-stu-id="df3aa-139">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="df3aa-140">Ez a **Kiadás állapota a raktár képernyőre történő helyezés után** paraméterrel van beállítva.</span><span class="sxs-lookup"><span data-stu-id="df3aa-140">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="df3aa-141">Indítsa el a termelési rendelést az ügyfélből vagy a kézi eszközről a **Termelés indítása** menüpont használatával.</span><span class="sxs-lookup"><span data-stu-id="df3aa-141">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="df3aa-142">A termelési rendelés elindítása után regisztrálhatja a nyersanyag-felhasználását a munkafolyamat segítségével a kézi eszközön.</span><span class="sxs-lookup"><span data-stu-id="df3aa-142">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="df3aa-143">Kezdjük azzal, hogy a B1 köteg-hez 25 kg felhasználást regisztrálunk.</span><span class="sxs-lookup"><span data-stu-id="df3aa-143">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="df3aa-144">Válassza ki az **Anyag regisztrálása** **Felhasználás** menüelemet a kézi eszközhöz, és írja be a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="df3aa-144">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="df3aa-145">A termelési rendelés száma.</span><span class="sxs-lookup"><span data-stu-id="df3aa-145">The production order number.</span></span> 
-    <span data-ttu-id="df3aa-146">Az anyagfelhasználás helye, ebben az esetben: PIL-01.</span><span class="sxs-lookup"><span data-stu-id="df3aa-146">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="df3aa-147">Cikkszám: RM-100.</span><span class="sxs-lookup"><span data-stu-id="df3aa-147">Item number RM-100.</span></span> 
-    <span data-ttu-id="df3aa-148">Kötegszám: B1.</span><span class="sxs-lookup"><span data-stu-id="df3aa-148">Batch number B1.</span></span> 
-    <span data-ttu-id="df3aa-149">Mennyiség: 25.</span><span class="sxs-lookup"><span data-stu-id="df3aa-149">A quantity of 25.</span></span>

7.  <span data-ttu-id="df3aa-150">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="df3aa-150">Select **OK**.</span></span>

<span data-ttu-id="df3aa-151">Vegye figyelembe, hogy a kijelzőn megjelenik „A naplósor létrehozva” üzenet.</span><span class="sxs-lookup"><span data-stu-id="df3aa-151">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="df3aa-152">A termelési rendelésen van egy, az RM-100 cikkszámhoz és a B1 kötegszámhoz tartozó **Termelési kitárolási lista** típusú üres napló.</span><span class="sxs-lookup"><span data-stu-id="df3aa-152">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="df3aa-153">Választhat, hogy folytatja-e a regisztrálást, például a B2 kötegszám esetében, és ahányszor az **OK** lehetőséget választja, a rendszer új naplósort ad hozzá a nyitott naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="df3aa-153">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="df3aa-154">A regisztrálás befejezése után válassza a **Kész** lehetőséget a napló feladásához és a munkafolyamat befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="df3aa-154">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="df3aa-155">További megjegyzések</span><span class="sxs-lookup"><span data-stu-id="df3aa-155">Additional comments</span></span> 

-   <span data-ttu-id="df3aa-156">Ha a felhasználó megszakítja a munkafolyamatot egy naplósor létrehozása után, a napló fel nem adott állapotban van, de ha a felhasználó egy későbbi időpontban ezt a munkafolyamatot használja ugyanahhoz a termelési rendeléshez, a rendszer a sorokat a nyitott naplóhoz adja hozzá, nem pedig egy új naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="df3aa-156">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="df3aa-157">Az új munkafolyamat a sorozatszámok bejegyzését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="df3aa-157">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="df3aa-158">Csak olyan cikkszámot lehet regisztrálni, amely az anyagjegyzékben vagy a kiválasztott termelési rendelés vagy kötegrendelés képletében meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="df3aa-158">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="df3aa-159">Az anyag túlfogyasztása engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="df3aa-159">Material can be overconsumed.</span></span> <span data-ttu-id="df3aa-160">Például ha a becsült mennyiségű felhasználandó anyagmennyiség 100 kg, akkor a túlfogyasztás mennyisége például 105 kg lehet.</span><span class="sxs-lookup"><span data-stu-id="df3aa-160">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>




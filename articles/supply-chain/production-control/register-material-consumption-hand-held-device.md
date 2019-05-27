---
title: Anyagfelhasználás regisztrálása mobileszköz segítségével
description: Ez a témakör olyan munkafolyamatot ír le, amely lehetővé teszi a nyersanyag-felhasználás regisztrálását a termelésben egy kézi eszköz használatával.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5b9c73cf9b23eb8ad9ed872b76b92b395609e9a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571023"
---
# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="00a5f-103">Anyagfelhasználás regisztrálása mobileszköz segítségével</span><span class="sxs-lookup"><span data-stu-id="00a5f-103">Register material consumption using a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00a5f-104">Ez a témakör olyan munkafolyamatot ír le, amely lehetővé teszi a nyersanyag-felhasználás regisztrálását a termelésben egy kézi eszköz használatával.</span><span class="sxs-lookup"><span data-stu-id="00a5f-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="00a5f-105">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="00a5f-105">Introduction</span></span>
------------

<span data-ttu-id="00a5f-106">A munkafolyamat akkor releváns, ha az anyag nyomon követhetősége szigorú követelmény.</span><span class="sxs-lookup"><span data-stu-id="00a5f-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="00a5f-107">Ebben az esetben az anyagok nyomonkövethetőségének megőrzése érdekében jelenteni kell a fogyasztás pontos időtartamát és mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="00a5f-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="00a5f-108">Ez a folyamat ellentétben áll az előzetes vagy utólagos kiürítési műveletekkel, ahol eltolás van a regisztrálás időpontja és a tényleges felhasználás időpontja között.</span><span class="sxs-lookup"><span data-stu-id="00a5f-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="00a5f-109">Ez a magyarázata annak, hogy miért nem használható az automatikus felhasználási stratégia bizonyos anyagok nyomonkövethetőségi követelményeire.</span><span class="sxs-lookup"><span data-stu-id="00a5f-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="00a5f-110">Nézzünk egy egyszerű forgatókönyvet, amely azt ismerteti, hogyan állítsunk be úgy egy munkafolyamat, hogy lehetővé tegyük a nyersanyag-felhasználás termelés során történő regisztrálását egy kézi eszközzel.</span><span class="sxs-lookup"><span data-stu-id="00a5f-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> <span data-ttu-id="00a5f-111">[![munkafolyamat beállítása nyersanyag-felhasználás kézi eszközzel történő rögzítéséhez](./media/scenario3.png)](./media/scenario3.png)</span><span class="sxs-lookup"><span data-stu-id="00a5f-111">[![set up a workflow to enable registration of raw material consumption by using a handheld device](./media/scenario3.png)](./media/scenario3.png)</span></span>

### <a name="scenario-details"></a><span data-ttu-id="00a5f-112">Forgatókönyv részletei</span><span class="sxs-lookup"><span data-stu-id="00a5f-112">Scenario details</span></span>

<span data-ttu-id="00a5f-113">Egy folyamatos gyártási folyamat (5) az RM-100 köteg szerint nyilvántartott nyersanyagot használja fel.</span><span class="sxs-lookup"><span data-stu-id="00a5f-113">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="00a5f-114">Az anyag a Bulk-001 (1) helyen aktuálisan megtalálható a PL-1 azonosítótáblán két köteggel (B1 és B2), mindkettő mennyisége 100 kg.</span><span class="sxs-lookup"><span data-stu-id="00a5f-114">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="00a5f-115">A raktári munkát (2) kiadják és feldolgozzák az RM-100 esetében, a Bulk-001-ból az anyagot kitárolják a PIL-01 termelési bemeneti helyre (3), amely nem azonosítótáblás szabályozásúként van definiálva van.</span><span class="sxs-lookup"><span data-stu-id="00a5f-115">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="00a5f-116">A gépkezelő leméri az anyagot a termelési bemeneti helyről (3), és regisztrálja a tömeget és a ténylegesen felhasznált kötegszámot (4).</span><span class="sxs-lookup"><span data-stu-id="00a5f-116">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="00a5f-117">A termelési bemeneti helyről az anyag egy részét meghatározott időközönként manuálisan adják hozzá a termelési folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="00a5f-117">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="00a5f-118">Amikor a gépkezelő anyagot ad hozzá, az anyagot mérlegen le kell mérni, valamint regisztrálni kell a kötegszámot.</span><span class="sxs-lookup"><span data-stu-id="00a5f-118">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-theworkflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="00a5f-119">Állítsa be a munkafolyamatot a felhasználás kézi eszközzel történő regisztrálásához</span><span class="sxs-lookup"><span data-stu-id="00a5f-119">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="00a5f-120">Hozzon létre készterméket (FG-100) olyan anyagjegyzékkel, amely az RM-100 köteg szerint nyilvántartott nyersanyagot tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="00a5f-120">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="00a5f-121">Adjon hozzá két RM-100 köteget (B1 és B2) 100-as mennyiségben a helyhez. Bulk-001 az azonosítótáblán: PL-1.</span><span class="sxs-lookup"><span data-stu-id="00a5f-121">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="00a5f-122">Az anyagjegyzék RM-100 anyagjegyzéksorában levő kiürítési elv értéke **Kézi**.</span><span class="sxs-lookup"><span data-stu-id="00a5f-122">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="00a5f-123">Állítsa a termelés alapértelmezett bemeneti helyét PIL-01 értékre.</span><span class="sxs-lookup"><span data-stu-id="00a5f-123">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="00a5f-124">Ezt úgy teheti meg, ha ezt a helyet választja alapértelmezett termelési bemeneti helynek az 51-es raktárban.</span><span class="sxs-lookup"><span data-stu-id="00a5f-124">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="00a5f-125">Új mobileszköz-menüpont létrehozása:</span><span class="sxs-lookup"><span data-stu-id="00a5f-125">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="00a5f-126">**Menüpont neve** – Anyagfelhasználás regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="00a5f-126">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="00a5f-127">**Beosztás** – Anyagfelhasználás regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="00a5f-127">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="00a5f-128">**Mód** – Közvetett.</span><span class="sxs-lookup"><span data-stu-id="00a5f-128">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="00a5f-129">**Tevékenységkód** – Anyagfelhasználás regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="00a5f-129">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="00a5f-130">Adja hozzá a menüelemet a **Production Mobile** mobileszközmenühöz.</span><span class="sxs-lookup"><span data-stu-id="00a5f-130">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="00a5f-131">Termelési rendelés létrehozása a késztermékhez:</span><span class="sxs-lookup"><span data-stu-id="00a5f-131">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="00a5f-132">**Cikkszám** – FG-100</span><span class="sxs-lookup"><span data-stu-id="00a5f-132">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="00a5f-133">**Telephely** – 5</span><span class="sxs-lookup"><span data-stu-id="00a5f-133">**Site** - 5</span></span> 
-    <span data-ttu-id="00a5f-134">**Raktár** – 51</span><span class="sxs-lookup"><span data-stu-id="00a5f-134">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="00a5f-135">**Mennyiség** – 150</span><span class="sxs-lookup"><span data-stu-id="00a5f-135">**Quantity** - 150</span></span>

<span data-ttu-id="00a5f-136">A termelési rendelés **Becsült** és **Engedélyezett** értékeket kap, és létrejön a raktárkezelési munka.</span><span class="sxs-lookup"><span data-stu-id="00a5f-136">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="00a5f-137">Hajtsa végre a munkát a kézi eszköz nyersanyag-kitároláshoz használt munkafolyamatával.</span><span class="sxs-lookup"><span data-stu-id="00a5f-137">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="00a5f-138">Ez az anyagot az ömlesztett tárolóhelyről a PIL-01 termelési bemeneti helyre viszi.</span><span class="sxs-lookup"><span data-stu-id="00a5f-138">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="00a5f-139">A munka befejezése után az anyag állapota **Kitárolás a termelési bemeneti helyén** lesz.</span><span class="sxs-lookup"><span data-stu-id="00a5f-139">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="00a5f-140">Az állapot a munka feldolgozása után **Kitárolva** vagy **Foglalt tényleges** lehet.</span><span class="sxs-lookup"><span data-stu-id="00a5f-140">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="00a5f-141">Ez a **Kiadás állapota a raktár képernyőre történő helyezés után** paraméterrel van beállítva.</span><span class="sxs-lookup"><span data-stu-id="00a5f-141">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="00a5f-142">Indítsa el a termelési rendelést az ügyfélből vagy a kézi eszközről a **Termelés indítása** menüpont használatával.</span><span class="sxs-lookup"><span data-stu-id="00a5f-142">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="00a5f-143">A termelési rendelés elindítása után regisztrálhatja a nyersanyag-felhasználását a munkafolyamat segítségével a kézi eszközön.</span><span class="sxs-lookup"><span data-stu-id="00a5f-143">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="00a5f-144">Kezdjük azzal, hogy a B1 köteghez 25 kg felhasználást regisztrálunk.</span><span class="sxs-lookup"><span data-stu-id="00a5f-144">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="00a5f-145">Válassza ki az **Anyag regisztrálása** **Felhasználás** menüelemet a kézi eszközhöz, és írja be a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="00a5f-145">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="00a5f-146">A termelési rendelés száma.</span><span class="sxs-lookup"><span data-stu-id="00a5f-146">The production order number.</span></span> 
-    <span data-ttu-id="00a5f-147">Az anyagfelhasználás helye, ebben az esetben: PIL-01.</span><span class="sxs-lookup"><span data-stu-id="00a5f-147">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="00a5f-148">Cikkszám: RM-100.</span><span class="sxs-lookup"><span data-stu-id="00a5f-148">Item number RM-100.</span></span> 
-    <span data-ttu-id="00a5f-149">Kötegszám: B1.</span><span class="sxs-lookup"><span data-stu-id="00a5f-149">Batch number B1.</span></span> 
-    <span data-ttu-id="00a5f-150">Mennyiség: 25.</span><span class="sxs-lookup"><span data-stu-id="00a5f-150">A quantity of 25.</span></span>

7.  <span data-ttu-id="00a5f-151">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00a5f-151">Select **OK**.</span></span>

<span data-ttu-id="00a5f-152">Vegye figyelembe, hogy a kijelzőn megjelenik „A naplósor létrehozva” üzenet.</span><span class="sxs-lookup"><span data-stu-id="00a5f-152">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="00a5f-153">A termelési rendelésen van egy, az RM-100 cikkszámhoz és a B1 kötegszámhoz tartozó **Termelési kitárolási lista** típusú üres napló.</span><span class="sxs-lookup"><span data-stu-id="00a5f-153">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="00a5f-154">Választhat, hogy folytatja-e a regisztrálást, például a B2 kötegszám esetében, és ahányszor az **OK** lehetőséget választja, a rendszer új naplósort ad hozzá a nyitott naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="00a5f-154">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="00a5f-155">A regisztrálás befejezése után válassza a **Kész** lehetőséget a napló feladásához és a munkafolyamat befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="00a5f-155">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="00a5f-156">További megjegyzések</span><span class="sxs-lookup"><span data-stu-id="00a5f-156">Additional comments</span></span> 

-   <span data-ttu-id="00a5f-157">Ha a felhasználó megszakítja a munkafolyamatot egy naplósor létrehozása után, a napló fel nem adott állapotban van, de ha a felhasználó egy későbbi időpontban ezt a munkafolyamatot használja ugyanahhoz a termelési rendeléshez, a rendszer a sorokat a nyitott naplóhoz adja hozzá, nem pedig egy új naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="00a5f-157">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="00a5f-158">Az új munkafolyamat a sorozatszámok bejegyzését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="00a5f-158">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="00a5f-159">Csak olyan cikkszámot lehet regisztrálni, amely az anyagjegyzékben vagy a kiválasztott termelési rendelés vagy kötegrendelés képletében meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="00a5f-159">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="00a5f-160">Az anyag túlfogyasztása engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="00a5f-160">Material can be overconsumed.</span></span> <span data-ttu-id="00a5f-161">Például ha a becsült mennyiségű felhasználandó anyagmennyiség 100 kg, akkor a túlfogyasztás mennyisége például 105 kg lehet.</span><span class="sxs-lookup"><span data-stu-id="00a5f-161">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>



---
title: "Termelési rendelések áttárolása kiszállítási területekbe"
description: "Ez a témakör leírja, hogyan kell kezelni az anyag áttárolásának folyamatát, amelyet egy gyártósorról befejezettnek jelentenek egy kimenő szállítási dokk felé."
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
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a3f193b5b16406aa6ac3ed6a96f909318d100439
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="cross-docking-from-production-orders-to-outbound-docks"></a><span data-ttu-id="a11f4-103">Termelési rendelések áttárolása kiszállítási területekbe</span><span class="sxs-lookup"><span data-stu-id="a11f4-103">Cross-docking from production orders to outbound docks</span></span>

<span data-ttu-id="a11f4-104">Ez a témakör leírja, hogyan kell kezelni az anyag áttárolásának folyamatát, amelyet egy gyártósorról befejezettnek jelentenek egy kimenő szállítási dokk felé.</span><span class="sxs-lookup"><span data-stu-id="a11f4-104">This topic describes how to manage the process of cross-docking material that is being reported as finished from a production line to an outbound transportation dock.</span></span>

<a name="introduction"></a><span data-ttu-id="a11f4-105">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="a11f4-105">Introduction</span></span>
------------

<span data-ttu-id="a11f4-106">A termelésből a kimenő helyre történő áttárolás fontos azoknál a gyártóknál, akik nagy mennyiséget termelnek, és ideális esetben a késztermékeket azonnal szeretnék szállítani, amint elkészülnek a gyártósorok.</span><span class="sxs-lookup"><span data-stu-id="a11f4-106">Cross-docking from production to an outbound location is relevant for manufacturers who produce high volume and ideally want to ship the finished products as soon as they are reported as finished from the production lines.</span></span> <span data-ttu-id="a11f4-107">A cél az, hogy a termékeket olyan elosztóközpontokba szállítsák, amelyek fizikailag a vevői igényekhez közel helyezkednek el, ahelyett, hogy a készletet gyártási helyen halmoznák fel.</span><span class="sxs-lookup"><span data-stu-id="a11f4-107">The purpose is to ship the products to distribution centers that are physically located close to the customer demand, rather than build up inventory at the manufacturing site.</span></span>

<span data-ttu-id="a11f4-108">Abban az esetben, ha nincs azonnali kereslet egy termékre, azt el kell helyezni a raktárhelyiségekbe a gyártási helyszínen.</span><span class="sxs-lookup"><span data-stu-id="a11f4-108">In case there is no immediate demand for a product, it must be put away to warehouse locations on the manufacturing site.</span></span> <span data-ttu-id="a11f4-109">Ezt a folyamatot *alkalmi áttárolásnak* is nevezik, ami azt jelenti, hogy a termék szállítási igény esetén, majd ehhez a lehetőséghez használandó helyett betárolásra szolgál a termék belső tárolására.</span><span class="sxs-lookup"><span data-stu-id="a11f4-109">This process is also known as *opportunistic cross-docking*, which indicates that if there is a demand for shipping the product, then this opportunity should be used instead of putting the product away for internal storage.</span></span>

<span data-ttu-id="a11f4-110">A következő példa három olyan változatot mutat be, amely a gyártósor végén (2) kezdődik.</span><span class="sxs-lookup"><span data-stu-id="a11f4-110">The following example shows three variations of a flow that starts at the end of the production line (2).</span></span>

<span data-ttu-id="a11f4-111">A terméket a gyártási kimeneti helyre (3) késztermékként jelentik, és egy targoncakezelő felveszi a raklapot ezen a helyen (3).</span><span class="sxs-lookup"><span data-stu-id="a11f4-111">A product is reported as finished to the production output location (3) and a fork lift driver will pick up the pallet at this location (3).</span></span>

-   <span data-ttu-id="a11f4-112">Ha van tervezett tevékenység (6) a termék gyártóhely (1) és elosztó központ (7) közötti átvitelére, akkor a járművezetőt a rendszer irányítja arra, hogy a raklapot a megfelelő rakodóhelyre (4) helyezze el.</span><span class="sxs-lookup"><span data-stu-id="a11f4-112">If there is a planned activity (6) for transferring the product from manufacturing (1) to a distribution center (7), then the truck driver will be directed by the system to put the pallet by a bay-door location (4).</span></span>
-   <span data-ttu-id="a11f4-113">Ha a pótkocsi már hozzá van rendelve a rakodóhelyre, akkor a teherautó-vezető rakodja a terméket közvetlenül a pótkocsira.</span><span class="sxs-lookup"><span data-stu-id="a11f4-113">If a trailer is already assigned to the bay door, the truck driver will be directed to load the product directly to the trailer.</span></span>
-   <span data-ttu-id="a11f4-114">Ha nincs tervezett tevékenység a termék átvitelére, akkor a targoncavezetőt arra irányítják, hogy a terméket a belső raktárba (5) helyezze el.</span><span class="sxs-lookup"><span data-stu-id="a11f4-114">If there is no planned activity for transferring the product, the fork lift driver will be directed to put the product away to a location in the internal warehouse (5).</span></span>

<span data-ttu-id="a11f4-115">[![lehetőség szerinti áttárolás](./media/scenario1.png)](./media/scenario1.png)</span><span class="sxs-lookup"><span data-stu-id="a11f4-115">[![opportunistic cross-docking](./media/scenario1.png)](./media/scenario1.png)</span></span>

## <a name="configure-cross-docking"></a><span data-ttu-id="a11f4-116">Áttárolás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a11f4-116">Configure cross-docking</span></span>
<span data-ttu-id="a11f4-117">Az áttárolási folyamatot **munkairányelvekkel** konfigurálhatja.</span><span class="sxs-lookup"><span data-stu-id="a11f4-117">You configure the cross-docking process in **work policies**.</span></span> <span data-ttu-id="a11f4-118">A munkairányelv munkarendelés-típust, helyet és terméket foglal magában.</span><span class="sxs-lookup"><span data-stu-id="a11f4-118">A work policy includes a work order type, location, and product.</span></span> <span data-ttu-id="a11f4-119">A következő példában az áttárolás az X termékhez és az Y helyhez van beállítva.</span><span class="sxs-lookup"><span data-stu-id="a11f4-119">In the following example, cross-docking is configured for product X and location Y.</span></span>

#### <a name="work-order-types"></a><span data-ttu-id="a11f4-120">Munkarendelés típusai</span><span class="sxs-lookup"><span data-stu-id="a11f4-120">Work order types</span></span>

-   <span data-ttu-id="a11f4-121">Munkarendelés típusa: Késztermékek betárolása</span><span class="sxs-lookup"><span data-stu-id="a11f4-121">Work order type: Finished goods put way</span></span>
-   <span data-ttu-id="a11f4-122">Munka létrehozási módja: Áttárolás</span><span class="sxs-lookup"><span data-stu-id="a11f4-122">Work creation method: Cross docking</span></span>
-   <span data-ttu-id="a11f4-123">Áttárolási irányelv neve: Átmozgatási rendelések</span><span class="sxs-lookup"><span data-stu-id="a11f4-123">Cross docking policy name: Transfer orders</span></span>

#### <a name="inventory-locations"></a><span data-ttu-id="a11f4-124">Készlethelyek</span><span class="sxs-lookup"><span data-stu-id="a11f4-124">Inventory locations</span></span>

-   <span data-ttu-id="a11f4-125">Raktár: 51</span><span class="sxs-lookup"><span data-stu-id="a11f4-125">Warehouse: 51</span></span>
-   <span data-ttu-id="a11f4-126">Tárolóhely: Y</span><span class="sxs-lookup"><span data-stu-id="a11f4-126">Location: Y</span></span>

#### <a name="products"></a><span data-ttu-id="a11f4-127">Termékek</span><span class="sxs-lookup"><span data-stu-id="a11f4-127">Products</span></span>

-   <span data-ttu-id="a11f4-128">Cikkszám: X</span><span class="sxs-lookup"><span data-stu-id="a11f4-128">Item number: X</span></span>

<span data-ttu-id="a11f4-129">Az áttárolás jelenleg csak két munkarendelés-típushoz konfigurálható:</span><span class="sxs-lookup"><span data-stu-id="a11f4-129">Currently, cross-docking can be configured for only two work order types:</span></span>

-   <span data-ttu-id="a11f4-130">Késztermékek betárolása</span><span class="sxs-lookup"><span data-stu-id="a11f4-130">Finished goods put away</span></span>
-   <span data-ttu-id="a11f4-131">Társ- és melléktermék betárolása</span><span class="sxs-lookup"><span data-stu-id="a11f4-131">Co-product and by-product put away</span></span>

<span data-ttu-id="a11f4-132">Az **áttárolási irányelvben** Ön határozza meg, hogy mely dokumentumtípusok használhatók az áttároláshoz.</span><span class="sxs-lookup"><span data-stu-id="a11f4-132">In the **cross-docking policy**, you define which document types are applicable for cross-docking.</span></span> <span data-ttu-id="a11f4-133">Jelenleg az egyetlen támogatott dokumentumtípus az **Átmozgatási rendelések**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-133">Currently, the only document type that is supported is **Transfer orders**.</span></span> <span data-ttu-id="a11f4-134">Az alábbi példa az áttárolási irányelv konfigurációját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="a11f4-134">The following example shows the configuration of a cross-docking policy.</span></span>

### <a name="cross-docking-policy-name-transfer-order"></a><span data-ttu-id="a11f4-135">Áttárolási irányelv neve: Átmozgatási rendelés</span><span class="sxs-lookup"><span data-stu-id="a11f4-135">Cross-docking policy name: Transfer order</span></span>

-   <span data-ttu-id="a11f4-136">Sorszám: 10</span><span class="sxs-lookup"><span data-stu-id="a11f4-136">Sequence number: 10</span></span>
-   <span data-ttu-id="a11f4-137">Munkarendelés típusa: Átmozgatási probléma</span><span class="sxs-lookup"><span data-stu-id="a11f4-137">Work order type: Transfer issue</span></span>
-   <span data-ttu-id="a11f4-138">Az áttárolási igényhez meg kell adni a helyet: Hamis</span><span class="sxs-lookup"><span data-stu-id="a11f4-138">Cross docking demand requires location: False</span></span>
-   <span data-ttu-id="a11f4-139">Párhuzamos áttárolási stratégia: dátuma és időpontja</span><span class="sxs-lookup"><span data-stu-id="a11f4-139">Cross docking strategy: Date and time</span></span>

### <a name="sequence-number"></a><span data-ttu-id="a11f4-140">Sorszám</span><span class="sxs-lookup"><span data-stu-id="a11f4-140">Sequence number</span></span>

<span data-ttu-id="a11f4-141">A **sorszámú** az ilyen típusú dokumentumok prioritását jelzi.</span><span class="sxs-lookup"><span data-stu-id="a11f4-141">The **sequence number** indicates the priority of the document type.</span></span> <span data-ttu-id="a11f4-142">Az egyedüli támogatott dokumentumtípus jelenleg az **átmozgatási rendelések**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-142">Currently, **Transfer issue** is the only type that is supported.</span></span> <span data-ttu-id="a11f4-143">Emiatt a sorszám lesz megfelelő csak akkor áll rendelkezésre, ha több rendelést munkatípusok támogatottak.</span><span class="sxs-lookup"><span data-stu-id="a11f4-143">Therefore, the sequence number will become relevant only when more work order types are supported.</span></span>

### <a name="cross-docking-policy"></a><span data-ttu-id="a11f4-144">Áttárolási irányelv</span><span class="sxs-lookup"><span data-stu-id="a11f4-144">Cross-docking policy</span></span>

<span data-ttu-id="a11f4-145">Az áttárolási irányelv is beállítja a házirend az átmozgatási rendelés igény prioritásának a beállítására.</span><span class="sxs-lookup"><span data-stu-id="a11f4-145">The cross-docking policy also sets the policy for the prioritization of transfer order demand.</span></span> <span data-ttu-id="a11f4-146">Például ha több átmozgatási rendelés létezik ugyanarra a termékre, ütemezett dátuma és időpontja, a rakomány meg, és az átmozgatási rendeléshez társított, meghatározhatja a rangsor a rendelések között.</span><span class="sxs-lookup"><span data-stu-id="a11f4-146">For example, if multiple transfer orders exist for the same product, the scheduled date and time that are set on the load, and associated with the transfer order, determine the prioritization between the orders.</span></span> <span data-ttu-id="a11f4-147">Közvetlenül a rakományban ütemezett dátuma és időpontja is megadható, illetve állíthatók be egy **találkozó ütemezése**, amely a terhelés kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="a11f4-147">The scheduled date and time can be set directly on the load, or they can be set on an **appointment schedule** that is associated with the load.</span></span> <span data-ttu-id="a11f4-148">Az áttárolási stratégia a prioritás határozza meg.</span><span class="sxs-lookup"><span data-stu-id="a11f4-148">The prioritization is determined by the cross-docking strategy.</span></span> <span data-ttu-id="a11f4-149">Jelenleg csak egy stratégia: **dátum és időpont**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-149">Currently, there is only one strategy: **Date and time**.</span></span>

### <a name="cross-docking-demand-requires-location"></a><span data-ttu-id="a11f4-150">Az áttárolási igényhez meg kell adni a helyet.</span><span class="sxs-lookup"><span data-stu-id="a11f4-150">Cross-docking demand requires location</span></span>

<span data-ttu-id="a11f4-151">Az áttárolási házirendben állíthat be egy feltételt megköveteli, hogy van-e átmozgatási rendelések egy hozzárendelt hely annak érdekében, hogy jogosult az áttárolási.</span><span class="sxs-lookup"><span data-stu-id="a11f4-151">In the cross-docking policy, you can set up a criterion to require that transfer orders have an assigned location in order to be eligible for cross-docking.</span></span> <span data-ttu-id="a11f4-152">Ennek a kritériumnak van megadva a **érintő áttárolási igény szükséges hely** mező.</span><span class="sxs-lookup"><span data-stu-id="a11f4-152">This criterion is set in the **Cross docking demand requires location** field.</span></span> <span data-ttu-id="a11f4-153">A hely a rakomány társított a találkozó ütemezése a végső helyeként szolgál az áruk, amelyeket áttárolt.</span><span class="sxs-lookup"><span data-stu-id="a11f4-153">The location on the appointment schedule that is associated with the load is used as the final location for the goods that are being cross-docked.</span></span> <span data-ttu-id="a11f4-154">Az áruk, amelyeket cross-rögzített végső helye határozza meg a helyutasítást **átmozgatási probléma** számára a **betárolási** Munkarendelés típusa.</span><span class="sxs-lookup"><span data-stu-id="a11f4-154">The final location for the goods that are being cross-docked is determined by the location directive for **Transfer issue** for the **Put** work order type.</span></span> <span data-ttu-id="a11f4-155">Akkor lehet hasznos beállítása a **érintő áttárolási igény szükséges hely** mezőjében egy esetet, ha az elkészült termékek kell érintő-rögzített csak akkor, ha a pótkocsi rakodórámpájához ajtó hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="a11f4-155">You might find it useful to set the **Cross docking demand requires location** field in a scenario where the finished goods should be cross-docked only if a trailer is assigned to a bay door.</span></span> <span data-ttu-id="a11f4-156">Ebben a forgatókönyvben az árukat a gyártósorból közvetlenül a pótkocsiba szállítják.</span><span class="sxs-lookup"><span data-stu-id="a11f4-156">In this scenario, the goods are moved directly from the production line into the trailer.</span></span> <span data-ttu-id="a11f4-157">Amikor pótkocsi van hozzárendelve a rakodóhely ajtajához, a felhasználó hozzárendeli a helyet a találkozó ütemtervéhez, és ezáltal megadja a helyet az áttároláshoz.</span><span class="sxs-lookup"><span data-stu-id="a11f4-157">When a trailer is assigned to the bay door, a user will assign the location to the appointment schedule and will therefore make the location applicable for cross-docking.</span></span> <span data-ttu-id="a11f4-158">Az alábbi lépések végigvezetik két példán.</span><span class="sxs-lookup"><span data-stu-id="a11f4-158">The following sections walk you through two examples.</span></span>

#### <a name="scenario-1--cross-docking-from-production-to-transfer-orders"></a><span data-ttu-id="a11f4-159">1. forgatókönyv – Termelési rendelések áttárolása átadási rendelésekbe</span><span class="sxs-lookup"><span data-stu-id="a11f4-159">Scenario 1 – Cross-docking from production to transfer orders</span></span>

<span data-ttu-id="a11f4-160">Miután egy terméket a gyártósoron befejezettnek nyilvánítottak, áthelyezik egy rakodóhelyre, ahol azt egy tehergépkocsiba rakják és áthelyezik egy elosztóközpontba.</span><span class="sxs-lookup"><span data-stu-id="a11f4-160">After a product is reported as finished at the production line it is transferred to a bay-door location where it is loaded to a truck and transferred to a distribution center.</span></span> <span data-ttu-id="a11f4-161">Használja az USMF vállalatot.</span><span class="sxs-lookup"><span data-stu-id="a11f4-161">Use company USMF.</span></span>

1.  <span data-ttu-id="a11f4-162">Engedélyezzen új számsorozatot az áttároláshoz.</span><span class="sxs-lookup"><span data-stu-id="a11f4-162">Enable a new number sequence for cross-docking.</span></span> <span data-ttu-id="a11f4-163">Ugrás a **Számsorozatok** oldalt, majd válassza ki a **létrehozása** gombra.</span><span class="sxs-lookup"><span data-stu-id="a11f4-163">Go to the **Number sequences** page, and select the **Generate** button.</span></span> <span data-ttu-id="a11f4-164">A varázsló végigvezeti a folyamaton.</span><span class="sxs-lookup"><span data-stu-id="a11f4-164">A wizard will guide you through the process.</span></span>
2.  <span data-ttu-id="a11f4-165">Hozzon létre áttárolási irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a11f4-165">Create a cross-docking policy.</span></span> <span data-ttu-id="a11f4-166">Ugrás a **áttárolási irányelv párhuzamos** oldalt, majd hozzon létre egy új házirendet nevű **, az átmozgatási rendelés áttárolás**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-166">Go to the **Cross docking policy** page, and create a new policy that is named **Cross docking to transfer order**.</span></span> <span data-ttu-id="a11f4-167">Megjegyzés: csak munka rendelés típusa, amelyből választani lehet lehetőséget, hogy a program **átmozgatási probléma**, és a rendelkezésre álló csak áttárolási stratégia **dátuma és időpontja**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-167">Note that the only work order type that you can select is **Transfer issue**, and the only cross-docking strategy that is available is **Date and time**.</span></span>
3.  <span data-ttu-id="a11f4-168">Hozzon létre munkairányelvet.</span><span class="sxs-lookup"><span data-stu-id="a11f4-168">Create a work policy.</span></span> <span data-ttu-id="a11f4-169">Ugorjon a **Munkairányelvek** oldalra, majd hozzon létre egy új munkairányelvet: **Áttárolás L0101**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-169">Go to the **Work policies** page, and create a new work policy that is named **Cross Dock L0101**.</span></span>
4.  <span data-ttu-id="a11f4-170">Állítson be rakományokat úgy, hogy automatikusan létrehozásra kerüljenek az átadási rendelések.</span><span class="sxs-lookup"><span data-stu-id="a11f4-170">Set up loads so that they are created automatically for transfer orders.</span></span> <span data-ttu-id="a11f4-171">A raktárparamétereknél állítson be rakományokat úgy, hogy automatikusan létrehozásra kerüljenek az átadási rendelések.</span><span class="sxs-lookup"><span data-stu-id="a11f4-171">In the warehouse parameters, set up loads so that they are created automatically when transfer orders are created.</span></span> <span data-ttu-id="a11f4-172">A rakodás előfeltétele annak, hogy az átadási rendelés jogosult legyen az áttárolásra.</span><span class="sxs-lookup"><span data-stu-id="a11f4-172">A load is a prerequisite for making the transfer order eligible for cross-docking.</span></span>
5.  <span data-ttu-id="a11f4-173">Állítsa be a cikk–rakomány hozzárendelését.</span><span class="sxs-lookup"><span data-stu-id="a11f4-173">Set up the item load mapping.</span></span> <span data-ttu-id="a11f4-174">Lépjen a **Cikk–rakomány megfeleltetés** oldalra, majd állítsa be a szabványos rakománysablont a **CarAudio** cikkcsoportnál.</span><span class="sxs-lookup"><span data-stu-id="a11f4-174">Go to the **Item load mapping** page, and set up a standard load template for the **CarAudio** item group.</span></span> <span data-ttu-id="a11f4-175">Ez a leképezés automatikusan áthelyezi a terhelési sablont a terhelésre, amikor az átadási rendelés létrejön.</span><span class="sxs-lookup"><span data-stu-id="a11f4-175">This mapping will automatically insert the load template on the load when the transfer order is created.</span></span>
6.  <span data-ttu-id="a11f4-176">Hozzon létre átmozgatási rendelést.</span><span class="sxs-lookup"><span data-stu-id="a11f4-176">Create a transfer order.</span></span> <span data-ttu-id="a11f4-177">Hozzon létre az L0101 tételszámú átadási rendelést.</span><span class="sxs-lookup"><span data-stu-id="a11f4-177">Create the transfer order for item number L0101.</span></span> <span data-ttu-id="a11f4-178">Mennyiség = 20.</span><span class="sxs-lookup"><span data-stu-id="a11f4-178">Quantity = 20.</span></span>
7.  <span data-ttu-id="a11f4-179">Oldja fel az átadási rendelést a terheléstervező munkaállomástól.</span><span class="sxs-lookup"><span data-stu-id="a11f4-179">Release the transfer order from the load planning workbench.</span></span> <span data-ttu-id="a11f4-180">A **Szállítás** lapon válassza ki a menüelemet, a rakomány tervezési munkaterület és a, a **Kiadás** menüben a rakománysornál válassza a **Raktárba való kiadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a11f4-180">On the **Ship** tab, select the menu item for the load planning workbench and on the **Release** menu of the load line, select **Release to warehouse**.</span></span> <span data-ttu-id="a11f4-181">Az átmozgatási rendelésben jelenleg létezik egy **Átmozgatási probléma** típusú nyitott hullámvonal.</span><span class="sxs-lookup"><span data-stu-id="a11f4-181">An open wave line of type **Transfer issue** now exists for the transfer order.</span></span>
8.  <span data-ttu-id="a11f4-182">Termelési rendelés létrehozása.</span><span class="sxs-lookup"><span data-stu-id="a11f4-182">Create a production order.</span></span> <span data-ttu-id="a11f4-183">Lépjen a **Termelési rendelés** listaoldalt, és hozzon létre egy gyártási rendelést az L0101 termékhez.</span><span class="sxs-lookup"><span data-stu-id="a11f4-183">Go to the **Production order** list page, and create a production order for product L0101.</span></span> <span data-ttu-id="a11f4-184">Mennyiség = 20.</span><span class="sxs-lookup"><span data-stu-id="a11f4-184">Quantity = 20.</span></span> <span data-ttu-id="a11f4-185">A termelési rendelés becsült ideje és indulása.</span><span class="sxs-lookup"><span data-stu-id="a11f4-185">Estimate and start the production order.</span></span> <span data-ttu-id="a11f4-186">A **Kitárolási lista feladása** mező beállítása továbbra is **Nem**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-186">Note that the **Post picking list now** field remains set to **No**.</span></span>
9.  <span data-ttu-id="a11f4-187">Készként jelentés a mobileszközről.</span><span class="sxs-lookup"><span data-stu-id="a11f4-187">Report as finished from the mobile device.</span></span> <span data-ttu-id="a11f4-188">Menjen a mobileszköz-portálra, és válassza ki a **Készként jelentés és betárolás** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="a11f4-188">Go to the mobile device portal and select menu item **Report as finished and put away**.</span></span> <span data-ttu-id="a11f4-189">Most jelentse készként az L0101 cikkszámot a kézben tartott eszközről.</span><span class="sxs-lookup"><span data-stu-id="a11f4-189">Now report as finished L0101 from the handheld device.</span></span> <span data-ttu-id="a11f4-190">Ne feledje, hogy a helyszín a **BAYDOOR**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-190">Note that the put location is **BAYDOOR**.</span></span> <span data-ttu-id="a11f4-191">Ezt a helyet az **Átmozgatási probléma** helymeghatározási irányelvnél találhatja az **Eltárolás** munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="a11f4-191">This location is found from the **Transfer issue** location directive for the **Put** work order type.</span></span> <span data-ttu-id="a11f4-192">Vegye figyelembe, hogy az **Átmozgatási probléma** típusú munkát létrehozták és befejezték.</span><span class="sxs-lookup"><span data-stu-id="a11f4-192">Also notice that work of the type **Transfer issue** has been created and completed.</span></span> <span data-ttu-id="a11f4-193">Lépjen az átmozgatási rendelés munkarészleteihez a munka ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="a11f4-193">Go to the transfer order work details to verify the work.</span></span>
10. <span data-ttu-id="a11f4-194">Most próbáljon 20-szor többet elindítani a termelési rendelésben, majd próbáljon meg jelenteni 20-at a kézben tartott eszköz használatával.</span><span class="sxs-lookup"><span data-stu-id="a11f4-194">Now try to start 20 pieces more on the production order and then try to report 20 ea as finished by using the handheld device.</span></span> <span data-ttu-id="a11f4-195">Ezúttal az **LP-001** helyszín javasolt eltárolási helyszínként.</span><span class="sxs-lookup"><span data-stu-id="a11f4-195">This time, location **LP-001** is suggested as the put location.</span></span> <span data-ttu-id="a11f4-196">Ezt a helyet a helymeghatározási irányelvnél találhatja a **Késztermékek betárolása** lehetőségnél.</span><span class="sxs-lookup"><span data-stu-id="a11f4-196">This location is found from the location directive for **Finished goods put away**.</span></span> <span data-ttu-id="a11f4-197">Ezt a helymeghatározási irányelvet használják, mert nincs áttárolási lehetőség.</span><span class="sxs-lookup"><span data-stu-id="a11f4-197">This location directive is being used, because no opportunity for cross-docking exists.</span></span> <span data-ttu-id="a11f4-198">Az LP-001 átadási rendelést teljes mértékben teljesítette az első áttárolási tevékenység.</span><span class="sxs-lookup"><span data-stu-id="a11f4-198">The transfer order for LP-001 was completely fulfilled by the first cross-docking activity.</span></span>

<span data-ttu-id="a11f4-199">Létrejött és feldolgozásra került a **Késztermékek betárolása** funkció.</span><span class="sxs-lookup"><span data-stu-id="a11f4-199">Work of the type **Finished goods put away** was created and processed.</span></span>

#### <a name="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule"></a><span data-ttu-id="a11f4-200">2. forgatókönyv – Termelési rendelések áttárolása átadási rendelésekbe találkozási ütemtervvel</span><span class="sxs-lookup"><span data-stu-id="a11f4-200">Scenario 2 - Cross-docking from production to transfer orders with an appointment schedule</span></span>

<span data-ttu-id="a11f4-201">Miután egy terméket a gyártósoron befejezettnek nyilvánítottak, áthelyezik egy rakodóhelyre, amelyet a rakodóhelyek kijelölési ütemterve határoz meg.</span><span class="sxs-lookup"><span data-stu-id="a11f4-201">After a product is reported as finished at the production line it is transferred to a bay-door location that is identified by an appointment schedule for the bay-door locations.</span></span> <span data-ttu-id="a11f4-202">Használja az USMF vállalatot.</span><span class="sxs-lookup"><span data-stu-id="a11f4-202">Use company USMF.</span></span>

1.  <span data-ttu-id="a11f4-203">Módosítsa az áttárolási irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a11f4-203">Change the cross-docking policy.</span></span> <span data-ttu-id="a11f4-204">Módosítsa az 1. forgatókönyvben létrehozott áttárolási irányelvet **Az áttárolási igényhez meg kell adni a helyet.** jelölőnégyzet bejelölésével.</span><span class="sxs-lookup"><span data-stu-id="a11f4-204">Change the cross-docking policy that you created in scenario 1 by selecting the **Cross docking demand requires location** check box.</span></span>
2.  <span data-ttu-id="a11f4-205">Hozzon létre új átadási rendelést.</span><span class="sxs-lookup"><span data-stu-id="a11f4-205">Create a new transfer order.</span></span>
3.  <span data-ttu-id="a11f4-206">Nyissa meg a **Rakománytervezési munkaterületet**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-206">Open the **Load planning workbench**.</span></span>
4.  <span data-ttu-id="a11f4-207">A rakománytervezési munkaterületről lépj a **Rakományok** szakaszhoz, és válassza ki a **Találkozó ütemezése** lehetőséget a **Szállítás** menüben egy új találkozóütemezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a11f4-207">From the load planning workbench, go to the **Loads** section, and select **Appointment schedule** on the **Transportation** menu to create a new appointment schedule.</span></span> <span data-ttu-id="a11f4-208">Ne feledje, hogy a találkozási ütemterv hivatkozik az átmozgatási rendelésre a **Rendelés száma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a11f4-208">Note that the appointment schedule has a reference to the transfer order in the **Order number** field.</span></span> <span data-ttu-id="a11f4-209">A **Tervezett kezdő dátum és idő adott helyen** mezőben beállíthatja a megbeszélés dátumát és idejét.</span><span class="sxs-lookup"><span data-stu-id="a11f4-209">In the **Planned start date/time at location** field, you can set the date and time for the appointment.</span></span> <span data-ttu-id="a11f4-210">Ezt a dátumot és időt fogják használni, ha az áttárolási igényt az áttárolási folyamat során kiemelték.</span><span class="sxs-lookup"><span data-stu-id="a11f4-210">This date and time will be used when cross-docking demand is prioritized during the cross-docking process.</span></span> <span data-ttu-id="a11f4-211">Az ezen a területen beállított dátum és idő frissíti a **Rakomány indításának ütemezett dátuma és időpontja** mezőt a kapcsolódó rakománynál.</span><span class="sxs-lookup"><span data-stu-id="a11f4-211">The date and time that you set in this field will update the **Scheduled load shipping date and time** field on the corresponding load.</span></span> <span data-ttu-id="a11f4-212">A **Szállítás részletei** gyorslap meghatározza az átmozgatási rendelés helyét.</span><span class="sxs-lookup"><span data-stu-id="a11f4-212">The location on the **Shipping details** FastTab determines the location that the transfer order is shipped on.</span></span>
5.  <span data-ttu-id="a11f4-213">A **Rakománytervező munkaterületen** adja ki a raktárnak.</span><span class="sxs-lookup"><span data-stu-id="a11f4-213">On the **Load planning workbench** release to the warehouse.</span></span>
6.  <span data-ttu-id="a11f4-214">Hozzon létre egy gyártási rendelést az **L0101** cikkszámhoz, és állítsa az állapotot **Elindítva** értékre, 20-as mennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="a11f4-214">Create a production order for item number **L0101**, and set the status to **Started**, with a quantity of 20.</span></span>
7.  <span data-ttu-id="a11f4-215">Készként jelentés a mobileszközről.</span><span class="sxs-lookup"><span data-stu-id="a11f4-215">Report as finished from the mobile device.</span></span>
8.  <span data-ttu-id="a11f4-216">Menjen a mobileszköz-portálra, és válassza ki a **Készként jelentés és betárolás** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="a11f4-216">Go to the mobile device portal, and select the **Report as finished and put away** menu item.</span></span>
9.  <span data-ttu-id="a11f4-217">Jelentse készként az **L0101** cikkszámot a kézben tartott eszközről.</span><span class="sxs-lookup"><span data-stu-id="a11f4-217">Report item number **L0101** as finished from the handheld device.</span></span> <span data-ttu-id="a11f4-218">Ne feledje, hogy a helyszín a **BAYDOOR 2**.</span><span class="sxs-lookup"><span data-stu-id="a11f4-218">Note that the put location is now **BAYDOOR 2**.</span></span> <span data-ttu-id="a11f4-219">Ezt a helyet a találkozási ütemterv alapján találja meg az **Átmozgatási bevételezés** helymeghatározási irányelv helyett.</span><span class="sxs-lookup"><span data-stu-id="a11f4-219">This location is found from the appointment schedule instead of the **Transfer receipt** location directive.</span></span>

### <a name="additional-information"></a><span data-ttu-id="a11f4-220">További információk</span><span class="sxs-lookup"><span data-stu-id="a11f4-220">Additional information</span></span>

-   <span data-ttu-id="a11f4-221">Az áttárolási forgatókönyv támogatott a kötegelt és sorozatosan vezérelt cikkeknél, mind a köteg-, mind a sorozatszám-dimenziókkal, amelyeket a foglalási hierarchiában fent és alul találhat meg.</span><span class="sxs-lookup"><span data-stu-id="a11f4-221">The cross docking scenario is supported for batch and serial controlled items, both with the batch and serial number dimensions defined above and below location in the reservation hierarchy.</span></span>



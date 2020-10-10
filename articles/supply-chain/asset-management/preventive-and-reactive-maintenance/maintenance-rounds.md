---
title: Karbantartási körök
description: Ez a témakör az Eszközkezelés karbantartási köreit ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRoundTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 63cb2614b2037fac1129c7d2f82a26dac41a3490
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889961"
---
# <a name="maintenance-rounds"></a><span data-ttu-id="b2182-103">Karbantartási körök</span><span class="sxs-lookup"><span data-stu-id="b2182-103">Maintenance rounds</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b2182-104">Az **Eszközkezelésben** különböző olyan eszközökhöz lehet karbantartási köröket létrehozni, amelyekhez rendszeres időközönként hasonló feladatot kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="b2182-104">In **Asset Management**, you can create maintenance rounds for various assets, on which you need to carry out a similar task at regular intervals.</span></span> <span data-ttu-id="b2182-105">Például olyan kenési vagy biztonsági ellenőrzési feladatok esetén, amelyeket több gépen kell végrehajtani adott időközönként.</span><span class="sxs-lookup"><span data-stu-id="b2182-105">For example, lubrication jobs or safety inspection jobs that need to be carried out on a number of machines within the same intervals.</span></span> <span data-ttu-id="b2182-106">Első lépésként létre kell hozni egy karbantartási kört, többek között azokat az eszközöket, amelyekhez ugyanazt a karbantartási feladatot kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="b2182-106">First step is to create a maintenance round, including assets that require the same form of maintenance job.</span></span> <span data-ttu-id="b2182-107">Ezután ütemezheti a karbantartási köröket.</span><span class="sxs-lookup"><span data-stu-id="b2182-107">Next, you schedule the maintenance rounds.</span></span> <span data-ttu-id="b2182-108">Ha befejezte a karbantartási körök ütemezését, akkor az **Összes karbantartási ütemezés** és a **Nyitott karbantartási ütemezés** sorban láthatja a körhöz kapcsolódó feladatok rekordjait.</span><span class="sxs-lookup"><span data-stu-id="b2182-108">When you have completed the maintenance rounds schedule, you can see all the job records relating to the round in the **All maintenance schedule** and **Open maintenance schedule lines**.</span></span>

>[!NOTE]
><span data-ttu-id="b2182-109">A karbantartási köröket a munkavégzési helyszíneken is be lehet állítani, hogy a munkavégzési helyszíneken működő eszközökön, a köralapú munkarendelés létrehozásakor történjen meg a feladat.</span><span class="sxs-lookup"><span data-stu-id="b2182-109">Maintenance rounds can also be set up on functional locations to be completed on the assets installed on the functional location at the time of creation of the round-based work order.</span></span> <span data-ttu-id="b2182-110">A karbantartási körök munkavégzési helyszíneken történő beállításáról a [Munkavégzési helyszínek létrehozása](../functional-locations/create-functional-locations.md) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="b2182-110">Refer to [Create functional locations](../functional-locations/create-functional-locations.md) for more information on the setup of maintenance rounds on functional locations.</span></span>

## <a name="set-up-a-maintenance-round"></a><span data-ttu-id="b2182-111">Karbantartási kör beállítása</span><span class="sxs-lookup"><span data-stu-id="b2182-111">Set up a maintenance round</span></span>

1. <span data-ttu-id="b2182-112">Kattintson az **Eszközkezelés** > **Beállítások** > **Megelőző karbantartás** > **Karbantartási körök** elemre.</span><span class="sxs-lookup"><span data-stu-id="b2182-112">Click **Asset management** > **Setup** > **Preventive maintenance** > **Maintenance rounds**.</span></span>

2. <span data-ttu-id="b2182-113">Új karbantartási kör létrehozásához kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2182-113">Click **New** to create a new maintenance round.</span></span>

3. <span data-ttu-id="b2182-114">Szúrja be és adja meg az azonosítót a **Karbantartási kör** mezőbe, és adja meg a karbantartási kör nevét a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b2182-114">Insert and ID in the **Maintenance round** field, and a name for the maintenance round in the **Name** field.</span></span>

4. <span data-ttu-id="b2182-115">A **Kezdő dátum** mezőben válassza ki a kör kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="b2182-115">Select a start date for the round in the **Start date** field.</span></span>

5. <span data-ttu-id="b2182-116">A **Befejezés ennyi nap múlva** és **Befejezés ennyi óra múlva** mezőkbe a várható záró dátumot napokban vagy órákban lehet beszúrni.</span><span class="sxs-lookup"><span data-stu-id="b2182-116">In the **Finish within days** and **Finish within hours** fields, you can insert expected end date in days or hours.</span></span> <span data-ttu-id="b2182-117">A várható záró dátumot a karbantartási ütemezés sorainak létrehozásakor, a kezdő dátumhoz viszonyítva számítja ki a rendszer.</span><span class="sxs-lookup"><span data-stu-id="b2182-117">The expected end date is calculated relative to the start date, which is calculated when maintenance schedule lines are created.</span></span> <span data-ttu-id="b2182-118">Adja meg például a „7” számot a **Befejezés ennyi nap múlva** mezőben, ha a kapcsolódó feladatot a kezdő dátumtól egy héten belül kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="b2182-118">For example, you can insert "7" in the **Finish within days** field to indicate that the related job should be completed within a week from the start date.</span></span>

6. <span data-ttu-id="b2182-119">Válassza az „Igen” lehetőséget az **Automatikus létrehozás** váltógombnál, ha a munkarendeléseket automatikusan létre szeretné hozni az ebből a karbantartási körből létrehozott karbantartási ütemezési sorokból.</span><span class="sxs-lookup"><span data-stu-id="b2182-119">Select "Yes" on the **Auto create** toggle button if work orders should automatically be created from maintenance schedule lines that are created from this maintenance round.</span></span>

7. <span data-ttu-id="b2182-120">A **Munkarendelés típusa** mezőben válassza ki azt a munkarendelés-típust, amelyet a karbantartási körből létrehozott munkarendelésekhez kíván használni.</span><span class="sxs-lookup"><span data-stu-id="b2182-120">In the **Work order type** field, select the work order type to be used on work orders created from this maintenance round.</span></span>

8. <span data-ttu-id="b2182-121">A **Szolgáltatásszint** mezőben válassza ki a munkarendelés azon szolgáltatásszintjét, amelyet a karbantartási körből létrehozott munkarendelésekhez kíván használni.</span><span class="sxs-lookup"><span data-stu-id="b2182-121">In the **Service level** field, select the work order service level to be used on work orders created from this maintenance round.</span></span>

9. <span data-ttu-id="b2182-122">Az **Eszközsorok** gyorslapon a **Hozzáadás** gombra kattintva vehet fel eszközt a karbantartási körbe.</span><span class="sxs-lookup"><span data-stu-id="b2182-122">On the **Asset lines** FastTab, click **Add** to add an asset to the maintenance round.</span></span>

10. <span data-ttu-id="b2182-123">A rendszer automatikusan beszúrja a sorszámot a **Sorszám** mezőbe; ez jelöli az eszközök karbantartási körön belüli sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="b2182-123">A line number is automatically inserted in the **Line number** field to indicate the sequence of the assets in maintenance round.</span></span>

11. <span data-ttu-id="b2182-124">Az **Eszköz** mezőben válassza ki az eszközt.</span><span class="sxs-lookup"><span data-stu-id="b2182-124">Select the asset in the **Asset** field.</span></span>

12. <span data-ttu-id="b2182-125">A **Karbantartási feladat típusa** mezőben válassza ki a karbantartási feladat típusát az eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="b2182-125">Select the maintenance job type for the asset in the **Maintenance job type** field.</span></span>

13. <span data-ttu-id="b2182-126">Ha szükséges, adja meg a karbantartási feladat típusához a **Karbantartási feladat típusának változata** és a **Kereskedelem** beállítást.</span><span class="sxs-lookup"><span data-stu-id="b2182-126">If required, select **Maintenance job typ variant** and **Trade** related to the maintenance job type.</span></span>

14. <span data-ttu-id="b2182-127">Válassza ki az ismétlődést (nap, hét stb.) az **Időszak típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b2182-127">Select the recurrence (day, week, etc.) in the **Period type** field.</span></span>

15. <span data-ttu-id="b2182-128">Az **Időszak gyakorisága** mezőben adja meg a karbantartási körhöz tartozó ismétlődések számát.</span><span class="sxs-lookup"><span data-stu-id="b2182-128">In the **Period frequency** field, insert the number of recurrences for the maintenance round.</span></span> <span data-ttu-id="b2182-129">Példa: Ha a „Nap” beállítást adta meg az **Időszak típusa** mezőben, és itt a „7” írja be, akkor a megelőző karbantartás ütemezése során a program hetente egyszer hoz létre új sorokat a karbantartási körhöz.</span><span class="sxs-lookup"><span data-stu-id="b2182-129">Example: If you have selected "Day" in the **Period type** field, and you insert the number "7" in this field, new maintenance round lines are created during preventive maintenance scheduling once a week.</span></span>

16. <span data-ttu-id="b2182-130">A **Kezdő dátum** mezőben válassza ki azt a kezdő dátumot az eszközhöz, amelyet fel szeretne venni a karbantartási körbe.</span><span class="sxs-lookup"><span data-stu-id="b2182-130">Select a start date for the asset to be included in the maintenance round in the **Start date** field.</span></span> <span data-ttu-id="b2182-131">Ez a dátum eltérhet a karbantartási körhöz megadott kezdő dátumtól.</span><span class="sxs-lookup"><span data-stu-id="b2182-131">This date may differ from the start date set on the maintenance round.</span></span>

17. <span data-ttu-id="b2182-132">A 9–16. lépések megismétlésével további eszközöket vehet fel a karbantartási körbe.</span><span class="sxs-lookup"><span data-stu-id="b2182-132">Repeat steps 9-16 to add more assets to the maintenance round.</span></span>

18. <span data-ttu-id="b2182-133">A **Munkavégzési helyszín sorai** gyorslapon a **Hozzáadás** gombra kattintva vehet fel munkavégzési helyszínt a karbantartási körbe.</span><span class="sxs-lookup"><span data-stu-id="b2182-133">On the **Functional location lines** FastTab, click **Add** to add a functional location to the maintenance round.</span></span> <span data-ttu-id="b2182-134">Tekintse át a fenti kapcsolódó mezőkben lévő leírást.</span><span class="sxs-lookup"><span data-stu-id="b2182-134">Refer to the description of the related fields above.</span></span> <span data-ttu-id="b2182-135">Ugyanezek a mezők használhatók az eszközsorok létrehozásához, de szükség esetén a **Gyártó** és a **Modell** beállítást is megadhatja a munkavégzési helyszínhez.</span><span class="sxs-lookup"><span data-stu-id="b2182-135">The same fields are available as for creating an asset line, but you can also select **Manufacturer** and **Model** for a functional location, if required.</span></span> <span data-ttu-id="b2182-136">Ha csak egy munkavégzési helyszínt választ ki egy sorban, de nem adja meg az **Eszköztípus**, a **Gyártó**, a **Modell**, a **Karbantartási feladat típusa**, a **Karbantartási feladat típusának változata** és a **Kereskedelem** beállítást, az adott munkavégzési helyszínhez a karbantartási ütemezés időpontjában kapcsolódó összes eszköz a szerepelni fog a karbantartási körben.</span><span class="sxs-lookup"><span data-stu-id="b2182-136">If you only select a functional location on a line, but make no selections in **Asset type**, **Manufacturer**, **Model**, **Maintenance job type**, **Maintenance job type variant** and **Trade**, all assets related to that functional location at the time of maintenance scheduling will be included in the maintenance round.</span></span>

19. <span data-ttu-id="b2182-137">A **Csoportok** gyorslap **Hozzáadás** gombjára kattintva kiválaszthatja a karbantartási körben szerepeltetni kívánt munkarendelés-gyűjtőt.</span><span class="sxs-lookup"><span data-stu-id="b2182-137">On the **Pools** FastTab, click **Add** to select a work order pool to be included in the maintenance round.</span></span> <span data-ttu-id="b2182-138">Egy karbantartási körhöz több munkarendelés-gyűjtő is csatlakoztatható.</span><span class="sxs-lookup"><span data-stu-id="b2182-138">Several work order pools can be connected to one maintenance round.</span></span>

20. <span data-ttu-id="b2182-139">Mentse a beállításokat.</span><span class="sxs-lookup"><span data-stu-id="b2182-139">Save your setup.</span></span>

>[!NOTE]
><span data-ttu-id="b2182-140">A **Fejléc** gyorslap **Részletek** csoportjában lévő **Eszközök** és **Sorok** mezőjében látható a kiválasztott karbantartási körhöz kapcsolódó eszközök és sorok teljes száma.</span><span class="sxs-lookup"><span data-stu-id="b2182-140">The **Assets** and **Lines** fields located in the **Details** group on the **Header** FastTab show the total number of assets and lines related to the selected maintenance round.</span></span>

<span data-ttu-id="b2182-141">Az alábbi ábra három tárgyi eszközt tartalmazó karbantartási fordulóra mutat be példát.</span><span class="sxs-lookup"><span data-stu-id="b2182-141">The illustration below shows and example of a maintenance round containing three assets.</span></span>

![1. ábra](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a><span data-ttu-id="b2182-143">Karbantartási körök ütemezése</span><span class="sxs-lookup"><span data-stu-id="b2182-143">Schedule maintenance rounds</span></span>

<span data-ttu-id="b2182-144">Ha beállította a karbantartási kört, akkor ütemezési feladatot futtathat a karbantartási körhöz kapcsolódó feladatok ütemezéséhez.</span><span class="sxs-lookup"><span data-stu-id="b2182-144">When you've set up a maintenance round, you run a schedule job to schedule all the jobs related to the maintenance round.</span></span>

1. <span data-ttu-id="b2182-145">Kattintson az **Eszközkezelés** > **Időszakos** > **Megelőző karbantartás** > **Karbantartási körök ütemezése** vagy az **Eszközkezelés** > **Közös** > **Karbantartási ütemezés** > **Összes karbantartási ütemezés** vagy a **Nyitott karbantartási ütemezés** vagy a **Nyitott karbantartási ütemezési csoportok** > a lista kiválasztott karbantartási ütemezési sora > **Karbantartási körök** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2182-145">Click **Asset management** > **Periodic** > **Preventive maintenance** > **Schedule maintenance rounds**, or **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** > select maintenance schedule line in the list > **Maintenance rounds** button.</span></span>

2. <span data-ttu-id="b2182-146">Az **Időszak** mezőben válassza ki az ütemezési feladathoz használandó időszaktípust.</span><span class="sxs-lookup"><span data-stu-id="b2182-146">In the **Period** field, select the period type to be used for the scheduling job.</span></span>

3. <span data-ttu-id="b2182-147">Az **Időszak gyakorisága** mezőben adja meg, hogy hány időszak szerepeljen az ütemezési feladatban.</span><span class="sxs-lookup"><span data-stu-id="b2182-147">In the **Period frequency** field, insert the number of periods to be included in the scheduling job.</span></span> <span data-ttu-id="b2182-148">Az ütemezés az aktuális dátummal kezdődik.</span><span class="sxs-lookup"><span data-stu-id="b2182-148">The start of the scheduling is the current date.</span></span>

4. <span data-ttu-id="b2182-149">Ha egy munkarendelést automatikusan létre kell hozni egy karbantartási kör alapján, akkor adja meg az „Igen” értéket az **Automatikus létrehozás** váltógombnál.</span><span class="sxs-lookup"><span data-stu-id="b2182-149">Select "Yes" on the **Auto create** toggle button if a work order should automatically be created on the basis of a maintenance round.</span></span>

>[!NOTE]
><span data-ttu-id="b2182-150">Ha ennek a váltógombnak az értéke „Igen”, és az **Automatikus létrehozás** váltógomb értéke is „Igen” a **Karbantartási körök** űrlapon lévő karbantartási körnél, akkor a munkarendelések a karbantartási kör sorai alapján jönnek létre, és „Munkarendelés létrehozva” állapotú karbantartási ütemezési sorok is létrejönnek.</span><span class="sxs-lookup"><span data-stu-id="b2182-150">If this toggle button is set to "Yes", and the **Auto create** toggle button is also set to "Yes" on the maintenance round in **Maintenance rounds** form, work orders are created based on the maintenance round lines, and maintenance schedule lines with status "Work order created" are also created.</span></span> <span data-ttu-id="b2182-151">Ha csak az egyik **Automatikus létrehozás** váltógomb értéke „Igen”, ebben a legördülő menüben vagy a **Karbantartási körök** beállításnál, csak a „Létrehozott” állapotú karbantartási ütemezési sorok jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="b2182-151">If only one of the **Auto create** toggle buttons is set to "Yes", in this drop-down or in **Maintenance rounds**, only maintenance schedule lines are created with status "Created".</span></span> <span data-ttu-id="b2182-152">Ebben az esetben nem jön létre munkarendelés.</span><span class="sxs-lookup"><span data-stu-id="b2182-152">In that case, no work orders are created.</span></span>

5. <span data-ttu-id="b2182-153">Ha szükséges, kiválaszthat konkrét ütemezési köröket, illetve másik kezdő dátumot az ütemezési feladathoz.</span><span class="sxs-lookup"><span data-stu-id="b2182-153">If required, you can select specific rounds or another start date for the schedule job.</span></span> <span data-ttu-id="b2182-154">Kattintson a **Szűrő** elemre, és adja hozzá a szerepeltetni kívánt köröket.</span><span class="sxs-lookup"><span data-stu-id="b2182-154">Click **Filter**, and add the rounds to be included.</span></span>

6. <span data-ttu-id="b2182-155">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2182-155">Click **OK**.</span></span>

7. <span data-ttu-id="b2182-156">Most már látni fogja a karbantartási körök feladatait az **Eszközkezelés** > **Közös** > **Karbantartási ütemezés** > **Összes karbantartási ütemezés** vagy **Nyitott karbantartási ütemezés** sorban.</span><span class="sxs-lookup"><span data-stu-id="b2182-156">You are now able to see the maintenance rounds jobs in **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines**.</span></span> <span data-ttu-id="b2182-157">Ha az ütemezett köröket munkarendelési csoporttal kapcsolja össze, akkor a karbantartási ütemezés sorai is láthatók a **Nyitott karbantartási ütemezési csoportok** részen.</span><span class="sxs-lookup"><span data-stu-id="b2182-157">If the scheduled rounds are connected to a work order pool, you also see maintenance schedule lines in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="b2182-158">A kör alapján létrehozott karbantartási ütemezési sorok hivatkozástípusa „Karbantartási körök”.</span><span class="sxs-lookup"><span data-stu-id="b2182-158">Maintenance schedule lines created from a round have the reference type "Maintenance rounds".</span></span>

<span data-ttu-id="b2182-159">Az alábbi két illusztráció egy ütemezési feladatot mutat be a **Karbantartási körök ütemezése** párbeszédablakban, és az ütemezési feladat alapján az **Összes karbantartási ütemezésben** létrehozott karbantartási ütemezési sorokat.</span><span class="sxs-lookup"><span data-stu-id="b2182-159">The two illustrations below show a schedule job in the **Schedule maintenance rounds** dialog, and the maintenance schedule lines created in **All maintenance schedule** based on that schedule job.</span></span>

![2. ábra](media/14-preventive-maintenance.png)

![3. ábra](media/15-preventive-maintenance.png)

- <span data-ttu-id="b2182-162">Ha a munkarendelések létrehozása manuálisan, egyszállítói garanciával fedezett eszközhöz történik, egy párbeszédpanel jelenik meg, amely a felhívja a felhasználó figyelmét a jótállásra.</span><span class="sxs-lookup"><span data-stu-id="b2182-162">When work orders are manually created on assets that are covered by a vendor warranty, a dialog box is shown to make the user aware of the warranty.</span></span> <span data-ttu-id="b2182-163">A munkarendelés létrehozása ezt követően visszavonható.</span><span class="sxs-lookup"><span data-stu-id="b2182-163">The creation of the work order can then be canceled.</span></span> <span data-ttu-id="b2182-164">Az automatikusan létrehozott munkarendelések a jótállási kapcsolat keresése ki van hagyva.</span><span class="sxs-lookup"><span data-stu-id="b2182-164">The check for a warranty relation is omitted for work orders that are automatically created.</span></span>  
- <span data-ttu-id="b2182-165">A **Futtatás a háttérben** gyorslapon beállítható kötegelt feladat a körök szabályos időközönként történő ütemezéséhez.</span><span class="sxs-lookup"><span data-stu-id="b2182-165">You can set up a batch job on the **Run in the background** FastTab to schedule rounds at regular intervals.</span></span>  
- <span data-ttu-id="b2182-166">Ha egy kör több munkarendelési gyűjtőben is szerepel (lásd: [Munkarendelés-gyűjtők](../work-orders/work-order-pools.md)), akkor minden gyűjtőhöz egy rekord jelenik meg a **Nyitott karbantartási ütemezési csoportok** részen.</span><span class="sxs-lookup"><span data-stu-id="b2182-166">If a round is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="b2182-167">Ez a munkarendelés-gyűjtők szűrési beállításainak optimalizálására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b2182-167">This is done to optimize the filtering options for work order pools.</span></span>


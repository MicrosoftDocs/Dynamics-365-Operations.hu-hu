---
title: Költség- és dátumellenőrzés
description: Ez a cikk az Eszközkezelés költség és dátum kontroll funkcióját ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918395"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="0b356-103">Költség- és dátumellenőrzés</span><span class="sxs-lookup"><span data-stu-id="0b356-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="0b356-104">Az eszközkezelésben kiszámíthatja a költségeket, és így áttekintést kaphat a tényleges költségekről a költségvetésben meghatározott költségekkel szemben az eszközökön, munkavégzési helyszínekn vagy munkarendeléseken.</span><span class="sxs-lookup"><span data-stu-id="0b356-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="0b356-105">A tényleges költségek a feladott tranzakciókon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="0b356-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="0b356-106">Ha a munkarendelések tényleges kezdési és befejezési dátumaival szeretné összehasonlítani az ütemezett kezdési és befejezési dátumokat, akkor dátumszámítást is végezhet.</span><span class="sxs-lookup"><span data-stu-id="0b356-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="0b356-107">Költség-ellenőrzés az eszközökhöz, a munkavégzési helyszínekhez és a munkarendelésekhez</span><span class="sxs-lookup"><span data-stu-id="0b356-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="0b356-108">Az eszközökre, munkavégzési helyszínekre és munkarendelésekre vonatkozó számítások szinte megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="0b356-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="0b356-109">Az egyetlen különbség az, hogy az eszközök és munkavégzési helyszínek esetén a számításban szerepelnek aleszközök és al-munkavégzési helyszínek is.</span><span class="sxs-lookup"><span data-stu-id="0b356-109">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="0b356-110">A dátum a tranzakció dátuma, amikor a regisztráció rögzítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="0b356-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="0b356-111">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszközköltség ellenőrzése** vagy **Munkavégzési helyszín költségeinek ellenőrzése** elemre, vagy az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelések költségellenőrzése** elemre.</span><span class="sxs-lookup"><span data-stu-id="0b356-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="0b356-112">Válassza ki a kiszámítani kívánt időszakot itt: **Eszköz költségkontrollja** / **Munkavégzési helyszín költségellenőrzése** / **Munkarendelés költségének ellenőrzése**.</span><span class="sxs-lookup"><span data-stu-id="0b356-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a period to be calculated.</span></span>

3. <span data-ttu-id="0b356-113">Szükség szerint válasszon egy pénzügyi dimenziókészlet elemet, amit szerepeltetni szeretne a számításban.</span><span class="sxs-lookup"><span data-stu-id="0b356-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="0b356-114">Ha a nulla költséget tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="0b356-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="0b356-115">A **Szint** mezőben megadhatja, hogy a költségellenőrzési sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="0b356-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> <span data-ttu-id="0b356-116">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínek hierarchiájához, akkor a munkavégzési helyszínekhez tartozó költségellenőrzési sorok a legfelső szinten jelennek meg, így a sorban szereplő órák hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="0b356-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="0b356-117">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely az költségellenőrzés minden sorát megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="0b356-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="0b356-118">Ha a számításban szerepeltetni szeretné ezt az oszlopot, válassza az „Igen” beállítást a **Nyitott vállalt költség megjelenítése** gombbal.</span><span class="sxs-lookup"><span data-stu-id="0b356-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="0b356-119">Ha az aleszközökhöz tartozó költségeket külön sorként szeretné megjeleníteni, állítsa az **Aleszközök szerepeltetése** beállítást „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="0b356-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="0b356-120">Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket/munkavégzési helyszíneket/munkarendeléseket a **Szerepeltetni kívánt rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="0b356-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="0b356-121">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="0b356-121">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="0b356-122">Az alábbi ábrán az **Eszközköltség ellenőrzése** párbeszédpanel egyik példája látható.</span><span class="sxs-lookup"><span data-stu-id="0b356-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

![1. ábra](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="0b356-124">Az **Eszközköltség ellenőrzése** lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="0b356-124">In the **Group by...** action pane groups on the **Asset cost control** page, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="0b356-125">A kiválasztott műveleti ablaktábla gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="0b356-125">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="0b356-126">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="0b356-126">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="0b356-127">Az alábbi ábrán az **Eszközköltség kontrollja** számítási eredmény egyik példája látható.</span><span class="sxs-lookup"><span data-stu-id="0b356-127">The figure below shows an example of calculation results in **Asset cost control**.</span></span>

![2. ábra](media/02-controlling-and-reporting.png)

<span data-ttu-id="0b356-129">A költség számításának másik módja az, ha többszörös kiválasztással kiválasztja az eszközöket az **Összes eszköz** vagy **Aktív eszközök** pontban.</span><span class="sxs-lookup"><span data-stu-id="0b356-129">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="0b356-130">Ezután kattintson a **Költségellenőrzés** gombra az **Általános** lapon. Az **Eszközköltség ellenőrzése** párbeszédpanelen a program automatikusan beilleszti a kiválasztott eszközöket az **Eszköz** mezőbe a **Belefoglalandó rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="0b356-130">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="0b356-131">Kattintson az **OK** gombra, és megjelenik a kiválasztott eszközökre vonatkozó költségszámítás.</span><span class="sxs-lookup"><span data-stu-id="0b356-131">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="0b356-132">Ugyanez az eljárás hajtható végre az **Összes munkavégzési helyszín** vagy **Aktív munkavégzési helyszínek** pontban található munkavégzési helyszíneknél, valamint a munkarendeléseknél az **Összes munkarendelés** vagy **Aktív munkarendelések** pontban.</span><span class="sxs-lookup"><span data-stu-id="0b356-132">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>

>[!NOTE]
><span data-ttu-id="0b356-133">Az **Eredeti költségvetés** mezőben a munkarendelési előrejelzésből származó költségvetési költségek láthatók.</span><span class="sxs-lookup"><span data-stu-id="0b356-133">The **Original budget** field shows budget costs from the work order forecast.</span></span> <span data-ttu-id="0b356-134">A **Vállalt költség** mező a jogi személy által vállalt fizetendő összes költséget mutatja.</span><span class="sxs-lookup"><span data-stu-id="0b356-134">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> <span data-ttu-id="0b356-135">A **Nyitott vállalt költség** mező a megrendelt vagy bevételezett, de még ki nem fizetett cikkek, órák vagy szolgáltatások kifizetésére vonatkozó kötelezettségeket mutatja.</span><span class="sxs-lookup"><span data-stu-id="0b356-135">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> <span data-ttu-id="0b356-136">Ha minden felhasználási regisztráció fel van adva, a kapcsolódó költségek a **Tényleges költség** mezőben szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="0b356-136">When all consumption registrations have been posted, the related costs are included in the **Actual cost** field.</span></span>

## <a name="work-order-date-control"></a><span data-ttu-id="0b356-137">Munkarendelési dátum ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="0b356-137">Work order date control</span></span>

<span data-ttu-id="0b356-138">Ezen a lapon áttekintést kaphat a munkarendelések várható kezdő és befejező dátumairól, a tényleges kezdési és befejezési dátumokhoz képest.</span><span class="sxs-lookup"><span data-stu-id="0b356-138">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="0b356-139">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelés dátumkontrollja** elemre.</span><span class="sxs-lookup"><span data-stu-id="0b356-139">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="0b356-140">Kattintson a **Számítás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0b356-140">Click **Calculate**.</span></span>

3. <span data-ttu-id="0b356-141">A **Munkavégzési helyszín** mezőben válassza ki a munkavégzési helyszínt.</span><span class="sxs-lookup"><span data-stu-id="0b356-141">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="0b356-142">A **Kezdő dátum** és **Záró dátum** mezőben válassza ki azt az időszakot, amelyhez el szeretné végezni a számítást.</span><span class="sxs-lookup"><span data-stu-id="0b356-142">Insert the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="0b356-143">Minden olyan munkarendelést tartalmaz, amely várhatóan az adott időszakon belül kezdődik.</span><span class="sxs-lookup"><span data-stu-id="0b356-143">All work orders with expected start within the period will be included.</span></span>

5. <span data-ttu-id="0b356-144">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0b356-144">Click **OK**.</span></span>

6. <span data-ttu-id="0b356-145">Az Eszközórák ellenőrzése lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="0b356-145">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="0b356-146">A kiválasztott műveleti ablaktábla gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="0b356-146">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="0b356-147">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="0b356-147">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="0b356-148">Az alábbi ábrán a **Munkarendelés dátumkontrollja** számítási eredmény egyik példája látható.</span><span class="sxs-lookup"><span data-stu-id="0b356-148">The figure below shows an example of calculation results in **Work order date control**.</span></span>

![3. ábra](media/03-controlling-and-reporting.png)

- <span data-ttu-id="0b356-150">Az **Átlagos kezdő késleltetés** mező a munkarendelés tervezett kezdési dátuma és a tényleges kezdési dátum közötti különbséget jeleníti meg napokban.</span><span class="sxs-lookup"><span data-stu-id="0b356-150">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="0b356-151">Ha például a tényleges kezdési dátum két nappal az ütemezett kezdési dátum előtt volt, akkor ebben a mezőben a „-2” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="0b356-151">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="0b356-152">Az **Átlagos záró késleltetés** mező a munkarendelés tervezett záró dátuma és a tényleges záró dátum közötti különbséget jeleníti meg napokban.</span><span class="sxs-lookup"><span data-stu-id="0b356-152">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="0b356-153">Ha például a tényleges záró dátum három nappal az ütemezett kezdési dátum után volt, akkor ebben a mezőben a „3” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="0b356-153">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="0b356-154">Az **Előfordulások** mező mutatja, hogy hányszor fordulnak elő eltérések az ütemezett és a tényleges kezdési dátumra nézve, valamint az ütemezett és a tényleges befejezési dátumra nézve a munkarendelésen.</span><span class="sxs-lookup"><span data-stu-id="0b356-154">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>


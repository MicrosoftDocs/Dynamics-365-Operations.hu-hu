---
title: Költség- és dátumellenőrzés
description: Ez a cikk az Eszközkezelés költség és dátum kontroll funkcióját ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBICostControlWorkspace, EntAssetWorkOrderDateControl, EntAssetWorkOrderForecastCostInfoPart, EntAssetMaintenanceCostTrans, EntAssetWorkOrderDateControlCalcDialog, EntAssetCostControl, EntAssetCostObjectCalendar, EntAssetWorkOrderCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1de12233ff296f77ba9984fa8d957d4c2bc90b3f
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019075"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="d7c51-103">Költség- és dátumellenőrzés</span><span class="sxs-lookup"><span data-stu-id="d7c51-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d7c51-104">Az eszközkezelésben kiszámíthatja a költségeket, és így áttekintést kaphat a tényleges költségekről a költségvetésben meghatározott költségekkel szemben az eszközökön, munkavégzési helyszínekn vagy munkarendeléseken.</span><span class="sxs-lookup"><span data-stu-id="d7c51-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="d7c51-105">A tényleges költségek a feladott tranzakciókon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="d7c51-105">Actual costs are based on posted transactions.</span></span> 

<span data-ttu-id="d7c51-106">Ha a munkarendelések tényleges kezdési és befejezési dátumaival szeretné összehasonlítani az ütemezett kezdési és befejezési dátumokat, akkor dátumszámítást is végezhet.</span><span class="sxs-lookup"><span data-stu-id="d7c51-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="d7c51-107">Költség-ellenőrzés az eszközökhöz, a munkavégzési helyszínekhez és a munkarendelésekhez</span><span class="sxs-lookup"><span data-stu-id="d7c51-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="d7c51-108">Az eszközökre, munkavégzési helyszínekre és munkarendelésekre vonatkozó számítások szinte megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="d7c51-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="d7c51-109">Az egyetlen különbség az, hogy az eszközök és munkavégzési helyszínek esetén a számításban szerepelnek aleszközök és almunkavégzési helyszínek is.</span><span class="sxs-lookup"><span data-stu-id="d7c51-109">The only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="d7c51-110">A dátum a tranzakció dátuma, amikor a regisztráció rögzítése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="d7c51-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="d7c51-111">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszközköltség ellenőrzése** vagy **Munkavégzési helyszín költségeinek ellenőrzése** elemre, vagy az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelések költségellenőrzése** elemre.</span><span class="sxs-lookup"><span data-stu-id="d7c51-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="d7c51-112">Válassza ki a kiszámítani kívánt időtartományt itt: **Eszköz költségkontrollja** / **Munkavégzési helyszín költségellenőrzése** / **Munkarendelés költségének ellenőrzése**.</span><span class="sxs-lookup"><span data-stu-id="d7c51-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a time range to be calculated.</span></span>

3. <span data-ttu-id="d7c51-113">Szükség szerint válasszon egy pénzügyi dimenziókészlet elemet, amit szerepeltetni szeretne a számításban.</span><span class="sxs-lookup"><span data-stu-id="d7c51-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="d7c51-114">Ha a nulla költséget tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="d7c51-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="d7c51-115">A **Szint** mezőben megadhatja, hogy a költségellenőrzési sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket.</span><span class="sxs-lookup"><span data-stu-id="d7c51-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="d7c51-116">Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínek hierarchiájához, akkor a munkavégzési helyszínekhez tartozó költségellenőrzési sorok a legfelső szinten jelennek meg, így a sorban szereplő órák hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből.</span><span class="sxs-lookup"><span data-stu-id="d7c51-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="d7c51-117">Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely az költségellenőrzés minden sorát megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="d7c51-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="d7c51-118">Ha a számításban szerepeltetni szeretné ezt az oszlopot, válassza az „Igen” beállítást a **Nyitott vállalt költség megjelenítése** gombbal.</span><span class="sxs-lookup"><span data-stu-id="d7c51-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="d7c51-119">Ha az aleszközökhöz tartozó költségeket külön sorként szeretné megjeleníteni, állítsa az **Aleszközök szerepeltetése** beállítást „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="d7c51-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="d7c51-120">Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket/munkavégzési helyszíneket/munkarendeléseket a **Szerepeltetni kívánt rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="d7c51-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="d7c51-121">Kattintson az **OK** gombra az számítás indításához.</span><span class="sxs-lookup"><span data-stu-id="d7c51-121">Click **OK** to start the calculation.</span></span>

    <span data-ttu-id="d7c51-122">Az alábbi ábrán az **Eszközköltség ellenőrzése** párbeszédpanel egyik példája látható.</span><span class="sxs-lookup"><span data-stu-id="d7c51-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

    ![Eszköz költségének ellenőrzése párbeszédpanel](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="d7c51-124">Az **Eszközköltségek ellenőrzése** lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d7c51-124">On the **Asset cost control** page, click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="d7c51-125">A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="d7c51-125">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="d7c51-126">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="d7c51-126">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="d7c51-127">Példa</span><span class="sxs-lookup"><span data-stu-id="d7c51-127">Example</span></span>

<span data-ttu-id="d7c51-128">Az alábbi képernyőfotón az **Eszközköltség kontrollja** számítási eredmény egyik példája látható.</span><span class="sxs-lookup"><span data-stu-id="d7c51-128">The screenshot below shows an example of calculation results in **Asset cost control**.</span></span>

- <span data-ttu-id="d7c51-129">Az **Eredeti költségvetés** mezőben a munkarendelési előrejelzésből származó költségvetési költségek láthatók.</span><span class="sxs-lookup"><span data-stu-id="d7c51-129">The **Original budget** field shows budget costs from the work order forecast.</span></span> 
- <span data-ttu-id="d7c51-130">A **Vállalt költség** mező a jogi személy által vállalt fizetendő összes költséget mutatja.</span><span class="sxs-lookup"><span data-stu-id="d7c51-130">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> 
- <span data-ttu-id="d7c51-131">A **Nyitott vállalt költség** mező a megrendelt vagy bevételezett, de még ki nem fizetett cikkek, órák vagy szolgáltatások kifizetésére vonatkozó kötelezettségeket mutatja.</span><span class="sxs-lookup"><span data-stu-id="d7c51-131">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> 
- <span data-ttu-id="d7c51-132">Miután minden felhasználási regisztráció fel van adva, a kapcsolódó költségek a **Tényleges költség** mezőben szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="d7c51-132">The **Actual cost** field shows related costs after all consumption registrations have been posted.</span></span>

![Példa számítási eredmények az Eszköz költségének ellenőrzéséhez](media/02-controlling-and-reporting.png)

<span data-ttu-id="d7c51-134">A költség számításának másik módja az, ha többszörös kiválasztással kiválasztja az eszközöket az **Összes eszköz** vagy **Aktív eszközök** pontban.</span><span class="sxs-lookup"><span data-stu-id="d7c51-134">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="d7c51-135">Ezután kattintson a **Költségellenőrzés** gombra az **Általános** lapon. Az **Eszközköltség ellenőrzése** párbeszédpanelen a program automatikusan beilleszti a kiválasztott eszközöket az **Eszköz** mezőbe a **Belefoglalandó rekordok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="d7c51-135">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="d7c51-136">Kattintson az **OK** gombra, és megjelenik a kiválasztott eszközökre vonatkozó költségszámítás.</span><span class="sxs-lookup"><span data-stu-id="d7c51-136">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="d7c51-137">Ugyanez az eljárás hajtható végre az **Összes munkavégzési helyszín** vagy **Aktív munkavégzési helyszínek** pontban található munkavégzési helyszíneknél, valamint a munkarendeléseknél az **Összes munkarendelés** vagy **Aktív munkarendelések** pontban.</span><span class="sxs-lookup"><span data-stu-id="d7c51-137">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>


## <a name="work-order-date-control"></a><span data-ttu-id="d7c51-138">Munkarendelési dátum ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="d7c51-138">Work order date control</span></span>

<span data-ttu-id="d7c51-139">Ezen a lapon áttekintést kaphat a munkarendelések várható kezdő és befejező dátumairól, a tényleges kezdési és befejezési dátumokhoz képest.</span><span class="sxs-lookup"><span data-stu-id="d7c51-139">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="d7c51-140">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelés dátumkontrollja** elemre.</span><span class="sxs-lookup"><span data-stu-id="d7c51-140">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="d7c51-141">Kattintson a **Számítás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d7c51-141">Click **Calculate**.</span></span>

3. <span data-ttu-id="d7c51-142">A **Munkavégzési helyszín** mezőben válassza ki a munkavégzési helyszínt.</span><span class="sxs-lookup"><span data-stu-id="d7c51-142">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="d7c51-143">A **Kezdő dátum** és **Záró dátum** mezőben válassza ki azt az tartományt, amelyhez el szeretné végezni a számítást.</span><span class="sxs-lookup"><span data-stu-id="d7c51-143">Insert the range for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="d7c51-144">Minden olyan munkarendelést tartalmaz, amely várhatóan az adott tartományon belül kezdődik.</span><span class="sxs-lookup"><span data-stu-id="d7c51-144">All work orders with expected start date within the range will be included.</span></span>

5. <span data-ttu-id="d7c51-145">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d7c51-145">Click **OK**.</span></span>

6. <span data-ttu-id="d7c51-146">Kattintson a **Csoportosítási szempont...** gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d7c51-146">Click the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="d7c51-147">A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve.</span><span class="sxs-lookup"><span data-stu-id="d7c51-147">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="d7c51-148">A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.</span><span class="sxs-lookup"><span data-stu-id="d7c51-148">Click on a button to activate or deactivate it.</span></span>

## <a name="example"></a><span data-ttu-id="d7c51-149">Példa</span><span class="sxs-lookup"><span data-stu-id="d7c51-149">Example</span></span>

<span data-ttu-id="d7c51-150">Az alábbi képernyőfotón a **Munkarendelés dátumkontrollja** számítási eredmény egyik példája látható.</span><span class="sxs-lookup"><span data-stu-id="d7c51-150">The screenshot below shows an example of calculation results in **Work order date control**.</span></span>

- <span data-ttu-id="d7c51-151">Az **Átlagos kezdő késleltetés** mező a munkarendelés tervezett kezdési dátuma és a tényleges kezdési dátum közötti különbséget jeleníti meg napokban.</span><span class="sxs-lookup"><span data-stu-id="d7c51-151">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="d7c51-152">Ha például a tényleges kezdési dátum két nappal az ütemezett kezdési dátum előtt volt, akkor ebben a mezőben a „-2” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d7c51-152">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="d7c51-153">Az **Átlagos záró késleltetés** mező a munkarendelés tervezett záró dátuma és a tényleges záró dátum közötti különbséget jeleníti meg napokban.</span><span class="sxs-lookup"><span data-stu-id="d7c51-153">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="d7c51-154">Ha például a tényleges záró dátum három nappal az ütemezett kezdési dátum után volt, akkor ebben a mezőben a „3” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d7c51-154">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="d7c51-155">Az **Előfordulások** mező mutatja, hogy hányszor fordulnak elő eltérések az ütemezett és a tényleges kezdési dátumra nézve, valamint az ütemezett és a tényleges befejezési dátumra nézve a munkarendelésen.</span><span class="sxs-lookup"><span data-stu-id="d7c51-155">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

![Példa számítási eredmények a Munkarendelés dátumának ellenőrzéséhez](media/03-controlling-and-reporting.png)



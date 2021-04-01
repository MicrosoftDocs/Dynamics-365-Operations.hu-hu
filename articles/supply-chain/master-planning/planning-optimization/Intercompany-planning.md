---
title: Vállalatközi tervezés
description: Ez a témakör bemutatja a vállalatközi tervezést, és bemutatja, hogyan kell konfigurálni a vállalatközi tervezést a Microsoft Dynamics 365 Supply Chain Management Tervezési optimalizálás megoldásával.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd498489e18eaba81720757faa14c0bf7b7d67f1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263398"
---
# <a name="intercompany-planning"></a><span data-ttu-id="f8ae2-103">Vállalatközi tervezés</span><span class="sxs-lookup"><span data-stu-id="f8ae2-103">Intercompany planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f8ae2-104">Néhány szervezetnél a logisztikai műveletek a szervezet többi jogi személyétől (vállalatától) függenek.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-104">For some organizations, logistics operations depend on other legal entities (companies) in the organization.</span></span> <span data-ttu-id="f8ae2-105">Ezeket a műveleteket vállalatközi értékesítések és beszerzések használatával kezeli a program, mert mindegyik jogi személyhez külön számlatükör tartozik.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-105">These operations are handled by using intercompany sales and purchases, because each legal entity has a separate chart of accounts.</span></span>

<span data-ttu-id="f8ae2-106">Ez a témakör bemutatja a vállalatközi tervezést, és bemutatja, hogyan kell konfigurálni a vállalatközi tervezést a Microsoft Dynamics 365 Supply Chain Management Tervezési optimalizálás megoldásával.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-106">This topic describes intercompany planning and explains how to configure intercompany planning with Planning Optimization in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="f8ae2-107">Ez a témakör a következő fontos vállalatközi kifejezéseket használja:</span><span class="sxs-lookup"><span data-stu-id="f8ae2-107">This topic uses the following important intercompany terms:</span></span>

- <span data-ttu-id="f8ae2-108">**Felfelé irányuló** – Relatív hivatkozás egy vállalatban vagy egy ellátási láncban.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-108">**Upstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="f8ae2-109">Az alapanyag beszállítója irányába mutató mozgást jelez.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-109">It indicates movement in the direction of the raw material supplier.</span></span>
- <span data-ttu-id="f8ae2-110">**Lefelé irányuló** – Relatív hivatkozás egy vállalatban vagy egy ellátási láncban.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-110">**Downstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="f8ae2-111">A vevő irányába mutató mozgást jelez.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-111">It indicates movement in the direction of the customer.</span></span>
- <span data-ttu-id="f8ae2-112">**Tervezett vállalatközi igény** – A termék tervezett igénye egy vállalaton belül a termék egy alsóbb vállalattól fennálló tervezett igénye alapján.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-112">**Planned intercompany demand** – Planned demand for a product in a company, based on planned demand for the product from a downstream company.</span></span>

<span data-ttu-id="f8ae2-113">Az alaptervezésben az egyik vállalatnál a terv tartalmazhatja azt a tervezett vállalatközi igényt, amely egy másik vállalat tervének tervezett rendeléseihez kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-113">In master planning, a plan in one company can include planned intercompany demand that is related to planned orders from a plan in another company.</span></span> <span data-ttu-id="f8ae2-114">Ez a funkció hasznos, mivel teljes láthatóságot ad a tervezett rendelésekről a vállalatok között.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-114">This capability is useful, because it provides full visibility into planned orders across companies.</span></span> <span data-ttu-id="f8ae2-115">Biztosítja azt is, hogy minden szükséges tervezett beszerzési rendelés létrejöjjön, de a vállalatközi igényhez tartozó tervezett rendelések megerősítésének megkövetelése nélkül.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-115">It also ensures that all required planned supply orders are created, but without requiring that planned orders be firmed for the intercompany demand.</span></span>

<span data-ttu-id="f8ae2-116">Ha egy alaptervből futtatja az alaptervezést, amely tartalmazza a tervezett lefelé irányuló igényt, akkor a kapcsolódó vállalatközi szállítóktól származó tervezett beszerzési rendelések igényként szerepelnek a tervben.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-116">If you run master planning from a master plan that includes planned downstream demand, planned purchase orders from the related intercompany vendors will be included in the plan as demand.</span></span>

## <a name="required-setup"></a><span data-ttu-id="f8ae2-117">Szükséges beállítás</span><span class="sxs-lookup"><span data-stu-id="f8ae2-117">Required setup</span></span>

<span data-ttu-id="f8ae2-118">A vállalatközi tervezés használatához a következő módon kell felkészíteni a rendszert:</span><span class="sxs-lookup"><span data-stu-id="f8ae2-118">To use intercompany planning, you must prepare your system in the following way:</span></span>

1. <span data-ttu-id="f8ae2-119">A releváns termékeket minden érintett vállalatnál ki kell adni.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-119">The relevant products must be released in all the relevant companies.</span></span> <span data-ttu-id="f8ae2-120">További tudnivalókért lásd: [Vállalatközi kereskedelem konfigurálása és használata itt: Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) a Microsoft Learn rendszerében.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-120">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="f8ae2-121">A lefelé irányuló igényt a felsőbb vállalattal vállalatközi kapcsolattal rendelkező szállítótól érkező beszerzéseknek és a vevő megfelelő alapértelmezett készletdimenzióinak (hely és raktár) kell fedezniük.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-121">Downstream demand must be covered by purchases from a vendor that has an intercompany relation to the upstream company and relevant default inventory dimensions (site and warehouse) on the customer.</span></span> <span data-ttu-id="f8ae2-122">További tudnivalókért lásd: [Vállalatközi kereskedelem konfigurálása és használata itt: Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) a Microsoft Learn rendszerében.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-122">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="f8ae2-123">A felsőbb szintű vállalat alaptervének tartalmaznia kell a tervezett lefelé irányuló igényt, és meg kell adni az érintett vállalatot és alaptervet a lefelé irányuló tervekben.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-123">The master plan in the upstream company must include planned downstream demand, and the relevant company and master plan must be specified in the downstream plans.</span></span>

## <a name="include-planned-downstream-demand"></a><span data-ttu-id="f8ae2-124">Tervezett alsóbb rétegbeli igény figyelembevétele</span><span class="sxs-lookup"><span data-stu-id="f8ae2-124">Include planned downstream demand</span></span>

<span data-ttu-id="f8ae2-125">Ha egy alaptervet úgy kíván konfigurálni, hogy az tartalmazza a tervezett lefelé irányuló igényt, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-125">Follow these steps to configure your master plan so that it includes planned downstream demand.</span></span>

1. <span data-ttu-id="f8ae2-126">Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-126">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="f8ae2-127">Válasszon ki vagy hozzon létre egy alaptervet.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-127">Select or create a master plan.</span></span>
1. <span data-ttu-id="f8ae2-128">Az **Vállalatközi tervezés** gyorslapon állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="f8ae2-128">On the **Intercompany planning** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="f8ae2-129">**Tervezett lefelé irányuló igény belefoglalása** – Ezt a beállítást *Igen* értékre állítva engedélyezheti az alaptervhez tartozó vállalatközi tervezést.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-129">**Include planned downstream demand** – Set this option to *Yes* to enable intercompany planning for the master plan.</span></span>
    - <span data-ttu-id="f8ae2-130">**Lefelé irányuló tervek** – Ha a **Tervezett lefelé irányuló igény belefoglalása** beállítást *Igen* értékűre állítja, akkor az eszköztár és a rács segítségével adja hozzá a többi vállalattól a kívánt alapterveket.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-130">**Downstream plans** – If you set the **Include planned downstream demand** option to *Yes*, use the toolbar and grid to add the desired master plans from other companies.</span></span>

## <a name="peg-across-companies-by-using-multilevel-pegging"></a><span data-ttu-id="f8ae2-131">Kövesse az igényeket a vállalatok között többszintű igénykövetéssel</span><span class="sxs-lookup"><span data-stu-id="f8ae2-131">Peg across companies by using multilevel pegging</span></span>

<span data-ttu-id="f8ae2-132">A többszintű igénykövetésben megtekintheti a vállalatok közötti igénykövetést, hogy megtekintse az ellátással fedezett igény kezdeti forrását.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-132">In multilevel pegging, you can view pegging across companies to see the initial source of demand that is being covered by a supply.</span></span>

<span data-ttu-id="f8ae2-133">A többszintű igénykövetési adatok megtekintéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-133">To view multilevel pegging information, follow these steps.</span></span>

1. <span data-ttu-id="f8ae2-134">Ugorjon az **Alaptervezés \> Alaptervezés \> Tervezett rendelések** pontra.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-134">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="f8ae2-135">Válasszon ki vagy nyisson meg egy tervezett rendelést.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-135">Select or open a planned order.</span></span>
1. <span data-ttu-id="f8ae2-136">A Művelet ablaktábla **Nézet** lapjának **Követelmények** csoportjában válassza a **Többszintű igénykövetés** elemet.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-136">On the Action Pane, on the **View** tab, in the **Requirements** group, select **Multilevel pegging**.</span></span>

### <a name="intercompany-example-that-involves-two-companies"></a><span data-ttu-id="f8ae2-137">Vállalatközi példa, amely két vállalatot érint</span><span class="sxs-lookup"><span data-stu-id="f8ae2-137">Intercompany example that involves two companies</span></span>

<span data-ttu-id="f8ae2-138">Ehhez a példához egy tervezett termelési rendelés jön létre a USMF vállalatban, amely fedezi az értékesítési rendelést a DEMF vállalatban.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-138">For this example, a planned production order is created in the USMF company to cover a sales order in the DEMF company.</span></span> <span data-ttu-id="f8ae2-139">A USMF vállalatban a közvetlen igény a tervezett vállalatközi igény.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-139">In USMF, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="f8ae2-140">Ha azt szeretné, hogy ez az igény megjelenjen a USMF-ben, akkor az alaptervezést először a DEMF, majd a USMF esetében kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-140">To make this demand appear in USMF, master planning is run first in DEMF and then in USMF.</span></span>

<span data-ttu-id="f8ae2-141">A következő ábra azt mutatja be, hogyan jelenhet meg ez a példa a tervezett termelési rendelés **Többszintű igénykövetés** oldalán.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-141">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Vállalatközi példa, amely két vállalatot érint](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a><span data-ttu-id="f8ae2-143">Vállalatközi példa, amely három vállalatot érint</span><span class="sxs-lookup"><span data-stu-id="f8ae2-143">Intercompany example that involves three companies</span></span>

<span data-ttu-id="f8ae2-144">Ehhez a példához egy tervezett beszerzési rendelés jön létre a USMF vállalatban, amely fedezi az értékesítési rendelést a FRRT vállalatban.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-144">For this example, a planned purchase order is created in the USMF company to cover a sales order in the FRRT company.</span></span> <span data-ttu-id="f8ae2-145">A DEMF és USMF vállalatban a közvetlen igény a tervezett vállalatközi igény.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-145">In the DEMF and USMF companies, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="f8ae2-146">Ha azt szeretné, hogy ez az igény megjelenjen a USMF-ben, akkor az alaptervezést először az FRRT, majd a DEMF, végül a USMF esetében kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-146">To make this demand appear in USMF, master planning is run first in FRRT, then in DEMF, and finally in USMF.</span></span>

<span data-ttu-id="f8ae2-147">A következő ábra azt mutatja be, hogyan jelenhet meg ez a példa a tervezett termelési rendelés **Többszintű igénykövetés** oldalán.</span><span class="sxs-lookup"><span data-stu-id="f8ae2-147">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Vállalatközi példa, amely három vállalatot érint](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
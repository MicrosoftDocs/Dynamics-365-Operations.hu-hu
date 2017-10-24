--- 
title: "Értékesítési ajánlatok létrehozása és szerkesztése"
description: "Ez az eljárás bemutatja, hogyan hozhat létre és frissíthet értékesítési árajánlatokat."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f56b495131836689395a2124d5a834579e1646b7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-edit-sales-quotations"></a><span data-ttu-id="813a6-103">Értékesítési ajánlatok létrehozása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="813a6-103">Create and edit sales quotations</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="813a6-104">Ez az eljárás bemutatja, hogyan hozhat létre és frissíthet értékesítési árajánlatokat.</span><span class="sxs-lookup"><span data-stu-id="813a6-104">This procedure demonstrates how to create and update a sales quotation.</span></span> <span data-ttu-id="813a6-105">Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="813a6-105">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-sales-quotation"></a><span data-ttu-id="813a6-106">Értékesítési ajánlat létrehozása</span><span class="sxs-lookup"><span data-stu-id="813a6-106">Create a sales quotation</span></span>
1. <span data-ttu-id="813a6-107">Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.</span><span class="sxs-lookup"><span data-stu-id="813a6-107">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
2. <span data-ttu-id="813a6-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="813a6-108">Click New.</span></span>
3. <span data-ttu-id="813a6-109">A Fiók típusa mezőben válassza ki a „Potenciális vevő” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="813a6-109">In the Account type field, select 'Prospect'.</span></span>
4. <span data-ttu-id="813a6-110">A Potenciális vevő mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="813a6-110">In the Prospect field, enter or select a value.</span></span>
5. <span data-ttu-id="813a6-111">Bontsa ki az Általános szakaszt.</span><span class="sxs-lookup"><span data-stu-id="813a6-111">Expand the General section.</span></span>
    * <span data-ttu-id="813a6-112">Mivel azt választotta, hogy az Értékesítés és Marketing területről hoz létre árajánlatot, a típus automatikusan Értékesítési árajánlat lesz.</span><span class="sxs-lookup"><span data-stu-id="813a6-112">Because you chose to create a quotation from the Sales and Marketing area, the type is automatically set to Sales quotation.</span></span> <span data-ttu-id="813a6-113">Ha projekthez akar árajánlatot létrehozni, akkor a Projektvezetés és könyvelés modulból kell hozzáférnie.</span><span class="sxs-lookup"><span data-stu-id="813a6-113">To create a quotation for a project you must access it from the Project management and accounting module.</span></span>   
6. <span data-ttu-id="813a6-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="813a6-114">Click OK.</span></span>
    * <span data-ttu-id="813a6-115">A mezők és a műveletek az ajánlati sorok esetében nagyon hasonlítanak az értékesítésirendelés-sorokhoz tartozókhoz.</span><span class="sxs-lookup"><span data-stu-id="813a6-115">The fields and actions on the quotation lines are very similar to the ones on the sales order lines.</span></span>   <span data-ttu-id="813a6-116">Az értékesítési rendelésekhez hasonlóan az árajánlatokat létre lehet hozni egy konkrét cikkhez, vagy ha a cikkszám nem ismert vagy nem létezik az árajánlat létrehozásásnak időpontjában, létre lehet hozni az értékesítési kategóriában.</span><span class="sxs-lookup"><span data-stu-id="813a6-116">Like sales orders, quotations can be created for a specific item or, when item number is not known or does not exist at the time of quotation creation, quotations can be created for a sales category.</span></span>  
7. <span data-ttu-id="813a6-117">A Cikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="813a6-117">In the Item field, enter or select a value.</span></span>
8. <span data-ttu-id="813a6-118">Írjon be egy értéket a Cikk mezőbe.</span><span class="sxs-lookup"><span data-stu-id="813a6-118">In the Item field, type a value.</span></span>
9. <span data-ttu-id="813a6-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="813a6-119">Close the page.</span></span>
10. <span data-ttu-id="813a6-120">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="813a6-120">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="813a6-121">Ha a sorban a kiválasztott elemhez tartoznak érvényes kereskedelmi megállapodások, akkor az alkalmazandó ár és engedmények automatikusan átmásolódnak az árajánlati sorba.</span><span class="sxs-lookup"><span data-stu-id="813a6-121">If there are valid trade agreements for the item selected on the line, the applicable price and discounts will be automatically copied to the quotation line.</span></span> <span data-ttu-id="813a6-122">Győződjön meg arról, hogy az Egységár mező tartalmaz értéket, és megadhat engedmény értékeket is, ha szeretne</span><span class="sxs-lookup"><span data-stu-id="813a6-122">Make sure that the Unit price field contains a value and you can also enter discount values if you want to.</span></span>  
11. <span data-ttu-id="813a6-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="813a6-123">Click Save.</span></span>
12. <span data-ttu-id="813a6-124">A Művelet panelen kattintson az Értékesítési ajánlat elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-124">On the Action Pane, click Sales quotation.</span></span>
13. <span data-ttu-id="813a6-125">Kattintson az Összegek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="813a6-125">Click Totals.</span></span>
14. <span data-ttu-id="813a6-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="813a6-126">Click OK.</span></span>
15. <span data-ttu-id="813a6-127">Kattintson az Értékesítésiajánlat-sor lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="813a6-127">Click Sales quotation line.</span></span>
16. <span data-ttu-id="813a6-128">Kattintson az Árak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="813a6-128">Click Prices.</span></span>
    * <span data-ttu-id="813a6-129">Az Árszimuláció futtatása lapon kísérletezhet az érajánlat várt bevételének vagy jövedelmezőségének beállításával a kívánt egységár, kedvezményösszeg, kedvezményszázalék, teljes összeg, árrés vagy hozzájárulási arány alapján.</span><span class="sxs-lookup"><span data-stu-id="813a6-129">In the Run price simulation page you can experiment with adjusting the expected revenue or profitability of your quotation based on the desired unit price, discount amount, discount percentage, total amount, margin, or contribution ratio.</span></span>   <span data-ttu-id="813a6-130">Ha elégedett a cél számokkal, alkalmazza a javaslatot az ajánlati sorra, és az árral kapcsolatos mezői ennek megfelelően frissülni fognak..</span><span class="sxs-lookup"><span data-stu-id="813a6-130">When you are satisfied with the target figures, you apply the suggestion to the quotation line, and its price-related fields will be updated accordingly.</span></span>  
    * <span data-ttu-id="813a6-131">Annyi árszimulációt végezhet amennyit akar.</span><span class="sxs-lookup"><span data-stu-id="813a6-131">Y ou can create as many price simulations as you wish.</span></span> <span data-ttu-id="813a6-132">Ha az Új gombra kattint az aktuálisár ajánlati sorból az árfeltételek átmásolódnak a lapra.</span><span class="sxs-lookup"><span data-stu-id="813a6-132">When you click New, the price conditions from the current quotation line are copied to the page.</span></span> <span data-ttu-id="813a6-133">Ezután módosíthatja, a célok árral kapcsolatos mezőinek értékeit.</span><span class="sxs-lookup"><span data-stu-id="813a6-133">You can then modify values in any of the price-related fields to the target ones.</span></span> <span data-ttu-id="813a6-134">A mezők valamelyikén végzett változása elindítja az összes mező újraszámítását.</span><span class="sxs-lookup"><span data-stu-id="813a6-134">A change in one of the fields will trigger recalculation in all the other fields.</span></span> <span data-ttu-id="813a6-135">Ahhoz, hogy a rendszer kiszámolja az értékesítési árrést és hozzájárulási arányt a termék egységköltségét ismerni kell.</span><span class="sxs-lookup"><span data-stu-id="813a6-135">In order for the system to calculate the sales margin and contribution ratio, the product's unit cost has to be known.</span></span> <span data-ttu-id="813a6-136">A Szimulált árak lapon részletesen megtekinthetők az eredeti árak, a javasolt módosítások és hatásaik az árajánlati összegekre.</span><span class="sxs-lookup"><span data-stu-id="813a6-136">Use the Simulated prices tab for a detailed view of the original prices, proposed changes and their effect on the quotation totals.</span></span>   <span data-ttu-id="813a6-137">Általános szabályként elmondható, hogy amikor egy új összeget beállító szimulációt alkalmaznak az árajánlati sorra, a rendszer újraszámolja, és egy új értéket ír be az Egységár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="813a6-137">As a general rule, when a simulation that sets a new amount is applied to the quotation line, the system recalculates and enters a new value in the Unit price field.</span></span> <span data-ttu-id="813a6-138">Ha szimuláció alapja egy új árrés vagy egy új hozzájárulási arány, csak a Nettó összeg mező frissül, és az Egységár üres marad.</span><span class="sxs-lookup"><span data-stu-id="813a6-138">If the simulation is based on a new margin or a new contribution ratio, only the Net amount field is updated, and the Unit price is blank.</span></span> <span data-ttu-id="813a6-139">Mindkét esetben törlődnek az engedmények, amelyek az árajánlati soron voltak a szimuláció előtt.</span><span class="sxs-lookup"><span data-stu-id="813a6-139">In both cases, any discounts that were on the quotation line before simulation will be deleted.</span></span>  
17. <span data-ttu-id="813a6-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="813a6-140">Close the page.</span></span>
18. <span data-ttu-id="813a6-141">A Művelet panelen kattintson az Árajánlat elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-141">On the Action Pane, click Quotation.</span></span>
19. <span data-ttu-id="813a6-142">Kattintson az Árajánlat küldése elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-142">Click Send quotation.</span></span>
20. <span data-ttu-id="813a6-143">Válassza az Igen lehetőséget az Árajánlat nyomtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="813a6-143">Select Yes in the Print quotation field.</span></span>
21. <span data-ttu-id="813a6-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="813a6-144">Click OK.</span></span>
    * <span data-ttu-id="813a6-145">A jelentés létrehozása egy percig is eltarthat.</span><span class="sxs-lookup"><span data-stu-id="813a6-145">The report may take a minute to generate.</span></span> <span data-ttu-id="813a6-146">Amíg ez meg nem történik ne zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="813a6-146">Don’t close the page until it does so.</span></span>  
22. <span data-ttu-id="813a6-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="813a6-147">Close the page.</span></span>

## <a name="update-a-sales-quotation"></a><span data-ttu-id="813a6-148">Értékesítési ajánlat frissítése</span><span class="sxs-lookup"><span data-stu-id="813a6-148">Update a sales quotation</span></span>
1. <span data-ttu-id="813a6-149">A műveleti panelen kattintson a Követés elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-149">On the Action Pane, click Follow up.</span></span>
2. <span data-ttu-id="813a6-150">Kattintson a Konvertálás vevővé elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-150">Click Convert to customer.</span></span>
3. <span data-ttu-id="813a6-151">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="813a6-151">In the Customer account field, type a value.</span></span>
4. <span data-ttu-id="813a6-152">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="813a6-152">Click Check.</span></span>
    * <span data-ttu-id="813a6-153">Ellenőrizze, hogy megjelenik-e egy üzenet, amely szerint a megadott számlaszám szabadon használható.</span><span class="sxs-lookup"><span data-stu-id="813a6-153">Make sure you see a message that the account number you typed in is free to use.</span></span>  
5. <span data-ttu-id="813a6-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="813a6-154">Click OK.</span></span>
    * <span data-ttu-id="813a6-155">A rendszer most létrehozott egy új vevőszámlát, a potenciális vevőhöz az árajánlaton.</span><span class="sxs-lookup"><span data-stu-id="813a6-155">The system has now created a new customer account for the prospect on the quotation.</span></span>  
6. <span data-ttu-id="813a6-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="813a6-156">Close the page.</span></span>
7. <span data-ttu-id="813a6-157">A műveleti panelen kattintson a Követés elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-157">On the Action Pane, click Follow up.</span></span>
8. <span data-ttu-id="813a6-158">Kattintson a Megerősítés gombra.</span><span class="sxs-lookup"><span data-stu-id="813a6-158">Click Confirm.</span></span>
9. <span data-ttu-id="813a6-159">A Ok mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="813a6-159">In the Reason field, enter or select a value.</span></span>
10. <span data-ttu-id="813a6-160">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="813a6-160">Click OK.</span></span>
11. <span data-ttu-id="813a6-161">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-161">On the Action Pane, click General.</span></span>
12. <span data-ttu-id="813a6-162">Kattintson az Értékesítési rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="813a6-162">Click Sales orders.</span></span>
13. <span data-ttu-id="813a6-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="813a6-163">Close the page.</span></span>


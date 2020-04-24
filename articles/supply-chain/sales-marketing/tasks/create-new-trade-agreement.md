---
title: Új kereskedelmi szerződés létrehozása
description: Ez az eljárás bemutatja, hogyan hozhat létre egy kereskedelmi megállapodást, amelyben regisztrálhat egy új termékeladási árat, amelyben egy adott vevővel megállapodott.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9aa46f959c35c209791457aa697ab829264b3275
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211951"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="4ba55-103">Új kereskedelmi szerződés létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ba55-103">Create a new trade agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4ba55-104">Ez az eljárás bemutatja, hogyan hozhat létre egy kereskedelmi megállapodást, amelyben regisztrálhat egy új termékeladási árat, amelyben egy adott vevővel megállapodott.</span><span class="sxs-lookup"><span data-stu-id="4ba55-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="4ba55-105">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="4ba55-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="4ba55-106">Saját adatok használatakor az útmutató használatának megkezdése előtt győződjön meg róla, hogy a Kereskedelmi megállapodások napló neve létezik, ahol az Alapértelmezett viszony az "Ár (eladási)".</span><span class="sxs-lookup"><span data-stu-id="4ba55-106">If you're using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to "Price (sales)".</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="4ba55-107">Hozzon létre és tegyen közzé egy új kereskedelmi megállapodási naplót</span><span class="sxs-lookup"><span data-stu-id="4ba55-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="4ba55-108">Ugorjon a **Navigációs lap > Modulok >Értékesítés és marketing > Árak és engedmények > Kereskedelmi megállapodási naplók** elemre.</span><span class="sxs-lookup"><span data-stu-id="4ba55-108">Go to **Navigation pane > Modules > Sales and marketing > Prices and discounts > Trade agreement journals**.</span></span>
2. <span data-ttu-id="4ba55-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4ba55-109">Click **New**.</span></span>
3. <span data-ttu-id="4ba55-110">A **Név** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4ba55-110">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4ba55-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4ba55-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="4ba55-112">A **Művelet panelen** kattintson a **Sorok** elemre.</span><span class="sxs-lookup"><span data-stu-id="4ba55-112">On **Action pane**, click **Lines**.</span></span>
6. <span data-ttu-id="4ba55-113">A **Fiókkód** mezőben válassza ki a „Tábla” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ba55-113">In the **Account code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="4ba55-114">Ebben a példában egy konkrét vevő árát frissíti, ami azt jelenti, hogy meg kell adnia egy Táblát.</span><span class="sxs-lookup"><span data-stu-id="4ba55-114">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="4ba55-115">Ha a termék listaárát frissítené, az „Összeset” kellene kiválasztania, úgy, hogy az új ár legyen érvényes az összes vevőre.</span><span class="sxs-lookup"><span data-stu-id="4ba55-115">If you were updating the product's list price, you would select 'All', so that the new price is valid for all customers.</span></span> <span data-ttu-id="4ba55-116">Ha különböző árakat különböztet meg az egyes vevői szegmensek között, akkor válassza a Csoportot.</span><span class="sxs-lookup"><span data-stu-id="4ba55-116">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="4ba55-117">A Csoport kiválasztásához be kell állítania a Vevői árcsoportokat.</span><span class="sxs-lookup"><span data-stu-id="4ba55-117">To select Group, you must have set up Customer price groups.</span></span>  

7. <span data-ttu-id="4ba55-118">A **Fiókválasztás** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4ba55-118">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="4ba55-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4ba55-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="4ba55-120">A **Cikk-kód** mezőben válassza ki a „Tábla” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ba55-120">In the **Item code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="4ba55-121">Ha "Ár (eladási)" típusú kereskedelmi megállapodást ír be, akkor csak a "Tábla" elemet válassza ki a **Cikk-kód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ba55-121">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the **Item code** field.</span></span> <span data-ttu-id="4ba55-122">Ennek oka az, hogy az ár abszolút érték, és nem lehet azonos egy termékcsoport összes termékére.</span><span class="sxs-lookup"><span data-stu-id="4ba55-122">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>
    
10. <span data-ttu-id="4ba55-123">A **Cikk-viszony** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4ba55-123">In the **Item relation** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="4ba55-124">A listában válassza ki a szerződésben szerepeltetni kívánt terméket.</span><span class="sxs-lookup"><span data-stu-id="4ba55-124">In the list, select the product you want to include in the agreement.</span></span> <span data-ttu-id="4ba55-125">Jegyezze meg, hogy mely termék van kijelölve.</span><span class="sxs-lookup"><span data-stu-id="4ba55-125">Make a note of which product you've selected.</span></span>  
12. <span data-ttu-id="4ba55-126">Adja meg a minimum mennyiséget a **Kezdőérték** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ba55-126">In the **From** field, enter a minimum quantity.</span></span>
    - <span data-ttu-id="4ba55-127">Ha a vevőnek egy minimális mennyiséget kell rendelnie, mielőtt új ár igényelhetne, akkor meg kell adnia a mennyiséget itt.</span><span class="sxs-lookup"><span data-stu-id="4ba55-127">If the customer has to order a minimum quantity before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    - <span data-ttu-id="4ba55-128">Adjon meg egy értéket a **Címzett** mezőben, hogy megadja a maximális mennyiséget, amely felett a megállapodási ár nem lesz érvényes.</span><span class="sxs-lookup"><span data-stu-id="4ba55-128">Enter a value in the **To** field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="4ba55-129">Ha több mennyiségi szünet alapján ajánl árakat és engedményeket, adja meg az egyes mennyiségi határértékeket egy minimális és maximális mennyiségként a **Kezdő** és a **Befejező** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="4ba55-129">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the **From** and **To** fields respectively.</span></span>
13. <span data-ttu-id="4ba55-130">Az **Összeg devizában mezőben** adjon meg egy árat.</span><span class="sxs-lookup"><span data-stu-id="4ba55-130">In the **Amount in currency field**, enter a price.</span></span>
14. <span data-ttu-id="4ba55-131">A **Részletek** szakaszban, a **Kezdő dátum** mezőben adjon meg egy dátumot, amelytől kezdve érvényes lesz a szerződés.</span><span class="sxs-lookup"><span data-stu-id="4ba55-131">Under the **Details** section, in the **From date** field, enter a date from which this agreement will be valid.</span></span>
15. <span data-ttu-id="4ba55-132">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ba55-132">Click **Save**.</span></span>
16. <span data-ttu-id="4ba55-133">Kattintson az **Érvényesítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ba55-133">Click **Validate**.</span></span>
17. <span data-ttu-id="4ba55-134">Kattintson a **Kijelölt sorok érvényesítése** pontra.</span><span class="sxs-lookup"><span data-stu-id="4ba55-134">Click **Validate selected lines**.</span></span>
18. <span data-ttu-id="4ba55-135">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ba55-135">Click **OK**.</span></span>
19. <span data-ttu-id="4ba55-136">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ba55-136">Click **Post**.</span></span>
20. <span data-ttu-id="4ba55-137">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ba55-137">Click **OK**.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="4ba55-138">Termékkel kapcsolatos kereskedelmi megállapodások megtekintése</span><span class="sxs-lookup"><span data-stu-id="4ba55-138">View trade agreements for a product</span></span>
1. <span data-ttu-id="4ba55-139">Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek**.</span><span class="sxs-lookup"><span data-stu-id="4ba55-139">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="4ba55-140">A listában keresse meg és válassza ki a terméket, amelynek éppen frissítette az árát.</span><span class="sxs-lookup"><span data-stu-id="4ba55-140">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="4ba55-141">A **Művelet panelen** kattintson az **Értékesítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="4ba55-141">On the **Action Pane**, click **Sell**.</span></span>
4. <span data-ttu-id="4ba55-142">Kattintson a **Kereskedelmi megállapodások megtekintése** pontra.</span><span class="sxs-lookup"><span data-stu-id="4ba55-142">Click **View trade agreements**.</span></span>
    
    <span data-ttu-id="4ba55-143">Tekintse át az imént létrehozott ármegállapodás részletes adatait.</span><span class="sxs-lookup"><span data-stu-id="4ba55-143">Review the details of the price trade agreement you have just created.</span></span>    

5. <span data-ttu-id="4ba55-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4ba55-144">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ba55-145">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4ba55-145">Additional resources</span></span>
### <a name="community-blogs"></a><span data-ttu-id="4ba55-146">Közösségi blogok</span><span class="sxs-lookup"><span data-stu-id="4ba55-146">Community blogs</span></span>
- [<span data-ttu-id="4ba55-147">Értékesítési árak a Dynamics 365 for Finance and Operations szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="4ba55-147">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)

--- 
title: "Felhasználási igénylés létrehozása"
description: "Ez az eljárás bemutatja az igénylések létrehozásának a folyamatát."
author: mkirknel
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: bad86a4726ce69015f318d9af98992b36d34b29a
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-requisition-for-consumption"></a><span data-ttu-id="c9b5f-103">Felhasználási igénylés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9b5f-103">Create a requisition for consumption</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9b5f-104">Ez az eljárás bemutatja az igénylések létrehozásának a folyamatát.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-104">This procedure walks you through the process of creating a requisition.</span></span> <span data-ttu-id="c9b5f-105">Megmutatja, hogy milyen különböző módokon tudja keresni a termékeket a beszerzési katalógusban, illetve hogyan tud hozzáadni egy olyan terméket, amely nem szerepel a katalógusban.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-105">It shows you different ways to search for products in your procurement catalog and how to add a product that isn’t in your catalog.</span></span> <span data-ttu-id="c9b5f-106">Az eljárás megkezdése előtt rendelkeznie kell egy beszerzési irányelvvel, amelyet az igénylés alapértelmezett típusaként kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-106">Before you start this procedure, you must have a purchasing policy set up with Consumption as the default type of requisition.</span></span> <span data-ttu-id="c9b5f-107">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="c9b5f-108">Az eljárás csak olyan felhasználói profil által hajtható végre, amely dolgozóként van beállítva.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-108">The procedure can only be carried out by a user profile that is set up as worker.</span></span>  <span data-ttu-id="c9b5f-109">Ezt a feladatot általában egy alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-109">This task would normally be carried out by an employee.</span></span> <span data-ttu-id="c9b5f-110">Az alkalmazott által alkalmazott biztonsági szerepkör teszi lehetővé a feladatok elvégzését, vagy ha USMF-et használ, jelentkezzen be ezen a néven: Alíz.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-110">The Employee employ security role will allow you to carry out the tasks, or if you’re using USMF, you can log in as Alicia.</span></span>


## <a name="create-a-new-requisition"></a><span data-ttu-id="c9b5f-111">Új igénylés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9b5f-111">Create a new requisition</span></span>
1. <span data-ttu-id="c9b5f-112">Ugrás a Beszerzés és forrás > Beszerzési igénylések > Beszerzési igénylések általam létrehozva elemre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-112">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="c9b5f-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-113">Click New.</span></span>
3. <span data-ttu-id="c9b5f-114">A Név mezőbe írja be az igénylés nevét.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-114">In the Name field, give the requisition a name.</span></span>
4. <span data-ttu-id="c9b5f-115">Adja meg a dátumot az Igényelt dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-115">In the Requested date field, enter a date.</span></span>
    * <span data-ttu-id="c9b5f-116">Alapértelmezés szerint a kért dátumot és a könyvelési dátumot a rendszer a beszerzési igénylés soraiba másolja.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-116">By default, the requested date and accounting date are copied to the purchase requisition lines.</span></span> <span data-ttu-id="c9b5f-117">A dátumok megváltoztathatók a sorok szintjén.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-117">They can be changed at the line level.</span></span> <span data-ttu-id="c9b5f-118">A kért dátum a kért szállítási dátum.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-118">The requested date is the requested delivery date.</span></span>  
5. <span data-ttu-id="c9b5f-119">Adja meg a dátumot a Könyvelés dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-119">In the Accounting date field, enter a date.</span></span>
    * <span data-ttu-id="c9b5f-120">A könyvelési dátum a főkönyvbe felvett könyvelési bejegyzés rögzítéséhez használható, valamint annak ellenőrzéséhez, hogy rendelkezésre állnak-e a költségvetési alapok.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-120">The accounting date is used to record the accounting entry in the general ledger, and to validate whether budget funds are available.</span></span>  
6. <span data-ttu-id="c9b5f-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-121">Click OK.</span></span>
7. <span data-ttu-id="c9b5f-122">Az Ok mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-122">In the Reason field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c9b5f-123">A választott indok alapértelmezés szerint megjelenik a beszerzési igénylési sorokban, de a sor szintjén módosíthatja azt.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-123">By default, the business justification reason that you select appears for the purchase requisition lines, but you can change it at the line level.</span></span>    
8. <span data-ttu-id="c9b5f-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-124">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="c9b5f-125">Válasszon ki egy okot</span><span class="sxs-lookup"><span data-stu-id="c9b5f-125">Select the reason</span></span>
10. <span data-ttu-id="c9b5f-126">A részletek mezőben adja meg az igénylést leíró részleteket</span><span class="sxs-lookup"><span data-stu-id="c9b5f-126">In the details field enter a more descriptive justification for the requisition</span></span>

## <a name="add-a-line-to-the-requisition"></a><span data-ttu-id="c9b5f-127">Sor hozzáadása az igényléshez</span><span class="sxs-lookup"><span data-stu-id="c9b5f-127">Add a line to the requisition</span></span>
1. <span data-ttu-id="c9b5f-128">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-128">Click Add line.</span></span>
    * <span data-ttu-id="c9b5f-129">A sorok hozzáadásának a beszerzési igényléshez két módja van.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-129">There are two ways of adding lines to the purchase requisition.</span></span> <span data-ttu-id="c9b5f-130">Ha a termékszámot ismeri, vagy már tudja, hogy olyan terméket kér, amely nem szerepel a termékkatalógusban, hozzáadhatja a sort közvetlenül a „Sor hozzáadása” paranccsal.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-130">If you already know the product number or you already  know that you are requesting a product that is not in the product catalog, then you can add the line directly with "Add line".</span></span> <span data-ttu-id="c9b5f-131">A másik lehetőség a „Termékek hozzáadása” lehetőség, amellyel a keresést és a szűrést is használhatja a termékkatalógusban szereplő cikkek kereséséhez.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-131">The other way is to use "Add products" where you can use searching and filtering to find items in the product catalog.</span></span>    
2. <span data-ttu-id="c9b5f-132">Kattintson a most létrehozott sorra.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-132">Click on the row you just created.</span></span>
    * <span data-ttu-id="c9b5f-133">A kérelmező az a dolgozó, aki az igénylést kérte.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-133">The requester is the worker that has requested the requisition.</span></span>   
    * <span data-ttu-id="c9b5f-134">Alapértelmezés szerint az igénylés előkészítését végző személy az a dolgozó, aki azt kérte.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-134">By default the person preparing the requisition is the worker who has requested it.</span></span> <span data-ttu-id="c9b5f-135">Jogosultsággal kell rendelkeznie ahhoz, ha egy másik dolgozó nevében Igényléssort szeretne készíteni.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-135">You have to be given permission to prepare a requisition line on behalf of another worker.</span></span> <span data-ttu-id="c9b5f-136">Ha ilyen engedélyek birtokában van, a többi dolgozó megjelenik a keresésben.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-136">If you have such permissions then the other workers will show up in this lookup.</span></span>  
3. <span data-ttu-id="c9b5f-137">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-137">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="c9b5f-138">A választható elemek korlátozva vannak a kategória-hozzáférési irányelv alapján, illetve a vásárló jogi személybeszerzési katalógusa alapján.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-138">The items that are available for you to choose are limited by the category access policy and the procurement catalog for the buying legal entity.</span></span>   
4. <span data-ttu-id="c9b5f-139">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-139">In the Quantity field, enter a number.</span></span>

## <a name="add-more-products-to-the-requisition"></a><span data-ttu-id="c9b5f-140">További termékek felvétele az igényléshez</span><span class="sxs-lookup"><span data-stu-id="c9b5f-140">Add more products to the requisition</span></span>
1. <span data-ttu-id="c9b5f-141">Kattintson a Termékek hozzáadása elemre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-141">Click Add products.</span></span>
    * <span data-ttu-id="c9b5f-142">Ezzel a beállítással kereshet a termékkatalógusban szereplő termékek között.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-142">This is the option where you can search for products in the product catalog.</span></span>    
2. <span data-ttu-id="c9b5f-143">A beszerzési kategória csomópontjának keresése mezőjébe írja be a keresett kategória nevének első részét, és kattintson az Enter billentyűre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-143">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="c9b5f-144">Például írja be a comput szöveget.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-144">For example, type comput.</span></span>  
3. <span data-ttu-id="c9b5f-145">Használja az InvokeDefaultButton billentyűparancsot.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-145">Use the InvokeDefaultButton shortcut.</span></span>
4. <span data-ttu-id="c9b5f-146">A választott kategóriában használja a Szűrés lehetőséget a termékek listájának szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-146">Use the Filter to filter the list of products in the selected category.</span></span>
5. <span data-ttu-id="c9b5f-147">Válassza ki azt a termékkártyát, amelyet hozzá szeretné adni az igényléshez.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-147">Select the product card that you want to add to the requisition.</span></span>
6. <span data-ttu-id="c9b5f-148">Kattintson a Hozzáadás a sorokhoz elemre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-148">Click Add to lines.</span></span>
7. <span data-ttu-id="c9b5f-149">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-149">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="c9b5f-150">A beszerzési kategória csomópontjának keresése mezőjébe írja be a keresett kategória nevének első részét, és kattintson az Enter billentyűre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-150">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="c9b5f-151">Írja be például a High (kiemelők) szöveget.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-151">For example, type High (highlighters).</span></span>  
9. <span data-ttu-id="c9b5f-152">Használja az InvokeDefaultButton billentyűparancsot.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-152">Use the InvokeDefaultButton shortcut.</span></span>
10. <span data-ttu-id="c9b5f-153">Kattintson a Fel nem sorolt termék hozzáadása a sorokhoz elemre, ha olyan terméket szeretne hozzáadni, amely nem szerepel a beszerzési katalógusban.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-153">Click Add unlisted product to lines to add a product that’s not listed in the procurement catalog.</span></span>
11. <span data-ttu-id="c9b5f-154">Írjon be egy értéket a Terméknév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-154">In the Product name field, type a value.</span></span>
12. <span data-ttu-id="c9b5f-155">Írjon be egy értéket a Mértékegység mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-155">In the Unit field, type a value.</span></span>
13. <span data-ttu-id="c9b5f-156">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-156">Click OK.</span></span>
14. <span data-ttu-id="c9b5f-157">A Cikk leírása mezőbe írja be a termék leírását.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-157">In the Item description field, add a description of the product.</span></span>
15. <span data-ttu-id="c9b5f-158">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-158">In the Quantity field, enter a number.</span></span>
16. <span data-ttu-id="c9b5f-159">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-159">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="c9b5f-160">Ha tudja az adott szállító árát (amit a szállítói számla mezőben választott ki), akkor ezt az árat is megadhatja</span><span class="sxs-lookup"><span data-stu-id="c9b5f-160">If you know the price for a particular vendor (that you select in the vendor account field) then that price can be entered</span></span>   
17. <span data-ttu-id="c9b5f-161">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-161">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c9b5f-162">Az ebben a mezőben rendelkezésre álló szállítók a beszerzési irányelvektől és attól az állapottól függnek, amellyel a szállító rendelkezik az aktuális beszerzési kategóriára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-162">The vendors that are available in this field depend on the purchasing policies and the status that the vendor has for the current procurement category.</span></span> <span data-ttu-id="c9b5f-163">Ahelyett, hogy itt kiválasztja a szállítót, rákattinthat a Szállítói javaslat gombra is.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-163">As an alternative to selecting a vendor here, you can click the Suggest vendor button.</span></span>    
18. <span data-ttu-id="c9b5f-164">A listából válassza ki a használni kívánt szállítót.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-164">In the list, select the vendor you want to use.</span></span>
19. <span data-ttu-id="c9b5f-165">A Külső cikkszám mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-165">In the External item number field, type a value.</span></span>
    * <span data-ttu-id="c9b5f-166">Ez annak a terméknek a hivatkozási száma, amelyet a szállító által ismer.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-166">This is a reference number for the product that is known by the vendor.</span></span> <span data-ttu-id="c9b5f-167">Ez lehet például lehet a szállító saját katalógusban szereplő termék cikkszáma.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-167">For example, this could be the item number of the product in the vendor's own catalog.</span></span>  
20. <span data-ttu-id="c9b5f-168">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-168">Click OK.</span></span>

## <a name="distribute-amounts"></a><span data-ttu-id="c9b5f-169">Összegek felosztása</span><span class="sxs-lookup"><span data-stu-id="c9b5f-169">Distribute amounts</span></span>
1. <span data-ttu-id="c9b5f-170">Kattintson a Pénzügyre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-170">Click Financials.</span></span>
2. <span data-ttu-id="c9b5f-171">Kattintson az Összegek felosztása elemre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-171">Click Distribute amounts.</span></span>
    * <span data-ttu-id="c9b5f-172">Ez a folyamat bemutatja, hogyan tudja az első sor költségét 2 számla között felosztani.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-172">This process shows you how to distribute the cost for the first line between 2 accounts.</span></span> <span data-ttu-id="c9b5f-173">Ezt később is megteheti, az igénylés ellenőrzésekor.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-173">This can also be done later when the requisition is in review.</span></span>  
3. <span data-ttu-id="c9b5f-174">Ha új elosztási sort szeretne létrehozni, Kattintson a Szétválasztás elemre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-174">Click Split to create a new distribution line.</span></span>
4. <span data-ttu-id="c9b5f-175">A Főkönyvi számla mezőben válassza ki azt az első költséghelyet, amelyet a költség részévé akar tenni.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-175">In the Ledger account field select the first cost center that should take part of the cost.</span></span>
5. <span data-ttu-id="c9b5f-176">Válassza ki a másik felosztási sort.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-176">Select the other distribution line.</span></span>
6. <span data-ttu-id="c9b5f-177">A Főkönyvi számla mezőben adja meg a költséghelyet.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-177">In the Ledger account field specify the other cost center.</span></span>
7. <span data-ttu-id="c9b5f-178">Kattintson az Egyenlő kiosztás elemre.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-178">Click Distribute equally.</span></span>
8. <span data-ttu-id="c9b5f-179">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-179">Close the page.</span></span>

## <a name="view-line-details"></a><span data-ttu-id="c9b5f-180">A sor részleteinek megjelenítése</span><span class="sxs-lookup"><span data-stu-id="c9b5f-180">View line details</span></span>
1. <span data-ttu-id="c9b5f-181">Bontsa ki a Sorok részletei részt.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-181">Toggle the expansion of the Line details section.</span></span>

## <a name="submit-the-requisition"></a><span data-ttu-id="c9b5f-182">Az igénylés elküldése</span><span class="sxs-lookup"><span data-stu-id="c9b5f-182">Submit the requisition</span></span>
1. <span data-ttu-id="c9b5f-183">A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-183">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="c9b5f-184">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-184">Click Submit.</span></span>
3. <span data-ttu-id="c9b5f-185">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-185">Close the page.</span></span>
4. <span data-ttu-id="c9b5f-186">A Megjegyzés mezőbe írjon be egy megjegyzést az igénylés jóváhagyójának.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-186">In the Comment field, type a note for the approver of the requisition.</span></span>
5. <span data-ttu-id="c9b5f-187">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-187">Click Submit.</span></span>
6. <span data-ttu-id="c9b5f-188">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9b5f-188">Close the page.</span></span>
7. <span data-ttu-id="c9b5f-189">Frissítse a lapot..</span><span class="sxs-lookup"><span data-stu-id="c9b5f-189">Refresh the page.</span></span>



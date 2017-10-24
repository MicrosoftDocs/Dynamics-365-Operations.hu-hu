--- 
title: "Beszerzési kategóriák hierarchiájának beállítása"
description: "Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát."
author: mkirknel
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9897b1184e8159b20a45d4cedbba56baef31a3c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="1e05d-103">Beszerzési kategóriák hierarchiájának beállítása</span><span class="sxs-lookup"><span data-stu-id="1e05d-103">Set up a procurement category hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1e05d-104">Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát.</span><span class="sxs-lookup"><span data-stu-id="1e05d-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="1e05d-105">Ezeket a feladatokat jellemzően egy beszerzési vezető végzi el.</span><span class="sxs-lookup"><span data-stu-id="1e05d-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="1e05d-106">Az eljárás megkezdése előtt kell lennie egy Beszerzés típusú kategóriahierarchiának.</span><span class="sxs-lookup"><span data-stu-id="1e05d-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="1e05d-107">Ha bemutató adatokat használ, ezt az eljárást az USMF vállalatban futtathatja.</span><span class="sxs-lookup"><span data-stu-id="1e05d-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="1e05d-108">Új beszerzési kategória hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1e05d-108">Add a new procurement category</span></span>
1. <span data-ttu-id="1e05d-109">Ugrás a Beszerzés és forrás > ..</span><span class="sxs-lookup"><span data-stu-id="1e05d-109">Go to Procurement and sourcing > ..</span></span> <span data-ttu-id="1e05d-110">> Beszerzési kategóriák.</span><span class="sxs-lookup"><span data-stu-id="1e05d-110">> Procurement categories.</span></span>
2. <span data-ttu-id="1e05d-111">Kattintson a Kategóriahierarchiák szerkesztése pontra.</span><span class="sxs-lookup"><span data-stu-id="1e05d-111">Click Edit category hierarchy.</span></span>
    * <span data-ttu-id="1e05d-112">Az aktuális beszerzési kategóriák hierarchiája az oldal bal oldalán jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1e05d-112">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="1e05d-113">Ezzel módosítja a hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="1e05d-113">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="1e05d-114">Kattintson az Új kategória-csomópont gombra.</span><span class="sxs-lookup"><span data-stu-id="1e05d-114">Click New category node.</span></span>
    * <span data-ttu-id="1e05d-115">A rendszer alapértelmezés szerint kiválasztja a felső csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1e05d-115">The system selects the top node by default.</span></span> <span data-ttu-id="1e05d-116">Ha ezzel az eljárással a feladatot útmutatóként futtatja, kattintson a zárolás feloldása gombra, és válasszon másik szülő-csomópontot, amelybe az új csomópontot szeretné beilleszteni.</span><span class="sxs-lookup"><span data-stu-id="1e05d-116">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="1e05d-117">Ezt követően zárolja újra a feladatútmutatót, és kattintson az Új kategória-csomópontra.</span><span class="sxs-lookup"><span data-stu-id="1e05d-117">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="1e05d-118">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1e05d-118">In the Name field, type a value.</span></span>
5. <span data-ttu-id="1e05d-119">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1e05d-119">In the Description field, type a value.</span></span>
6. <span data-ttu-id="1e05d-120">Írjon be egy értéket a Barátságos név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1e05d-120">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="1e05d-121">A baráti név nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="1e05d-121">The friendly name is optional.</span></span> <span data-ttu-id="1e05d-122">A kategória keresésekben a kategórianévvel együtt fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="1e05d-122">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="1e05d-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1e05d-123">Click Save.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="1e05d-124">Termékek hozzáadása az új beszerzési kategóriához</span><span class="sxs-lookup"><span data-stu-id="1e05d-124">Add products to your new procurement category</span></span>
1. <span data-ttu-id="1e05d-125">Ugrás a Beszerzés és forrás > ..</span><span class="sxs-lookup"><span data-stu-id="1e05d-125">Go to Procurement and sourcing > ..</span></span> <span data-ttu-id="1e05d-126">> Beszerzési kategóriák.</span><span class="sxs-lookup"><span data-stu-id="1e05d-126">> Procurement categories.</span></span>
    * <span data-ttu-id="1e05d-127">Jelölje ki az éppen hozzáadott csomópontot.</span><span class="sxs-lookup"><span data-stu-id="1e05d-127">Select the node you just added.</span></span> <span data-ttu-id="1e05d-128">Ha ezt a folyamatot feladat-útmutatóként használja, szükség lehet a feladat-útmutató feloldására a csomópont kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-128">If you’re running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="1e05d-129">Váltsa át a Termékek szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="1e05d-129">Toggle the expansion of the Products section.</span></span>
3. <span data-ttu-id="1e05d-130">Kattintson a Hozzáadás gombra a termékek hozzárendeléséhez a beszerzési kategóriával.</span><span class="sxs-lookup"><span data-stu-id="1e05d-130">Click Add to associate products with the procurement category.</span></span>
4. <span data-ttu-id="1e05d-131">Válassza ki azt a terméket, amelyet hozzá szeretné adni a beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-131">Select the product you want to add to the procurement category.</span></span>
5. <span data-ttu-id="1e05d-132">Kattintson a nyílra a termék kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-132">Click the arrow to select the product.</span></span>
6. <span data-ttu-id="1e05d-133">Válasszon egy másik terméket, amelyet hozzá szeretné adni a beszerzési kategóriához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-133">Select another product to add to the procurement category.</span></span>
7. <span data-ttu-id="1e05d-134">Kattintson a nyílra a termék kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-134">Click the arrow to select the product.</span></span>
8. <span data-ttu-id="1e05d-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1e05d-135">Click OK.</span></span>

## <a name="add-approved-and-preferred-vendors"></a><span data-ttu-id="1e05d-136">Jóváhagyott és preferált szállítók hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1e05d-136">Add approved and preferred vendors</span></span>
1. <span data-ttu-id="1e05d-137">Módosítsa a Szállítók szakasz bővítését.</span><span class="sxs-lookup"><span data-stu-id="1e05d-137">Toggle the expansion of the Vendors section.</span></span>
2. <span data-ttu-id="1e05d-138">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="1e05d-138">Click Add.</span></span>
    * <span data-ttu-id="1e05d-139">Szállítót adhat hozzá egy beszerzési kategóriához és megadhatja, hogy a szállító preferált vagy csak jóváhagyott legyen-e a kategóriában.</span><span class="sxs-lookup"><span data-stu-id="1e05d-139">You can add a vendor to a procurement category and specify whether a vendor is preferred or just approved for the category.</span></span> <span data-ttu-id="1e05d-140">Egy szállító kategóriából történő törlésekor a szállítóval történt előzménytranzakciók nem törlődnek.</span><span class="sxs-lookup"><span data-stu-id="1e05d-140">When you delete a vendor from a category, the historical transactions with the vendor in the category are not deleted.</span></span>   
3. <span data-ttu-id="1e05d-141">Keresse meg az a beszállítót, amelyet hozzá szeretné adni a kategóriához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-141">Find the vendor you want to add to the category.</span></span>
4. <span data-ttu-id="1e05d-142">Kattintson a nyílra a beszállító kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-142">Click the arrow to select the vendor.</span></span>
5. <span data-ttu-id="1e05d-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1e05d-143">Click OK.</span></span>
6. <span data-ttu-id="1e05d-144">Válassza ki a módosítani kívánt beszállítói sort.</span><span class="sxs-lookup"><span data-stu-id="1e05d-144">Select the vendor row that you want to modify.</span></span>
7. <span data-ttu-id="1e05d-145">A Beszállítói állapot mezőben válasszon ki egy opciót.</span><span class="sxs-lookup"><span data-stu-id="1e05d-145">In the Vendor status field, select an option.</span></span>
    * <span data-ttu-id="1e05d-146">A szállító kiválasztása beállítása a Kategória-irányelvszabályban azt szabályozza, hogy az elsődleges, a jóváhagyott, illetve valamennyi szállító elérhető-e a beszerzési igénylésekben.</span><span class="sxs-lookup"><span data-stu-id="1e05d-146">The vendor selection setting in the Category policy rule governs whether preferred, approved, or all vendors are available on purchase requisitions.</span></span>   

## <a name="add-additional-information-to-the-category"></a><span data-ttu-id="1e05d-147">További adatok hozzáadása a kategóriához</span><span class="sxs-lookup"><span data-stu-id="1e05d-147">Add additional information to the category</span></span>
1. <span data-ttu-id="1e05d-148">Váltsa át a Szállítóértékelési feltétel csoport kibontását.</span><span class="sxs-lookup"><span data-stu-id="1e05d-148">Toggle the expansion of the Vendor evaluation criterion groups section.</span></span>
    * <span data-ttu-id="1e05d-149">Ez a lap lehetővé teszi annak meghatározását, hogy melyik kritériumokkal szemben lesznek a beszerzési kategóriához tartozó szállítók mérve.</span><span class="sxs-lookup"><span data-stu-id="1e05d-149">This tab allows you to define which criteria the vendors in the procurement category should be rated against.</span></span> <span data-ttu-id="1e05d-150">Ehhez kattintson a Hozzáadás gombra, és válassza ki azt a szállítóértékelési csoportot, amely tartalmazza a kívánt feltételeket.</span><span class="sxs-lookup"><span data-stu-id="1e05d-150">To do this you would click Add and then select a vendor evaluation group that contains the criteria you want.</span></span>  
2. <span data-ttu-id="1e05d-151">Váltsa át a Kérdőívek szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="1e05d-151">Toggle the expansion of the Questionnaires section.</span></span>
    * <span data-ttu-id="1e05d-152">Ezen a lapon hozzáadhat kérdőíveket, amelyek megjelennek az igénylésen, mindaddig, amíg a Tevékenység típusának az „Igénylés”-t választja.</span><span class="sxs-lookup"><span data-stu-id="1e05d-152">This tab allows you to add questionnaires that will appear on the requisition, as long as you set the Activity type to "Requisition".</span></span> <span data-ttu-id="1e05d-153">A kérelmezőnek ki kell töltenie egy kérdőívet, mielőtt beküld egy kérelmet a beszerzési kategóriához tartozó termékek igénylése előtt.</span><span class="sxs-lookup"><span data-stu-id="1e05d-153">The requester then has to fill out a questionnaire before they submit a requisition for the specific product or products in the procurement category.</span></span>  
3. <span data-ttu-id="1e05d-154">Váltsa át a Cikkáfacsoport szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="1e05d-154">Toggle the expansion of the Item sales tax groups section.</span></span>
4. <span data-ttu-id="1e05d-155">A Cikkáfacsoport: mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e05d-155">In the Item sales tax group: field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1e05d-156">Áfacsoport kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="1e05d-156">Select a sales tax group.</span></span>
6. <span data-ttu-id="1e05d-157">Váltsa át a Kategóriaoldal szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="1e05d-157">Toggle the expansion of the Category page section.</span></span>
    * <span data-ttu-id="1e05d-158">A kategóriaoldalak a Kategóriahierarchia oldalon jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="1e05d-158">Category pages are created in the Category hierarchy page.</span></span> <span data-ttu-id="1e05d-159">Adatokat tartalmaznak a beszerzési kategóriáról, például az egy kategórián belüli terméktípus adatait, egy kategórián belüli termékek képeit, vagy bejelentéseket, például a kategórián belül elérhető kedvezményeket.</span><span class="sxs-lookup"><span data-stu-id="1e05d-159">They contain information about the procurement category such as information about the type of products in a category, images of products in a category, or announcements such as the discounts that are available in a category.</span></span> <span data-ttu-id="1e05d-160">A kategóriaoldalon lévő információk megjelennek a beszerzési igényléseken.</span><span class="sxs-lookup"><span data-stu-id="1e05d-160">The information in a category page is displayed on purchase requisitions.</span></span>  
7. <span data-ttu-id="1e05d-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1e05d-161">Close the page.</span></span>



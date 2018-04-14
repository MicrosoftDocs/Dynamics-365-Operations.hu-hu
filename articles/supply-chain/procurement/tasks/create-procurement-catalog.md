--- 
title: "Beszerzési katalógus létrehozása"
description: "Ez az segédlet bemutatja, hogyan lehet beszerzési katalógust létrehozni."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
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
ms.openlocfilehash: 66c0f41e1c98cf84b6a0afff5ee55e7c15fecd2d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="ca0dc-103">Beszerzési katalógus létrehozása</span><span class="sxs-lookup"><span data-stu-id="ca0dc-103">Create a procurement catalog</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ca0dc-104">Ez az segédlet bemutatja, hogyan lehet beszerzési katalógust létrehozni.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="ca0dc-105">Ezt a feladatot tipikusan egy beszerzési szakember végzi el.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="ca0dc-106">Azt is megtudhatja, hogy hogyan használhatják az alkalmazottak a katalógust egy igénylést létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="ca0dc-107">Katalógus létrehozása előtt már kell egy beszerzési kategória hierarchiával rendelkeznie a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="ca0dc-108">Az új katalógussal örökli a hierarchiát, minden olyan termékkel együtt, ami a hierarchiában benne van.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="ca0dc-109">Használhatja ezt a segédletet az USMF bemutató adatok vállalatban, ahol a beszerzési kategóriák hierarchiája rendelkezésre áll, ugyanúgy, mint az eljárásban használt példák.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="ca0dc-110">Győződjön meg arról, hogy létezik a beszerzési kategóriák hierarchiája</span><span class="sxs-lookup"><span data-stu-id="ca0dc-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="ca0dc-111">Ugorjon a Beszerzés és forrás > Beszerzési kategóriák pontra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="ca0dc-112">Egy beszerzési kategória hierarchia elérhető az USMF bemutató adatok vállalatnál és az Irodai gépek/Számítógépek kategóriához termékek lettek hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="ca0dc-113">Ha ezt a folyamatot feladat-útmutatóként használja, szüksége lehet az útmutató feloldására a kategóriák kereséséhez.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="ca0dc-114">Ha a hierarchia nem volt elérhető, hozzon létre egyet az Új gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="ca0dc-115">Ez csak egyszer lehetséges.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-115">This can only be done once.</span></span>  
2. <span data-ttu-id="ca0dc-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="ca0dc-117">Katalógus létrehozása</span><span class="sxs-lookup"><span data-stu-id="ca0dc-117">Create a catalog</span></span>
1. <span data-ttu-id="ca0dc-118">Ugorjon a Beszerzés és forrás > Katalógusok > Beszerzési katalógusok pontra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="ca0dc-119">Az Új beszerzési katalógus gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="ca0dc-120">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ca0dc-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-121">Click OK.</span></span>
5. <span data-ttu-id="ca0dc-122">A fán, nyissa ki a „CORP PROCUREMENT CATEGORIES” pontot.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="ca0dc-123">A fán, nyissa ki az „OFFICE MACHINES” pontot.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="ca0dc-124">A fán, válassza a „Computers” pontot.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="ca0dc-125">A beszerzési kategóriából származó termékek megjelennek a listában.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="ca0dc-126">Ha szeretne terméket hozzáadni a kategóriához, akkor ezt a Beszerzési kategóriák hierarchiája lapon vagy a Cikk részletei lapon teheti meg.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="ca0dc-127">Az Alapértelmezett frissítés típus meghatározza, hogy az új termékek amelyek hozzá lettek adva a beszerzési kategóriák hierarchiájához azonnal jelenjenek meg a katalógusban.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="ca0dc-128">Ha a frissítés típusa Dinamikus, a módosítások azonnal megjelennek.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="ca0dc-129">Ha a frissítés típusa Statikus, az új termékek csak azoknak az emberek számára fog megjelenni, akik az újra kiadott katalógust használják.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="ca0dc-130">A közzététel művelet a Művelet ablakban érhető el az oldal tetején.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="ca0dc-131">Ha termékek lettek eltávolítva a beszerzési kategóriák hierarchiájából, a változás azonnal látható, az Alapértelmezett frissítés típusától függetlenül.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="ca0dc-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="ca0dc-133">Kattintson az Elrejtésre.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-133">Click Hide.</span></span>
10. <span data-ttu-id="ca0dc-134">A Műveleti ablakban kattintson a Kategóriák szerinti navigációra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="ca0dc-135">Kattintson a Letiltásra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-135">Click Disable.</span></span>
12. <span data-ttu-id="ca0dc-136">A Műveleti ablakban kattintson a Kategóriák szerinti navigációra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="ca0dc-137">Kattintson az Engedélyezés gombra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-137">Click Enable.</span></span>
14. <span data-ttu-id="ca0dc-138">Kattintson a katalógus aktiválására.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="ca0dc-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="ca0dc-140">Tegye láthatóvá a katalógust</span><span class="sxs-lookup"><span data-stu-id="ca0dc-140">Make the catalog visible</span></span>
1. <span data-ttu-id="ca0dc-141">Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Irányelvek > Beszerzési irányelvek.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="ca0dc-142">Válassza az USMF Beszerzési Irányelvet.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="ca0dc-143">Ki kell választania a beszerzési irányelvet ahhoz jogi személyhez amihez a dolgozó csatlakozik és aminek a felhasználói profilja termékek rendelésére engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="ca0dc-144">A USMF bemutató adatokban, az Admin felhasználó a Julia Funderburk nevű dolgozóhoz van csatlakoztatva és ő rendeli meg a termékeket az USMF-ben alapértelmezés szerint.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="ca0dc-145">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ca0dc-146">Válassza ki a most létrehozott katalógust.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="ca0dc-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-147">Click OK.</span></span>
6. <span data-ttu-id="ca0dc-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-148">Close the page.</span></span>
7. <span data-ttu-id="ca0dc-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="ca0dc-150">Használja a katalógust</span><span class="sxs-lookup"><span data-stu-id="ca0dc-150">Use the catalog</span></span>
1. <span data-ttu-id="ca0dc-151">Ugorjon a Beszerzés és forrás > Beszerzési igénylések > Összes beszerzési igénylés pontra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="ca0dc-152">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-152">Click New.</span></span>
3. <span data-ttu-id="ca0dc-153">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="ca0dc-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-154">Click OK.</span></span>
5. <span data-ttu-id="ca0dc-155">Kattintson a Termékek hozzáadása elemre.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-155">Click Add products.</span></span>
6. <span data-ttu-id="ca0dc-156">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ca0dc-157">Használhatja a bal oldalon található kategóriahierarchiát vagy a lista tetején található szűrőt a termékek szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="ca0dc-158">Kattintson a Hozzáadás a sorokhoz elemre.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-158">Click Add to lines.</span></span>
8. <span data-ttu-id="ca0dc-159">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="ca0dc-160">Kattintson a Hozzáadás a sorokhoz elemre.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-160">Click Add to lines.</span></span>
10. <span data-ttu-id="ca0dc-161">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ca0dc-161">Click OK.</span></span>



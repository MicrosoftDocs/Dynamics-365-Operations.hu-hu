---
title: Alvállalkozói munkacella létrehozása a lean manufacturing szolgáltatáshoz
description: A lean manufacturing feladatokhoz alvállalkozásba adott munka modellezése érdekében létre kell hoznia egy olyan munkacellát, amely a munkát nyújtó szállítóhoz van társítva.
author: cvocph
manager: tfehr
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86838eb81f42b0f930f3989f7edfa5ee724bd05e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006891"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="189b6-103">Alvállalkozói munkacella létrehozása a lean manufacturing szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="189b6-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="189b6-104">A lean manufacturing feladatokhoz alvállalkozásba adott munka modellezése érdekében létre kell hoznia egy olyan munkacellát, amely a munkát nyújtó szállítóhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="189b6-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="189b6-105">Az alvállalkozói munkacella a szállítóhoz a Szállító típusa erőforrásának társításán keresztül kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="189b6-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="189b6-106">Ha ezt a felvételt lejátssza az USMF bemutató vállalat esetében, kiválaszthatja az 1002-es azonosítóval és az 1-es hellyes rendelkező szállítói számlát.</span><span class="sxs-lookup"><span data-stu-id="189b6-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="189b6-107">Szállítói erőforrás létrehozása</span><span class="sxs-lookup"><span data-stu-id="189b6-107">Create a vendor resource</span></span>
1. <span data-ttu-id="189b6-108">Ugrás az Erőforrások parancsra.</span><span class="sxs-lookup"><span data-stu-id="189b6-108">Go to Resources.</span></span>
2. <span data-ttu-id="189b6-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="189b6-109">Click New.</span></span>
3. <span data-ttu-id="189b6-110">Érték beírása az Erőforrás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="189b6-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="189b6-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="189b6-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="189b6-112">Válassza a Szállító lehetőséget a Típus mezőben.</span><span class="sxs-lookup"><span data-stu-id="189b6-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="189b6-113">A Szállító mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="189b6-114">Erőforráscsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="189b6-114">Create the resource group</span></span>
1. <span data-ttu-id="189b6-115">Ugrás az erőforráscsoportokra.</span><span class="sxs-lookup"><span data-stu-id="189b6-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="189b6-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="189b6-116">Click New.</span></span>
3. <span data-ttu-id="189b6-117">Írjon be egy értéket az Erőforráscsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="189b6-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="189b6-118">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="189b6-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="189b6-119">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="189b6-120">Válassza ki azt a helyet, amelyhez a munkacellát kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="189b6-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="189b6-121">Elméletben a hely a szállító által üzemeltetett egyetlen hely is lehet.</span><span class="sxs-lookup"><span data-stu-id="189b6-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="189b6-122">Azonban a legtöbb esetben a rendszer csak hozzárendeli az alvállalkozói erőforrásokat ahhoz a helyhez, amely megrendeli az alvállalkozói munkát.</span><span class="sxs-lookup"><span data-stu-id="189b6-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="189b6-123">Vegye figyelembe, hogy az alvállalkozói munkacellák bemeneti és kimeneti raktárainak ugyanazon a helyen kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="189b6-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="189b6-124">Érték beírása a Telephely mezőbe.</span><span class="sxs-lookup"><span data-stu-id="189b6-124">In the Site field, type a value.</span></span>
7. <span data-ttu-id="189b6-125">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="189b6-125">@SysTaskRecorder:_RequestClose</span></span>
8. <span data-ttu-id="189b6-126">Jelölje be a Munkacella jelölőnégyzetet, vagy törölje a jelet.</span><span class="sxs-lookup"><span data-stu-id="189b6-126">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="189b6-127">A Bemenő raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-127">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="189b6-128">Válassza ki azt a raktárt és helyet, amelyet a szállító által kezelt munkacellaanyagok előkészítéséhez használ.</span><span class="sxs-lookup"><span data-stu-id="189b6-128">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="189b6-129">A legtöbb esetben a rendszer a raktárt és a helyet szállítónként egy külön raktár és munkacellánként egy hely segítségével modellezi.</span><span class="sxs-lookup"><span data-stu-id="189b6-129">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="189b6-130">A Bemeneti hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-130">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="189b6-131">A Kimenő raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-131">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="189b6-132">Határozza meg azt a raktárt és helyet, ahol az anyagot feladták a munkacella alvállalkozói tevékenységeinek feladásakor.</span><span class="sxs-lookup"><span data-stu-id="189b6-132">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="189b6-133">A raktár és a hely a szállító helyén is lehet, ha a szállító jelenti a kanbanfeladatokat.</span><span class="sxs-lookup"><span data-stu-id="189b6-133">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="189b6-134">Másik lehetőségként a raktár és a hely a termelési folyamat következő lépéséhez társított fogadó hely is lehet.</span><span class="sxs-lookup"><span data-stu-id="189b6-134">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="189b6-135">A Kimeneti hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-135">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="189b6-136">Bontsa ki vagy csukja össze a Naptárak szakaszt.</span><span class="sxs-lookup"><span data-stu-id="189b6-136">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="189b6-137">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="189b6-137">Click Add.</span></span>
15. <span data-ttu-id="189b6-138">A Naptár mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-138">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="189b6-139">Társítsa a munkacella munkanaptárát az erőforráscsoporttal.</span><span class="sxs-lookup"><span data-stu-id="189b6-139">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="189b6-140">Kritikus erőforrások esetén javasoljuk, hogy a pontos munkaidőt és a munkacella vagy a szállító helyének kapcsolódó kapacitásait megjelenítő konkrét naptárakat határozzon meg.</span><span class="sxs-lookup"><span data-stu-id="189b6-140">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="189b6-141">Bontsa ki vagy csukja össze az Erőforrások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="189b6-141">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="189b6-142">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="189b6-142">Click Add.</span></span>
    * <span data-ttu-id="189b6-143">Az alvállalkozói erőforráscsoportnak rendelkeznie kell a Szállító típusa társított erőforrásával, amely összeköti az erőforráscsoportot a szállítói számlával.</span><span class="sxs-lookup"><span data-stu-id="189b6-143">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="189b6-144">Az Erőforrás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-144">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="189b6-145">Válassza ki vagy írja be az előző alfeladatban létrehozott szállítói erőforrást.</span><span class="sxs-lookup"><span data-stu-id="189b6-145">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="189b6-146">Bontsa ki vagy csukja össze a Munkacella-kapacitás adatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="189b6-146">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="189b6-147">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="189b6-147">Click Add.</span></span>
    * <span data-ttu-id="189b6-148">A munkacellának meghatározott kapacitással kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="189b6-148">A work cell must have a defined capacity.</span></span> <span data-ttu-id="189b6-149">Ebben a példában a termelési kapacitás egy szokásos munkanapon 100 munkadarab.</span><span class="sxs-lookup"><span data-stu-id="189b6-149">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="189b6-150">A Termelési folyamatmodell mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-150">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="189b6-151">Válassza ki valamelyik lehetőséget az Kapacitásidőszak mezőben.</span><span class="sxs-lookup"><span data-stu-id="189b6-151">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="189b6-152">Írjon be egy számot az Átlagos teljesítmény mezőbe.</span><span class="sxs-lookup"><span data-stu-id="189b6-152">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="189b6-153">Az Egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="189b6-153">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="189b6-154">ResolveChanges az Egység.</span><span class="sxs-lookup"><span data-stu-id="189b6-154">ResolveChanges the Unit.</span></span>


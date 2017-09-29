--- 
title: "Szervezeti jelentési hierarchia létrehozása"
description: "Ezzel az eljárással a szervezet jelentéseihez szükséges jelentéshierarchiát hozhatja létre."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f593c59660abcf5b0d5771ddd9daced6ec5fbfb4
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="8a539-103">Szervezeti jelentési hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a539-103">Create an organization report hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8a539-104">Ezzel az eljárással a szervezet jelentéseihez szükséges jelentéshierarchiát hozhatja létre.</span><span class="sxs-lookup"><span data-stu-id="8a539-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="8a539-105">Ezen felvétel célja a dimenzióhierarchia bemutatása, hogy folytatni tudja a munkát, amíg létrehozza a teljes szervezete jelentési struktúráját.</span><span class="sxs-lookup"><span data-stu-id="8a539-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="8a539-106">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="8a539-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="8a539-107">Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.</span><span class="sxs-lookup"><span data-stu-id="8a539-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="8a539-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-108">Click New.</span></span>
3. <span data-ttu-id="8a539-109">A HierarchyTypeComboBox mezőben válassza a Dimenzió-osztályozáshierarchia lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a539-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="8a539-110">Válassza a Dimenzió-osztályozáshierarchia lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a539-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="8a539-111">A Dimenzióosztályozás-hierarchia típus a szabályokhoz és a jelentésekhez szükséges.</span><span class="sxs-lookup"><span data-stu-id="8a539-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="8a539-112">Támogatja az összes dimenziót, például költségobjektumokat, költségelemeket és statisztikai dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="8a539-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="8a539-113">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-113">Click Create.</span></span>
5. <span data-ttu-id="8a539-114">A Dimenzióhierarchia mezőbe írja be a Szervezet USP2 értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="8a539-115">A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="8a539-116">Válassza a Költséghelyek lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a539-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="8a539-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-117">Click Save.</span></span>
8. <span data-ttu-id="8a539-118">Kattintson a Hierarchia megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="8a539-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-119">Click New.</span></span>
10. <span data-ttu-id="8a539-120">A Csomópont neve mezőbe írja be a Vezérigazgató értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="8a539-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-121">Click Save.</span></span>
12. <span data-ttu-id="8a539-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-122">Click New.</span></span>
13. <span data-ttu-id="8a539-123">A Csomópont neve mezőbe írja be a Vezérigazgatói költséghelyek értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="8a539-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-124">Click Save.</span></span>
15. <span data-ttu-id="8a539-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-125">Click New.</span></span>
16. <span data-ttu-id="8a539-126">A Csomópont neve mezőbe írja be a Keleti régió értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="8a539-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-127">Click Save.</span></span>
18. <span data-ttu-id="8a539-128">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-128">Click New.</span></span>
19. <span data-ttu-id="8a539-129">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a539-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="8a539-130">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="8a539-131">Válassza ki a csomópontnak megfelelő dimenziótagot.</span><span class="sxs-lookup"><span data-stu-id="8a539-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="8a539-132">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-132">Click Save.</span></span>
22. <span data-ttu-id="8a539-133">A fán válassza a Szervezet USP2\Vezérigazgató\Vezérigazgatói költséghelyek lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a539-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="8a539-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-134">Click New.</span></span>
24. <span data-ttu-id="8a539-135">A Csomópont neve mezőbe írja be a Nyugati régió értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="8a539-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-136">Click Save.</span></span>
26. <span data-ttu-id="8a539-137">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-137">Click New.</span></span>
27. <span data-ttu-id="8a539-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a539-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="8a539-139">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="8a539-140">Válassza ki a csomópontnak megfelelő dimenziótagot.</span><span class="sxs-lookup"><span data-stu-id="8a539-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="8a539-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-141">Click Save.</span></span>
30. <span data-ttu-id="8a539-142">A fán válassza a Szervezet USP2\Vezérigazgató lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a539-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="8a539-143">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-143">Click New.</span></span>
32. <span data-ttu-id="8a539-144">A Csomópont neve mezőbe írja be a Pénzügyi vezetői költséghelyek értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="8a539-145">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-145">Click Save.</span></span>
34. <span data-ttu-id="8a539-146">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-146">Click New.</span></span>
35. <span data-ttu-id="8a539-147">A Csomópont neve mezőbe írja be a Marketingkamp értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="8a539-148">A Csomópont neve mezőbe írja be a Marketingkampány értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="8a539-149">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-149">Click Save.</span></span>
38. <span data-ttu-id="8a539-150">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-150">Click New.</span></span>
39. <span data-ttu-id="8a539-151">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a539-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="8a539-152">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="8a539-153">Válassza ki a csomópontnak megfelelő dimenziótagot.</span><span class="sxs-lookup"><span data-stu-id="8a539-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="8a539-154">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-154">Click Save.</span></span>
42. <span data-ttu-id="8a539-155">A fán válassza a Szervezet USP2\Vezérigazgató\Vezérigazgatói költséghelyek lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a539-155">In the tree, select 'Oganization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="8a539-156">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-156">Click New.</span></span>
44. <span data-ttu-id="8a539-157">A Csomópont neve mezőbe írja be a Kereskedelmi börzék értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="8a539-158">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-158">Click Save.</span></span>
46. <span data-ttu-id="8a539-159">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-159">Click New.</span></span>
47. <span data-ttu-id="8a539-160">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a539-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="8a539-161">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="8a539-162">Válassza ki a csomópontnak megfelelő dimenziótagot.</span><span class="sxs-lookup"><span data-stu-id="8a539-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="8a539-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-163">Click Save.</span></span>
50. <span data-ttu-id="8a539-164">A fán válassza a Szervezet USP2\Vezérigazgató lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a539-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="8a539-165">A Csomópont neve mezőbe írja be a Informatikai igazgatói költséghelyek értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="8a539-166">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-166">Click Save.</span></span>
53. <span data-ttu-id="8a539-167">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-167">Click New.</span></span>
54. <span data-ttu-id="8a539-168">A Csomópont neve mezőbe írja be a Hívásközpontok értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="8a539-169">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-169">Click Save.</span></span>
56. <span data-ttu-id="8a539-170">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a539-170">Click New.</span></span>
57. <span data-ttu-id="8a539-171">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8a539-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="8a539-172">A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a539-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="8a539-173">Válassza ki a csomópontnak megfelelő dimenziótagot.</span><span class="sxs-lookup"><span data-stu-id="8a539-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="8a539-174">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a539-174">Click Save.</span></span>



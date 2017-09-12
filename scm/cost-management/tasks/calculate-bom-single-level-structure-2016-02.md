--- 
title: "Anyagjegyzék-számítás elvégzése egyszintű struktúra használatával (csak 2016. február)"
description: "Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét egyszintű alábontással, amelynek az alapja a költségszámítási táblázat."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0e6829238b244cc01b070fde6acdf37bdaeb9670
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016-only"></a><span data-ttu-id="16f28-103">Anyagjegyzék-számítás elvégzése egyszintű struktúra használatával (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="16f28-103">Calculate a BOM by using a single level structure (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="16f28-104">Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét egyszintű alábontással, amelynek az alapja a költségszámítási táblázat.</span><span class="sxs-lookup"><span data-stu-id="16f28-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="16f28-105">Ez az anyagjegyzék-számítási sorozat hatodik feladata.</span><span class="sxs-lookup"><span data-stu-id="16f28-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="16f28-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="16f28-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="16f28-107">Ugrás a Kiadott termékek elemre.</span><span class="sxs-lookup"><span data-stu-id="16f28-107">Go to Released products.</span></span>
2. <span data-ttu-id="16f28-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="16f28-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="16f28-109">Termék BOM_1 kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="16f28-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="16f28-110">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="16f28-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="16f28-111">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="16f28-111">Click Item price.</span></span>
5. <span data-ttu-id="16f28-112">Kattintson a Cikk-költség kiszámítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="16f28-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="16f28-113">Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.</span><span class="sxs-lookup"><span data-stu-id="16f28-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="16f28-114">A Költségszámítási verzió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="16f28-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="16f28-115">Ehhez a bemutatóhoz válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="16f28-115">For this demo, select 10.</span></span> <span data-ttu-id="16f28-116">Ez ugyanaz a költségszámítási verzió, amelyet az önköltségi ár hozzáadására használtunk az összetevőkhöz.</span><span class="sxs-lookup"><span data-stu-id="16f28-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="16f28-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="16f28-117">Click OK.</span></span>
8. <span data-ttu-id="16f28-118">Kattintson a Számítás részleteinek megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="16f28-118">Click View calculation details.</span></span>
    * <span data-ttu-id="16f28-119">Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.</span><span class="sxs-lookup"><span data-stu-id="16f28-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="16f28-120">Itt látható a költség összetétele: • 10 az ITEM_A elemből származik, 10 az ITEM_B elemből, 10 a BOM_2 elemből.</span><span class="sxs-lookup"><span data-stu-id="16f28-120">Here's the composition of the cost:  •    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="16f28-121">Ebben az esetben nincsenek részletek a BOM_2 esetében, mert a bevitele 10-es elszámolóárként történt, de nem a kalkuláció használatával.</span><span class="sxs-lookup"><span data-stu-id="16f28-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="16f28-122">•  7 forrása a beállítási idő, amely egy állandó költség, és további 7 forrása a futásidejű művelet (folyamat).</span><span class="sxs-lookup"><span data-stu-id="16f28-122">•  7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="16f28-123">•   Vannak egyéb összegek is, amelyek megfelelnek a közvetett költségeknek.</span><span class="sxs-lookup"><span data-stu-id="16f28-123">•   There are also other amounts that correspond to indirect costs.</span></span>  
9. @SysTaskRecorder:_RequestClose



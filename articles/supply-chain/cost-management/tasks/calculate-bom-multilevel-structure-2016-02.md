--- 
title: "Anyagjegyzék-számítás elvégzése több szintű struktúra használatával (csak 2016. február)"
description: "Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét többszintű alábontással, amelynek az alapja a költségszámítási táblázat."
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 16c2cacaf70df5455c3ed49b8dcb5756e89f8cb8
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016-only"></a><span data-ttu-id="29f2b-103">Anyagjegyzék-számítás elvégzése több szintű struktúra használatával (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="29f2b-103">Calculate a BOM by using a multilevel structure (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="29f2b-104">Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét többszintű alábontással, amelynek az alapja a költségszámítási táblázat.</span><span class="sxs-lookup"><span data-stu-id="29f2b-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="29f2b-105">Ez az anyagjegyzék-számítási sorozat hetedik feladata.</span><span class="sxs-lookup"><span data-stu-id="29f2b-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="29f2b-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="29f2b-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="29f2b-107">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29f2b-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="29f2b-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="29f2b-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="29f2b-109">Termék BOM_1 kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="29f2b-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="29f2b-110">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="29f2b-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="29f2b-111">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="29f2b-111">Click Item price.</span></span>
5. <span data-ttu-id="29f2b-112">Kattintson a Cikk-költség kiszámítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="29f2b-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="29f2b-113">Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.</span><span class="sxs-lookup"><span data-stu-id="29f2b-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="29f2b-114">A Költségszámítási verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="29f2b-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="29f2b-115">Válassza a 20-as költségszámítási verziót, mivel ez egy tervezett költségtípus, és az alábontási mód többszintű.</span><span class="sxs-lookup"><span data-stu-id="29f2b-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="29f2b-116">A többszintű alábontási módot a tervezett költségekhez és szimulációkhoz használjuk.</span><span class="sxs-lookup"><span data-stu-id="29f2b-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="29f2b-117">Az elszámolóárhoz nem használt.</span><span class="sxs-lookup"><span data-stu-id="29f2b-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="29f2b-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="29f2b-118">Click OK.</span></span>
8. <span data-ttu-id="29f2b-119">Kattintson a Számítás részleteinek megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="29f2b-119">Click View calculation details.</span></span>
    * <span data-ttu-id="29f2b-120">Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.</span><span class="sxs-lookup"><span data-stu-id="29f2b-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="29f2b-121">Ebben az esetben figyelje meg, hogy BOM_2 kiszámításánál figyelembe vesszük a nyersanyagot, a feldolgozást és a járulékos költséget összesen 29,40 értékben ahelyett a 10-es elszámolóár helyett, amelyet a sorozat első feladat-útmutatójában aktiváltunk.</span><span class="sxs-lookup"><span data-stu-id="29f2b-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="29f2b-122">Kattintson a Költségszámítási táblázat fülre.</span><span class="sxs-lookup"><span data-stu-id="29f2b-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="29f2b-123">A Költségszámítás lapfülre lépve a költségcsoportonkénti összegek különböznek az előző feladat-útmutatóban elvégzett számítástól.</span><span class="sxs-lookup"><span data-stu-id="29f2b-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="29f2b-124">A Szint mezőben válassza a következőt: „Többszörös”.</span><span class="sxs-lookup"><span data-stu-id="29f2b-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="29f2b-125">Többszörös kiválasztáskor a költségek besorolásának alapja a BOM_2, ahol a 10 forrása az M1 költségcsoport (ITEM_C), a 15,60 pedig a gyártásából származik, ahol a költségcsoport az L2.</span><span class="sxs-lookup"><span data-stu-id="29f2b-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="29f2b-126">A közvetett költségek is eltérőek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="29f2b-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="29f2b-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="29f2b-127">Close the page.</span></span>
12. <span data-ttu-id="29f2b-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="29f2b-128">Close the page.</span></span>


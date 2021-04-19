---
title: Anyagjegyzék-számítás elvégzése egyetlen szintű struktúra használatával (2016. február)
description: Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét egyszintű alábontással, amelynek az alapja a költségszámítási táblázat.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 013eddf1ba8e8cab3c87cb1f063d9bf886b0f833
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821393"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a><span data-ttu-id="f4b13-103">Anyagjegyzék-számítás elvégzése egyetlen szintű struktúra használatával (2016. február)</span><span class="sxs-lookup"><span data-stu-id="f4b13-103">Calculate a BOM by using a single level structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f4b13-104">Ez az eljárás bemutatja, hogyan lehet kiszámítani egy késztermék költségét egyszintű alábontással, amelynek az alapja a költségszámítási táblázat.</span><span class="sxs-lookup"><span data-stu-id="f4b13-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="f4b13-105">Ez az anyagjegyzék-számítási sorozat hatodik feladata.</span><span class="sxs-lookup"><span data-stu-id="f4b13-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="f4b13-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="f4b13-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="f4b13-107">Ugrás a Kiadott termékek elemre.</span><span class="sxs-lookup"><span data-stu-id="f4b13-107">Go to Released products.</span></span>
2. <span data-ttu-id="f4b13-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f4b13-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f4b13-109">Termék BOM_1 kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="f4b13-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="f4b13-110">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="f4b13-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="f4b13-111">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="f4b13-111">Click Item price.</span></span>
5. <span data-ttu-id="f4b13-112">Kattintson a Cikk-költség kiszámítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f4b13-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="f4b13-113">Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.</span><span class="sxs-lookup"><span data-stu-id="f4b13-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="f4b13-114">A Költségszámítási verzió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f4b13-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f4b13-115">Ehhez a bemutatóhoz válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="f4b13-115">For this demo, select 10.</span></span> <span data-ttu-id="f4b13-116">Ez ugyanaz a költségszámítási verzió, amelyet az önköltségi ár hozzáadására használtunk az összetevőkhöz.</span><span class="sxs-lookup"><span data-stu-id="f4b13-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="f4b13-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f4b13-117">Click OK.</span></span>
8. <span data-ttu-id="f4b13-118">Kattintson a Számítás részleteinek megjelenítése elemre.</span><span class="sxs-lookup"><span data-stu-id="f4b13-118">Click View calculation details.</span></span>
    * <span data-ttu-id="f4b13-119">Előfordulhat, hogy a három pont (...) elemre kell kattintania a lehetőség megtekintéséhez a főmenüben.</span><span class="sxs-lookup"><span data-stu-id="f4b13-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="f4b13-120">Itt látható a költség összetétele:  \*    10 az ITEM_A elemből származik, 10 az ITEM_B elemből, 10 a BOM_2 elemből.</span><span class="sxs-lookup"><span data-stu-id="f4b13-120">Here's the composition of the cost:  \*    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="f4b13-121">Ebben az esetben nincsenek részletek a BOM_2 esetében, mert a bevitele 10-es elszámolóárként történt, de nem a kalkuláció használatával.</span><span class="sxs-lookup"><span data-stu-id="f4b13-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="f4b13-122">\*    7 forrása a beállítási idő, amely egy állandó költség, és további 7 forrása a futásidejű művelet (folyamat).</span><span class="sxs-lookup"><span data-stu-id="f4b13-122">\*    7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="f4b13-123">\*    Vannak egyéb összegek is, amelyek megfelelnek a közvetett költségeknek.</span><span class="sxs-lookup"><span data-stu-id="f4b13-123">\*    There are also other amounts that correspond to indirect costs.</span></span>  
9. <span data-ttu-id="f4b13-124">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="f4b13-124">@SysTaskRecorder:_RequestClose</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Tervezett rendelések karbantartása
description: Ez a témakör a tervezett rendelések kezelésével kapcsolatban nyújt információkat. Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.
author: roxanadiaconu
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ecda1c113a0663ff430aa15a0023668097078ad1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213814"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="9dd52-104">Tervezett rendelések karbantartása</span><span class="sxs-lookup"><span data-stu-id="9dd52-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9dd52-105">Ez a témakör a tervezett rendelések kezelésével kapcsolatban nyújt információkat.</span><span class="sxs-lookup"><span data-stu-id="9dd52-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="9dd52-106">Leírja, hogyan frissítheti a tervezett rendelések állapotát, erősítheti meg őket, és hogy hogyan szűrheti a kijelölttel azonos állapotú tervezett rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="9dd52-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="9dd52-107">A tervezett rendeléseket kezelheti az **Alaptervezés** munkaterületen, a **Tervezett rendelés** listában, vagy a **Tervezett termelési rendelések**, **Tervezett beszerzési rendelések**, és **Tervezett átmozgatás** listákban.</span><span class="sxs-lookup"><span data-stu-id="9dd52-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="9dd52-108">Tervezett rendelésállapot</span><span class="sxs-lookup"><span data-stu-id="9dd52-108">Planned order status</span></span>
<span data-ttu-id="9dd52-109">Használhatja az **Állapot** mezőt, ami segít nyomon követni folyamatot.</span><span class="sxs-lookup"><span data-stu-id="9dd52-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="9dd52-110">A következő értékek kerülnek felhasználásra:</span><span class="sxs-lookup"><span data-stu-id="9dd52-110">The following values are used:</span></span>

-   <span data-ttu-id="9dd52-111">Amikor az alaptervezés tervezett rendeléseket készít, akkor a tervezett rendelések állapota **Feldolgozatlan**.</span><span class="sxs-lookup"><span data-stu-id="9dd52-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="9dd52-112">Ha úgy dönt, hogy nem erősíti meg a tervezett rendelést, akkor hozzárendelheti a **Befejezett** állapotot.</span><span class="sxs-lookup"><span data-stu-id="9dd52-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="9dd52-113">Ha meg szeretné határozni a tervezett rendelést, akkor a **Jóváhagyott** állapotra módosítható.</span><span class="sxs-lookup"><span data-stu-id="9dd52-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="9dd52-114">Az Alaptervezés figyelembe veszi a **Jóváhagyott** állapotú tervezett rendeléseket, így azokat nem módosítja vagy nem törli a program későbbi alaptervezés futtatása során.</span><span class="sxs-lookup"><span data-stu-id="9dd52-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted during a later master planning run.</span></span> <span data-ttu-id="9dd52-115">Ennek elérése érdekében a tervezési logika átmásolja a **Jóváhagyott** tervezett rendeléseket a régi terv verzióból az új terv verzióba az alaptervezés során.</span><span class="sxs-lookup"><span data-stu-id="9dd52-115">To achieve this, the planning logic copies the **Approved** planned orders from the old plan version to the new plan version during master planning.</span></span>

## <a name="firming-planned-orders"></a><span data-ttu-id="9dd52-116">Tervezett rendelések megerősítése</span><span class="sxs-lookup"><span data-stu-id="9dd52-116">Firming planned orders</span></span> 
<span data-ttu-id="9dd52-117">A tervezett rendelések megerősítésével létrejönnek a tényleges rendelések.</span><span class="sxs-lookup"><span data-stu-id="9dd52-117">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="9dd52-118">Ismertek *kiadott* vagy *nyitott rendelésként* is.</span><span class="sxs-lookup"><span data-stu-id="9dd52-118">These are also known as *released* or *open orders*.</span></span> <span data-ttu-id="9dd52-119">Amikor egy tervezett rendelést megerősít, akkor az a megfelelő modul rendelések szakaszába kerül.</span><span class="sxs-lookup"><span data-stu-id="9dd52-119">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="9dd52-120">A **Tervezett rendelések** lapon két megerősítő beállítást választhat:</span><span class="sxs-lookup"><span data-stu-id="9dd52-120">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="9dd52-121">**Megerősítés** – egy vagy több kiválasztott tervezett rendelést erősít meg.</span><span class="sxs-lookup"><span data-stu-id="9dd52-121">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="9dd52-122">**Összes megerősítése** – a szűrő minden tervezett rendelését megerősíti.</span><span class="sxs-lookup"><span data-stu-id="9dd52-122">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="9dd52-123">Az **Összes megerősítése** használatakor nem kell kijelölni a tervezett rendelést, a szűrőn belül minden tervezett rendelés megerősítést kap.</span><span class="sxs-lookup"><span data-stu-id="9dd52-123">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="9dd52-124">Ez a beállítás akkor lehet hasznos, ha nagy számú tervezett rendelést erősít meg.</span><span class="sxs-lookup"><span data-stu-id="9dd52-124">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="9dd52-125">Nyomon követheti azt a tervezett rendelést, amely itt lett megerősítve: **Megerősítések előzményei**, a következő alatt: **Tervezett rendelések képernyő > Nézet > Megerősítések előzményei**.</span><span class="sxs-lookup"><span data-stu-id="9dd52-125">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="9dd52-126">Párhuzamos megerősítés</span><span class="sxs-lookup"><span data-stu-id="9dd52-126">Parallelize firming</span></span>
<span data-ttu-id="9dd52-127">Ha egyszerre több rendelést szeretne megerősíteni, akkor a futtatás párhuzamosítása javíthatja a futási időt vagy a teljesítményt.</span><span class="sxs-lookup"><span data-stu-id="9dd52-127">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="9dd52-128">Ez a beállítás csak akkor érhető el, ha több tervezett rendelést erősít meg a következők egyikével: **Megerősítés** vagy **Összes megerősítése**.</span><span class="sxs-lookup"><span data-stu-id="9dd52-128">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="9dd52-129">A következő paraméterek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="9dd52-129">The following parameters are available:</span></span>

-   <span data-ttu-id="9dd52-130">**Megerősítés párhuzamosítása** – ha **Igen**, a megerősítési folyamat párhuzamos lesz a **Szálak száma** esetében meghatározott szálak számával.</span><span class="sxs-lookup"><span data-stu-id="9dd52-130">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="9dd52-131">**Szálak száma** – a megerősítési folyamat párhuzamosítására használt szálak számát adja meg.</span><span class="sxs-lookup"><span data-stu-id="9dd52-131">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="9dd52-132">A paraméter csak akkor jelenik meg, ha a **Megerősítés párhuzamosítása** beállítása **Igen**.</span><span class="sxs-lookup"><span data-stu-id="9dd52-132">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="9dd52-133">A **Párhuzamos megerősítés** lehetősége csak akkor jelenik meg, ha egynél több tervezett rendelés van kiválasztva a megerősítéskor.</span><span class="sxs-lookup"><span data-stu-id="9dd52-133">The option for **Parallelize firming** is only shown when you have more than one planned order selected for firming.</span></span>

<a name="additional-resources"></a><span data-ttu-id="9dd52-134">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9dd52-134">Additional resources</span></span>
--------

[<span data-ttu-id="9dd52-135">Alaptervek áttekintése</span><span class="sxs-lookup"><span data-stu-id="9dd52-135">Master plans overview</span></span>](master-plans.md)




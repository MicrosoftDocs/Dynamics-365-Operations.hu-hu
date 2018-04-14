---
title: "Készlet mozgatásának engedélyezése társított munkával a Raktárkezelésben"
description: "Ez a témakör leírja, hogyan állíthatja be és alkalmazhatja a darabkitárolás megerősítését mobileszközről."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7d81397ed30751f5b3dd7c46ffe6b27b8153c8f9
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="9ee0d-103">Készlet mozgatásának engedélyezése társított munkával a Raktárkezelésben</span><span class="sxs-lookup"><span data-stu-id="9ee0d-103">Movement of inventory with associated work in Warehouse management</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="9ee0d-104">A készletmozgás használatával megadhatja, hogy melyik raktárosok számára engedélyezett a lefoglalt készlet mozgatása.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="9ee0d-105">Ez rugalmasságot biztosít a szabályozott raktárakban, mert lehetőséget nyújt úgy dönteni, hogy nem engedélyezi új kitárolási hely választását a dolgozó számára a már létrehozott kitárolási munkákhoz.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="9ee0d-106">Emellett lehetővé teszi a raktárvezető számára annak a kontrollját, hogy egyes kevésbé tapasztalt dolgozók milyen lehetőségekkel rendelkezzenek.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="9ee0d-107">A raktári dolgozók napi tevékenységének kezelését érintő rugalmasság például az alábbi esetekben lehet hasznos:</span><span class="sxs-lookup"><span data-stu-id="9ee0d-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="9ee0d-108">1. eset</span><span class="sxs-lookup"><span data-stu-id="9ee0d-108">Scenario 1</span></span>
<span data-ttu-id="9ee0d-109">A vállalatnak van egy viszonylag kis fogadóterülete, amely zsúfolva van betárolásra váró raklapokkal és dobozokkal.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="9ee0d-110">Az aktuális napon nagy szállítmány várható, ezért a bevételezési adminisztrátor úgy dönt, hogy kiüríti a beérkezési területet úgy, hogy a raklapok egy részét egy másodlagos bejövő előkészítő területre helyezi át.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="9ee0d-111">2. eset</span><span class="sxs-lookup"><span data-stu-id="9ee0d-111">Scenario 2</span></span>
<span data-ttu-id="9ee0d-112">Egy tapasztalt raktári dolgozó észreveszi, hogy bizonyos cikkeket egy helyre lehetne konszolidálni ahelyett, hogy három közeli helyen tárolnák őket, mindhárom helyen kis mennyiségben.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across 3 nearby locations with little quantity on each.</span></span> <span data-ttu-id="9ee0d-113">A dolgozó konszolidálni szeretné a mennyiséget azzal, hogy mindhárom helyről egy helyre viszi a cikkeket, azonos azonosítótábla alá.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="9ee0d-114">3. eset</span><span class="sxs-lookup"><span data-stu-id="9ee0d-114">Scenario 3</span></span>
<span data-ttu-id="9ee0d-115">Egy raklap szállításra vár egy előkészítő helyen, például a STAGE01 helyen, amely a BAYDOOR01 közelében van.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="9ee0d-116">Azonban a tervek módosítása miatt a teherautó érkezése a BAYDOOR04 területre van ütemezve.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="9ee0d-117">A szállítási adminisztrátor tud erről, és biztosítania kell, hogy a teherautónak ne kelljen várnia a berakodásra a STAGE01 területről.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="9ee0d-118">A szállítási adminisztrátor úgy dönt, hogy a szállítmányhoz tartozó cikkeket át kell helyezni a STAGE01 területről az új célhoz közelebbi STAGE04 területre.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="9ee0d-119">Jelenlegi korlátozások</span><span class="sxs-lookup"><span data-stu-id="9ee0d-119">Current limitations</span></span>

<span data-ttu-id="9ee0d-120">Az áthelyezhető munkafoglalások a következőkre korlátoznak: értékesítési rendelés, átmozgatási rendelés kiadása, átmozgatási rendelés – bevételezés, beszerzési rendelés és feltöltési munka.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="9ee0d-121">A cikkek áthelyezése korlátozott a munkasorok felosztásának megakadályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="9ee0d-122">Ez azt jelenti, hogy ha van egy munkasorunk 100 darabra az A cikkből a Loc1 helyről, nem lehet csak 30 darabot áthelyezni az A cikkből innen egy másik helyre.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="9ee0d-123">Ez a meglévő munkasor felosztását eredményezné 30 és 70 cikkre, mivel most már más a hely.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="9ee0d-124">Az előkészítési esetekben, amikor az azonosítótábla, amelyről vagy amelyre áthelyezzük a cikkeket, a munkarendelés cél azonosítótáblájaként van beállítva, csak a teljes azonosítótábla mozgása engedélyezett, hogy ne legyen felbontva a cél azonosítótábla.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>
<span data-ttu-id="9ee0d-125">Jelenleg csak az ad hoc mozgás támogatott.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="9ee0d-126">Ez azt jelenti, hogy nem lehet mozgatni a foglalt készletet a mozgás sablon szerint mobileszközmenü-elemekkel.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="9ee0d-127">Engedély beállítása az egyes dolgozók számára a lefoglalt készlet mozgatásához</span><span class="sxs-lookup"><span data-stu-id="9ee0d-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="9ee0d-128">Annak a dolgozónak az esetében, akinek a számára engedélyezni kell a foglalt készlet mozgatását, jelölje be a **Készlet mozgatásának engedélyezése társított munkával** jelölőnégyzetet a következő helyen: **Raktárkezelés** > **Beállítás** > **Dolgozó**.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-128">For the worker who should be allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management** > **Setup** > **Worker**.</span></span>  

### <a name="backported"></a><span data-ttu-id="9ee0d-129">Visszaportolás</span><span class="sxs-lookup"><span data-stu-id="9ee0d-129">Backported</span></span>

<span data-ttu-id="9ee0d-130">Ezt a funkciót visszaportoltuk a Microsoft Dynamics AX 2012 R3 verzióba, és elérhető lesz az CU12 részeként.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-130">This feature has also been back-ported to Microsoft Dynamics AX 2012 R3 and will be available as part of CU12.</span></span>
<span data-ttu-id="9ee0d-131">Önállóan is letölthető a 3192548 KB-számon.</span><span class="sxs-lookup"><span data-stu-id="9ee0d-131">It can also be downloaded individually through KB number 3192548.</span></span> 



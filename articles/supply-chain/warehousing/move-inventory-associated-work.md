---
title: Készlet mozgatásának engedélyezése társított munkával a Raktárkezelésben
description: A készletmozgás használatával megadhatja, hogy melyik raktárosok számára engedélyezett a lefoglalt készlet mozgatása.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6477a91b3c65e8be5ab527eaff12c92ae7918b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808750"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="89c5a-103">Készlet mozgatásának engedélyezése társított munkával a Raktárkezelésben</span><span class="sxs-lookup"><span data-stu-id="89c5a-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89c5a-104">A készletmozgás használatával megadhatja, hogy melyik raktárosok számára engedélyezett a lefoglalt készlet mozgatása.</span><span class="sxs-lookup"><span data-stu-id="89c5a-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="89c5a-105">Ez rugalmasságot biztosít a szabályozott raktárakban, mert lehetőséget nyújt úgy dönteni, hogy nem engedélyezi új kitárolási hely választását a dolgozó számára a már létrehozott kitárolási munkákhoz.</span><span class="sxs-lookup"><span data-stu-id="89c5a-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="89c5a-106">Emellett lehetővé teszi a raktárvezető számára annak a kontrollját, hogy egyes kevésbé tapasztalt dolgozók milyen lehetőségekkel rendelkezzenek.</span><span class="sxs-lookup"><span data-stu-id="89c5a-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="89c5a-107">A raktári dolgozók napi tevékenységének kezelését érintő rugalmasság például az alábbi esetekben lehet hasznos:</span><span class="sxs-lookup"><span data-stu-id="89c5a-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="89c5a-108">1. eset</span><span class="sxs-lookup"><span data-stu-id="89c5a-108">Scenario 1</span></span>

<span data-ttu-id="89c5a-109">A vállalatnak van egy viszonylag kis fogadóterülete, amely zsúfolva van betárolásra váró raklapokkal és dobozokkal.</span><span class="sxs-lookup"><span data-stu-id="89c5a-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="89c5a-110">Az aktuális napon nagy szállítmány várható, ezért a bevételezési adminisztrátor úgy dönt, hogy kiüríti a beérkezési területet úgy, hogy a raklapok egy részét egy másodlagos bejövő előkészítő területre helyezi át.</span><span class="sxs-lookup"><span data-stu-id="89c5a-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="89c5a-111">2. eset</span><span class="sxs-lookup"><span data-stu-id="89c5a-111">Scenario 2</span></span>

<span data-ttu-id="89c5a-112">Egy tapasztalt raktári dolgozó észreveszi, hogy bizonyos cikkeket egy helyre lehetne konszolidálni ahelyett, hogy három közeli helyen tárolnák őket, mindhárom helyen kis mennyiségben.</span><span class="sxs-lookup"><span data-stu-id="89c5a-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across three nearby locations with little quantity on each.</span></span> <span data-ttu-id="89c5a-113">A dolgozó konszolidálni szeretné a mennyiséget azzal, hogy mindhárom helyről egy helyre viszi a cikkeket, azonos azonosítótábla alá.</span><span class="sxs-lookup"><span data-stu-id="89c5a-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="89c5a-114">3. eset</span><span class="sxs-lookup"><span data-stu-id="89c5a-114">Scenario 3</span></span>

<span data-ttu-id="89c5a-115">Egy raklap szállításra vár egy előkészítő helyen, például a STAGE01 helyen, amely a BAYDOOR01 közelében van.</span><span class="sxs-lookup"><span data-stu-id="89c5a-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="89c5a-116">Azonban a tervek módosítása miatt a teherautó érkezése a BAYDOOR04 területre van ütemezve.</span><span class="sxs-lookup"><span data-stu-id="89c5a-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="89c5a-117">A szállítási adminisztrátor tud erről, és biztosítania kell, hogy a teherautónak ne kelljen várnia a berakodásra a STAGE01 területről.</span><span class="sxs-lookup"><span data-stu-id="89c5a-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="89c5a-118">A szállítási adminisztrátor úgy dönt, hogy a szállítmányhoz tartozó cikkeket át kell helyezni a STAGE01 területről az új célhoz közelebbi STAGE04 területre.</span><span class="sxs-lookup"><span data-stu-id="89c5a-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="89c5a-119">Jelenlegi korlátozások</span><span class="sxs-lookup"><span data-stu-id="89c5a-119">Current limitations</span></span>

<span data-ttu-id="89c5a-120">Az áthelyezhető munkafoglalások a következőkre korlátoznak: értékesítési rendelés, átmozgatási rendelés kiadása, átmozgatási rendelés – bevételezés, beszerzési rendelés és feltöltési munka.</span><span class="sxs-lookup"><span data-stu-id="89c5a-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="89c5a-121">A cikkek áthelyezése korlátozott a munkasorok felosztásának megakadályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="89c5a-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="89c5a-122">Ez azt jelenti, hogy ha van egy munkasorunk 100 darabra az A cikkből a Loc1 helyről, nem lehet csak 30 darabot áthelyezni az A cikkből innen egy másik helyre.</span><span class="sxs-lookup"><span data-stu-id="89c5a-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="89c5a-123">Ez a meglévő munkasor felosztását eredményezné 30 és 70 cikkre, mivel most már más a hely.</span><span class="sxs-lookup"><span data-stu-id="89c5a-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="89c5a-124">Az előkészítési esetekben, amikor az azonosítótábla, amelyről vagy amelyre áthelyezzük a cikkeket, a munkarendelés cél azonosítótáblájaként van beállítva, csak a teljes azonosítótábla mozgása engedélyezett, hogy ne legyen felbontva a cél azonosítótábla.</span><span class="sxs-lookup"><span data-stu-id="89c5a-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>

<span data-ttu-id="89c5a-125">Jelenleg csak az ad hoc mozgás támogatott.</span><span class="sxs-lookup"><span data-stu-id="89c5a-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="89c5a-126">Ez azt jelenti, hogy nem lehet mozgatni a foglalt készletet a mozgás sablon szerint mobileszközmenü-elemekkel.</span><span class="sxs-lookup"><span data-stu-id="89c5a-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="89c5a-127">Engedély beállítása az egyes dolgozók számára a lefoglalt készlet mozgatásához</span><span class="sxs-lookup"><span data-stu-id="89c5a-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="89c5a-128">Annak a dolgozónak az esetében, akinek a számára engedélyezett a foglalt készlet mozgatása, jelölje be a **Készlet mozgatásának engedélyezése társított munkával** jelölőnégyzetet a következő helyen: **Raktárkezelés \> Beállítás \> Dolgozó**.</span><span class="sxs-lookup"><span data-stu-id="89c5a-128">For the worker who is allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management \> Setup \> Worker**.</span></span>  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

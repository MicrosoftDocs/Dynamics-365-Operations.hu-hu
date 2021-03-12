---
title: Foglalások a raktárkezelési modulban – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári foglalási munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a1ea23059d56ebf387a95a1378e2a3cd47556d5f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993863"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="36f5a-103">Foglalások a raktárkezelési modulban – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="36f5a-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36f5a-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári foglalási munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="36f5a-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="36f5a-105">A következő hibaüzenet jelenik meg: „Foglalások nem távolíthatók el, mert van olyan munkafolyamat, amely a foglalásokon alapul”.</span><span class="sxs-lookup"><span data-stu-id="36f5a-105">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="36f5a-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="36f5a-106">Issue description</span></span>

<span data-ttu-id="36f5a-107">Egy értékesítési sorban nem lehet lefoglalni a készletet, mert nyitott munka van a sornál.</span><span class="sxs-lookup"><span data-stu-id="36f5a-107">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="36f5a-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="36f5a-108">Issue resolution</span></span>

<span data-ttu-id="36f5a-109">Vizsgálja meg, hogy nyitott csomagolási csoportmunka létrezik-e, hogy a cikkeket egy csomagoló állomástól egy másik helyre (például *Baydoor*) vigye.</span><span class="sxs-lookup"><span data-stu-id="36f5a-109">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="36f5a-110">A **Munkalétrehozási előzmények naplója** és **Munkarészletek** lapján található rekordok áttekintésével határozza meg, hogy mi a készlet tényleges foglalása, majd töltse ki vagy törölje a foglalást kiadó munkát.</span><span class="sxs-lookup"><span data-stu-id="36f5a-110">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="36f5a-111">A következő hibaüzenet jelenik meg: „Készletmennyiség –%1 nem lehet frissíteni a cikkhez elégtelen készlettranzakciók miatt %2...”</span><span class="sxs-lookup"><span data-stu-id="36f5a-111">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="36f5a-112">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="36f5a-112">Issue description</span></span>

<span data-ttu-id="36f5a-113">Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="36f5a-113">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="36f5a-114">Íme a hibaüzenet teljes szövege:</span><span class="sxs-lookup"><span data-stu-id="36f5a-114">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="36f5a-115">„Készletmennyiség –%1 nem lehet frissíteni a cikkhez elégtelen készlettranzakciók miatt %2 a következő méretekkel: Méret=%3, Szí=%4, Kiegészítések=%5, Telephely=%6, Raktár=%7, Hely=%8, Készletállapot=Elérhető, Azonosítótábla=%9, Kötegszám=%10 referenciaazonosítónak %11 a tételazonosítóhoz %12.</span><span class="sxs-lookup"><span data-stu-id="36f5a-115">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="36f5a-116">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="36f5a-116">Issue resolution</span></span>

<span data-ttu-id="36f5a-117">Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="36f5a-117">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="36f5a-118">Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.</span><span class="sxs-lookup"><span data-stu-id="36f5a-118">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="36f5a-119">A következő hibaüzenet jelenik meg: „Tényleges aktuális készlet... nem foglalható le, mert csak 0,00 érhető el a készletben."</span><span class="sxs-lookup"><span data-stu-id="36f5a-119">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="36f5a-120">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="36f5a-120">Issue description</span></span>

<span data-ttu-id="36f5a-121">Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="36f5a-121">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="36f5a-122">Íme a hibaüzenet teljes szövege:</span><span class="sxs-lookup"><span data-stu-id="36f5a-122">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="36f5a-123">Tényleges aktuális Telephely=%1, Raktár=%2, Készletállapot=Elérhető, Kötegszám=%3, Tulajdonos=%4: %5 nem foglalható le, mert csak 0,00 érhető el a készletben.</span><span class="sxs-lookup"><span data-stu-id="36f5a-123">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="36f5a-124">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="36f5a-124">Issue resolution</span></span>

<span data-ttu-id="36f5a-125">Ezt a problémát valószínűleg a nyitott munka okozza.</span><span class="sxs-lookup"><span data-stu-id="36f5a-125">This issue is probably caused by open work.</span></span> <span data-ttu-id="36f5a-126">Vagy hajtsa végre a munkát vagy fogadja a munka létrehozása nélkül.</span><span class="sxs-lookup"><span data-stu-id="36f5a-126">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="36f5a-127">Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="36f5a-127">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="36f5a-128">Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.</span><span class="sxs-lookup"><span data-stu-id="36f5a-128">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="36f5a-129">A következő hibaüzenet jelenik meg: „A hullámhoz hozzárendelni kívánt soroknak meg kell adni a hely fölötti dimenzióit.</span><span class="sxs-lookup"><span data-stu-id="36f5a-129">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="36f5a-130">Ezeknek a dimenzióknak a hozzárendeléséhez foglalja le és hozza létre újból a rakománysort.”</span><span class="sxs-lookup"><span data-stu-id="36f5a-130">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="36f5a-131">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="36f5a-131">Issue description</span></span>

<span data-ttu-id="36f5a-132">Ha olyan cikket használ, amelyben a „köteg felett” foglalási hierarchia szerepel (a **Hely** dimenzió *fölött* megadott **Kötegszám** dimenzióval), akkor a részleges mennyiséghez tartozó **Rakománytervezési** munkaterület lap **Kiadás a raktárba** parancsa nem használható.</span><span class="sxs-lookup"><span data-stu-id="36f5a-132">When you use an item that has a "batch above" reservation hierarchy (with the **Batch number** dimension placed *above* the **Location** dimension), the **Release to warehouse** command on the **Load planning workbench** page for a partial quantity doesn't work.</span></span> <span data-ttu-id="36f5a-133">Ez a hibaüzenet jelenik meg, és a rendszer nem hoz létre munkát a részleges mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="36f5a-133">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="36f5a-134">Azonban ha olyan cikket használ, amelyben a „köteg alatt” foglalási hierarchia szerepel (a **Hely** dimenzió *alatt* megadott **Kötegszám** dimenzióval), akkor a részleges mennyiséghez tartozó **Rakománytervezési munkaterület** lapról kiadhatja a rakományt.</span><span class="sxs-lookup"><span data-stu-id="36f5a-134">However, if you use an item that has a "batch below" reservation hierarchy (with the **Batch number** dimension placed *below* the **Location** dimension), you can release a load from the **Load planning workbench** page for a partial quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="36f5a-135">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="36f5a-135">Issue resolution</span></span>

<span data-ttu-id="36f5a-136">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="36f5a-136">This behavior is by design.</span></span> <span data-ttu-id="36f5a-137">Ha a foglalási hierarchiában a **Hely** dimenzió felett helyez fel egy dimenziót, akkor azt a raktárba történő kiadás előtt meg kell határozni.</span><span class="sxs-lookup"><span data-stu-id="36f5a-137">If you put a dimension above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="36f5a-138">A Microsoft kiértékelte ezt a hibát, és azt állapította meg, hogy a rakománytervezési munkaterületről a raktárba történő kiadások jellemzően korlátozást jelentenek.</span><span class="sxs-lookup"><span data-stu-id="36f5a-138">Microsoft has evaluated this issue and has determined that it's a feature limitation during releases to the warehouse from the load planning workbench.</span></span> <span data-ttu-id="36f5a-139">A részleges mennyiségek nem adhatók ki, ha a **Hely** fölötti egy vagy több dimenzió nincs meghatározva.</span><span class="sxs-lookup"><span data-stu-id="36f5a-139">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

<span data-ttu-id="36f5a-140">További információ: [Rugalmas raktárszintű dimenzió foglalási irányelv](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="36f5a-140">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>

---
title: Foglalások a raktárkezelési modulban – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári foglalási munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828106"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="3a43b-103">Foglalások a raktárkezelési modulban – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="3a43b-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a43b-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári foglalási munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="3a43b-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="3a43b-105">A köteg- és sorozatszám-regisztrációkhoz kapcsolódó témakörökért lásd: [Raktár kötegelési és sorozatszám-foglalási hierarchiáinak hibaelhárítása](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="3a43b-105">For topics that are related to batch and serial number registrations, see [Troubleshoot warehouse batch and serial reservation hierarchies](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="3a43b-106">A következő hibaüzenet jelenik meg: „Foglalások nem távolíthatók el, mert van olyan munkafolyamat, amely a foglalásokon alapul”.</span><span class="sxs-lookup"><span data-stu-id="3a43b-106">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a43b-107">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="3a43b-107">Issue description</span></span>

<span data-ttu-id="3a43b-108">Egy értékesítési sorban nem lehet lefoglalni a készletet, mert nyitott munka van a sornál.</span><span class="sxs-lookup"><span data-stu-id="3a43b-108">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a43b-109">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="3a43b-109">Issue resolution</span></span>

<span data-ttu-id="3a43b-110">Vizsgálja meg, hogy nyitott csomagolási csoportmunka létrezik-e, hogy a cikkeket egy csomagoló állomástól egy másik helyre (például *Baydoor*) vigye.</span><span class="sxs-lookup"><span data-stu-id="3a43b-110">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="3a43b-111">A **Munkalétrehozási előzmények naplója** és **Munkarészletek** lapján található rekordok áttekintésével határozza meg, hogy mi a készlet tényleges foglalása, majd töltse ki vagy törölje a foglalást kiadó munkát.</span><span class="sxs-lookup"><span data-stu-id="3a43b-111">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="3a43b-112">A következő hibaüzenet jelenik meg: „Készletmennyiség –%1 nem lehet frissíteni a cikkhez elégtelen készlettranzakciók miatt %2...”</span><span class="sxs-lookup"><span data-stu-id="3a43b-112">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a43b-113">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="3a43b-113">Issue description</span></span>

<span data-ttu-id="3a43b-114">Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="3a43b-114">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="3a43b-115">Íme a hibaüzenet teljes szövege:</span><span class="sxs-lookup"><span data-stu-id="3a43b-115">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="3a43b-116">„Készletmennyiség –%1 nem lehet frissíteni a cikkhez elégtelen készlettranzakciók miatt %2 a következő méretekkel: Méret=%3, Szí=%4, Kiegészítések=%5, Telephely=%6, Raktár=%7, Hely=%8, Készletállapot=Elérhető, Azonosítótábla=%9, Kötegszám=%10 referenciaazonosítónak %11 a tételazonosítóhoz %12.</span><span class="sxs-lookup"><span data-stu-id="3a43b-116">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a43b-117">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="3a43b-117">Issue resolution</span></span>

<span data-ttu-id="3a43b-118">Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="3a43b-118">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="3a43b-119">Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.</span><span class="sxs-lookup"><span data-stu-id="3a43b-119">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="3a43b-120">A következő hibaüzenet jelenik meg: „Tényleges aktuális készlet... nem foglalható le, mert csak 0,00 érhető el a készletben."</span><span class="sxs-lookup"><span data-stu-id="3a43b-120">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a43b-121">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="3a43b-121">Issue description</span></span>

<span data-ttu-id="3a43b-122">Ez a probléma akkor fordulhat elő, ha a rendszer nem tudja frissíteni a készlet mennyiségét, mivel nincs elég készlettranzakció a megadott dimenziókhoz.</span><span class="sxs-lookup"><span data-stu-id="3a43b-122">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="3a43b-123">Íme a hibaüzenet teljes szövege:</span><span class="sxs-lookup"><span data-stu-id="3a43b-123">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="3a43b-124">Tényleges aktuális Telephely=%1, Raktár=%2, Készletállapot=Elérhető, Kötegszám=%3, Tulajdonos=%4: %5 nem foglalható le, mert csak 0,00 érhető el a készletben.</span><span class="sxs-lookup"><span data-stu-id="3a43b-124">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a43b-125">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="3a43b-125">Issue resolution</span></span>

<span data-ttu-id="3a43b-126">Ezt a problémát valószínűleg a nyitott munka okozza.</span><span class="sxs-lookup"><span data-stu-id="3a43b-126">This issue is probably caused by open work.</span></span> <span data-ttu-id="3a43b-127">Vagy hajtsa végre a munkát vagy fogadja a munka létrehozása nélkül.</span><span class="sxs-lookup"><span data-stu-id="3a43b-127">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="3a43b-128">Győződjön meg arról, hogy a készlettranzakciók ténylegesen nem foglalnak mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="3a43b-128">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="3a43b-129">Előfordulhat például, hogy ezek a tranzakciók nyitott minőségi rendelések, készletzároló rekordok vagy kimenő rendelések.</span><span class="sxs-lookup"><span data-stu-id="3a43b-129">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

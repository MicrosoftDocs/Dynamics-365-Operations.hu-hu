---
title: Készlet számlálása egy raktárban
description: Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c0bbfe8f86d27f81b0d577ed89dfa34ebcf3f18
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549902"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="095e8-103">Készlet számlálása egy raktárban</span><span class="sxs-lookup"><span data-stu-id="095e8-103">Count inventory in a warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="095e8-104">Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához.</span><span class="sxs-lookup"><span data-stu-id="095e8-104">This procedure walks you through the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="095e8-105">Ez az eljárás az „alapvető raktározás” szolgáltatásra vonatkozik, amely a Készletgazdálkodás modul része, és nem a „raktározás” szolgáltatásra, amely a Raktárkezelés modul része.</span><span class="sxs-lookup"><span data-stu-id="095e8-105">The procedure applies to “basic warehousing” functionality, available in the Inventory management module, not to the warehousing functionality that’s available in the Warehouse management module.</span></span> <span data-ttu-id="095e8-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="095e8-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="095e8-107">Ha a saját adatait használja, ügyeljen rá, hogy legyenek beállított termékek és helyek, és hogy létrehozzon egy készletnaplónevet a leltárnaplókhoz.</span><span class="sxs-lookup"><span data-stu-id="095e8-107">If you’re using your own data, make sure that you have products and locations set up, and that you’ve created an inventory journal name for counting journals.</span></span> <span data-ttu-id="095e8-108">A készletleltározást általában egy raktári alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="095e8-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="095e8-109">Készletleltározási napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="095e8-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="095e8-110">Lépjen a Készletgazdálkodás > Naplóbejegyzések > Cikkleltár > Leltár menüpontba.</span><span class="sxs-lookup"><span data-stu-id="095e8-110">Go to Inventory management > Journal entries > Item counting > Counting.</span></span>
2. <span data-ttu-id="095e8-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="095e8-111">Click New.</span></span>
3. <span data-ttu-id="095e8-112">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="095e8-112">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="095e8-113">A listában kattintson a készletleltározási naplónévre, amelyet használni kíván.</span><span class="sxs-lookup"><span data-stu-id="095e8-113">In the list, click on the inventory counting journal name you want to use</span></span>
    * <span data-ttu-id="095e8-114">Ki lesz töltve néhány más mező a kiválasztott készletleltározási naplónév beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="095e8-114">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
5. <span data-ttu-id="095e8-115">A Dolgozó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="095e8-115">In the Worker field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="095e8-116">A listából válassza ki a használni kívánt dolgozót.</span><span class="sxs-lookup"><span data-stu-id="095e8-116">In the list, select the worker you want to use.</span></span>
7. <span data-ttu-id="095e8-117">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="095e8-117">Click Select.</span></span>
8. <span data-ttu-id="095e8-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="095e8-118">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="095e8-119">Naplósorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="095e8-119">Create journal lines</span></span>
1. <span data-ttu-id="095e8-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="095e8-120">Click New.</span></span>
2. <span data-ttu-id="095e8-121">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="095e8-121">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="095e8-122">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="095e8-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="095e8-123">Az USMF bemutatócég használata esetén válassza az „A0001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="095e8-123">If you are using demo data company USMF, select 'A0001'.</span></span>  
4. <span data-ttu-id="095e8-124">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="095e8-124">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="095e8-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="095e8-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="095e8-126">Az USMF bemutatócég használata esetén válassza a2 „2” telephelyet.</span><span class="sxs-lookup"><span data-stu-id="095e8-126">If you are using demo data company USMF, select site '2'.</span></span>  
6. <span data-ttu-id="095e8-127">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="095e8-127">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="095e8-128">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="095e8-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="095e8-129">Az USMF bemutatócég használata esetén válassza az „24” raktárat.</span><span class="sxs-lookup"><span data-stu-id="095e8-129">If you are using demo data company USMF, select warehouse '24'.</span></span>  
8. <span data-ttu-id="095e8-130">A Hely mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="095e8-130">In the Location field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="095e8-131">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="095e8-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="095e8-132">Az USMF bemutatócég használata esetén válassza az „BULK-001” helyet</span><span class="sxs-lookup"><span data-stu-id="095e8-132">If you are using demo data company USMF, select location 'BULK-001'</span></span>  
10. <span data-ttu-id="095e8-133">Adjon meg egy számot a Leltározva mezőben.</span><span class="sxs-lookup"><span data-stu-id="095e8-133">In the Counted field, enter a number.</span></span>
    * <span data-ttu-id="095e8-134">Ha olyan megszámolt darabszámot ír be, amely különbözik az Aktuális készlet mezőben láthatótól, akkor a Mennyiség mező frissül, hogy mutassa az értékeltérést.</span><span class="sxs-lookup"><span data-stu-id="095e8-134">If you enter a counted number that’s different to the number shown in the On-hand field, the Quantity field is updated to show the discrepancy.</span></span>  
11. <span data-ttu-id="095e8-135">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="095e8-135">Click Save.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="095e8-136">Készletleltározási napló feladása</span><span class="sxs-lookup"><span data-stu-id="095e8-136">Post the inventory counting journal</span></span>
1. <span data-ttu-id="095e8-137">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="095e8-137">Click Post.</span></span>
    * <span data-ttu-id="095e8-138">Készletleltározási napló feladásakor, ha a megszámolt darabszám különbözik az Aktuális készlet mezőben láthatótól, feladásra kerül egy készletbevétel vagy -kiadás, módosul a készletszint és a készletérték, és főkönyvi tranzakciók jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="095e8-138">When you post an inventory counting journal, if the counted amount differs from amount that’s reported in the On-hand field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
2. <span data-ttu-id="095e8-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="095e8-139">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="095e8-140">Készlettranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="095e8-140">View inventory transactions</span></span>
1. <span data-ttu-id="095e8-141">Kattintson a Készlet parancsra.</span><span class="sxs-lookup"><span data-stu-id="095e8-141">Click Inventory.</span></span>
2. <span data-ttu-id="095e8-142">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="095e8-142">Click Transactions.</span></span>
    * <span data-ttu-id="095e8-143">Itt láthatók a kapcsolódó tranzakciók, amelyek a készletleltározási napló feladásakor jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="095e8-143">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   


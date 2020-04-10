---
title: Készlet számlálása egy raktárban
description: Ez a témakör leírja azt a folyamatot amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 53e9457074b696efaf5958b3a3b4616f06f5a6ff
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145760"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="37443-103">Készlet számlálása egy raktárban</span><span class="sxs-lookup"><span data-stu-id="37443-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="37443-104">Ez a témakör leírja azt a folyamatot amellyel létrehozható és feladható egy készletleltározási napló a raktárban egy adott helyen található konkrét cikk leltározásához.</span><span class="sxs-lookup"><span data-stu-id="37443-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="37443-105">Ez az eljárás az „alapvető raktározás” szolgáltatásra vonatkozik, amely a Készletgazdálkodás modul része, és nem a „raktározás” szolgáltatásra, amely a Raktárkezelés modul része.</span><span class="sxs-lookup"><span data-stu-id="37443-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="37443-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="37443-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="37443-107">Ha a saját adatait használja, ügyeljen rá, hogy legyenek beállított termékek és helyek, és hogy létrehozzon egy készletnaplónevet a leltárnaplókhoz.</span><span class="sxs-lookup"><span data-stu-id="37443-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="37443-108">A készletleltározást általában egy raktári alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="37443-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="37443-109">Készletleltározási napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="37443-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="37443-110">Lépjen a **Navigációs panel > Modulok >Készletgazdálkodás > Naplóbejegyzések > Cikkleltár > Leltár** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="37443-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="37443-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-111">Select **New**.</span></span>
3. <span data-ttu-id="37443-112">A **Név** mezőben válassza ki a használni kívánt készletleltár-napló nevét a legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="37443-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="37443-113">Ki lesz töltve néhány más mező a kiválasztott készletleltározási naplónév beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="37443-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="37443-114">A **Dolgozó** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="37443-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="37443-115">A listából **Válassza ki** a használni kívánt dolgozót.</span><span class="sxs-lookup"><span data-stu-id="37443-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="37443-116">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="37443-117">Naplósorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="37443-117">Create journal lines</span></span>
1. <span data-ttu-id="37443-118">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-118">Select **New**.</span></span>
2. <span data-ttu-id="37443-119">A **Cikkszám** mezőben válassza ki a kívánt rekordot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="37443-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="37443-120">Az USMF bemutatócég használata esetén válassza az **A0001** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="37443-121">A **Hely** mezőben válassza ki a kívánt rekordot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="37443-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="37443-122">Az USMF bemutatócég használata esetén válassza a **2** telephelyet.</span><span class="sxs-lookup"><span data-stu-id="37443-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="37443-123">A **Raktár** mezőben válassza ki a kívánt rekordot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="37443-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="37443-124">Az USMF bemutatócég használata esetén válassza az **24** raktárat.</span><span class="sxs-lookup"><span data-stu-id="37443-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="37443-125">A **Hely** mezőben válassza ki a kívánt rekordot a legördülő listából.</span><span class="sxs-lookup"><span data-stu-id="37443-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="37443-126">Az USMF bemutatócég használata esetén válassza a **BULK-001** helyet</span><span class="sxs-lookup"><span data-stu-id="37443-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="37443-127">Adjon meg egy számot a Leltározva mezőben.</span><span class="sxs-lookup"><span data-stu-id="37443-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="37443-128">Ha olyan megszámolt darabszámot ír be, amely különbözik az **Aktuális készlet** mezőben láthatótól, akkor a **Mennyiség** mező frissül, hogy mutassa az értékeltérést.</span><span class="sxs-lookup"><span data-stu-id="37443-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="37443-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="37443-130">Készletleltározási napló feladása</span><span class="sxs-lookup"><span data-stu-id="37443-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="37443-131">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="37443-131">Select **Post**.</span></span> <span data-ttu-id="37443-132">Készletleltározási napló feladásakor, ha a megszámolt darabszám különbözik az **Aktuális készlet** mezőben láthatótól, feladásra kerül egy készletbevétel vagy -kiadás, módosul a készletszint és a készletérték, és főkönyvi tranzakciók jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="37443-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="37443-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="37443-134">Készlettranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="37443-134">View inventory transactions</span></span>
1. <span data-ttu-id="37443-135">Válassza a **Készlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="37443-136">Válassza a **Tranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="37443-136">Select **Transactions**.</span></span> <span data-ttu-id="37443-137">Itt láthatók a kapcsolódó tranzakciók, amelyek a készletleltározási napló feladásakor jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="37443-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   


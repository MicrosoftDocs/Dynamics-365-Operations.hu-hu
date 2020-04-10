---
title: Készletkövetési információk helyesbítése
description: Ez az eljárás végigvezeti a készletátviteli napló feladási létrehozásának folyamatán, hogy képes legyen készletkövetési információk javítására.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5155ada23fe4f559c79964e6bd10d86712009d1d
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145772"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="8c713-103">Készletkövetési információk helyesbítése</span><span class="sxs-lookup"><span data-stu-id="8c713-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8c713-104">Ez az eljárás végigvezeti a készletátviteli napló feladási létrehozásának folyamatán, hogy képes legyen készletkövetési információk javítására.</span><span class="sxs-lookup"><span data-stu-id="8c713-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="8c713-105">Ebben a példában egy kötegelt ellenőrzött cikk adatait módosítjuk, azza,l hogy megváltoztatunk egy hibásan regisztrált köteget egy másikra.</span><span class="sxs-lookup"><span data-stu-id="8c713-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="8c713-106">Ezt a folyamatot az USPI bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="8c713-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="8c713-107">Saját adatok használatakor rendelkezni kell egy kötegelésre alkalmas cikkel, és nem szabad helyvezéreltnek lennie.</span><span class="sxs-lookup"><span data-stu-id="8c713-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="8c713-108">Először be kell állítani egy készletnaplónevet a készletmozgatáshoz.</span><span class="sxs-lookup"><span data-stu-id="8c713-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="8c713-109">Ezeket a feladatokat általában egy raktári alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="8c713-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="8c713-110">Készletátviteli napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="8c713-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="8c713-111">Ugrás az Áthelyezéshez.</span><span class="sxs-lookup"><span data-stu-id="8c713-111">Go to Transfer.</span></span>
2. <span data-ttu-id="8c713-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8c713-112">Click New.</span></span>
3. <span data-ttu-id="8c713-113">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8c713-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="8c713-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8c713-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="8c713-115">Naplósorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="8c713-115">Create journal lines</span></span>
1. <span data-ttu-id="8c713-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8c713-116">Click New.</span></span>
2. <span data-ttu-id="8c713-117">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8c713-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="8c713-118">Az USPI használata esetén válassza az „M5003” cikket.</span><span class="sxs-lookup"><span data-stu-id="8c713-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="8c713-119">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="8c713-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="8c713-120">Kattintson a Készlet dimenziók lapra.</span><span class="sxs-lookup"><span data-stu-id="8c713-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="8c713-121">A Kötegszám mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8c713-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="8c713-122">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8c713-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="8c713-123">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8c713-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="8c713-124">A Kötegszám mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8c713-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="8c713-125">Napló feladása</span><span class="sxs-lookup"><span data-stu-id="8c713-125">Post the journal</span></span>
1. <span data-ttu-id="8c713-126">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8c713-126">Click Post.</span></span>
2. <span data-ttu-id="8c713-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8c713-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="8c713-128">Nyomkövetési adatok ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="8c713-128">Check tracing information</span></span>
1. <span data-ttu-id="8c713-129">Kattintson a Készlet parancsra.</span><span class="sxs-lookup"><span data-stu-id="8c713-129">Click Inventory.</span></span>
2. <span data-ttu-id="8c713-130">Kattintson a Nyomon követés elemre.</span><span class="sxs-lookup"><span data-stu-id="8c713-130">Click Trace.</span></span>
3. <span data-ttu-id="8c713-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8c713-131">Click OK.</span></span>
    * <span data-ttu-id="8c713-132">A nyomkövetési adatokkal visszakövetheti, hogy melyik kötegből korrigálta a készletet.</span><span class="sxs-lookup"><span data-stu-id="8c713-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="8c713-133">A Cikk-követés lap használatával is megtekintheti ezt az adatot.</span><span class="sxs-lookup"><span data-stu-id="8c713-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="8c713-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8c713-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="8c713-135">Készlettranzakciók ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="8c713-135">Check inventory transactions</span></span>
1. <span data-ttu-id="8c713-136">Kattintson a Készlet parancsra.</span><span class="sxs-lookup"><span data-stu-id="8c713-136">Click Inventory.</span></span>
2. <span data-ttu-id="8c713-137">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="8c713-137">Click Transactions.</span></span>
    * <span data-ttu-id="8c713-138">Itt láthatók a napló feladásakor létrehozott tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="8c713-138">Here you can see the transactions that were created when you posted your journal.</span></span>   


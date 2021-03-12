---
title: Készletkövetési információk helyesbítése
description: Ez az eljárás végigvezeti a készletátviteli napló feladási létrehozásának folyamatán, hogy képes legyen készletkövetési információk javítására.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c70dba7d21eab372cec235efa5a4be19587a409
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000134"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="3d9d9-103">Készletkövetési információk helyesbítése</span><span class="sxs-lookup"><span data-stu-id="3d9d9-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3d9d9-104">Ez az eljárás végigvezeti a készletátviteli napló feladási létrehozásának folyamatán, hogy képes legyen készletkövetési információk javítására.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="3d9d9-105">Ebben a példában egy kötegelt ellenőrzött cikk adatait módosítjuk, azza,l hogy megváltoztatunk egy hibásan regisztrált köteget egy másikra.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="3d9d9-106">Ezt a folyamatot az USPI bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="3d9d9-107">Saját adatok használatakor rendelkezni kell egy kötegelésre alkalmas cikkel, és nem szabad helyvezéreltnek lennie.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="3d9d9-108">Először be kell állítani egy készletnaplónevet a készletmozgatáshoz.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="3d9d9-109">Ezeket a feladatokat általában egy raktári alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="3d9d9-110">Készletátviteli napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="3d9d9-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="3d9d9-111">Ugrás az Áthelyezéshez.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-111">Go to Transfer.</span></span>
2. <span data-ttu-id="3d9d9-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-112">Click New.</span></span>
3. <span data-ttu-id="3d9d9-113">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="3d9d9-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="3d9d9-115">Naplósorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="3d9d9-115">Create journal lines</span></span>
1. <span data-ttu-id="3d9d9-116">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-116">Click New.</span></span>
2. <span data-ttu-id="3d9d9-117">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="3d9d9-118">Az USPI használata esetén válassza az „M5003” cikket.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="3d9d9-119">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="3d9d9-120">Kattintson a Készlet dimenziók lapra.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="3d9d9-121">A Kötegszám mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="3d9d9-122">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="3d9d9-123">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="3d9d9-124">A Kötegszám mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="3d9d9-125">Napló feladása</span><span class="sxs-lookup"><span data-stu-id="3d9d9-125">Post the journal</span></span>
1. <span data-ttu-id="3d9d9-126">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-126">Click Post.</span></span>
2. <span data-ttu-id="3d9d9-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="3d9d9-128">Nyomkövetési adatok ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="3d9d9-128">Check tracing information</span></span>
1. <span data-ttu-id="3d9d9-129">Kattintson a Készlet parancsra.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-129">Click Inventory.</span></span>
2. <span data-ttu-id="3d9d9-130">Kattintson a Nyomon követés elemre.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-130">Click Trace.</span></span>
3. <span data-ttu-id="3d9d9-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-131">Click OK.</span></span>
    * <span data-ttu-id="3d9d9-132">A nyomkövetési adatokkal visszakövetheti, hogy melyik kötegből korrigálta a készletet.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="3d9d9-133">A Cikk-követés lap használatával is megtekintheti ezt az adatot.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="3d9d9-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="3d9d9-135">Készlettranzakciók ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="3d9d9-135">Check inventory transactions</span></span>
1. <span data-ttu-id="3d9d9-136">Kattintson a Készlet parancsra.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-136">Click Inventory.</span></span>
2. <span data-ttu-id="3d9d9-137">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-137">Click Transactions.</span></span>
    * <span data-ttu-id="3d9d9-138">Itt láthatók a napló feladásakor létrehozott tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="3d9d9-138">Here you can see the transactions that were created when you posted your journal.</span></span>   


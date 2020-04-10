---
title: Tényleges készlet áthelyezése a raktáron belül
description: Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 899701413814ce38a4367618ed72d1039eca0bf8
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148170"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="2b903-103">Tényleges készlet áthelyezése a raktáron belül</span><span class="sxs-lookup"><span data-stu-id="2b903-103">Transfer physical inventory within the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2b903-104">Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez.</span><span class="sxs-lookup"><span data-stu-id="2b903-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="2b903-105">Először be kell állítani egy készletnaplónevet a készletmozgatáshoz.</span><span class="sxs-lookup"><span data-stu-id="2b903-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="2b903-106">Végig mehet ezen az eljáráson az USMF bemutatócég esetében a megjelenített példaértékeket használva, vagy használhatja a saját adatait is ha beállított termékeket és helyeket.</span><span class="sxs-lookup"><span data-stu-id="2b903-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="2b903-107">Ezeket a feladatokat általában egy raktári alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="2b903-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="2b903-108">Készletátviteli napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="2b903-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="2b903-109">A **Navigációs ablaktáblán** lépjen a **Készletgazdálkodás > Naplóbejegyzések > Cikkek > Átvitel** elemre.</span><span class="sxs-lookup"><span data-stu-id="2b903-109">In the **Navigation pane**, go to **Inventory management > Journal entries > Items > Transfer**.</span></span>
2. <span data-ttu-id="2b903-110">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="2b903-110">Click **New**.</span></span>
3. <span data-ttu-id="2b903-111">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="2b903-112">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2b903-112">Click **OK**.</span></span> <span data-ttu-id="2b903-113">Az egyes naplósorok esetében meg lehet adni a „Kezdőérték” és a „Végérték” dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="2b903-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="2b903-114">Ezek a szükségesek ehhez a naplótípushoz.</span><span class="sxs-lookup"><span data-stu-id="2b903-114">These are essential for this journal type.</span></span> <span data-ttu-id="2b903-115">Más szabályokat alkalmazva is lehet cikkeket átszállítani.</span><span class="sxs-lookup"><span data-stu-id="2b903-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="2b903-116">Ebben a példában egy adott raktáron belül fogunk egy cikket átszállítani, egy olyan helyről, ahol azonosítótábla alapján történik a vezérlés egy olyan helyre, ahol nem azonosítótábla alapján.</span><span class="sxs-lookup"><span data-stu-id="2b903-116">In this example we'll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="2b903-117">Naplósorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="2b903-117">Create journal lines</span></span>
1. <span data-ttu-id="2b903-118">A **Naplósorok gyorslapon** kattintson az **Új** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b903-118">Int the **Journal lines fastTab**, click **New**.</span></span>
2. <span data-ttu-id="2b903-119">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-119">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="2b903-120">Az USMF használata esetén választhatja az „A0001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b903-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="2b903-121">A **Forrástelephely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-121">In the **From site** field, enter or select a value.</span></span> <span data-ttu-id="2b903-122">Az USMF használata esetén választhatja az „2” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b903-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="2b903-123">A **Céltelephely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-123">In the **To site** field, enter or select a value.</span></span> <span data-ttu-id="2b903-124">Az USMF használata esetén választhatja az „2” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b903-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="2b903-125">A **Forrásraktár** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-125">In the **From warehouse** field, enter or select a value.</span></span> <span data-ttu-id="2b903-126">Az USMF használata esetén választhatja a „24” lehetőséget</span><span class="sxs-lookup"><span data-stu-id="2b903-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="2b903-127">A **Célraktár** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-127">In the **To warehouse** field, enter or select a value.</span></span> <span data-ttu-id="2b903-128">Az USMF használata esetén választhatja a „24” lehetőséget</span><span class="sxs-lookup"><span data-stu-id="2b903-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="2b903-129">A **Forráshely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-129">In the **From location** field, enter or select a value.</span></span> <span data-ttu-id="2b903-130">Az USMF használata esetén választhatja az „FL-001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b903-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="2b903-131">A **Célhely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-131">In the **To location** field, enter or select a value.</span></span> <span data-ttu-id="2b903-132">Az USMF használata esetén választhatja a „BULK-001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b903-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="2b903-133">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2b903-133">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="2b903-134">A **Sorrészletek** gyorslapon kattintson a **Készletdimenziók** lapra.</span><span class="sxs-lookup"><span data-stu-id="2b903-134">In the **Line details** fastTab, click the **Inventory dimensions** tab.</span></span>
11. <span data-ttu-id="2b903-135">A **Forrás-készletdimenziók** pontban az **Azonosítótábla** mezőben adjon meg vagy válasszon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b903-135">In **From inventory dimensions**, in the **License plate** field, enter or select a value.</span></span> <span data-ttu-id="2b903-136">Az USMF használata esetén választhatja a „24” lehetőséget</span><span class="sxs-lookup"><span data-stu-id="2b903-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="2b903-137">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="2b903-137">Click **Save**.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="2b903-138">Készletátviteli napló feladása</span><span class="sxs-lookup"><span data-stu-id="2b903-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="2b903-139">A **Művelet panelen** kattintson a **Feladás** elemre.</span><span class="sxs-lookup"><span data-stu-id="2b903-139">On the **Action pane**, click **Post**.</span></span>
2. <span data-ttu-id="2b903-140">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="2b903-140">Click **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="2b903-141">Készlettranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="2b903-141">View inventory transactions</span></span>
1. <span data-ttu-id="2b903-142">Kattintson a **Készlet** parancsra.</span><span class="sxs-lookup"><span data-stu-id="2b903-142">Click **Inventory**.</span></span>
2. <span data-ttu-id="2b903-143">Kattintson a **Tranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="2b903-143">Click **Transactions**.</span></span> <span data-ttu-id="2b903-144">Itt láthatók a napló feladásakor létrehozott tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="2b903-144">Here you can see the transactions that were created when you posted your journal.</span></span>  


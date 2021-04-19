---
title: Tényleges készlet áthelyezése a raktáron belül
description: Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez.
author: MarkusFogelberg
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a298f05185f3c81f2fde995e4d731b95a5f8d870
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832106"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="ca091-103">Tényleges készlet áthelyezése a raktáron belül</span><span class="sxs-lookup"><span data-stu-id="ca091-103">Transfer physical inventory within the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca091-104">Ez az eljárás végigvezeti a folyamaton, amellyel létrehozható és feladható egy készletmozgatási napló egy cikk egy adott raktáron belüli átszállításának nyilvántartásba vételéhez.</span><span class="sxs-lookup"><span data-stu-id="ca091-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="ca091-105">Először be kell állítani egy készletnaplónevet a készletmozgatáshoz.</span><span class="sxs-lookup"><span data-stu-id="ca091-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="ca091-106">Végig mehet ezen az eljáráson az USMF bemutatócég esetében a megjelenített példaértékeket használva, vagy használhatja a saját adatait is ha beállított termékeket és helyeket.</span><span class="sxs-lookup"><span data-stu-id="ca091-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="ca091-107">Ezeket a feladatokat általában egy raktári alkalmazott végzi el.</span><span class="sxs-lookup"><span data-stu-id="ca091-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="ca091-108">Készletátviteli napló létrehozása</span><span class="sxs-lookup"><span data-stu-id="ca091-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="ca091-109">A **Navigációs ablaktáblán** lépjen a **Készletgazdálkodás > Naplóbejegyzések > Cikkek > Átvitel** elemre.</span><span class="sxs-lookup"><span data-stu-id="ca091-109">In the **Navigation pane**, go to **Inventory management > Journal entries > Items > Transfer**.</span></span>
2. <span data-ttu-id="ca091-110">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="ca091-110">Click **New**.</span></span>
3. <span data-ttu-id="ca091-111">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="ca091-112">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca091-112">Click **OK**.</span></span> <span data-ttu-id="ca091-113">Az egyes naplósorok esetében meg lehet adni a „Kezdőérték” és a „Végérték” dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="ca091-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="ca091-114">Ezek a szükségesek ehhez a naplótípushoz.</span><span class="sxs-lookup"><span data-stu-id="ca091-114">These are essential for this journal type.</span></span> <span data-ttu-id="ca091-115">Más szabályokat alkalmazva is lehet cikkeket átszállítani.</span><span class="sxs-lookup"><span data-stu-id="ca091-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="ca091-116">Ebben a példában egy adott raktáron belül fogunk egy cikket átszállítani, egy olyan helyről, ahol azonosítótábla alapján történik a vezérlés egy olyan helyre, ahol nem azonosítótábla alapján.</span><span class="sxs-lookup"><span data-stu-id="ca091-116">In this example we'll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="ca091-117">Naplósorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="ca091-117">Create journal lines</span></span>
1. <span data-ttu-id="ca091-118">A **Naplósorok gyorslapon** kattintson az **Új** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ca091-118">Int the **Journal lines fastTab**, click **New**.</span></span>
2. <span data-ttu-id="ca091-119">Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-119">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="ca091-120">Az USMF használata esetén választhatja az „A0001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca091-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="ca091-121">A **Forrástelephely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-121">In the **From site** field, enter or select a value.</span></span> <span data-ttu-id="ca091-122">Az USMF használata esetén választhatja az „2” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca091-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="ca091-123">A **Céltelephely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-123">In the **To site** field, enter or select a value.</span></span> <span data-ttu-id="ca091-124">Az USMF használata esetén választhatja az „2” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca091-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="ca091-125">A **Forrásraktár** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-125">In the **From warehouse** field, enter or select a value.</span></span> <span data-ttu-id="ca091-126">Az USMF használata esetén választhatja a „24” lehetőséget</span><span class="sxs-lookup"><span data-stu-id="ca091-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="ca091-127">A **Célraktár** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-127">In the **To warehouse** field, enter or select a value.</span></span> <span data-ttu-id="ca091-128">Az USMF használata esetén választhatja a „24” lehetőséget</span><span class="sxs-lookup"><span data-stu-id="ca091-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="ca091-129">A **Forráshely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-129">In the **From location** field, enter or select a value.</span></span> <span data-ttu-id="ca091-130">Az USMF használata esetén választhatja az „FL-001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca091-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="ca091-131">A **Célhely** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-131">In the **To location** field, enter or select a value.</span></span> <span data-ttu-id="ca091-132">Az USMF használata esetén választhatja a „BULK-001” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ca091-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="ca091-133">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="ca091-133">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="ca091-134">A **Sorrészletek** gyorslapon kattintson a **Készletdimenziók** lapra.</span><span class="sxs-lookup"><span data-stu-id="ca091-134">In the **Line details** fastTab, click the **Inventory dimensions** tab.</span></span>
11. <span data-ttu-id="ca091-135">A **Forrás-készletdimenziók** pontban az **Azonosítótábla** mezőben adjon meg vagy válasszon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="ca091-135">In **From inventory dimensions**, in the **License plate** field, enter or select a value.</span></span> <span data-ttu-id="ca091-136">Az USMF használata esetén választhatja a „24” lehetőséget</span><span class="sxs-lookup"><span data-stu-id="ca091-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="ca091-137">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca091-137">Click **Save**.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="ca091-138">Készletátviteli napló feladása</span><span class="sxs-lookup"><span data-stu-id="ca091-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="ca091-139">A **Művelet panelen** kattintson a **Feladás** elemre.</span><span class="sxs-lookup"><span data-stu-id="ca091-139">On the **Action Pane**, click **Post**.</span></span>
2. <span data-ttu-id="ca091-140">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="ca091-140">Click **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="ca091-141">Készlettranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="ca091-141">View inventory transactions</span></span>
1. <span data-ttu-id="ca091-142">Kattintson a **Készlet** parancsra.</span><span class="sxs-lookup"><span data-stu-id="ca091-142">Click **Inventory**.</span></span>
2. <span data-ttu-id="ca091-143">Kattintson a **Tranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="ca091-143">Click **Transactions**.</span></span> <span data-ttu-id="ca091-144">Itt láthatók a napló feladásakor létrehozott tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="ca091-144">Here you can see the transactions that were created when you posted your journal.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Online értékesítések és kifizetések feladása
description: Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3bac0cab764436a618fa570901c84ab720dbc86
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140784"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="53b5a-103">Online értékesítések és kifizetések feladása</span><span class="sxs-lookup"><span data-stu-id="53b5a-103">Posting of online sales and payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53b5a-104">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.</span><span class="sxs-lookup"><span data-stu-id="53b5a-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="53b5a-105">Az online értékesítés és fizetések feladása két szakaszból áll.</span><span class="sxs-lookup"><span data-stu-id="53b5a-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="53b5a-106">Az online kereskedelmi tranzakcióadatok lekérése a központból.</span><span class="sxs-lookup"><span data-stu-id="53b5a-106">Pulling the online commerce transaction data in HQ.</span></span>
- <span data-ttu-id="53b5a-107">A rendelések szinkronizálása az értékesítési rendelések központban történő létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="53b5a-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="53b5a-108">Az online tranzakcióadatok lekérése történhet manuálisan, P-feladat futtatásával, vagy ismétlődő kötegelt feladat létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="53b5a-108">Pulling the online transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="53b5a-109">P-feladat manuális futtatása</span><span class="sxs-lookup"><span data-stu-id="53b5a-109">Manually running the P-job</span></span>

1. <span data-ttu-id="53b5a-110">Ugorjon a következő oldalra: Összes munkaterület >Retail és Commerce infromatika pontra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-110">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="53b5a-111">Kattintson az Elosztási ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="53b5a-112">Válassza a P-0001 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="53b5a-112">Select P-0001.</span></span>
4. <span data-ttu-id="53b5a-113">Szükség esetén módosítsa a csatorna-adatbázis-csoportokat.</span><span class="sxs-lookup"><span data-stu-id="53b5a-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="53b5a-114">Kattintson a Futtatás most elemre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-114">Click Run now.</span></span>
6. <span data-ttu-id="53b5a-115">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="53b5a-116">Ismétlődő P-feladat ütemezése</span><span class="sxs-lookup"><span data-stu-id="53b5a-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="53b5a-117">Ugorjon a következő oldalra: Összes munkaterület >Retail és Commerce infromatika pontra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-117">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="53b5a-118">Kattintson az Elosztási ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="53b5a-119">Válassza a P-0001 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="53b5a-119">Select P-0001.</span></span>
4. <span data-ttu-id="53b5a-120">Kattintson a Kötegelt feladat létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-120">Click Create batch job.</span></span>
5. <span data-ttu-id="53b5a-121">Kattintson a Futtatás a háttérben elemre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-121">Click Run in the background.</span></span>
5. <span data-ttu-id="53b5a-122">Engedélyezze a Kötegelt feldolgozást.</span><span class="sxs-lookup"><span data-stu-id="53b5a-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="53b5a-123">Kattintson az Ismétlődés elemre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-123">Click Recurrence..</span></span>
7. <span data-ttu-id="53b5a-124">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="53b5a-124">Select the No end date option.</span></span>
8. <span data-ttu-id="53b5a-125">A Szám mezőbe írja be a futások közötti időszakot (percben).</span><span class="sxs-lookup"><span data-stu-id="53b5a-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="53b5a-126">Ez általában 5-10 perc.</span><span class="sxs-lookup"><span data-stu-id="53b5a-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="53b5a-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-127">Click OK.</span></span>
10. <span data-ttu-id="53b5a-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-128">Click OK.</span></span>

<span data-ttu-id="53b5a-129">A rendelések vagy manuálisan, a „Rendelések szinkronizálása” feladat futtatásával, vagy ismétlődő kötegelt feladat létrehozásával szinkronizálhatók.</span><span class="sxs-lookup"><span data-stu-id="53b5a-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="53b5a-130">A rendelés szinkronizálásának manuális futtatása</span><span class="sxs-lookup"><span data-stu-id="53b5a-130">Manually running order synchronization</span></span> 

<span data-ttu-id="53b5a-131">A „Rendelések szinkronizálása” feladat manuális futtatásához hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="53b5a-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="53b5a-132">Ugorjon az Összes munkaterület > Áruház pénzügyei oldalra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-132">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="53b5a-133">Kattintson Rendelések szinkronizálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="53b5a-134">A Szervezeti hierarchia mezőben válassza ki a „Áruházak régiók szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="53b5a-134">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="53b5a-135">Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="53b5a-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="53b5a-136">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="53b5a-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="53b5a-137">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="53b5a-138">A kötegelt feldolgozás letiltása</span><span class="sxs-lookup"><span data-stu-id="53b5a-138">Disable Batch processing</span></span>
6. <span data-ttu-id="53b5a-139">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-139">Click Recurrence.</span></span>
7. <span data-ttu-id="53b5a-140">Adja meg a Befejezés ezt követően beállítást</span><span class="sxs-lookup"><span data-stu-id="53b5a-140">Select End After option</span></span>
8. <span data-ttu-id="53b5a-141">A Befejezés ezt követően mezőbe írja be az 1 értéket.</span><span class="sxs-lookup"><span data-stu-id="53b5a-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="53b5a-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-142">Click OK.</span></span>
10. <span data-ttu-id="53b5a-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="53b5a-144">Ismétlődő rendelés szinkronizálásának ütemezése</span><span class="sxs-lookup"><span data-stu-id="53b5a-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="53b5a-145">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.</span><span class="sxs-lookup"><span data-stu-id="53b5a-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="53b5a-146">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="53b5a-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="53b5a-147">Ugorjon az Összes munkaterület > Áruház pénzügyei oldalra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-147">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="53b5a-148">Kattintson Rendelések szinkronizálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="53b5a-149">A Szervezeti hierarchia mezőben válassza ki a „Áruházak régiók szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="53b5a-149">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="53b5a-150">Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="53b5a-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="53b5a-151">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="53b5a-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="53b5a-152">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="53b5a-153">Engedélyezze a Kötegelt feldolgozást</span><span class="sxs-lookup"><span data-stu-id="53b5a-153">Enable Batch processing</span></span>
6. <span data-ttu-id="53b5a-154">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="53b5a-154">Click Recurrence.</span></span>
7. <span data-ttu-id="53b5a-155">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="53b5a-155">Select the No end date option.</span></span>
8. <span data-ttu-id="53b5a-156">A Szám mezőbe írja be a futások közötti időszakot (percben).</span><span class="sxs-lookup"><span data-stu-id="53b5a-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="53b5a-157">Ez általában 2-20 perc.</span><span class="sxs-lookup"><span data-stu-id="53b5a-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="53b5a-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-158">Click OK.</span></span>
10. <span data-ttu-id="53b5a-159">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="53b5a-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="53b5a-160">A folyamatban érintett adatentitások</span><span class="sxs-lookup"><span data-stu-id="53b5a-160">Data entities involved in the process</span></span>

- <span data-ttu-id="53b5a-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="53b5a-161">RetailTransactionTable</span></span>
- <span data-ttu-id="53b5a-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="53b5a-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="53b5a-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="53b5a-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="53b5a-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="53b5a-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="53b5a-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="53b5a-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="53b5a-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="53b5a-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="53b5a-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="53b5a-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="53b5a-171">RetailTransactionAttributeTrans</span></span>

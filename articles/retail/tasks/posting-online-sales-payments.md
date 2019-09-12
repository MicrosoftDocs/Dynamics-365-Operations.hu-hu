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
ms.openlocfilehash: 1d42b585a61214628980cd45a859215443ed55b5
ms.sourcegitcommit: c461758290d7ddc19f0b60701368937c35ef78b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864153"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="c51e5-103">Online értékesítések és kifizetések feladása</span><span class="sxs-lookup"><span data-stu-id="c51e5-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="c51e5-104">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.</span><span class="sxs-lookup"><span data-stu-id="c51e5-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="c51e5-105">Az online értékesítés és fizetések feladása két szakaszból áll.</span><span class="sxs-lookup"><span data-stu-id="c51e5-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="c51e5-106">Az online kiskereskedelmi tranzakcióadatok lekérése a központból.</span><span class="sxs-lookup"><span data-stu-id="c51e5-106">Pulling the online retail transaction data in HQ.</span></span>
- <span data-ttu-id="c51e5-107">A rendelések szinkronizálása az értékesítési rendelések központban történő létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c51e5-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="c51e5-108">Az online kiskereskedelmi tranzakcióadatok lekérése történhet manuálisan, P-feladat futtatásával, vagy ismétlődő kötegelt feladat létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="c51e5-108">Pulling the online retail transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="c51e5-109">P-feladat manuális futtatása</span><span class="sxs-lookup"><span data-stu-id="c51e5-109">Manually running the P-job</span></span>

1. <span data-ttu-id="c51e5-110">Ugorjon a következő oldalra: Összes munkaterület > Kiskereskedelmi IT.</span><span class="sxs-lookup"><span data-stu-id="c51e5-110">Go to All workspaces > Retail IT.</span></span>
2. <span data-ttu-id="c51e5-111">Kattintson az Elosztási ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="c51e5-112">Válassza a P-0001 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c51e5-112">Select P-0001.</span></span>
4. <span data-ttu-id="c51e5-113">Szükség esetén módosítsa a csatorna-adatbázis-csoportokat.</span><span class="sxs-lookup"><span data-stu-id="c51e5-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="c51e5-114">Kattintson a Futtatás most elemre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-114">Click Run now.</span></span>
6. <span data-ttu-id="c51e5-115">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="c51e5-116">Ismétlődő P-feladat ütemezése</span><span class="sxs-lookup"><span data-stu-id="c51e5-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="c51e5-117">Ugorjon a következő oldalra: Összes munkaterület > Kiskereskedelmi IT.</span><span class="sxs-lookup"><span data-stu-id="c51e5-117">Go to All workspaces > Retail IT.</span></span>
2. <span data-ttu-id="c51e5-118">Kattintson az Elosztási ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="c51e5-119">Válassza a P-0001 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c51e5-119">Select P-0001.</span></span>
4. <span data-ttu-id="c51e5-120">Kattintson a Kötegelt feladat létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-120">Click Create batch job.</span></span>
5. <span data-ttu-id="c51e5-121">Kattintson a Futtatás a háttérben elemre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-121">Click Run in the background.</span></span>
5. <span data-ttu-id="c51e5-122">Engedélyezze a Kötegelt feldolgozást.</span><span class="sxs-lookup"><span data-stu-id="c51e5-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="c51e5-123">Kattintson az Ismétlődés elemre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-123">Click Recurrence..</span></span>
7. <span data-ttu-id="c51e5-124">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c51e5-124">Select the No end date option.</span></span>
8. <span data-ttu-id="c51e5-125">A Szám mezőbe írja be a futások közötti időszakot (percben).</span><span class="sxs-lookup"><span data-stu-id="c51e5-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="c51e5-126">Ez általában 5-10 perc.</span><span class="sxs-lookup"><span data-stu-id="c51e5-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="c51e5-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-127">Click OK.</span></span>
10. <span data-ttu-id="c51e5-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-128">Click OK.</span></span>

<span data-ttu-id="c51e5-129">A rendelések vagy manuálisan, a „Rendelések szinkronizálása” feladat futtatásával, vagy ismétlődő kötegelt feladat létrehozásával szinkronizálhatók.</span><span class="sxs-lookup"><span data-stu-id="c51e5-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="c51e5-130">A rendelés szinkronizálásának manuális futtatása</span><span class="sxs-lookup"><span data-stu-id="c51e5-130">Manually running order synchronization</span></span> 

<span data-ttu-id="c51e5-131">A „Rendelések szinkronizálása” feladat manuális futtatásához hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c51e5-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="c51e5-132">Ugorjon a következő oldalra: Összes munkaterület > Kiskereskedelmi üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="c51e5-132">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="c51e5-133">Kattintson Rendelések szinkronizálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="c51e5-134">A Szervezeti hierarchia mezőben válassza ki a „Kiskereskedelmi áruházak régiók szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c51e5-134">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="c51e5-135">Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="c51e5-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="c51e5-136">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="c51e5-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="c51e5-137">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="c51e5-138">A kötegelt feldolgozás letiltása</span><span class="sxs-lookup"><span data-stu-id="c51e5-138">Disable Batch processing</span></span>
6. <span data-ttu-id="c51e5-139">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-139">Click Recurrence.</span></span>
7. <span data-ttu-id="c51e5-140">Adja meg a Befejezés ezt követően beállítást</span><span class="sxs-lookup"><span data-stu-id="c51e5-140">Select End After option</span></span>
8. <span data-ttu-id="c51e5-141">A Befejezés ezt követően mezőbe írja be az 1 értéket.</span><span class="sxs-lookup"><span data-stu-id="c51e5-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="c51e5-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-142">Click OK.</span></span>
10. <span data-ttu-id="c51e5-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="c51e5-144">Ismétlődő rendelés szinkronizálásának ütemezése</span><span class="sxs-lookup"><span data-stu-id="c51e5-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="c51e5-145">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.</span><span class="sxs-lookup"><span data-stu-id="c51e5-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="c51e5-146">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="c51e5-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="c51e5-147">Ugorjon a következő oldalra: Összes munkaterület > Kiskereskedelmi üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="c51e5-147">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="c51e5-148">Kattintson Rendelések szinkronizálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="c51e5-149">A Szervezeti hierarchia mezőben válassza ki a „Kiskereskedelmi áruházak régiók szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c51e5-149">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="c51e5-150">Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="c51e5-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="c51e5-151">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="c51e5-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="c51e5-152">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="c51e5-153">Engedélyezze a Kötegelt feldolgozást</span><span class="sxs-lookup"><span data-stu-id="c51e5-153">Enable Batch processing</span></span>
6. <span data-ttu-id="c51e5-154">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="c51e5-154">Click Recurrence.</span></span>
7. <span data-ttu-id="c51e5-155">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c51e5-155">Select the No end date option.</span></span>
8. <span data-ttu-id="c51e5-156">A Szám mezőbe írja be a futások közötti időszakot (percben).</span><span class="sxs-lookup"><span data-stu-id="c51e5-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="c51e5-157">Ez általában 2-20 perc.</span><span class="sxs-lookup"><span data-stu-id="c51e5-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="c51e5-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-158">Click OK.</span></span>
10. <span data-ttu-id="c51e5-159">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c51e5-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="c51e5-160">A folyamatban érintett adatentitások</span><span class="sxs-lookup"><span data-stu-id="c51e5-160">Data entities involved in the process</span></span>

- <span data-ttu-id="c51e5-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="c51e5-161">RetailTransactionTable</span></span>
- <span data-ttu-id="c51e5-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="c51e5-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="c51e5-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="c51e5-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="c51e5-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="c51e5-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="c51e5-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="c51e5-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="c51e5-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="c51e5-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="c51e5-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="c51e5-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="c51e5-171">RetailTransactionAttributeTrans</span></span>

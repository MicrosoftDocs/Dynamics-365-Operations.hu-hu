---
title: A minőség- és a szabálytalanságkezelés engedélyezése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Supply Chain Management minőség- és szabálytalanságkezelési szolgáltatásainak beállításával és konfigurálásával kapcsolatos folyamatról.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956254"
---
# <a name="enable-quality-and-nonconformance-management"></a><span data-ttu-id="afe3e-103">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="afe3e-103">Enable quality and nonconformance management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afe3e-104">Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Supply Chain Management minőség- és szabálytalanságkezelési szolgáltatásainak beállításával és konfigurálásával kapcsolatos folyamatról.</span><span class="sxs-lookup"><span data-stu-id="afe3e-104">This topic provides an overview of the process for setting up and configuring quality and nonconformance management features in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a><span data-ttu-id="afe3e-105">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="afe3e-105">Enable quality and nonconformance management</span></span>

<span data-ttu-id="afe3e-106">A következő lépések elvégzésével engedélyezheti a minőségkezelést a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="afe3e-106">Follow these steps to enable quality management on your system.</span></span>

1. <span data-ttu-id="afe3e-107">Válassz a **Készletkezelés \> Beállítás \> Készlet- és raktárkezelési paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="afe3e-107">Go to **Inventory management \> Setup \> Inventory and warehouse management parameters**.</span></span>
1. <span data-ttu-id="afe3e-108">A **Minőségkezelés** fülön állítsa **Igen** értékre a *Minőségkezelés használata* beállítást.</span><span class="sxs-lookup"><span data-stu-id="afe3e-108">On the **Quality management** tab, set the **Use quality management** option to *Yes*.</span></span>
1. <span data-ttu-id="afe3e-109">Az **Órabér** mezőben adhatja meg az óradíjat, helyi pénznemben.</span><span class="sxs-lookup"><span data-stu-id="afe3e-109">In the **Hourly rate** field, enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="afe3e-110">A rendszer az óradíjjal számítja ki a szabálytalansággal kapcsolatos műveletek költségeit.</span><span class="sxs-lookup"><span data-stu-id="afe3e-110">The hourly rate is used to calculate costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="afe3e-111">Az óradíj és a számított költségek csak a szabálytalanságokra vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="afe3e-111">The hourly rate and calculated costs provide reference information for a nonconformance.</span></span> <span data-ttu-id="afe3e-112">Más funkciókat nem érintenek.</span><span class="sxs-lookup"><span data-stu-id="afe3e-112">They don't interact with other functionality.</span></span>
1. <span data-ttu-id="afe3e-113">Válassza a **Beállítás jelentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="afe3e-113">Select **Report setup**.</span></span>
1. <span data-ttu-id="afe3e-114">Új sorok hozzáadása a különböző jelentéstípusokhoz, és az egyes jelentésekhez használt dokumentumtípus kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="afe3e-114">Add new lines for the various report types, and select the type of document to use for each report.</span></span>
1. <span data-ttu-id="afe3e-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="afe3e-115">Close the page.</span></span>
1. <span data-ttu-id="afe3e-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="afe3e-116">Close the page.</span></span>

## <a name="quality-management-configuration-process"></a><span data-ttu-id="afe3e-117">Minőségkezelési konfiguráció folyamata</span><span class="sxs-lookup"><span data-stu-id="afe3e-117">Quality management configuration process</span></span>

<span data-ttu-id="afe3e-118">Ahhoz, hogy használni tudja a minőségkezelési funkciókat, és minőségi rendeléseket hozzon létre, konfigurálnia kell a rendszert és az előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="afe3e-118">Before you can start to use the quality management features and generate quality orders, you must configure the system and prerequisites.</span></span> <span data-ttu-id="afe3e-119">Az alábbiakban találja a minőségkezelés konfigurálához szükséges lépéseket.</span><span class="sxs-lookup"><span data-stu-id="afe3e-119">Here is a list of the steps that are required to configure quality management.</span></span>

1. <span data-ttu-id="afe3e-120">[A minőség- és a szabálytalanságkezelés engedélyezése](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="afe3e-120">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="afe3e-121">Választható: [Tesztszerek konfigurálása](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-121">Optional: [Configure test instruments](quality-test-instruments.md).</span></span>
1. <span data-ttu-id="afe3e-122">[Tesztek konfigurálása](quality-tests.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-122">[Configure tests](quality-tests.md).</span></span>
1. <span data-ttu-id="afe3e-123">[Tesztváltozók és kimenetelek konfigurálása](quality-test-variables.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-123">[Configure test variables and outcomes](quality-test-variables.md).</span></span>
1. <span data-ttu-id="afe3e-124">[Tesztcsoportok konfigurálása](quality-test-groups.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-124">[Configure test groups](quality-test-groups.md).</span></span>
1. <span data-ttu-id="afe3e-125">Választható: [Állítsa be a minőségi csoportokat, és csatolja hozzájuk a termékeket](quality-groups.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-125">Optional: [Configure quality groups, and link to products](quality-groups.md).</span></span>
1. <span data-ttu-id="afe3e-126">Választható: [Minőségi társítások konfigurálása](quality-associations.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-126">Optional: [Configure quality associations](quality-associations.md).</span></span>

<span data-ttu-id="afe3e-127">A konfiguráció befejezése után elindíthatja és feldolgozhatja a minőségi rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="afe3e-127">After the configuration is completed, you can start to create and process quality orders.</span></span> <span data-ttu-id="afe3e-128">A minőségi rendelések létrehozásával és használatával kapcsolatos további tudnivalókért tanulmányozza a [Minőségi rendelések](quality-orders.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="afe3e-128">For more information about how to create and work with quality orders, see [Quality orders](quality-orders.md).</span></span>

## <a name="nonconformance-management-configuration-process"></a><span data-ttu-id="afe3e-129">Szabálytalanságkezelési konfiguráció folyamata</span><span class="sxs-lookup"><span data-stu-id="afe3e-129">Nonconformance management configuration process</span></span>

<span data-ttu-id="afe3e-130">Ahhoz, hogy használni tudja a szabálytalanságkezelési funkciókat, és szabálytalanságokat hozzon létre, konfigurálnia kell a rendszert és az előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="afe3e-130">Before you can start to use the nonconformance management features and generate nonconformances, you must configure the system and prerequisites.</span></span> <span data-ttu-id="afe3e-131">Az alábbiakban találja a szabálytalanságkezelés konfigurálához szükséges lépéseket.</span><span class="sxs-lookup"><span data-stu-id="afe3e-131">Here is a list of the steps that are required to configure nonconformance management.</span></span>

1. <span data-ttu-id="afe3e-132">[A minőség- és a szabálytalanságkezelés engedélyezése](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="afe3e-132">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="afe3e-133">[A szabálytalanságok jóváhagyásáért felelős dolgozók konfigurálása](quality-responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-133">[Configure workers who are responsible for approving nonconformances](quality-responsible-workers.md).</span></span>
1. <span data-ttu-id="afe3e-134">[Problématípusok konfigurálása](quality-problem-types.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-134">[Configure problem types](quality-problem-types.md).</span></span>
1. <span data-ttu-id="afe3e-135">[Karanténzónák konfigurálása](quality-quarantine-zones.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-135">[Configure quarantine zones](quality-quarantine-zones.md).</span></span>
1. <span data-ttu-id="afe3e-136">[Diagnosztikatípusok konfigurálása](quality-diagnostic-types.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-136">[Configure diagnostic types](quality-diagnostic-types.md).</span></span>
1. <span data-ttu-id="afe3e-137">[Műveletek konfigurálása](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-137">[Configure operations](quality-operations.md).</span></span>
1. <span data-ttu-id="afe3e-138">Választható: [Minőségi költségek konfigurálása](quality-charges.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-138">Optional: [Configure quality charges](quality-charges.md).</span></span>

<span data-ttu-id="afe3e-139">A konfiguráció befejezése után elindíthatja és feldolgozhatja a szabálytalanságokat.</span><span class="sxs-lookup"><span data-stu-id="afe3e-139">After the configuration is completed, you can start to create and process nonconformances.</span></span> <span data-ttu-id="afe3e-140">További információkért a szabálytalanságok létrehozásáról és használatáról lásd: [Szabálytalanságok létrehozása és feldolgozása](tasks/create-process-non-conformance.md).</span><span class="sxs-lookup"><span data-stu-id="afe3e-140">For more information about how to create and work with nonconformances, see [Create and process nonconformances](tasks/create-process-non-conformance.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="afe3e-141">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="afe3e-141">Additional resources</span></span>

- [<span data-ttu-id="afe3e-142">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="afe3e-142">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="afe3e-143">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="afe3e-143">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="afe3e-144">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="afe3e-144">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Áru minőségének ellenőrzése
description: Ez a témakör a minőségi rendelések feldolgozását írja le.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956134"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="8bed0-103">Áru minőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="8bed0-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8bed0-104">Ez a témakör a minőségi rendelések feldolgozását írja le.</span><span class="sxs-lookup"><span data-stu-id="8bed0-104">This topic describes how to process quality orders.</span></span> <span data-ttu-id="8bed0-105">A minőségvizsgálatokat általában minőségadminisztrátorok végzik.</span><span class="sxs-lookup"><span data-stu-id="8bed0-105">Quality inspections are typically done by a quality clerk.</span></span>

<span data-ttu-id="8bed0-106">Ha telepítve vannak a szabványos bemutatóadatok, akkor az ebben a témakörben található eljárásokat lehet használni.</span><span class="sxs-lookup"><span data-stu-id="8bed0-106">If the standard demo data is installed, you can use it to complete the procedures in this topic.</span></span> <span data-ttu-id="8bed0-107">A bemutatóadatok használatához az *USMF* jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="8bed0-107">To use the demo data, select the *USMF* legal entity before you begin.</span></span> <span data-ttu-id="8bed0-108">Ezt követően meg kell erősítenie a *000016-os* beszerzési rendelést, és fel kell adnia egy terméknyugtát.</span><span class="sxs-lookup"><span data-stu-id="8bed0-108">You must then confirm purchase order *000016* and post a product receipt.</span></span> <span data-ttu-id="8bed0-109">A minőségi rendelések automatikusan létre vannak hozva.</span><span class="sxs-lookup"><span data-stu-id="8bed0-109">A quality order is automatically generated.</span></span>

## <a name="step-1-select-a-quality-order"></a><span data-ttu-id="8bed0-110">1. lépés: Minőségi rendelés kiválasztása</span><span class="sxs-lookup"><span data-stu-id="8bed0-110">Step 1: Select a quality order</span></span>

<span data-ttu-id="8bed0-111">A minőségi rendelés kiválasztásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8bed0-111">To select a quality order, follow these steps.</span></span>

1. <span data-ttu-id="8bed0-112">Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8bed0-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="8bed0-113">Válassza ki az eljárás megkezdése előtt létrehozott minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="8bed0-113">Select the quality order that was generated before you started this procedure.</span></span>

## <a name="step-2-record-test-results"></a><span data-ttu-id="8bed0-114">2. lépés: Teszteredmények rögzítése</span><span class="sxs-lookup"><span data-stu-id="8bed0-114">Step 2: Record test results</span></span>

<span data-ttu-id="8bed0-115">A teszteredmények rögzítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8bed0-115">To record test results, follow these steps.</span></span>

1. <span data-ttu-id="8bed0-116">Válassza az **Eredmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8bed0-116">Select **Results**.</span></span>
1. <span data-ttu-id="8bed0-117">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="8bed0-117">Select **Edit**.</span></span>
1. <span data-ttu-id="8bed0-118">Az **Eredmény mennyisége** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="8bed0-118">In the **Result quantity** field, enter a number.</span></span>
1. <span data-ttu-id="8bed0-119">A **Kimenet** mezőben válassza ki a rekordot.</span><span class="sxs-lookup"><span data-stu-id="8bed0-119">In the **Outcome** field, select the desired record.</span></span> <span data-ttu-id="8bed0-120">Ebben a példában az eredmény egy előre meghatározott eredményen alapul.</span><span class="sxs-lookup"><span data-stu-id="8bed0-120">In this example, the result is based on a predefined outcome.</span></span> <span data-ttu-id="8bed0-121">Általában speciálisabb teszteredményeket rögzít majd, például egy méretet vagy más dimenziót.</span><span class="sxs-lookup"><span data-stu-id="8bed0-121">Usually, you will record a more specific test result, such as a size or other dimension.</span></span>
1. <span data-ttu-id="8bed0-122">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8bed0-122">Select **Save**.</span></span>
1. <span data-ttu-id="8bed0-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8bed0-123">Close the page.</span></span>

## <a name="step-3-validate-the-quality-order"></a><span data-ttu-id="8bed0-124">3. lépés: A minőségi rendelés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="8bed0-124">Step 3: Validate the quality order</span></span>

<span data-ttu-id="8bed0-125">A minőségi rendelés ellenőrzéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8bed0-125">To validate the quality order, follow these steps.</span></span>

1. <span data-ttu-id="8bed0-126">A **Validálás** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="8bed0-126">Select **Validate**.</span></span>
1. <span data-ttu-id="8bed0-127">Az **Ellenőrzést végezte** mezőben válassza ki azt a felhasználót, aki az ellenőrzést elvégezte.</span><span class="sxs-lookup"><span data-stu-id="8bed0-127">In the **Validated by** field, select the user who is doing the inspection.</span></span>
1. <span data-ttu-id="8bed0-128">Válassza ki a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8bed0-128">Select **Select**.</span></span>
1. <span data-ttu-id="8bed0-129">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8bed0-129">Select **OK**.</span></span>
1. <span data-ttu-id="8bed0-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8bed0-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

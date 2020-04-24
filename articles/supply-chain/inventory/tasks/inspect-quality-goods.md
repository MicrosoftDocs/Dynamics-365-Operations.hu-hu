---
title: Áru minőségének ellenőrzése
description: Ez a cikk a minőségi rendelések feldolgozását ismerteti.
author: perlynne
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee5f83b2dad60567341f33a73ce63d01e9da8289
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213975"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="59289-103">Áru minőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="59289-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="59289-104">Ez a cikk a minőségi rendelések feldolgozását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="59289-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="59289-105">Ezt az útmutatót lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="59289-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="59289-106">A példaeljárás megkezdése előtt erősítse meg a „000016” beszerzési rendelést, és adja fel a termékbevételezést.</span><span class="sxs-lookup"><span data-stu-id="59289-106">Before you start this example procedure, you need to confirm purchase order "000016" and post a product receipt.</span></span> <span data-ttu-id="59289-107">Ez automatikusan létrehoz egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="59289-107">This will automatically create a quality order.</span></span> <span data-ttu-id="59289-108">A minőségvizsgálatokat általában minőségadminisztrátorok végzik.</span><span class="sxs-lookup"><span data-stu-id="59289-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="59289-109">Minőségi rendelés kiválasztása</span><span class="sxs-lookup"><span data-stu-id="59289-109">Select a quality order</span></span>
1. <span data-ttu-id="59289-110">A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Időszakos feladatok > Minőségkezelés > Minőségi rendelések** részre.</span><span class="sxs-lookup"><span data-stu-id="59289-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="59289-111">Válassza ki az eljárás megkezdése előtt létrehozott minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="59289-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="59289-112">Teszteredmények rögzítése</span><span class="sxs-lookup"><span data-stu-id="59289-112">Record test results</span></span>
1. <span data-ttu-id="59289-113">Válassza az **Eredmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59289-113">Select **Results**.</span></span>
2. <span data-ttu-id="59289-114">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="59289-114">Select **Edit**.</span></span>
3. <span data-ttu-id="59289-115">Az **Eredmény mennyisége** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="59289-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="59289-116">Az **Eredmény** mező legördülő mezőjében válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="59289-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="59289-117">Ebben a példában az eredményt egy előre meghatározott eredmény alapul.</span><span class="sxs-lookup"><span data-stu-id="59289-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="59289-118">Általában speciálisabb teszteredményeket rögzít majd, például egy méretet vagy más dimenziót.</span><span class="sxs-lookup"><span data-stu-id="59289-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="59289-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59289-119">Select **Save**.</span></span>
6. <span data-ttu-id="59289-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="59289-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="59289-121">A minőségi rendelés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="59289-121">Validate the quality order</span></span>
1. <span data-ttu-id="59289-122">A **Validálás**kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="59289-122">Select **Validate**.</span></span>
2. <span data-ttu-id="59289-123">Az **Ellenőrzést végezte** mező legördülő mezőjében válassza ki a vizsgálatot végző felhasználót.</span><span class="sxs-lookup"><span data-stu-id="59289-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="59289-124">Kattintson a **Kiválasztás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="59289-124">Click **Select**.</span></span>
4. <span data-ttu-id="59289-125">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="59289-125">Select **OK**.</span></span>
5. <span data-ttu-id="59289-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="59289-126">Close the page.</span></span>


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
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e37ac8c9320d427b9f9a3ca32b0e4667c7023339
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244423"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="6572f-103">Áru minőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="6572f-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6572f-104">Ez a cikk a minőségi rendelések feldolgozását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="6572f-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="6572f-105">Ezt az útmutatót lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="6572f-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="6572f-106">A példaeljárás megkezdése előtt erősítse meg a „000016” beszerzési rendelést, és adja fel a termékbevételezést.</span><span class="sxs-lookup"><span data-stu-id="6572f-106">Before you start this example procedure, you need to confirm purchase order "000016" and post a product receipt.</span></span> <span data-ttu-id="6572f-107">Ez automatikusan létrehoz egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="6572f-107">This will automatically create a quality order.</span></span> <span data-ttu-id="6572f-108">A minőségvizsgálatokat általában minőségadminisztrátorok végzik.</span><span class="sxs-lookup"><span data-stu-id="6572f-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="6572f-109">Minőségi rendelés kiválasztása</span><span class="sxs-lookup"><span data-stu-id="6572f-109">Select a quality order</span></span>
1. <span data-ttu-id="6572f-110">A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Időszakos feladatok > Minőségkezelés > Minőségi rendelések** részre.</span><span class="sxs-lookup"><span data-stu-id="6572f-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="6572f-111">Válassza ki az eljárás megkezdése előtt létrehozott minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="6572f-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="6572f-112">Teszteredmények rögzítése</span><span class="sxs-lookup"><span data-stu-id="6572f-112">Record test results</span></span>
1. <span data-ttu-id="6572f-113">Válassza az **Eredmények** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6572f-113">Select **Results**.</span></span>
2. <span data-ttu-id="6572f-114">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="6572f-114">Select **Edit**.</span></span>
3. <span data-ttu-id="6572f-115">Az **Eredmény mennyisége** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="6572f-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="6572f-116">Az **Eredmény** mező legördülő mezőjében válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="6572f-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="6572f-117">Ebben a példában az eredményt egy előre meghatározott eredmény alapul.</span><span class="sxs-lookup"><span data-stu-id="6572f-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="6572f-118">Általában speciálisabb teszteredményeket rögzít majd, például egy méretet vagy más dimenziót.</span><span class="sxs-lookup"><span data-stu-id="6572f-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="6572f-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6572f-119">Select **Save**.</span></span>
6. <span data-ttu-id="6572f-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6572f-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="6572f-121">A minőségi rendelés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="6572f-121">Validate the quality order</span></span>
1. <span data-ttu-id="6572f-122">A **Validálás** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="6572f-122">Select **Validate**.</span></span>
2. <span data-ttu-id="6572f-123">Az **Ellenőrzést végezte** mező legördülő mezőjében válassza ki a vizsgálatot végző felhasználót.</span><span class="sxs-lookup"><span data-stu-id="6572f-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="6572f-124">Kattintson a **Kiválasztás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6572f-124">Click **Select**.</span></span>
4. <span data-ttu-id="6572f-125">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6572f-125">Select **OK**.</span></span>
5. <span data-ttu-id="6572f-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6572f-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
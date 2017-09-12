---
title: "Áru minőségének ellenőrzése"
description: "Ez az eljárás bemutatja, hogyan dolgozhat fel egy minőségi rendelést."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: aeed7eab750c606ea0009fa7c51baf96e2f9de51
ms.contentlocale: hu-hu
ms.lasthandoff: 09/12/2017

---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="10a07-103">Áru minőségének ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="10a07-103">Inspect the quality of goods</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10a07-104">Ez az eljárás bemutatja, hogyan dolgozhat fel egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="10a07-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="10a07-105">Ezt az útmutatót lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="10a07-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="10a07-106">A példaeljárás megkezdése előtt erősítse meg a „000016” beszerzési rendelést, és adja fel a termékbevételezést.</span><span class="sxs-lookup"><span data-stu-id="10a07-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="10a07-107">Ez automatikusan létrehoz egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="10a07-107">This will automatically create a quality order.</span></span> <span data-ttu-id="10a07-108">A minőségvizsgálatokat általában minőségadminisztrátorok végzik.</span><span class="sxs-lookup"><span data-stu-id="10a07-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="10a07-109">Minőségi rendelés kiválasztása</span><span class="sxs-lookup"><span data-stu-id="10a07-109">Select a quality order</span></span>
1. <span data-ttu-id="10a07-110">Ugorjon a Készletkezelés > Időszakos feladatok > Minőségkezelés > Minőségi rendelések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10a07-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="10a07-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="10a07-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="10a07-112">Válassza ki az eljárás megkezdése előtt létrehozott minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="10a07-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="10a07-113">Teszteredmények rögzítése</span><span class="sxs-lookup"><span data-stu-id="10a07-113">Record test results</span></span>
1. <span data-ttu-id="10a07-114">Kattintson az Eredmények lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10a07-114">Click Results.</span></span>
2. <span data-ttu-id="10a07-115">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10a07-115">Click Edit.</span></span>
3. <span data-ttu-id="10a07-116">Adjon meg egy számot az Eredménymennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="10a07-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="10a07-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="10a07-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="10a07-118">A Kimenetel mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10a07-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="10a07-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="10a07-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="10a07-120">Ebben a példában az eredményt egy előre meghatározott eredmény alapul.</span><span class="sxs-lookup"><span data-stu-id="10a07-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="10a07-121">Általában speciálisabb teszteredményeket rögzít majd, például egy méretet vagy más dimenziót.</span><span class="sxs-lookup"><span data-stu-id="10a07-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="10a07-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="10a07-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="10a07-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="10a07-123">Click Save.</span></span>
9. <span data-ttu-id="10a07-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="10a07-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="10a07-125">A minőségi rendelés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="10a07-125">Validate the quality order</span></span>
1. <span data-ttu-id="10a07-126">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="10a07-126">Click Validate.</span></span>
2. <span data-ttu-id="10a07-127">Az Ellenőrzést végezte mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10a07-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="10a07-128">Válassza ki az ellenőrzést végző felhasználót.</span><span class="sxs-lookup"><span data-stu-id="10a07-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="10a07-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="10a07-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="10a07-130">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="10a07-130">Click Select.</span></span>
5. <span data-ttu-id="10a07-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10a07-131">Click OK.</span></span>
6. <span data-ttu-id="10a07-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="10a07-132">Close the page.</span></span>


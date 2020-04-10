---
title: Elavult termékváltozatok keresése
description: Ez az eljárás bemutatja, hogyan lehet megkeresni az elavult kiadott termékeket vagy termékváltozatokat, és hogyan lehet termékéletciklus-állapotot társítani az elavult termékekhez.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dcd0f67bae1042cb1e81423898eacd20f921e0e2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147584"
---
# <a name="find-obsolete-product-variants"></a><span data-ttu-id="9391f-103">Elavult termékváltozatok keresése</span><span class="sxs-lookup"><span data-stu-id="9391f-103">Find obsolete product variants</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9391f-104">Ez az eljárás bemutatja, hogyan lehet megkeresni az elavult kiadott termékeket vagy termékváltozatokat, és hogyan lehet termékéletciklus-állapotot társítani az elavult termékekhez.</span><span class="sxs-lookup"><span data-stu-id="9391f-104">This procedure shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="9391f-105">Előfeltétel: Meg kell határozni legalább egy, tervezéshez inaktív termékéletciklus-állapotot a jelen feladat-útmutató lejátszásához.</span><span class="sxs-lookup"><span data-stu-id="9391f-105">Prerequisite: You need to define at least one product lifecycle state that is inactive for planning before you can play this task guide.</span></span>


## <a name="run-a-simulation"></a><span data-ttu-id="9391f-106">Szimuláció futtatása</span><span class="sxs-lookup"><span data-stu-id="9391f-106">Run a simulation</span></span>
1. <span data-ttu-id="9391f-107">Ugorjon a Termékinformációk kezelése > Időszakos feladatok > Elavult termékek életciklus-állapotának módosítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9391f-107">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
2. <span data-ttu-id="9391f-108">Az Új termékéletciklus-állapot mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9391f-108">In the New product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="9391f-109">A Szimuláció futtatása termékadatok frissítése nélkül mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9391f-109">Select Yes in the Run simulation without updating product data field.</span></span>
4. <span data-ttu-id="9391f-110">Az Ennyi napon belül létrehozott termékek kizárása mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="9391f-110">In the Exclude products created within this number of days field, enter a number.</span></span>
5. <span data-ttu-id="9391f-111">A Tranzakciókban használt termékek kizárása (napokban megadva) mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="9391f-111">In the Exclude products used in transactions (in number of days) field, enter a number.</span></span>
6. <span data-ttu-id="9391f-112">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9391f-112">Expand the Records to include section.</span></span>
7. <span data-ttu-id="9391f-113">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="9391f-113">Click Filter.</span></span>
8. <span data-ttu-id="9391f-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9391f-114">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="9391f-115">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9391f-115">In the Criteria field, type a value.</span></span>
10. <span data-ttu-id="9391f-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9391f-116">Click OK.</span></span>
11. <span data-ttu-id="9391f-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9391f-117">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="9391f-118">Ajánlott a kötegelt szimuláció futtatása, ha jelentős számú termékekre keres.</span><span class="sxs-lookup"><span data-stu-id="9391f-118">It is recommended to run the simulation in batch if you expect to search a large number of products.</span></span> <span data-ttu-id="9391f-119">Ezenkívül győződjön meg arról, hogy a szimulációt ne a vállalat a leginkább aktív munkaidejében futtassa.</span><span class="sxs-lookup"><span data-stu-id="9391f-119">Also, make sure that the simulation is not run during the most active working time of the company.</span></span>  

## <a name="review-the-simulation-results"></a><span data-ttu-id="9391f-120">A szimuláció eredményeinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="9391f-120">Review the simulation results</span></span>
1. <span data-ttu-id="9391f-121">Ugorjon a Termékinformációk kezelése > Lekérdezések és jelentések > Termékéletciklus-állapot karbantartási előzményei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9391f-121">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>
   
> [!NOTE]
> <span data-ttu-id="9391f-122">Ezen az oldalon áttekintheti a szimulációs eredményeket, és kiértékelheti, hogy hány termékhez és termékváltozathoz lesz új termékéletciklus-állapot társítva, ha a frissítést szimuláció nélkül futtatjuk.</span><span class="sxs-lookup"><span data-stu-id="9391f-122">On this page, you can review the simulation results and make an assessment of how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a><span data-ttu-id="9391f-123">Futtassa az Elavult termékek életciklus-állapota frissítését</span><span class="sxs-lookup"><span data-stu-id="9391f-123">Run the update of the Product lifecycle state for obsolete products</span></span>
1. <span data-ttu-id="9391f-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9391f-124">Close the page.</span></span>
2. <span data-ttu-id="9391f-125">Ugorjon a Termékinformációk kezelése > Időszakos feladatok > Elavult termékek életciklus-állapotának módosítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9391f-125">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
3. <span data-ttu-id="9391f-126">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9391f-126">Expand the Records to include section.</span></span>

> [!NOTE]
> <span data-ttu-id="9391f-127">Vegye figyelembe, hogy az utolsó kijelölés mentése megtörtént.</span><span class="sxs-lookup"><span data-stu-id="9391f-127">Note that the last selection has been saved.</span></span>  

4. <span data-ttu-id="9391f-128">A Szimuláció futtatása termékadatok frissítése nélkül mezőben válassza a Nem lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9391f-128">Select No in the Run simulation without updating product data field.</span></span>
5. <span data-ttu-id="9391f-129">Bontsa ki a Futtatás a háttérben szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9391f-129">Expand the Run in the background section.</span></span>

> [!NOTE]
> <span data-ttu-id="9391f-130">Attól függően, hogy hány termék és termékváltozat érintett, fontolja meg a feladat kötegben történő futtatását.</span><span class="sxs-lookup"><span data-stu-id="9391f-130">Depending on how many products and product variants are affected, consider running this job in batch.</span></span> <span data-ttu-id="9391f-131">Győződjön meg arról, hogy ne futtasson nagy frissítési feladatokat a vállalat leginkább aktív munkaidejében.</span><span class="sxs-lookup"><span data-stu-id="9391f-131">Make sure that you are not running a large update job during the most active working hours in the company.</span></span>  

6. <span data-ttu-id="9391f-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9391f-132">Click OK.</span></span>
7. <span data-ttu-id="9391f-133">Ugorjon a Termékinformációk kezelése > Lekérdezések és jelentések > Termékéletciklus-állapot karbantartási előzményei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9391f-133">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>

> [!NOTE]
> <span data-ttu-id="9391f-134">Tekintse át a módosított kiadott termékeket és termékváltozatokat.</span><span class="sxs-lookup"><span data-stu-id="9391f-134">Review the changed released products and product variants.</span></span>  

8. <span data-ttu-id="9391f-135">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9391f-135">In the list, find and select the desired record.</span></span>


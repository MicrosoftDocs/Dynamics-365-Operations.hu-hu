---
title: Folytonossági ütemezések meghatározása
description: Ez a témakör végigvezeti a folyamatos program (más néven ismétlődő rendelések) beállításának lépésein.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 37c4022cb2f2acf567437c821946ad452ba8f37c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972330"
---
# <a name="define-continuity-schedules"></a><span data-ttu-id="7023e-103">Folytonossági ütemezések meghatározása</span><span class="sxs-lookup"><span data-stu-id="7023e-103">Define continuity schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7023e-104">Ez a témakör végigvezeti a folyamatos program (más néven ismétlődő rendelések) beállításának lépésein.</span><span class="sxs-lookup"><span data-stu-id="7023e-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="7023e-105">Ez a témakör az USRT cég bemutatóadatait használja.</span><span class="sxs-lookup"><span data-stu-id="7023e-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="7023e-106">Folytonos program létrehozása</span><span class="sxs-lookup"><span data-stu-id="7023e-106">Create continuity program</span></span>
1. <span data-ttu-id="7023e-107">Ugorjon a Kiskereskedelem és kereskedelem > Folytonosság > Hűségprogramok elemre.</span><span class="sxs-lookup"><span data-stu-id="7023e-107">Go to Retail and Commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="7023e-108">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="7023e-108">Click New.</span></span>
3. <span data-ttu-id="7023e-109">Az Ütemezésazonosító mezőben adja meg a folytonossági ütemezés azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="7023e-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="7023e-110">A Rendelés kezdete mezőben válassza az „Első esemény” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7023e-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="7023e-111">Ha egy vevő új rendelést küld be a folytonos programba, a termékszállításra két lehetőség kínálkozik: 1.</span><span class="sxs-lookup"><span data-stu-id="7023e-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="7023e-112">Első esemény: a folytonos program első terméke kerül kiszállításra.</span><span class="sxs-lookup"><span data-stu-id="7023e-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="7023e-113">2.</span><span class="sxs-lookup"><span data-stu-id="7023e-113">2.</span></span> <span data-ttu-id="7023e-114">Aktuális esemény: az aktuális termék kerül kiszállításra.</span><span class="sxs-lookup"><span data-stu-id="7023e-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="7023e-115">Például:</span><span class="sxs-lookup"><span data-stu-id="7023e-115">For example.</span></span> <span data-ttu-id="7023e-116">a vevő a program három hónapjának elteltével kapja meg a harmadikat a programban.</span><span class="sxs-lookup"><span data-stu-id="7023e-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="7023e-117">Jelölje be az „Igen” lehetőséget, és a rendszer rákérdez a rendelés kezdő dátumára.</span><span class="sxs-lookup"><span data-stu-id="7023e-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="7023e-118">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7023e-118">Click Add line.</span></span>
7. <span data-ttu-id="7023e-119">A Cikkszám mezőbe írja be az első termék cikkszámát (0013).</span><span class="sxs-lookup"><span data-stu-id="7023e-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="7023e-120">Írja be a következőt: „CP”.</span><span class="sxs-lookup"><span data-stu-id="7023e-120">Type 'CP'.</span></span>
9. <span data-ttu-id="7023e-121">Adja meg a dátumot, amikor az első termék rendelhető lesz.</span><span class="sxs-lookup"><span data-stu-id="7023e-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="7023e-122">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="7023e-122">Click Add line.</span></span>
11. <span data-ttu-id="7023e-123">A cikkszám mezőbe írja be a „0014” értéket.</span><span class="sxs-lookup"><span data-stu-id="7023e-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="7023e-124">A Dátumtartomány kódja mezőben törölje az értéket, hogy a mező üres legyen.</span><span class="sxs-lookup"><span data-stu-id="7023e-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="7023e-125">Ehhez az eljáráshoz törölje a dátumintervallumot.</span><span class="sxs-lookup"><span data-stu-id="7023e-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="7023e-126">A dátumot növekményes módon kell beállítani az első cikk kezdési dátumától.</span><span class="sxs-lookup"><span data-stu-id="7023e-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="7023e-127">Itt kell megadni a termékek szállítási intervallumát.</span><span class="sxs-lookup"><span data-stu-id="7023e-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="7023e-128">Írja be a következőt: „30”.</span><span class="sxs-lookup"><span data-stu-id="7023e-128">Type '30'.</span></span>
    * <span data-ttu-id="7023e-129">Havi programnál 30 napot kell beírni időszakként.</span><span class="sxs-lookup"><span data-stu-id="7023e-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="7023e-130">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7023e-130">Click Add line.</span></span>
15. <span data-ttu-id="7023e-131">A cikkszám mezőbe írja be a „0015” értéket.</span><span class="sxs-lookup"><span data-stu-id="7023e-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="7023e-132">Írja be a következőt: „Vége”.</span><span class="sxs-lookup"><span data-stu-id="7023e-132">Type 'End'.</span></span>
17. <span data-ttu-id="7023e-133">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7023e-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="7023e-134">Hozzárendelés folytonos elemhez</span><span class="sxs-lookup"><span data-stu-id="7023e-134">Assign to continuity item</span></span>
1. <span data-ttu-id="7023e-135">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7023e-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="7023e-136">Válassza ki a „0016” elemet.</span><span class="sxs-lookup"><span data-stu-id="7023e-136">Select item '0016'.</span></span>
    * <span data-ttu-id="7023e-137">Ehhez az eljáráshoz válassza ki a 0016-os cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="7023e-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="7023e-138">Általában ekkor már létrehozott egy kibocsátott terméket, amelyre további folyamatos üzleti logika kerül alkalmazásra, amikor a hívásközpontban bekerül egy értékesítési rendelésbe.</span><span class="sxs-lookup"><span data-stu-id="7023e-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="7023e-139">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7023e-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7023e-140">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7023e-140">Click Edit.</span></span>
5. <span data-ttu-id="7023e-141">Bontsa ki vagy csukja össze a(z) Értékesítés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7023e-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="7023e-142">Itt lehet megadni a folytonosság programot, amelyet ez a cikk képvisel.</span><span class="sxs-lookup"><span data-stu-id="7023e-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="7023e-143">Írja be a korábban létrehozott ütemezésazonosítót.</span><span class="sxs-lookup"><span data-stu-id="7023e-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="7023e-144">Amikor sor kerül ennek a cikknek az eladására egy hívásközpontban, további üzleti logika kerül alkalmazásra a kijelölt folytonos programra.</span><span class="sxs-lookup"><span data-stu-id="7023e-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="7023e-145">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7023e-145">Click Save.</span></span>


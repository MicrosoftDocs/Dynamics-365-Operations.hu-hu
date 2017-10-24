--- 
title: "Folytonos program használata"
description: "Ez az eljárás a folytonos program révén történő értékesítés és a kapcsolódó vevői rendelések feldolgozását mutatja be."
author: scott-tucker
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d3b5690bfbd10b77e784d35d0c4f4518de58333
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="use-a-continuity-program"></a><span data-ttu-id="aca6c-103">Folytonos program használata</span><span class="sxs-lookup"><span data-stu-id="aca6c-103">Use a continuity program</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="aca6c-104">Ez az eljárás a folytonos program révén történő értékesítés és a kapcsolódó vevői rendelések feldolgozását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="aca6c-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="aca6c-105">Az eljárás végrehajtásához a felhasználónak hívásközpont felhasználójaként kell beállítva lennie.</span><span class="sxs-lookup"><span data-stu-id="aca6c-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="aca6c-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="aca6c-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="aca6c-107">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Vevők > Ügyfélszolgálat.</span><span class="sxs-lookup"><span data-stu-id="aca6c-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="aca6c-108">A Keresés szövegben mezőbe írja be, hogy „Karen”, majd nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="aca6c-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="aca6c-109">Megjelenik a Speciális keresés párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="aca6c-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="aca6c-110">Ha nem, kattintson a Keresés gombra a mező jobb oldalán.</span><span class="sxs-lookup"><span data-stu-id="aca6c-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="aca6c-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aca6c-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="aca6c-112">Elvileg csak egy sor látszik, amely a Karen Berg értéket tünteti fel.</span><span class="sxs-lookup"><span data-stu-id="aca6c-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="aca6c-113">Jelölje ki a sort úgy, hogy rákattint a rács bal szélén látható pipa oszlopra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="aca6c-114">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aca6c-114">Click Select.</span></span>
5. <span data-ttu-id="aca6c-115">Kattintson az Új értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-115">Click New sales order.</span></span>
    * <span data-ttu-id="aca6c-116">Érdemes megjegyezni az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="aca6c-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="aca6c-117">Később szükség lesz rá az eljárás során.</span><span class="sxs-lookup"><span data-stu-id="aca6c-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="aca6c-118">A Cikkszám mezőbe írja be, hogy „88000”, majd nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="aca6c-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="aca6c-119">Ez egy folytonos cikk az USRT bemutatóadatok között.</span><span class="sxs-lookup"><span data-stu-id="aca6c-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="aca6c-120">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-120">Click Complete.</span></span>
8. <span data-ttu-id="aca6c-121">A Fizetési mód mezőbe írja be, hogy „Visa”.</span><span class="sxs-lookup"><span data-stu-id="aca6c-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="aca6c-122">Kattintson a Hitelkártya hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aca6c-122">Click Add credit card.</span></span>
    * <span data-ttu-id="aca6c-123">Ezen az oldalon adja meg a szükséges hitelkártyaadatokat.</span><span class="sxs-lookup"><span data-stu-id="aca6c-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="aca6c-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-124">Click OK.</span></span>
11. <span data-ttu-id="aca6c-125">Bontsa ki a Kifizetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="aca6c-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="aca6c-126">Hívásközponti rendelés elküldéséhez meg kell adni a rendeléshez tartozó kifizetéseket.</span><span class="sxs-lookup"><span data-stu-id="aca6c-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="aca6c-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-127">Click OK.</span></span>
13. <span data-ttu-id="aca6c-128">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-128">Click Submit.</span></span>
    * <span data-ttu-id="aca6c-129">Végzett az új folyamatos rendelés létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="aca6c-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="aca6c-130">Ezt követően két kötegelt eljárás futtatása következik, amelyek a folytonos rendelés feldolgozását végzik.</span><span class="sxs-lookup"><span data-stu-id="aca6c-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="aca6c-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aca6c-131">Close the page.</span></span>
15. <span data-ttu-id="aca6c-132">Ugorjon a Kiskereskedelem és kereskedelem > Folytonosság > Folytonos fizetések feldolgozása elemre.</span><span class="sxs-lookup"><span data-stu-id="aca6c-132">Go to Retail and commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="aca6c-133">A Folytonos cikk mezőbe írja be, hogy „88000”, és nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="aca6c-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="aca6c-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-134">Click OK.</span></span>
18. <span data-ttu-id="aca6c-135">Ugorjon a Kiskereskedelem és kereskedelem > Folytonosság > Folytonos gyermekrendelések létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="aca6c-135">Go to Retail and commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="aca6c-136">Ezt a folyamat új értékesítési rendeléseket hoz létre a folyamatos programok beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="aca6c-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="aca6c-137">A Folytonos cikk mezőbe írja be, hogy „88000”, és nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="aca6c-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="aca6c-138">A „88000” egy folytonos cikk az USRT-bemutatóadatok között.</span><span class="sxs-lookup"><span data-stu-id="aca6c-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="aca6c-139">Az Értékesítési rendelés mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aca6c-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="aca6c-140">Adja meg az eljárás során korábban feljegyzett értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="aca6c-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="aca6c-141">Ez minimálisra csökkenti az eljáráshoz szükséges feldolgozási időt.</span><span class="sxs-lookup"><span data-stu-id="aca6c-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="aca6c-142">A Értékesítési rendelés mező kitöltése nem kötelező - bármely programhoz feldolgozható az összes megrendelés.</span><span class="sxs-lookup"><span data-stu-id="aca6c-142">The Sales order field field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="aca6c-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="aca6c-143">Click OK.</span></span>


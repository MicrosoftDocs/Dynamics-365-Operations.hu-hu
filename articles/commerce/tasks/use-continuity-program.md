---
title: Folytonos program használata
description: Ez az eljárás a folytonos program révén történő értékesítés és a kapcsolódó vevői rendelések feldolgozását mutatja be.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd0bfcd99a23e4c639a6317adefb41a947a487a5
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022753"
---
# <a name="using-continuity-program"></a><span data-ttu-id="19891-103">Folytonos program használata</span><span class="sxs-lookup"><span data-stu-id="19891-103">Using continuity program</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="19891-104">Ez az eljárás a folytonos program révén történő értékesítés és a kapcsolódó vevői rendelések feldolgozását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="19891-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="19891-105">Az eljárás végrehajtásához a felhasználónak hívásközpont felhasználójaként kell beállítva lennie.</span><span class="sxs-lookup"><span data-stu-id="19891-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="19891-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="19891-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="19891-107">Nyissa meg a következőt: Commerce > Vevők > Ügyfélszolgálat.</span><span class="sxs-lookup"><span data-stu-id="19891-107">Go to Retail and Commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="19891-108">A Keresés szövegben mezőbe írja be, hogy „Karen”, majd nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="19891-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="19891-109">Megjelenik a Speciális keresés párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="19891-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="19891-110">Ha nem, kattintson a Keresés gombra a mező jobb oldalán.</span><span class="sxs-lookup"><span data-stu-id="19891-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="19891-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="19891-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="19891-112">Elvileg csak egy sor látszik, amely a Karen Berg értéket tünteti fel.</span><span class="sxs-lookup"><span data-stu-id="19891-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="19891-113">Jelölje ki a sort úgy, hogy rákattint a rács bal szélén látható pipa oszlopra.</span><span class="sxs-lookup"><span data-stu-id="19891-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="19891-114">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="19891-114">Click Select.</span></span>
5. <span data-ttu-id="19891-115">Kattintson az Új értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="19891-115">Click New sales order.</span></span>
    * <span data-ttu-id="19891-116">Érdemes megjegyezni az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="19891-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="19891-117">Később szükség lesz rá az eljárás során.</span><span class="sxs-lookup"><span data-stu-id="19891-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="19891-118">A Cikkszám mezőbe írja be, hogy „88000”, majd nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="19891-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="19891-119">Ez egy folytonos cikk az USRT bemutatóadatok között.</span><span class="sxs-lookup"><span data-stu-id="19891-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="19891-120">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="19891-120">Click Complete.</span></span>
8. <span data-ttu-id="19891-121">A Fizetési mód mezőbe írja be, hogy „Visa”.</span><span class="sxs-lookup"><span data-stu-id="19891-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="19891-122">Kattintson a Hitelkártya hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="19891-122">Click Add credit card.</span></span>
    * <span data-ttu-id="19891-123">Ezen az oldalon adja meg a szükséges hitelkártyaadatokat.</span><span class="sxs-lookup"><span data-stu-id="19891-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="19891-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="19891-124">Click OK.</span></span>
11. <span data-ttu-id="19891-125">Bontsa ki a Kifizetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="19891-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="19891-126">Hívásközponti rendelés elküldéséhez meg kell adni a rendeléshez tartozó kifizetéseket.</span><span class="sxs-lookup"><span data-stu-id="19891-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="19891-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="19891-127">Click OK.</span></span>
13. <span data-ttu-id="19891-128">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="19891-128">Click Submit.</span></span>
    * <span data-ttu-id="19891-129">Végzett az új folyamatos rendelés létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="19891-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="19891-130">Ezt követően két kötegelt eljárás futtatása következik, amelyek a folytonos rendelés feldolgozását végzik.</span><span class="sxs-lookup"><span data-stu-id="19891-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="19891-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="19891-131">Close the page.</span></span>
15. <span data-ttu-id="19891-132">Ugorjon a Retail és Commerce > Folytonosság > Folytonos fizetések feldolgozása elemre.</span><span class="sxs-lookup"><span data-stu-id="19891-132">Go to Retail and Commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="19891-133">A Folytonos cikk mezőbe írja be, hogy „88000”, és nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="19891-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="19891-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="19891-134">Click OK.</span></span>
18. <span data-ttu-id="19891-135">Ugorjon a Retail és Commerce > Folytonosság > Folytonos gyermekrendelések létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="19891-135">Go to Retail and Commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="19891-136">Ezt a folyamat új értékesítési rendeléseket hoz létre a folyamatos programok beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="19891-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="19891-137">A Folytonos cikk mezőbe írja be, hogy „88000”, és nyomja le a Tab billentyűt.</span><span class="sxs-lookup"><span data-stu-id="19891-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="19891-138">A „88000” egy folytonos cikk az USRT-bemutatóadatok között.</span><span class="sxs-lookup"><span data-stu-id="19891-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="19891-139">Az Értékesítési rendelés mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="19891-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="19891-140">Adja meg az eljárás során korábban feljegyzett értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="19891-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="19891-141">Ez minimálisra csökkenti az eljáráshoz szükséges feldolgozási időt.</span><span class="sxs-lookup"><span data-stu-id="19891-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="19891-142">A Értékesítési rendelés mező kitöltése nem kötelező - bármely programhoz feldolgozható az összes megrendelés.</span><span class="sxs-lookup"><span data-stu-id="19891-142">The Sales order field field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="19891-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="19891-143">Click OK.</span></span>


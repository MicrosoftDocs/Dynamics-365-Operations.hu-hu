--- 
title: "Hívásközponti rendelések létrehozása"
description: "Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 62f88cc2e28405a9d2eb43819fb09d83a64658b6
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="create-call-center-orders"></a><span data-ttu-id="b226f-103">Hívásközponti rendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="b226f-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="b226f-104">Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől.</span><span class="sxs-lookup"><span data-stu-id="b226f-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="b226f-105">Az eljárás az USRT bemutatócéget használja, és az Értékesítési adminisztrátor számára készült.</span><span class="sxs-lookup"><span data-stu-id="b226f-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="b226f-106">Előfeltételek: Az eljárást elvégző felhasználók a Hívásközpont felhasználóiként vannak beállítva, valamint a Gyári Féléves Katalógus közzététele megtörtént, legalább egy Forráskóddal.</span><span class="sxs-lookup"><span data-stu-id="b226f-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="b226f-107">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Vevők > Ügyfélszolgálat.</span><span class="sxs-lookup"><span data-stu-id="b226f-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="b226f-108">A Keresés szövegben mezőbe írja be a feltételeket a vevő kikereséséhez.</span><span class="sxs-lookup"><span data-stu-id="b226f-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="b226f-109">Ebben a példaeljárásban írja be: „karen”, majd nyomja meg a TAB billentyűt.</span><span class="sxs-lookup"><span data-stu-id="b226f-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="b226f-110">Kattintson a Keresés gombra.</span><span class="sxs-lookup"><span data-stu-id="b226f-110">Click Search.</span></span>
    * <span data-ttu-id="b226f-111">Mivel a bemutató adatsor csak egy „Karen” nevű vevőt tartalmaz, az ő kiválasztása automatikusan megtörténik.</span><span class="sxs-lookup"><span data-stu-id="b226f-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="b226f-112">Kattintson az Új értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="b226f-112">Click New sales order.</span></span>
5. <span data-ttu-id="b226f-113">Bontsa ki vagy csukja össze az Értékesítési rendelés fejléce szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b226f-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="b226f-114">Válassza ki a katalógus forráskódját.</span><span class="sxs-lookup"><span data-stu-id="b226f-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="b226f-115">Amennyiben nincsenek aktív Forráskódok, bezárhatja a Forrás mezőt, és kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="b226f-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="b226f-116">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b226f-116">Click Add line.</span></span>
8. <span data-ttu-id="b226f-117">A Cikkszám mezőbe írja be írja be a cikk-keresési kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b226f-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="b226f-118">Ebben a mintaeljárásban írja be a következő cikkszám-részletet: „8111”, majd nyomja meg a TAB billentyűt.</span><span class="sxs-lookup"><span data-stu-id="b226f-118">For this sample procedure enter a partial item number of '8111' and press tab.</span></span> <span data-ttu-id="b226f-119">Ekkor megjelenik a cikk-kereső ablak.</span><span class="sxs-lookup"><span data-stu-id="b226f-119">This will pop up the item search window.</span></span>  
9. <span data-ttu-id="b226f-120">Válassza ki az értékesítési rendeléshez hozzáadandó terméket.</span><span class="sxs-lookup"><span data-stu-id="b226f-120">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="b226f-121">Adja meg az értékesítési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="b226f-121">Enter the sales quantity.</span></span>
11. <span data-ttu-id="b226f-122">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b226f-122">Click Create.</span></span>
12. <span data-ttu-id="b226f-123">Kattintson a Befejezés gombra a vevői fizetés rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b226f-123">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="b226f-124">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b226f-124">Click Add.</span></span>
    * <span data-ttu-id="b226f-125">A Hivatkozás hozzáadása a Kifizetések lapon található.</span><span class="sxs-lookup"><span data-stu-id="b226f-125">The Add link is in the Payments tab.</span></span> <span data-ttu-id="b226f-126">Bontsa ki a Kifizetések lapot, ha össze van csukva.</span><span class="sxs-lookup"><span data-stu-id="b226f-126">Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="b226f-127">Válassza ki a fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="b226f-127">Select the payment method.</span></span>
    * <span data-ttu-id="b226f-128">Ebben az eljárásban válassza ki a készpénzfizetési módszert.</span><span class="sxs-lookup"><span data-stu-id="b226f-128">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="b226f-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b226f-129">Close the page.</span></span>
16. <span data-ttu-id="b226f-130">Írja be az összeget.</span><span class="sxs-lookup"><span data-stu-id="b226f-130">Enter the amount.</span></span>
    * <span data-ttu-id="b226f-131">Ennél az eljárásnál írjon be egy olyan összeget, amely megegyezik a rendelési egyenleggel. Ez az Értékesítési rendelés összesítése oldalon látható, az összeg mezőtől balra.</span><span class="sxs-lookup"><span data-stu-id="b226f-131">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="b226f-132">Ez lehetővé teszi, hogy teljesen kifizetett állapotban befejezze a rendelést.</span><span class="sxs-lookup"><span data-stu-id="b226f-132">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="b226f-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b226f-133">Click OK.</span></span>
18. <span data-ttu-id="b226f-134">Kattintson a Küldés hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b226f-134">Click Submit.</span></span>



---
title: Hívásközponti rendelések létrehozása
description: Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dce2fdd9d91c2bd867f0455573733aefb0796fa7
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107352"
---
# <a name="create-call-center-orders"></a><span data-ttu-id="83806-103">Hívásközponti rendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="83806-103">Create call center orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83806-104">Ez az eljárás bemutatja, hogy hogyan kereshet ki egy vevőt, hozhat létre egy új rendelést és kereshet rá egy termére, továbbá hogyan szedhet be kifizetést a vevőtől.</span><span class="sxs-lookup"><span data-stu-id="83806-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="83806-105">Az eljárás az USRT bemutatócéget használja, és az Értékesítési adminisztrátor számára készült.</span><span class="sxs-lookup"><span data-stu-id="83806-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="83806-106">Előfeltételek: Az eljárást elvégző felhasználók a Hívásközpont felhasználóiként vannak beállítva, valamint a Gyári Féléves Katalógus közzététele megtörtént, legalább egy Forráskóddal.</span><span class="sxs-lookup"><span data-stu-id="83806-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="83806-107">Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Ügyfelek \> Ügyfélszolgálat**.</span><span class="sxs-lookup"><span data-stu-id="83806-107">Go to **Retail and Commerce \> Customers \> Customer service**.</span></span>
2. <span data-ttu-id="83806-108">A **Keresés szövegben** mezőbe írja be a feltételeket a vevő kikereséséhez.</span><span class="sxs-lookup"><span data-stu-id="83806-108">For **SearchText** , enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="83806-109">Ebben a példaeljárásban írja be: „karen”, majd nyomja meg a **TAB** billentyűt.</span><span class="sxs-lookup"><span data-stu-id="83806-109">For this example procedure, enter "Karen" and select **Tab**.</span></span>  
3. <span data-ttu-id="83806-110">Válassza a Keresés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83806-110">Select Search.</span></span>
    * <span data-ttu-id="83806-111">Mivel a bemutató adatsor csak egy „Karen” nevű vevőt tartalmaz, az eredmény kiválasztása automatikusan megtörténik.</span><span class="sxs-lookup"><span data-stu-id="83806-111">Since there is only one customer named "Karen" in demo data, the result will be automatically selected.</span></span>  
4. <span data-ttu-id="83806-112">Válassza ki az **Új értékesítési rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83806-112">Select **New sales order**.</span></span>
5. <span data-ttu-id="83806-113">Bontsa ki vagy csukja össze az **Értékesítési rendelés** fejléce szakaszt.</span><span class="sxs-lookup"><span data-stu-id="83806-113">Expand or collapse the **Sales order** header section.</span></span>
6. <span data-ttu-id="83806-114">Válassza ki a katalógus forráskódját.</span><span class="sxs-lookup"><span data-stu-id="83806-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="83806-115">Amennyiben nincsenek aktív Forráskódok, kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="83806-115">If there are no active source codes you can skip this step.</span></span>  
7. <span data-ttu-id="83806-116">Válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83806-116">Select **Add line**.</span></span>
8. <span data-ttu-id="83806-117">A **Cikkszám** mezőbe írja be írja be a cikk-keresési kifejezést.</span><span class="sxs-lookup"><span data-stu-id="83806-117">For **Item number** , enter the item search term.</span></span>
    * <span data-ttu-id="83806-118">Ebben a mintaeljárásban írja be a következő cikkszám-részletet: „8111”, majd nyomja meg a TAB billentyűt. Ezzel a művelettel megjelenik a cikk-kereső ablak.</span><span class="sxs-lookup"><span data-stu-id="83806-118">For this sample procedure, enter a partial item number of '8111' and press tab. This action will bring up the item search window.</span></span>  
9. <span data-ttu-id="83806-119">Válassza ki az értékesítési rendeléshez hozzáadandó terméket.</span><span class="sxs-lookup"><span data-stu-id="83806-119">Select the product to add to the sales order.</span></span>
10. <span data-ttu-id="83806-120">Adja meg az értékesítési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="83806-120">Enter the sales quantity.</span></span>
11. <span data-ttu-id="83806-121">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83806-121">Select **Create**.</span></span>
12. <span data-ttu-id="83806-122">Kattintson a **Befejezés** gombra a vevői fizetés rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="83806-122">Select **Complete** to capture the customer payment.</span></span>
13. <span data-ttu-id="83806-123">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83806-123">Select **Add**.</span></span>
    * <span data-ttu-id="83806-124">A Hivatkozás hozzáadása a Kifizetések lapon található. Bontsa ki a Kifizetések lapot, ha össze van csukva.</span><span class="sxs-lookup"><span data-stu-id="83806-124">The Add link is in the Payments tab. Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="83806-125">Válassza ki a fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="83806-125">Select the payment method.</span></span>
    * <span data-ttu-id="83806-126">Ebben az eljárásban válassza ki a készpénzfizetési módszert.</span><span class="sxs-lookup"><span data-stu-id="83806-126">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="83806-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="83806-127">Close the page.</span></span>
16. <span data-ttu-id="83806-128">Írja be az összeget.</span><span class="sxs-lookup"><span data-stu-id="83806-128">Enter the amount.</span></span>
    * <span data-ttu-id="83806-129">Ennél az eljárásnál írjon be egy olyan összeget, amely megegyezik a rendelési egyenleggel. Ez az Értékesítési rendelés összesítése oldalon látható, az összeg mezőtől balra.</span><span class="sxs-lookup"><span data-stu-id="83806-129">For this procedure, enter an amount equal to the order balance that can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="83806-130">Ez a művelet lehetővé teszi, hogy teljesen kifizetett állapotban befejezze a rendelést.</span><span class="sxs-lookup"><span data-stu-id="83806-130">This action will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="83806-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83806-131">Select **OK**.</span></span>
18. <span data-ttu-id="83806-132">Válassza a **Beküldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="83806-132">Select **Submit**.</span></span>


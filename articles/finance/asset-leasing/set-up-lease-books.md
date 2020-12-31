---
title: Lízingkönyvek beállítása
description: Ez a témakör a lízingkönyvekben található információkat ismerteti. A lízingkönyvek tartalmazzák azokat a könyvelési irányelveket, amelyek meghatározzák, hogyan számolja el a lízinget a rendszerben.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444176"
---
# <a name="set-up-lease-books"></a><span data-ttu-id="f204d-104">Lízingkönyvek beállítása</span><span class="sxs-lookup"><span data-stu-id="f204d-104">Set up lease books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f204d-105">A lízingkönyvek tartalmazzák azokat a könyvelési irányelveket, amelyek meghatározzák, hogyan számolja el a lízinget a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f204d-105">Lease books contain the accounting policies that determine how a lease is accounted for in the system.</span></span> <span data-ttu-id="f204d-106">A készpénzalapú elszámolás mellett az eszközlízing a következő standardokat támogatja:</span><span class="sxs-lookup"><span data-stu-id="f204d-106">In addition to cash basis accounting, Asset leasing supports the following standards:</span></span>

- <span data-ttu-id="f204d-107">Általánosan elfogadott könyvelési elvek az Egyesült Államokban (US GAAP)</span><span class="sxs-lookup"><span data-stu-id="f204d-107">Generally Accepted Accounting Principles in the United States (US GAAP)</span></span>
- <span data-ttu-id="f204d-108">Könyvelési standardok kodifikációs témaköre 842 (ASC 842)</span><span class="sxs-lookup"><span data-stu-id="f204d-108">Accounting Standards Codification Topic 842 (ASC 842)</span></span>
- <span data-ttu-id="f204d-109">ASC 840</span><span class="sxs-lookup"><span data-stu-id="f204d-109">ASC 840</span></span>
- <span data-ttu-id="f204d-110">Nemzetközi pénzügyi jelentési standard 16 (IFRS 16)</span><span class="sxs-lookup"><span data-stu-id="f204d-110">International Financial Reporting Standard 16 (IFRS 16)</span></span>
- <span data-ttu-id="f204d-111">Nemzetközi könyvelési standard 17 (IAS 17)</span><span class="sxs-lookup"><span data-stu-id="f204d-111">International Accounting Standard 17 (IAS 17)</span></span>

<span data-ttu-id="f204d-112">Lízingkönyv létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f204d-112">To create a lease book, follow these steps.</span></span>

1. <span data-ttu-id="f204d-113">Nyissa meg az **Eszközlízing \> Beállítás \> Lízingkönyvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f204d-113">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="f204d-114">Könyv hozzáadásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f204d-114">Select **New** to add a book.</span></span>
3. <span data-ttu-id="f204d-115">Állítsa be a következő mezőket.</span><span class="sxs-lookup"><span data-stu-id="f204d-115">Set the following fields.</span></span>

    | <span data-ttu-id="f204d-116">Név</span><span class="sxs-lookup"><span data-stu-id="f204d-116">Name</span></span>                                     | <span data-ttu-id="f204d-117">Leírás</span><span class="sxs-lookup"><span data-stu-id="f204d-117">Description</span></span> |
    |------------------------------------------|-------------|
    | <span data-ttu-id="f204d-118">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="f204d-118">Posting layer</span></span>                            | <span data-ttu-id="f204d-119">Válassza ki a használni kívánt feladási réteget.</span><span class="sxs-lookup"><span data-stu-id="f204d-119">Select the posting layer to use.</span></span> <span data-ttu-id="f204d-120">Minden könyv, amely egy lízinghez van csatolva, egy adott feladási réteghez van beállítva.</span><span class="sxs-lookup"><span data-stu-id="f204d-120">Each book that is attached to a lease is set up for a specific posting layer.</span></span> <span data-ttu-id="f204d-121">Minden feladási rétegnek különböző feladási céljai vannak.</span><span class="sxs-lookup"><span data-stu-id="f204d-121">Each posting layer has different posting purposes.</span></span> |
    | <span data-ttu-id="f204d-122">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="f204d-122">Lease type</span></span>                               | <span data-ttu-id="f204d-123">Válassza ki, hogy a lízinget automatikusan kell-e besorolni, vagy előre meg kell-e határozni pénzügyi vagy operatív lízingként.</span><span class="sxs-lookup"><span data-stu-id="f204d-123">Select whether the lease should be classified automatically, or whether it should be predefined as a finance or operating lease.</span></span> |
    | <span data-ttu-id="f204d-124">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="f204d-124">Accounting framework</span></span>                     | <span data-ttu-id="f204d-125">Válassza ki a könyvhöz társított keretrendszert.</span><span class="sxs-lookup"><span data-stu-id="f204d-125">Select the framework that is associated with the book.</span></span> |
    | <span data-ttu-id="f204d-126">Lízingfutamidő/hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="f204d-126">Lease term/Useful life Set Up</span></span>          | <span data-ttu-id="f204d-127">A rendszer akkor minősíti a lízinget pénzügyi lízingnek, ha a lízingtípust **Automatikusra** állították, és ha az eszköz lízingfutamideje az eszköz hasznos élettartamán túl nagyobb vagy egyenlő az ebben a mezőben megadott százalékkal.</span><span class="sxs-lookup"><span data-stu-id="f204d-127">The system will classify the lease as a finance lease if the lease type is set to **Automatic**, and if the lease term over useful life of the asset is greater than or equal to the percentage entered in this field.</span></span>  |
    | <span data-ttu-id="f204d-128">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="f204d-128">Present value / Asset fair value setup</span></span>   | <span data-ttu-id="f204d-129">Adjon meg egy egész számot a lízing típusát meghatározó küszöbérték meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="f204d-129">Enter a whole number to define the threshold that will determine the lease type.</span></span> <span data-ttu-id="f204d-130">Ha a jövőbeli minimális lízingfizetések jelenértéke nagyobb, mint a könyv beállításából származó felhasználó által meghatározott érték, és ha a könyv lízingbesorolása automatikus, a rendszer a lízinget pénzügyi lízingként sorolja be.</span><span class="sxs-lookup"><span data-stu-id="f204d-130">If the present value of future minimum lease payments is more than the user-defined value from the book setup, and if the book's lease classification is set to automatic, the system will classify the lease as a finance lease.</span></span> |
    | <span data-ttu-id="f204d-131">Rövid távú küszöbérték</span><span class="sxs-lookup"><span data-stu-id="f204d-131">Short-term threshold</span></span>                     | <span data-ttu-id="f204d-132">Adja meg a rövid távú lízingek küszöbértékként használandó hónapok számát.</span><span class="sxs-lookup"><span data-stu-id="f204d-132">Enter the number of months to use as a threshold for short-term leases.</span></span> <span data-ttu-id="f204d-133">Ha a lízing időtartama kisebb vagy egyenlő az itt megadott hónapok számával, a rendszer a lízinget rövid távú lízingként osztályozza, és a halasztott bérleti díjat kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="f204d-133">If the lease term is less than or equal to the number of months that you enter here, the system will classify the lease as a short-term lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="f204d-134">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="f204d-134">Low value threshold</span></span>                      | <span data-ttu-id="f204d-135">Adja meg az alacsony értékű lízingek küszöbértékeként használandó összeget.</span><span class="sxs-lookup"><span data-stu-id="f204d-135">Enter an amount to use as a threshold for low-value leases.</span></span> <span data-ttu-id="f204d-136">Ha az eszköz valós értéke kisebb vagy egyenlő az itt megadott értékkel, a rendszer a lízinget alacsony értékű lízingként osztályozza, és a halasztott bérleti díjat kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="f204d-136">If the fair value of the asset is less than or equal or the value that you enter here, the system will classify the lease as a low-value lease, and the deferred rent treatment will be applied.</span></span> |
    | <span data-ttu-id="f204d-137">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="f204d-137">Pay to vendor</span></span>                            | <span data-ttu-id="f204d-138">Állítsa ezt a beállítást **Igen** értékre, ha lehetővé szeretné tenni a lízingkifizetések számlaként történő feladását az egyes lízingeken megadott szállítói számlára.</span><span class="sxs-lookup"><span data-stu-id="f204d-138">Set this option to **Yes** to allow lease payments to be posted, as an invoice, to the vendor account that is specified on each lease.</span></span> <span data-ttu-id="f204d-139">A lízingkifizetés feladásakor a szállítói számla jóváírásra kerül.</span><span class="sxs-lookup"><span data-stu-id="f204d-139">When a lease payment is posted, the vendor account will be credited.</span></span> <span data-ttu-id="f204d-140">Ha ez a beállítás **Nem** értékű, akkor a **Lízing fizetési** feladási típushoz a **Lízing feladási paraméterek** lapon megadott számla kerül jóváírásra.</span><span class="sxs-lookup"><span data-stu-id="f204d-140">If this option is set to **No**, the account that is specified for the **Lease payment** posting type on the **Lease posting parameters** page will be credited instead.</span></span> |

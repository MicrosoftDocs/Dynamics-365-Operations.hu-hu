---
title: Díjazási profilok
description: Ez a témakör az adatok beállítását írja le a díjazási profilokhoz.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f754a8b86b0d369af03812a831d77a8a6fa8154
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233511"
---
# <a name="rating-profiles"></a><span data-ttu-id="409cb-103">Díjazási profilok</span><span class="sxs-lookup"><span data-stu-id="409cb-103">Rating profiles</span></span>

<span data-ttu-id="409cb-104">A díjazási profil egy logisztikai szerződéshez hasonlít (de nem szerződéshez).</span><span class="sxs-lookup"><span data-stu-id="409cb-104">A rating profile resembles a logistics contract (but not a legal contract).</span></span> <span data-ttu-id="409cb-105">Ez a rakományok szállítási vámtarifáinak meghatározására szolgál.</span><span class="sxs-lookup"><span data-stu-id="409cb-105">It's used to determine transportation tariffs for loads.</span></span> 

<span data-ttu-id="409cb-106">Minden díjazási profil egyedi jellegű a szállítmányozóra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="409cb-106">Each rating profile is unique to a shipping carrier.</span></span> <span data-ttu-id="409cb-107">A profilban a szállítmányozót egy díjnyilvántartáshoz társíthatja.</span><span class="sxs-lookup"><span data-stu-id="409cb-107">In the profile, you associate the shipping carrier with a rate master.</span></span> <span data-ttu-id="409cb-108">A díjnyilvántartás meghatározza a díjalap-hozzárendelést és az alapdíjat.</span><span class="sxs-lookup"><span data-stu-id="409cb-108">The rate master defines the rate base assignment and the rate base.</span></span> <span data-ttu-id="409cb-109">Az alapdíj határozza meg a szállítmányozó díját.</span><span class="sxs-lookup"><span data-stu-id="409cb-109">The rate base determines the rate of the carrier.</span></span>

<span data-ttu-id="409cb-110">A díjazási profilt egy általános oldal, amely áttekintést nyújt az összes meglévő díjazási profilra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="409cb-110">You can set up a rating profile by using a generic page that shows an overview of all existing rating profiles.</span></span> <span data-ttu-id="409cb-111">Másik lehetőségként a díjazási profilt közvetlenül a szállítmányozóból is beállíthatja.</span><span class="sxs-lookup"><span data-stu-id="409cb-111">Alternatively, you can set up a rating profile directly from the shipping carrier.</span></span> <span data-ttu-id="409cb-112">Mindkét esetben a minősítési profilhoz megadott információ ugyanaz.</span><span class="sxs-lookup"><span data-stu-id="409cb-112">In both cases, the information that you set up for the rating profile is the same.</span></span>

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a><span data-ttu-id="409cb-113">Díjazási profil létrehozása vagy szerkesztése a díjazási profilok oldalon lehetséges</span><span class="sxs-lookup"><span data-stu-id="409cb-113">Create or edit a rating profile on the Rating profiles page</span></span>

<span data-ttu-id="409cb-114">A **Díjazási profilok** lapon tekintheti meg az összes elérhető díjazási profilt.</span><span class="sxs-lookup"><span data-stu-id="409cb-114">On the **Rating profiles** page, you can review all available rating profiles.</span></span> <span data-ttu-id="409cb-115">Lehetőség van a meglévő profilok szerkesztésére és új profilok létrehozására is.</span><span class="sxs-lookup"><span data-stu-id="409cb-115">You can also edit existing profiles and create new profiles.</span></span>

1. <span data-ttu-id="409cb-116">Lépjen a **Szállításkezelés \> Beállítás \> Díjazás \> Díjazási profil** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="409cb-116">Go to **Transportation management \> Setup \> Rating \> Rating profile**.</span></span>
1. <span data-ttu-id="409cb-117">A művelet ablakban válassza az **Új** lehetőséget új díjazási sablon rácshoz való hozzáadásához, vagy válassza a **Szerkesztés** lehetőséget egy meglévő profil szerkesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="409cb-117">On the Action Pane, select **New** to add a new rating profile to the grid, or select **Edit** to edit an existing profile.</span></span>
1. <span data-ttu-id="409cb-118">Az új vagy meglévő díjazási profil sorában állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="409cb-118">In the row for the new or existing rating profile, set the following fields:</span></span>

    - <span data-ttu-id="409cb-119">**Díjazási profil** – Adja meg a díjazási profil egyedi azonosítóját (azonosító).</span><span class="sxs-lookup"><span data-stu-id="409cb-119">**Rating profile** – Enter a unique identifier (ID) for the rating profile.</span></span>
    - <span data-ttu-id="409cb-120">**Név** – Írja be a díjazási profil leíró nevét.</span><span class="sxs-lookup"><span data-stu-id="409cb-120">**Name** – Enter a descriptive name for the rating profile.</span></span>
    - <span data-ttu-id="409cb-121">**Szállítmányozó** – Válasszon ki egy szállítmányozót.</span><span class="sxs-lookup"><span data-stu-id="409cb-121">**Shipping carrier** – Select a shipping carrier.</span></span> <span data-ttu-id="409cb-122">A beállított díjazási profil a kiválasztott szállítmányozó **Szállítmányozó** lapján is látható lesz .</span><span class="sxs-lookup"><span data-stu-id="409cb-122">The rating profile that you're setting up will also be shown on the **Shipping carriers** page for the selected carrier.</span></span>
    - <span data-ttu-id="409cb-123">**Telephely** és **Raktár** – Válasszon ki egy telephelyet és raktárat.</span><span class="sxs-lookup"><span data-stu-id="409cb-123">**Site** and **Warehouse** – Select a site and warehouse.</span></span>
    - <span data-ttu-id="409cb-124">**Díjazási motor** – Válassza ki a díjazási profilhoz tartozó díjazási motort.</span><span class="sxs-lookup"><span data-stu-id="409cb-124">**Rate engine** – Select the rate engine for the rating profile.</span></span>
    - <span data-ttu-id="409cb-125">**Díjnyilvántartás** – Válassza ki a díjnyilvántartáshoz tartozó díjazási motort.</span><span class="sxs-lookup"><span data-stu-id="409cb-125">**Rate master** – Select the rate master for the rating profile.</span></span> <span data-ttu-id="409cb-126">A díjnyilvántartás segítségével meghatározhatja az alapdíj típusát és az alapdíjat.</span><span class="sxs-lookup"><span data-stu-id="409cb-126">You can use the rate master to define a rate base type and a rate base.</span></span> <span data-ttu-id="409cb-127">További információkért lásd: [Díjnyilvántartások beállítása](set-up-rate-masters.md).</span><span class="sxs-lookup"><span data-stu-id="409cb-127">For more information, see [Set up rate masters](set-up-rate-masters.md).</span></span>
    - <span data-ttu-id="409cb-128">**Szállításiidő-kalkulátor** – Válassza ki a díjazási profil szállításiidő-kalkulátorát.</span><span class="sxs-lookup"><span data-stu-id="409cb-128">**Transit time engine** – Select the transit time engine for the rating profile.</span></span>
    - <span data-ttu-id="409cb-129">**Szállítmányozói üzemanyag-mutató** – Válassza ki a díjazási profilhoz használt díjkalkulátort és szállítmányozói üzemanyag-mutatót.</span><span class="sxs-lookup"><span data-stu-id="409cb-129">**Carrier fuel index** – Select the carrier fuel index for the rating profile.</span></span>
    - <span data-ttu-id="409cb-130">A **Kezdő dátum és idő** és a **Tényleges befejezés dátuma és időpontja** – Adja meg azt az időszakot, amikor a díjazási profilnak aktívnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="409cb-130">**Effect start date and time** and **Effective end date and time** – Define the period when the rating profile should be active.</span></span>

1. <span data-ttu-id="409cb-131">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="409cb-131">On the Action Pane, select **Save**.</span></span>

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a><span data-ttu-id="409cb-132">Díjazási profil létrehozása közvetlenül a Szállítmányozók oldalon lehetséges</span><span class="sxs-lookup"><span data-stu-id="409cb-132">Create a rating profile directly on the Shipping carriers page</span></span>

1. <span data-ttu-id="409cb-133">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozók \> Szállítmányozók** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="409cb-133">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="409cb-134">A listában válasszon ki egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="409cb-134">Select a shipping carrier in the list.</span></span>
1. <span data-ttu-id="409cb-135">A **Díjazási profilok** gyorslapon válassza az **Új** lehetőséget a díjazási profil létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="409cb-135">On the **Rating profiles** FastTab, select **New** to create a rating profile.</span></span>
1. <span data-ttu-id="409cb-136">Adja meg az új díjazási profil mezőit.</span><span class="sxs-lookup"><span data-stu-id="409cb-136">Set the fields for the new rating profile.</span></span> <span data-ttu-id="409cb-137">Ezek a mezők megegyeznek a **Díjazási profilok** lap mezőivel, a témakör előző szakaszának leírása szerint.</span><span class="sxs-lookup"><span data-stu-id="409cb-137">These fields correspond to the fields on the **Rating profiles** page, as described in previous section of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="409cb-138">A **Szállítmányozók** lapon létrehozott profilok a **Díjazási profilok** oldalon is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="409cb-138">Profiles that are created on the **Shipping carriers** page are also shown on the **Rating profiles** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
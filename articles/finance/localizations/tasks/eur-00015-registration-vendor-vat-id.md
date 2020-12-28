---
title: EUR-00015 Szállítói adószám rögzítése
description: Ez az eljárás bemutatja, hogyan lehet áfaregisztrációs azonosítókat és áfamentességi számot adni egy szállítói fiókhoz.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5126868038801091c7a9c17eee78e31db322cbb7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408042"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a><span data-ttu-id="95de3-103">EUR-00015 Szállítói adószám rögzítése</span><span class="sxs-lookup"><span data-stu-id="95de3-103">EUR-00015 Registration of vendor VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="95de3-104">Ez az eljárás bemutatja, hogyan lehet áfaregisztrációs azonosítókat és áfamentességi számot adni egy szállítói fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="95de3-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="95de3-105">Ez a folyamat hasonló a jogi személyek és az ügyfelek számára.</span><span class="sxs-lookup"><span data-stu-id="95de3-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="95de3-106">Mielőtt ezt az eljárást elvégezné, áfaazonosítókat kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="95de3-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="95de3-107">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="95de3-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="95de3-108">Ezt az eljárást a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="95de3-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="95de3-109">Ez az eljárás az adatkezelés rendszergazdája, a kötelezettségeket kezelő vezető és a kinnlevőség-kezelő számára szól.</span><span class="sxs-lookup"><span data-stu-id="95de3-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="95de3-110">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="95de3-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="95de3-111">Ugrás a Kötelezettségek > Szállítók > Minden szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="95de3-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="95de3-112">A DE-01001 szállító megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="95de3-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="95de3-113">Kattintson a Nyilvántartási azonosítók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95de3-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="95de3-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="95de3-114">Click Add.</span></span>
5. <span data-ttu-id="95de3-115">Áfaazonosító kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="95de3-115">Select VAT ID.</span></span>
6. <span data-ttu-id="95de3-116">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="95de3-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="95de3-117">A kiválasztott szállítóhoz adjon meg egy áfaazonosítót Németországban.</span><span class="sxs-lookup"><span data-stu-id="95de3-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="95de3-118">Az azonosítónak meg kell egyeznie a regisztrációs típus megadott formátumával.</span><span class="sxs-lookup"><span data-stu-id="95de3-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="95de3-119">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="95de3-119">Click the General tab.</span></span>
8. <span data-ttu-id="95de3-120">Adjon meg egy dátumot az Érvényesség mezőben.</span><span class="sxs-lookup"><span data-stu-id="95de3-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="95de3-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="95de3-121">Click Save.</span></span>
10. <span data-ttu-id="95de3-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95de3-122">Click New.</span></span>
11. <span data-ttu-id="95de3-123">A „Név vagy leírás” mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="95de3-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="95de3-124">Például írja be, hogy ITA.</span><span class="sxs-lookup"><span data-stu-id="95de3-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="95de3-125">Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="95de3-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="95de3-126">Válassza, például az ITA-t.</span><span class="sxs-lookup"><span data-stu-id="95de3-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="95de3-127">Válassza az Igen lehetőséget az Ország elsődleges címe mezőben.</span><span class="sxs-lookup"><span data-stu-id="95de3-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="95de3-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="95de3-128">Click Save.</span></span>
15. <span data-ttu-id="95de3-129">Kattintson az Áttekintés fülre.</span><span class="sxs-lookup"><span data-stu-id="95de3-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="95de3-130">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="95de3-130">Click Add.</span></span>
17. <span data-ttu-id="95de3-131">A Regisztráció típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="95de3-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="95de3-132">Válassza ki például a „Áfaazonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95de3-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="95de3-133">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="95de3-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="95de3-134">Adjon meg például egy olaszországi áfaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="95de3-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="95de3-135">Az azonosítónak meg kell egyeznie a regisztrációs típus formátumával.</span><span class="sxs-lookup"><span data-stu-id="95de3-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="95de3-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="95de3-136">Click Save.</span></span>
20. <span data-ttu-id="95de3-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="95de3-137">Close the page.</span></span>
21. <span data-ttu-id="95de3-138">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="95de3-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="95de3-139">Válassza ki például a DE-01001-et.</span><span class="sxs-lookup"><span data-stu-id="95de3-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="95de3-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="95de3-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="95de3-141">Nyissa meg A számlázás és szállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="95de3-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="95de3-142">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="95de3-142">Click Edit.</span></span>
25. <span data-ttu-id="95de3-143">Az Adómentességi szám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="95de3-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="95de3-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="95de3-144">Click Save.</span></span>


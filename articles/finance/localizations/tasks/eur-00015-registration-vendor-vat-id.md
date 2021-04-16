---
title: EUR-00015 Szállítói adószám rögzítése
description: Ez az eljárás bemutatja, hogyan lehet áfaregisztrációs azonosítókat és áfamentességi számot adni egy szállítói fiókhoz.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 578f961fe1b5e3d06b624b78c278c8314df47f5e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822560"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a><span data-ttu-id="30771-103">EUR-00015 Szállítói adószám rögzítése</span><span class="sxs-lookup"><span data-stu-id="30771-103">EUR-00015 Registration of vendor VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="30771-104">Ez az eljárás bemutatja, hogyan lehet áfaregisztrációs azonosítókat és áfamentességi számot adni egy szállítói fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="30771-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="30771-105">Ez a folyamat hasonló a jogi személyek és az ügyfelek számára.</span><span class="sxs-lookup"><span data-stu-id="30771-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="30771-106">Mielőtt ezt az eljárást elvégezné, áfaazonosítókat kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="30771-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="30771-107">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="30771-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="30771-108">Ezt az eljárást a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="30771-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="30771-109">Ez az eljárás az adatkezelés rendszergazdája, a kötelezettségeket kezelő vezető és a kinnlevőség-kezelő számára szól.</span><span class="sxs-lookup"><span data-stu-id="30771-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="30771-110">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="30771-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="30771-111">Ugrás a Kötelezettségek > Szállítók > Minden szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="30771-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="30771-112">A DE-01001 szállító megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="30771-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="30771-113">Kattintson a Nyilvántartási azonosítók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30771-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="30771-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="30771-114">Click Add.</span></span>
5. <span data-ttu-id="30771-115">Áfaazonosító kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="30771-115">Select VAT ID.</span></span>
6. <span data-ttu-id="30771-116">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="30771-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="30771-117">A kiválasztott szállítóhoz adjon meg egy áfaazonosítót Németországban.</span><span class="sxs-lookup"><span data-stu-id="30771-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="30771-118">Az azonosítónak meg kell egyeznie a regisztrációs típus megadott formátumával.</span><span class="sxs-lookup"><span data-stu-id="30771-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="30771-119">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="30771-119">Click the General tab.</span></span>
8. <span data-ttu-id="30771-120">Adjon meg egy dátumot az Érvényesség mezőben.</span><span class="sxs-lookup"><span data-stu-id="30771-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="30771-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30771-121">Click Save.</span></span>
10. <span data-ttu-id="30771-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30771-122">Click New.</span></span>
11. <span data-ttu-id="30771-123">A „Név vagy leírás” mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="30771-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="30771-124">Például írja be, hogy ITA.</span><span class="sxs-lookup"><span data-stu-id="30771-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="30771-125">Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="30771-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="30771-126">Válassza, például az ITA-t.</span><span class="sxs-lookup"><span data-stu-id="30771-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="30771-127">Válassza az Igen lehetőséget az Ország elsődleges címe mezőben.</span><span class="sxs-lookup"><span data-stu-id="30771-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="30771-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30771-128">Click Save.</span></span>
15. <span data-ttu-id="30771-129">Kattintson az Áttekintés fülre.</span><span class="sxs-lookup"><span data-stu-id="30771-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="30771-130">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="30771-130">Click Add.</span></span>
17. <span data-ttu-id="30771-131">A Regisztráció típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="30771-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="30771-132">Válassza ki például a „Áfaazonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="30771-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="30771-133">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="30771-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="30771-134">Adjon meg például egy olaszországi áfaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="30771-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="30771-135">Az azonosítónak meg kell egyeznie a regisztrációs típus formátumával.</span><span class="sxs-lookup"><span data-stu-id="30771-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="30771-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30771-136">Click Save.</span></span>
20. <span data-ttu-id="30771-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="30771-137">Close the page.</span></span>
21. <span data-ttu-id="30771-138">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="30771-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="30771-139">Válassza ki például a DE-01001-et.</span><span class="sxs-lookup"><span data-stu-id="30771-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="30771-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="30771-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="30771-141">Nyissa meg A számlázás és szállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="30771-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="30771-142">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="30771-142">Click Edit.</span></span>
25. <span data-ttu-id="30771-143">Az Adómentességi szám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="30771-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="30771-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="30771-144">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
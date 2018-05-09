--- 
title: "Szállítói adószám regisztrálása"
description: "Ez az eljárás bemutatja, hogyan lehet áfaregisztrációs azonosítókat és áfamentességi számot adni egy szállítói fiókhoz."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c398ca76b2cef2c27b57bab4b50824ec59538297
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="register-a-vendor-vat-id"></a><span data-ttu-id="2b7c1-103">Szállítói adószám regisztrálása</span><span class="sxs-lookup"><span data-stu-id="2b7c1-103">Register a vendor VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2b7c1-104">Ez az eljárás bemutatja, hogyan lehet áfaregisztrációs azonosítókat és áfamentességi számot adni egy szállítói fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="2b7c1-105">Ez a folyamat hasonló a jogi személyek és az ügyfelek számára.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="2b7c1-106">Mielőtt ezt az eljárást elvégezné, áfaazonosítókat kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="2b7c1-107">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="2b7c1-108">Ezt az eljárást a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="2b7c1-109">Ez az eljárás az adatkezelés rendszergazdája, a kötelezettségeket kezelő vezető és a kinnlevőség-kezelő számára szól.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="2b7c1-110">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="2b7c1-111">Ugrás a Kötelezettségek > Szállítók > Minden szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="2b7c1-112">A DE-01001 szállító megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="2b7c1-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="2b7c1-113">Kattintson a Nyilvántartási azonosítók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="2b7c1-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-114">Click Add.</span></span>
5. <span data-ttu-id="2b7c1-115">Áfaazonosító kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-115">Select VAT ID.</span></span>
6. <span data-ttu-id="2b7c1-116">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="2b7c1-117">A kiválasztott szállítóhoz adjon meg egy áfaazonosítót Németországban.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="2b7c1-118">Az azonosítónak meg kell egyeznie a regisztrációs típus megadott formátumával.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="2b7c1-119">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-119">Click the General tab.</span></span>
8. <span data-ttu-id="2b7c1-120">Adjon meg egy dátumot az Érvényesség mezőben.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="2b7c1-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-121">Click Save.</span></span>
10. <span data-ttu-id="2b7c1-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-122">Click New.</span></span>
11. <span data-ttu-id="2b7c1-123">A „Név vagy leírás” mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="2b7c1-124">Például írja be, hogy ITA.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="2b7c1-125">Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="2b7c1-126">Válassza, például az ITA-t.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="2b7c1-127">Válassza az Igen lehetőséget az Ország elsődleges címe mezőben.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="2b7c1-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-128">Click Save.</span></span>
15. <span data-ttu-id="2b7c1-129">Kattintson az Áttekintés fülre.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="2b7c1-130">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-130">Click Add.</span></span>
17. <span data-ttu-id="2b7c1-131">A Regisztráció típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="2b7c1-132">Válassza ki például a „Áfaazonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="2b7c1-133">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="2b7c1-134">Adjon meg például egy olaszországi áfaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="2b7c1-135">Az azonosítónak meg kell egyeznie a regisztrációs típus formátumával.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="2b7c1-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-136">Click Save.</span></span>
20. <span data-ttu-id="2b7c1-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-137">Close the page.</span></span>
21. <span data-ttu-id="2b7c1-138">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2b7c1-139">Válassza ki például a DE-01001-et.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="2b7c1-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="2b7c1-141">Nyissa meg A számlázás és szállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="2b7c1-142">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-142">Click Edit.</span></span>
25. <span data-ttu-id="2b7c1-143">Az Adómentességi szám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="2b7c1-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="2b7c1-144">Click Save.</span></span>



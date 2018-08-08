---
title: "A cikk érkezésáttekintési profiljának beállítása"
description: "Ez a feladat érkeztetési áttekintési profil létrehozására szolgál."
author: perlynne
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
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 4b4b89f39008218721ef092ee01a93522d1461b1
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="dd2bf-103">A cikk érkezésáttekintési profiljának beállítása</span><span class="sxs-lookup"><span data-stu-id="dd2bf-103">Set up an item arrival overview profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd2bf-104">Ez a feladat érkeztetési áttekintési profil létrehozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-104">This task focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="dd2bf-105">Az érkeztetési áttekintési profil szabályok gyűjteménye, amelyet egy Érkeztetési áttekintési oldal felhasználó általi megnyitásakor alkalmaz a rendszer.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-105">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="dd2bf-106">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-106">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="dd2bf-107">Általában ezt a feladatot egy befogadó jegyző végzi el.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-107">This procedure would typically be carried out by a receiving clerk.</span></span>





1. <span data-ttu-id="dd2bf-108">Ugorjon a Készletkezelés > Beállítás > Felosztás > Érkeztetési áttekintési profilok pontra.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-108">Go to Inventory management > Setup > Distribution > Arrival overview profiles.</span></span>
2. <span data-ttu-id="dd2bf-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-109">Click New.</span></span>
    * <span data-ttu-id="dd2bf-110">Mivel szinte mindig ugyanabban a raktárban dolgozik teljes rakományok lerakásával, mindig kell egy érkezési áttekintési profilt létrehozni a beérkezett cikkek regisztrálásának egyszerűsítéséhez.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-110">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="dd2bf-111">Az Érkeztetési áttekintési profil mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-111">In the Arrival overview profile name field, type a value.</span></span>
4. <span data-ttu-id="dd2bf-112">Válasszon ki egy lehetőséget a Sorok megjelenítése mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-112">In the Show lines field, select an option.</span></span>
    * <span data-ttu-id="dd2bf-113">Válassza ki, hogy mely sorok látsszanak a bevételezéseknél: az összes – valamennyi sor megjelenik, állapottól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-113">Select which lines to show for the receipts:   All – Show all lines, regardless of status.</span></span>   <span data-ttu-id="dd2bf-114">Folyamatban – Bevételezési sorok megjelenítése, amelyben az előrehaladás Elkészült vagy Részben.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-114">In progress – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="dd2bf-115">Ez azt jelenti, hogy minden sor teljes vagy egy részleges mennyisége regisztrálva van az érkeztetési naplóban.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-115">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   <span data-ttu-id="dd2bf-116">Nem teljes – Bevételezési sorok megjelenítése, amelyben az előrehaladás Nincs vagy Részben.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-116">Not complete – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="dd2bf-117">Ez azt jelenti, hogy az egyes soroknál semmi sem vagy csak a mennyiség egy része van regisztrálva az érkeztetési naplóba.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-117">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  
5. <span data-ttu-id="dd2bf-118">Bontsa ki vagy csukja össze az Érkezési beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-118">Expand or collapse the Arrival options section.</span></span>
6. <span data-ttu-id="dd2bf-119">A Napok mától mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-119">In the Days forward field, type a value.</span></span>
    * <span data-ttu-id="dd2bf-120">Ez beállít egy szűrőt, hogy megmutassa a következő napban fogadni kívánt nyugtasorokat (a beállított számtól függően).</span><span class="sxs-lookup"><span data-stu-id="dd2bf-120">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="dd2bf-121">A Napra visszamenőleg mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-121">In the Days back field, type a value.</span></span>
    * <span data-ttu-id="dd2bf-122">Ezzel beállít egy szűrőt, amely megjeleníti az adott nap előtt adott számú nappal fogadott nyugtasorokat.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-122">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="dd2bf-123">A Raktárak mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-123">In the Warehouses field, type a value.</span></span>
    * <span data-ttu-id="dd2bf-124">Szűrjön egy vagy több raktárra.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-124">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="dd2bf-125">Válasszon ki egy értéket a Szállítási mód mezőbe.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-125">In the Mode of delivery field, select a value.</span></span>
    * <span data-ttu-id="dd2bf-126">Ez beállít egy szűrőt, hogy csak ezzel a szállítási móddal jelenjenek meg nyugtasorok.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-126">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="dd2bf-127">A Név mezőben, válassza a WHS-t.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-127">In the Name field, select WHS.</span></span>
11. <span data-ttu-id="dd2bf-128">A Raktár mezőben válassza ki a 24-es raktárt.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-128">In the Warehouse field, select warehouse 24.</span></span>
    * <span data-ttu-id="dd2bf-129">Ez az alapértelmezett raktár, amellyel a profilt használó nyugtasorok be lesznek jegyezve.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-129">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="dd2bf-130">A Hely mezőben válassza ki a Baydoor-t.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-130">In the Location field, select Baydoor.</span></span>
    * <span data-ttu-id="dd2bf-131">Ez az alapértelmezett hely, amellyel a profilt használó nyugtasorok be lesznek jegyezve.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-131">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="dd2bf-132">Bontsa ki vagy csukja össze a Érkezéslekérdezés részletei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-132">Expand or collapse the Arrival query details section.</span></span>
14. <span data-ttu-id="dd2bf-133">A Készletező hely mezőben válassza 2. helyet.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-133">In the Restrict to site field, select site 2.</span></span>
    * <span data-ttu-id="dd2bf-134">Ez beállít egy szűrőt, hogy csak ezzel a hellyel jelenjenek meg nyugtasorok.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-134">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="dd2bf-135">A Beszerzési rendelések beállítást állítsa Igen értékre.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-135">Set the Purchase orders option to Yes.</span></span>
    * <span data-ttu-id="dd2bf-136">Nyugtasorok kiválasztása beszerzési rendelésekből.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-136">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="dd2bf-137">A Szállítási rendelések beállítást állítsa Igen értékre.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-137">Set the Transfer orders option to Yes.</span></span>
    * <span data-ttu-id="dd2bf-138">Nyugtasorok kiválasztása átmozgatási rendelésekből.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-138">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="dd2bf-139">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-139">Click Save.</span></span>
18. <span data-ttu-id="dd2bf-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="dd2bf-140">Close the page.</span></span>


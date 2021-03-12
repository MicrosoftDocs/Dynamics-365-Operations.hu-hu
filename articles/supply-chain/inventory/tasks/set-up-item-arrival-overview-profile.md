---
title: A cikk érkezésáttekintési profiljának beállítása
description: Ez a témakör az érkezésáttekintési profil beállítását ismerteti.
author: ShylaThompson
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ecfe132d9b0e096c5fdf015f80a6efb34c9b178
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961430"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="0c0bf-103">A cikk érkezésáttekintési profiljának beállítása</span><span class="sxs-lookup"><span data-stu-id="0c0bf-103">Set up an item arrival overview profile</span></span>

<span data-ttu-id="0c0bf-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="0c0bf-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="0c0bf-105">Ez a témakör az érkezésáttekintési profil beállítását ismerteti.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-105">This topic focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="0c0bf-106">Az érkeztetési áttekintési profil szabályok gyűjteménye, amelyet egy Érkeztetési áttekintési oldal felhasználó általi megnyitásakor alkalmaz a rendszer.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-106">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="0c0bf-107">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="0c0bf-108">Általában ezt a feladatot egy befogadó jegyző végzi el.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-108">This procedure would typically be carried out by a receiving clerk.</span></span>

1. <span data-ttu-id="0c0bf-109">A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Beállítás > Kiosztás > Érkezésáttekintési profilok** részre.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-109">In the navigation pane, go to **Modules > Inventory management > Setup > Distribution > Arrival overview profiles**.</span></span>
2. <span data-ttu-id="0c0bf-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-110">Select **New**.</span></span> <span data-ttu-id="0c0bf-111">Mivel szinte mindig ugyanabban a raktárban dolgozik teljes rakományok lerakásával, mindig kell egy érkezési áttekintési profilt létrehozni a beérkezett cikkek regisztrálásának egyszerűsítéséhez.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-111">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="0c0bf-112">Adjon meg egy értéket az **Érkezésáttekintési profil** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-112">In the **Arrival overview profile name** field, type a value.</span></span>
4. <span data-ttu-id="0c0bf-113">Válasszon ki egy lehetőséget a **Sorok megjelenítése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-113">In the **Show lines** field, select an option.</span></span> <span data-ttu-id="0c0bf-114">Válassza ki, hogy mely soroknak kell látszódniuk a bevételezéseknél:</span><span class="sxs-lookup"><span data-stu-id="0c0bf-114">Select which lines to show for the receipts:</span></span>  

    - <span data-ttu-id="0c0bf-115">**Mind** – minden sor megmutatása állapottól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-115">**All** – Show all lines, regardless of status.</span></span>   
    - <span data-ttu-id="0c0bf-116">**Folyamatban** – azoknak a bevételezési soroknak a megjelenítése, amelyben az előrehaladás Elkészült vagy Részben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-116">**In progress** – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="0c0bf-117">Ez azt jelenti, hogy minden sor teljes vagy egy részleges mennyisége regisztrálva van az érkeztetési naplóban.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-117">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   
    - <span data-ttu-id="0c0bf-118">**Nem teljes** – azoknak a bevételezési soroknak a megjelenítése, amelyben az előrehaladás Nincs vagy Részben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-118">**Not complete** – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="0c0bf-119">Ez azt jelenti, hogy az egyes soroknál semmi sem vagy csak a mennyiség egy része van regisztrálva az érkeztetési naplóba.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-119">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  

5. <span data-ttu-id="0c0bf-120">Bontsa ki vagy csukja össze az **Érkezési beállítások** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-120">Expand or collapse the **Arrival options** section.</span></span>
6. <span data-ttu-id="0c0bf-121">Adjon meg egy értéket a **Napok mától** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-121">In the **Days forward** field, type a value.</span></span> <span data-ttu-id="0c0bf-122">Ez beállít egy szűrőt, hogy megmutassa a következő napban fogadni kívánt nyugtasorokat (a beállított számtól függően).</span><span class="sxs-lookup"><span data-stu-id="0c0bf-122">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="0c0bf-123">Adjon meg egy értéket a **Napra visszamenőleg** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-123">In the **Days back** field, type a value.</span></span> <span data-ttu-id="0c0bf-124">Ezzel beállít egy szűrőt, amely megjeleníti az adott nap előtt adott számú nappal fogadott nyugtasorokat.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-124">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="0c0bf-125">Adjon meg egy értéket a **Raktárak** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-125">In the **Warehouses** field, type a value.</span></span> <span data-ttu-id="0c0bf-126">Szűrjön egy vagy több raktárra.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-126">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="0c0bf-127">Válasszon ki egy értéket a **Szállítási mód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-127">In the **Mode of delivery** field, select a value.</span></span> <span data-ttu-id="0c0bf-128">Ez beállít egy szűrőt, hogy csak ezzel a szállítási móddal jelenjenek meg nyugtasorok.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-128">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="0c0bf-129">A **Név** mezőben, válassza a WHS-t.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-129">In the **Name** field, select WHS.</span></span>
11. <span data-ttu-id="0c0bf-130">A **Raktár** mezőben válassza ki a 24-es raktárt.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-130">In the **Warehouse** field, select warehouse 24.</span></span> <span data-ttu-id="0c0bf-131">Ez az alapértelmezett raktár, amellyel a profilt használó nyugtasorok be lesznek jegyezve.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-131">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="0c0bf-132">A **Hely** mezőben válassza ki a **Baydoor** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-132">In the **Location** field, select **Baydoor**.</span></span> <span data-ttu-id="0c0bf-133">Ez az alapértelmezett hely, amellyel a profilt használó nyugtasorok be lesznek jegyezve.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-133">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="0c0bf-134">Bontsa ki vagy csukja össze a **Érkezéslekérdezés részletei** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-134">Expand or collapse the **Arrival query details** section.</span></span>
14. <span data-ttu-id="0c0bf-135">A **Korlátozás a helyre** mezőben válassza 2. helyet.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-135">In the **Restrict to site** field, select site 2.</span></span> <span data-ttu-id="0c0bf-136">Ez beállít egy szűrőt, hogy csak ezzel a hellyel jelenjenek meg nyugtasorok.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-136">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="0c0bf-137">A **Beszerzési rendelések** beállítást állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-137">Set the **Purchase orders** option to **Yes**.</span></span> <span data-ttu-id="0c0bf-138">Nyugtasorok kiválasztása beszerzési rendelésekből.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-138">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="0c0bf-139">Az **Átvitel** beállítást állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-139">Set the **Transfer** orders option to **Yes**.</span></span> <span data-ttu-id="0c0bf-140">Nyugtasorok kiválasztása átmozgatási rendelésekből.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-140">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="0c0bf-141">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-141">Select **Save**.</span></span>
18. <span data-ttu-id="0c0bf-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0c0bf-142">Close the page.</span></span>


---
title: Egy munkafolyamat munkatételeinek delegálása
description: Ha azt tervezi, hogy távol lesz a munkahelyétől, vagy valamilyen más okból nem tud elvégezni egy adott munkaelemet, a munkaelemeket más felhasználóknak delegálhatja, illetve hozzárendelheti a felhasználókhoz.
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed21f6d32cdcf74eb153daba32c20b7cef94d4e4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747369"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="9f6d7-103">Egy munkafolyamat munkatételeinek delegálása</span><span class="sxs-lookup"><span data-stu-id="9f6d7-103">Delegate work items in a workflow</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="9f6d7-104">Munkaelem delegálátsa manuálisan</span><span class="sxs-lookup"><span data-stu-id="9f6d7-104">Manually delegate a work item</span></span>

<span data-ttu-id="9f6d7-105">Ha egyetlen munkaelemet szeretne delegálni, válassza a **Delegálás** beállítást a **Munkafolyamat** menüben, majd adja meg a delegálni kívánt felhasználót a megjegyzéssel együtt.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="9f6d7-106">Ez hozzárendeli a munkaelemet újra a felhasználóhoz, így végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="manually-delegate-multiple-work-items"></a><span data-ttu-id="9f6d7-107">Több munkatétel manuális delegálása</span><span class="sxs-lookup"><span data-stu-id="9f6d7-107">Manually delegate multiple work items</span></span>

<span data-ttu-id="9f6d7-108">Több munkatétel együttesen delegálható a **Hozzám rendelt munkatételek** oldalról.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-108">Multiple work items can be delegated together from the **Work items assigned to me** page.</span></span> <span data-ttu-id="9f6d7-109">A következő munkafolyamat-típusok használhatók tömeges delegáláshoz: Beszerzési szerződés jóváhagyási munkafolyamata, Beszerzési rendelés munkafolyamata, Beszerzési igénylés ellenőrzése és Szállítói számla munkafolyamata.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-109">The following workflow types are eligible for mass delegation: Purchase agreement approval workflow, Purchase order workflow, Purchase requisition review, and Vendor invoice workflow.</span></span> <span data-ttu-id="9f6d7-110">A **Több munkatétel delegálása** funkció alapértelmezés szerint le van tiltva, és a **Munkaterületek > Szolgáltatások kezelése** modulban engedélyezhető.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-110">The **Delegate multiple work items** feature is disabled by default and can be enabled in **Workspaces > Feature management**.</span></span> <span data-ttu-id="9f6d7-111">A funkció engedélyezésével kapcsolatos segítségért forduljon a rendszergazdához.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-111">Contact your system administrator for help with enabling this feature.</span></span>
1.  <span data-ttu-id="9f6d7-112">Ugorjon a **Közös > Közös > Munkatételek >Hozzám rendelt munkatételek** pontra.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-112">Go to **Common > Common > Work items > Work items assigned to me**.</span></span>
2.  <span data-ttu-id="9f6d7-113">Válassza ki azokat a munkatételeket, amelyek delegálva lesznek.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-113">Select the work items that will be delegated.</span></span>
3.  <span data-ttu-id="9f6d7-114">Kattintson a **Munkatételek delegálása** menüre.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-114">Click the **Delegate work items** menu.</span></span>
4.  <span data-ttu-id="9f6d7-115">A **Felhasználó** mezőben jelölje ki azt a felhasználót, akihez a munkatételeket delegálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-115">In the **User** field, select the user to delegate the work items to.</span></span>
5.  <span data-ttu-id="9f6d7-116">A **Megjegyzés** mezőben adjon meg egy megjegyzést, amely leírja, miért delegálja a munkatételeket.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-116">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
6.  <span data-ttu-id="9f6d7-117">A munkatétel-delegálás befejezéséhez kattintson a **Munkatételek delegálása** gombra.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-117">Click the **Delegate work items** button to complete the work item delegation.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="9f6d7-118">Munkaelem delegálása automatikusan</span><span class="sxs-lookup"><span data-stu-id="9f6d7-118">Automatically delegate work items</span></span>

<span data-ttu-id="9f6d7-119">Ha úgy tervezi, hogy nem lesz az irodában vagy más okból nem lesz elérhető a munkaelemek feldolgozáshoz egy bizonyos ideig, automatikusan delegálhatja az új munkaelemeket más felhasználókhoz a **Felhasználói beállítások** oldal segítségével.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-119">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="9f6d7-120">Automatikus delegálás beállítása</span><span class="sxs-lookup"><span data-stu-id="9f6d7-120">Set up automatic delegation</span></span>
1. <span data-ttu-id="9f6d7-121">Ugrás a **Közös > Beállítás > Felhasználói beállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-121">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="9f6d7-122">Kattintson a **Munkafolyamat** fülre. Győződjön meg róla, hogy a Delegálások szakasz ki van bontva.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-122">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="9f6d7-123">Annak a konfigurálásához, hogy a rendszer automatikusan delegálja az Ön munkaelemeit más felhasználóknak, delegálási szabályok kell létrehoznia, amelyek megadják, hogy mikor kell bizonyos típusú munkatételeket delegálni.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-123">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="9f6d7-124">Delegálási szabály létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-124">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="9f6d7-125">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-125">Click **Add**.</span></span>
4. <span data-ttu-id="9f6d7-126">A **Hatókör** mezőben válasszon egy lehetőséget:</span><span class="sxs-lookup"><span data-stu-id="9f6d7-126">In the **Scope** field, select an option:</span></span>
    - <span data-ttu-id="9f6d7-127">Mind – Az Önhöz rendelt összes munkaelem delegálása.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-127">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="9f6d7-128">Modul – Csak azoknak a munkaelemeknek a delegálása, amelyek adott típusú munkafolyamathoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-128">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="9f6d7-129">Ha ezt a lehetőséget választja, a **Név** mezőben ki kell választania a munkafolyamat típusát.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-129">If you select this option, you must select the type of workflow in the **Name** field.</span></span>
    - <span data-ttu-id="9f6d7-130">Munkafolyamat – Csak azoknak a munkaelemeknek a delegálása, amelyek adott munkafolyamathoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-130">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="9f6d7-131">Ha ezt a lehetőséget választja, a **Név** mezőben ki kell választania a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-131">If you select this option, you must select the workflow in the **Name** field.</span></span>  
5. <span data-ttu-id="9f6d7-132">A **Név** mezőben:</span><span class="sxs-lookup"><span data-stu-id="9f6d7-132">In the **Name** field:</span></span>
    - <span data-ttu-id="9f6d7-133">A **Modul** hatóköréhez válassza ki a célmodult.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-133">For **Module** scope, select the target module.</span></span>
    - <span data-ttu-id="9f6d7-134">A **Munkafolyamat** hatóköréhez válassza ki a célmunkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-134">For **Workflow** scope, select the target workflow.</span></span>
6. <span data-ttu-id="9f6d7-135">A **Delegálás** mezőben jelölje ki azt a felhasználót, akihez a munkatételeket delegálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-135">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="9f6d7-136">A **Kezdő dátum/időpont** és a **Záró dátum/időpont** mezők használatával adja meg, mikor szeretné, hogy automatikusan megtörténjen a munkatételek delegálása.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-136">Use the **Start date/time** and **End date/time** fields to specify when you want the work items to be automatically delegated.</span></span>  
7. <span data-ttu-id="9f6d7-137">A **Kezdő dátum/idő** mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-137">In the **Start date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="9f6d7-138">A **Záró dátum/idő** mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-138">In the **End date/time** field, enter a date and time.</span></span>
9. <span data-ttu-id="9f6d7-139">A delegálási szabály aktiválásához jelölje be az **Engedélyezett** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-139">Select the **Enabled** check box to activate the delegation rule.</span></span> 
10. <span data-ttu-id="9f6d7-140">A **Megjegyzés** mezőben adjon meg egy megjegyzést, amely leírja, miért delegálja a munkatételeket.</span><span class="sxs-lookup"><span data-stu-id="9f6d7-140">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
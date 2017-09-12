--- 
title: "Dolgozói szállások kezelése"
description: "Ez az eljárás végigvezeti a munkakörnyezet szállástípusok létrehozásán, például ergonómikus székek vagy időszakos szünetek beállításának lépésein."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 10d34d0b2eca95034d1f67931ff72a035be9a6b8
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="manage-worker-accommodations"></a><span data-ttu-id="3c16b-103">Dolgozói szállások kezelése</span><span class="sxs-lookup"><span data-stu-id="3c16b-103">Manage worker accommodations</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="3c16b-104">Ez az eljárás végigvezeti a munkakörnyezet szállástípusok létrehozásán, például ergonómikus székek vagy időszakos szünetek beállításának lépésein.</span><span class="sxs-lookup"><span data-stu-id="3c16b-104">This procedure walks through the steps for setting up work environment accommodation types, such as ergonomic chairs or periodic breaks.</span></span> <span data-ttu-id="3c16b-105">Azt is leírja, hogyan rendelhetők hozzá ezek a szállástípusok egy dolgozóhoz, és hogyan hagyhatók jóvá és utasíthatók el a szállástípusok.</span><span class="sxs-lookup"><span data-stu-id="3c16b-105">It also shows how to assign these accommodation types to a worker, and either approve or deny the accommodation type.</span></span> <span data-ttu-id="3c16b-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="3c16b-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="setup-accommodations"></a><span data-ttu-id="3c16b-107">Szállások beállítása</span><span class="sxs-lookup"><span data-stu-id="3c16b-107">Setup accommodations</span></span>
1. <span data-ttu-id="3c16b-108">Ugorjon az Emberi erőforrások > Beállítás > Szállástípusok pontra.</span><span class="sxs-lookup"><span data-stu-id="3c16b-108">Go to Human resources > Setup > Accommodation types.</span></span>
2. <span data-ttu-id="3c16b-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3c16b-109">Click New.</span></span>
3. <span data-ttu-id="3c16b-110">A Szállástípus mezőben adja meg a szállás nevét.</span><span class="sxs-lookup"><span data-stu-id="3c16b-110">In the Accommodation type field, enter a name for the accommodation.</span></span> <span data-ttu-id="3c16b-111">Példa: Billentyűzet.</span><span class="sxs-lookup"><span data-stu-id="3c16b-111">Example: Keyboard.</span></span>
4. <span data-ttu-id="3c16b-112">A Leírás mezőben adjon meg egy leírást a szálláshoz.</span><span class="sxs-lookup"><span data-stu-id="3c16b-112">In the Description field, enter a description for the accommodation.</span></span> <span data-ttu-id="3c16b-113">Példa: Ergonómikus billentyűzet.</span><span class="sxs-lookup"><span data-stu-id="3c16b-113">Example: Ergonomic Keyboard.</span></span>
5. <span data-ttu-id="3c16b-114">A Megjegyzés mezőben adjon meg információkat, amelyek segítséget nyújtanak a szállás egyértelművé tételében.</span><span class="sxs-lookup"><span data-stu-id="3c16b-114">In the Note field, enter any information that helps to clarify the accommodation.</span></span>
6. <span data-ttu-id="3c16b-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3c16b-115">Click Save.</span></span>
7. <span data-ttu-id="3c16b-116">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3c16b-116">Close the page.</span></span>

## <a name="assign-accommodations"></a><span data-ttu-id="3c16b-117">Szállások hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="3c16b-117">Assign accommodations</span></span>
1. <span data-ttu-id="3c16b-118">Ugrás az Emberi erőforrások > Dolgozók > Alkalmazottak lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3c16b-118">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="3c16b-119">Jelöljön ki a listából egy dolgozót.</span><span class="sxs-lookup"><span data-stu-id="3c16b-119">From the list, select an employee.</span></span>
3. <span data-ttu-id="3c16b-120">Kattintson az alkalmazott nevére a szállást kérő személy adatainak megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="3c16b-120">Click the employee's name to view details about the employee who is requesting the accommodation.</span></span>
4. <span data-ttu-id="3c16b-121">Bontsa ki a Személyes adatok gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="3c16b-121">Expand the Personal information FastTab.</span></span>
5. <span data-ttu-id="3c16b-122">Kattintson a Szállások pontra.</span><span class="sxs-lookup"><span data-stu-id="3c16b-122">Click Accommodations.</span></span>
6. <span data-ttu-id="3c16b-123">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="3c16b-123">Click New.</span></span>
7. <span data-ttu-id="3c16b-124">A Szállástípus mezőben válassza ki a megfelelő szállást.</span><span class="sxs-lookup"><span data-stu-id="3c16b-124">In the Accommodation type field, select the appropriate accommodation.</span></span> <span data-ttu-id="3c16b-125">Példa: Billentyűzet</span><span class="sxs-lookup"><span data-stu-id="3c16b-125">Example: Keyboard</span></span>
8. <span data-ttu-id="3c16b-126">A Munkafeladat mezőben írja be a munkafeladatot, amelyhez a szállást igényelték.</span><span class="sxs-lookup"><span data-stu-id="3c16b-126">In the Job task field, enter the work task that requires the accommodation.</span></span>
9. <span data-ttu-id="3c16b-127">Adja meg az Állapot mezőben a megfelelő állapotot.</span><span class="sxs-lookup"><span data-stu-id="3c16b-127">In the Status field, enter the appropriate status.</span></span> <span data-ttu-id="3c16b-128">Példa: Ésszerű</span><span class="sxs-lookup"><span data-stu-id="3c16b-128">Example: Reasonable</span></span>
    * <span data-ttu-id="3c16b-129">A következő állapotok érhetők el.</span><span class="sxs-lookup"><span data-stu-id="3c16b-129">The following statuses are available.</span></span> <span data-ttu-id="3c16b-130">A Kért azt jelzi, hogy a szállás létrejött, de még nem ellenőrizték.</span><span class="sxs-lookup"><span data-stu-id="3c16b-130">Requested indicates that the accommodation has been created but not yet reviewed.</span></span> <span data-ttu-id="3c16b-131">Az Ésszerű azt jlezi, hogy a szállás ésszerű-e, és kiadják-e.</span><span class="sxs-lookup"><span data-stu-id="3c16b-131">Reasonable indicates that the accommodation is reasonable and will be granted.</span></span> <span data-ttu-id="3c16b-132">A Méltánytalan nehézség azt jelzi, hogy a szállás túlzott megterhelést jelent a munkáltatónak, ezért megtagadták.</span><span class="sxs-lookup"><span data-stu-id="3c16b-132">Undue hardship indicates that the accommodation will place an unreasonable burden on the employer, and has been denied.</span></span> <span data-ttu-id="3c16b-133">Ebben a példában a kérést azonnal jóváhagyták, mert minimális volt a szállás iránti igény.</span><span class="sxs-lookup"><span data-stu-id="3c16b-133">In this example, the request was approved immediately because the accommodation request was minimal.</span></span>  
10. <span data-ttu-id="3c16b-134">Az Elfogadott mezőben válassza ki azt a személyt, aki elfogadta a szállásigénylést.</span><span class="sxs-lookup"><span data-stu-id="3c16b-134">In the Accepted field, select the person who accepted the accommodation request.</span></span>
11. <span data-ttu-id="3c16b-135">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3c16b-135">Click Select.</span></span>
12. <span data-ttu-id="3c16b-136">Az Elfogadott dátum mezőben adja meg a dátumot és időpontot, amikor a szállás iránti igényt el lett fogadva.</span><span class="sxs-lookup"><span data-stu-id="3c16b-136">In the Accepted date field, enter the date and time when the accommodation request was accepted.</span></span>
13. <span data-ttu-id="3c16b-137">Bontsa ki a Megjegyzés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3c16b-137">Expand the Note section.</span></span>
14. <span data-ttu-id="3c16b-138">A Pénzügy mezőben adjon meg minden olyan adatot vagy erőforrás-költséget, amely segítséget nyújt a szállás kifejtett hatásának megállapításában.</span><span class="sxs-lookup"><span data-stu-id="3c16b-138">In the Financial field, enter any information or resource costs that helps to clarify the impact of the accommodation.</span></span>
    * <span data-ttu-id="3c16b-139">A szállás meg lett tagadva, a Válasz mező segítségével adja meg, hogy miért lett a kérés megtagadva.</span><span class="sxs-lookup"><span data-stu-id="3c16b-139">If the accommodation has been denied, the Reply field can be used to indicate why a request was denied.</span></span>  
15. <span data-ttu-id="3c16b-140">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3c16b-140">Click Save.</span></span>



--- 
title: "Termékmodell útvonalának karbantartása"
description: "Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre."
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 3f6bacc54664c32a7d42f2befc51c420e29ada56
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="maintain-a-route-for-a-product-model"></a><span data-ttu-id="5ecbd-103">Termékmodell útvonalának karbantartása</span><span class="sxs-lookup"><span data-stu-id="5ecbd-103">Maintain a route for a product model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ecbd-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="5ecbd-105">Ez az eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva vezeti Önt végig a folyamaton.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="5ecbd-106">Útvonalművelet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="5ecbd-106">Add a route operation</span></span>
1. <span data-ttu-id="5ecbd-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="5ecbd-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="5ecbd-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5ecbd-110">Válassza ki a Felső kategóriás modellt ehhez a gyakorlathoz.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="5ecbd-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5ecbd-112">Bontsa ki az Útvonalműveletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="5ecbd-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-113">Click Add.</span></span>
7. <span data-ttu-id="5ecbd-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="5ecbd-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="5ecbd-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="5ecbd-117">Útvonalművelet részleteinek megadása</span><span class="sxs-lookup"><span data-stu-id="5ecbd-117">Enter route operation details</span></span>
1. <span data-ttu-id="5ecbd-118">Kattintson az Útvonalműveleti részletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-118">Click Route operation details.</span></span>
2. <span data-ttu-id="5ecbd-119">A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="5ecbd-120">A Műv.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-120">In the Oper.</span></span> <span data-ttu-id="5ecbd-121">Szám</span><span class="sxs-lookup"><span data-stu-id="5ecbd-121">No.</span></span> <span data-ttu-id="5ecbd-122">mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-122">field, enter a number.</span></span>
    * <span data-ttu-id="5ecbd-123">A műveleti számok határozzák meg az útvonalsorrendet.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="5ecbd-124">Egy útvonalművelet egyes tulajdonságainak lehet statikus értékük, vagy hozzá lehet rendelni őket egy attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="5ecbd-125">Az attribútumhoz rendelés következtében az érték a konfiguráció része lesz.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="5ecbd-126">Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="5ecbd-127">Az útvonalcsoport határozza meg az alapvető viselkedést a költségszámítási, a felhasználás és beállítás esetében.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="5ecbd-128">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="5ecbd-129">Kattintson az Idők fülre.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-129">Click the Times tab.</span></span>
7. <span data-ttu-id="5ecbd-130">A Folyamat menny.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-130">In the Process qty.</span></span> <span data-ttu-id="5ecbd-131">mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-131">field, enter a number.</span></span>
    * <span data-ttu-id="5ecbd-132">Határozza meg, hogy mennyi lesz feldolgozva egy művelet során.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-132">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="5ecbd-133">Az Órák/idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-133">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="5ecbd-134">Adja meg az időarányt.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-134">Enter the time ratio.</span></span>  
9. <span data-ttu-id="5ecbd-135">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-135">Select the Set check box.</span></span>
10. <span data-ttu-id="5ecbd-136">Adjon meg egy számot a Futási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-136">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="5ecbd-137">Határozza meg a feldolgozási időt a megadott mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-137">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="5ecbd-138">Kattintson az Erőforrás-követelmények fülre.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-138">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="5ecbd-139">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-139">Click Add.</span></span>
13. <span data-ttu-id="5ecbd-140">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-140">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="5ecbd-141">A Követelmény típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-141">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="5ecbd-142">Döntse el, hogy akar-e megadni konkrét erőforrásokat vagy adottságokat, amelyeket fel kell dolgozniuk.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-142">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="5ecbd-143">A Követelmény mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-143">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="5ecbd-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5ecbd-144">Click OK.</span></span>



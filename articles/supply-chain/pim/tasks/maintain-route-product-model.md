--- 
title: "Termékmodell útvonalának karbantartása"
description: "Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 25d9530fc137b443b99a183b9d10886585c7b65f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="maintain-a-route-for-a-product-model"></a><span data-ttu-id="7ae3c-103">Termékmodell útvonalának karbantartása</span><span class="sxs-lookup"><span data-stu-id="7ae3c-103">Maintain a route for a product model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7ae3c-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="7ae3c-105">Ez az eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva vezeti Önt végig a folyamaton.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="7ae3c-106">Útvonalművelet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="7ae3c-106">Add a route operation</span></span>
1. <span data-ttu-id="7ae3c-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="7ae3c-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="7ae3c-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7ae3c-110">Válassza ki a Felső kategóriás modellt ehhez a gyakorlathoz.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="7ae3c-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7ae3c-112">Bontsa ki az Útvonalműveletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="7ae3c-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-113">Click Add.</span></span>
7. <span data-ttu-id="7ae3c-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="7ae3c-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="7ae3c-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="7ae3c-117">Útvonalművelet részleteinek megadása</span><span class="sxs-lookup"><span data-stu-id="7ae3c-117">Enter route operation details</span></span>
1. <span data-ttu-id="7ae3c-118">Kattintson az Útvonalműveleti részletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-118">Click Route operation details.</span></span>
2. <span data-ttu-id="7ae3c-119">A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="7ae3c-120">A Műv.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-120">In the Oper.</span></span> <span data-ttu-id="7ae3c-121">Szám</span><span class="sxs-lookup"><span data-stu-id="7ae3c-121">No.</span></span> <span data-ttu-id="7ae3c-122">mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-122">field, enter a number.</span></span>
    * <span data-ttu-id="7ae3c-123">A műveleti számok határozzák meg az útvonalsorrendet.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="7ae3c-124">Egy útvonalművelet egyes tulajdonságainak lehet statikus értékük, vagy hozzá lehet rendelni őket egy attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="7ae3c-125">Az attribútumhoz rendelés következtében az érték a konfiguráció része lesz.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="7ae3c-126">Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="7ae3c-127">Az útvonalcsoport határozza meg az alapvető viselkedést a költségszámítási, a felhasználás és beállítás esetében.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="7ae3c-128">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="7ae3c-129">Kattintson az Idők fülre.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-129">Click the Times tab.</span></span>
7. <span data-ttu-id="7ae3c-130">A Folyamat menny. mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-130">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="7ae3c-131">Határozza meg, hogy mennyi lesz feldolgozva egy művelet során.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-131">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="7ae3c-132">Az Órák/idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-132">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="7ae3c-133">Adja meg az időarányt.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-133">Enter the time ratio.</span></span>  
9. <span data-ttu-id="7ae3c-134">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-134">Select the Set check box.</span></span>
10. <span data-ttu-id="7ae3c-135">Adjon meg egy számot a Futási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-135">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="7ae3c-136">Határozza meg a feldolgozási időt a megadott mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-136">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="7ae3c-137">Kattintson az Erőforrás-követelmények fülre.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-137">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="7ae3c-138">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-138">Click Add.</span></span>
13. <span data-ttu-id="7ae3c-139">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-139">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="7ae3c-140">A Követelmény típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-140">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="7ae3c-141">Döntse el, hogy akar-e megadni konkrét erőforrásokat vagy adottságokat, amelyeket fel kell dolgozniuk.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-141">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="7ae3c-142">A Követelmény mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-142">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="7ae3c-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7ae3c-143">Click OK.</span></span>



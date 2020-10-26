---
title: Termékmodell útvonalának karbantartása
description: Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cc41f99085e5f30ae29edce296a5e3752cbabd33
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985269"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="07de9-103">Termékmodell útvonalának karbantartása</span><span class="sxs-lookup"><span data-stu-id="07de9-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="07de9-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="07de9-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="07de9-105">Ez az eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva vezeti Önt végig a folyamaton.</span><span class="sxs-lookup"><span data-stu-id="07de9-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="07de9-106">Útvonalművelet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="07de9-106">Add a route operation</span></span>
1. <span data-ttu-id="07de9-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="07de9-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="07de9-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="07de9-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="07de9-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="07de9-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="07de9-110">Válassza ki a Felső kategóriás modellt ehhez a gyakorlathoz.</span><span class="sxs-lookup"><span data-stu-id="07de9-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="07de9-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="07de9-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="07de9-112">Bontsa ki az Útvonalműveletek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="07de9-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="07de9-113">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="07de9-113">Click Add.</span></span>
7. <span data-ttu-id="07de9-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="07de9-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="07de9-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="07de9-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="07de9-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="07de9-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="07de9-117">Útvonalművelet részleteinek megadása</span><span class="sxs-lookup"><span data-stu-id="07de9-117">Enter route operation details</span></span>
1. <span data-ttu-id="07de9-118">Kattintson az Útvonalműveleti részletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="07de9-118">Click Route operation details.</span></span>
2. <span data-ttu-id="07de9-119">A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="07de9-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="07de9-120">A Műv.</span><span class="sxs-lookup"><span data-stu-id="07de9-120">In the Oper.</span></span> <span data-ttu-id="07de9-121">Szám</span><span class="sxs-lookup"><span data-stu-id="07de9-121">No.</span></span> <span data-ttu-id="07de9-122">mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="07de9-122">field, enter a number.</span></span>
    * <span data-ttu-id="07de9-123">A műveleti számok határozzák meg az útvonalsorrendet.</span><span class="sxs-lookup"><span data-stu-id="07de9-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="07de9-124">Egy útvonalművelet egyes tulajdonságainak lehet statikus értékük, vagy hozzá lehet rendelni őket egy attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="07de9-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="07de9-125">Az attribútumhoz rendelés következtében az érték a konfiguráció része lesz.</span><span class="sxs-lookup"><span data-stu-id="07de9-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="07de9-126">Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="07de9-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="07de9-127">Az útvonalcsoport határozza meg az alapvető viselkedést a költségszámítási, a felhasználás és beállítás esetében.</span><span class="sxs-lookup"><span data-stu-id="07de9-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="07de9-128">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="07de9-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="07de9-129">Kattintson az Idők fülre.</span><span class="sxs-lookup"><span data-stu-id="07de9-129">Click the Times tab.</span></span>
7. <span data-ttu-id="07de9-130">A Folyamat menny. mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="07de9-130">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="07de9-131">Határozza meg, hogy mennyi lesz feldolgozva egy művelet során.</span><span class="sxs-lookup"><span data-stu-id="07de9-131">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="07de9-132">Az Órák/idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="07de9-132">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="07de9-133">Adja meg az időarányt.</span><span class="sxs-lookup"><span data-stu-id="07de9-133">Enter the time ratio.</span></span>  
9. <span data-ttu-id="07de9-134">Jelölje be a Beállít jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="07de9-134">Select the Set check box.</span></span>
10. <span data-ttu-id="07de9-135">Adjon meg egy számot a Futási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="07de9-135">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="07de9-136">Határozza meg a feldolgozási időt a megadott mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="07de9-136">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="07de9-137">Kattintson az Erőforrás-követelmények fülre.</span><span class="sxs-lookup"><span data-stu-id="07de9-137">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="07de9-138">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="07de9-138">Click Add.</span></span>
13. <span data-ttu-id="07de9-139">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="07de9-139">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="07de9-140">A Követelmény típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="07de9-140">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="07de9-141">Döntse el, hogy akar-e megadni konkrét erőforrásokat vagy adottságokat, amelyeket fel kell dolgozniuk.</span><span class="sxs-lookup"><span data-stu-id="07de9-141">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="07de9-142">A Követelmény mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="07de9-142">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="07de9-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="07de9-143">Click OK.</span></span>


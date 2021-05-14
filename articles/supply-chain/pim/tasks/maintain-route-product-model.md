---
title: Termékmodell útvonalának karbantartása
description: Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921265"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="64c94-103">Termékmodell útvonalának karbantartása</span><span class="sxs-lookup"><span data-stu-id="64c94-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="64c94-104">Ezen eljárás futtatásához szükség van egy már létező termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="64c94-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="64c94-105">Ez az eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használva vezeti Önt végig a folyamaton.</span><span class="sxs-lookup"><span data-stu-id="64c94-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>

## <a name="add-a-route-operation"></a><span data-ttu-id="64c94-106">Útvonalművelet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="64c94-106">Add a route operation</span></span>

1. <span data-ttu-id="64c94-107">Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="64c94-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="64c94-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="64c94-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="64c94-109">Válassza ki a Felső kategóriás modellt ehhez a gyakorlathoz.</span><span class="sxs-lookup"><span data-stu-id="64c94-109">Select the High end speaker model for this exercise.</span></span>  
1. <span data-ttu-id="64c94-110">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="64c94-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="64c94-111">Bontsa ki az **Útvonalműveletek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="64c94-111">Expand the **Route operations** section.</span></span>
1. <span data-ttu-id="64c94-112">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64c94-112">Select **Add**.</span></span>
1. <span data-ttu-id="64c94-113">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="64c94-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="64c94-114">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="64c94-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="64c94-115">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64c94-115">Select **Save**.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="64c94-116">Útvonalművelet részleteinek megadása</span><span class="sxs-lookup"><span data-stu-id="64c94-116">Enter route operation details</span></span>

1. <span data-ttu-id="64c94-117">**Útvonalművelet részleteinek** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="64c94-117">Select **Route operation details**.</span></span>
1. <span data-ttu-id="64c94-118">A **Műveletek** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64c94-118">In the **Operation** field, enter or select a value.</span></span>
1. <span data-ttu-id="64c94-119">A **Műveletszám**</span><span class="sxs-lookup"><span data-stu-id="64c94-119">In the **Oper. No.**</span></span> <span data-ttu-id="64c94-120">mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="64c94-120">field, enter a number.</span></span>
    * <span data-ttu-id="64c94-121">A műveleti számok határozzák meg az útvonalsorrendet.</span><span class="sxs-lookup"><span data-stu-id="64c94-121">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="64c94-122">Egy útvonalművelet egyes tulajdonságainak lehet statikus értékük, vagy hozzá lehet rendelni őket egy attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="64c94-122">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="64c94-123">Az attribútumhoz rendelés következtében az érték a konfiguráció része lesz.</span><span class="sxs-lookup"><span data-stu-id="64c94-123">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
1. <span data-ttu-id="64c94-124">Az **Útvonalcsoport** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64c94-124">In the **Route group** field, enter or select a value.</span></span>
    * <span data-ttu-id="64c94-125">Az útvonalcsoport határozza meg az alapvető viselkedést a költségszámítási, a felhasználás és beállítás esetében.</span><span class="sxs-lookup"><span data-stu-id="64c94-125">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
1. <span data-ttu-id="64c94-126">Válassza ki a **Beállítás** fület.</span><span class="sxs-lookup"><span data-stu-id="64c94-126">Select the **Setup** tab.</span></span>
1. <span data-ttu-id="64c94-127">Válassza ki az **Időpontok** fület.</span><span class="sxs-lookup"><span data-stu-id="64c94-127">Select the **Times** tab.</span></span>
1. <span data-ttu-id="64c94-128">A **Folyamat menny.** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="64c94-128">In the **Process qty.** field, enter a number.</span></span>
    * <span data-ttu-id="64c94-129">Határozza meg, hogy mennyi lesz feldolgozva egy művelet során.</span><span class="sxs-lookup"><span data-stu-id="64c94-129">Determine how many will be processed during one operation.</span></span>  
1. <span data-ttu-id="64c94-130">Az **Órák/idő** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="64c94-130">In the **Hours/time** field, enter a number.</span></span>
    * <span data-ttu-id="64c94-131">Adja meg az időarányt.</span><span class="sxs-lookup"><span data-stu-id="64c94-131">Enter the time ratio.</span></span>  
1. <span data-ttu-id="64c94-132">Jelölje be a **Beállít** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="64c94-132">Select the **Set** check box.</span></span>
1. <span data-ttu-id="64c94-133">Adjon meg egy számot a **Futási idő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="64c94-133">In the **Run time** field, enter a number.</span></span>
    * <span data-ttu-id="64c94-134">Határozza meg a feldolgozási időt a megadott mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="64c94-134">Determine the processing time for the quantity that you have specified.</span></span>  
1. <span data-ttu-id="64c94-135">Válassza ki az **Erőforrás-követelmények** fület.</span><span class="sxs-lookup"><span data-stu-id="64c94-135">Select the **Resource requirements** tab.</span></span>
1. <span data-ttu-id="64c94-136">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64c94-136">Select **Add**.</span></span>
1. <span data-ttu-id="64c94-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="64c94-137">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="64c94-138">A **Követelmény típusa** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64c94-138">In the **Requirement type** field, select an option.</span></span>
    * <span data-ttu-id="64c94-139">Döntse el, hogy akar-e megadni konkrét erőforrásokat vagy adottságokat, amelyeket fel kell dolgozniuk.</span><span class="sxs-lookup"><span data-stu-id="64c94-139">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
1. <span data-ttu-id="64c94-140">A **Követelmény** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="64c94-140">In the **Requirement** field, enter or select a value.</span></span>
1. <span data-ttu-id="64c94-141">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64c94-141">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
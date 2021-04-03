---
title: Üzemi erőforrás létrehozása
description: Az üzemi erőforrás hajtja végre egy projekt vagy egy termelési folyamat tevékenységeit.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 514b0b27065b4318891a84f364b39e8e378d6a4a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255085"
---
# <a name="create-an-operations-resource"></a><span data-ttu-id="dd34b-103">Üzemi erőforrás létrehozása</span><span class="sxs-lookup"><span data-stu-id="dd34b-103">Create an operations resource</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd34b-104">Az üzemi erőforrás hajtja végre egy projekt vagy egy termelési folyamat tevékenységeit.</span><span class="sxs-lookup"><span data-stu-id="dd34b-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="dd34b-105">Ez az eljárás bemutatja, hogyan határozzon meg egy üzemi erőforrást.</span><span class="sxs-lookup"><span data-stu-id="dd34b-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="dd34b-106">Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="dd34b-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="dd34b-107">Ugrás az Erőforrások parancsra.</span><span class="sxs-lookup"><span data-stu-id="dd34b-107">Go to Resources.</span></span>
2. <span data-ttu-id="dd34b-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dd34b-108">Click New.</span></span>
3. <span data-ttu-id="dd34b-109">Érték beírása az Erőforrás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="dd34b-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="dd34b-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="dd34b-111">Határozza meg a kapacitás és a felhasználási paramétereit</span><span class="sxs-lookup"><span data-stu-id="dd34b-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="dd34b-112">Bontsa ki a Művelet szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dd34b-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="dd34b-113">Adjon meg egy számot a Selejtszázalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="dd34b-114">A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="dd34b-115">Adja meg azt a költségkategóriát, amely meghatározza, hogyan számolhatja el a beállítás költségét.</span><span class="sxs-lookup"><span data-stu-id="dd34b-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="dd34b-116">A Lefutásiidő-kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="dd34b-117">Adja meg azt a költségkategóriát, amely meghatározza, hogyan számolhatja el a futtatási idő költségét.</span><span class="sxs-lookup"><span data-stu-id="dd34b-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="dd34b-118">A Mennyiségkategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="dd34b-119">Adja meg azt a költségkategóriát, amely meghatározza, hogyan lehet a elszámolni a kimeneti mennyiségeken alapuló erőforrásköltséget.</span><span class="sxs-lookup"><span data-stu-id="dd34b-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="dd34b-120">Egy lehetőség kiválasztása a Kapacitásegység mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="dd34b-121">Annak az egységnek a megadása, amelyben az üzemi erőforrás kapacitását kifejezik.</span><span class="sxs-lookup"><span data-stu-id="dd34b-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="dd34b-122">Adjon meg egy számot a Kapacitás mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="dd34b-123">Adjon meg egy számot a Hatékonyság (százalék) mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="dd34b-124">Adja meg, hogy milyen hatékonyságot vár el az üzemi erőforrástól.</span><span class="sxs-lookup"><span data-stu-id="dd34b-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="dd34b-125">A hatékonysági százalék beállítja az üzemi erőforrás teljesítményét és befolyásolja az erőforrás lefoglalt időt.</span><span class="sxs-lookup"><span data-stu-id="dd34b-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="dd34b-126">A Műveletütemezés százalék mezőjében adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="dd34b-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="dd34b-127">Adja meg az üzemi erőforrások kapacitásának azt a maximális százalékát, amelyet a műveletek ütemezésében használni kíván.</span><span class="sxs-lookup"><span data-stu-id="dd34b-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="dd34b-128">Válassza az Igen lehetőséget a Véges kapacitás mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="dd34b-129">Állítsa ezt a beállítást Igen-re, ha az üzemi erőforrást a ténylegesen elérhető kapacitás alapján kell ütemezni, és ha a meglévő kapacitásfoglalásokat figyelembe kell venni.</span><span class="sxs-lookup"><span data-stu-id="dd34b-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="dd34b-130">Ha ebben a beállításban Nem szerepel, az üzemi erőforrás feltételezett kapacitása korlátlan, és előfordulhat, hogy az erőforrás túl van foglalva.</span><span class="sxs-lookup"><span data-stu-id="dd34b-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="dd34b-131">Válassza az Igen lehetőséget a Szűk keresztmetszetű erőforrás mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="dd34b-132">Munkaidők meghatározása</span><span class="sxs-lookup"><span data-stu-id="dd34b-132">Define working times</span></span>
1. <span data-ttu-id="dd34b-133">Bontsa ki a Naptárak szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dd34b-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="dd34b-134">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dd34b-134">Click Add.</span></span>
3. <span data-ttu-id="dd34b-135">A Naptárak mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="dd34b-136">Adja meg azt a munkaidőnaptárt, amely meghatározza az erőforrás kapacitását (órában).</span><span class="sxs-lookup"><span data-stu-id="dd34b-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="dd34b-137">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="dd34b-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="dd34b-138">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="dd34b-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="dd34b-139">Erőforrás-képességek meghatározása</span><span class="sxs-lookup"><span data-stu-id="dd34b-139">Define resource capabilities</span></span>
1. <span data-ttu-id="dd34b-140">Bontsa ki Képességek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dd34b-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="dd34b-141">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dd34b-141">Click Add.</span></span>
    * <span data-ttu-id="dd34b-142">A képesség egy üzemi erőforrás képességét jelenti egy adott tevékenység végrehajtására.</span><span class="sxs-lookup"><span data-stu-id="dd34b-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="dd34b-143">Az ütemezési motor erőforrásokat utal ki azáltal, hogy összekapcsolja az egyes tevékenységek erőforrás-követelményeit az elérhető üzemi erőforrásokkal.</span><span class="sxs-lookup"><span data-stu-id="dd34b-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="dd34b-144">A Képesség mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="dd34b-145">Adjon meg egy számot a Szint mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="dd34b-146">Adja meg azt a szakértelemszintet, amellyel az erőforrás feldolgozza a képességet.</span><span class="sxs-lookup"><span data-stu-id="dd34b-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="dd34b-147">Adjon meg egy számot a Prioritás mezőben.</span><span class="sxs-lookup"><span data-stu-id="dd34b-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="dd34b-148">Adja meg az üzemi erőforrás prioritását a képesség tekintetében.</span><span class="sxs-lookup"><span data-stu-id="dd34b-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="dd34b-149">A prioritás szerint ütemezéskor a legmagasabb prioritású (legkisebb numerikus értékű) üzemi erőforrás lesz elsőként kijelölve.</span><span class="sxs-lookup"><span data-stu-id="dd34b-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="dd34b-150">Erőforrás hozzárendelése az erőforráscsoporthoz</span><span class="sxs-lookup"><span data-stu-id="dd34b-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="dd34b-151">Bontsa ki az Erőforráscsoportok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="dd34b-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="dd34b-152">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="dd34b-152">Click Add.</span></span>
    * <span data-ttu-id="dd34b-153">Az erőforráscsoport határozza meg a telephelyet, a termelési egységet és a raktárkörnyezetet az üzemi erőforrások számára.</span><span class="sxs-lookup"><span data-stu-id="dd34b-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="dd34b-154">Az üzemi erőforrást csak akkor lehet ütemezni, ha hozzá van rendelve egy erőforráscsoporthoz, és csak azon a telephelyen, ahol az erőforráscsoport található.</span><span class="sxs-lookup"><span data-stu-id="dd34b-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="dd34b-155">Az Erőforráscsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="dd34b-156">A Bemeneti hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dd34b-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="dd34b-157">Adja meg annak a raktárnak az elhelyezkedését, ahonnan az üzemi erőforrás anyagot használ.</span><span class="sxs-lookup"><span data-stu-id="dd34b-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
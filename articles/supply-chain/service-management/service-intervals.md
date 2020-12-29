---
title: Szolgáltatás intervallumai
description: A szerviz intervalluma azt a gyakoriságot jelzi, amellyel a szervizrendeléssorok létrejönnek a szervizrendelések automatikus létrehozása esetén.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1027a6a1ddb1057ba039382d394522d6f9538a90
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429606"
---
# <a name="service-intervals"></a><span data-ttu-id="333e2-103">Szolgáltatás intervallumai</span><span class="sxs-lookup"><span data-stu-id="333e2-103">Service intervals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="333e2-104">A szolgáltatási szerződés intervalluma azt a gyakoriságot jelzi, amellyel a szervizrendeléssorok létrejönnek a szervizrendelések automatikus létrehozása esetén.</span><span class="sxs-lookup"><span data-stu-id="333e2-104">The service agreement interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders automatically.</span></span>

<span data-ttu-id="333e2-105">Ha automatikusan hoz létre szervizrendeléseket, akkor a rendelés sorai a szerződéssor kezdő dátumától kezdve a szolgáltatási szerződés sorára meghatározott időközönként jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="333e2-105">When you create service orders automatically, service order lines are created according to the interval that you have specified for the service agreement line from the start date of the agreement line.</span></span>

<span data-ttu-id="333e2-106">Ha az **Intervallum** mező üres a **Szolgáltatási szerződések** lap valamelyik szerződéssorában, akkor az adott sor egyszeri eseményt jelöl, amely nem vesz részt a szervizrendelések ismételt létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="333e2-106">If the **Interval** field of a service agreement line in the **Service agreements** page is blank, the line is a one-time event, and it is not used to create service orders repeatedly.</span></span>

## <a name="example"></a><span data-ttu-id="333e2-107">Példa</span><span class="sxs-lookup"><span data-stu-id="333e2-107">Example</span></span>

<span data-ttu-id="333e2-108">Ez a példa azt mutatja be, hogy miként befolyásolja a szerviz intervalluma a szolgáltatási szerződés sorait és a szervizrendeléssorokat egy szervizrendelésnél.</span><span class="sxs-lookup"><span data-stu-id="333e2-108">This example illustrates how a service interval will affect service agreement lines and service order lines on a service order.</span></span>

### <a name="create-a-service-agreement"></a><span data-ttu-id="333e2-109">Szolgáltatási szerződés létrehozása</span><span class="sxs-lookup"><span data-stu-id="333e2-109">Create a service agreement</span></span>

<span data-ttu-id="333e2-110">Először hozzon létre egy szolgáltatási szerződést, és állítsa a **Szervizrendelések kombinálása** beállítást **Szolgáltatási szerződés szerint** értékre.</span><span class="sxs-lookup"><span data-stu-id="333e2-110">First, you create a service agreement and set the **Combine service orders** option to **By service agreement**.</span></span>

1. <span data-ttu-id="333e2-111">Kattintson a **Szolgáltatási szerződések** pontra</span><span class="sxs-lookup"><span data-stu-id="333e2-111">Click **Service agreements**</span></span>
2. <span data-ttu-id="333e2-112">A **Műveleti ablaktáblán**, a **Szolgáltatási szerződés** lapon, az **Új** csoportban, kattintson a **Szolgáltatási szerződés** lehetőségre egy új szolgáltatási szerződés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="333e2-112">On the **Action Pane**, on the **Service agreement** tab, in the **New** group, click **Service agreement** to create a new service agreement.</span></span>
3. <span data-ttu-id="333e2-113">Adjon meg egy leírást, válasszon ki egy projektet a **Projektazonosító** mezőben, és adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="333e2-113">Enter a description, select a project in the **Project ID** field, and enter a date in the **Start date** field.</span></span>
4. <span data-ttu-id="333e2-114">A **Szervizrendelések kombinálása** mezőben válassza ki a **Szolgáltatási szerződés szerint** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="333e2-114">In the **Combine service orders** field, select **By service agreement**.</span></span>

<span data-ttu-id="333e2-115">Ezzel létrehozta a következő szolgáltatási szerződést:</span><span class="sxs-lookup"><span data-stu-id="333e2-115">You have now created the following service agreement:</span></span>

| <span data-ttu-id="333e2-116">Project</span><span class="sxs-lookup"><span data-stu-id="333e2-116">Project</span></span>      | <span data-ttu-id="333e2-117">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="333e2-117">Start date</span></span>                                                                         |
|--------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="333e2-118">Saját projekt</span><span class="sxs-lookup"><span data-stu-id="333e2-118">Your project</span></span> | <span data-ttu-id="333e2-119">A projektnél megadott dátum.</span><span class="sxs-lookup"><span data-stu-id="333e2-119">The date you specified for the project.</span></span> <span data-ttu-id="333e2-120">Ebben a példában az aktuális dátumot használjuk.</span><span class="sxs-lookup"><span data-stu-id="333e2-120">In this example, the current date is used.</span></span> |

### <a name="create-a-service-agreement-line"></a><span data-ttu-id="333e2-121">Szolgáltatásiszerződés-sor létrehozása</span><span class="sxs-lookup"><span data-stu-id="333e2-121">Create a service agreement line</span></span>

<span data-ttu-id="333e2-122">A következő lépésben hozzon létre egy szolgáltatásiszerződés-sort, amelynek tranzakciótípusa **Óra**.</span><span class="sxs-lookup"><span data-stu-id="333e2-122">Next, you create a service agreement line that has the transaction type **Hour**.</span></span>

<span data-ttu-id="333e2-123">A példa jelen részének végrehajtásához létre kell hoznia egy 10 napos szolgáltatás-intervallumot a **Szolgáltatás-intervallum** lapon.</span><span class="sxs-lookup"><span data-stu-id="333e2-123">To complete this part of the example, you must create a service interval of 10 days in the **Service intervals** page.</span></span> 

1. <span data-ttu-id="333e2-124">Válassza ki az imént létrehozott szolgáltatási szerződést.</span><span class="sxs-lookup"><span data-stu-id="333e2-124">Select the service agreement that you just created.</span></span> 
2. <span data-ttu-id="333e2-125">A **Sorok** gyorslapon kattintson a **Hozzáadás** gombra egy új sor létrehozásához a **Szolgáltatási szerződések** lapon.</span><span class="sxs-lookup"><span data-stu-id="333e2-125">On the **Lines** FastTab, click the **Add** button to create a new line in the lower pane of the **Service agreements** page.</span></span>
3. <span data-ttu-id="333e2-126">Válassza ki az **Óra** lehetőséget a **Tranzakció típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="333e2-126">In the **Transaction type** field, select **Hour**.</span></span>
4. <span data-ttu-id="333e2-127">A **Dolgozó** mezőben válassza ki azt a dolgozót, aki elvégzi a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="333e2-127">In the **Worker** field, select the worker who will deliver the service.</span></span>
5. <span data-ttu-id="333e2-128">A **Szolgáltatás intervalluma** mezőben válassza ki a 10 napos intervallumot.</span><span class="sxs-lookup"><span data-stu-id="333e2-128">In the **Service interval** field, select the 10 days interval.</span></span>

<span data-ttu-id="333e2-129">Ezzel létrehozta a szolgáltatásiszerződés-sort a következő adatokkal:</span><span class="sxs-lookup"><span data-stu-id="333e2-129">You have now created a service agreement line with the following information:</span></span>

| <span data-ttu-id="333e2-130">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="333e2-130">Transaction type</span></span> | <span data-ttu-id="333e2-131">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="333e2-131">Start date</span></span>                               | <span data-ttu-id="333e2-132">Szolgáltatás intervalluma</span><span class="sxs-lookup"><span data-stu-id="333e2-132">Service interval</span></span> |
|------------------|------------------------------------------|------------------|
| <span data-ttu-id="333e2-133">Óra</span><span class="sxs-lookup"><span data-stu-id="333e2-133">Hour</span></span>             | <span data-ttu-id="333e2-134">Az aktuális dátum.</span><span class="sxs-lookup"><span data-stu-id="333e2-134">The current date.</span></span>                        | <span data-ttu-id="333e2-135">10 naponta</span><span class="sxs-lookup"><span data-stu-id="333e2-135">Every 10 days</span></span>    |
| <span data-ttu-id="333e2-136">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="333e2-136">Worker</span></span>           | <span data-ttu-id="333e2-137">A szolgáltatást végző dolgozó.</span><span class="sxs-lookup"><span data-stu-id="333e2-137">The worker who will perform the service.</span></span> |                  |

<span data-ttu-id="333e2-138">Nincs megadott időszak a sornál.</span><span class="sxs-lookup"><span data-stu-id="333e2-138">There is no time window specified for the line.</span></span> 

### <a name="create-planned-service-orders"></a><span data-ttu-id="333e2-139">Tervezett szervizrendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="333e2-139">Create planned service orders</span></span>

<span data-ttu-id="333e2-140">Ekkor létrehozhatja a tervezett szervizrendeléseket és azok sorait a következő hónapra.</span><span class="sxs-lookup"><span data-stu-id="333e2-140">You can now create planned service orders and service order lines for the coming month.</span></span>

1. <span data-ttu-id="333e2-141">A **Szolgáltatási szerződések** lap **műveleti ablaktábláján**, a **Szállítás** lapon kattintson a **Tervezett szervizrendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="333e2-141">In the **Service agreements** page, on the **Action Pane**, on the **Deliver** tab, click **Planned service orders**.</span></span>
2. <span data-ttu-id="333e2-142">A **Szervizrendelések létrehozása** lapon adja meg az aktuális dátumot a **Kezdő dátum** mezőben, illetve az aktuális dátum után egy hónappal lévő dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="333e2-142">In the **Create service orders** page, enter the current date in the **From date** field and a date that is one month from the current date in the **To date** field.</span></span>
3. <span data-ttu-id="333e2-143">Állítsa az **Óra** csúszkát **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="333e2-143">Set the **Hour** slider to **Yes**.</span></span> 
4. <span data-ttu-id="333e2-144">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="333e2-144">Click **OK**.</span></span>

<span data-ttu-id="333e2-145">Mivel a szervizrendelésen nincs csoportosítás (amit a **Szolgáltatási szerződés szerint** lehetőség jelez a **Szervizrendelések kombinálása** beállításban), ezért szervizrendelésenként egy szervizrendeléssor jön létre.</span><span class="sxs-lookup"><span data-stu-id="333e2-145">Because there is no grouping on the service order (defined by the **By service agreement** option in the **Combine service orders** field), one service order line is created per service order.</span></span>

### <a name="service-orders-created"></a><span data-ttu-id="333e2-146">A létrehozott szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="333e2-146">Service orders created</span></span>

<span data-ttu-id="333e2-147">Az ebben a példányban létrehozott három szervizrendeléssor a **Szervizrendelések létrehozása** párbeszédpanelen beállított időkeretbe esik.</span><span class="sxs-lookup"><span data-stu-id="333e2-147">Three service order lines have been created within the time frame that you specified in the **Create service orders** dialog box.</span></span> <span data-ttu-id="333e2-148">A szervizrendeléseket a **Szolgáltatási szerződések** lapon tekintheti meg (**Műveleti ablaktábla** \> **Szállítás** lap \>**Megjelenítés** gomb).</span><span class="sxs-lookup"><span data-stu-id="333e2-148">You can view the service order lines in the **Service agreements** page (**Action Pane** \> **Deliver** tab \>**View** button).</span></span>

## <a name="related-topics"></a><span data-ttu-id="333e2-149">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="333e2-149">Related topics</span></span>

[<span data-ttu-id="333e2-150">Szolgáltatás intervallumainak beállítása</span><span class="sxs-lookup"><span data-stu-id="333e2-150">Set up service intervals</span></span>](set-up-service-intervals.md)  


---
title: "Termelési rendelések kiadása"
description: "A kiadott termelési rendelés olyan rendelés, amely engedélyt kapott termelésre. A „Kiadva” kifejezés, egy a termelés rendelési ciklus állapotát leíró elnevezés. Jelentése, hogy a termelési rendelés készen áll a raktári folyamatokra és az értékesítésre."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 9b9009c714445871c15363c26829da812e56c688
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="release-production-orders"></a><span data-ttu-id="5ac9c-104">Termelési rendelések kiadása</span><span class="sxs-lookup"><span data-stu-id="5ac9c-104">Release production orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5ac9c-105">A kiadott termelési rendelés olyan rendelés, amely engedélyt kapott termelésre.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-105">A released production order is an order that has been authorized for production.</span></span> <span data-ttu-id="5ac9c-106">A „Kiadva” kifejezés, egy a termelés rendelési ciklus állapotát leíró elnevezés. Jelentése, hogy a termelési rendelés készen áll a raktári folyamatokra és az értékesítésre.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-106">The term Released is used to describe a state in the production order life cycle, where the production order is available for execution on the production shop floor and for warehouse processes.</span></span> 

<a name="characteristics-of-the-released-state"></a><span data-ttu-id="5ac9c-107">A Kiadott állapot szerinti jellemzők</span><span class="sxs-lookup"><span data-stu-id="5ac9c-107">Characteristics of the Released state</span></span>
-------------------------------------

<span data-ttu-id="5ac9c-108">A **Kiadott** folyamatállapot a termelési rendelés életciklusának egy állapota.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-108">The **Released** state is one state in the production order life cycle.</span></span> <span data-ttu-id="5ac9c-109">A termelési rendelések, melyek **Kiadott** állapotban vannak, végrehajtásra elérhetők a termelési üzem és a raktárkezelési folyamatok számára.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-109">Production orders that are in the **Released** state are available for execution on the production shop floor and for warehouse processes.</span></span> <span data-ttu-id="5ac9c-110">A **Kiadott** állapotát a következő jellemzőkkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="5ac9c-110">The **Released** state has the following characteristics:</span></span>

-   <span data-ttu-id="5ac9c-111">A termelési rendelést a **Kiadott** állapotra vagy a termelési rendelés, vagy a kötegfolyamat használatával lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-111">A production order can be changed to the **Released** state either from the production order or by using a batch process.</span></span> <span data-ttu-id="5ac9c-112">A termelési rendelés is automatikusan is frissíthető a tervezett termelési rendelésekből, amelyeket a **Megerősítési időkorlát** mezőben az **Alapterv** oldalon lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-112">The production order can also be updated automatically from planned production orders that are firmed by using the **Firming time fence** field on the **Master plan** page.</span></span>
-   <span data-ttu-id="5ac9c-113">A **Kiadott** folyamatállapot jelzi, hogy az üzemi dolgozók (operátorok) elindíthatják a termelési feladatokat az üzemben.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-113">The **Released** state is the signal for the shop floor operators (operators) to start executing the production jobs on the shop floor.</span></span>
-   <span data-ttu-id="5ac9c-114">Termelési dokumentumok, például útvonalkártyák, útvonalfeladatok és a feladatkártyák a termelési feladatokkal kapcsolatban tartalmaznak tájékoztatást, és kiállíthatók.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-114">Production papers, such as route cards, route jobs, and jobs cards provide information about production jobs and can be issued.</span></span>
-   <span data-ttu-id="5ac9c-115">A ténylegesen lefoglalt anyagok esetében raktár munka generálódik, hogy az anyagokat ki lehessen tárolni a termelési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-115">For materials that are physically reserved, warehouse work is generated to pick materials for the production order.</span></span>

## <a name="releasing-jobs-to-the-shop-floor"></a><span data-ttu-id="5ac9c-116">Feladatok kiadása az üzem számára</span><span class="sxs-lookup"><span data-stu-id="5ac9c-116">Releasing jobs to the shop floor</span></span>
<span data-ttu-id="5ac9c-117">Egy termelési rendelést kiadását követően, a hozzá kapcsolódó termelési feladatok láthatók, és készen állnak a regisztrációra.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-117">After a production order is released, production jobs that are related to the order are visible and ready for registration.</span></span> <span data-ttu-id="5ac9c-118">A kezelők feladatregisztrációkat végezhetnek – például indítás, leállítás és befejezés – a **Feladatkártya-terminál** vagy a **Feladatkártya-eszköz** lapon.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-118">The operators can make job registrations, such as Start, Stop, and Completion, on either the **Job card terminal** page or the **Job card device** page.</span></span> <span data-ttu-id="5ac9c-119">A regisztrált idő és mennyiség automatikusan átkerül a regisztrációs lapokról a termelési naplókba, hogy nyomon követhető legyen a felhasznált idő és mennyiség.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-119">The registered time and quantity are automatically transferred from the registration pages to production journals to keep track of the consumed time and quantity.</span></span>

## <a name="route-cards"></a><span data-ttu-id="5ac9c-120">Útvonalkártyák</span><span class="sxs-lookup"><span data-stu-id="5ac9c-120">Route cards</span></span>
<span data-ttu-id="5ac9c-121">Az útvonalkártya áttekintő információt tartalmaz az útvonal és a művelet beállítása, illetve a feladatütemezési módszerek alapján.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-121">A route card provides an overview of information that comes from route and operation setups, and from operation and job scheduling methods.</span></span>

## <a name="route-jobs"></a><span data-ttu-id="5ac9c-122">Munkatervek</span><span class="sxs-lookup"><span data-stu-id="5ac9c-122">Route jobs</span></span>
<span data-ttu-id="5ac9c-123">Az útvonalfeladat egy művelet mindegyik feladatát részletesen felsorolja, és tartalmazza a beállítási, feldolgozási, várakozási és szállítási időket is.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-123">A route job lists each job of an operation in detail, and includes setup, process, queue, and transportation times.</span></span> <span data-ttu-id="5ac9c-124">Például egy festési művelethez olyan egyéni feladatok lehetnek szükségesek, mint a beállítási és a futási idő a festési feladathoz, és a várakozási idő a száradáshoz.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-124">For example, an operation such as painting might require individual jobs, such as setup time, run time for the painting process, and queue time for drying.</span></span>

## <a name="job-cards"></a><span data-ttu-id="5ac9c-125">Feladatkártyák</span><span class="sxs-lookup"><span data-stu-id="5ac9c-125">Job cards</span></span>
<span data-ttu-id="5ac9c-126">A feladatkártya egy adott művelet egyéni feladatszámait sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-126">A job card lists the individual job numbers of a particular operation.</span></span> <span data-ttu-id="5ac9c-127">Egy feladat jelenik meg minden oldalon.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-127">One job appears on each page.</span></span> <span data-ttu-id="5ac9c-128">A feladatkártyán szereplő feladatok és becsült idejük az útvonal és a művelet beállítási adataiból származik.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-128">The jobs that are included on a job card, and their estimated times, come from the route and operation setup information.</span></span> <span data-ttu-id="5ac9c-129">A feladatkártyáról megnyithatók a **Termelésinapló-sorok**, a **Feladatkártya**oldalon.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-129">From a job card, you can open the **Production journal lines**, **job card** page.</span></span> <span data-ttu-id="5ac9c-130">A műveleti erőforrásokat működtető emberek visszajelzést adhatnak a termelési folyamatról.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-130">People who run operations resources can provide feedback about the production process.</span></span> <span data-ttu-id="5ac9c-131">Vannak olyan mezők, ahol felhasználási statisztikai adatokat és egyéb információkat adhatnak meg, például a hibák mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-131">There are fields where you can enter consumption statistics and information such as the error quantity.</span></span>

## <a name="warehouse-work-for-raw-material-picking"></a><span data-ttu-id="5ac9c-132">Raktári munka a nyersanyag-kitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-132">Warehouse work for raw material picking</span></span>
<span data-ttu-id="5ac9c-133">A nyersanyag-kitárolási munka a kiadás során jön létre.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-133">Work for raw material picking is generated during release.</span></span> <span data-ttu-id="5ac9c-134">A munka csak ahhoz az anyagmennyiséghez jön létre, amelyet ténylegesen lefoglaltak a termelési rendeléshez a rendelés kiadása előtt.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-134">Work is generated only for the quantity of materials that was physically reserved for the production order before the order was released.</span></span> <span data-ttu-id="5ac9c-135">A következő beállítás szükséges raktári munka létrehozásához a nyersanyag-kitároláshoz:</span><span class="sxs-lookup"><span data-stu-id="5ac9c-135">The following setup is required to generate warehouse work for raw material picking:</span></span>

-   <span data-ttu-id="5ac9c-136">A nyersanyag-kitárolási helyutasítás azt határozza meg, hogy melyik helyen lévő raktárból legyenek az anyagok kitárolva.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-136">A location directive for raw materials picking that determines which warehouse location to pick the materials in</span></span>
-   <span data-ttu-id="5ac9c-137">Hullámsablon nyersanyagok számára, ahol a raktári munka végrehajtásához szükséges szabályok konfigurálódnak.</span><span class="sxs-lookup"><span data-stu-id="5ac9c-137">A wave template for raw materials, where policies for the execution of warehouse work are configured</span></span>
-   <span data-ttu-id="5ac9c-138">Termelések beérkezési helye, amely meghatározza, hogy hová teszik az anyagokat</span><span class="sxs-lookup"><span data-stu-id="5ac9c-138">A production input location that determines where materials are put</span></span>






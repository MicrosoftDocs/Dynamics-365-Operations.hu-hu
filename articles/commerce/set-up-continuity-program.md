---
title: Folytonossági programok beállítása hívásközpontok számára
description: Ez a cikk bemutatja, hogyan állíthat be folytonos programot egy hívásközpontban.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 738841407b63ef604da092b7c8f4d0f2064d3886
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412740"
---
# <a name="set-up-continuity-programs-for-call-centers"></a><span data-ttu-id="2e328-103">Folytonossági programok beállítása hívásközpontok számára</span><span class="sxs-lookup"><span data-stu-id="2e328-103">Set up continuity programs for call centers</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2e328-104">Ez a cikk bemutatja, hogyan állíthat be folytonos programot egy hívásközpontban.</span><span class="sxs-lookup"><span data-stu-id="2e328-104">This article describes how to set up a continuity program for a call center.</span></span>

<span data-ttu-id="2e328-105">A folytonos program (más néven ismétlődő rendelés) keretében a vevők egy előre definiált ütemezés alapján rendszeres szállítmányokat kapnak.</span><span class="sxs-lookup"><span data-stu-id="2e328-105">In a continuity program, which is also known as a recurring order program, customers receive regular product shipments according to a predefined schedule.</span></span> <span data-ttu-id="2e328-106">Az egyes szállítmányok különböző termékeket is tartalmazhatnak, mint például „A hónap bestsellere” klubban, más esetekben pedig ugyanazt a terméket küldik.</span><span class="sxs-lookup"><span data-stu-id="2e328-106">Each shipment can contain a different product, as in the case of a book-of-the-month club, or the same product can be sent repeatedly.</span></span> <span data-ttu-id="2e328-107">A folytonossági program beállításához a következő feladatokat kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="2e328-107">To set up a continuity program, you must complete the following tasks.</span></span>

1. <span data-ttu-id="2e328-108">A folytonos paraméterek beállítása a **Hívásközponti paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2e328-108">Set the continuity parameters on the **Call center parameters** page.</span></span>
2. <span data-ttu-id="2e328-109">Hozzon létre egy folytonossági programot, amelyben megadja az olyan részleteket, mint például a fizetési ütemezés, a szállítmányok ütemezése, és hogy előzetes számlázást használ-e.</span><span class="sxs-lookup"><span data-stu-id="2e328-109">Create a continuity program that specifies details such as the payment schedule, the timing of the shipments, and whether billing is up front.</span></span> <span data-ttu-id="2e328-110">Emellett meg kell adnia a folytonos programban használt termékek listáját is.</span><span class="sxs-lookup"><span data-stu-id="2e328-110">You must also add a list of products that are included in the continuity program.</span></span> <span data-ttu-id="2e328-111">Minden termék eseményazonosító számot kap, amely az egyesnél kezdődően rendelésenként nő.</span><span class="sxs-lookup"><span data-stu-id="2e328-111">Each product receives an event ID number that is assigned sequentially, beginning with 1.</span></span> <span data-ttu-id="2e328-112">Az eseményazonosító a termékek eljuttatásának sorrendjét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="2e328-112">The event IDs determine the order that products are sent in.</span></span>

    - <span data-ttu-id="2e328-113">Ha a vevő minden szállítmányba egy másik terméket kap, akkor a termékeket az eseményazonosító alapján felállított sorrendben küldik ki, az aktuális eseménnyel kezdve.</span><span class="sxs-lookup"><span data-stu-id="2e328-113">If customers receive a different product in each shipment, the products are sent in sequential order, based on their event IDs and beginning with the current event.</span></span>
    - <span data-ttu-id="2e328-114">Ha a vevő minden szállítmányban ugyanazt a terméket kapja, akkor a list csak egy terméket tartalmaz, egyetlen eseményazonosítóval.</span><span class="sxs-lookup"><span data-stu-id="2e328-114">If customers receive the same product in each shipment, the list contains only one product that has one event ID.</span></span> <span data-ttu-id="2e328-115">Ugyanaz az esemény ismétlődik meg minden alkalommal.</span><span class="sxs-lookup"><span data-stu-id="2e328-115">The same event occurs repeatedly.</span></span> <span data-ttu-id="2e328-116">Megadhatja, hogy hányszor szeretné ismételni az egyes eseményeket.</span><span class="sxs-lookup"><span data-stu-id="2e328-116">You can specify how many times each event is repeated.</span></span>

3. <span data-ttu-id="2e328-117">Hozzon létre egy szülő terméket, amely a 2. feladatban létrehozott folytonossági programot jelöli ki.</span><span class="sxs-lookup"><span data-stu-id="2e328-117">Create a parent product that represents the continuity program that you created in task 2.</span></span> <span data-ttu-id="2e328-118">Ha ezt a terméket hozzáadja egy értékesítési rendeléshez, megnyílik a **Folytonosság** oldal.</span><span class="sxs-lookup"><span data-stu-id="2e328-118">If you add this product to a sales order, the **Continuity** page opens.</span></span> <span data-ttu-id="2e328-119">Ezek után ezen az oldalon hozhatja létre a tényleges folytonos megrendelést.</span><span class="sxs-lookup"><span data-stu-id="2e328-119">You can then use that page to create the actual continuity order.</span></span> <span data-ttu-id="2e328-120">A szülőtermék nem határozza meg, hogy a vevő milyen termékeket kap az egyes szállításokban.</span><span class="sxs-lookup"><span data-stu-id="2e328-120">The parent product doesn't specify the individual products that the customer receives in each shipment.</span></span>

<span data-ttu-id="2e328-121">A folytonos program beállítása után (amelyről a fenti részben olvashat), készen áll rá, hogy folytonos megrendelést hozzon létre egy vevő részére.</span><span class="sxs-lookup"><span data-stu-id="2e328-121">After you've set up a continuity program as described above, you can create a continuity order for a customer.</span></span> <span data-ttu-id="2e328-122">Egyes esetekben a következő, kiegészítő karbantartási feladatokra is szükség lehet</span><span class="sxs-lookup"><span data-stu-id="2e328-122">You might also have to perform the following additional maintenance tasks.</span></span>

- <span data-ttu-id="2e328-123">**Frissítse a folytonosság aktuális eseményidőszakát** – Állítson be olyan kötegelt feladatot, amely értesíti a rendszert az aktuális eseményidőszakról.</span><span class="sxs-lookup"><span data-stu-id="2e328-123">**Update the current continuity event period** – Set up a batch job that tells the system what the current event period is.</span></span>
- <span data-ttu-id="2e328-124">**Folytonos gyermekrendelések létrehozása** – Hozzon létre gyermekrendeléseket a folytonossági szülőrendelésből.</span><span class="sxs-lookup"><span data-stu-id="2e328-124">**Create continuity child orders** – Create child orders from the parent continuity order.</span></span>
- <span data-ttu-id="2e328-125">**Folytonos fizetések feldolgozása** – Dolgozza fel a folytonos értékesítési rendelésekhez kapcsolódó fizetések számláit és értesítéseit.</span><span class="sxs-lookup"><span data-stu-id="2e328-125">**Process continuity payments** – Process billing and notifications for payments that are associated with continuity sales orders.</span></span>
- <span data-ttu-id="2e328-126">**Folytonossági sorok meghosszabbítása** (szükség esetén) – Hosszabbítsa meg a folytonos esemény ismétlődéseinek számát.</span><span class="sxs-lookup"><span data-stu-id="2e328-126">**Extend continuity lines** (if required) – Extend the number of times that a continuity event can be repeated.</span></span> <span data-ttu-id="2e328-127">A szállítások ismétlődése túllépheti a hívásközponti paramétereknél a **Folytonos ismétlődés küszöbértéke** mezőben megadott limitet.</span><span class="sxs-lookup"><span data-stu-id="2e328-127">The repetition of shipments can then extend beyond the limit that was set in the **Continuity repeat threshold** field in the call center parameters.</span></span>
- <span data-ttu-id="2e328-128">**Folytonossági frissítés elvégzése** (szükség szerint) – Szinkronizálja a módosításokat a folytonos program és a szülő folytonos értékesítési rendelések között.</span><span class="sxs-lookup"><span data-stu-id="2e328-128">**Perform a continuity update** (if required) – Synchronize changes between the continuity program and the continuity parent sales orders.</span></span>
- <span data-ttu-id="2e328-129">**Folytonossági szülősorok és rendelések lezárása** – Zárja le a folytonos megrendeléseket.</span><span class="sxs-lookup"><span data-stu-id="2e328-129">**Close continuity parent lines and orders** – Close continuity orders.</span></span>

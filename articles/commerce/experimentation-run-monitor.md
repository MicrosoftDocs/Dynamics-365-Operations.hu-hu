---
title: Kísérlet futtatása és nyomon követése
description: Ez a témakör azt mutatja be, hogyan indíthat el és követhet nyomon kísérletet egy harmadik fél szolgáltatásban. Ez a témakör azt is leírja, hogy hogyan lehet módosítani a változatokat a kísérlet elindítása után.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4cb7d863d9d69612aa0c340099c1f7861c9d12ba
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930211"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="aaedb-104">Kísérlet futtatása és nyomon követése</span><span class="sxs-lookup"><span data-stu-id="aaedb-104">Run and monitor an experiment</span></span>

<span data-ttu-id="aaedb-105">Ez a témakör azt mutatja be, hogyan futtathatja és követheti nyomon a kísérleteit egy harmadik fél alkalmazásban, továbbá hogyan módosíthatja szükség esetén a változatokat.</span><span class="sxs-lookup"><span data-stu-id="aaedb-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="aaedb-106">A témakör lépéseinek végrehajtása előtt [közzé kell tennie](experimentation-preview-publish.md) a kísérletet a Commerce modulban.</span><span class="sxs-lookup"><span data-stu-id="aaedb-106">Before you complete the steps in this topic, you'll need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> <span data-ttu-id="aaedb-107">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="aaedb-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="aaedb-108">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="aaedb-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="aaedb-109">[ ![Kísérletezés felhasználói interakciósorozata – Futtatás és nyomon követés](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aaedb-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="aaedb-110">A változatok közzététele után végezze el a kísérletek futtatásához szükséges lépéseket a Commerce modulban.</span><span class="sxs-lookup"><span data-stu-id="aaedb-110">After you publish your variations, all the steps you need to do in Commerce to run your experiment are done.</span></span> <span data-ttu-id="aaedb-111">A következő lépés azt határozza meg, hogy melyik változat jelenjen meg az egyes felhasználóknak, amikor egy oldalt hívnak le.</span><span class="sxs-lookup"><span data-stu-id="aaedb-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="aaedb-112">A harmadik fél szolgáltatás teszi ezt a meghatározást, de először aktiválni kell a kísérletet a szolgáltatáson belül.</span><span class="sxs-lookup"><span data-stu-id="aaedb-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="aaedb-113">Mivel a kísérletek aktiválásának lépései szolgáltatásonként eltérők, a szolgáltatáshoz vagy a szolgáltatóhoz tartozó utasításokat kell követni.</span><span class="sxs-lookup"><span data-stu-id="aaedb-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="aaedb-114">Ha a kísérlet nincs aktiválva, a felhasználók csak az oldal alapértelmezett változatát fogják látni – nem fognak megjelenni az eltérések.</span><span class="sxs-lookup"><span data-stu-id="aaedb-114">If the experiment is not activated, users will only see the default version of the page - no variations will be displayed.</span></span>

<span data-ttu-id="aaedb-115">Elég hosszú ideig kell futtatnia a kísérletet ahhoz, hogy a statisztikailag érvényes eredményeket hozó adatokat gyűjtsön.</span><span class="sxs-lookup"><span data-stu-id="aaedb-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="aaedb-116">A harmadik fél szolgáltatások segítségével nyomon követheti a kísérlethez kapcsolódó adatokat és analitikákat.</span><span class="sxs-lookup"><span data-stu-id="aaedb-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="aaedb-117">A változatok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="aaedb-117">Adjust your variations</span></span>
<span data-ttu-id="aaedb-118">Ha bármilyen oknál fogva módosítania kell a változatokat, az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="aaedb-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aaedb-119">Ha módosít egy élő kísérletet a Commerce modulban vagy a harmadik fél szolgáltatásban, akkor az jelentős mértékben befolyásolhatja az eredményeket.</span><span class="sxs-lookup"><span data-stu-id="aaedb-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="aaedb-120">Esetleg hagyja végigfutni a kísérletet, és aztán a jelentősebb módosításokhoz új kísérletet hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="aaedb-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="aaedb-121">Lépjen a webhelykészítő **Kísérletek** fülére, és válassza ki a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="aaedb-121">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
1. <span data-ttu-id="aaedb-122">Válassza ki a frissíteni kívánt változatot a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="aaedb-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="aaedb-123">Végezze el a szükséges módosításokat, majd tekintse meg előnézetben és tegye közzé a változatokat.</span><span class="sxs-lookup"><span data-stu-id="aaedb-123">Make needed changes, then preview and publish the variations.</span></span> <span data-ttu-id="aaedb-124">További tudnivalókért lásd: [Egy kísérlet előnézete és közzététele](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="aaedb-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="aaedb-125">Nyissa meg a harmadik fél szolgáltatást a kísérletezéssel kapcsolatos módosítások elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="aaedb-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="aaedb-126">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="aaedb-126">Previous step</span></span>
[<span data-ttu-id="aaedb-127">Kísérlet előnézetének megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="aaedb-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="aaedb-128">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="aaedb-128">Next step</span></span>
[<span data-ttu-id="aaedb-129">Változat előléptetése és egy kísérlet végrehajtása</span><span class="sxs-lookup"><span data-stu-id="aaedb-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)

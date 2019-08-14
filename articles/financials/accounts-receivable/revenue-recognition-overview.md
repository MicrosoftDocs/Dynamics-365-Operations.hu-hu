---
title: Az árbevétel-elszámolás áttekintése
description: Ez a témakör a árbevétel-elszámolás funkcióról nyújt tájékoztatást. Ez a funkció rugalmas keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a többelemű rendelések bevételi árának és bevételütemezésének elszámolásához.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: d52a9c7315cccf668a8b9bcf7ba5cad7039e186e
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863563"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="36457-104">Az árbevétel-elszámolás áttekintése</span><span class="sxs-lookup"><span data-stu-id="36457-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> <span data-ttu-id="36457-105">Az „Árbevétel-elszámolás” funkció még nem kapcsolható be a Funkciókezelés helyen.</span><span class="sxs-lookup"><span data-stu-id="36457-105">The Revenue recognition feature can't yet be turned on through Feature management.</span></span> <span data-ttu-id="36457-106">Jelenleg konfigurációs kulcsok használatával kapcsolhatja be.</span><span class="sxs-lookup"><span data-stu-id="36457-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="36457-107">Olyan iparágak vállalatai esetében, ahol több elem (például termékek, szolgáltatások, előfizetések stb.) értékesítése történik, képesnek kell lennie a több elemből álló rendelések szétbontására, hogy a bevételeket vállalat-és iparág-specifikus irányelvek alapján lehessen elszámolni.</span><span class="sxs-lookup"><span data-stu-id="36457-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="36457-108">Általánosságban a bevétel-elszámolási folyamat a következő feladatok végrehajtásához használható:</span><span class="sxs-lookup"><span data-stu-id="36457-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="36457-109">Bevétel hozzárendelése annak érdekében, hogy garantálható legyen a megfelelő bevételi ár elszámolása a több elemből álló rendelések összetevőinek értéke alapján.</span><span class="sxs-lookup"><span data-stu-id="36457-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized based on the value of the components on the multi-element orders.</span></span>
* <span data-ttu-id="36457-110">Bevétel elhalasztása egy bevételütemezés alapján, amely a szerződéses időkeretet és százalékértékeket tartalmazza a bevétel elszámolásához az idők során.</span><span class="sxs-lookup"><span data-stu-id="36457-110">Defer revenue, based on a revenue schedule that represents the contractual timeframe and percentages for recognizing revenue over time.</span></span>

<span data-ttu-id="36457-111">A Bevételelszámolás funkció egy keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a bevételi árak és bevételütemezésének elszámolásához.</span><span class="sxs-lookup"><span data-stu-id="36457-111">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="36457-112">A kiadott termékek használatosak a bevételelszámoláshoz az értékesítési rendelési dokumentumokon.</span><span class="sxs-lookup"><span data-stu-id="36457-112">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="36457-113">A kiadott termékek tartalmazzák azt a beállítást, amely szükséges a bevételi ár és a bevételütemezés meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="36457-113">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="36457-114">Az értékesítési rendelés idő- és anyagelszámolású projektből származhat.</span><span class="sxs-lookup"><span data-stu-id="36457-114">The sales order can originate from a Time and material project.</span></span>

<span data-ttu-id="36457-115">A vállalatok a bevételütemezés funkciót használhatják a bevételi ár funkcionalitás alkalmazása nélkül is.</span><span class="sxs-lookup"><span data-stu-id="36457-115">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="36457-116">Ennélfogva az értékesítésirendelés-sorokban szereplő ár bevételként vagy halasztott bevételként is felhasználható.</span><span class="sxs-lookup"><span data-stu-id="36457-116">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="36457-117">Ha van bevételi ütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár halasztásra kerül.</span><span class="sxs-lookup"><span data-stu-id="36457-117">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="36457-118">Ha nincs bevételütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár a számlázáskor közzé lesz téve egy bevételi számlán.</span><span class="sxs-lookup"><span data-stu-id="36457-118">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="36457-119">A bevételi ár számítása az értékesítési rendelés visszaigazolásakor vagy a számla feladásakor történik.</span><span class="sxs-lookup"><span data-stu-id="36457-119">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="36457-120">Ha meg szeretné tekinteni az előzetes bevételi árat a számla feladása előtt, akkor meg kell erősítenie az értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="36457-120">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="36457-121">Az értékesítési rendelést megerősítésekor, ha bármely értékesítésirendelés-sor bevételi ütemezést tartalmaz, egy várható bevételütemezés is létrejön.</span><span class="sxs-lookup"><span data-stu-id="36457-121">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line contains a revenue schedule.</span></span> <span data-ttu-id="36457-122">Az értékesítési rendelés számlázásakor, a program törli a várható bevételütemezést, és a várható bevételütemezést a tényleges árbevétel-kimutatási ütemezéssel helyettesíti.</span><span class="sxs-lookup"><span data-stu-id="36457-122">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="36457-123">A program minden értékesítésirendelés-sorhoz megtartja a bevétel-elszámolás ütemezésének adatait.</span><span class="sxs-lookup"><span data-stu-id="36457-123">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="36457-124">Ennélfogva a bevétel-elszámolással foglalkozó vezetője megtekintheti a részleteket, és a szerződéses kötelezettség teljesítésekor felszabadíthatja a bevételi sorokat.</span><span class="sxs-lookup"><span data-stu-id="36457-124">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="36457-125">Az egyes időszakok végén a bevétel-elszámolással foglalkozó vezető bevételi naplót hozhat létre, hogy az általa megadott dátumon vagy azt megelőzően esedékes ütemezési sorokat felszabadítsa.</span><span class="sxs-lookup"><span data-stu-id="36457-125">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="36457-126">Ez a bevételi napló nem lesz azonnal feladva.</span><span class="sxs-lookup"><span data-stu-id="36457-126">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="36457-127">Ennélfogva a bevétel-elszámolással foglalkozó vezető ellenőrizheti, hogy a megfelelő összegek lesznek-e felszabadítva a halasztott bevételből a tényleges bevételhez.</span><span class="sxs-lookup"><span data-stu-id="36457-127">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="36457-128">Ha egy szerződésmódosítás következtében új értékesítésirendelés-sort kell hozzáadni a meglévő értékesítési rendeléshez vagy új értékesítési rendeléshez, akkor egy újrafelosztási folyamat futtatható a bevételi ár javításához az összes értékesítési rendelés soraiban.</span><span class="sxs-lookup"><span data-stu-id="36457-128">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines the sales orders.</span></span>
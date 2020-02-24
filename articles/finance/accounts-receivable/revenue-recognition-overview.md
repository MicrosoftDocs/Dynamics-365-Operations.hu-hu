---
title: A bevételelszámolás áttekintése
description: Ez a témakör a árbevétel-elszámolás funkcióról nyújt tájékoztatást. Ez a funkció rugalmas keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a többelemű rendelések bevételi árának és bevételütemezésének elszámolásához.
author: kweekley
manager: aolson
ms.date: 11/11/2019
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
ms.openlocfilehash: c5a3a90b0065f8cd076117818df810cf10202d29
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2020
ms.locfileid: "3030968"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="42d50-104">A bevételelszámolás áttekintése</span><span class="sxs-lookup"><span data-stu-id="42d50-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="42d50-105">A Bevételelszámolás funkció nem kapcsolható be a Funkciókezelés segítségével.</span><span class="sxs-lookup"><span data-stu-id="42d50-105">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="42d50-106">Jelenleg konfigurációs kulcsok használatával kapcsolhatja be.</span><span class="sxs-lookup"><span data-stu-id="42d50-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="42d50-107">Olyan iparágak vállalatai esetében, ahol több elem (például termékek, szolgáltatások, előfizetések stb.) értékesítése történik, képesnek kell lennie a több elemből álló rendelések szétbontására, hogy a bevételeket vállalat-és iparág-specifikus irányelvek alapján lehessen elszámolni.</span><span class="sxs-lookup"><span data-stu-id="42d50-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="42d50-108">Általánosságban a bevétel-elszámolási folyamat a következő feladatok végrehajtásához használható:</span><span class="sxs-lookup"><span data-stu-id="42d50-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="42d50-109">Bevétel hozzárendelése annak érdekében, hogy garantálható legyen a megfelelő bevételi ár elszámolása a több elemből álló rendelések összetevőinek értéke alapján.</span><span class="sxs-lookup"><span data-stu-id="42d50-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="42d50-110">Bevétel elhalasztása egy olyan bevételütemezés alapján, amely a szerződéses időkeretet és százalékértékeket tartalmazza a bevétel időbeli elszámolásához.</span><span class="sxs-lookup"><span data-stu-id="42d50-110">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

<span data-ttu-id="42d50-111">A [bevételelszámolás használata a szolgáltatásban Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) című videóban (fent) szerepel a [Finance and Operations lejátszási listán,](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) amely elérhető a  YouTube.</span><span class="sxs-lookup"><span data-stu-id="42d50-111">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="42d50-112">A Bevételelszámolás funkció egy keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a bevételi árak és bevételütemezésének elszámolásához.</span><span class="sxs-lookup"><span data-stu-id="42d50-112">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="42d50-113">A kiadott termékek használatosak a bevételelszámoláshoz az értékesítési rendelési dokumentumokon.</span><span class="sxs-lookup"><span data-stu-id="42d50-113">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="42d50-114">A kiadott termékek tartalmazzák azt a beállítást, amely szükséges a bevételi ár és a bevételütemezés meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="42d50-114">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="42d50-115">Az értékesítési rendelés idő- és anyagelszámolású projektből származhat.</span><span class="sxs-lookup"><span data-stu-id="42d50-115">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="42d50-116">A vállalatok a bevételütemezési funkciót a bevételi ár funkcionalitás alkalmazása nélkül is használhatják.</span><span class="sxs-lookup"><span data-stu-id="42d50-116">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="42d50-117">Ennélfogva az értékesítésirendelés-sorokban szereplő ár bevételként vagy halasztott bevételként is felhasználható.</span><span class="sxs-lookup"><span data-stu-id="42d50-117">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="42d50-118">Ha van bevételi ütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár halasztásra kerül.</span><span class="sxs-lookup"><span data-stu-id="42d50-118">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="42d50-119">Ha nincs bevételütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár a számlázáskor közzé lesz téve egy bevételi számlán.</span><span class="sxs-lookup"><span data-stu-id="42d50-119">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="42d50-120">A bevételi ár számítása az értékesítési rendelés visszaigazolásakor vagy a számla feladásakor történik.</span><span class="sxs-lookup"><span data-stu-id="42d50-120">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="42d50-121">Ha meg szeretné tekinteni az előzetes bevételi árat a számla feladása előtt, akkor meg kell erősítenie az értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="42d50-121">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="42d50-122">Ha az értékesítési rendelés megerősítésekor az egyik értékesítésirendelés-sor bevételi ütemezést tartalmaz, egy várható bevételütemezés is létrejön.</span><span class="sxs-lookup"><span data-stu-id="42d50-122">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="42d50-123">Az értékesítési rendelés számlázásakor, a program törli a várható bevételütemezést, és a várható bevételütemezést a tényleges árbevétel-kimutatási ütemezéssel helyettesíti.</span><span class="sxs-lookup"><span data-stu-id="42d50-123">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="42d50-124">A program minden értékesítésirendelés-sorhoz megtartja a bevétel-elszámolás ütemezésének adatait.</span><span class="sxs-lookup"><span data-stu-id="42d50-124">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="42d50-125">Ennélfogva a bevétel-elszámolással foglalkozó vezetője megtekintheti a részleteket, és a szerződéses kötelezettség teljesítésekor felszabadíthatja a bevételi sorokat.</span><span class="sxs-lookup"><span data-stu-id="42d50-125">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="42d50-126">Az egyes időszakok végén a bevétel-elszámolással foglalkozó vezető bevételi naplót hozhat létre, hogy az általa megadott dátumon vagy azt megelőzően esedékes ütemezési sorokat felszabadítsa.</span><span class="sxs-lookup"><span data-stu-id="42d50-126">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="42d50-127">Ez a bevételi napló nem lesz azonnal feladva.</span><span class="sxs-lookup"><span data-stu-id="42d50-127">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="42d50-128">Ennélfogva a bevétel-elszámolással foglalkozó vezető ellenőrizheti, hogy a megfelelő összegek lesznek-e felszabadítva a halasztott bevételből a tényleges bevételhez.</span><span class="sxs-lookup"><span data-stu-id="42d50-128">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="42d50-129">Ha egy szerződésmódosítás következtében új értékesítésirendelés-sort kell hozzáadni a meglévő értékesítési rendeléshez vagy új értékesítési rendeléshez, akkor újrafelosztási folyamat futtatható a bevételi ár javításához az összes értékesítési rendelés soraiban.</span><span class="sxs-lookup"><span data-stu-id="42d50-129">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>

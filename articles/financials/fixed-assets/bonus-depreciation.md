---
title: "Rendkívüli értékcsökkenés"
description: "Ez a cikk a rendkívüli értékcsökkenési funkcióról nyújt áttekintést."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 53d05e66670194e38d1d1f748001ba1eac5f7b94
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="bonus-depreciation"></a><span data-ttu-id="b59b1-103">Rendkívüli értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="b59b1-103">Bonus depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b59b1-104">Ez a cikk a rendkívüli értékcsökkenési funkcióról nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="b59b1-104">This article provides an overview of the bonus depreciation functionality.</span></span>

<span data-ttu-id="b59b1-105">Rendkívüli értékcsökkenés esetében különleges vagy rendkívüli értékcsökkenési összegeket alkalmazhat egy eszköz üzembe helyezésének és értékcsökkenésének első évében.</span><span class="sxs-lookup"><span data-stu-id="b59b1-105">For bonus depreciation, you can take extra or bonus depreciation amounts during the first year that the asset is put in service and depreciated.</span></span> <span data-ttu-id="b59b1-106">A rendkívüli értékcsökkenést a többi értékcsökkenési számítás előtt kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="b59b1-106">Bonus depreciation must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="b59b1-107">Ezért célszerű a rendkívüli értékcsökkenés olyan könyvekkel történő használata, ahol a Feladás a főkönyvbe funkció le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="b59b1-107">Therefore, it's best to use bonus depreciation with books where the Post to general ledger functionality is disabled.</span></span> <span data-ttu-id="b59b1-108">Használhatja a **Főkönyvbe nem feladott tranzakciók törlése** lehetőséget könyveket, a nem a főkönyvbe feladott könyvek előzménytranzakcióinak törléséhez.</span><span class="sxs-lookup"><span data-stu-id="b59b1-108">You can use the **Delete transactions not posted to general ledger** option to delete historical transactions for books that don't post to the general ledger.</span></span> <span data-ttu-id="b59b1-109">A rendkívüli értékcsökkenést az eszköz életciklusának későbbi pontjában rendezheti úgy, hogy törli a korábban feladott értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="b59b1-109">You can then accommodate bonus depreciation later in the asset life cycle by deleting depreciation transactions that were previously posted.</span></span> 

<span data-ttu-id="b59b1-110">A rendkívüli értékcsökkenést kiszámíthatja a javaslati eljárással, vagy létrehozhatja manuálisan a rendkívüli értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="b59b1-110">You can calculate bonus depreciation by using the proposal process, or you can create manual bonus depreciation transactions.</span></span> <span data-ttu-id="b59b1-111">Ha az adott eszköz könyvében már vannak értékcsökkenés-tranzakciók vagy értékcsökkenés-módosítási tranzakciók, akkor nem lehet létrehozni rendkívüli értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="b59b1-111">You can't create bonus depreciation transactions if depreciation transactions or depreciation adjustment transactions exist for that asset book.</span></span>

<span data-ttu-id="b59b1-112">Ha a javaslati művelet segítségével számítja ki a rendkívüli értékcsökkenést, minden létező rendkívüli értékcsökkenési tranzakció szerepel az alap kiszámításában.</span><span class="sxs-lookup"><span data-stu-id="b59b1-112">When you use the proposal process to calculate bonus depreciation, all existing bonus transactions are included in the calculation of the basis.</span></span> <span data-ttu-id="b59b1-113">A számítás tartalmazza a korábban a manuálisan beírt rendkívüli értékcsökkenést is.</span><span class="sxs-lookup"><span data-stu-id="b59b1-113">The calculation also includes any previous bonus depreciations that you manually entered for the asset.</span></span> 

<span data-ttu-id="b59b1-114">Ha egy eszközre több rendkívüli értékcsökkenést alkalmaz, akkor a rendszer figyelembe veszi a prioritást.</span><span class="sxs-lookup"><span data-stu-id="b59b1-114">If more than one bonus depreciation will be taken for an asset, the priority is considered.</span></span> <span data-ttu-id="b59b1-115">Minden rendkívüli értékcsökkenés csökkenti a következő rendkívüli értékcsökkenés eszközalapját.</span><span class="sxs-lookup"><span data-stu-id="b59b1-115">Each bonus reduces the asset basis for the next bonus.</span></span> <span data-ttu-id="b59b1-116">A program a maradványértéket nem kezeli az eszközalap részeként a rendkívüli értékcsökkenés számításánál, és az értékcsökkenési szabály nem vonatkozik a rendkívüli értékcsökkenésre.</span><span class="sxs-lookup"><span data-stu-id="b59b1-116">Salvage value isn't considered in the asset basis for bonus depreciation calculations, and the depreciation convention doesn't apply for bonus depreciation.</span></span> 

<span data-ttu-id="b59b1-117">Jelenleg az Egyesült Államokban bizonyos vagyontárgyak 179-es szakaszba tartozó vagyontárgyaknak minősülnek.</span><span class="sxs-lookup"><span data-stu-id="b59b1-117">Currently, in the United States, some property qualifies as Section 179 property.</span></span> <span data-ttu-id="b59b1-118">A 179-es szakasz szerinti levonás esetén lehetőség van arra, hogy leírja egy bizonyos vagyontárgy költségének egészét vagy egy részét – egy bizonyos határig.</span><span class="sxs-lookup"><span data-stu-id="b59b1-118">By using the Section 179 deduction, you can recover all or part of the cost of some property, up to a limit.</span></span> <span data-ttu-id="b59b1-119">A költséget a vagyontárgy szolgálatba állításának az első évében írhatja le.</span><span class="sxs-lookup"><span data-stu-id="b59b1-119">You can recover the cost by deducting it in the year when you put the property in service.</span></span>

## <a name="example"></a><span data-ttu-id="b59b1-120">Példa</span><span class="sxs-lookup"><span data-stu-id="b59b1-120">Example</span></span>
<span data-ttu-id="b59b1-121">Az alábbi rendkívüli értékcsökkenések egy eszköz könyvéhez társulnak:</span><span class="sxs-lookup"><span data-stu-id="b59b1-121">The following bonus depreciations are associated with an asset book:</span></span>

-   <span data-ttu-id="b59b1-122">**179-es szakasz:** 1000,00 dollár, 1-es prioritás</span><span class="sxs-lookup"><span data-stu-id="b59b1-122">**Section 179:** 1,000.00, Priority 1</span></span>
-   <span data-ttu-id="b59b1-123">**Liberty Zone:** 30 százalék, 2-es prioritás</span><span class="sxs-lookup"><span data-stu-id="b59b1-123">**Liberty Zone:** 30 percent, Priority 2</span></span>

<span data-ttu-id="b59b1-124">Az eszköz beszerzési ára 5000,00 dollár.</span><span class="sxs-lookup"><span data-stu-id="b59b1-124">The asset acquisition cost is 5,000.00.</span></span> <span data-ttu-id="b59b1-125">A rendkívüli értékcsökkenési összeg számítása során az első rendkívüli értékcsökkenési összeg 1000,00 dollár lesz a 179-es szakasz értékcsökkenése alapján.</span><span class="sxs-lookup"><span data-stu-id="b59b1-125">When bonus depreciation is calculated, the first bonus depreciation amount is 1,000.00 for the Section 179 depreciation.</span></span> 

<span data-ttu-id="b59b1-126">A következő rendkívüli értékcsökkenési összeg kiszámítása – a Liberty Zone értékcsökkenés alapján – az alábbi számítással történik:</span><span class="sxs-lookup"><span data-stu-id="b59b1-126">The next bonus depreciation amount, for the Liberty Zone depreciation, is calculated as follows:</span></span> 

<span data-ttu-id="b59b1-127">Beszerzési ár – 1000 dollár (a 179-es szakasz értékcsökkenése) x 30 százalék = 1200 dollár</span><span class="sxs-lookup"><span data-stu-id="b59b1-127">Acquisition cost – 1,000 (Section 179 depreciation) × 30 percent = 1,200</span></span> 

<span data-ttu-id="b59b1-128">Ha a rendkívüli értékcsökkenés összege nagyobb, mint a maradék beszerzési ár, akkor a rendkívüli értékcsökkenési összeg a számított rendkívüli értékcsökkenés, vagy a maradék beszerzési ár közül a kevesebbik lesz.</span><span class="sxs-lookup"><span data-stu-id="b59b1-128">If the bonus depreciation amount is more than the remaining acquisition cost, the bonus depreciation amount is either the result of the bonus depreciation calculation or the remaining acquisition cost, whichever amount is less.</span></span> 

<span data-ttu-id="b59b1-129">Ha a maradék beszerzési ár 0 (nulla) vagy kevesebb, akkor nem készülnek rendkívüli értékcsökkenési tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="b59b1-129">If the remaining acquisition cost is 0 (zero) or less, bonus depreciation transactions isn't generated.</span></span> 

<span data-ttu-id="b59b1-130">Ha a rendkívüli értékcsökkenést a javaslati művelettel számítja ki, akkor az eszköz könyvéhez társított valamennyi alkalmazható rendkívüli értékcsökkenési rekordhoz létrejön egy rendkívüli értékcsökkenési tranzakció.</span><span class="sxs-lookup"><span data-stu-id="b59b1-130">When bonus depreciation is calculated by using the proposal process, a bonus depreciation transaction is created for all applicable bonus depreciation records that are associated with the asset book.</span></span> 

<span data-ttu-id="b59b1-131">A létrehozható rendkívüli értékcsökkenési rekordok száma korlátlan.</span><span class="sxs-lookup"><span data-stu-id="b59b1-131">You can create an unlimited number of bonus depreciation records.</span></span> <span data-ttu-id="b59b1-132">Miután az eszközcsoport könyvéhez társította a rekordokat, a program alkalmazza őket az eszköz könyvére.</span><span class="sxs-lookup"><span data-stu-id="b59b1-132">After you assign those records to the asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="b59b1-133">A rendkívüli értékcsökkenést százalékként vagy százalékként vagy rögzített összegként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="b59b1-133">Bonus depreciation is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="b59b1-134">Ha értékcsökkenési javaslatot ad fel, akkor a program az értékcsökkenés tranzakcióitól különálló tranzakciókként adja fel a rendkívüli értékcsökkenés tranzakcióit a könyvbe.</span><span class="sxs-lookup"><span data-stu-id="b59b1-134">When you post depreciation proposals, bonus depreciation transactions are posted to the book as separate transactions from the depreciation transactions.</span></span>




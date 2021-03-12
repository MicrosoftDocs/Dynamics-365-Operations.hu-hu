---
title: Értékcsökkenési módszerek és szabályok
description: Ez a cikk betekintést nyújt a Microsoft Dynamics 365 Finance által támogatott értékcsökkenési szabályokba és az értékcsökkenési metódusokba.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af1c1a222981a0bcf9d7341cde5b83dd720da802
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994965"
---
# <a name="depreciation-methods-and-conventions"></a><span data-ttu-id="85649-103">Értékcsökkenési módszerek és konvenciók</span><span class="sxs-lookup"><span data-stu-id="85649-103">Depreciation methods and conventions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="85649-104">Ez a cikk betekintést nyújt a támogatott értékcsökkenési szabályokba és az értékcsökkenési metódusokba.</span><span class="sxs-lookup"><span data-stu-id="85649-104">This article provides an overview of the supported depreciation conventions and depreciation methods.</span></span>

<span data-ttu-id="85649-105">Különféle értékcsökkenési módszerek és szabályok közül lehet választani.</span><span class="sxs-lookup"><span data-stu-id="85649-105">You can select various depreciation methods and conventions.</span></span> <span data-ttu-id="85649-106">A módszerek célja, hogy a pénzügyi időszakok között felosszák a tárgyi eszköz értékcsökkenésként elszámolható értékét.</span><span class="sxs-lookup"><span data-stu-id="85649-106">The purpose of the methods is to allocate the depreciable value of the fixed asset into fiscal periods.</span></span> <span data-ttu-id="85649-107">A tárgyi eszköz értékcsökkenésként elszámolható részét úgy lehet kiszámítani, hogy a beszerzési árat csökkenti az esetleges maradványértékkel.</span><span class="sxs-lookup"><span data-stu-id="85649-107">The depreciable value of the fixed asset is the acquisition price, reduced by a scrap value, if any.</span></span> 

<span data-ttu-id="85649-108">Ha értékcsökkenési szabályokat használ, és módosítja egy eszköz értékcsökkenésének a futtatási dátumát, amellyel néhány értékcsökkenés kihagyását okozza, akkor a legutóbbi év értékcsökkenése kevesebb vagy több lehet a vártnál.</span><span class="sxs-lookup"><span data-stu-id="85649-108">If you are using depreciation conventions and you modify the last depreciation run date for an asset, which then causes some depreciations to be skipped, the depreciation for the last year might be more than or less than is expected.</span></span> <span data-ttu-id="85649-109">Az értékcsökkenés kiigazítható az értékcsökkenés legutóbbi futtatási dátumának a módosításával befolyásolt értékcsökkenési időszakok számával.</span><span class="sxs-lookup"><span data-stu-id="85649-109">The depreciation is adjusted by the number of depreciation periods affected by the modification of the last depreciation run date.</span></span>

<span data-ttu-id="85649-110">Ha például három évig használja a féléves értékcsökkenési szabályt, akkor az értékcsökkenés normális esetben 3 1/2 évig tart.</span><span class="sxs-lookup"><span data-stu-id="85649-110">For example, if you are using the Half year depreciation convention over three years, depreciation ordinarily occurs over 3 1/2 years.</span></span> <span data-ttu-id="85649-111">Ha a 3 1/2 év alatt módosítja a legutóbbi értékcsökkenés futtatási dátumát, akkor az értékcsökkenés utolsó éve már nem tartozik a érintett időszakok közé.</span><span class="sxs-lookup"><span data-stu-id="85649-111">If you change the last depreciation run date during the 3 1/2 years, the last year of depreciation moves out the number of periods affected.</span></span> <span data-ttu-id="85649-112">Ha három hónappal áthelyezi a dátumot, akkor az utolsó évben kilenc hónapnyi értékcsökkenés lesz, pedig normális esetben csak hat hónapnyi értékcsökkenés lenne.</span><span class="sxs-lookup"><span data-stu-id="85649-112">If you move the date by three months, the last year will have nine months’ worth of depreciation, when ordinarily there would be six months’ worth of depreciation.</span></span>

<span data-ttu-id="85649-113">Az alábbi értékcsökkenési szabályok közül lehet választani.</span><span class="sxs-lookup"><span data-stu-id="85649-113">You can select from the following depreciation conventions.</span></span>


-   <span data-ttu-id="85649-114">Félév</span><span class="sxs-lookup"><span data-stu-id="85649-114">Half year</span></span>
-   <span data-ttu-id="85649-115">Teljes hónap</span><span class="sxs-lookup"><span data-stu-id="85649-115">Full month</span></span>
-   <span data-ttu-id="85649-116">Negyedév közepe</span><span class="sxs-lookup"><span data-stu-id="85649-116">Mid quarter</span></span>
-   <span data-ttu-id="85649-117">Hónap közepe (hó elseje)</span><span class="sxs-lookup"><span data-stu-id="85649-117">Mid month (1st of month)</span></span>
-   <span data-ttu-id="85649-118">Hónap közepe (hó 15-e)</span><span class="sxs-lookup"><span data-stu-id="85649-118">Mid month (15th of month)</span></span>
-   <span data-ttu-id="85649-119">Félév (évkezdet)</span><span class="sxs-lookup"><span data-stu-id="85649-119">Half year (start of year)</span></span>
-   <span data-ttu-id="85649-120">Félév (következő év)</span><span class="sxs-lookup"><span data-stu-id="85649-120">Half year (next year)</span></span>

<span data-ttu-id="85649-121">A következő értékcsökkenési módok közül választhat.</span><span class="sxs-lookup"><span data-stu-id="85649-121">You can select from the following depreciation methods.</span></span>
-   <span data-ttu-id="85649-122">Lineáris - élettartam</span><span class="sxs-lookup"><span data-stu-id="85649-122">Straight line service life</span></span>
-   <span data-ttu-id="85649-123">Degresszív</span><span class="sxs-lookup"><span data-stu-id="85649-123">Reducing balance</span></span>
-   <span data-ttu-id="85649-124">Manuális</span><span class="sxs-lookup"><span data-stu-id="85649-124">Manual</span></span>
-   <span data-ttu-id="85649-125">Szorzó</span><span class="sxs-lookup"><span data-stu-id="85649-125">Factor</span></span>
-   <span data-ttu-id="85649-126">Felhasználás</span><span class="sxs-lookup"><span data-stu-id="85649-126">Consumption</span></span>
-   <span data-ttu-id="85649-127">Lineáris - hátralevő élettartam</span><span class="sxs-lookup"><span data-stu-id="85649-127">Straight line life remaining</span></span>
-   <span data-ttu-id="85649-128">200% degresszív</span><span class="sxs-lookup"><span data-stu-id="85649-128">200% reducing balance</span></span>
-   <span data-ttu-id="85649-129">175% degresszív</span><span class="sxs-lookup"><span data-stu-id="85649-129">175% reducing balance</span></span>
-   <span data-ttu-id="85649-130">150% degresszív</span><span class="sxs-lookup"><span data-stu-id="85649-130">150% reducing balance</span></span>
-   <span data-ttu-id="85649-131">125% degresszív</span><span class="sxs-lookup"><span data-stu-id="85649-131">125% reducing balance</span></span>





<a name="additional-resources"></a><span data-ttu-id="85649-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="85649-132">Additional resources</span></span>
--------

[<span data-ttu-id="85649-133">Tárgyi eszközök értékcsökkenése</span><span class="sxs-lookup"><span data-stu-id="85649-133">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)

[<span data-ttu-id="85649-134">Élettartamon alapuló lineáris értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-134">Straight line service life depreciation</span></span>](Straight-line-service-life-depreciation.md)

[<span data-ttu-id="85649-135">Degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-135">Reduce balance depreciation</span></span>](reduce-balance-depreciation.md)

[<span data-ttu-id="85649-136">Manuális értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-136">Manual depreciation</span></span>](manual-depreciation.md)

[<span data-ttu-id="85649-137">Tényezős értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-137">Factor depreciation</span></span>](factor-depreciation.md)

[<span data-ttu-id="85649-138">Felhasználás értékcsökkenése</span><span class="sxs-lookup"><span data-stu-id="85649-138">Consumption depreciation</span></span>](consumption-depreciation.md)

[<span data-ttu-id="85649-139">Lineáris - hátralevő élettartam értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-139">Straight line life remaining depreciation</span></span>](straight-line-life-remaining-depreciation.md)

[<span data-ttu-id="85649-140">125 százalékos degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-140">125 percent reducing balance depreciation</span></span>](125-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="85649-141">150 százalék degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-141">150 percent reducing balance depreciation</span></span>](150-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="85649-142">175 százalék degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-142">175 percent reducing balance depreciation</span></span>](175-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="85649-143">200 százalék degresszív értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="85649-143">200 percent reducing balance depreciation</span></span>](200-percent-reducing-balance-depreciation.md)




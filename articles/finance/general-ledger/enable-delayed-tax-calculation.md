---
title: Késleltetett adószámítás engedélyezése a naplókban
description: Ez a témakör azt mutatja be, hogyan lehet a Késleltetett adó számításának engedélyezése funkciót a számítási teljesítmény növelésére használni, ha a naplósorok mennyisége nagyon nagy.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 4ea79747e8e7c078baa6e270ecebf88c4832e079
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968804"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a><span data-ttu-id="1eaef-103">Késleltetett adószámítás engedélyezése a naplókban</span><span class="sxs-lookup"><span data-stu-id="1eaef-103">Enable delayed tax calculation on journals</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="1eaef-104">Ez a témakör azt mutatja be, hogyan lehet késleltetni az áfa számítását a naplókon.</span><span class="sxs-lookup"><span data-stu-id="1eaef-104">This topic explains how you can delay sales tax calculation on journals.</span></span> <span data-ttu-id="1eaef-105">Ez a lehetőség segít az adószámítás hatékonyságának javításában, ha sok naplósor van.</span><span class="sxs-lookup"><span data-stu-id="1eaef-105">This capability helps improve the performance of tax calculations when there are many journal lines.</span></span>

<span data-ttu-id="1eaef-106">Alapértelmezés szerint a rendszer a naplósorokban szereplő áfaösszegeket akkor számítja ki, amikor az adóval kapcsolatos mezőket frissítették.</span><span class="sxs-lookup"><span data-stu-id="1eaef-106">By default, sales tax amounts on journal lines are calculated whenever tax-related fields are updated.</span></span> <span data-ttu-id="1eaef-107">Ezek a mezők tartalmazzák az áfacsoportok és a cikkáfacsoportok mezőit.</span><span class="sxs-lookup"><span data-stu-id="1eaef-107">These fields include the fields for sales tax groups and item sales tax groups.</span></span> <span data-ttu-id="1eaef-108">A naplósor frissítésével az összes naplósor esetében újra lesznek számítva az adózási összegek.</span><span class="sxs-lookup"><span data-stu-id="1eaef-108">Any update to a journal line causes tax amounts to be recalculated for all journal lines.</span></span> <span data-ttu-id="1eaef-109">Annak ellenére, hogy ez a viselkedés segít a felhasználó számára a valós időben számított adóknál, hatással lehet a teljesítményre is, ha a naplósorok száma nagyon nagy.</span><span class="sxs-lookup"><span data-stu-id="1eaef-109">Although this behavior helps user see tax amounts calculated in real time, it can also affect performance if the number of journal lines is very large.</span></span>

<span data-ttu-id="1eaef-110">A Késleltetett adószámítási funkció lehetővé teszi az adószámítás elhalasztását a naplókon, és így segít a teljesítménnyel kapcsolatos problémák megoldásában.</span><span class="sxs-lookup"><span data-stu-id="1eaef-110">The Delayed tax calculation feature lets you delay tax calculation on journals and therefore helps fix performance issues.</span></span> <span data-ttu-id="1eaef-111">Ha ez a funkció be van kapcsolva, akkor az adó összegeket csak akkor számítja ki a rendszer, amikor a felhasználó az **Áfa** parancsra kattint vagy feladja a naplót.</span><span class="sxs-lookup"><span data-stu-id="1eaef-111">When this feature is turned on, tax amounts are calculated only when a user selects **Sales Tax** or posts the journal.</span></span>

<span data-ttu-id="1eaef-112">A áfa kiszámítását három szinten teheti meg:</span><span class="sxs-lookup"><span data-stu-id="1eaef-112">You can delay the calculation of sales taxes at three levels:</span></span>

- <span data-ttu-id="1eaef-113">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="1eaef-113">Legal entity</span></span>
- <span data-ttu-id="1eaef-114">Napló neve</span><span class="sxs-lookup"><span data-stu-id="1eaef-114">Journal name</span></span>
- <span data-ttu-id="1eaef-115">Napló fejléce</span><span class="sxs-lookup"><span data-stu-id="1eaef-115">Journal header</span></span>

<span data-ttu-id="1eaef-116">A rendszer prioritást ad a naplófejléc beállításának.</span><span class="sxs-lookup"><span data-stu-id="1eaef-116">The system gives priority to the setting for the journal header.</span></span> <span data-ttu-id="1eaef-117">Alapértelmezés szerint ez a beállítás a napló nevéből származik.</span><span class="sxs-lookup"><span data-stu-id="1eaef-117">By default, this setting is taken from the journal name.</span></span> <span data-ttu-id="1eaef-118">Alapértelmezés szerint a naplónév beállítását a rendszer a **Főkönyvi paraméterek** lap beállításából veszi, amikor a napló neve létrejön.</span><span class="sxs-lookup"><span data-stu-id="1eaef-118">By default, the setting for the journal name is taken from the setting on the **General ledger parameters** page when the journal name is created.</span></span> <span data-ttu-id="1eaef-119">A következő szakaszok azt mutatják be, hogyan lehet bekapcsolni az adó késleletett számítását a jogi személyek, a naplónevek és a naplófejlécek esetében.</span><span class="sxs-lookup"><span data-stu-id="1eaef-119">The following sections explain how to turn on delayed tax calculation for legal entities, journal names, and journal headers.</span></span>

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a><span data-ttu-id="1eaef-120">A késleltetett adószámítás bekapcsolása a jogi személy szintjén</span><span class="sxs-lookup"><span data-stu-id="1eaef-120">Turn on delayed tax calculation at the legal entity level</span></span>

1. <span data-ttu-id="1eaef-121">Menjen a **Főkönyv \> Főkönyv beállítás \> Főkönyv paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="1eaef-121">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="1eaef-122">Az **Áfa** lapon, az **Általános** gyorslapon állítsa a **Késleltetett adószámítás** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="1eaef-122">On the **Sales tax** tab, on the **General** FastTab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Főkönyvi paraméterek képe](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a><span data-ttu-id="1eaef-124">A késleltetett adószámítás bekapcsolása a naplónév szintjén</span><span class="sxs-lookup"><span data-stu-id="1eaef-124">Turn on delayed tax calculation at the journal name level</span></span>

1. <span data-ttu-id="1eaef-125">Menjen a **Főkönyv \> Naplóbeállítások \> Naplónevek** pontra.</span><span class="sxs-lookup"><span data-stu-id="1eaef-125">Go to **General ledger \> Journal setup \> Journal names**.</span></span>
2. <span data-ttu-id="1eaef-126">Az **Általános** gyorslapon az **Áfa** szakaszban állítsa a **Késleltetett adószámítás** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="1eaef-126">On the **General** FastTab, in the **Sales tax** section, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Naplónevek képe](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a><span data-ttu-id="1eaef-128">A késleltetett adószámítás bekapcsolása a naplófejléc szintjén</span><span class="sxs-lookup"><span data-stu-id="1eaef-128">Turn on delayed tax calculation at the journal header level</span></span>

1. <span data-ttu-id="1eaef-129">Válassza a **Főkönyv \> Naplóbejegyzések \> Általános naplók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1eaef-129">Go to **General ledger \> Journal entries \> General journals**.</span></span>
2. <span data-ttu-id="1eaef-130">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1eaef-130">Select **New**.</span></span>
3. <span data-ttu-id="1eaef-131">Válasszon egy naplónevet.</span><span class="sxs-lookup"><span data-stu-id="1eaef-131">Select a journal name.</span></span>
4. <span data-ttu-id="1eaef-132">A **Beállítás** lapon adja meg a **Késleltetett adószámítás** beállítását **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="1eaef-132">On the **Setup** tab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Általános naplólap képe](media/delayed-tax-calculation-journal-header.png)

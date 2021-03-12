---
title: Rakomány-összeállítási munkaterület
description: Ez a témakör azt mutatja be, hogyan lehet használni a rakományépítő munkaterületet.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1ed91adba5c7accf9a18d7a754d33b2b35b848f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974225"
---
# <a name="load-building-workbench"></a><span data-ttu-id="36936-103">Rakomány-összeállítási munkaterület</span><span class="sxs-lookup"><span data-stu-id="36936-103">Load building workbench</span></span>

<span data-ttu-id="36936-104">A rakomány-összeállítási munkaterületen a rakományok létrehozásakor használhatók a rakomány-összeállítási stratégiák.</span><span class="sxs-lookup"><span data-stu-id="36936-104">The load building workbench lets you apply load building strategies when you create loads.</span></span>

## <a name="create-a-load-building-strategy"></a><span data-ttu-id="36936-105">Rakomány-összeállítási stratégia létrehozása</span><span class="sxs-lookup"><span data-stu-id="36936-105">Create a load building strategy</span></span>

<span data-ttu-id="36936-106">A rakomány-összeállítási stratégiák a rakományok automatikus összeállítására használható.</span><span class="sxs-lookup"><span data-stu-id="36936-106">You use load building strategies to automatically build loads.</span></span> <span data-ttu-id="36936-107">Ez a lehetőség a következő helyzetekben előnyös lehet:</span><span class="sxs-lookup"><span data-stu-id="36936-107">This capability can be beneficial in the following situations:</span></span>

- <span data-ttu-id="36936-108">Ha rendszeresen szállít egy meghatározott termékeket, akkor a rakománystratégiák segítségével időt takaríthat meg, mivel nem kell minden alkalommal ugyanazt a rakományt összeállítani.</span><span class="sxs-lookup"><span data-stu-id="36936-108">If you regularly ship a specific set of products, load strategies help save time, because you don't have to build the same load every time.</span></span>
- <span data-ttu-id="36936-109">Ha a hatékonyság maximalizálása érdekében el szeretné kerülni a félig tele rakományokat, akkor a rakománystratégiák segítségével a lehető legjobban feltöltheti a rakományokat.</span><span class="sxs-lookup"><span data-stu-id="36936-109">If you want to avoid half-full loads to maximize efficiency, load strategies can help fill each load as much as possible.</span></span>

<span data-ttu-id="36936-110">A `TMSLoadBuildingVolumeStrategy` nevű rakomány-összeállítási stratégiaosztály biztosítja a *Térfogaton alapuló rakomány-összeállítási stratégia* nevű rakomány-összeállítási stratégiát.</span><span class="sxs-lookup"><span data-stu-id="36936-110">A load building strategy class that is named `TMSLoadBuildingVolumeStrategy` provides a load building strategy that is named *Volume-based load building strategy*.</span></span> <span data-ttu-id="36936-111">Ez a stratégia lehetővé teszi a rakomány-sablonban megadott maximális magasság- és súlyértékek használatát, vagy a beállítások felülírását új értékek megadásával.</span><span class="sxs-lookup"><span data-stu-id="36936-111">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="36936-112">Ez a stratégia az egyetlen olyan stratégia, amely beépítetten érkezik.</span><span class="sxs-lookup"><span data-stu-id="36936-112">This strategy is the only strategy that is included out of the box.</span></span> <span data-ttu-id="36936-113">(Előfordulhat azonban, hogy valamilyen egyéni stratégiát tartalmaz.)</span><span class="sxs-lookup"><span data-stu-id="36936-113">(However, you might have some custom strategies.)</span></span>

<span data-ttu-id="36936-114">A beépített *Térfogaton alapuló rakomány-összeállítási stratégia* stratégia használatához válassza a **Rakomány-összeállítási stratégia** mezőt a **Rakomány-összeállítási munkaterület** oldalon (**Szállításkezelés &gt; Tervezés &gt; Rakomány-összeállítási munkaterület**).</span><span class="sxs-lookup"><span data-stu-id="36936-114">To use the out-of-box *Volume-based load building strategy* strategy, select it in the **Load building strategy** field on the **Load building workbench** page (**Transportation management &gt; Planning &gt; Load building workbench**).</span></span>

<span data-ttu-id="36936-115">Rakomány-összeállítási stratégia létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="36936-115">To create a load building strategy, follow these steps.</span></span>

1. <span data-ttu-id="36936-116">Lépjen a **Szállításkezelés &gt; Beállítás &gt; Rakomány-összeállítás &gt; Rakomány-összeállítási stratégiák** pontra.</span><span class="sxs-lookup"><span data-stu-id="36936-116">Go to **Transportation management &gt; Setup &gt; Load building &gt; Load building strategies**.</span></span>
1. <span data-ttu-id="36936-117">A műveleti ablaktáblán válassza az **Osztálylista létrehozása** lehetőséget, és győződjön meg arról, hogy az összes rendelkezésre álló osztály legfrissebb verzióival rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="36936-117">On the Action Pane, select **Generate class list** to make sure that you have the latest versions of all available classes.</span></span>
1. <span data-ttu-id="36936-118">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="36936-118">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="36936-119">Adjon meg egy egyedi nevet a stratégiának, válassza ki a rakomány-összeállítási stratégiai osztályt, és adjon meg egy leírást.</span><span class="sxs-lookup"><span data-stu-id="36936-119">Enter a unique name for the strategy, select the load building strategy class for it, and enter a description.</span></span>
1. <span data-ttu-id="36936-120">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="36936-120">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="36936-121">A Műveleti panelen válassza a **Paraméterek** elemet.</span><span class="sxs-lookup"><span data-stu-id="36936-121">On the Action Pane, select **Parameters**.</span></span>
1. <span data-ttu-id="36936-122">A **Rakomány-összeállítási stratégia paraméterei** oldalon válassza a **Térfogat-kapacitás** lehetőséget a listából, majd az **Érték** mezőben adja meg a rakomány teljes térfogat-kapacitásának százalékát, amelyre az új rakomány-összeállítási stratégiát alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="36936-122">On the **Load building strategy parameters** page, select **Volume capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total volume capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="36936-123">Válassza a **Súlykapacitás** lehetőséget a listából, majd az **Érték** mezőben adja meg a rakomány teljes súlykapacitásának százalékát, amelyre az új rakomány-összeállítási stratégiát alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="36936-123">Select **Weight capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total weight capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="36936-124">Zárja be a **Rakomány-összeállítási stratégia paraméterei** oldalt.</span><span class="sxs-lookup"><span data-stu-id="36936-124">Close the **Load building strategy parameters** page.</span></span>
1. <span data-ttu-id="36936-125">Zárja be a **Rakomány-összeállítási stratégiák** oldalt.</span><span class="sxs-lookup"><span data-stu-id="36936-125">Close the **Load building strategies** page.</span></span>

<span data-ttu-id="36936-126">Ezután hozzárendelheti a rakomány-összeállítási stratégiát egy rakomány-összeállítási sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="36936-126">You can now assign the load building strategy to a load building template.</span></span> <span data-ttu-id="36936-127">Azt is megteheti, hogy közvetlenül a rakomány-összeállítási munkaterületen is használhatja.</span><span class="sxs-lookup"><span data-stu-id="36936-127">Alternatively, you can use it directly in the load planning workbench.</span></span>

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a><span data-ttu-id="36936-128">Rakomány-összeállítási stratégia használata a rakomány-összeállítási munkaterületen</span><span class="sxs-lookup"><span data-stu-id="36936-128">Use a load building strategy in the load building workbench</span></span>

1. <span data-ttu-id="36936-129">Ugorjon a **Szállításkezelés &gt; Tervezés &gt; Rakomány-összeállítási munkaterület** elemre.</span><span class="sxs-lookup"><span data-stu-id="36936-129">Go to **Transportation management &gt; Planning &gt; Load building workbench**.</span></span>
1. <span data-ttu-id="36936-130">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="36936-130">Follow one of these steps:</span></span>

    - <span data-ttu-id="36936-131">Válassza ki a stratégiát a **Rakomány-összeállítási stratégia** mezőben.</span><span class="sxs-lookup"><span data-stu-id="36936-131">Select a strategy in the **Load building strategy** field.</span></span>
    - <span data-ttu-id="36936-132">Ha már meghatározta a rakomány-összeállítási sablont, és hozzárendelte a rakomány-összeállítási stratégiát, a műveleti panel **Sablonok kezelése** lapján válassza a **Sablon alkalmazása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="36936-132">If you've defined a load building template and assigned the load building strategy to it, on the Action Pane, on the **Manage templates** tab, select **Apply template**.</span></span> <span data-ttu-id="36936-133">Majd a **Rakomány-összeállítási sablon alkalmazása** legördülő párbeszédpanelen válasszon egy sablont a **Rakomány-összeállítási sablon neve** mezőben.</span><span class="sxs-lookup"><span data-stu-id="36936-133">Then, in the **Apply load building template** drop-down dialog box, select a template in the **Load building template name** field.</span></span>

1. <span data-ttu-id="36936-134">A **Rakománysablonok sorrendje** gyorslapon válasszon egy vagy több [rakománysablont](load-template.md).</span><span class="sxs-lookup"><span data-stu-id="36936-134">On the **Load templates sequence** FastTab, select one or more [load templates](load-template.md).</span></span> <span data-ttu-id="36936-135">A munkaterület az itt megadott sorrendben próbálja meg a rakományt az ilyen típusú tárolókba elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="36936-135">The workbench will try to fit the load into these types of containers, in the sequence that is specified here.</span></span> <span data-ttu-id="36936-136">Általában a lista tetején kell elhelyezni a legkisebb tárolókat, hogy a lehető legkisebb tartály legyen először kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="36936-136">Typically, you should put the smallest containers at the top of the list to ensure that the smallest possible container is selected first.</span></span>
1. <span data-ttu-id="36936-137">A Művelet ablaktáblán válassza ki a **Rakományok javaslása** elemet.</span><span class="sxs-lookup"><span data-stu-id="36936-137">On the Action Pane, select **Propose loads**.</span></span>
1. <span data-ttu-id="36936-138">Tekintse át a javasolt rakományokat és a javasolt rakománysorokat.</span><span class="sxs-lookup"><span data-stu-id="36936-138">Review the proposed loads and proposed load lines.</span></span>
1. <span data-ttu-id="36936-139">A művelet ablaktáblán válassza a **Rakományok létrehozása** lehetőséget, ha a **Javasolt rakománysorok** gyorslapjon szereplő forrásdokumentum-sorokon alapuló rakományokat kíván létrehozni.</span><span class="sxs-lookup"><span data-stu-id="36936-139">On the Action Pane, select **Create loads** to create loads that are based on the source document lines on the **Proposed load lines** FastTab.</span></span>
1. <span data-ttu-id="36936-140">Zárja be a **Rakomány-összeállítási munkaterület** oldalt.</span><span class="sxs-lookup"><span data-stu-id="36936-140">Close the **Load building workbench** page.</span></span>

---
title: Minőségbiztosítási tesztváltozók
description: Ez a témakör azt mutatja be, hogyan lehet tesztváltozókat létrehozni, amelyek a minőségi rendelések kvalitatív tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e94972b41baf3f59a633fa7bbc7434abfb90460
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956684"
---
# <a name="quality-management-test-variables"></a><span data-ttu-id="cccca-103">Minőségbiztosítási tesztváltozók</span><span class="sxs-lookup"><span data-stu-id="cccca-103">Quality management test variables</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cccca-104">Ez a témakör azt mutatja be, hogyan lehet tesztváltozókat létrehozni, amelyek a minőségi rendelések kvalitatív tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cccca-104">This topic describes how to create test variables that can be used for qualitative tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="cccca-105">Minden egyes, a **Tesztek** oldalon megadott minőségi teszthez definiálnia kell egy változót és annak eredményeit.</span><span class="sxs-lookup"><span data-stu-id="cccca-105">For every qualitative test that is defined on the **Tests** page, you must define a test variable and its possible outcomes (results).</span></span> <span data-ttu-id="cccca-106">(Minőségi tesztek esetén a **Tesztek** a **Típus** mező értéke legyen *Lehetőség*.)</span><span class="sxs-lookup"><span data-stu-id="cccca-106">(For qualitative tests, the **Type** field on the **Tests** page is set to *Option*.)</span></span>

<span data-ttu-id="cccca-107">A **Tesztváltozók** oldalon lehet beállítani, módosítani vagy megtekinteni a minőségi teszthez kapcsolódó tesztváltozó lehetséges eredményeit.</span><span class="sxs-lookup"><span data-stu-id="cccca-107">You use the **Test variables** page to set up, edit, and view the possible outcomes for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="cccca-108">Mindegyik eredményhez *Sikeres* vagy *Sikertelen* eredményállapot hozzárendelésével kell jelezni, hogy a teszt sikeres vagy sikertelen volt, amennyiben az eredményt teszteredményként választják ki.</span><span class="sxs-lookup"><span data-stu-id="cccca-108">For each outcome, you assign an outcome status of either *Pass* or *Fail* to indicate whether the test is passed or failed when that outcome is selected as a test result.</span></span> <span data-ttu-id="cccca-109">A **Tesztcsoportok** oldal használatával lehet tesztváltozót és az alapértelmezett eredményt adott minőségi teszthez hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="cccca-109">You use the **Test groups** page to assign a test variable and a default outcome for it to an individual qualitative test.</span></span>

<span data-ttu-id="cccca-110">Minden tesztváltozónál ajánlott legalább két eredményt meghatározni: egyet *Sikeres* eredménystátuszhoz, egyet pedig *Sikertelen* eredménystátuszhoz.</span><span class="sxs-lookup"><span data-stu-id="cccca-110">For every test variable, we recommend that you define at least two outcomes: one that has an outcome status of *Pass* and one that has an outcome status of *Fail*.</span></span> <span data-ttu-id="cccca-111">Nincs korlátozva a definiálható változók és eredmények teljes száma.</span><span class="sxs-lookup"><span data-stu-id="cccca-111">There is no limit on the total number of variables or outcomes that can be defined.</span></span> <span data-ttu-id="cccca-112">Ezenkívül az eredmények rögzítésére több teszt is használhatja ugyanazt a tesztváltozót.</span><span class="sxs-lookup"><span data-stu-id="cccca-112">Additionally, multiple tests can use the same test variables to record results.</span></span>

## <a name="examples-of-test-variables"></a><span data-ttu-id="cccca-113">Példák tesztváltozókra</span><span class="sxs-lookup"><span data-stu-id="cccca-113">Examples of test variables</span></span>

### <a name="example-1"></a><span data-ttu-id="cccca-114">1. példa</span><span class="sxs-lookup"><span data-stu-id="cccca-114">Example 1</span></span>

<span data-ttu-id="cccca-115">Egy gyártóvállalat két tesztet végez el a gyártott anyagokon.</span><span class="sxs-lookup"><span data-stu-id="cccca-115">A manufacturing company performs two tests on manufactured materials.</span></span> <span data-ttu-id="cccca-116">Az egyik tesztben a pH-szint egy színcsíkhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="cccca-116">In one test, the pH level is associated with a color strip.</span></span> <span data-ttu-id="cccca-117">Az elfogadható pH-szintek a világosabb színek, a nem elfogadható pH-szintek a sötétebb színek.</span><span class="sxs-lookup"><span data-stu-id="cccca-117">Acceptable pH levels are in lighter colors, and unacceptable pH levels are in darker colors.</span></span> <span data-ttu-id="cccca-118">Egy másik teszten több vizuális vizsgálatot végeznek, és a minőségbiztosítási dolgozók saját belátásuk szerint döntik el, hogy a cikk megfelelő-e, vagy sem.</span><span class="sxs-lookup"><span data-stu-id="cccca-118">In another test, multiple visual inspections are performed, and quality workers use their judgement to determine whether the item passes or fails the visual inspection.</span></span>

### <a name="example-2"></a><span data-ttu-id="cccca-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="cccca-119">Example 2</span></span>

<span data-ttu-id="cccca-120">Egy süteménygyártó a készterméken vizsgálatot végez.</span><span class="sxs-lookup"><span data-stu-id="cccca-120">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="cccca-121">A vizsgálat tesztnek többféle változója van.</span><span class="sxs-lookup"><span data-stu-id="cccca-121">This inspection test has several variables.</span></span> <span data-ttu-id="cccca-122">Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz.</span><span class="sxs-lookup"><span data-stu-id="cccca-122">One variable is taste, and the possible outcomes for it are good and bad.</span></span> <span data-ttu-id="cccca-123">Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</span><span class="sxs-lookup"><span data-stu-id="cccca-123">A second variable is color, and the possible outcomes for it are too dark, too light, and correct.</span></span>

## <a name="create-a-test-variable"></a><span data-ttu-id="cccca-124">Új tesztváltozó létrehozása</span><span class="sxs-lookup"><span data-stu-id="cccca-124">Create a test variable</span></span>

<span data-ttu-id="cccca-125">Tesztváltozó létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cccca-125">Follow these steps to create a test variable.</span></span>

1. <span data-ttu-id="cccca-126">Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztváltozók** elemre.</span><span class="sxs-lookup"><span data-stu-id="cccca-126">Go to **Inventory management \> Setup \> Quality control \> Test variables**.</span></span>
1. <span data-ttu-id="cccca-127">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="cccca-127">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="cccca-128">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="cccca-128">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="cccca-129">**Változó** – Adja meg a változó egyedi azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="cccca-129">**Variable** – Enter a unique ID or name for the variable.</span></span>
    - <span data-ttu-id="cccca-130">**Leírás** – Adja meg a változó részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="cccca-130">**Description** – Enter a detailed description of the variable.</span></span>

1. <span data-ttu-id="cccca-131">Amíg az új sor még ki van választva, válassza ki az **Eredményeket** a műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="cccca-131">While the new row is still selected, select **Outcomes** on the Action Pane.</span></span>
1. <span data-ttu-id="cccca-132">A **Tesztváltozó eredményei** oldalon a Műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához.</span><span class="sxs-lookup"><span data-stu-id="cccca-132">On the **Test variable outcomes** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="cccca-133">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="cccca-133">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="cccca-134">**Eredmény** – Adja meg az eredmény egyedi azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="cccca-134">**Outcome** – Enter a unique ID or name for the outcome.</span></span>
    - <span data-ttu-id="cccca-135">**Leírás** – Adja meg az eredmény részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="cccca-135">**Description** – Enter a detailed description of the outcome.</span></span>
    - <span data-ttu-id="cccca-136">**Eredmény állapota** Mindegyik eredménynél a *Sikeres* vagy *Sikertelen* eredményállapot hozzárendelésével kell jelezni, hogy a teszt sikeres vagy sikertelen volt, amennyiben az eredményt teszteredményként választják ki.</span><span class="sxs-lookup"><span data-stu-id="cccca-136">**Outcome status** – Select either *Pass* or *Fail* to indicate whether the test is passed or failed when the outcome is selected as a test result.</span></span>

1. <span data-ttu-id="cccca-137">Ismételje meg az előző lépést minden további eredményhez.</span><span class="sxs-lookup"><span data-stu-id="cccca-137">Repeat the previous step for each additional outcome.</span></span> <span data-ttu-id="cccca-138">Győződjön meg róla, hogy legalább egy eredményállapot *Sikeres*, és legalább egy eredményállapot *Sikertelen*.</span><span class="sxs-lookup"><span data-stu-id="cccca-138">Make sure that at least one outcome has an outcome status of *Pass* and at least one has an outcome status of *Fail*.</span></span>
1. <span data-ttu-id="cccca-139">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="cccca-139">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cccca-140">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cccca-140">Additional resources</span></span>

- [<span data-ttu-id="cccca-141">Minőségbiztosítási tesztműszerek</span><span class="sxs-lookup"><span data-stu-id="cccca-141">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="cccca-142">Minőségkezelési tesztek</span><span class="sxs-lookup"><span data-stu-id="cccca-142">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="cccca-143">Minőségbiztosítási tesztcsoportok</span><span class="sxs-lookup"><span data-stu-id="cccca-143">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

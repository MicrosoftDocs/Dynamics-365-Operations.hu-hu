---
title: Minőségbiztosítási tesztek
description: Ez a témakör azt mutatja be, hogyan lehet teszteket létrehozni, amelyek minőségi rendelésekhez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
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
ms.openlocfilehash: b88011f486b6582db4727b85d021868899c6abe1
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956683"
---
# <a name="quality-management-tests"></a><span data-ttu-id="e4dee-103">Minőségbiztosítási tesztek</span><span class="sxs-lookup"><span data-stu-id="e4dee-103">Quality management tests</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4dee-104">Ez a témakör azt mutatja be, hogyan lehet teszteket létrehozni, amelyek minőségi rendelésekhez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="e4dee-104">This topic describes how to create tests that can be used for quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="e4dee-105">A **Tesztek** oldalon lehet meghatározni és megtekinteni azokat a teszteket, amelyekkel megállapítható, hogy a termékek megfelelnek-e a minőségi specifikációknak.</span><span class="sxs-lookup"><span data-stu-id="e4dee-105">You use the **Tests** page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="e4dee-106">Hozzárendelhet egy vagy több különálló tesztet egy tesztcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="e4dee-106">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="e4dee-107">Ebben az esetben tesztspecifikus adatokat is megadhat, például az elfogadható mérési értékeket.</span><span class="sxs-lookup"><span data-stu-id="e4dee-107">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="e4dee-108">A mértékegységeket a mennyiségi teszteknél lehet használni.</span><span class="sxs-lookup"><span data-stu-id="e4dee-108">Measurement values are used for quantitative tests.</span></span> <span data-ttu-id="e4dee-109">A kvalitatív tesztekhez tesztváltozókat kell használni.</span><span class="sxs-lookup"><span data-stu-id="e4dee-109">For qualitative tests, test variables are used.</span></span>

- <span data-ttu-id="e4dee-110">Mennyiségi teszt esetén a **Típus** mező beállítása *Tört* vagy *Egész szám*.</span><span class="sxs-lookup"><span data-stu-id="e4dee-110">For quantitative tests, the **Type** field is set to *Integer* or *Fraction*.</span></span> <span data-ttu-id="e4dee-111">Mértékegység is meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="e4dee-111">A unit of measure is also specified.</span></span> <span data-ttu-id="e4dee-112">A minőségi specifikációk és a teszteredmények számokként fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="e4dee-112">Quality specifications and test results are expressed as numbers.</span></span>
- <span data-ttu-id="e4dee-113">(Minőségi tesztek esetén a **Típus** mező értéke legyen *Lehetőség*.)</span><span class="sxs-lookup"><span data-stu-id="e4dee-113">For qualitative tests, the **Type** field is set to *Option*.</span></span> <span data-ttu-id="e4dee-114">A minőségi tesztekhez további, a mérendő tesztváltozóra és annak sorszámozott lehetőségeire vonatkozó adatok szükségesek.</span><span class="sxs-lookup"><span data-stu-id="e4dee-114">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="e4dee-115">A minőségi specifikációk és a teszteredmények egy eredménynek megfelelően fejeződnek ki.</span><span class="sxs-lookup"><span data-stu-id="e4dee-115">Quality specifications and test results are expressed according to an outcome.</span></span>

<span data-ttu-id="e4dee-116">Opcionálisan tesztműszert is hozzá lehet rendelni egy teszthez.</span><span class="sxs-lookup"><span data-stu-id="e4dee-116">You can optionally assign a test instrument to a test.</span></span> <span data-ttu-id="e4dee-117">A minőségi rendelésekhez azonban nem szükséges tesztműszereket létrehozni és használni.</span><span class="sxs-lookup"><span data-stu-id="e4dee-117">However, test instruments aren't required to create and use tests with quality orders.</span></span> <span data-ttu-id="e4dee-118">További információért lásd: [Minőségbiztosítási tesztműszerek](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="e4dee-118">For more information, see [Quality management test instruments](quality-test-instruments.md).</span></span>

<span data-ttu-id="e4dee-119">A tesztekhez tetszés szerint megadhat egy egységet is, ezzel jelezheti, a mértékegységet, amelyben a teszteredményeket rögzítik.</span><span class="sxs-lookup"><span data-stu-id="e4dee-119">You can also optionally specify a unit for a test, to indicate the unit of measure that test results are recorded in.</span></span> <span data-ttu-id="e4dee-120">Például a hőmérséklet-teszthez tartozhat egy Fahrenheit vagy Celsius.</span><span class="sxs-lookup"><span data-stu-id="e4dee-120">For example, a test for temperature might include a unit of either degrees Fahrenheit or degrees Celsius.</span></span>

## <a name="example-of-a-test"></a><span data-ttu-id="e4dee-121">Példa egy tesztre</span><span class="sxs-lookup"><span data-stu-id="e4dee-121">Example of a test</span></span>

<span data-ttu-id="e4dee-122">Egy gyártóvállalat a beszerzett anyagon két tesztet végez el: ezek egyike az anyagminőséggel kapcsolatos mennyiségi teszt, a másik pedig a csomagolási sérüléseket felmérő minőségi teszt.</span><span class="sxs-lookup"><span data-stu-id="e4dee-122">A manufacturing company performs two tests on purchased material: a quantitative test for material quality and a qualitative test for packaging damage.</span></span> <span data-ttu-id="e4dee-123">A vállalat további adatokat ad meg a kvalitatív tesztre vonatkozóan, hogy azonosítsa a tesztváltozót (például sérült csomagolás) és annak kimeneteleit.</span><span class="sxs-lookup"><span data-stu-id="e4dee-123">The company specifies additional information about the qualitative test to define the test variable (for example, damaged packaging) and its outcomes.</span></span> <span data-ttu-id="e4dee-124">A vállalat a **Tesztcsoportok** oldalon hozzárendeli a két tesztet egy tesztcsoporthoz és megadja a tesztspecifikus adatokat.</span><span class="sxs-lookup"><span data-stu-id="e4dee-124">The company uses the **Test groups** page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="e4dee-125">A tesztcsoportot hozzárendeli egy minőségi rendeléshez, hogy a két teszt eredményét jelenteni tudja.</span><span class="sxs-lookup"><span data-stu-id="e4dee-125">The test group is assigned to a quality order so that the company can report test results for the two tests.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="e4dee-126">Teszt létrehozása</span><span class="sxs-lookup"><span data-stu-id="e4dee-126">Create a test</span></span>

<span data-ttu-id="e4dee-127">Teszt létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e4dee-127">Follow these steps to create a test.</span></span>

1. <span data-ttu-id="e4dee-128">Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztek** elemre.</span><span class="sxs-lookup"><span data-stu-id="e4dee-128">Go to **Inventory management \> Setup \> Quality control \> Tests**.</span></span>
1. <span data-ttu-id="e4dee-129">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="e4dee-129">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="e4dee-130">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="e4dee-130">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="e4dee-131">**Teszt** – Adja meg a teszt egyedi azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="e4dee-131">**Test** – Enter a unique ID or name for the test.</span></span>
    - <span data-ttu-id="e4dee-132">**Leírás** – Adja meg a teszt részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="e4dee-132">**Description** – Enter a detailed description of the test.</span></span>
    - <span data-ttu-id="e4dee-133">**Típus** – válassza ki a teszt által biztosított eredmények típusát.</span><span class="sxs-lookup"><span data-stu-id="e4dee-133">**Type** – Select the type of results that the test produces.</span></span> <span data-ttu-id="e4dee-134">Mennyiségi tesztek esetén válassza a *Tört* vagy az *Egész érték* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e4dee-134">For quantitative tests, select *Fraction* or *Integer*.</span></span> <span data-ttu-id="e4dee-135">Kvalitatív tesztek esetén válassza a *Lehetőség* értéket.</span><span class="sxs-lookup"><span data-stu-id="e4dee-135">For qualitative tests, select *Option*.</span></span>
    - <span data-ttu-id="e4dee-136">**Tesztműszer** – Válassza ki a teszthez használt [tesztműszert](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="e4dee-136">**Test instrument** – Select a [test instrument](quality-test-instruments.md) that should be used for the test.</span></span>
    - <span data-ttu-id="e4dee-137">**Egység** – ha a *Típus* mezőben a *Tört* vagy **Egész szám** lehetőséget választotta (azaz mennyiségi tesztről van szó), válassza ki azt a mértékegységet, amelyben a teszteredményeket rögzíteni kell.</span><span class="sxs-lookup"><span data-stu-id="e4dee-137">**Unit** – If you selected *Fraction* or *Integer* in the **Type** field (that is, if the test is a quantitative test), select the unit of measure that test results should be recorded in.</span></span>

1. <span data-ttu-id="e4dee-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e4dee-138">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="e4dee-139">A teszt mentése után a rácsban már nem szerkeszthető a **Típus** mező.</span><span class="sxs-lookup"><span data-stu-id="e4dee-139">After you save a test, you can no longer edit the **Type** field in the grid.</span></span> <span data-ttu-id="e4dee-140">Ha módosítania kell egy teszthez rögzíteni kívánt teszteredmények típusát, válassza a Műveleti panelen a **Minőségteszt típusának módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e4dee-140">If you must change the type of test results that will be recorded for a test, select **Change quality test type** on the Action Pane.</span></span> <span data-ttu-id="e4dee-141">A **Minőségteszt típusának módosítása** párbeszédpanelen állítsa a kívánt típusra az **Új típus** mezőt, majd a párbeszédpanel bezárásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="e4dee-141">In the **Change quality test type** dialog box, set the **New type** field to the desired type, and then select **OK** to close the dialog box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4dee-142">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e4dee-142">Additional resources</span></span>

- [<span data-ttu-id="e4dee-143">Minőségbiztosítási tesztműszerek</span><span class="sxs-lookup"><span data-stu-id="e4dee-143">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="e4dee-144">Minőségbiztosítási tesztcsoportok</span><span class="sxs-lookup"><span data-stu-id="e4dee-144">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="e4dee-145">Minőségbiztosítási tesztváltozók</span><span class="sxs-lookup"><span data-stu-id="e4dee-145">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="e4dee-146">Minőségi társítások</span><span class="sxs-lookup"><span data-stu-id="e4dee-146">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

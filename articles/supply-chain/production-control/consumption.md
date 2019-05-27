---
title: Anyagfelhasználás kiszámítása
description: Ez a cikk tájékoztatást nyújt az anyagfelhasználás kiszámításához kapcsolódó különféle lehetőségekkel kapcsolatban.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e4010b5abb6b5a871d098422f1489cb2db3a071
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572650"
---
# <a name="calculate-material-consumption"></a><span data-ttu-id="c4c62-103">Anyagfelhasználás kiszámítása</span><span class="sxs-lookup"><span data-stu-id="c4c62-103">Calculate material consumption</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4c62-104">Ez a cikk tájékoztatást nyújt az anyagfelhasználás kiszámításához kapcsolódó különféle lehetőségekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="c4c62-104">This article provides information about various options that are related to the calculation of material consumption.</span></span> 

<span data-ttu-id="c4c62-105">A következő, anyagfelhasználás kiszámításához való lehetőségek a **Beállítás** és **Fokozatos felhasználás** a lapokon, a **Sor adatai** gyorslapjon, az **Anyagjegyzék** oldalon érhetők el.</span><span class="sxs-lookup"><span data-stu-id="c4c62-105">The following options that are related to the calculation of material consumption are available on the **Setup** and **Step consumption** tabs on the **Line details** FastTab of the **Bill of materials** page.</span></span>

## <a name="variable-and-constant-consumption"></a><span data-ttu-id="c4c62-106">Változó és állandó felhasználás</span><span class="sxs-lookup"><span data-stu-id="c4c62-106">Variable and constant consumption</span></span>
<span data-ttu-id="c4c62-107">A **Felhasználás** mezőben kiválaszthatja, hogy a felhasználás állandó vagy változó mennyiségként legyen kiszámolva.</span><span class="sxs-lookup"><span data-stu-id="c4c62-107">In the **Consumption is** field, you can select whether consumption should be calculated as a constant quantity or a variable quantity.</span></span> <span data-ttu-id="c4c62-108">Válassza az **Állandó** lehetőséget, ha egy fix mennyiség vagy terjedelem szükséges a termeléshez, a termelt mennyiségtől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="c4c62-108">Select **Constant** if a fixed quantity or volume is required for the production, regardless of the quantity that is produced.</span></span> <span data-ttu-id="c4c62-109">Válassza a **Változó**lehetőséget, amely az alapértelmezett beállítás, ha a szükséges anyag a késztermékek mérete arányos a befejezett termékek számával.</span><span class="sxs-lookup"><span data-stu-id="c4c62-109">Select **Variable**, which is the default setting, if the required amount of material in the finished goods is proportional to the number of finished goods that are produced.</span></span>

## <a name="calculating-consumption-from-a-formula"></a><span data-ttu-id="c4c62-110">Felhasználás számítása képletből</span><span class="sxs-lookup"><span data-stu-id="c4c62-110">Calculating consumption from a formula</span></span>
<span data-ttu-id="c4c62-111">A **Képlet** mezőben be lehet állítani különböző képleteket az anyagfelhasználás kiszámítására.</span><span class="sxs-lookup"><span data-stu-id="c4c62-111">In the **Formula** field, you can set up various formulas for calculating material consumption.</span></span> <span data-ttu-id="c4c62-112">Ha az alapértelmezett **Normál** értéket használja, a felhasználás a nem képletből lesz kiszámolva.</span><span class="sxs-lookup"><span data-stu-id="c4c62-112">If you use the default value, **Standard**, the consumption isn't calculated from a formula.</span></span> <span data-ttu-id="c4c62-113">A következő képletek együttműködnek a **Magasság**, **Szélesség**, **Mélység**, **Dűrűség**, és **Állandó** mezőkkel:</span><span class="sxs-lookup"><span data-stu-id="c4c62-113">The following formulas work together with the **Height**, **Width**, **Depth**, **Density**, and **Constant** fields:</span></span>

-   <span data-ttu-id="c4c62-114">Magasság \* Konstans</span><span class="sxs-lookup"><span data-stu-id="c4c62-114">Height \* Constant</span></span>
-   <span data-ttu-id="c4c62-115">Magasság \* Szélesség \* Konstans</span><span class="sxs-lookup"><span data-stu-id="c4c62-115">Height \* Width \* Constant</span></span>
-   <span data-ttu-id="c4c62-116">Magasság \* Szélesség \* Mélység \* Konstans</span><span class="sxs-lookup"><span data-stu-id="c4c62-116">Height \* Width \* Depth \* Constant</span></span>
-   <span data-ttu-id="c4c62-117">(Magasság \* Szélesség \* Mélység / Sűrűség) \* Konstans</span><span class="sxs-lookup"><span data-stu-id="c4c62-117">(Height \* Width \* Depth / Density) \* Constant</span></span>

## <a name="rounding-up-and-multiples"></a><span data-ttu-id="c4c62-118">Kerekítés és többszörösök</span><span class="sxs-lookup"><span data-stu-id="c4c62-118">Rounding up and multiples</span></span>
<span data-ttu-id="c4c62-119">A **Kerekítés** és a **Többszörösök** mezők együttesen lehetővé teszik az anyagfelhasználás értékének kerekítését.</span><span class="sxs-lookup"><span data-stu-id="c4c62-119">Together, the **Rounding up** and **Multiples** fields let you round up the material consumption value.</span></span> <span data-ttu-id="c4c62-120">Például az anyagkezelési egység szerint kerekítheti az értéket, amelyben a nyersanyagot kitárolják a termeléshez.</span><span class="sxs-lookup"><span data-stu-id="c4c62-120">For example, you can round up the value according to the handling unit in which the raw material is picked for production.</span></span> <span data-ttu-id="c4c62-121">A következő lehetőségek érhetők el a **Kerekítés** mezőben: **Mennyiség**, **Mérték**, és **Felhasználás**.</span><span class="sxs-lookup"><span data-stu-id="c4c62-121">The following options are available in the **Rounding up** field: **Quantity**, **Measurement**, and **Consumption**.</span></span>

### <a name="quantity"></a><span data-ttu-id="c4c62-122">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="c4c62-122">Quantity</span></span>

<span data-ttu-id="c4c62-123">Ha bejelöli **Mennyiség** lehetőséget a kerekítés módszereként, a mennyiségnek a megadott mennyiség többszörösének kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c4c62-123">If you select **Quantity** as the rounding-up mechanism, the quantity must be a multiple of the specified quantity.</span></span> <span data-ttu-id="c4c62-124">Ha például csak egész számokat lehet megadni, válassza ki az **1** értéket a **Többszörösök** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c4c62-124">For example, if whole numbers are required, select **1** in the **Multiples** field.</span></span> <span data-ttu-id="c4c62-125">Így a számok 1-el osztható mennyiségre lesznek kerekítve.</span><span class="sxs-lookup"><span data-stu-id="c4c62-125">Numbers are then rounded up to a quantity that is divisible by 1.</span></span>

### <a name="measurement"></a><span data-ttu-id="c4c62-126">Mérték</span><span class="sxs-lookup"><span data-stu-id="c4c62-126">Measurement</span></span>

<span data-ttu-id="c4c62-127">Általában a **Mérték** lehetőséget kell a kerekítés módszerként választani, ha a nyersanyag meghatározott méretekben érkezik.</span><span class="sxs-lookup"><span data-stu-id="c4c62-127">Typically, you select **Measurement** as the rounding-up mechanism when the raw material comes in specific dimensions.</span></span> <span data-ttu-id="c4c62-128">Például egy 2 méteres fémcső szükséges egy késztermékhez, és fémcsövet 4,5 méteres hosszúságban tárolják.</span><span class="sxs-lookup"><span data-stu-id="c4c62-128">For example, a piece of 2-meter metal tube is required for a finished good, and the metal tube is stored in 4.5-meter lengths.</span></span> <span data-ttu-id="c4c62-129">Ebben az esetben a **Mérték** kerekítési mechanizmusa használható annak kiszámítására, hogy hány fémcsőre van szükség egy adott számú késztermék előállításához.</span><span class="sxs-lookup"><span data-stu-id="c4c62-129">In this case, the **Measurement** rounding-up mechanism can be used to calculate how many metal tubes are required to produce a specific number of pieces of the finished good.</span></span> <span data-ttu-id="c4c62-130">Ebben a példában a **Képlet** mező értéke a **Magasság \* Konstans**  értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="c4c62-130">For this example, the **Formula** field is set to **Height \* Constant**.</span></span> <span data-ttu-id="c4c62-131">A **Magasság** mező értéke **2**, amely a késztermékhez szükséges csőhosszt jelzi.</span><span class="sxs-lookup"><span data-stu-id="c4c62-131">The **Height** field is set to **2** to indicate the length of the tube that is required for the finished good.</span></span> <span data-ttu-id="c4c62-132">A **Többszörös** mező értéke **4,5**, amely jelzi, hogy a cső 4,5 méteres hosszban lesz kitárolva.</span><span class="sxs-lookup"><span data-stu-id="c4c62-132">The **Multiple** field is set to **4.5** to indicate that the tube is picked in lengths of 4.5 meters.</span></span> <span data-ttu-id="c4c62-133">A számítás a következő:</span><span class="sxs-lookup"><span data-stu-id="c4c62-133">Here is the calculation:</span></span>

1.  <span data-ttu-id="c4c62-134">A 10 darab késztermékhez szükséges többszörösök száma: 10 ÷ 2 = 5 darab</span><span class="sxs-lookup"><span data-stu-id="c4c62-134">Number of multiples that are required for 10 pieces of the finished good: 10 ÷ 2 = 5 pieces</span></span>
2.  <span data-ttu-id="c4c62-135">Összes felhasználás: 4,5 x 5 = 22,5 méter fémcső.</span><span class="sxs-lookup"><span data-stu-id="c4c62-135">Total consumption:  4.5 × 5 = 22.5 meters of metal tube</span></span>

<span data-ttu-id="c4c62-136">A feltételezés szerint 0,5 méter selejtcső keletkezik minden 5 darab felhasznált cső után.</span><span class="sxs-lookup"><span data-stu-id="c4c62-136">It's assumed that 0.5 meter of tube is scrapped for every five pieces of tube that are consumed.</span></span>

### <a name="consumption"></a><span data-ttu-id="c4c62-137">Felhasználás</span><span class="sxs-lookup"><span data-stu-id="c4c62-137">Consumption</span></span>

<span data-ttu-id="c4c62-138">Általában a**Felhasználás** lehetőséget kell kerekítési módszerként választani, ha a nyersanyagot a termék egy adott anyagkezelési egység teljes mennyiségében kell megadni.</span><span class="sxs-lookup"><span data-stu-id="c4c62-138">Typically, you select **Consumption** as the rounding-up mechanism when raw material must be picked in whole quantities of a specific handling unit of the product.</span></span> <span data-ttu-id="c4c62-139">Például 2 liter festékre van szükség egy darab késztermékhez, és a festéket 25 literes tartályokban tárolják ki.</span><span class="sxs-lookup"><span data-stu-id="c4c62-139">For example, 2 quarts of paint are used to produce one piece of a finished good, and the paint is picked in 25-quart cans.</span></span> <span data-ttu-id="c4c62-140">Ebben az esetben a **Felhasználás** kerekítési mechanizmusa használható a 25 literes tartályok esetében az egész számokra való kerekítéshez.</span><span class="sxs-lookup"><span data-stu-id="c4c62-140">In this case, the **Consumption** rounding-up mechanism can be used to round up consumption to whole numbers of 25-quart cans.</span></span> <span data-ttu-id="c4c62-141">Ha 180 darab késztermékre van szükség, így lehet kiszámítani a szükséges festék mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="c4c62-141">Here is the calculation for the amount of paint that is required if 180 pieces of the finished good must be produced:</span></span>

1.  <span data-ttu-id="c4c62-142">Szükséges festék, a selejtet leszámítva: 180 x 2 = 360 liter</span><span class="sxs-lookup"><span data-stu-id="c4c62-142">Paint that is required, excluding scrap: 180 × 2 = 360 quarts</span></span>
2.  <span data-ttu-id="c4c62-143">Festékes dobozok száma: 360 ÷ 25 = 14,4, amely kerekítve 15.</span><span class="sxs-lookup"><span data-stu-id="c4c62-143">Number of cans: 360 ÷ 25 = 14.4, which is rounded up to 15</span></span>
3.  <span data-ttu-id="c4c62-144">Szükséges festék, a selejtet beleszámítva: 15 x 25 = 375 liter</span><span class="sxs-lookup"><span data-stu-id="c4c62-144">Paint that is required, including scrap: 15 × 25 = 375 quarts</span></span>

## <a name="step-consumption"></a><span data-ttu-id="c4c62-145">Fokozatos felhasználás</span><span class="sxs-lookup"><span data-stu-id="c4c62-145">Step consumption</span></span>
<span data-ttu-id="c4c62-146">A fokozatos felhasználást kell használni a mennyiségi intervallumokban történő állandó felhasználás kiszámítására.</span><span class="sxs-lookup"><span data-stu-id="c4c62-146">Step consumption is used to calculate constant consumption in quantity intervals.</span></span> <span data-ttu-id="c4c62-147">Ha bejelöli a **Fokozatos felhasználás** elemet a **Képlet** mezőbe a **Beállítás** lapon, hozzáadhat információkat a lépésekről a **Fokozatos felhasználás** lapon. A rögzített felhasznált mennyiség a megtermelt mennyiség intervallumait állítható be.</span><span class="sxs-lookup"><span data-stu-id="c4c62-147">If you select **Step consumption** in the **Formula** field on the **Setup** tab, you can add information about the steps on the **Step consumption** tab. The fixed consumed quantity can be set up in intervals of the produced quantity.</span></span> <span data-ttu-id="c4c62-148">Például a fokozatos felhasználás a következő táblázatban látható módon van beállítva.</span><span class="sxs-lookup"><span data-stu-id="c4c62-148">For example, step consumption is set up as shown in the following table.</span></span>

| <span data-ttu-id="c4c62-149">Kezdő sorozat</span><span class="sxs-lookup"><span data-stu-id="c4c62-149">From series</span></span> | <span data-ttu-id="c4c62-150">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="c4c62-150">Quantity</span></span> |
|-------------|----------|
| <span data-ttu-id="c4c62-151">0,00</span><span class="sxs-lookup"><span data-stu-id="c4c62-151">0.00</span></span>        | <span data-ttu-id="c4c62-152">10.0000</span><span class="sxs-lookup"><span data-stu-id="c4c62-152">10.0000</span></span>  |
| <span data-ttu-id="c4c62-153">100,00</span><span class="sxs-lookup"><span data-stu-id="c4c62-153">100.00</span></span>      | <span data-ttu-id="c4c62-154">20.0000</span><span class="sxs-lookup"><span data-stu-id="c4c62-154">20.0000</span></span>  |
| <span data-ttu-id="c4c62-155">200,00</span><span class="sxs-lookup"><span data-stu-id="c4c62-155">200.00</span></span>      | <span data-ttu-id="c4c62-156">40.0000</span><span class="sxs-lookup"><span data-stu-id="c4c62-156">40.0000</span></span>  |

<span data-ttu-id="c4c62-157">Az anyagjegyzék (AJ) mennyisége 1, a termelési mennyiség pedig 110.</span><span class="sxs-lookup"><span data-stu-id="c4c62-157">The bill of materials (BOM) quantity is 1, and the production quantity is 110.</span></span> <span data-ttu-id="c4c62-158">A felhasználás receptúrája: Kezdő sorozat (Mennyiség) = Felhasználás.</span><span class="sxs-lookup"><span data-stu-id="c4c62-158">The formula for the consumption is From series (Quantity) = Consumption.</span></span> <span data-ttu-id="c4c62-159">Mivel a termelési mennyiség 110, az beleesik a „100 fölött” sorozatba.</span><span class="sxs-lookup"><span data-stu-id="c4c62-159">Because the production quantity is 110, it falls into the "From 100 series."</span></span> <span data-ttu-id="c4c62-160">Ezért a mennyiség 20.</span><span class="sxs-lookup"><span data-stu-id="c4c62-160">Therefore, the quantity is 20.</span></span>




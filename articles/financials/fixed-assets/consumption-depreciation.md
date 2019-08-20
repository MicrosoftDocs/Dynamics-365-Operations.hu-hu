---
title: Felhasználás értékcsökkenése
description: Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c9d95a7a45ed99c63516749285126c786685c87
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840697"
---
# <a name="consumption-depreciation"></a><span data-ttu-id="7a773-103">Felhasználás értékcsökkenése</span><span class="sxs-lookup"><span data-stu-id="7a773-103">Consumption depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a773-104">Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="7a773-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="7a773-105">Ha beállít egy tárgyi eszközök értékcsökkenésével kapcsolatos profilt, és a **Felhasználás** lehetőséget választja ki a **Mód** mezőben az **Értékcsökkenési profilok** oldalán, akkor az ehhez az értékcsökkenési profilhoz társított tárgyi eszközök értékcsökkenése a tárgyi eszközök használatán alapul.</span><span class="sxs-lookup"><span data-stu-id="7a773-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="7a773-106">Nem kell a százalékos értékeket és az időszakokat beállítsani az **Értékcsökkenési profilok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7a773-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="7a773-107">Miután létrehozta a Felhasználási módot alkalmazó értékcsökkenési profilt, többféle módon is beállíthatja a módszert.</span><span class="sxs-lookup"><span data-stu-id="7a773-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="7a773-108">Felhasználási értékcsökkenés beállítása és használata</span><span class="sxs-lookup"><span data-stu-id="7a773-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="7a773-109">Az **Értékcsökkenési profilok** oldalon hozza létre az értékcsökkenési profilt.</span><span class="sxs-lookup"><span data-stu-id="7a773-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="7a773-110">A felhasználási számításokhoz az értékcsökkenési profilnak tartalmaznia kell egy azonosítót és egy nevet és **Felhasználás** lehetőséget ki kell választani a **Módszer** mezőben.</span><span class="sxs-lookup"><span data-stu-id="7a773-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="7a773-111">Az **Felhasználási tényezők** lapon állítsa be a felhasználási tényezőket.</span><span class="sxs-lookup"><span data-stu-id="7a773-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="7a773-112">Minden felhasználási tényezőnek rendelkeznie kell egy Azonosítóval és egy névvel és egy felhasználási tényezővel, amely vagy mennyiségben vagy százalékban van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="7a773-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="7a773-113">Az **Felhasználási egységek** lapon állítsa be a felhasználási egységeket.</span><span class="sxs-lookup"><span data-stu-id="7a773-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="7a773-114">Minden egyes felhasználási egységnek azonosítóval és névvel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="7a773-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="7a773-115">A felhasználási értékcsökkenést a felhasználási értékcsökenés kiszámítására használják a **Felhasználási értékcsökkenés** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7a773-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="7a773-116">Az egység lehet például kilométer (km), kilogramm (kg) és óra.</span><span class="sxs-lookup"><span data-stu-id="7a773-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="7a773-117">A **Tárgyi eszközök** lapon állítsa be az egyes tárgyi eszközöket.</span><span class="sxs-lookup"><span data-stu-id="7a773-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="7a773-118">Az értékcsökkenési profiloktárgyi eszközhoz válassza ki az értékcsökkenési profillal rendelkező értékmodelleket és értékcsökkenési könyveket.</span><span class="sxs-lookup"><span data-stu-id="7a773-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="7a773-119">Be kell állítania az értékmodelleket vagy az értékcsökkenési könyveket a felhasználási értékcsökkenéshez, ha a tárgyi eszközök bármelyike a a Felhasználási módszeren alapuló értékcsökkenési profilokat használja.</span><span class="sxs-lookup"><span data-stu-id="7a773-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="7a773-120">Ezzel a beállítással végezheti el vagy a **Érték modellek** oldal **Értékcsökkenés** lapján vagy a **Értékcsökkenési profil** oldal **Általános** gyorslapján.</span><span class="sxs-lookup"><span data-stu-id="7a773-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="7a773-121">Ugyanaz az értékmodell több tárgyi eszközhöz is használható.</span><span class="sxs-lookup"><span data-stu-id="7a773-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="7a773-122">Az értékcsökkenési profilok a tárgyi eszközhöz választott értékmodell vagy értékcsökkenési könyv részei.</span><span class="sxs-lookup"><span data-stu-id="7a773-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="7a773-123">Nem lehet hozzáadni vagy módosítani az értékcsökkenési profilokat közvetlenül a **Tárgyi eszközök** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7a773-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="7a773-124">Az értékcsökkenési profilokat csak módosítani lehet az **Értékcsökkenés könyvek** lapon.</span><span class="sxs-lookup"><span data-stu-id="7a773-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="7a773-125">Az **Értékmodellek** lapon vagy a **Értékcsökkenési könvyek** lapon, a **Felhasználási értékcsökkenés** mező csoportban adja meg az információkat a következő mezókben:</span><span class="sxs-lookup"><span data-stu-id="7a773-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="7a773-126">Felhasználási tényező</span><span class="sxs-lookup"><span data-stu-id="7a773-126">Consumption factor</span></span>
    -   <span data-ttu-id="7a773-127">Egység</span><span class="sxs-lookup"><span data-stu-id="7a773-127">Unit</span></span>
    -   <span data-ttu-id="7a773-128">Egység értékcsökkenése</span><span class="sxs-lookup"><span data-stu-id="7a773-128">Unit depreciation</span></span>
    -   <span data-ttu-id="7a773-129">Becsült felhasználás</span><span class="sxs-lookup"><span data-stu-id="7a773-129">Estimated consumption</span></span>

    <span data-ttu-id="7a773-130">A**Megadott felhasználás** mező mutatja azon felhasználási értékcsökkenést egységekben, amelyet már megadtak vagy a tárgyi eszközök és értékmodellek kombinációja vagy az értékcsökkenési könyv részére.</span><span class="sxs-lookup"><span data-stu-id="7a773-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="7a773-131">Ebben a mezőben nem frissítheti manuálisan az értéket.</span><span class="sxs-lookup"><span data-stu-id="7a773-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="7a773-132">Példák</span><span class="sxs-lookup"><span data-stu-id="7a773-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="7a773-133">1. példa</span><span class="sxs-lookup"><span data-stu-id="7a773-133">Example 1</span></span>

<span data-ttu-id="7a773-134">Az alábbi felhasználási tényező van beállítva január 31-re vonatkozóan:</span><span class="sxs-lookup"><span data-stu-id="7a773-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="7a773-135">A mennyiség 1,000.</span><span class="sxs-lookup"><span data-stu-id="7a773-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="7a773-136">A tárgyi eszközhöz megadott egység értékcsökkenési ár 1,5.</span><span class="sxs-lookup"><span data-stu-id="7a773-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="7a773-137">Január 31-i értékcsökkenési javaslat a következőképpen történik: Mennyiség x 1000 x 1,5 = 1500, ha a tárgyi eszköz számára megadott tényező egy százalékos tényező, a **Becsült felhasználás** mezőben megbecsült mennyiség megszorozzák a kiválasztott záró dátumhoz beállított százalékkal.</span><span class="sxs-lookup"><span data-stu-id="7a773-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="7a773-138">Az így kapott mennyiséget a program majd az időszak értékcsökkenési mennyiségeként javasolja.</span><span class="sxs-lookup"><span data-stu-id="7a773-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="7a773-139">2. példa</span><span class="sxs-lookup"><span data-stu-id="7a773-139">Example 2</span></span>

<span data-ttu-id="7a773-140">Január 31-ére vonatkozóan az alábbi tényező van beállítva a felhasználási értékcsökkenéshez:</span><span class="sxs-lookup"><span data-stu-id="7a773-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="7a773-141">A százalékos érték 10 százalék.</span><span class="sxs-lookup"><span data-stu-id="7a773-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="7a773-142">A tárgyi eszközhöz megadott egység értékcsökkenési ár 1,5.</span><span class="sxs-lookup"><span data-stu-id="7a773-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="7a773-143">A tárgyi eszköz becsült mennyisége 2 000.</span><span class="sxs-lookup"><span data-stu-id="7a773-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="7a773-144">Január 31-i értékcsökkenési javaslat a következőképpen történik: Becsült mennyiség x Százalék x Egység értékcsökkenése 2 000 x.10 x 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="7a773-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>




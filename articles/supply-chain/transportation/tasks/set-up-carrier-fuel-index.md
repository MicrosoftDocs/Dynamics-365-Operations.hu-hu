---
title: Szállítmányozói üzemanyag-mutató beállítása
description: Ez az útmutató bemutatja, hogyan hozhat létre üzemanyag-mutató régiót, üzemanyag mutatót és szállítmányozói üzemanyag-mutatót.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1e972f2ba8211c47b11a4b83dac9ff60f813b1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837583"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="041ae-103">Szállítmányozói üzemanyag-mutató beállítása</span><span class="sxs-lookup"><span data-stu-id="041ae-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="041ae-104">Ez az útmutató bemutatja, hogyan hozhat létre üzemanyag-mutató régiót, üzemanyag mutatót és szállítmányozói üzemanyag-mutatót.</span><span class="sxs-lookup"><span data-stu-id="041ae-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="041ae-105">Az üzemanyag-mutató régió megadja, hogy mely régióra kell vonatkoznia az üzemanyag-mutatónak, az üzemanyag-mutató pedig megadja az adott időszakra érvényes üzemanyagárat.</span><span class="sxs-lookup"><span data-stu-id="041ae-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="041ae-106">Üzemanyag-árak időbeli változásának tükrözéséhez több üzemanyag-mutatót is társíthat a szállítmányozóhoz.</span><span class="sxs-lookup"><span data-stu-id="041ae-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="041ae-107">Ezeket a feladatokat általában a szállítási koordinátor végzi.</span><span class="sxs-lookup"><span data-stu-id="041ae-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="041ae-108">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="041ae-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="041ae-109">Üzemanyag-mutató régió létrehozása</span><span class="sxs-lookup"><span data-stu-id="041ae-109">Create a fuel index region</span></span>
1. <span data-ttu-id="041ae-110">Ugorjon a Szállítási kezelés > Beállítás > Üzemanyag-mutatók > Üzemanyag-mutató régiók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="041ae-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="041ae-111">Először létre kell hoznia különböző régiókat, ahol dolgozik, aztán ki kell számolnia az üzemanyag-pótdíjakat.</span><span class="sxs-lookup"><span data-stu-id="041ae-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="041ae-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="041ae-112">Click New.</span></span>
3. <span data-ttu-id="041ae-113">A Régió mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="041ae-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="041ae-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="041ae-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="041ae-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="041ae-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="041ae-116">Hozzon létre egy üzemanyag-mutatót</span><span class="sxs-lookup"><span data-stu-id="041ae-116">Create a fuel index</span></span>
1. <span data-ttu-id="041ae-117">Ugorjon a Szállítási kezelés > Beállítás > Üzemanyag-mutatók > Üzemanyag-mutatók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="041ae-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="041ae-118">A beállított régiókhoz meg kell adnia a jelenlegi üzemanyagárakat.</span><span class="sxs-lookup"><span data-stu-id="041ae-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="041ae-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="041ae-119">Click New.</span></span>
3. <span data-ttu-id="041ae-120">A Régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="041ae-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="041ae-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="041ae-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="041ae-122">Az Ár/gallon mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="041ae-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="041ae-123">Az Érvényesség kezdő dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="041ae-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="041ae-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="041ae-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="041ae-125">Szállítmányozói üzemanyag-mutató létrehozása</span><span class="sxs-lookup"><span data-stu-id="041ae-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="041ae-126">Ugorjon a Szállítási kezelés > Beállítás Üzemanyag-mutatók > Szállítmányozói üzemanyag-mutatók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="041ae-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="041ae-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="041ae-127">Click New.</span></span>
3. <span data-ttu-id="041ae-128">Írjon be egy értéket a Szállítmányozói üzemanyag-mutató mezőbe.</span><span class="sxs-lookup"><span data-stu-id="041ae-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="041ae-129">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="041ae-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="041ae-130">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="041ae-130">Click New.</span></span>
6. <span data-ttu-id="041ae-131">Az Érvényesség kezdő dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="041ae-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="041ae-132">Írjon be egy számot a Kezdő üzemanyagár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="041ae-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="041ae-133">Ebben a példában a Kezdő üzemanyagár mezőt 1,95-re állíthatja.</span><span class="sxs-lookup"><span data-stu-id="041ae-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="041ae-134">Írjon be egy számot a Záró üzemanyagár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="041ae-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="041ae-135">Ebben a példában a Záró üzemanyagár mezőt 2-re állíthatja.</span><span class="sxs-lookup"><span data-stu-id="041ae-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="041ae-136">Adjon meg egy számot a Százalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="041ae-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="041ae-137">Ebben a példában a százalékot 3-ra állíthatja.</span><span class="sxs-lookup"><span data-stu-id="041ae-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="041ae-138">A Pénznem mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="041ae-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="041ae-139">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="041ae-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="041ae-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="041ae-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="041ae-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="041ae-141">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
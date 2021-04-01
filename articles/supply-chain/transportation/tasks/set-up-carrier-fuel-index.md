---
title: Szállítmányozói üzemanyag-mutató beállítása
description: Ez az útmutató bemutatja, hogyan hozhat létre üzemanyag-mutató régiót, üzemanyag mutatót és szállítmányozói üzemanyag-mutatót.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09dc948e673bb8be49ac81e5ad2b20bc6c62b286
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233655"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="82770-103">Szállítmányozói üzemanyag-mutató beállítása</span><span class="sxs-lookup"><span data-stu-id="82770-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82770-104">Ez az útmutató bemutatja, hogyan hozhat létre üzemanyag-mutató régiót, üzemanyag mutatót és szállítmányozói üzemanyag-mutatót.</span><span class="sxs-lookup"><span data-stu-id="82770-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="82770-105">Az üzemanyag-mutató régió megadja, hogy mely régióra kell vonatkoznia az üzemanyag-mutatónak, az üzemanyag-mutató pedig megadja az adott időszakra érvényes üzemanyagárat.</span><span class="sxs-lookup"><span data-stu-id="82770-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="82770-106">Üzemanyag-árak időbeli változásának tükrözéséhez több üzemanyag-mutatót is társíthat a szállítmányozóhoz.</span><span class="sxs-lookup"><span data-stu-id="82770-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="82770-107">Ezeket a feladatokat általában a szállítási koordinátor végzi.</span><span class="sxs-lookup"><span data-stu-id="82770-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="82770-108">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="82770-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="82770-109">Üzemanyag-mutató régió létrehozása</span><span class="sxs-lookup"><span data-stu-id="82770-109">Create a fuel index region</span></span>
1. <span data-ttu-id="82770-110">Ugorjon a Szállítási kezelés > Beállítás > Üzemanyag-mutatók > Üzemanyag-mutató régiók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82770-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="82770-111">Először létre kell hoznia különböző régiókat, ahol dolgozik, aztán ki kell számolnia az üzemanyag-pótdíjakat.</span><span class="sxs-lookup"><span data-stu-id="82770-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="82770-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82770-112">Click New.</span></span>
3. <span data-ttu-id="82770-113">A Régió mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82770-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="82770-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="82770-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="82770-115">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="82770-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="82770-116">Hozzon létre egy üzemanyag-mutatót</span><span class="sxs-lookup"><span data-stu-id="82770-116">Create a fuel index</span></span>
1. <span data-ttu-id="82770-117">Ugorjon a Szállítási kezelés > Beállítás > Üzemanyag-mutatók > Üzemanyag-mutatók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82770-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="82770-118">A beállított régiókhoz meg kell adnia a jelenlegi üzemanyagárakat.</span><span class="sxs-lookup"><span data-stu-id="82770-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="82770-119">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82770-119">Click New.</span></span>
3. <span data-ttu-id="82770-120">A Régió mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="82770-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="82770-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="82770-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="82770-122">Az Ár/gallon mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="82770-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="82770-123">Az Érvényesség kezdő dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="82770-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="82770-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="82770-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="82770-125">Szállítmányozói üzemanyag-mutató létrehozása</span><span class="sxs-lookup"><span data-stu-id="82770-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="82770-126">Ugorjon a Szállítási kezelés > Beállítás Üzemanyag-mutatók > Szállítmányozói üzemanyag-mutatók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82770-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="82770-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82770-127">Click New.</span></span>
3. <span data-ttu-id="82770-128">Írjon be egy értéket a Szállítmányozói üzemanyag-mutató mezőbe.</span><span class="sxs-lookup"><span data-stu-id="82770-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="82770-129">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82770-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="82770-130">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="82770-130">Click New.</span></span>
6. <span data-ttu-id="82770-131">Az Érvényesség kezdő dátuma és időpontja mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="82770-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="82770-132">Írjon be egy számot a Kezdő üzemanyagár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="82770-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="82770-133">Ebben a példában a Kezdő üzemanyagár mezőt 1,95-re állíthatja.</span><span class="sxs-lookup"><span data-stu-id="82770-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="82770-134">Írjon be egy számot a Záró üzemanyagár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="82770-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="82770-135">Ebben a példában a Záró üzemanyagár mezőt 2-re állíthatja.</span><span class="sxs-lookup"><span data-stu-id="82770-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="82770-136">Adjon meg egy számot a Százalék mezőben.</span><span class="sxs-lookup"><span data-stu-id="82770-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="82770-137">Ebben a példában a százalékot 3-ra állíthatja.</span><span class="sxs-lookup"><span data-stu-id="82770-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="82770-138">A Pénznem mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="82770-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="82770-139">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="82770-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="82770-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="82770-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="82770-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="82770-141">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
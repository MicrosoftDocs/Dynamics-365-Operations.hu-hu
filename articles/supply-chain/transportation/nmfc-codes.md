---
title: NMFC (National Motor Freight Classification) kódok
description: Ez a témakör azt mutatja be, hogyan lehet dolgozni az NMFC (National Motor Freight Classification) kódokkal a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0307437d3868f7ac34fa16a0913907a046ac14d4
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941882"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a><span data-ttu-id="8e779-103">NMFC (National Motor Freight Classification) kódok</span><span class="sxs-lookup"><span data-stu-id="8e779-103">National Motor Freight Classification (NMFC) codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e779-104">A NMFC (National Motor Freight Classification) kódok segítségével osztályozhatja a szállítható cikkeket.</span><span class="sxs-lookup"><span data-stu-id="8e779-104">National Motor Freight Classification (NMFC) codes help you classify items that can be shipped.</span></span> <span data-ttu-id="8e779-105">Az NMFC-kód az áruk csoportosítására használható.</span><span class="sxs-lookup"><span data-stu-id="8e779-105">The NMFC code is a designation that is used to group commodities.</span></span> <span data-ttu-id="8e779-106">Lehetővé teszi a szállítmányozási vállalatok számára, hogy a cikkek osztályozása során figyelembe vehessék például a termékek teherautóhoz való illeszkedését, az esetleg felmerülő rakodási és kezelési problémákat, illetve a romlandóságot.</span><span class="sxs-lookup"><span data-stu-id="8e779-106">It enables transport companies to evaluate goods for shipment by classifying items based on considerations such as truck fit, loading issues, handling issues, and perishability.</span></span> <span data-ttu-id="8e779-107">Az áruk 18 fuvarosztályba vannak sorolva 50 és 500 közötti számokkal való rangsorolás segítségével.</span><span class="sxs-lookup"><span data-stu-id="8e779-107">Commodities are grouped into one of 18 freight classes by using a range of numbers from 50 to 500.</span></span> <span data-ttu-id="8e779-108">Az árucikkeket négy szállítási jellemző – a sűrűség, a tárolhatóság, a kezelhetőség és a felelősség – kiértékelése alapján csoportosítják.</span><span class="sxs-lookup"><span data-stu-id="8e779-108">The class that a commodity is grouped into is based on an evaluation of four transportation characteristics: density, stowability, handling, and liability.</span></span> <span data-ttu-id="8e779-109">Ezek a jellemzők együttesen határozzák meg az árucikk szállíthatóságát.</span><span class="sxs-lookup"><span data-stu-id="8e779-109">Together, these characteristics establish the commodity's transportability.</span></span>

<span data-ttu-id="8e779-110">NMFC-kód van társítva minden olyan kisebb cikkhez, amely egy teherautórakománynál (LTL) kisebb.</span><span class="sxs-lookup"><span data-stu-id="8e779-110">An NMFC code is associated with every less than truckload (LTL) shipping item.</span></span> <span data-ttu-id="8e779-111">Például lehet, hogy egy hordozható számítógéphez egy 2,5-ös NMFC van hozzárendelve, míg a elektromos vezetékek hozzárendelhetőek egy 65-ös osztályú NMFC-hez.</span><span class="sxs-lookup"><span data-stu-id="8e779-111">For example, a laptop might be assigned an NMFC that is classed at 2.5, whereas electrical cords might be assigned an NMFC that is classed at 65.</span></span>

<span data-ttu-id="8e779-112">Ez a funkció segít a dolgozóknak az NMFC-kódok használatával az LTL-szállítási cikkek osztályozásában.</span><span class="sxs-lookup"><span data-stu-id="8e779-112">This feature can help workers use NMFC codes to classify LTL shipping items.</span></span> <span data-ttu-id="8e779-113">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="8e779-113">Here are some examples:</span></span>

- <span data-ttu-id="8e779-114">Ha a vállalat fuvarleírást is ad a fuvarlevélhez (BOL), akkor a szállítmányozónak valamilyen elképzelése arról, hogy mit is szállít.</span><span class="sxs-lookup"><span data-stu-id="8e779-114">If your company includes a freight description on the bill of lading (BOL), the carrier will have some idea what the freight is.</span></span> <span data-ttu-id="8e779-115">A szállítmány osztályozása azért fontos, mert sok szállítmányozó vállalat az egész üzleti modelljét az általuk szállított fuvarozási típusokra alapozza.</span><span class="sxs-lookup"><span data-stu-id="8e779-115">Freight is an important classification because many transportation companies base their whole business model on the types of freight that they ship.</span></span>
- <span data-ttu-id="8e779-116">Ez az osztályozás fontos lehet a vállalat számára, mivel ez az adott rakomány költségének megállapítására használható.</span><span class="sxs-lookup"><span data-stu-id="8e779-116">This classification might be essential to your company because it's used to determine the cost of a given load.</span></span>
- <span data-ttu-id="8e779-117">Vállalata azonosíthatja egy LTL-logisztikai és szállítmányozási vállalat nyereségességét.</span><span class="sxs-lookup"><span data-stu-id="8e779-117">Your company can identify the profitability of an LTL logistics and transportation company.</span></span>

<span data-ttu-id="8e779-118">Ez a témakör az NMFC-kódokkal végzett munkát mutatja be a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8e779-118">This topic describes how to work with NMFC codes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8e779-119">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8e779-119">Prerequisites</span></span>

<span data-ttu-id="8e779-120">Az NMFC-kódok létrehozása előtt be kell állítani az összes olyan LTL-fuvarozási sztályt, amelyet le kell képezni a számukra.</span><span class="sxs-lookup"><span data-stu-id="8e779-120">Before you can create NMFC codes, you must set up all the LTL freight classes that must be mapped to them.</span></span> <span data-ttu-id="8e779-121">Az LTL-fuvarozási osztályok cikkkategóriákat képviselnek, míg az NMFC-kódok a 18 fuvarosztály mindegyikében meghatározott árukhoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="8e779-121">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span> <span data-ttu-id="8e779-122">Az LTL-osztályok használatával kapcsolatos további tudnivalókat lásd a [Kisebb, mint egy teherautórakomány (LTL) osztályok](ltl-class.md) részben.</span><span class="sxs-lookup"><span data-stu-id="8e779-122">For more information about how to work with LTL classes, see [Less than truckload (LTL) classes](ltl-class.md).</span></span>

## <a name="create-an-nmfc-code"></a><span data-ttu-id="8e779-123">NMFC-kód létrehozása</span><span class="sxs-lookup"><span data-stu-id="8e779-123">Create an NMFC code</span></span>

<span data-ttu-id="8e779-124">NMFC-kód létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8e779-124">To create an NMFC code, follow these steps.</span></span>

1. <span data-ttu-id="8e779-125">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="8e779-125">Follow one of these steps:</span></span>

    - <span data-ttu-id="8e779-126">Menjen a **Raktárkezelés \> Beállítás \> Készlet \> NMFC-kódok** elemre.</span><span class="sxs-lookup"><span data-stu-id="8e779-126">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
    - <span data-ttu-id="8e779-127">Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozási standardok \> NMFC-kódok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8e779-127">Go to **Transportation management \> Setup \> Transportation standards \> NMFC codes**.</span></span>

1. <span data-ttu-id="8e779-128">Válassza ki az **Új** lehetőséget egy NMFC-kód létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8e779-128">Select **New** to create an NMFC code.</span></span> <span data-ttu-id="8e779-129">Majd, állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="8e779-129">Then set the following fields:</span></span>

    - <span data-ttu-id="8e779-130">**NMFC-kód** – Adja meg a mezőben az árucikk-típus NMFC-kódját.</span><span class="sxs-lookup"><span data-stu-id="8e779-130">**NMFC code** – Enter the NMFC code for the commodity type.</span></span>
    - <span data-ttu-id="8e779-131">**Név** – Adjon egy nevet az NMFC-kódnak.</span><span class="sxs-lookup"><span data-stu-id="8e779-131">**Name** – Enter a name for the NMFC code.</span></span>
    - <span data-ttu-id="8e779-132">**LTL-osztály** – Az NMFC-kódhoz társított LTL-osztály kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="8e779-132">**LTL class** – Select the LTL class that is associated with the NMFC code.</span></span>
    - <span data-ttu-id="8e779-133">**Fuvarlevélkezelési egység** – A szállítmány alapértelmezett kezelési típusának meghatározása.</span><span class="sxs-lookup"><span data-stu-id="8e779-133">**BOL handling unit** – Define the default handling type for the shipment.</span></span>

## <a name="example-set-up-nmfc-codes"></a><span data-ttu-id="8e779-134">Példa: NMFC-kódok beállítása</span><span class="sxs-lookup"><span data-stu-id="8e779-134">Example: Set up NMFC codes</span></span>

<span data-ttu-id="8e779-135">A következő példa bemutatja, hogyan lehet két különböző NMFC-kódot beállítani, amelyek különböző termékekkel használhatók.</span><span class="sxs-lookup"><span data-stu-id="8e779-135">The following example shows how to set up two different NMFC codes that can be used with different products.</span></span>

1. <span data-ttu-id="8e779-136">Menjen a **Raktárkezelés \> Beállítás \> Készlet \> NMFC-kódok** elemre.</span><span class="sxs-lookup"><span data-stu-id="8e779-136">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
1. <span data-ttu-id="8e779-137">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8e779-137">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8e779-138">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="8e779-138">On the new line, set the following values:</span></span>

    - <span data-ttu-id="8e779-139">**NMFC-kód:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="8e779-139">**NMFC code:** *92.5*</span></span>
    - <span data-ttu-id="8e779-140">**Név:** *Számítógépek*</span><span class="sxs-lookup"><span data-stu-id="8e779-140">**Name:** *Computers*</span></span>
    - <span data-ttu-id="8e779-141">**LTL-osztály:** *92,5*</span><span class="sxs-lookup"><span data-stu-id="8e779-141">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="8e779-142">**Fuvarlevél anyagkezelési egység:** *Egység*</span><span class="sxs-lookup"><span data-stu-id="8e779-142">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="8e779-143">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8e779-143">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="8e779-144">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="8e779-144">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="8e779-145">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="8e779-145">On the new line, set the following values:</span></span>

    - <span data-ttu-id="8e779-146">**NMFC-kód:** *125*</span><span class="sxs-lookup"><span data-stu-id="8e779-146">**NMFC code:** *125*</span></span>
    - <span data-ttu-id="8e779-147">**Név:** *Mobiltelefonok*</span><span class="sxs-lookup"><span data-stu-id="8e779-147">**Name:** *Phones*</span></span>
    - <span data-ttu-id="8e779-148">**LTL-osztály:** *125*</span><span class="sxs-lookup"><span data-stu-id="8e779-148">**LTL class:** *125*</span></span>
    - <span data-ttu-id="8e779-149">**Fuvarlevél anyagkezelési egység:** *Egység*</span><span class="sxs-lookup"><span data-stu-id="8e779-149">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="8e779-150">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8e779-150">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8e779-151">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8e779-151">Additional resources</span></span>

- [<span data-ttu-id="8e779-152">Kevesebb mint a teherautóosztályok (LTL)</span><span class="sxs-lookup"><span data-stu-id="8e779-152">Less than truckload (LTL) classes</span></span>](ltl-class.md)
- [<span data-ttu-id="8e779-153">Fuvarlevél létrehozása</span><span class="sxs-lookup"><span data-stu-id="8e779-153">Create a bill of landing</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

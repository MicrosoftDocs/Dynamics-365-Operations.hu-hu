---
title: Mértékegység kezelése
description: Ez az eljárás bemutatja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8d9b6f18fdc1c47d6a695ca6a2330f6f02fc1bd
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2020
ms.locfileid: "3886992"
---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="42bf6-103">Mértékegység kezelése</span><span class="sxs-lookup"><span data-stu-id="42bf6-103">Manage unit of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="42bf6-104">Ez az eljárás bemutatja, hogyan lehet meghatározni egy mértékegységet, meghatározni fordításokat a mértékegységhez és a leírását, és átváltási szabályokat megadni a kapcsolódó egységekhez.</span><span class="sxs-lookup"><span data-stu-id="42bf6-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="42bf6-105">Ezt a folyamatot bemutatóadatokkal vagy saját adatokkal is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="42bf6-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="42bf6-106">Kattintson ide: **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek karbantartása**.</span><span class="sxs-lookup"><span data-stu-id="42bf6-106">Go to **Navigation pane > Modules > Product information management > Released product maintenance**.</span></span>
2. <span data-ttu-id="42bf6-107">Kattintson a **Mértékegységek** elemre.</span><span class="sxs-lookup"><span data-stu-id="42bf6-107">Click **Units**.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="42bf6-108">Mértékegység létrehozása</span><span class="sxs-lookup"><span data-stu-id="42bf6-108">Create a unit of measure</span></span>
1. <span data-ttu-id="42bf6-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="42bf6-109">Click **New**.</span></span>
2. <span data-ttu-id="42bf6-110">Írjon be egy értéket a **Mértékegység** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="42bf6-110">In the **Unit** field, type a value.</span></span> <span data-ttu-id="42bf6-111">Adja meg a mértékegységre történő hivatkozás során használt azonosítót vagy szimbólumot.</span><span class="sxs-lookup"><span data-stu-id="42bf6-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="42bf6-112">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="42bf6-112">In the **Description** field, type a value.</span></span> <span data-ttu-id="42bf6-113">Írjon be egy jellemző nevet a mértékegységnek a rendszer nyelvén.</span><span class="sxs-lookup"><span data-stu-id="42bf6-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="42bf6-114">Válasszon ki egy lehetőséget a **Mértékegységosztály** mezőben.</span><span class="sxs-lookup"><span data-stu-id="42bf6-114">In the **Unit class** field, select an option.</span></span> <span data-ttu-id="42bf6-115">Az egységosztály határozza meg, hogy milyen logikai csoport, például terület, tömeg vagy mennyiség része a mértékegység.</span><span class="sxs-lookup"><span data-stu-id="42bf6-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="42bf6-116">A **Tizedes pontosság** mezőben meg kell adnia egy számot.</span><span class="sxs-lookup"><span data-stu-id="42bf6-116">In the **Decimal precision** field, enter a number.</span></span> <span data-ttu-id="42bf6-117">Adja meg a tizedesek számát, amelyre az átalakított mértékegységet kerekíteni kell a mértékegység számítás befejeztével.</span><span class="sxs-lookup"><span data-stu-id="42bf6-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="42bf6-118">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="42bf6-118">Click **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="42bf6-119">Egység fordításainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="42bf6-119">Define unit translations</span></span>
1. <span data-ttu-id="42bf6-120">A **Művelet panelen** kattintson az **Egységleírások** elemre.</span><span class="sxs-lookup"><span data-stu-id="42bf6-120">On the **Action Pane**, click **Unit texts**.</span></span>
2. <span data-ttu-id="42bf6-121">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="42bf6-121">Click **New**.</span></span> <span data-ttu-id="42bf6-122">Használjon egységes szöveget az azonosító fordítására vagy egy mértékegységet képviselő szimbólumot külső dokumentumokhoz vevő vagy szállító-specifikus nyelveken.</span><span class="sxs-lookup"><span data-stu-id="42bf6-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="42bf6-123">A **Nyelv** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="42bf6-123">In the **Language** field, enter or select a value.</span></span>
4. <span data-ttu-id="42bf6-124">Írjon be egy értéket a **Szöveg** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="42bf6-124">In the **Text** field, type a value.</span></span>
5. <span data-ttu-id="42bf6-125">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="42bf6-125">Click **Save**.</span></span>
6. <span data-ttu-id="42bf6-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42bf6-126">Close the page.</span></span>
7. <span data-ttu-id="42bf6-127">A **Művelet panelen** kattintson az **Lefordított egységleírások** elemre.</span><span class="sxs-lookup"><span data-stu-id="42bf6-127">On the **Action Pane**, click **Translated unit descriptions**.</span></span>
8. <span data-ttu-id="42bf6-128">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="42bf6-128">Click **New**.</span></span> <span data-ttu-id="42bf6-129">Határozzon meg nyelvspecifikus leírásokat a mértékegységhez.</span><span class="sxs-lookup"><span data-stu-id="42bf6-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="42bf6-130">A **Nyelv** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="42bf6-130">In the **Language** field, enter or select a value.</span></span>
10. <span data-ttu-id="42bf6-131">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="42bf6-131">In the **Description** field, type a value.</span></span>
11. <span data-ttu-id="42bf6-132">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="42bf6-132">Click **Save**.</span></span>
12. <span data-ttu-id="42bf6-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42bf6-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="42bf6-134">Egység átváltási szabályok definiálása</span><span class="sxs-lookup"><span data-stu-id="42bf6-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="42bf6-135">A **Művelet panelen** kattintson az **Egységek átváltása** elemre.</span><span class="sxs-lookup"><span data-stu-id="42bf6-135">On the **Action Pane**, click **Unit conversions**.</span></span> <span data-ttu-id="42bf6-136">Adjon meg szabályokat a mértékegységek átalakításához más mértékegységekről és -re a kijelölt egységosztályban.</span><span class="sxs-lookup"><span data-stu-id="42bf6-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="42bf6-137">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42bf6-137">Click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="42bf6-138">A **Tényező** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="42bf6-138">In the **Factor** field, enter a number.</span></span> <span data-ttu-id="42bf6-139">Átszámítási arány a forrás és a cél mértékegység között.</span><span class="sxs-lookup"><span data-stu-id="42bf6-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="42bf6-140">Például a centiméterről méterre való átváltási arány 100, mert egy méter 100 centiméterből áll.</span><span class="sxs-lookup"><span data-stu-id="42bf6-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="42bf6-141">A **Cél egység** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="42bf6-141">In the **To unit** field, enter or select a value.</span></span>
5. <span data-ttu-id="42bf6-142">A **Kerekítés** mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42bf6-142">In the **Rounding** field, select an option.</span></span> <span data-ttu-id="42bf6-143">Határozza meg, hogyan kell kerekíteni a konvertált értéket.</span><span class="sxs-lookup"><span data-stu-id="42bf6-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="42bf6-144">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="42bf6-144">Click **OK**.</span></span>
7. <span data-ttu-id="42bf6-145">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42bf6-145">Close the page.</span></span>


---
title: Pontozási mód létrehozása az ajánlatkérésekhez
description: Ez az eljárás bemutatja, hogyan lehet pontozási módszert létrehozni.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd8657098519391ee488025e175e1499c58a55ce
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429624"
---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="213b6-103">Pontozási mód létrehozása az ajánlatkérésekhez</span><span class="sxs-lookup"><span data-stu-id="213b6-103">Create a scoring method for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="213b6-104">Ez az eljárás bemutatja, hogyan lehet pontozási módszert létrehozni.</span><span class="sxs-lookup"><span data-stu-id="213b6-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="213b6-105">A pontozási módszer olyan feltételek együttesét jelenti, amelyek alapján összehasonlíthatóak az ajánlatkérésre válaszként érkezett ajánlatok.</span><span class="sxs-lookup"><span data-stu-id="213b6-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="213b6-106">Minősítheti például a szállítókat múltbeli teljesítményük, vállalatuk környezetbarát jellege, megfelelő együttműködő készségük alapján, vagy összehasonlíthatja az ajánlatokon szereplő árakat.</span><span class="sxs-lookup"><span data-stu-id="213b6-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="213b6-107">A pontozási módszer társítható egy meghirdetési típussal; ekkor az adott típusú ajánlatkérések alapértelmezett pontozási módszere a kiválasztott módszer lesz.</span><span class="sxs-lookup"><span data-stu-id="213b6-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="213b6-108">Ezeket a feladatokat jellemzően egy beszerzési vezető végezné el.</span><span class="sxs-lookup"><span data-stu-id="213b6-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="213b6-109">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.</span><span class="sxs-lookup"><span data-stu-id="213b6-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="213b6-110">Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Ajánlatkérés > Pontozás típusa.</span><span class="sxs-lookup"><span data-stu-id="213b6-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="213b6-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="213b6-111">Click New.</span></span>
3. <span data-ttu-id="213b6-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="213b6-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="213b6-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="213b6-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="213b6-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="213b6-114">Click Save.</span></span>
6. <span data-ttu-id="213b6-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="213b6-115">Click New.</span></span>
7. <span data-ttu-id="213b6-116">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="213b6-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="213b6-117">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="213b6-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="213b6-118">Ez a leírás a pontozási módszer nevével együtt jelenik meg, amennyiben kiválaszt egy pontozási módszert egy ajánlatkéréshez.</span><span class="sxs-lookup"><span data-stu-id="213b6-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="213b6-119">Írjon be egy számot a Kezdő érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="213b6-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="213b6-120">A tartomány meghatározza, hogy a beszerzési szakember mely határértékek között adhat pontszámot.</span><span class="sxs-lookup"><span data-stu-id="213b6-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="213b6-121">Amennyiben egy ajánlatkérést több pontozási feltétel szerint értékelnek, a bevitt pontértékek összeadódnak, és az ajánlatok a kapott összeg alapján hasonlíthatóak össze.</span><span class="sxs-lookup"><span data-stu-id="213b6-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="213b6-122">Írjon be egy számot a Záró érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="213b6-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="213b6-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="213b6-123">Click New.</span></span>
12. <span data-ttu-id="213b6-124">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="213b6-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="213b6-125">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="213b6-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="213b6-126">Írjon be egy számot a Kezdő érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="213b6-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="213b6-127">Írjon be egy számot a Záró érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="213b6-127">In the Range to field, enter a number.</span></span>


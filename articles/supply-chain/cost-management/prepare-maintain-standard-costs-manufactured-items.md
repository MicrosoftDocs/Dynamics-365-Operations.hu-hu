---
title: Felkészülés a gyártott cikkek elszámolóárának karbantartására
description: Ez a téma leírja a gyártott cikkek költségeinek karbantartásának előkészítésére irányuló lépéseket.
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a82b0a205ac6b7a86b9aca0771303469c6666c1
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187746"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a><span data-ttu-id="55a34-103">Felkészülés a gyártott cikkek elszámolóárának karbantartására</span><span class="sxs-lookup"><span data-stu-id="55a34-103">Prepare to maintain standard costs for manufactured items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55a34-104">Ez a téma leírja a gyártott cikkek költségeinek karbantartásának előkészítésére irányuló lépéseket.</span><span class="sxs-lookup"><span data-stu-id="55a34-104">This topic describes the steps for preparing to maintain costs for manufactured items.</span></span> <span data-ttu-id="55a34-105">A gyártott cikkek lépései kissé eltérnek a megvásárolt cikkek lépéseitől.</span><span class="sxs-lookup"><span data-stu-id="55a34-105">The steps for manufactured items differ slightly from the steps for purchased items.</span></span>

<span data-ttu-id="55a34-106">A termékekhez hozzárendelt szabályok kihatással lehetnek a költségszámításokra a szülő gyártott termékek felé.</span><span class="sxs-lookup"><span data-stu-id="55a34-106">Policies that are assigned to manufactured items can affect the cost calculations for the parent manufactured items.</span></span> <span data-ttu-id="55a34-107">Felkészüléshez a gyártott cikkek költségeinek karbantartására kövesse e lépéseket.</span><span class="sxs-lookup"><span data-stu-id="55a34-107">To prepare to maintain costs for manufactured items, follow these steps.</span></span>

1. <span data-ttu-id="55a34-108">Rendeljen a termékhez egy cikkmodellcsoportot.</span><span class="sxs-lookup"><span data-stu-id="55a34-108">Assign an item model group to the manufactured item.</span></span> 

   <span data-ttu-id="55a34-109">A cikkmodellcsoport azonosítja a használandó önköltségi árakat.</span><span class="sxs-lookup"><span data-stu-id="55a34-109">The item model group identifies that standard costs will be used.</span></span>

2. <span data-ttu-id="55a34-110">Rendeljen a termékhez egy cikkcsoportot.</span><span class="sxs-lookup"><span data-stu-id="55a34-110">Assign an item group to the manufactured item.</span></span> 

   <span data-ttu-id="55a34-111">A cikkcsoportok tartalmazzák azokat a főkönyvi számlákat, amelyek a termékre érvényesek.</span><span class="sxs-lookup"><span data-stu-id="55a34-111">The item group contains ledger accounts that apply to the manufactured item.</span></span> <span data-ttu-id="55a34-112">Egy elszámolóáras készletmodellel rendelkező termék főkönyvi számlái számos gyártási eltérést, költségváltozási eltérést és készletköltség átértékelést foglalhatnak magukba.</span><span class="sxs-lookup"><span data-stu-id="55a34-112">The ledger accounts for a manufactured item that has a standard cost inventory model include several production variances, the cost change variance, and the inventory cost revaluation.</span></span>

3. <span data-ttu-id="55a34-113">Rendelje a cikkhez a készlet mértékegységét.</span><span class="sxs-lookup"><span data-stu-id="55a34-113">Assign the inventory unit of measure to the item.</span></span> 

   <span data-ttu-id="55a34-114">A cikk költségei mindig a cikk készletbeli mértékegységében vannak kifejezve.</span><span class="sxs-lookup"><span data-stu-id="55a34-114">The item's costs are always expressed in the item's inventory unit of measure.</span></span>

4. <span data-ttu-id="55a34-115">Ne rendeljen költségcsoportot a gyártott termékhez, hacsak a cikk nem lesz alapanyagként (beszerzett termékként) kezelve.</span><span class="sxs-lookup"><span data-stu-id="55a34-115">Don't assign a cost group to the manufactured item unless the item will be treated as a purchased item.</span></span>

5. <span data-ttu-id="55a34-116">Rendeljen a gyártott termékhez egy anyagjegyzék-számítási csoportot.</span><span class="sxs-lookup"><span data-stu-id="55a34-116">Assign a bill of materials (BOM) calculation group to the manufactured item.</span></span> 

   <span data-ttu-id="55a34-117">A cikk anyagjegyzék-számítási csoportja határozza meg a vonatkozó figyelmeztetési feltételeket.</span><span class="sxs-lookup"><span data-stu-id="55a34-117">The item's BOM calculation group defines warning conditions that apply.</span></span> <span data-ttu-id="55a34-118">Így az anyagjegyzék-számítás végeztével figyelmeztető üzenetek hozhatók létre az esetleges számítási hibák eredetére vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="55a34-118">In that way, when a BOM calculation is done, warning messages can be generated about possible sources of calculation errors.</span></span> <span data-ttu-id="55a34-119">Például egy figyelmeztető üzenet hívhatja fel a figyelmet arra, ha egy aktív anyagjegyzék vagy útvonal nem létezik.</span><span class="sxs-lookup"><span data-stu-id="55a34-119">For example, a warning message can identify when an active BOM or route doesn't exist.</span></span> <span data-ttu-id="55a34-120">Az anyagjegyzék-számítási csoport tartalmaz egy alábontás-leállítási szabályt, amely jelzi, hogy mettől kell a cikket alapanyagként kezelni.</span><span class="sxs-lookup"><span data-stu-id="55a34-120">The BOM calculation group contains a stop explosion policy that indicates when a manufactured item should be treated as a purchased item.</span></span>

6. <span data-ttu-id="55a34-121">Ha a gyártott cikk költségei állandók, rendeljen a termékhez egy szokásos rendelési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="55a34-121">If the manufactured item has constant costs, assign a standard order quantity to it.</span></span> 

   <span data-ttu-id="55a34-122">A szokásos rendelési mennyiség az állandó költségek amortizációjának könyvelési adagmérete.</span><span class="sxs-lookup"><span data-stu-id="55a34-122">The standard order quantity is an accounting lot size for amortizing constant costs.</span></span> <span data-ttu-id="55a34-123">Példa állandó költségekre a beállítási idők az útvonalműveleteknél vagy egy állandó összetevőmennyiség egy anyagjegyzékben (AJ).</span><span class="sxs-lookup"><span data-stu-id="55a34-123">Examples of constant costs include setup times in routing operations and a constant component quantity in the BOM.</span></span>

7. <span data-ttu-id="55a34-124">Határozza meg a termék anyagjegyzékét.</span><span class="sxs-lookup"><span data-stu-id="55a34-124">Define the BOM for the manufactured item.</span></span> 

   <span data-ttu-id="55a34-125">Egy termék számára több anyagjegyzéket is meg lehet adni.</span><span class="sxs-lookup"><span data-stu-id="55a34-125">One or more BOM versions can be defined for the manufactured item.</span></span> <span data-ttu-id="55a34-126">Ellenőrizze, hogy a kívánt verziók jóváhagyott és aktív jelet kaptak-e, és hogy a dátum érvényessége megfelelő-e.</span><span class="sxs-lookup"><span data-stu-id="55a34-126">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="55a34-127">Az anyagjegyzékverzió vállalatszintű és hely specifikus lehet.</span><span class="sxs-lookup"><span data-stu-id="55a34-127">The BOM version can be company-wide or site-specific.</span></span>

8. <span data-ttu-id="55a34-128">Határozza meg a termék útvonalát.</span><span class="sxs-lookup"><span data-stu-id="55a34-128">Define the routing for the manufactured item.</span></span> 

   <span data-ttu-id="55a34-129">Egy termék számára több útvonalat is meg lehet adni.</span><span class="sxs-lookup"><span data-stu-id="55a34-129">One or more route versions can be defined for the manufactured item.</span></span> <span data-ttu-id="55a34-130">Ellenőrizze, hogy a kívánt verziók jóváhagyott és aktív jelet kaptak-e, és hogy a dátum érvényessége megfelelő-e.</span><span class="sxs-lookup"><span data-stu-id="55a34-130">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="55a34-131">Az útvonalverzió vállalatszintű és hely specifikus lehet.</span><span class="sxs-lookup"><span data-stu-id="55a34-131">The route version must be site-specific.</span></span>

<span data-ttu-id="55a34-132">Ha útvonaladatokat kíván használni a költségképzési célokra, az további előkészületi lépéseket igényel.</span><span class="sxs-lookup"><span data-stu-id="55a34-132">If you want to use routing information for costing purposes, additional preparation steps are required.</span></span> <span data-ttu-id="55a34-133">Például az útvonalműveletekhez rendelt költségkategóriáknak pontosaknak és hiánytalanoknak kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="55a34-133">For example, the cost categories that are assigned to routing operations must be correct and completed.</span></span>

## <a name="related-topics"></a><span data-ttu-id="55a34-134">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="55a34-134">Related topics</span></span>

[<span data-ttu-id="55a34-135">A legyártott cikkek állandó költségeinek amortizálása</span><span class="sxs-lookup"><span data-stu-id="55a34-135">Amortize constant costs for a manufactured item</span></span>](amortize-constant-costs-manufactured-item.md)

[<span data-ttu-id="55a34-136">Gyártható vagy beszerezhető termékek beállítása</span><span class="sxs-lookup"><span data-stu-id="55a34-136">Set up products that can be produced or procured</span></span>](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
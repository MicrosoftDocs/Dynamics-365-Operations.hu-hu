---
title: " Az áttároláshoz és a központi elosztáshoz tartozó szabályok és paraméterek beállítása"
description: Ez az eljárás bemutatja a Feltöltési szabályok létrehozásának lépéseit.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bccd92946783628dce37c3fd018e4dd927efd49
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412892"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="11c03-103"> Az áttároláshoz és a központi elosztáshoz tartozó szabályok és paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="11c03-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11c03-104">Ez az eljárás bemutatja a Feltöltési szabályok létrehozásának lépéseit.</span><span class="sxs-lookup"><span data-stu-id="11c03-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="11c03-105">A Feltöltési szabályok Áttárolás vagy Központi elosztás használatakor a termékek üzletekbe való elosztásának irányítására alkalmazhatóak.</span><span class="sxs-lookup"><span data-stu-id="11c03-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="11c03-106">Feltöltési szabályok beállíthatók üzletekre vagy üzletcsoportokra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="11c03-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="11c03-107">A szabály mindegyik sorára definiált súly határozza meg, hogyan történjen a termékmennyiségek üzletek közötti szétosztása, amikor Áttárolás vagy Központi elosztás alkalmazásánál Feltöltési szabályok adják az elosztási módszert.</span><span class="sxs-lookup"><span data-stu-id="11c03-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="11c03-108">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="11c03-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="11c03-109">Nyissa meg a következőt: Feltöltési szabályok.</span><span class="sxs-lookup"><span data-stu-id="11c03-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="11c03-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="11c03-110">Click New.</span></span>
3. <span data-ttu-id="11c03-111">Írjon be egy értéket a Feltöltési szabály mezőbe.</span><span class="sxs-lookup"><span data-stu-id="11c03-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="11c03-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="11c03-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="11c03-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="11c03-113">Click Save.</span></span>
6. <span data-ttu-id="11c03-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="11c03-114">Click Add.</span></span>
7. <span data-ttu-id="11c03-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="11c03-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="11c03-116">Választhat a Feltöltési hierarchia vagy a Csatorna típus között.</span><span class="sxs-lookup"><span data-stu-id="11c03-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="11c03-117">Az érték meghatározza, hogy kijelöléskor a Név csatornák egy hierarchiáját vagy egy adott csatornát fog jelenteni.</span><span class="sxs-lookup"><span data-stu-id="11c03-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="11c03-118">Ennél a példánál hagyja meg a Feltöltési hierarchia beállítást.</span><span class="sxs-lookup"><span data-stu-id="11c03-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="11c03-119">Válasszon egy értéket a Név mezőben.</span><span class="sxs-lookup"><span data-stu-id="11c03-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="11c03-120">Az alapértelmezett súlyérték a raktárnál meghatározott súly alapján kerül meghatározásra.</span><span class="sxs-lookup"><span data-stu-id="11c03-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="11c03-121">A Feltöltési szabály meghatározásához használható ez a súly, vagy a Súly mezőben megadható új súly.</span><span class="sxs-lookup"><span data-stu-id="11c03-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="11c03-122">Adjon meg egy számot a Súly mezőben.</span><span class="sxs-lookup"><span data-stu-id="11c03-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="11c03-123">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="11c03-123">Click Add.</span></span>
11. <span data-ttu-id="11c03-124">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="11c03-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="11c03-125">Válassza a „Csatorna” lehetőséget a Típus mezőben.</span><span class="sxs-lookup"><span data-stu-id="11c03-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="11c03-126">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="11c03-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="11c03-127">Adjon meg egy számot a Súly mezőben.</span><span class="sxs-lookup"><span data-stu-id="11c03-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="11c03-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="11c03-128">Click Save.</span></span>


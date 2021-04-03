---
title: Költségszámítási szint
description: Ez a témakör az anyagjegyzék (BOM) szintet írja le, amelynek neve Költségszámítás szint. Ez az Anyagjegyzék szint kizárja a termelési és a kötegelt rendeléseket a számításokból.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 1cfbbb6aadbd24a0352776285f6c60ff10f59549
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251026"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="e2b8b-104">Költségszámítási szint</span><span class="sxs-lookup"><span data-stu-id="e2b8b-104">Cost calculation level</span></span>

<span data-ttu-id="e2b8b-105">A **Költségszámítási szint** nevű anyagjegyzék (BOM) szint kizárja a termelési rendeléseket és a kötegelt rendeléseket a számításaiból.</span><span class="sxs-lookup"><span data-stu-id="e2b8b-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="e2b8b-106">Ez a szint akkor használatos, amikor költségszámítási verziókban a rendszer költség-számításokat futtat.</span><span class="sxs-lookup"><span data-stu-id="e2b8b-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="e2b8b-107">Olyan folyamatok, mint, például az újraszámítás és a készlet zárása során a rendszer a **Költségszint** anyagjegyzék szintet használja ehelyett.</span><span class="sxs-lookup"><span data-stu-id="e2b8b-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="e2b8b-108">A következő egyszerű forgatókönyv a **Költségszámítási szint** anyagjegyzék-szint és a **Költségtervezés szint** anyagjegyzék-szint közötti különbségeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="e2b8b-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="e2b8b-109">Három termék van: A, B és C. a C termék a B termék összetevője, a B termék pedig az A termék összetevője.</span><span class="sxs-lookup"><span data-stu-id="e2b8b-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="e2b8b-110">**A költségtervezési szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="e2b8b-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="e2b8b-111">**A termék:** 0</span><span class="sxs-lookup"><span data-stu-id="e2b8b-111">**Product A:** 0</span></span>
    - <span data-ttu-id="e2b8b-112">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="e2b8b-112">**Product B:** 1</span></span>
    - <span data-ttu-id="e2b8b-113">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="e2b8b-113">**Product C:** 2</span></span>

- <span data-ttu-id="e2b8b-114">**A költségszámítási szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="e2b8b-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="e2b8b-115">**A termék:** 0</span><span class="sxs-lookup"><span data-stu-id="e2b8b-115">**Product A:** 0</span></span>
    - <span data-ttu-id="e2b8b-116">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="e2b8b-116">**Product B:** 1</span></span>
    - <span data-ttu-id="e2b8b-117">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="e2b8b-117">**Product C:** 2</span></span>

<span data-ttu-id="e2b8b-118">Ezután létrejön egy termelési rendelés a C termékhez, és az A termék hozzáadódik a termelési rendelés anyagjegyzékéhez.</span><span class="sxs-lookup"><span data-stu-id="e2b8b-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="e2b8b-119">A rendelés becslése után a program az anyagjegyzék-szinteket a következő módon frissíti:</span><span class="sxs-lookup"><span data-stu-id="e2b8b-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="e2b8b-120">**A költségtervezési szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="e2b8b-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="e2b8b-121">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="e2b8b-121">**Product B:** 1</span></span>
    - <span data-ttu-id="e2b8b-122">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="e2b8b-122">**Product C:** 2</span></span>
    - <span data-ttu-id="e2b8b-123">**A termék:** 3</span><span class="sxs-lookup"><span data-stu-id="e2b8b-123">**Product A:** 3</span></span>

- <span data-ttu-id="e2b8b-124">**A költségszámítási szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="e2b8b-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="e2b8b-125">**A termék:** 0</span><span class="sxs-lookup"><span data-stu-id="e2b8b-125">**Product A:** 0</span></span>
    - <span data-ttu-id="e2b8b-126">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="e2b8b-126">**Product B:** 1</span></span>
    - <span data-ttu-id="e2b8b-127">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="e2b8b-127">**Product C:** 2</span></span>

<span data-ttu-id="e2b8b-128">Ez a viselkedés biztosítja, hogy a termelési rendelési anyagjegyzékeinek módosításai ne befolyásolják a későbbi költségszámításokat.</span><span class="sxs-lookup"><span data-stu-id="e2b8b-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Költségszámítási szint
description: Ez a témakör az anyagjegyzék (BOM) szintet írja le, amelynek neve Költségszámítás szint. Ez az Anyagjegyzék szint kizárja a termelési és a kötegelt rendeléseket a számításokból.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f7cde239107528a6bc2aeb0e424d024d4f3fb2a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839487"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="b4291-104">Költségszámítási szint</span><span class="sxs-lookup"><span data-stu-id="b4291-104">Cost calculation level</span></span>

<span data-ttu-id="b4291-105">A **Költségszámítási szint** nevű anyagjegyzék (BOM) szint kizárja a termelési rendeléseket és a kötegelt rendeléseket a számításaiból.</span><span class="sxs-lookup"><span data-stu-id="b4291-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="b4291-106">Ez a szint akkor használatos, amikor költségszámítási verziókban a rendszer költség-számításokat futtat.</span><span class="sxs-lookup"><span data-stu-id="b4291-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="b4291-107">Olyan folyamatok, mint, például az újraszámítás és a készlet zárása során a rendszer a **Költségszint** anyagjegyzék szintet használja ehelyett.</span><span class="sxs-lookup"><span data-stu-id="b4291-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="b4291-108">A következő egyszerű forgatókönyv a **Költségszámítási szint** anyagjegyzék-szint és a **Költségtervezés szint** anyagjegyzék-szint közötti különbségeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b4291-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="b4291-109">Három termék van: A, B és C. a C termék a B termék összetevője, a B termék pedig az A termék összetevője.</span><span class="sxs-lookup"><span data-stu-id="b4291-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="b4291-110">**A költségtervezési szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="b4291-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="b4291-111">**A termék:** 0</span><span class="sxs-lookup"><span data-stu-id="b4291-111">**Product A:** 0</span></span>
    - <span data-ttu-id="b4291-112">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="b4291-112">**Product B:** 1</span></span>
    - <span data-ttu-id="b4291-113">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="b4291-113">**Product C:** 2</span></span>

- <span data-ttu-id="b4291-114">**A költségszámítási szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="b4291-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="b4291-115">**A termék:** 0</span><span class="sxs-lookup"><span data-stu-id="b4291-115">**Product A:** 0</span></span>
    - <span data-ttu-id="b4291-116">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="b4291-116">**Product B:** 1</span></span>
    - <span data-ttu-id="b4291-117">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="b4291-117">**Product C:** 2</span></span>

<span data-ttu-id="b4291-118">Ezután létrejön egy termelési rendelés a C termékhez, és az A termék hozzáadódik a termelési rendelés anyagjegyzékéhez.</span><span class="sxs-lookup"><span data-stu-id="b4291-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="b4291-119">A rendelés becslése után a program az anyagjegyzék-szinteket a következő módon frissíti:</span><span class="sxs-lookup"><span data-stu-id="b4291-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="b4291-120">**A költségtervezési szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="b4291-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="b4291-121">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="b4291-121">**Product B:** 1</span></span>
    - <span data-ttu-id="b4291-122">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="b4291-122">**Product C:** 2</span></span>
    - <span data-ttu-id="b4291-123">**A termék:** 3</span><span class="sxs-lookup"><span data-stu-id="b4291-123">**Product A:** 3</span></span>

- <span data-ttu-id="b4291-124">**A költségszámítási szint** a következő anyagjegyzék-szinteket rendeli hozzá:</span><span class="sxs-lookup"><span data-stu-id="b4291-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="b4291-125">**A termék:** 0</span><span class="sxs-lookup"><span data-stu-id="b4291-125">**Product A:** 0</span></span>
    - <span data-ttu-id="b4291-126">**B termék:** 1</span><span class="sxs-lookup"><span data-stu-id="b4291-126">**Product B:** 1</span></span>
    - <span data-ttu-id="b4291-127">**C termék:** 2</span><span class="sxs-lookup"><span data-stu-id="b4291-127">**Product C:** 2</span></span>

<span data-ttu-id="b4291-128">Ez a viselkedés biztosítja, hogy a termelési rendelési anyagjegyzékeinek módosításai ne befolyásolják a későbbi költségszámításokat.</span><span class="sxs-lookup"><span data-stu-id="b4291-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: "A termelési különbözetek gyakori okai"
description: "Ez a cikk a termelési eltérések különböző formáinak forrásait ismerteti."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a61761a5c9d98befd67682e1790af5377b7a55e1
ms.openlocfilehash: 649dbf6148ba0f4d8f31b31c120a2939b7491d5f
ms.contentlocale: hu-hu
ms.lasthandoff: 10/13/2017

---

# <a name="common-sources-of-production-variances"></a><span data-ttu-id="2a77a-103">A termelési különbözetek gyakori okai</span><span class="sxs-lookup"><span data-stu-id="2a77a-103">Common sources of production variances</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2a77a-104">Ez a cikk a termelési eltérések különböző formáinak forrásait ismerteti.</span><span class="sxs-lookup"><span data-stu-id="2a77a-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="2a77a-105">Íme, néhány tipikus példa az **adag méret** eltéréseire:</span><span class="sxs-lookup"><span data-stu-id="2a77a-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="2a77a-106">A termelési rendelés helyes mennyisége eltér az elszámolóár számításához használt mennyiségtől.</span><span class="sxs-lookup"><span data-stu-id="2a77a-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="2a77a-107">A mennyiség adja az állandó költségek amortizációjának alapját.</span><span class="sxs-lookup"><span data-stu-id="2a77a-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="2a77a-108">A termelési rendelés állandó költségeinek értéke nem egyenlő az elszámolási ár számításánál használt állandó értékekkel.</span><span class="sxs-lookup"><span data-stu-id="2a77a-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="2a77a-109">A termelési rendelés során alkalmazott állandó értékek több okból is eltérőek lehetnek.</span><span class="sxs-lookup"><span data-stu-id="2a77a-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="2a77a-110">Az állandó költségek például reflektálhatnak a következő tényezőkre:</span><span class="sxs-lookup"><span data-stu-id="2a77a-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="2a77a-111">A termelési anyagjegyzék (BOM) vagy az útvonal manuális változtatásaira</span><span class="sxs-lookup"><span data-stu-id="2a77a-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="2a77a-112">Az eltérő anyagjegyzék verzió vagy az eltérő útvonal verzió választására a termelési rendelés során</span><span class="sxs-lookup"><span data-stu-id="2a77a-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="2a77a-113">A cikkhez rendelt anyagjegyzék verzió vagy útvonal verzió tervezett műszaki módosításaira</span><span class="sxs-lookup"><span data-stu-id="2a77a-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="2a77a-114">Íme, néhány tipikus példa a **termelési ár** eltéréseire:</span><span class="sxs-lookup"><span data-stu-id="2a77a-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="2a77a-115">Az útvonal tervezési művelet jelentett felhasználási költség kategóriája (illetve a költség kategória ára) nem egyezik meg, az alap költségszámítás során alkalmazott költség kategóriával.</span><span class="sxs-lookup"><span data-stu-id="2a77a-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="2a77a-116">A költségkategória árához tartozó önköltség eltér az elszámolóár számításában használt költségkategória árától.</span><span class="sxs-lookup"><span data-stu-id="2a77a-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="2a77a-117">Íme, néhány tipikus példa a **termelési mennyiség** eltéréseire:</span><span class="sxs-lookup"><span data-stu-id="2a77a-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="2a77a-118">Többet vagy kevesebbet ad ki egy összetevő anyagból.</span><span class="sxs-lookup"><span data-stu-id="2a77a-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="2a77a-119">Alá- vagy fölé jelenti az útvonaltervezés idejét.</span><span class="sxs-lookup"><span data-stu-id="2a77a-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="2a77a-120">A rendelendő mennyiséghez képest többet, vagy kevesebbet rendel a megfelelő mennyiségnél a fő cikkből.</span><span class="sxs-lookup"><span data-stu-id="2a77a-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="2a77a-121">Az összetevők kiadása és a műveletek jelentése azonban, a termelési rendelés mennyiségi rendelésétől függ.</span><span class="sxs-lookup"><span data-stu-id="2a77a-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="2a77a-122">Íme, néhány tipikus példa a **termékhelyettesítés** eltéréseire:</span><span class="sxs-lookup"><span data-stu-id="2a77a-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="2a77a-123">Olyan összetevő anyagot ad ki, amely nem szerepel a termelési anyagjegyzékben.</span><span class="sxs-lookup"><span data-stu-id="2a77a-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="2a77a-124">Manuálisan hozzáad a termelési anyagjegyzékhez és felhasználtként jelent egy összetevőt.</span><span class="sxs-lookup"><span data-stu-id="2a77a-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="2a77a-125">Jelenti egy cikk felhasználását, azonban nem adja azt hozzá manuálisak a termelési anyagjegyzékhez.</span><span class="sxs-lookup"><span data-stu-id="2a77a-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="2a77a-126">Manuálisan hozzáad egy műveletet a termelési útvonalhoz és teljesítettként jelenti a műveletet.</span><span class="sxs-lookup"><span data-stu-id="2a77a-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="2a77a-127">A termelési rendelés létrehozásakor, az alap költségszámításban használt anyagjegyzéktől eltérő anyagjegyzéket választ.</span><span class="sxs-lookup"><span data-stu-id="2a77a-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="2a77a-128">A termelési rendelés létrehozásakor, az alap költségszámításban használt útvonal verziótól eltérő útvonal verziót választ.</span><span class="sxs-lookup"><span data-stu-id="2a77a-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>





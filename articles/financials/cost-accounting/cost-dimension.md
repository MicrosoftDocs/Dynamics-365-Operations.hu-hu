---
title: "Dimenziók létrehozása és dimenziótagok importálása"
description: "A költségkönyvelés független modul, amely alapadatokat igényel más modulokból."
author: YuyuScheller
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0fb276e7d62e2f7c02934e74741c8cf74778fc12
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="create-dimensions-and-import-dimension-members"></a><span data-ttu-id="86c9b-103">Dimenziók létrehozása és dimenziótagok importálása</span><span class="sxs-lookup"><span data-stu-id="86c9b-103">Create dimensions and import dimension members</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="86c9b-104">A költségkönyvelés független modul, amely adatokat igényel más modulokból.</span><span class="sxs-lookup"><span data-stu-id="86c9b-104">Cost accounting is an independent module that requires data from other modules.</span></span> <span data-ttu-id="86c9b-105">Az adatok a következők szerint csoportosíthatók:</span><span class="sxs-lookup"><span data-stu-id="86c9b-105">This data is categorized into the following:</span></span>

-  <span data-ttu-id="86c9b-106">Költségösszetevők</span><span class="sxs-lookup"><span data-stu-id="86c9b-106">Cost elements</span></span>
-  <span data-ttu-id="86c9b-107">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="86c9b-107">Cost objects</span></span>
-  <span data-ttu-id="86c9b-108">Statisztikai dimenziók</span><span class="sxs-lookup"><span data-stu-id="86c9b-108">Statistical dimensions</span></span>

<span data-ttu-id="86c9b-109">Egy **költségösszetevő** a számlatükör valamely költségfüggő elemének felel meg.</span><span class="sxs-lookup"><span data-stu-id="86c9b-109">A **Cost element** corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="86c9b-110">A **költségobjektum** bármilyen típusú pénzügyi dimenziónak felel meg, például termékek, költséghelyek és projektek, amelyekre becslést kíván végezni, költségeket akar rendelni, vagy közvetlenül mérni szeretné őket.</span><span class="sxs-lookup"><span data-stu-id="86c9b-110">A **Cost object** corresponds to any type of financial dimension, such as products, cost centers, and projects that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="86c9b-111">A **statisztikai dimenzió** és a tagjai a nem monetáris tételek regisztrálására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="86c9b-111">A **Statistical dimension** and its members are used to register non-monetary entries.</span></span> <span data-ttu-id="86c9b-112">A statisztikai dimenziótagok felosztási alapként használhatók a költségfelosztásben és a felosztásban</span><span class="sxs-lookup"><span data-stu-id="86c9b-112">Statistical dimension members can be used as an allocation base in cost distribution and allocation</span></span> 

<span data-ttu-id="86c9b-113">A következő ábra bemutatja a költségkönyvelésben használt dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="86c9b-113">The following diagram illustrates the dimensions that are used in Cost accounting.</span></span>

<span data-ttu-id="86c9b-114">[![Költségkönyvelés dimenziók](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="86c9b-114">[![Cost accounting dimensions](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span></span>

<span data-ttu-id="86c9b-115">Miután a költségkönyvelésbe importálta az adatokat, különféle szempontok létrehozásához használhatja, hogy információkat nyújthasson a vezetőknek a szervezet minden szintjén.</span><span class="sxs-lookup"><span data-stu-id="86c9b-115">After the data is imported into Cost accounting, you can use it to build various perspectives that provide insights to managers at all levels of the organization.</span></span> <span data-ttu-id="86c9b-116">Az alábbi témakörök a dimenziók létrehozásával és a dimenziótagok importálásával kapcsolatban nyújtanak tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="86c9b-116">The following topics provide information about creating dimensions and importing dimension members.</span></span> 

-  [<span data-ttu-id="86c9b-117">Költségösszetevő-dimenziók</span><span class="sxs-lookup"><span data-stu-id="86c9b-117">Cost element dimensions</span></span>](cost-elements.md)
-  [<span data-ttu-id="86c9b-118">Költségösszetevők létrehozása (feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="86c9b-118">Create cost elements (Task guide)</span></span>](./tasks/create-cost-elements.md)
-  [<span data-ttu-id="86c9b-119">Költségobjektum-dimenziók</span><span class="sxs-lookup"><span data-stu-id="86c9b-119">Cost object dimensions</span></span>](cost-objects.md)
-  [<span data-ttu-id="86c9b-120">Költségösszetevők létrehozása (feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="86c9b-120">Create cost elements (Task guide)</span></span>](./tasks/create-cost-objects.md)
-  [<span data-ttu-id="86c9b-121">Költségösszetevő-dimenziótagok hozzárendelése a dimenziótagok általános készletéhez</span><span class="sxs-lookup"><span data-stu-id="86c9b-121">Map cost element dimension members to a common set of dimension members</span></span>](map-cost-elements-dimension-members.md)
-  [<span data-ttu-id="86c9b-122">Költségösszetevő-dimenzió feltérképezése (feladat-útmutató)</span><span class="sxs-lookup"><span data-stu-id="86c9b-122">Map a cost element dimension (Task guide)</span></span>](./tasks/map-cost-element-dimension.md)
-  [<span data-ttu-id="86c9b-123">Statisztikai dimenziótagok és statisztikaimérték-szolgáltató sablonok</span><span class="sxs-lookup"><span data-stu-id="86c9b-123">Statistical dimension members and statistical measure provider templates</span></span>](statistical-measure-provider-template.md)







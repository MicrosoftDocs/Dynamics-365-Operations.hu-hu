--- 
title: "Előd hozzáadása termelésifolyamat-tevékenységhez"
description: "A termelésifolyamat-verziókban az összes tevékenységet sorba kell rendezni."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 71fbbaf645f8e8ac4cf406f67c59a9ec4cfe5ca2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="27ebb-103">Előd hozzáadása termelésifolyamat-tevékenységhez</span><span class="sxs-lookup"><span data-stu-id="27ebb-103">Add a predecessor to a production flow activity</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="27ebb-104">A termelésifolyamat-verziókban az összes tevékenységet sorba kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="27ebb-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="27ebb-105">Egy tevékenység egy vagy több megelőző és követő tevékenységgel rendelkezhet.</span><span class="sxs-lookup"><span data-stu-id="27ebb-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="27ebb-106">Ez az eljárás azt szemlélteti, hogyan lehet megelőző tevékenységet társítani egy tevékenységhez.</span><span class="sxs-lookup"><span data-stu-id="27ebb-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="27ebb-107">A feladat elvégzéséhez olyan termelési folyamatra van szükség, amelynek olyan Vázlat verziója van, amelynek van legalább két kapcsolható tevékenysége.</span><span class="sxs-lookup"><span data-stu-id="27ebb-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="27ebb-108">További információért olvassa el a „Lean manufacturing: Termelési folyamatok és tevékenységek” című ismertetőt.</span><span class="sxs-lookup"><span data-stu-id="27ebb-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="27ebb-109">Termelési folyamat és verzió megkeresése</span><span class="sxs-lookup"><span data-stu-id="27ebb-109">Find the production flow and version</span></span>
1. <span data-ttu-id="27ebb-110">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="27ebb-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="27ebb-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="27ebb-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="27ebb-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="27ebb-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="27ebb-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="27ebb-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="27ebb-114">Kattintson a Tevékenységek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="27ebb-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="27ebb-115">Jelöljön ki egy tevékenységet, és adjon hozzá egy megelőző tevékenységet</span><span class="sxs-lookup"><span data-stu-id="27ebb-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="27ebb-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="27ebb-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="27ebb-117">Kattintson a Megelőző hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="27ebb-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="27ebb-118">A Tevékenység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="27ebb-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="27ebb-119">Írjon be egy számot a Ciklusidőarány mezőbe.</span><span class="sxs-lookup"><span data-stu-id="27ebb-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="27ebb-120">A tevékenységkapcsolatok alapértelmezett ciklusidőaránya: 1.</span><span class="sxs-lookup"><span data-stu-id="27ebb-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="27ebb-121">Ez azt feltételezi, hogy mindkét tevékenység azonos ütemben vagy taktidő szerint fut.</span><span class="sxs-lookup"><span data-stu-id="27ebb-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="27ebb-122">Ha a megelőző tevékenység magasabb ütemben (alacsonyabb taktidővel) fut, az aránynak 1-nél kisebbnek kell lennie, ha a megelőző tevékenység futási üteme alacsonyabb (magasabb taktidő), a ciklusidő aránya 1-nél nagyobb.</span><span class="sxs-lookup"><span data-stu-id="27ebb-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="27ebb-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="27ebb-123">Click OK.</span></span>



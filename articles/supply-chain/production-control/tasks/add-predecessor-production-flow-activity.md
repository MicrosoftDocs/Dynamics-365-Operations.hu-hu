---
title: Előd hozzáadása termelésifolyamat-tevékenységhez
description: A termelésifolyamat-verziókban az összes tevékenységet sorba kell rendezni.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d76ec6ac928228011f42355bebd553576bcfd275
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255445"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="b7f1d-103">Előd hozzáadása termelésifolyamat-tevékenységhez</span><span class="sxs-lookup"><span data-stu-id="b7f1d-103">Add a predecessor to a production flow activity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b7f1d-104">A termelésifolyamat-verziókban az összes tevékenységet sorba kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="b7f1d-105">Egy tevékenység egy vagy több megelőző és követő tevékenységgel rendelkezhet.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="b7f1d-106">Ez az eljárás azt szemlélteti, hogyan lehet megelőző tevékenységet társítani egy tevékenységhez.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="b7f1d-107">A feladat elvégzéséhez olyan termelési folyamatra van szükség, amelynek olyan Vázlat verziója van, amelynek van legalább két kapcsolható tevékenysége.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="b7f1d-108">További információért olvassa el a „Lean manufacturing: Termelési folyamatok és tevékenységek” című ismertetőt.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="b7f1d-109">Termelési folyamat és verzió megkeresése</span><span class="sxs-lookup"><span data-stu-id="b7f1d-109">Find the production flow and version</span></span>
1. <span data-ttu-id="b7f1d-110">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="b7f1d-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b7f1d-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b7f1d-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b7f1d-114">Kattintson a Tevékenységek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="b7f1d-115">Jelöljön ki egy tevékenységet, és adjon hozzá egy megelőző tevékenységet</span><span class="sxs-lookup"><span data-stu-id="b7f1d-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="b7f1d-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="b7f1d-117">Kattintson a Megelőző hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="b7f1d-118">A Tevékenység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="b7f1d-119">Írjon be egy számot a Ciklusidőarány mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="b7f1d-120">A tevékenységkapcsolatok alapértelmezett ciklusidőaránya: 1.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="b7f1d-121">Ez azt feltételezi, hogy mindkét tevékenység azonos ütemben vagy taktidő szerint fut.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="b7f1d-122">Ha a megelőző tevékenység magasabb ütemben (alacsonyabb taktidővel) fut, az aránynak 1-nél kisebbnek kell lennie, ha a megelőző tevékenység futási üteme alacsonyabb (magasabb taktidő), a ciklusidő aránya 1-nél nagyobb.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="b7f1d-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b7f1d-123">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: "Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások"
description: "Ez a témakör az elszámolóárakra vonatkozó költségszámítási verziókra érvényes korlátozásokat mutatja be."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: c0383f78ea5cfa42183e0bfe8a96d7d3866766e7
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---


#  <a name="restrictions-on-costing-versions-for-standard-costs"></a><span data-ttu-id="2fbcf-103">Az elszámolóárakkal kapcsolatos költségszámítási verziókra vonatkozó korlátozások</span><span class="sxs-lookup"><span data-stu-id="2fbcf-103">Restrictions on costing versions for standard costs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2fbcf-104">Ez a témakör az elszámolóárakra vonatkozó költségszámítási verziókra érvényes korlátozásokat mutatja be.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-104">This topic describes the restrictions that apply to a costing version for standard costs.</span></span> 

<span data-ttu-id="2fbcf-105">A következő korlátozások segítenek biztosítani a szabványos költségszámítási elvek alkalmazását:</span><span class="sxs-lookup"><span data-stu-id="2fbcf-105">The following restrictions help guarantee adherence to standard costing principles:</span></span>

-  <span data-ttu-id="2fbcf-106">A cikkek költségében szerepelnie kell a költségeknek.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-106">Charges must be included in an item's cost.</span></span> <span data-ttu-id="2fbcf-107">A legyártott cikkhez tartozó költség az anyagjegyzékben és az útvonaladatokban szereplő amortizált állandó költséget képviseli.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-107">The charges for a manufactured item represent the amortized constant costs in the bill of materials (BOM) and route information.</span></span> <span data-ttu-id="2fbcf-108">Emiatt a költségeknek szerepelnie kell az egységköltségben.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-108">Therefore, the charges must be included in the unit cost.</span></span> <span data-ttu-id="2fbcf-109">A beszerzett cikkek költsége szintén szerepel a cikk egységköltségében.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-109">The charges for a purchased item are also included in the item's unit cost.</span></span>

-  <span data-ttu-id="2fbcf-110">A legyártott cikkek önköltségi árszámításának az elszámolóárakhoz tartozó költségszámítási verzióban szereplő költségrekordokon kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-110">Calculation of standard costs for manufactured items must be based on the cost records in a costing version for standard costs.</span></span> <span data-ttu-id="2fbcf-111">Költségadatok egyéb forrásait csak tervezett költségekhez tartozó költségszámítási verzióhoz lehet felhasználni, például beszerzett cikkekre vonatkozó, a beszerzési árakat meghatározó kereskedelmi megállapodások esetében.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-111">Alternative sources of cost data can be used only with a costing version for planned costs, such as purchase price trade agreements for purchased items.</span></span> <span data-ttu-id="2fbcf-112">Az alternatív költségadatforrásokat az anyagjegyzék-számítási csoport határozza meg.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-112">Alternative sources of cost data are defined by the BOM calculation group.</span></span>

-  <span data-ttu-id="2fbcf-113">Az anyagjegyzék-számításokhoz egyszintű alábontást kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-113">BOM calculations must be performed in a single-level explosion mode.</span></span>

<span data-ttu-id="2fbcf-114">Az elszámolóárakhoz tartozó cikk-költség adatokat át lehet másolni az elszámolóárakat vagy tervezett költségeket tartalmazó másik költségszámítási verzióba.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-114">The item cost data for standard costs can be copied to another costing version that contains standard costs or planned costs.</span></span> <span data-ttu-id="2fbcf-115">A tervezett költségekre vonatkozó cikk-költség adatokat azonban olyan költségszámítási verzióba nem lehet másolni, amely elszámolóárakat tartalmaz, mert a témakörben feljebb ismertetett megkötések nem érvényesek a tervezett költségekre.</span><span class="sxs-lookup"><span data-stu-id="2fbcf-115">However, the item cost data for planned costs can't be copied to a cost version that contains standard costs, because the restrictions that are listed earlier in this topic don't apply to planned costs.</span></span>

<a name="related-topics"></a><span data-ttu-id="2fbcf-116">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="2fbcf-116">Related topics</span></span>
--------

[<span data-ttu-id="2fbcf-117">Költségszámítási verziók</span><span class="sxs-lookup"><span data-stu-id="2fbcf-117">Costing versions</span></span>](costing-versions.md)

[<span data-ttu-id="2fbcf-118">Elszámoló árak frissítése nem-termelő jellegű környezetben</span><span class="sxs-lookup"><span data-stu-id="2fbcf-118">Update standard costs in a non-manufacturing environment</span></span>](update-standard-costs-non-manufacturing-environment.md)

[<span data-ttu-id="2fbcf-119">Felkészülés a gyártott cikkek elszámolóárának karbantartására</span><span class="sxs-lookup"><span data-stu-id="2fbcf-119">Prepare to maintain standard costs for manufactured items</span></span>](update-standard-costs-manufacturing-environment.md)



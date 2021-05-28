---
title: Hiányzó mezőbeállítások cikkmodellcsoportoknak egy másik jogi személybe való másolásakor
description: Hiányzó mezőbeállítások vannak a cikkmodellcsoportoknak egy másik jogi személybe való másolásakor.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026570"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a><span data-ttu-id="2224f-103">Hiányzó mezőbeállítások cikkmodellcsoportoknak egy másik jogi személybe való másolásakor</span><span class="sxs-lookup"><span data-stu-id="2224f-103">Missing field settings when item model groups are copied to another legal entity</span></span>

<span data-ttu-id="2224f-104">Tudásbáziscikk száma: 4612800</span><span class="sxs-lookup"><span data-stu-id="2224f-104">KB number: 4612800</span></span>

## <a name="symptoms"></a><span data-ttu-id="2224f-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="2224f-105">Symptoms</span></span>

<span data-ttu-id="2224f-106">Ha cikkmodellcsoportokat *Cikkmodellcsoport készlet házirend* entitás használatával másol egy másik jogi személybe (vállalat), néhány mezőbeállítás (például a készletmodell és a leírás) hiányzik a cél jogi személy új modellcsoportjaból.</span><span class="sxs-lookup"><span data-stu-id="2224f-106">When you copy item model groups to another legal entity (company) by using the *Item model group inventory policies* entity, some field settings (for example, the inventory model and description) are missing in the new model group in the destination legal entity.</span></span>

## <a name="resolution"></a><span data-ttu-id="2224f-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="2224f-107">Resolution</span></span>

<span data-ttu-id="2224f-108">Ha egy cikkmodellcsoport teljes másolatát egy másik jogi személynek is létre kell hoznia, akkor a cikkmodellcsoport készletirányelvei, a cikkmodellcsoporthoz társított cikkmodellcsoport készletirányelveket (`InventInventoryPolicyEntity`) és a költségforgalom-feltételezés házirendjeit (`InventCostFlowAssumptionPolicyEntity`) is át kell másolnia.</span><span class="sxs-lookup"><span data-stu-id="2224f-108">To create a complete copy of an item model group to another legal entity, you must also select both the item model group inventory policies (`InventInventoryPolicyEntity`) and the cost flow assumption policies (`InventCostFlowAssumptionPolicyEntity`) that are associated with the item model group.</span></span>
